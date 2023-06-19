
* [Third Edition Textbook]([bryant (cmu.edu)](http://csapp.cs.cmu.edu/3e/pieces/preface3e.pdf))
* [Third Edition Git](https://github.com/bitwitch/csapp)
* [CS:APP3e, Bryant and O'Hallaron (cmu.edu)](http://csapp.cs.cmu.edu/3e/students.html)
* [Guide to x86 Assembly (virginia.edu)](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html) (Module 2)
* http://csapp.cs.cmu.edu/3e/simguide.pdf


---


From Teams with Alex et al:

It is also a place where students should be exposed to the sheer coolness of systems without being drowned in the technical. This is a hard balance to find.

For example,

[[Explaining how control structures in C map to assembly]] should be in CSCI 1120

- Interpreting a stack frame of a function call should be (in my opinion) in CSCI 2122, once students know what a function is.
- [[Compiling, disassembling, and running, and observing C programs]] (in GDB)
- [[ C programs on Timberlea]] should be CSCI 1120
- Writing C programs should be in CSCI 2122.
- [[Reading and tracing IA32 x86]] should be in CSCI 1120
- Writing small snippets of IA32 x86 could be in CSCI 2122
- [[Interpreting binary data and converting]] (by hand) between formats
- Writing programs that manipulate binary data should be in CSCI 2122
- Describing the [[layer model for systems]] with use of examples

This is my own perspective on the division between CSCI 1120 and CSCI 2122.

1. Students taking CSCI 1120 are likely to have never programmed before or touched a command-line. We must expect this as the mode, as students who take CSCI 1105 in the fall take CSCI 1120 as well.
2. I feel that CSCI 1120 should not be a gate-keeper course. It is intended as an introductory course to computer systems.
3. I do not expect students to write C in CSCI 1120. I do not expect students to know what or write a function in any language until the third month of the term.
4. I do expect students to be able to understand a C program consisting of a single main() function, which may make calls to standard library functions. I expect this to happen by the mid-point of the term. **I was thinking that we should update the calendar description to recommend that students should have prior programming experience or be taking an intro to programming at the same time.**
5. I expect that students doing CSCI 1120 only have Academic Math 12 (some may have more).
6. I do expect students to be able to learn to use a command-line interface.
7. I do expect students to be able to learn some simple command-line tools such as
    
    1. ssh into timberlea
    2. directory and file manipulation: cd, ls, mkdir, rm,
    3. objdump
    4. gcc (to compile provided programs)
    5. gdb to load a program and step through the code
    
    - **I do not expect students to learn unix administration beyond the above**


---
# Content Areas

Numbers: Binary, Decimal, Hexadecimal
- Unsigned binary numbers
- Binary, hex and octal
- ASCII and Unicode
- 
Encoding
- signed binary numbers: two's compliment
- floating point numbers
- graphics
- arrays (optional)
- floating point arithmetic (optional)
- records (optional)
- image and video data (optional)
- audio (optional)
- naming numerous buts (optional)

Combinatorial Logic
- Combinational Circuits
- Gates, truth tables, and logic equations
- Combinational Logic (optional)

Multiple bit components and memory
- decoders, muxes, and adders
- Memory elements: Flip-flops, latches, and registers
- Registers, register files

Components of a CPU
- Constructing a basic ALU
- Clocks
- Timing diagrams

RAM
- SRAM and DRAM
- RAM design
- Buses
- Virtual memory
- Chip economics (optional)
- Composing memory (optional)

MIPS Processor Design
- Processor Design
- lw, sw, addi, add, Behavior
- j/jal
- beq/bne
- slt, sub, Verilog (optional)
- VHDL

MIPS Assembly Part 1
- Programmable processor concept
- lw, sw: Load and store instructions
- addi, add: Add instructions
- beq, bne, j : Branch and jump instructions
- A small assembly program
- Memory alignment and endianness (optional)
- Comments (optional)
- sub, mul: Subtraction and multiplication instructions (optional)
- slt: Set on less than instruction (optional)
- Input/ Output (optional)

MIPS Assembly Part 2
- instruction summary
- simulators
- load and store with offsets
- jal/ jr: subroutine instructions
- Assembly program example: Subroutines
- Subroutines and the program stack
- Machine instruction (optional)
- Jump / branch immediates (optional)
- Assemblers (optional)
- Flowcharts and assembly programming (optional)

C to assembly. Expressions and conditionals
- Assignments
- Expressions
- Conserving registers
- if-else
- if-else expressions

C to assembly, Arrays and Strings
- Arrays and strings

C to assembly, Loops and Functions
- Loops 
- Functions
- Compilers

Troubleshooting Process
- Hypotheses and tests
- logic of troubleshooting
- creating hypotheses
- examples

Programme Debugging
- basic debugging

Other
- a survey of RISC architectures for desktop, server, and embedded computers
- intel 80x86
- VAX architecture
- IBM 360/370 architecture for mainframe
- Historical perspectives and references
