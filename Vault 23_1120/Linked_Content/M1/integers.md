Overflow show_integer [[int README]] 

# Pre-problem
> Encoding a number using the pure binary number system is called a `unsigned int`, or unsigned integer. However, it is important to have a kind of integer that can express negative values. 
> Q1 - What is the least number of bits needed to encode whether a number is positive or negative?
> Q2 - What is the consequence of using 1 bit to encode the sign on the range of possible values on byte can encode? 
> 	A) Reduce by 1 the range, B) Half the range, C) Reduce by 2 the range

# Lecture code-along
## Two's complement integer
There are many ways to do this such as concatenating 1-bit sign and n-1 bit value. But this intuitive way to do this would lead to less efficient CPU architectures. 

Two's complement allows a CPU to use exactly the same circuitry to treat all numbers the same, and remove the need to hardcode a SUBTRACT operation.

Three simple rules with example for byte-sized `int`:
- The decimal value 0 and positive values are coded *normally*.
	- `00000000`, `00000001`, `00000010`, ... `01111111`
- Finding the opposite sign of a number requires two simple steps:
	- Flip each bit to its opposite (e.g. `0110` to `1001`)
	- Add one to this number (e.g. `1001` + `0001` = `1010`)

### Paper exercises 
#### A - the algorithm
Apply the two's complement procedure to determine -1 * *n* for the following *n*. Assume a 8-bit two's complement number.
- *n=0*
- *n=1*
- *n=2*
- *n=127*
- *n=126*

#### Insight
Following this logic, what should the binary value `10000000` encode?

Feel free to use `show_integer.c` to use the system to show how it looks on a real system. Try to not let the little endian make too much noise.

### B - limits
Assume the 1-byte two's complement `10000000`, or -128
- Attempt to encode 128 by starting at -128 and using the procedure  above.

##### Insight
- 128 cannot be expressed in a 1-bytes two's complement integer. 

Show the visual representation of how numbers are organized in a 2C integer:
![[int_to_unsignedint.png]]

#### C - Overflowing
Finally, let's perform an addition where we add 1 to 127. What result do you get?  

Feel free to use the minimalistic C program `overflow.c` in this folder to do the dirty work. It may be good to modify `overflow.c`, recompile and run again to build a mental memory of the process.  The main caveat here is that the type is `char`, which is introduced in the next section.

## Implication of selecting an integer type for a programmer

- Modern architectures are using either 32- or 64- bits integers. 
- Show a table of limits for `unsigned int`, `int`, `long`. Note that a `long` on a 32-bit system is also 32-bit in size.
![[integerlimits.png]]

- Derive the ways to calculate these limits.
For a system with an `int` encoded with *n* bit and:
$$n = 32$$

The ranges of an `unsigned int` are
$$U_{min}=0$$$$U_{max}=2^n-1$$
The -1 comes from the fact that the value 0 is a valid value and must be counted, so we never reach *2^n* with *n* bits. 

Likewise, using a signed integer, one bit is used for the sign so *n* is replaced by *n-1*
$$U_{min}=-2^{n-1}$$$$U_{max}=2^{n-1}-1$$

- Discuss why a programmer should consider using anything else than `long` since it is the most versatile. 
	- Functional boundaries from problem specifications. 
	- Total memory usage may matter if one need to store millions of these. 
- A program must ensure that a variable is not accidentally extending outside of its encoding range.
	- Loops that modify a value (counters, etc.)
	- Allowing user to input values.

# Post problem
## PP1
Each byte in RAM has one address: a number from 0 to *n* where *n* is usually large. You have seen one such address when running the C application `show_integer` already. The address is set by the word size on a system: usually 32 or 64 bits
Q1 - Why is the `unsigned int` is used to express a memory address instead of `int`?
Q2 - Calculate the total number of bytes that could be addressed in a 16-bit system. How much smaller is this from the expressibility of a 32-bit word? 

In a program you plan to write, you know that a value is always positive, can exceed 256 but would always be smaller than 1024. It would therefore be OK to encode with 10-bit. Knowing now that memory allocation is done at the byte level. Why would defining a 10-bit integer save no more memory space than using a `unsigned short` with 16-bit? 

## PP2
Order the following C type `char` from largest to smallest decimal value.$$k=\{0010010, 10000000, 11111111, 01111100\}$$
# GPT prompts to generate practice problems

```GPT
Generate a question that provides a program specification on one integer variable and asks which 32-bit system C data type would be the smallest possible type to use for this variable.
```