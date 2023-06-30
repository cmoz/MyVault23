GDB, the GNU Debugger, is a powerful tool for tracing and debugging programs written in languages like C and C++. Here's a proposed structure for a lab session to teach students how to use GDB to trace C programs:

**Introduction (15 mins):**

- Give an overview of what GDB is and why it's useful.
- Discuss the types of problems GDB can help solve, such as identifying segmentation faults or logical errors in code.
- Briefly introduce the concept of breakpoints, stepping, and inspecting variables.

**Demonstration (15 mins):**

- Show a pre-prepared C program with a known bug. The program should be simple but non-trivial - perhaps a small function with a logical error or an off-by-one error in a loop.
- Demonstrate how to compile the C program with debugging symbols (`gcc -g`).
- Demonstrate how to start GDB with the compiled program (`gdb ./program`).
- Set a breakpoint at the start of the main function and run the program.
- Step through the program one line at a time, demonstrating the `next`, `step`, `continue`, and `quit` commands.
- Show how to print the value of variables at different points in the program.
- Identify the bug and show how GDB helped you find it.

**Hands-On Exercise (45 mins):**

- Provide students with several C programs with different known bugs.
- The students' task is to use GDB to find and fix the bugs.
- Encourage students to use the commands you demonstrated and to experiment with other GDB commands as well.
- While students are working, walk around the room to offer assistance, answer questions, and give hints if necessary.

**Discussion and Wrap-Up (15 mins):**

- Discuss the solutions to the exercises, explaining how you would use GDB to find each bug.
- Discuss common pitfalls and best practices when using GDB.
- Leave time for students to ask questions about anything they found challenging or confusing.
- If possible, provide resources for further learning about GDB, such as online tutorials or documentation.

This structure allows students to learn by doing, which is often the most effective way to learn a practical skill like debugging. Make sure to encourage questions and active participation to keep students engaged and ensure they're getting the most out of the lab session.