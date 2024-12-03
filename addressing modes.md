before you even dive into the different address modes you should know ==what they do== and ==why we need multiple==

- what they do?
	- in a very broad sense address modes help us access and manipulate data
	- to be more specific they tell the assembler on ==how== to access the data we refenced for an instruction  
	- ^^^ the whole thing
	- the way the textbook explains it:
		- the type of function to be performed and the location of the operand(s) on which to perform that function. *the method of location the operand(s) are explained in this section*
- why we need multiple? (as seen below)
	- well the reason i asked this question is because one addressing mode can do the job for everything
	- but we use multiple because certain addressing modes are powerful in certain use cases. so the answer to that is performance, and efficiency.
	- also certain address modes can only do certain things not. all (yes you can design a program around one address more) but when you have these more tailored one it makes your life easier in some sense
		- this is just so i don't contradict my own statement

KEY-POINT: the addressing mode DOES NOT need to be specified, you can if you want to, or need to for your program, but the assembler can take care of it.
 - for this unit we are using them in different ways so in many cases we do need to specify it, especially because we are also using the address register.

SIDE NOTES: 
- address registers do not allow byte operations, they only allow word or long word operations, 
- address register A7 is used as a stack pointer
- address register specific operands do not affect the CCR flag (what is the CCR flag?)
- address registers are 32bit signed entities
	- `ADDA.L #$FFF4, A0`  becomes into `A0 = A0 + $0000FFF4`
	- `ADDA.W #$FFF4, A0` becomes into `A0 = A0 + $FFFFFFF4` 
	- NOTICE: the suffix !!! the .W sign extends

#### **Example:**
```
MOVE source, destination
```

addressing modes is telling the assembler how to access the source and destination (if i understand that correctly)

#### **Different types of Addressing Modes**
- [[data register direct]]
- [[absolute short]]
- [[absolute long]]
- [[immediate addressing]]
- [[indirect addressing]]
- [[post increment register indirect]]
- [[pre decrement register indirect]]
	- [[indirect addressing with displacement]]
- [[register indirect with offset]]
- [[register indirect with index and offset]]
- [[PC-relative with offset]]
- [[PC-relative with index and offset]]

#### there instruction format "codes":
![[Pasted image 20241013095253.png]]