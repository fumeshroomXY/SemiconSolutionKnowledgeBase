# LLVM
**LLVM** originally stood for **Low Level Virtual Machine**, but today the project is simply called LLVM because it has grown far beyond a virtual machine.

LLVM is a **compiler infrastructure framework** used to build compilers, language runtimes, optimization tools, and code analysis tools.

## Analogy

Imagine building cars.

- A **programming language** = a car design (Toyota, Honda, Tesla)
- A **compiler** = the factory that builds the car
- **LLVM** = a set of factory machines that many car companies share

Instead of every language team building their own optimizer and code generator, they can reuse LLVM.

## What LLVM actually does

Let's say someone invents a new language called *ELang*.

Without LLVM:
```
ELang
↓
Need to write:
  - parser
  - optimizer
  - x86 code generator
  - ARM code generator
  - RISC-V code generator
```
That's an enormous amount of work.

With LLVM:
```
ELang
    ↓
Frontend (your code, parser, grammar check)
    ↓
LLVM IR (Intermediate Representation)
    ↓
LLVM optimizer
    ↓
x86 / ARM / RISC-V machine code
```

You only need to convert your language into LLVM IR.

LLVM takes care of:

- optimization
- register allocation
- instruction scheduling
- machine code generation
- multiple CPU architectures

## What does IR mean?
### Real-world analogy

Imagine translating books.
```
Chinese → English
Japanese → English
French → English
```
Suppose every language had to translate directly into every other language:
```
Chinese → Japanese
Chinese → French
Japanese → French
...
```
That becomes messy.

Instead, use a common intermediate language:
```
Chinese
Japanese  → English → Target Language
French
```
LLVM IR is that "common language" for compilers.
