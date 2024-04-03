**what is operating system?**
- An operating system acts as an intermediary between the user of a computer and the computer hardware. The purpose of an operating system is to provide an environment in which a user can execute programs in a convenient and efficient manner.
![](https://i.imgur.com/m9RpnwF.png)


**what does OS do?**
- It provides a basis for application programs and acts an intermediary between computer user and computer hardware, so the user program like word processor, spreadsheets want to utilize the computer hardware so to provide them the hardware the operating system is responsible for allocating the resource for those application based on the requirement, as they require keyboard access or mouse and so on. *it has goals like convenience and efficiency*


**what is computer system Operation (CSO)**?
A modern general-purpose computer system consists of one or more CPUs and a number of device controllers connected through a common bus that provide access to shared memory 
![](https://i.imgur.com/RtY2BiO.png)
- each device controller is in charge of specific type of device
- the CPU and the device controller can execute concurrently, competing for memory cycles
- to ensure orderly access to the shared memory, a memory controller is provided whose function is to synchronize access to the memory
- The CSO involves 
	- Bootstrap program: the bootstrap program must locate the operating-system kernel and load it into memory 
	-  interrupt: interrupt from either the hardware or the software. Hardware may trigger an interrupt at any time by sending a signal to the CPU, usually by way of the system bus. Software may trigger an interrupt by executing a special operation called a system call
	-  system process


**What are Storage structure**?
1. Main memory is usually too small to store all needed programs and data permanently.
2.  2. Main memory is a volatile storage device that loses its contents when power is turned off or otherwise lost..
3. ![](https://i.imgur.com/CY8I9bQ.png)
The wide variety of storage systems can be organized in a hierarchy (Figure 1.4) according to speed and cost. The higher levels are expensive, but they are fast. As we move down the hierarchy, the cost per bit generally decreases, whereas the access time generally increases. This trade-off is reasonable; if a given storage system were both faster and less expensive than another


**what is Computer System Architecture**?
![](https://i.imgur.com/u3OBERR.png)

Types are based on number of *general purpose processors*.

1.Single processor System:
- One main CPU capable of executing a General purpose instruction set from user also other special purpose processor are also present which perform device specific tasks

2.Multiprocessor System:
- Parallel system 
- two or more processors in close communication, sharing the computer bus and sometimes the clock, memory, and peripheral devices   
Adv: 
- Increased  throughput, 
- economy of scale
![](https://i.imgur.com/LiMZQ1S.png)


3.Clustered System:
- Like MPS CS gather together multiple CPUs to accomplish computational work
- they are composed of two or more individual systems coupled together.
- Provides high availability
- can be asymmetrically and symmetrically


**What is Operating system Structure**?
Types
~*Multiprogramming*
- A single user cannot keep CPU busy all the time or the I/O devices at all ,
- Multiprogramming increase CPU utilization by organizing jobs so that the CPU always has one to executes.
~Multitasking 
- Cpu executes multiple jobs by switching among them
- Switches occur so frequently that the users can interact with each program while it is running
- Multitasking requires an interactive computer system which provides direct communication between the user and the system simultaneously.

**What are the services of OS**?
~User Interface-(CLI, GUI)
~Program Execution
~I/O operations
~File System Manipulation
~Communication
~Error Detection
~Resource allocation
~Protection and Security

**What are operating system operation**?
- Dual Mode![](https://i.imgur.com/fDctFrs.png)
	- A bit, called the mode bit, is added to the hardware of the computer to indicate the current mode: kernel (0) or user (1). With the mode bit, we can distinguish between a task that is executed on behalf of the operating system and one that is executed on behalf of the user.
	- When the computer system is executing on behalf of a user application, the system is in user mode
	- The dual mode of operation provides us with the means for protecting the operating system from errant users—and errant users from one another. We accomplish this protection by designating some of the machine instructions that may cause harm as privileged instructions. The hardware allows privileged instructions to be executed only in kernel mode. If an attempt is made to execute a privileged instruction in user mode, the hardware does not execute the instruction but rather treats it as illegal and traps it to the operating system.


**User Interface in Operating system**?
~CLI the user have to enter the command based in that the process will perform.
~GUI most commonly and user friendly contain (menu, setting and continues...)


[SYSTEM CALL](obsidian://open?vault=Notes&file=System%20call).

