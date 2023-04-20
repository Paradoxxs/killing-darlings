# RE Script

### Shellcode

#### Analysis

#### Identification

Most shellcode need to perform task, to setup the execution of it logic. we can use this to spot shellcode patterns in binary files using xorsearch

```
exorsearch -W -d 3 sample.bin
```

Emulating shellcode execution with scdbg

```
scdbg /f sample.bin
```

### tools

| Tool       | description                   |
| ---------- | ----------------------------- |
| scdbg      | emulate shellcode             |
| runsc      | debug shellcode               |
| shcode2exe | Compile shellcode into an exe |

## Python

Python can be compiled into exe files, luckily they can be uncompiled back to the source code.

[unpy2exe](https://github.com/matiasb/unpy2exe) [uncompyle2](https://github.com/wibiti/uncompyle2)
