# Ghidra

## Ghidra

Ghidra is a software reverse engineering suite of tools developed by the National Security Agency (NSA), It a free and open source software. Ghira inclues a disassembler to support static code analysis. The decompiler will recreate the code in pseudo _C_.

Ghidra GUI is based on Java, and for this reasons requires you to have installed java on the system.

On windows you can use the following command to install java if you have winget installed

```
winget install -e --id Oracle.JavaRuntimeEnvironment
```

It possible to automate some of the analysis within Ghidra using both Java and python scripts.\\

## Usage

### Setup

#### Listing fields

#### Ghidra-data

[Ghidra-data](https://github.com/0x6d696368/ghidra-data) contains typeinfo that will allow Ghidra to automatic add labes to function calls

### Function call tree

### Symbol table

### Shortcuts

| Key          | description              |
| ------------ | ------------------------ |
| L            | Add label                |
| E            | Set equate               |
| ;            | Create comment           |
| ctrl+t       | symbol table             |
| alt+⬅️       | Go back                  |
| alt+➡️       | Go forward               |
| ctrl+shift+f | show function references |
| T            | Set data type            |
| middlemouse  | highlight                |

### Extension

#### Ghidra typeinfo

Clone the ghidra-data project

```
git clone https://github.com/0x6d696368/ghidra-data
```

### Darkmode

Built in dark mode Edit → Tool Options → Tool\
enable "Use Inverted Colors" \and restart Ghidra."

The problem with their built in darkmode is that it look like shit.

I like https://github.com/zackelia/ghidra-dark, simple git clone the project

```
python .\install.py --path ghidra_10.1.5_PUBLIC
```

### Types

| operator | description                                 |
| -------- | ------------------------------------------- |
| lpcwstr  | long pointer wide string (possible unicode) |

