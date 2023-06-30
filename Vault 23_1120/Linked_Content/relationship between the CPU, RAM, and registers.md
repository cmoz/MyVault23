Sure, let's illustrate this with a simple example of a user running a program to add two numbers. 

1. **Starting the Program**
   
   A user starts a program to add the numbers 5 and 3. These numbers are initially loaded into the RAM along with the rest of the program's data.

2. **Fetch**

   The CPU looks at the address in the Program Counter (PC) register to see what instruction it should perform next. The PC points to the address in RAM where the first instruction of our program is stored. The CPU fetches this instruction and places it in the Instruction Register (IR). This instruction tells the CPU to load the number 5 into a CPU register.

3. **Decode**

   The Control Unit in the CPU decodes the instruction from the IR. It interprets that it needs to load data from a certain address in RAM into a CPU register.

4. **Execute**

   The CPU loads the number 5 from RAM into a general-purpose register, let's call it Register A.

5. **Next Instruction (Fetch, Decode, Execute)**

   The PC is incremented to point to the next instruction. The CPU fetches this instruction into the IR. It's an instruction to load the number 3 into another CPU register. The CPU decodes and executes this instruction, loading the number 3 into another general-purpose register, let's call it Register B.

6. **Addition Instruction (Fetch, Decode, Execute)**

   The PC is incremented again, and the CPU fetches the next instruction into the IR. This instruction is to add the contents of Register A and Register B. The CPU decodes this instruction, and then executes it using the Arithmetic Logic Unit (ALU). The result of the addition (8) is stored in another register, let's call it the Accumulator.

7. **Storing the Result**

   The next instruction might be to store the result back into RAM, or to output it to the user, depending on how the program is written. 

In this way, the CPU, RAM, and registers all work together to run a program. The CPU fetches instructions and data from RAM, decodes the instructions, and executes them using its internal registers for temporary storage and processing.

Keep in mind that in a real computer, these operations are happening millions or billions of times per second, and a single program can involve many different instructions and pieces of data. Also, this is a simplified example. Real-world CPU architectures can be much more complex, with many more types of registers and stages in the instruction cycle.