# Pre-problem
Run the project `display_string.c` on the screen and ask students to look carefully at the output for a few minutes. 

Q1 - How many bytes are used by the string `"CSCI 1120 rocks!"` 

Q2 - What is the minimal number of bytes needed to encode  `"CSCI 1120 rocks!"`  in a C program? 

# Lecture code-along
## Slow motion replay
Run `display_string.c` a few times, feel free to change the string in the code, recompile and run again. 
- Go over the memory address: 
	- hex is a proxy to binary
	- Think of RAM as a long row of cells with a unique address for each bytes
- Strings are sequences of `char`, and it doens't make sense to have a variable for each value as it would be tedious and inflexible. 
	- Instead a string is really just a stretch of bytes of a pre-defined length. 
	- Must be at least the length of what it will encode +1
	- Why there must be a `\0` character? 
		- Without, all strings would have to be allocated exactly their length and a programmer never really know what may end up in a string.
- Delve into the code and look at the array notation for a string. 
	- A string is a pointer to the first cell
	- Later cells are accessed through an offset `str[i]`
	- Offset 0 is the start of the string, or the same as the pointer to the string.
- Give students 5 minutes to look at the code and write down the parts that they do not understand. Look them up.
	- Ask the class what they needed to figure out
	- Go over the code line per line
		- String declaration
		- Pointers, dereferencing
		- printf for pointers, hex, char
	- Don't spend too much time on loop logic: this is a distractor.

# Post problem

# Taking it to the next level

# GPT prompts to generate practice problems

