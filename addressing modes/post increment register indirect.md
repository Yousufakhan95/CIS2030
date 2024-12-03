this builds upon [[indirect addressing]] but like in the name, it increments the address

Slide definition: *Same as indirect, but after operand is used, the address in the register is incremented by the side of the operand*( in bytes, but also by the size of the suffix, so .B will be bytes, .W is 2 bytes, and .L is 4 bytes )

`MOVE.B (A0)+, D0`
this is saying take the contents of A0 and move it to D0, then increment the address of A0 by the size of the suffix which in this case is 1 bytes

here are two examples:
![[Pasted image 20241013220116.png]]
- basically taking the contents of `$1000` and putting them in `D0` then incrementing the address by 1 byte

![[Pasted image 20241013220133.png]]
- basically taking the contents of `A0` in longword form this time, so that will be `01020304` putting them in `D0` then increments the address in `A0` by 4 bytes cause we used the `.L` suffix
#### attributes
- Faster than absolute addressing
- slower than direct addressing
- shorter addressing
#### instruction format
instruction mode format: `110`
instruction register format: `000-111` the number of the address register

there will be no extension words in the instruction BECAUSE of this addressing mode because the address its referencing is already in the address register, the complementing address may need extension words

![[Pasted image 20241013220911.png]]

