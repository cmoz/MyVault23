
> In this challenging lab, you will analyse three C programs that are manipulating strings and individual characters. Look at this lab as solving a puzzle: it is more about building your own tools to tackle difficult problems than *actually* solving the puzzle.

# Before you begin
1. Make sure that you have completed Lab 1 about numbers because this lab builds on the ability to read, analyse and understand C programs.
2. Make sure that you have completed the activities of the learning sessions on `string` and `pointers`. Without a basic grasp of these two concepts, this lab will require you to do more *learning on the job*.
3. Log to `timberlea.cs.dal.ca` and check out the code for this lab from the GitLab repository to obtain the most up-to-date version of the lab and code.
4. Don't panic, [don't give up](https://youtu.be/dQw4w9WgXcQ) Once you are done with this lab, many things will get easier. Teaching assistants are here to help you if you show them your work so far.

# Milestone 1 - inspect_argv.c
This program uses a few concepts that you will learn much later in a programming course. This is not trivial stuff, but this is something that you can do it you keep in mind the content from the [[strings]] lecture.

This program is going to be useful for you to verify your work when you are working with the main program: [[caesar_cypher.c]]. 

## Build the program and try it
Go to the folder `<GitRoot>/m1_data/Lab2_cyper/` and build with:

> `gcc -o inspect_argv inspect_arv.c`

This will create a new program that you can run like this:

> `./inspect_argv hello`
> `./inspect_argv hello buddy`
> `./inspect_argv "hello buddy"`

	1. Note the behaviour of the program each time you call it. Feel free to change the arguments to help you understand and explore, but make sure that you cover at least the three cases above.
	2. You know that you are done when you can answer the following questions:
		1. You can explain the connection between command line input and the number of output lines.
		2. You can explain what is the meaning of the values in paraentheses. 
		3. You can explain what is the purpose of the quotation marks. 

## Program analysis
Open the program on your own machine in a C editor, or use a paper print out (whichever works best for you). 

1. Consider the entire code, can you (vaguely) get a sense of the logic of this program? 
2. Circle elements that you need to look up. If you are working in a group, have a the element explained to you by a colleague. If there are elements that no one can explain, look them up either by consulting the web, asking GPT, or going to the [C standard library](https://en.cppreference.com/w/c/header).
3. Do not be afraid to make a copy of the program, modify and recompile. If you break the original, you may check it out from GitLab again. 

## Challenge
Modify the project to reveal the first element of `argv` at index 0. This will require you to make a small modification, recompile, run the program a few times.

# Milestone 2 - The cypher algorithm
It is fair to look up what is this cypher algorithm. For added challenge, don't just yet so you may discover it through analysis. Either approach is valid because the goal here is to develop your analysis skills, not to encrypt strings.

## Compile the program and try it

1. Go to the right folder, compile and run. Try as many times as you want with different input arguments.

> `./caesar_cypher mysecretmessage 1`

2. The second argument is the encryption key. Discover the limit of what can be input as key.
3. Use the knowledge from Milestone 1 to encrypt a message with more than one word in it.

## Program analysis
This is the main challenge of the lab this week. Keep in mind what you know about the connection between characters and `unsigned int`, the structure of a string, the [[ASCII Table]], and hexadecimal notation. Everything is coming together... now! 



## Steps
1. Go over [[caesar_cypher.c]] and answer a number of C syntax, logic and library questions. 
2. Use [[inspect_argv.c]] to help demonstrate that the cypher is functioning properly. Use two test cases of your choice, one without white space and one with white space that requires using quotation marks. 
3. Go over [[caesar_cracker.c]] to try to understand how the cypher code was refactored. Then understand the program's logic. 
4. Challenge students to decrypt `>N>Dz,,-+zmj^fn` and to deduce the encryption key. 
5. unzip a password-protected archive using the original message and obtain some zany reward. 

## Objectives
5. Introduce the notion that strings are arrays of characters, which are themselves `unsigned char`
6. Introduce the notion of arrays maybe as a way to talk about pointers.
7. Send student into a hunt to research certain C functions or syntactical feature
8. Introduce students to a fairly simple algorithm
9. Introduce this as an analytical exercise with the goal to be able to explain each parts and the logic. This is not about the cypher, the cypher is an excuse to perform an analysis. 