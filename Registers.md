
Immediate Addressing (Black)  
Register Addressing  (Orange)  
Register Indirect Addressing (Teal)  
Extended Addressing (Pastel Pink)

![Image of Yaktocat](https://github.com/spectrumcomputing/ZX-Machine-Code/blob/main/Registers.jpg)

#### Immediate Addressing (Black)

LD R,N (A, B, C, D, E, H, L)
LD A,229 - Load Register A with 229

LD BC,NN
LD DE,NN
LD HL,NN

LD HL,16384 - Load the Register Pair HL with 16384

#### Register Addressing  (Orange)

The general form is LD R,R (A, B, C, D, E, H, L)

Note: There are no 16 Bit Instructions like LD HL,DE. Instead use LD H,D and LD L,E

#### Register Indirect Addressing (Teal)

The general form is LD (RR),A or LD A,(RR) or LD (HL),N

Example: LD A,(HL) - Load the A registers with the contents pointed at in the HL Register Pair.

LD A, B, C, D, E, H, L, (HL) 

LD A, (BC)
LD A, (DE)

LD (HL), A, B, C, D, E, H, L 
LD (BC),A 
LD (DE),A 

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
