The memory hierarchy in computer architecture describes the relationship between different types of memory in a computer system. This hierarchy is based on speed, size, and cost. 

The memory near the top of the hierarchy is faster, smaller, and more expensive (per byte). As you move down the hierarchy, the memory becomes slower, larger, and less expensive (per byte). Here's a breakdown of a typical memory hierarchy from top to bottom:

1. **CPU Registers**: These are tiny storage areas inside the CPU. They're the fastest type of memory, and the CPU uses them to store data it's currently processing. However, registers are very limited in number and size.

2. **Cache Memory**: This is a small amount of high-speed memory on the CPU. It's slower and larger than registers, but still much faster and smaller than main memory. Cache memory stores copies of data from frequently used main memory locations.

3. **Main Memory (RAM)**: Random Access Memory is the main working memory of the computer. It's slower and larger than cache memory, but still much faster and smaller than secondary storage. It holds the data and instructions that the computer is currently using.

4. **Secondary Storage (Hard Disk Drives, Solid State Drives)**: This is where the computer stores data long-term. It's much slower and larger than RAM, but it's also much less expensive (per byte), and it retains data even when the computer is powered off.

5. **Tertiary Storage (Optical Disks, Tape Drives, etc.)**: This is the slowest and largest form of memory. It's used for archiving data and for large data sets that aren't needed very often.

This memory hierarchy is designed to balance speed and cost. The fastest memory is too expensive to use for all of a computer's data, so the computer system is designed to keep the most frequently used data in the fastest memory, while less frequently used data is kept in slower, less expensive memory. 

The control of data between these different levels of memory, which is known as memory management, is a critical aspect of computer design. It involves complex algorithms to decide when and where to move data, aiming to make the most efficient use of the memory hierarchy to achieve the best possible performance.