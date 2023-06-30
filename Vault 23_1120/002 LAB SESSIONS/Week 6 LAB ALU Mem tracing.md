**Title of the Lab Session**: Exploring ALU Memory Tracing in Computer Architecture

**Duration**: 1.5 hours

**Lab Outline**

**I. Introduction (10 minutes)**

- Greet the students and provide an overview of the lab objectives. (3 minutes)
- Review the key concepts that will be used during the lab, namely ALU operations and memory tracing. (7 minutes)

**II. Activity 1: Manual Memory Tracing Exercise (30 minutes)**

- Provide students with a written program that includes some ALU operations. It can be a simple program with mathematical operations. (5 minutes)
- Ask students to manually trace the memory as the program runs. They should note down the memory addresses accessed during each ALU operation. (15 minutes)
- Review the students' results as a class and discuss any discrepancies or interesting observations. (10 minutes)

**III. Activity 2: Introduction to a Memory Tracing Tool (20 minutes)**
CPU SIMULATOR program https://teach-sim.com/cpu-2/

- Introduce a memory tracing tool, such as Valgrind or a built-in feature in a CPU simulator. Demonstrate how to set it up and get it running. (10 minutes)
- Give students some time to set up the tool on their computers and become familiar with the interface. Provide assistance as needed. (10 minutes)

**IV. Activity 3: Using the Memory Tracing Tool (20 minutes)**

- Have students run the same program as before through the memory tracing tool. They should observe how the tool traces the memory accesses. (10 minutes)
- Discuss the output of the tool, including how to interpret the memory trace. Compare this with their manual tracing results from Activity 1. (10 minutes)

**V. Activity 4: Experimenting with Different Programs (20 minutes)**

- Provide a few different programs for the students to trace. They can compare the results and observe how different types of programs result in different memory traces. (15 minutes)
- Discuss as a class the observations from this activity. Encourage students to explain their findings and conclusions. (5 minutes)

**VI. Conclusion and Q&A (10 minutes)**

- Recap of the lab session and review the key learnings of each activity. (5 minutes)
- Open the floor for questions and final discussions. (5 minutes)

This hands-on lab session should provide students with a deeper understanding of memory tracing, especially in the context of ALU operations. Adjust the pace and difficulty of the activities based on your students' progress and understanding.


---

A simple program in C language that includes several ALU operations. This is a simple program that calculates the area and perimeter of a rectangle. The ALU operations in this program include multiplication and addition.

```c
#include<stdio.h>

int main() {
    int length, width, area, perimeter;

    // Prompt the user to enter the length and width of the rectangle
    printf("Enter the length of the rectangle: ");
    scanf("%d", &length);
    printf("Enter the width of the rectangle: ");
    scanf("%d", &width);

    // Calculate the area and perimeter
    area = length * width;      // Multiplication operation
    perimeter = 2 * (length + width);  // Addition operation

    // Print the results
    printf("The area of the rectangle is: %d\n", area);
    printf("The perimeter of the rectangle is: %d\n", perimeter);

    return 0;
}
```

When this program runs, it will first allocate memory to store the values of `length`, `width`, `area`, and `perimeter`. Then, when the ALU operations (multiplication and addition) are performed, the CPU will need to access the memory addresses where `length` and `width` are stored. After the results of the operations are calculated, the CPU will write these results back to the memory locations for `area` and `perimeter`.

Use this program for manual memory tracing exercise. Students can trace how these memory addresses are accessed during the program's execution. Later, they can use a memory tracing tool to verify their manual memory trace.