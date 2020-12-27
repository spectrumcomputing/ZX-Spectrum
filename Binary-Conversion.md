




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
