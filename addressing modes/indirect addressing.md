this is just [[data register direct]] but for the address register thats it

operand is in memory and address of operand is contained inside an **address register**

basically this is a pointer in the assembly language, 
- so if the contents that your trying to access is in the memory and you want to access it
- and the address to that "content"/"data" is in the address register and you want to access that value aka "dereference"
- you just call the address register like `(A0)`  
- something like this 
	- `MOVE.W (A0), D0`
	- so this will go to the address that's listed in (A0)
	- go get that value from that address
	- the store it in D0

#### instruction format
instruction mode format: `010`
instruction register format: `000-111` 
- because it can be from any of the address registers (remember) this is referencing the **address register**


#### example: 
![[Pasted image 20241013123057.png]]