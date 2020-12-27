
Immediate Addressing (Black)  
Register Addressing  (Orange)  
Register Indirect Addressing (Teal)  
Extended Addressing (Pastel Pink)

DOWN & ACROSS

![Image of Yaktocat](https://github.com/spectrumcomputing/ZX-Machine-Code/blob/main/Registers.jpg)

#### Immediate Addressing (Black)
```
LD A,N
LD B,N
LD C,N
LD D,N
LD E,N
LD H,N
LD L,N
LD BC,NN
LD DE,NN
LD HL,NN
```

#### Register Addressing  (Orange)
```
LD R,R
```
Works with registers A, B, C, D, E, H & L  
Note: There are no 16 Bit Instructions like LD HL,DE. Instead use:
```
LD H,D
LD L,E
```
#### Register Indirect Addressing (Teal)
```
LD (RR),A
LD A,(RR)
LD (HL),N
```
Example: LD A,(HL) - Load the A registers with the contents pointed at in the HL Register Pair.
```
LD R, (HL) 
Works with registers A, B, C, D, E, H & L  

LD A, (BC)
LD A, (DE)
```
```
LD (HL),R
Works with registers A, B, C, D, E, H & L  

LD (BC),A 
LD (DE),A 
```
LD (HL),N - Not in Graphic Above

#### Extended Addressing (Pastel Pink)

The general form is LD A,(NN) or LD (NN),A - Only A Regsister! 

If you want to do LD (NN),B you could do:

LD A,B
LD (NN),A

Or

LD HL,(nn) or LD (nn),HL

LD A,(NN)
LD (NN),A

LD BC or DE or HL ,(NN)
LD (NN),BC or DE or HL

#### Indexed Addressing
