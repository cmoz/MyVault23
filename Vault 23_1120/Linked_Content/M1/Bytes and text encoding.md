### C projects
[Hello World ](obsidian://open?vault=Vault%2023_1120&file=Linked_Content%2FHelloWorld )

# Lecture plan
## Pre-problem
> The goal of the pre-problem here is to get students to think of combinations of two states: up and down. Zero is a closed fist.

### Prompt
Find a way to count from 0 to 31 using only the fingers of one hand

## Core session
### A computer orders words differently that you would
> *The goal of this pre-problem is to observe that uppercases and lowercases letters are ordering themselves separately and not following the alphabetization we expect.*

In a terminal, using `python3`, type the following 4 lines of code.

```
# This is Python 3 code
words = ['aardvark', 'Aardvark', 'Zombie', 'zombie', 'ketchup']
print(words)
words.sort()
print(words)
```
#### Prompt
Can you explain why these 5 words are sorted in this unusual manner? It is OK to google, speak with colleagues. 

### Text is made of bytes: crack the code!
> The goal of this segment is to demonstrate text file in a command line context, and have students contrast the textual representation as well as the way it is encoded at the byte level. 
 
Create a file and put the phrase `Hellow World!` in, call it `helloworld.txt`:
> `nano helloworld.txt`
> 

Look at the file as a text file, then look at the raw data in hex notation:
> `more helloworld.txt`
> `xxd -C helloworld.txt`

#### Prompt
Crack the code and identify the connection between the byte level encoding and the text that it encodes. 
- What is the code for a `l`, for an `o`, or a white space?

#### Key discussion elements:
- There are twice as many characters in the hex display.
- The `ll` is likely the `6c6c` repeated part, from there `o` can be guessed to be `6f` and the white space `20`. 

Supporting video: [Hexadecimal notation and bytes](https://youtu.be/WOyr6syFNhg)

### Number systems and hexadecimal 
> This segment aims to formalize the code discovered before into the more formal number system in base 

### Let's learn to count (all over again)
We'll build the [[Hexadecimal Table]] 
1. starting with counting *in decimal* from 0 to 15. 
	- Pay special attention to the need for a second digit to express 10 (the base).
2. Let's write in base 16, using A to E for the symbols that we never bothered to invent.
3. Finally, let's count from 0 to 15 in the binary number system. 
	- Pay special attention to each time we reach a new power of two.

Video: [Slow motion look at anatomy of a number](https://youtu.be/1WtoGuc5bdU)
Video: [Expressivity of n-bit strings](https://youtu.be/sFMcqLCo5V4)

### Text encoding is a simple mapping of bytes to a symbol
Let's consider the [[ASCII Table]], locate the character `A` and `a`. Which one is the highest value?

Let's return to the hexadecimal content of `helloworld.c`
> `cat helloworld.c`
> `xxd -C helloworld.c`

#### Prompt
Locate all of the locations in this file where a line ends. How many are there? 

What is the first column output by `xxd` representing? (*The count in bytes expressed as an hexadecimal number*)


### Executable files are... just files 
> *The insight of this segment is that binary files are files that are not encoded using ASCII. They are, however, just files and have some kind of structure to them.*

Human readable code must be compiled to be translated into machine code for a computer to be able to execute software. 

Let's compare the text representation of an executable file, and its byte representation.
> `more helloworld`
> `xxd -C helloworld`
> `ls -lah helloworld`

The last line allows you to figure out the size of the executable: 33Kb.  Converting `0x8029` into decimal confirms the purpose of the first column output by `xxd`.  

### Insight: 
- With your forensic hat on, what can you see inside this executable files?
	- Is there a structure to the file?
	- Are there ASCII characters in the file?
	- Hint: Let's modify `helloworld.c` so it prints a different short phrase.
		- recompile with `gcc -o helloworld helloworld.c`
		- Run with `./helloworld`
		- re-examine with `xxd -C helloworld`

# Post session problem
- The True colour encoding is made of three bytes, one for each of the Red, Green, and Blue channels. Derive manually that the number of colour under this encoding is about 16 million colours. 

# Taking it to the next level
If you want to know how we can encode with characters beyond the ASCII set, such as UTF-8, please watch this video: [ASCII and UTF-8](https://youtu.be/SpXQZOJGYZ4)


# GPT prompts to generate practice problems

- `Generate two questions to test my understanding of hexadecimal number system`
	- After you are done: `Provide the answer to both questions.`
	- Or, `Solve the previous problems in a step-by step manner` (Be aware that GPT doesn't solves the problem in the most simple manner, so your mileage may vary.)
