The python interpreter is a compiler and a virtual machine linked together.
*Def*-
	simple-a interpreter is a program that directly executes a higher level program with out needing to compile the program before hand
	own - a interpreter is a low level virtual machine paired with a compiler to run high level code on demand/ line by line without having to compile the whole code before hand. the compiler compiles the code while running line by line.

1] _for python compile_ it does not compile the code in the same way as the c compile does. where as the c compiler compiles c code into machine code; the python compiler compiles its code into byte code
		difference between bytecode and machine code
			##bytecode
				1)it is a low-level representation of computer program 
				2)it is way more readable than assembly and less abstract
				3)it is more portable as it runarcitectures on a low-level virtual machine that can be compiled for different from different machines on release
				4)less speed 
			##machine code
				1)it is basically binary but it is usually represented in assembly for humans
				2)it is less readable
				3)it is is less portable as the code needs to be compiled for different os/cpu architecture seperately
				4)it is fast as fuck boi
2]the python virtual machine- well it explains itself; Its a virtual machine that is written in C and is packaged with the python program.... and not much is needed for now.