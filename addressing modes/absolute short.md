quick note: the 68k is actually 24 bit CPU. it doesn't use all of the 32bits 

so `0x00008000` is actually just `0x008000`

reference [[absolute long]] its more well written than this they are very simlar

- only works in the first and last 32k bytes of the memory
	- why? is because of sign extension. because we are only using 4 bytes to represent the address. which give us 32k options of addressing with hexadecimal. but because our memory is greater than 32k bytes when [[absolute short]] addressing is used the sign extension on the remaining bits open up our options to a total of 64k bytes
	- so the range for it is from `$000000` - `$007FFF` and `$FF8000` - `$FFFFFF`
	- if its somewhere inside that range the assembler may choose another addressing method like [[absolute long]], reference the range table below
- the instruction format for [[absolute short]] starts with  `$3A38` for [[absolute long]] it will just change to `$3A39`

##### **Range Table**

| short | `$FF8000`- `$FFFFFF` | `$3A38` |
| ----- | -------------------- | ------- |
| long  | `$008000`- `$FF7FFF` | `$3A39` |
| short | `$000000`- `$007FFF` | `$3A38` |

#### instruction format
instruction mode format: `111`
instruction register format: `000`
- because we are not referencing a specific register its set solid at `000`

#### **Slides for Reference**
![[Pasted image 20241006211805.png]]
![[Pasted image 20241006211819.png]]

