### Using Registers


#### Immediate Addressing
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

#### Register Addressing
```
LD R,R
```
Works with registers A, B, C, D, E, H & L  
Note: There are no 16 Bit Instructions like LD HL,DE. Instead use:
```
LD H,D
LD L,E
```
#### Register Indirect Addressing


```
LD A, (HL) 
LD B, (HL) 
LD C, (HL) 
LD D, (HL) 
LD E, (HL) 
LD H, (HL) 
LD L, (HL) 
```
```
LD A, (BC)
LD A, (DE)
```
```
LD (HL),A
LD (HL),B
LD (HL),C
LD (HL),D
LD (HL),E
LD (HL),H
LD (HL),L
```
```
LD (BC),A 
LD (DE),A 
```
```
LD (HL),N
```
#### Extended Addressing
```
LD A,(NN)
LD (NN),A
```
If you want to do LD (NN),B you could do:
```
LD A,B
LD (NN),A
```

```
LD BC,(NN)
LD DE,(NN)
LD HL,(NN)
```
```
LD (NN),BC
LD (NN),DE
LD (NN),HL
```

#### Indexed Addressing
