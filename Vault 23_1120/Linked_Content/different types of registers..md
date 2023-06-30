Registers are a small amount of very high-speed storage available in the CPU. Different types of registers perform different roles in the computer architecture, each facilitating a specific aspect of the CPU's operations. The exact types and numbers of registers can vary based on the specific architecture of the CPU, but generally, they are categorized as follows:

1. **General-Purpose Registers**: These registers are used for various computational tasks and can hold both data and addresses. They serve as temporary storage for the CPU during processing.

2. **Accumulator Register (ACC)**: This special-purpose register is used to store the results of operations carried out by the Arithmetic Logic Unit (ALU). 

3. **Data Registers (DR)**: These hold the input and output data for computations. 

4. **Address Registers**: These contain the memory addresses of data and instructions. They might be further classified into:
   
   - **Program Counter (PC)**: This register holds the address of the next instruction to be executed.
   
   - **Stack Pointer (SP)**: This points to the top of the current stack in memory, which is particularly useful for nested function calls and recursion.
   
   - **Base and Index Registers**: Used in indexed and relative addressing modes to hold base addresses and offset values, respectively.

5. **Instruction Register (IR)**: This holds the instruction currently being executed.

6. **Status Register / Flag Register**: This holds various status flags that provide information about the results of the most recent operation (like if an overflow occurred, or if the result was zero). 

7. **Control Registers**: These are used by the CPU to control and coordinate its operations. For example, control registers might be used to manage interrupts, control caching, or handle other hardware-level functions.

By having different types of registers, a CPU can efficiently handle various tasks simultaneously. The registers act as a rapid-access workspace for the CPU, holding the data, instructions, addresses, and flags it needs to perform its operations.