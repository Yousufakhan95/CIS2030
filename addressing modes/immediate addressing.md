Operand is contained inside the instruction using one or two extension words

`MOVE.suffix(only word or long word) #VALUE, DATA_REGISTER or $MEMORY_ADDRESS`
#### attributes
- specified using # symbol
- longest and slowest instruction (like absolute long)
- used for all true constants and to initialize memory and registers
- can only be used to specify a source operand

#### questions
- what happens if you pass in an address like `$FF`
	- like when you read it does it act like a normal value or an address

#### instruction format
instruction mode format: `111`
instruction register format: `100`

the extension words will contain the value your trying to pass into the address or register and its either one extension word or two depending on word size or longword


| 15      | 14  | 13   | 12  | 11                   | 10  | 9   | 8    | 7   | 6   | 5               | 4   | 3   | 2    | 1   | 0   |
| ------- | --- | ---- | --- | -------------------- | --- | --- | ---- | --- | --- | --------------- | --- | --- | ---- | --- | --- |
| op code |     | Size |     | Destination register |     |     | mode |     |     | Source register |     |     | mode |     |     |
| 0       | 0   | 1    | 0   | 0                    | 0   | 0   | 0    | 0   | 0   | 1               | 0   | 0   | 1    | 1   | 1   |
`MOVE.L #$FF, D0 = 0010000000100111
- moving the value `$FF` to data register `D0`
- in hexadecimal the instruction is `203C`
- the full instruction will look like `203C 0000 00FF`
- the length of the extension words vary from 1 or two depending on either word or long format. (they contain the value you want to pass into that address)

