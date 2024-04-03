Functional Units:
![](https://i.imgur.com/h98Tey6.png)

A computer consists of 5 functionally independent main parts: 
1) Input 
2) Memory 
3) ALU 
4) Output  
5) Control unit

Basic Operational Concepts:
- An Instruction consists of 2 parts 1) Operation code (Opcode) and 2) Operands.
-  The data/operands are stored in memory. 
- The individual instruction are brought from the memory to the processor. 
-  Then, the processor performs the specified operation.
- This instruction is an addition operation. 
	- The following are the steps to execute the instruction: 
		- Step 1: Fetch the instruction from main-memory into the processor. 
		- Step 2: Fetch the operand at location LOCA from main-memory into the processor. 
		- Step 3: Add the memory operand (i.e. fetched contents of LOCA) to the contents of register R0. 
		- Step 4: Store the result (sum) in R0. • The same instruction can be realized using 2 instructions as: Load LOCA, R1 Add R1, R0 
	- The following are the steps to execute the instruction: 
		- Step 1: Fetch the instruction from main-memory into the processor. 
		- Step 2: Fetch the operand at location LOCA from main-memory into the register R1. 
		- Step 3: Add the content of Register R1 and the contents of register R0. 
		- Step 4: Store the result (sum) in R0.


Bus structure
• A bus is a group of lines that serves as a connecting path for several devices.
• A bus may be lines or wires. 
• The lines carry data or address or control signal. 
• There are 2 types of Bus structures: 
1) Single Bus Structure and :
	  ![](https://i.imgur.com/y308tI2.png)

	 Because the bus can be used for only one transfer at a time, only 2 units can actively use the bus at any given time. 
	 Bus control lines are used to arbitrate multiple requests for use of the bus. 
	 Advantages: 
		1) Low cost 
		2) Flexibility for attaching peripheral devices.
2) Multiple Bus Structure:
	  Systems that contain multiple buses achieve more concurrency in operations.
	  Two or more transfers can be carried out at the same time. 
	  Advantage: Better performance. 
	  Disadvantage: Increased cost.


Performance – Processor Clock
- Processor circuits are controlled by a timing signal called a Clock. 
- The clock defines regular time intervals called Clock Cycles. 
-  To execute a machine instruction, the processor divides the action to be performed into a sequence of basic steps such that each step can be completed in one clock cycle.
- Let P = Length of one clock cycle R = Clock rate.
- R is measured in cycles per second. 
- Cycles per second is also called Hertz (Hz) 

Basic Performance Equation 
- Let T = Processor time required to executed a program.
- N = Actual number of instruction executions. 
- S = Average number of basic steps needed to execute one machine instruction. 
- R = Clock rate in cycles per second.  
- The program execution time is given by 
	![](https://i.imgur.com/KjeurQM.png)
- Equ1 is referred to as the basic performance equation. 
	-  To achieve high performance, the computer designer must reduce the value of T, which means reducing N and S, and increasing R. 
		-  The value of N is reduced if source program is compiled into fewer machine instructions. 
		-  The value of S is reduced if instructions have a smaller number of basic steps to perform. 
		-  The value of R can be increased by using a higher frequency clock. • Care has to be taken while modifying values since changes in one parameter may affect the other.


Performance Measurement

Memory Location and Addresses
	• Memory consists of many millions of storage cells (flip-flops). 
	• Each cell can store a bit of information i.e. 0 or 1 (Figure 2.1). 
	• Each group of n bits is referred to as a word of information, and n is called the  word length. 
	• The word length can vary from 8 to 64 bits. 
	• A unit of 8 bits is called a byte. 
	• Accessing the memory to store or retrieve a single item of information (word/byte) requires distinct addresses for each item location. (It is customary to use numbers from 0 through 2 k -1 as the addresses of successive-locations in the memory).
Memory Operations
	• Two memory operations are: 
		1) Load (Read/Fetch) 
		2) Store (Write). 
	• The Load operation transfers a copy of the contents of a specific memory-location to the processor. The memory contents remain unchanged. 
	• Steps for Load operation: 
		1) Processor sends the address of the desired location to the memory. 
		2) Processor issues „read‟ signal to memory to fetch the data. 
		3) Memory reads the data stored at that address. 
		4) Memory sends the read data to the processor. 
	• The Store operation transfers the information from the register to the specified memory-location. This will destroy the original contents of that memory-location. 
	• Steps for Store operation are: 
		1) Processor sends the address of the memory-location where it wants to store data. 
		2) Processor issues „write‟ signal to memory to store the data. 
		3) Content of register(MDR) is written into the specified memory-location.

Instruction and Instruction sequencing

Addressing Modes