# Calculator — x86 Assembly (8086)

A simple menu-driven calculator written in **x86 (8086) assembly language**, built as a
Computer Organization & Assembly Language (COAL) final project. It runs in DOS / DOSBox
using the MASM or TASM toolchain and uses BIOS/DOS interrupts (`INT 21h`) for all I/O.

## Features

| Operation       | Key | Status        |
| --------------- | --- | ------------- |
| Addition        | `A` | ✅ Working      |
| Subtraction     | `S` | ✅ Working      |
| Multiplication  | `M` | 🚧 Scaffolded (commented out) |
| Division        | `D` | 🚧 Scaffolded (commented out) |
| Exit            | `E` | ✅ Working      |

> **Note:** The multiplication and division routines exist in [src/calculator.asm](src/calculator.asm)
> but are currently commented out. Addition and subtraction operate on single-digit input.

## Project structure

```
.
├── src/
│   └── calculator.asm      # Main assembly source
├── docs/
│   ├── project-proposal.docx
│   └── presentation.pptx
├── .gitignore
├── LICENSE
└── README.md
```

## Requirements

- [DOSBox](https://www.dosbox.com/) (to emulate a DOS environment on modern systems)
- An 8086 assembler + linker — **MASM** (`masm.exe` / `link.exe`) or **TASM** (`tasm.exe` / `tlink.exe`)

## Build & run

Inside DOSBox, mount the folder containing the assembler and the source file, then:

### Using MASM

```dos
masm calculator.asm;
link calculator.obj;
calculator.exe
```

### Using TASM

```dos
tasm calculator.asm
tlink calculator.obj
calculator.exe
```

## How it works

The program prints a menu, reads a single key for the chosen operation, then prompts for
two single-digit numbers. Core helper procedures:

- `print` (macro) — prints a `$`-terminated string via `INT 21h`, function `09h`
- `input` — reads one character via `INT 21h`, function `01h`
- `Output` — prints one character via `INT 21h`, function `02h`
- `enterkey` — emits a CR/LF newline

## Author

**Saad Nadeem** — COAL Final Project
