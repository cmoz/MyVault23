The Fetch-Decode-Execute cycle, also known as the instruction cycle, describes the process a CPU uses to execute a program's instructions. This process involves the use of various registers. 

Here is a simplified view of how registers are used in each step of the cycle:

1. **Fetch**
   - The CPU looks at the Program Counter (PC) register, which contains the memory address of the next instruction to be executed.
   - The instruction stored at that address in memory (RAM) is fetched and placed in the Instruction Register (IR).
   - The Program Counter is then incremented to point to the next instruction.

2. **Decode**
   - The instruction in the Instruction Register is decoded by the CPU's control unit. This involves determining what operation needs to be performed and which registers or memory addresses are involved.

3. **Execute**
   - The CPU performs the instruction. This may involve several of the CPU's registers.

Let's illustrate this with a simple example: the instruction to add two numbers together and store the result.

1. **Fetch**
   - The CPU looks at the Program Counter to find the address of the 'Add' instruction, fetches the instruction from memory, and places it in the Instruction Register. The Program Counter is then incremented.

2. **Decode**
   - The CPU's control unit decodes the instruction from the Instruction Register. It determines that this is an 'Add' operation and identifies the registers involved.

3. **Execute**
   - The CPU uses the Arithmetic Logic Unit (ALU) to perform the addition. For example, if the instruction specified to add the contents of Register 1 and Register 2, the numbers in those two registers are fed into the ALU.
   - The ALU performs the addition and the result is stored in a special register called the Accumulator, or in some specific register defined by the instruction set.
  
It's important to note that the exact names and numbers of registers can vary based on the specific CPU architecture and instruction set. For example, some CPUs have a special 'Instruction Pointer' instead of a Program Counter, or may use a 'Flags Register' to store status information about the last operation performed by the ALU. Nonetheless, the overall concept of the Fetch-Decode-Execute cycle remains the same.