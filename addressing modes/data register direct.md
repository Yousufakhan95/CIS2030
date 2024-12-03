this is just like [[indirect addressing]] but for the data register instead of the address register

used to access, source, and manipulate data with in data registers

`MOVE.suffix DATA_REGISTER, DATA_REGISTER`
#### attributes
- Fastest address mode
- shortest instruction 
- typically used for temporary values and or frequently accessed variables

#### instruction format
==instruction mode format: `000`==

| 15      | 14  | 13   | 12  | 11                   | 10  | 9   | 8    | 7   | 6   | 5               | 4   | 3   | 2    | 1   | 0   |
| ------- | --- | ---- | --- | -------------------- | --- | --- | ---- | --- | --- | --------------- | --- | --- | ---- | --- | --- |
| op code |     | Size |     | Destination register |     |     | mode |     |     | Source register |     |     | mode |     |     |
| 0       | 0   | 0    | 1   | 0                    | 1   | 1   | 0    | 0   | 0   | 0               | 0   | 0   | 0    | 0   | 0   |

`MOVE.B D0,D3`= `001011000000`
- byte suffix is 01
- D3 is destination which is 011 and D0 is 000
- mode is 000 for direct register direct
##### detailed
- op code is just 00
- size is
	- byte: 01
	- word: 11
	- long word: 10
- destination:
	- register: the register number so `d3 = 011`
	- notice how the register number is the binary equivalate
	- mode: the addressing mode which is `000` for data register direct
- register:
	- register: the register number (remember from 0 to 7)
	- mode: the addressing mode which is `000` for data register direct

===this note is done for now===
