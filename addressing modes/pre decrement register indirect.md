this is very similar to [[post increment register indirect]] and [[indirect addressing]]

like [[post increment register indirect]] but its quite literally the opposite. 

Slide definition: *Same as indirect, but the address in the register is first decremented by the side of the operand (in bytes {the suffix size}) before its used*

`MOVE.W -(A0), D0`
this is saying go to the address of `A0` and store the contents from `A0 TO A0 - .W` so its reading backwards, then it increments the address back by the size of the suffix.

here are a couple of examples from the slides, that would make sense, keep an eye on the before and after on the data and address registers

![[Pasted image 20241013230423.png]]
- so it starts from `1004` then goes back 2 bytes cause word size
- then reads 2 bytes ahead and stores it in `D0` where it then reaches `1004` 
	- so it reads `0304` and stores that in `D0` as it should be
- then it DECREMENT'S the address in the address register by the size of the suffix which in this case is 2 bytes

#### attributes
- faster than absolute addressing
- slower than direct addressing 
- shorter instruction

#### instruction format
instruction mode format: `100`
instruction register format:  `000-111` the address register number

![[Pasted image 20241013230932.png]]
**==(a0)+ is wrong in that photo, its supposed to be -(a0) and yes the mode for source is right its supposed to be `100`  that's right==**


[[indirect addressing with displacement]]