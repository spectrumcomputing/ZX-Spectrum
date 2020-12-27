
```
main: ld hl,7d00h   ;Store loading screen at 32,000 decmal
      ld de,4000h   ;Start of screen area (16,384 decimal)
      ld bc,1800    ;Length of screen memory (6,144 decimal)
      ldir
      ret
```
```
LOAD "" CODE 32000
```
```
10 FOR A=30000 TO 30011: INPUT B: POKE A,B: NEXT A
```
```
33,0,125,17,0,64,1,0,27,237,176,201
```
```
10 RANDOMIZE 30000
20 PAUSE 0
```

