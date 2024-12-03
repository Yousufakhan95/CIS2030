Operand is in **memory** and **address** of operand is contained in two extension words as part of the instruction
- so you have to list the address and it will grab the stuff inside it

`MOVE.suffix $MEMORY_ADDRESS, $MEMORYADDRESS`
#### attributes
- longest instruction
- slowest instruction
- used to access simple global variables
- keyword:  **absolute** works all through out the memory, but long works from `$008000-$FF7FFF` the first and last 32k bytes come under [[absolute short]] addressing
#### range

| short | `$FF8000`- `$FFFFFF` | `$3A38` |
| ----- | -------------------- | ------- |
| long  | `$008000`- `$FF7FFF` | `$3A39` |
| short | `$000000`- `$007FFF` | `$3A38` |

#### question?
- can you access the data register with this?
- what does it mean on slide 5 of addressing modes part 1. by 6 reads and 1 write

#### instruction format
instruction mode format: `111`
instruction register format: `001`
- because we are not referencing a specific register its set solid at `001`


| 15      | 14  | 13   | 12  | 11                   | 10  | 9   | 8    | 7   | 6   | 5               | 4   | 3   | 2    | 1   | 0   |
| ------- | --- | ---- | --- | -------------------- | --- | --- | ---- | --- | --- | --------------- | --- | --- | ---- | --- | --- |
| op code |     | Size |     | Destination register |     |     | mode |     |     | Source register |     |     | mode |     |     |
| 0       | 0   | 0    | 1   | 0                    | 0   | 1   | 1    | 1   | 1   | 0               | 0   | 1   | 1    | 1   | 1   |

`MOVE.B $9000, 9001 = 0001001111001111`
- that's just the instruction not extension words so the instruction still does not know where to go for `$9000 & $9001`
- so `0001001111001111` is equal to `13F9` in hexadecimal format. 
- the full instruction for this would look like
	- `13F9 0000 9000 0000 9001`
- the extension words contain the 32bit long address in hexadecimal.
##### detailed
- op code is just 00
- size is
	- byte: 01
	- word: 11
	- long word: 10
- destination and source:
	- just set to `001 111` for [[absolute long]] addressing 001 for register and 111 for absolute addressing.
	- again the register is set solid to 001 because we are not referencing the register