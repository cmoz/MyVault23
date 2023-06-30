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



---


**Introduction (5 minutes):**

- Begin with an overview of what will be covered in the session.
- Define what an integer is in mathematical terms.

**Basic Properties of Integers (10 minutes):**

- Discuss the basic properties of integers, including the concept of positive and negative numbers, zero, even and odd numbers, prime numbers, etc.
- Explain the number line and how it can be used to understand addition and subtraction.
- Discuss the use of integers in basic mathematical operations (addition, subtraction, multiplication, division).

**Integers in Computer Science (15 minutes):**

- Discuss how integers are represented in computer memory, including binary representation and hexadecimal representation.
- Talk about the range of integers that can be represented in a certain number of bits.
- Discuss the difference between signed and unsigned integers, including how negative numbers are represented using two's complement.

**Integer Operations in Programming (15 minutes):**

- Discuss how integer operations are performed in programming, including arithmetic operations and bitwise operations.
- Show examples of integer arithmetic in a common programming language like Python or C++, including potential issues like integer overflow and underflow.
- Discuss the importance of choosing the right integer type in programming (e.g., short, int, long).

**Practical Exercise (10 minutes):**

- Provide students with a few simple problems to solve using integer arithmetic in a programming language. This could include things like calculating the sum of a list of integers, finding the maximum or minimum integer in a list, or reversing the digits of an integer.
- Walk around the room to answer questions and provide help as needed.

**Wrap-up and Questions (5 minutes):**

- Summarize the key points from the session.
- Provide resources for further learning, and encourage students to practice integer operations in programming.
- Open the floor for any questions and feedback.


---

Sample questions and interactive activities you can incorporate into each section of the lecture:

**1. Basic Properties of Integers:**

   *Questions:*
   - Can you name an integer that is not a whole number?
   - What does it mean if an integer is odd? How about if it's even?
   - What is the smallest positive integer?

   *Activity:* Use an interactive number line tool or draw on a board and ask students to indicate where certain integers are located. You could also have them demonstrate addition and subtraction on the number line.

**2. Integers in Computer Science:**

   *Questions:*
   - How is the integer 7 represented in binary? How about -7 in two's complement?
   - What is the largest positive integer you can represent with 8 bits in two's complement representation?
   - What's the difference between signed and unsigned integers?

   *Activity:* Provide a range of integers and have students convert them to binary and hexadecimal. Also, provide binary representations and ask students to convert back to decimal.

**3. Integer Operations in Programming:**

   *Questions:*
   - What would happen if we add 1 to the largest positive integer we can represent in 8 bits? What's the term for this event?
   - What is a bitwise operation? Can you give an example?
   - How do you choose the correct integer type for a specific task in a program?

   *Activity:* Have students write code snippets to perform basic arithmetic operations, such as addition, subtraction, multiplication, and division of integers. Also, let them experiment with bitwise operations and see the outcomes.

**4. Practical Exercise:**

   *Questions:*
   - What did you find challenging about these exercises?
   - How would you modify this code to handle larger integers? 

   *Activity:* Provide simple programming problems such as calculating factorial, finding maximum or minimum integer in an array, or counting the number of set bits in an integer's binary representation.

