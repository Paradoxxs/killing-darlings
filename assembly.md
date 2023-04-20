# Assembly

Stack pointer (ESP) points to value at the top of the stack. and changes with instructions like _PUSH, POP, CALL, LEAVE and RET_

How it work is that in the function prologue, that the EBP register is saved onto the stack, which is done with _PUSH EBP_. This Allows it to be restored once the function have finished, The EBP that was _push_ on the stack is called the Saved Frame Pointer (SFP). Next is to copy the current value of the stack pointer (ESP) to the EBP register, with _mov EBP, ESP_.\
When EBP is set up in the function prologue, it means that when you reference local variable using EBP minus value (for example, \[EBP –8]). And function parameter using EBP plus value (for example, \[EBP + 8]).\\

EBP (Frame pointer) is an reference point for the system, to return to after the function call have finished.\
EBP - value = local variables created inside the function call(registers may also be used)\
EBP + value = parameters that was push onto the stack before the function was called.

During prologue the reverse needs to happen. First the local variable needs to be _pop_ off the stack. then the EBP is moved into the ESP, and pop the old frame pointer into EBP. finally it uses the RET operation to return to the called address.

**Stack example:**

| Value          | location |
| -------------- | -------- |
| ...            |          |
| var2           | ebp-c    |
| var1           | ebp-8    |
| var0           | ebp-4    |
| sfp            | ebp      |
| return address | ebp-4    |
| arg0           | EBP+8    |
| arg1           | EBP+c    |
| arg2           | EBP+10   |
| ...            |          |

#### How opcode interact with the stack

| opcode        | stack operation                         |
| ------------- | --------------------------------------- |
| **push eax**  |                                         |
|               | sub esp, 4                              |
|               | mov \[ESP], eax                         |
| **pop eax**   |                                         |
|               | mov eax, \[ESP]                         |
|               | add esp, 4                              |
| **call func** |                                         |
|               | sub esp, 4                              |
|               | mov \[esp], address of next instruction |
|               | mov eip, function address               |
| **ret**       |                                         |
|               | mov eip, \[esp]                         |
|               | add esp,4                               |

**Passing values in x86**

| arg   | register    |
| ----- | ----------- |
| arg 0 | \[EBP+0x8]  |
| arg 1 | \[EBP+0XC]  |
| arg 2 | \[EBP+0X10] |
| arg 3 | \[EBP+0X14] |

### Resorces

* https://en.wikibooks.org/wiki/X86\_Assembly/X86\_Architecture
* http://unixwiz.net/techtips/x86-jumps.html
* http://unixwiz.net/techtips/win32-callconv-asm.html

## Control flow

#### Switch case

Execute one code block out of many based on an control value The address for each code block is sotred in an array.\
What you most likely will see is jmp \[varible\*4]

C code:

```c
switch(varible) {
    case 0:
    code
    break;
    ...
    case n:
    code
    break;
    default:
    code
    break;
}
```

Assembly:

```
mov eax, var1
cmp eax,1
ja end
jmp code_block_address_table[eax*4]
case_0: (offset 0x1000)
code
jmp end
case:1 (offset 0x2000)
code
end:
```
