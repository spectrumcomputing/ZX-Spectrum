
There are two screens in the Bytes: block at 6912 bytes each, which start at 49410. So there's no actual machine code until 63234. These are the start addresses you'll need:

USR 63234 - this routine isn't one of mine so don't go thinking it is (it's the PRINT42 routine that Einar recently found the author of)
My routines are rather shorter than that:
USR 63690  
USR 63702  
USR 63714  
USR 63859  
USR 63879  
USR 63900  
USR 63915  
USR 63930  

Some of these require values to be POKEd to nearby addresses before use. Take note of the listing.

###### Screen Layout (Top line of each character sqaure)
```
 0. 16384  
 1. 16416  
 2. 16448  
 3. 16480  
 4. 16512  
 5. 16544  
 6. 16576  
 7. 16608  
 8. 18432  
 9. 18464  
10. 18496  
11. 18528  
12. 18560  
13. 18592  
14. 18624  
15. 18656  
16. 20480  
17. 20512  
18. 20544  
19. 20576  
20. 20608  
21. 20640  
22. 20672  
23. 20704  
```
```
   10 POKE 23730,1: POKE 23731,193
   20 DIM t$(68,42): LOAD "" DATA t$()
   30 LOAD ""CODE 49410,15029
   40 BORDER 7: PAPER 7: INK 0: BRIGHT 0: FLASH 0: INVERSE 0: OVER 0: CLS : LET pd=160
   50 LET u=USR 63690
   60 FOR n=1 TO 22: FOR p=1 TO pd: NEXT p: LET z$=CHR$ 22+CHR$ (n-1)+CHR$ 0+t$(n, TO 20): LET u=USR 63234: NEXT n
   70 FOR p=1 TO 2*pd: NEXT p
   80 FOR n=0 TO 21: PRINT AT n,0;"               ": NEXT n
   90 FOR n=23 TO 44: FOR p=1 TO pd: NEXT p: LET z$=CHR$ 22+CHR$ (n-23)+CHR$ 0+t$(n, TO 20): LET u=USR 63234: NEXT n
  100 FOR p=1 TO 3*pd: NEXT p
  110 LET u=USR 63702
  120 FOR p=1 TO 2*pd: NEXT p
  130 FOR g=45 TO 55
  140 LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(g): LET u=USR 63234: NEXT g
  150 LET u=USR 63714: PRINT AT 17,0;"                                "
  160 FOR p=1 TO 3*pd: NEXT p
  170 FOR n=1 TO 20
  180 FOR p=1 TO 2*pd: NEXT p
  190 LET u=USR 63879
  200 LET x$="WAIT": FOR x=2 TO 5: POKE 63876,x: POKE 63877,CODE x$(x-1): LET u=USR 63859: FOR p=1 TO 40: NEXT p: NEXT x
  210 LET u=USR 63900
  220 LET u=USR 63930
  230 LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(56): LET u=USR 63234
  240 LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(57): LET u=USR 63234
  250 IF n<>6 AND RND<.8 THEN GO TO 270
  260 FOR g=58 TO 60: LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(g): LET u=USR 63234: NEXT g
  270 IF n<>20 THEN LET u=USR 63714: PRINT AT 17,0;"                                ": NEXT n
  280 NEXT n
  290 FOR g=61 TO 64: LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(g): LET u=USR 63234: NEXT g
  300 LET u=USR 63714: PRINT AT 17,0;"                                ": NEXT n
  310 FOR p=1 TO 1600: NEXT p
  320 LET u=USR 63879
  330 LET x$="OPEN CHEST": FOR x=2 TO 11: POKE 63876,x: POKE 63877,CODE x$(x-1): LET u=USR 63859: FOR p=1 TO 40: NEXT p: NEXT x
  340 LET u=USR 63915
  350 LET l=USR 63930
  360 FOR g=65 TO 67: LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(g): LET u=USR 63234: NEXT g
  370 LET u=USR 63714: PRINT AT 17,0;"                                ": NEXT n
  380 FOR p=1 TO 1600: NEXT p
  390 LET u=USR 63714: LET z$=CHR$ 22+CHR$ 17+CHR$ 0+t$(68): LET u=USR 63234
  400 LET u=USR 63714: PRINT AT 17,0;"                                ": NEXT n
  410 FOR p=1 TO 1600: NEXT p
  999 NEW 
```


```
63690 ld      hl,56322
63693 ld      de,16384
63696 ld      bc,6912
63699 ldir    
63701 ret   
```

```
63702 ld      hl,49410
63705 ld      de,16384
63708 ld      bc,6912
63711 ldir    
63713 ret    
```

```
63714 ld      hl,16416
63717 ld      de,16384
63720 ld      bc,2016
63723 ldir    
63725 ld      b,8
63727 ld      hl,18432
63730 ld      de,16608
63733 push    bc
63734 ld      bc,32
63737 ldir    
63739 ld      bc,224
63742 add     hl,bc
63743 ex      de,hl
63744 add     hl,bc
63745 ex      de,hl
63746 pop     bc
63747 djnz    63733
63749 ld      hl,18464
63752 ld      de,18432
63755 ld      bc,2016
63758 ldir    
63760 ld      b,8
63762 ld      hl,20480
63765 ld      de,18656
63768 push    bc
63769 ld      bc,32
63772 ldir    
63774 ld      bc,224
63777 add     hl,bc
63778 ex      de,hl
63779 add     hl,bc
63780 ex      de,hl
63781 pop     bc
63782 djnz    63768
63784 ld      b,8
63786 ld      hl,20512
63789 ld      de,20480
63792 push    bc
63793 ld      bc,32
63796 ldir    
63798 ld      bc,224
63801 add     hl,bc
63802 ex      de,hl
63803 add     hl,bc
63804 ex      de,hl
63805 pop     bc
63806 djnz    63792
63808 ld      b,8
63810 ld      hl,20512
63813 ld      de,20513
63816 push    bc
63817 ld      (hl),0
63819 ld      bc,31
63822 ldir    
63824 ld      bc,225
63827 add     hl,bc
63828 ex      de,hl
63829 add     hl,bc
63830 ex      de,hl
63831 pop     bc
63832 djnz    63816
63834 ld      hl,22560
63837 ld      de,22528
63840 ld      bc,576
63843 ldir    
63845 ld      hl,23072
63848 ld      (hl),56
63850 ld      de,23073
63853 ld      bc,31
63856 ldir    
63858 ret     
```

```
63859 ld      a,1
63861 call    5633
63864 ld      de,63874
63867 ld      bc,5
63870 call    8252
63873 ret     
```

```
63879 ld      a,1
63881 call    5633
63884 ld      de,63894
63887 ld      bc,6
63890 call    8252
63893 ret    
```

```
63900 ld      a,1
63902 call    5633
63905 ld      de,64067
63908 ld      bc,4
63911 call    8252
63914 ret     
```

```
63915 ld      a,1
63917 call    5633
63920 ld      de,64071
63923 ld      bc,4
63926 call    8252
63929 ret     
```

```
63930 ld      hl,20608
63933 ld      de,20576
63936 ld      b,8
63938 push    bc
63939 ld      bc,32
63942 ldir    
63944 ld      bc,224
63947 add     hl,bc
63948 ex      de,hl
63949 add     hl,bc
63950 ex      de,hl
63951 pop     bc
63952 djnz    63938
63954 ld      hl,20640
63957 ld      de,20608
63960 ld      b,8
63962 push    bc
63963 ld      bc,32
63966 ldir    
63968 ld      bc,224
63971 add     hl,bc
63972 ex      de,hl
63973 add     hl,bc
63974 ex      de,hl
63975 pop     bc
63976 djnz    63962
63978 ld      hl,20672
63981 ld      de,20640
63984 ld      b,8
63986 push    bc
63987 ld      bc,32
63990 ldir    
63992 ld      bc,224
63995 add     hl,bc
63996 ex      de,hl
63997 add     hl,bc
63998 ex      de,hl
63999 pop     bc
64000 djnz    63986
64002 ld      hl,20704
64005 ld      de,20672
64008 ld      b,8
64010 push    bc
64011 ld      bc,32
64014 ldir    
64016 ld      bc,224
64019 add     hl,bc
64020 ex      de,hl
64021 add     hl,bc
64022 ex      de,hl
64023 pop     bc
64024 djnz    64010
64026 ld      b,8
64028 ld      hl,20704
64031 ld      de,20705
64034 push    bc
64035 ld      (hl),0
64037 ld      bc,31
64040 ldir    
64042 ld      bc,225
64045 add     hl,bc
64046 ex      de,hl
64047 add     hl,bc
64048 ex      de,hl
64049 pop     bc
64050 djnz    64034
64052 ld      a,1
64054 call    5633
64057 ld      de,64075
64060 ld      bc,4
64063 call    8252
64066 ret     
```
