**what is operating system?**
-An OS is a program that manages the computer hardware
![](https://i.imgur.com/m9RpnwF.png)


**what does OS do?**
-It provides a basis for application programs and acts an intermediary between computer user and computer hardware, so the user program like word processor, spreadsheets want to utilize the computer hardware so to provide them the hardware the operating system is responsible for allocating the resource for those application based on the requirement, as they require keyboard access or mouse and so on. *it has goals like convenience and efficiency*


**what is computer system Operation**?
A modern general-purpose computer system consists of one or more CPUs and a number of device controllers connected through a common bus that provide access to shared memory 
![](https://i.imgur.com/RtY2BiO.png)
-each device controller is in charge of specific type of device
-the CPU and the device controller can execute concurrently, competing for memory cycles
-to ensure orderly access to the shared memory, a memory controller is provided whose function is to synchronize access to the memory


**What are Storage structure**?
-Register-they are the smallest devices which store binary values which be easily readable for computer.


**what is Computer System Architecture**?
Types are based on number of *general purpose processors*.

1.Single processor System:
-One main CPU capable of executing a General purpose instruction set from user also other special purpose processor are also present which perform device specific tasks

2.Multiprocessor System:
-Parallel system 
-two or more processors in close communication, sharing the computer bus and sometimes the clock, memory, and peripheral devices
-adv: 
--Increased  throughput, 
--economy of scale
![](https://i.imgur.com/LiMZQ1S.png)


3.Clustered System:
-Like MPS CS gather together multiple CPUs to accomplish computational work
-they are composed of two or more individual systems coupled together.
-Provides high availability
-can be asymmetrically and symmetrically


**What is Operating system Structure**?
Types
~*Multiprogramming*
-A single user cannot keep CPU busy all the time or the I/O devices at all ,
-Multiprogramming increase CPU utilization by organizing jobs so that the CPU always has one to executes.
~Multitasking 
-Cpu executes multiple jobs by switching among them
-Switches occur so frequently that the users can interact with each program while it is running
-Multitasking requires an interactive computer system which provides direct communication between the user and the system simultaneously.

**What are the services of OS**?
~User Interface-(CLI, GUI)
~Program Execution
~I/O operations
~File System Manipulation
~Communication
~Error Detection
~Resource allocation
~Protection and Security