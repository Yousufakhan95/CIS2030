
the way a computer runs a program, its like working through a line down. executing each instruction one at a time, to compute a result

0 - 0 - 0 - 0 - 0

kinda like working through a process like this, an example bring converting a binary number to its 2's complement. flip each bit then add one

(the default operation of the processor is to execute a straight line sequence of instructions read from ===successive memory locations===)

but there is are a couple of problems to this:
- the program can reach the end of the memory and just be lost
- the big one is that the program can't do anything useful, it cant make decisions, its cant loop etc... 

the solution to this is to allow the computer to ===branch=== from its usual sequence. and it can branch off to another part of the memory per say. so todo a loop you just branch off back it runs again and the cycle repeats until it passes some condition which allows it continue down its normal sequence. 

so by definition: Branch instruction modify the flow of control and cause the program to continue execution at the target address specified by the branch

but there are two types of branch conditions:
-  [[unconditional branch's]]
	- this will always branch to where you want
-  [[conditional branch's]]
	- this will branch according to a condition

here are some examples of branches in use

[[implementations]] (branch implementations)