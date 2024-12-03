this is basically the bigger picture on conditional branches and we can look at them under this one big umbrella and they split on to there own post this.

```cpp
BCC <label>

// these two are basically equivlant

if (label == True){
	PC -> PC + displacement
}
// else is just continue going
```


so if you look at it in the "memory" or what ever it is. if condition is true then it will branch if not it will keep going down its sequence
### how these things work? (here is the flow)
1. you have to do a CMP before a BCC command
2. the CMP executes and populates its results in the CCR
3. the BCC instruction reads the new updated CCR and makes its decision off that
4. if the condition is true it branches to the label given
5. if not then it continues down the code

here are the CCR flags that concern us, which will affect how we branch.

![[Pasted image 20241022203808.png]]

N is not affect by unsigned branches
N is only affected by signed branches
### Visual Example
![[Pasted image 20241025200633.png]]
this stack / CFG example is a good example for how the code flows
### types of conditional branches
-  [[Conditional branch instruction depending on a single CCR flag]]
-  [[conditional branch instruction for signed numbers]]
-  [[conditional branch instruction for unsigned numbers]]
### a way to memorize branches
![[IMG_1212.jpg]]

![[Pasted image 20241026082158.png]]
the condtions are not right though