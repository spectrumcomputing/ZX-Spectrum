### Spectrum Computing Forums

https://spectrumcomputing.co.uk/forums/viewtopic.php?p=52480#p52480


This is one of those problems that's an ideal opportunity to solve along the course of my machine code quest. Only thing is, I've not yet reached the point where I can read BASIC-assigned variables with machine code - but I can do most of it, just POKE one value, define an empty string b$, and execute the code. I've taken 64 bytes, which are assembled from 65000 to 65064 in this routine. As it stands, with the fixed numbers in the DATA lines, this has to stay at 65000, but the assembler code I've posted below the BASIC listing can be pasted into SPIN and assembled anywhere, and it'll work out all the new addresses to pick the values from and JR Z to.

Essentially, assemble to ad, POKE the value v to be converted into ad+65, and LET l=USR ad. The machine code will initially poke the value 48 into addresses ad+66 to ad+73, then analyse the value v and for every 1 in the binary value, it will increase the corresponding address from 48 to 49. All the BASIC then has to do is PEEK the addresses and add CHR$ of the CODE stored at that address to b$.

I've made this loop v from 0 to 255 so it displays all the values and shows how fast the routine is. You can paste this into a text editor, get shot of the REMs, bunch multiple statements into fewer lines, and cut out anything extraneous. Then paste that into BASin, renumber it as required, and save it as a Z80 snapshot. The code can saved and reloaded, just don't forget to CLEAR one less than the start address.

```
10 REM decimal to binary with machine code
20 CLEAR 64999
30 LET ad=65000
40 GO SUB 9000
50 FOR v=0 TO 255
60 LET b$=""
70 POKE ad+65,v
80 LET l=USR ad
90 FOR n=ad+66 TO ad+73
100 LET b$=b$+CHR$ (PEEK n)
110 NEXT n
120 POKE 23692,255
130 PRINT v;TAB 4;b$
140 NEXT v
999 STOP
9000 REM machine code
9010 RESTORE 9900
9020 FOR n=ad TO ad+64
9030 READ byte
9040 POKE n,byte
9050 NEXT n
9060 RETURN
9900 DATA 33,42,254,6,8,54,48,35,16,251
9910 DATA 58,41,254,33,42,254,203,127,40,1,52,35,203,119,40,1,52,35,203,111,40,1,52,35,203,103,40,1,52
9920 DATA 35,203,95,40,1,52,35,203,87,40,1,52,35,203,79,40,1,52,35,203,71,40,2,52,35,201
```


```
; 9900 DATA...

init:	ld hl,b7	; put address "b7" into HL
	ld b,8		; loop 8 times
loop1:	ld (hl),48	; POKE address held in HL with 48
	inc hl		; point HL to next address
	djnz loop1	; DEC B and loop until B=0
; eight addresses after STORE are loaded with the CODE for "0"

; 9910 DATA...

main:	ld a,(store)	; put the stored value into accumulator	
ch7:	ld hl,b7	; put HL back to address "b7" again
	bit 7,a		; check bit 7 of A
	jr z,ch6	; if bit 7 is 0, skip the next lines
	inc (hl)	; if bit 7 is 1, increase value held in "b7" by 1, i.e it is now CODE "1"
ch6:	inc hl		; first now increase the address HL points to, to "b6"
	bit 6,a		; and so on...
	jr z,ch5
	inc (hl)
ch5:	inc hl
	bit 5,a
	jr z,ch4
	inc (hl)
ch4:	inc hl
	bit 4,a
	jr z,ch3
	inc (hl)

; 9920 DATA...

ch3:	inc hl
	bit 3,a
	jr z,ch2
	inc (hl)
ch2:	inc hl
	bit 2,a
	jr z,ch1
	inc (hl)
ch1:	inc hl
	bit 1,a
	jr z,ch0
	inc (hl)
ch0:	inc hl
	bit 0,a
	jr z,finale
	inc (hl)
	inc hl
finale:	ret

; these aren't in the DATA statements - you POKE the value shown, the machine code works out the other eight bytes

store:	defb 0	; start address + 65 - POKE value to convert here
b7:	defb 0	; these will be 48 (CODE "0") or 49 (CODE "1") at end of routine. 
b6:	defb 0
b5:	defb 0
b4:	defb 0
b3:	defb 0
b2:	defb 0
b1:	defb 0
b0:	defb 0
```
