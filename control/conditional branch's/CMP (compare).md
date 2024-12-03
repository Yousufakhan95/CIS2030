at its core this is just subtraction. however it has the power to edit the CCR (*in a smart way not just putting in the subtraction result into the ccr"*)
- check out the CCR flags how the flags would be affected depending on your comparison 
#### Some More Specific Syntax:
`CMP <ea>, Dn` and the comparison will be `<DN> - <ea>` which will affect the CCR (condition code register)
#### CCR flags
here are the CCR flags that concern us. the CMP
![[Pasted image 20241022203808.png]]

#### Quick Example
here are the CMP commands in action and you can see how they affect the CCR, this will go more in depth for each specific CMP instruction
```cpp
D0: $0000007
D1: $0000007
D2: $0000005
// if it was like a ascii string it would just be the ascii values here

CMP.B D0, D1
// N = 0
// Z = 1
// V = 0
// C = 0

CMP.B D2, D0
// N = 0
// Z = 0 
// V = 0
// C = 0
```

#### going more in-depth on each specific CMP instruction
- [[CMP]] : data register
- [[CMPA]] : address register
- [[CMPI]] : immediate value
- [[CMPM]] : memory locations
#### Extra Stuff:
![[Pasted image 20241025203017.png]]
![[Pasted image 20241025201340.png]]