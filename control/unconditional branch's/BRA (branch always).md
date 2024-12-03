
all unconditional branches basically look the same on a CFG (control flow diagram) but they are different in a couple of ways

BRA branches an offset relative to the PC. so what do i mean by that? basically where ever i am on the program i have to tell the BRA instruction my target address (*cant be any target address*) and it will "goto" that address by using the target address and your current address getting the diffrence and offsetting the PC by that amount

in other words:

```cpp
1 00002000 ORG $2000  
2 00002000 601E BRA.S AHEAD  
3 00002002 4E71 NOP  
4 00002020 ORG $2020  
5 00002020 4E71 AHEAD NOP  
6 00002022 60FE HERE BRA.S HERE  
7 00002024 4E71 NOP
```

its reading this code seeing the PC address of `AHEAD` is `2020` and taking the of where ever in the PC the BRA instruction finish's executing so that would be `2002` and taking there difference and adding it to the PC. To finally reach `AHEAD`

```
002020: Destination
002002: PC once done executing BRA
------------
00001E : Displacement
```

basically it takes that displacement and adds it to the PC 

#### Instruction Format

// side note for future yousuf: its the night before the midterm so shits gotta go a bit quicker 

![[Pasted image 20241025190848.png]]

so the difference between BRA.S and BRA.L is how far you can go with the displacement as its 8 bit displacement and 16bit.

![[Pasted image 20241025191001.png]]