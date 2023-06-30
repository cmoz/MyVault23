> This project could be used as an integrative exercise maybe later. It is a bit hard for 1120, but I argue not if taken as an analytical/research exercise rather than a programming exercise.

There is a fair chance that GPT can explain this code just as much. Students should decide whether doing this will ultimately help them discover key concepts and understand them enough to be tested on them in a paper-based testing environment.

# Problem
The project `24bitfloat.c` is a strange program that set to 0 the lowest order bits in a 32-bit IEEE 754 floating point value. In a small group, or by yourself, explore each line of code to trace how this program executes.

## Objectives
- Students do not panic when encountering complexity
- Students research and figure out what is the difference between a `uint32_t` and and `unsigned int`
- Students research and figure out the bit-wise operation `&`. It is in the textbook. 
- Students can explain why the bitwise operations removes the information in the lowest order bit by connecting to lecture content on hexadecimal notation.

### Todo
- [ ] Expand code to perform only 1 operation per statement.
- [ ] Adjust inline comments to not reveal too much. 
- [ ] Compare encoding error of 32- and 24-bit with respect to 64-bit encoding?



This is an int datatype that is unsigned guaranteed to be 32 bits. To use it you need to include the stdint.h. If you are sure that the default `unsigned int` type is always going to be 32 bits, you may be able to just substitute `unsigned int` in its place. But using an explicit 32 bit datatype is preferable. standard types (`int8_t`, `uint8_t` ... `uint32_t`)