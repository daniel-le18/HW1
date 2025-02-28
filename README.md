# How to run
```java
javac *.java to compile all files in the directory
java CPU samplex.txt 200 for each sample
```

# Purpose:
- The purpose of this project is to stimulate the process of inside of a control processing unit and memory with the fetch and execute simple instructions.
The stimulation could be implemented using 2 processes, one for memory and CPU.
- In Java, this can be done by using Process class and execute another java file (memory.java) to run parallel then set up and input and output stream to send and get the data to the main process (cpu.java) from then we can execute the command.
The role of the memory is to fetch in the information or commands/ instructions and then pass it to the CPU. From there, the CPU executes each instruction and interact with the memory by using read and write functions to manipulate the array of instructions by using the address. For each instruction after being executed, the program jumped and have the counter plus 1 for the next one until it reaches the end of the instructions which marks by using a 50 instruction. 

# How it was implemented:
- Using the register, PC for program counter, IR for instruction, AC for accumulator, SP for stack pointer, X, Y, we can get the instructions using the stream then store them accordingly into these registers. Each execution our PC jumps 1 to the next IR.
The main function of the memory file is to read in the file name that is sent by the CPU then open file and populate the instruction array. It also can only support the read and write given the address if the CPU send the instruction to do so.
The main function of the CPU is to execute the command which was sent through the stream by the memory. It can send and get the instruction from and to the memory to assist the according logic of command. For example, 1\n10, it sends read signal by using the address to get the first integer, the 1 activates the switch case 1, inside we increase the program counter which increase the address and read again from the memory the next integer, this means 1 is load integer 10.
- I implemented the project accumulating using the given examples. For first example, the project is supposed to run and print out the alphabet following number from 1-10. What it does is it takes in the data, keep reading and incrementally jump to the next one and print out for the alphabet and then the number. These will be implemented first using some basic instruction like print 9, load data 1…The project is slowly expanded with the sets of instructions in second example with the most important is to jump to (23) which is implemented like a jump to function in basic programming language then after all instructions are executed it return to the main (24). In this example, the interrupt is also implemented by taking an input from command line from the user. The number of instructions dictated when the interrupt happens. In the fourth example, one simple check for memory violation is insert into the read from memory, if the address is trying to access address above 1000, we will prompt an error and end the program. The hardest part is to write the sample for the fifth example as each time anything got changed or added, we have to go back to previous line and change that value if we use a jump (23) as things getting added, our address gets changed. 
