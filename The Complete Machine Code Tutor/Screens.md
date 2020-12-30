### <div align="center">The Complete Machine Code Tutor</div>

                      by
                 MALCOLM EVANS

                 48K SPECTRUM

                Copyright 1984
           New Generation Software Ltd.
                     Bath,
                     Avon


             LOADING INSTRUCTIONS

This program is arranged on four sides of tape.

To load the program type LOAD "" using side 1.
This will load in the screen and program/simulator.
When instructed stop the tape. Do not press BREAK
during the loading of the simulator.

You will then be asked whether you wish to load
lessons.

If no (N) you will enter straight into the editor
part of the simulator. This is not recommended for
beginners. You may escape by pressing BREAK.

If yes (Y) you will be requested to load the
required group of lessons. Choose the desired
section and start the tape recorder. The group you
have chosen, will appear on the screen. If you have
selected the wrong group, pressing BREAK will stop
the load, and enable you to load another section

The program and lessons are arranged on the cassette
tapes as follows.

SIDE 1 - Program/simulator :  Lessons 1  -  9
SIDE 2 - Lessons 10 - 17   :  Lessons 18 - 25
SIDE 3 - Program/simulator :  Lessons 18 - 25
SIDE 4 - Lessons 26 - 35   :  Lessons 1  -  9


           ASSEMBLER INSTRUCTIONS

The assembler accepts all Z80 instructions as
included in the lesson summaries. In addition it
will accept the following instructions itself:

DEFB n  :  Define byte.  This allocates the
           Next memory location for storage.
           (This may be labelled), and initially
           loads it with n. The simulator will
           continually display the contents of
           the location in decimal or hex.

DEFW nn :  Define word. This allocates the next
           two memory locations for storage
           (may be labelled), and initially loads
           it with the two byte number nn. The
           simulator will continually display
           the contents of these locations as
           a single decimal or hex number.

BIN n   :  This is the same as DEFB, except that
           The simulator displays the memory
           contents in binary form. N is a
           decimal or hex number.

The assembler will also accept labels. A label is
defined in relationship to numbers as follows:

Decimal number     :  Any string containing only
                      0-9

Hexadecimal number :  Any string containing only
                      0-9 or A-F. It may be
                      distinguished from decimal
                      by following it with a H.

Label              :  Labels a memory location.
                      Any string not covered by
                      decimal or hexidecimal numbers
                      above, register names or
                      conditional letters i.e. C,
                      NC, Z, NZ, etc. The maximum
                      length is 6 characters.


ERROR MESSAGES - ASSEMBLER

Instruction unknown  -  First part of mnemonic not
                        recognised.

Space missing        -  Space missing after first
                        part of mnemonic i.e. LDA,5.

Missing space or ,   -  Space or , missing after
                        second pair of mnemonic
                        i.e. LD A5 or SUB AM

Error after instr.   -  Error after first part of
                        mnemonic which the assembler
                        was unable to recognize as
                        any other defined error.

Number missing       -  Part of mnemonic missing.
                        Could be a number.

Bracket missing      -  A bracket missing.

Number too large     -  16 bit number greater than 65535.

Label too long       -  Labels can only have up to 8
                        characters.

Label not found      -  Label appears in instruction
                        but not declared in label
                        column.

No DEFM or DEFW      -  Label with no instruction.

Can only add IX/IY   -  SBC IX/IY or ADC IX/IY found.

Offset too big       -  Offset in (IX+d) or (IY+d)
                        instruction greater than 255.

Offset missing       -  No offset in (IX+d) or (IY+d)
                        instruction.


ERROR MESSAGE - SIMULATOR

                     -  Your program has caused the
                        PC to jump to an adress which
                        is not the beginning of one
                        of your instruction lines.

You are trying to run code in allocated storage area

                     -  Your program has caused the PC
                        to jump to an adress which has
                        been allocated as storage.

You are about to affect memory area not allocated to
you
                      -  you are about to load a
                         memory location not allocated
                         to you. Your allocated area
                         is 16384 (4000h) to 23295
                         (5AFFh) and 32000 (7D00h) to
                         32192 (7DC0h)

You are about to write to memory which will affect your
program
                      -  you are about to load a
                         memory location within your
                         program instructions.

The stack pointer is outside allocated memory area

                      -  The stack pointer has moved
                         outside the area 32193 (7DC1h)
                         to 32255 (7DFFh).

There are too many registers called up

                      -  your program uses more
                         registers than the simulator
                         can display. The program
                         can be run, but only those
                         registers displayed can be
                         shown.

The lessons in this program are arranged in four
groups.	Upon loading of each section an introduction
appears on the screen. The menu for the group of
lessons can then be obtained by pressing SPACE, at
any time whilst in a lesson or example. Pressing BREAK
(CAPS SHIFT + SPACE) will return you to the menu.

The following is a complete list of all keys used at
various stages with a full description of their
function.


MENU

ENTER       :   Will enter any lesson or
                example highlighted on the menu.

SPACE       :   Pressing this key allows you to choose
                which item to enter.

LESSON AND EXAMPLE TEXT

SPACE       :   Pressing thls key will display the next
                page. At the end of each lesson it will
                effect a return to menu

BREAK       :   Will return you to the menu at any time.


SIMULATOR  -  All keys auto-run.

RUN         :   This clears all registers and starts
                program running.

ANY KEY     :   If in running state will perform the
                highlighted instruction.

STOP        :   This stops the running of the program.
(a+symbol shift)

EDIT        :   Pressing this key enters the editor,
(I+ symbol      allowing you to modify or re-write the
shift)          program.

G           :   This swops the display between decimal
                and hexadecimal notation. This key is
                operative only when the program is NOT
                running.

BREAK       :   Will return you to the menu.

Once completed if you wish to repeat the exercise then
press RUN.


EDITOR  -  All keys auto-run

CURSOR KEYS :   Pressing these will allow you to
(5,6,7,8 +      move the cursor in the direction of
CAPS SHIFT)     the arrows.

&           :   This clears the editor screen and
(6 + symbol     memory and returns the cursor to
shift)	        the start of the screen.

SPACE       :   Tabs to beginning of instruction
                when in label column, elsewhere
                a space will be created.

ENTER       :   This moves the cursor to the start
                of the next line.

DELETE	    :   This deletes the character to the
(0+CAPS         left of the cursor and shifts the
SHIFT)	        cursor one space to the left.

STOP        :   Initiates assembly of the program
                on screen. If assembled correctly
                the simulator mode is entered. If
                an error is found then an error
                statement is displayed against the
                appropriate line of the program and
                the editor waits for correction.

BREAK       :   Will return you to the menu.

The editor allways displays letters in capitals.
However CAPS SHIFT is not required.


INTRODUCTION TO LESSONS

The Complete Machine Code Tutor contains 35
lessons covering all the instructions on the z80
processor. Which is the processor in your Spectrum
computer.

All the lessons are dealt with in great detail on
screen. And in many cases are followed by example
programs, which you can use as exercises by
modifying them yourself. There is no danger that
you might crash the system.

There now follows a list of all the lesson headings,
together with an indication of those lessons that
are followed by examples. Under each heading there
is a summary of instructions which will become clear
to you as you progress through the tutor. These
summaries are intended as a permanent record of
instructions, to which you can easily refer for
revision purposes, without having to refer back to
the screen text.


LESSON 1    -   Registers and Memory
                Initially we only consider A,B,C,D,
                E,H And L registers.


LESSON 2    -   Simple Load Instructions
                The following instructions are covered:

LD r,r'         Where r and r' are any of the following:
                A,B,C,D,E,H and L.
LD r,n          Where n is a number 0 - 255.
LD A,(nn)       Where nn is a memory location 0 - 65535.
LD (nn),A       Where nn is a memory location 0 - 65535.
                Examples follow this lesson.


LESSON 3   -    Register Pairs
                A number  in a register pair is 256 x
                the high byte + the low byte.

                The following instructions are covered:
LD dd,nn        Where dd is any register pair
                BC, DE and HL.
                nn is a number 0 - 65535.
LD dd,(nn)      where nn is address of a memory location
                0 - 65535.
LD (nn),dd      where nn is address of a memory location
                0 - 65535.
EX DE,HL        Exchanges register contents.
                Examples follow this lesson


LESSON 4    -   Indirect Adressing

                The following instructions are covered:
LD r,(HL)       Where r is any single register -
LD (HL),r       A,B,C,D,E,H OR L.
LD A,(BC)
LD A,(DE)
LD (BC),A
LD (DE),A
				Examples follow this lesson.


LESSON 5    -   Additions and the Carry Flag
                Additions with Accumulator and HL
                register pair are discussed as well as
                ADD with Carry.

                The following lnstructions are covered:


ADD A,n	        Where n is a number 0 - 255.
ADD A,R	        Where r is any single register.
ADD A,(HL)
ADD HL,BC
ADD HL,DE

ADC A,n         ADD with Carry.
ADC A,r
ADC A(HL)
ADC HL,BC
ADC HL,DE
                2 examples follow this lesson.

LESSON 6    -   Subtraction and the carry flag
                Subtraction with and without carry on
                the accumulator and HL register pair are
                discussed.
                The following instructions are covered:
SUB n       )
SUB r       )   Subtract from A, n, r  or (HL)
SUB (HL)    )

SBC A,n     )
SBC A,r	    )   Subtract from A with carry
SBC A,(HL)  )

SBC HL,BC   )   Subtract from HL with carry
SBC HL,DE   )

SCF             Set carry flag
CCF             Compliment carry flag
                2 examples follow this lesson.

LESSON 7    -   Increment And Decrement Instructions
                The following instructions are covered:
INC n
INC (HL)
INC dd

DEC r
DEC (HL)
DEC dd
                Examples follow this lesson

LESSON 8    -   The zero flag

                No new instructions are covered in
                this lesson, which is included to show
                you the effect on the zero flag of all
                the instructions considered in
                previous lessons.
                A table of the effects of all
                instructions on all flags is given in
                appendix (A)
                examples follow thls lesson

LESSON 9    -   Compare
                If n is the number with which A is
                compared, then the following results:
                                  Carry    Zero
                A greater than n    0       0
                A equals n          0       1
                A less than n       1       0
                The following instructions are covered:
CP n            Compares A with n (o-255)
CP r            Compares A with register r
CP (HL)         Compares A with memory location (HL)
                Examples follow this lesson

LESSON 10   -   Conditional & Unconditional Jumps
                The following instructions are covered:
JP nn
JP (HL)
JR NC,nn        Jump if carry flag not set
JP C,nn         Jump if carry flag set
JP NZ,nn        Jump if zero flag not set
JP Z,nn         Jump if zero flag set
                Examples follow this lesson


LESSON 11  -    Relative Jumps
                The following instructions are covered:
JR e            Where e is the displacement in the
                range 127 to -128.
JR NC,e
JR C,e
JR NZ,e
JR Z,e
DJNZ e          Decrement and jump on non zero
                2 examples follow this lesson.


LESSON 12  -    The Stack
                The stack and the stack pointer are
                introduced.
                The following instructions are covered:

PUSH dd         Where dd is AF, BC, DE or HL. From
                now on dd can be considered as BC, DE,
                HL or SP.

POP dd
LD SP,nn
LD SP,(nn)
LD (nn),SP
LD SP,HL
ADD HL,SP
ADC HL,SP
SBC HL,SP
INC SP
DEC SP
EX (SP),HL
                Examples follow this lesson.


LESSON 13   -   Calls To Subroutines
                The following instructions are covered:
CALL            RET        Unconditional
CALL NC,nn      RET NC     No carry
CALL C,nn       RET C      Carry set
CALL NZ,nn      RET NZ     Not zero
CALL Z,nn       RET Z      Zero set
                2 examples follow this lesson.


LESSON 14   -   Binary Notation
                This lesson is about a whole new number
                base - binary. This is a system of
                using only two different numbers, one
                and zero. In each digit column, a
                flag is an excellent example of a
                binary digit. This is because it can
                only hold a value of one or zero. After
                reading the lesson about binary, you may
                find this reference chart useful:

Values of Bit 7 TO Bit 0:
Bit number :	 7   6   5   4   3  2  1  0
Values     :    128  64  32  16  8  4  2  1
                Examples follow this lesson


LESSON 15   -   Hexadecimal Notation
                Hexadecimal notation is discussed at
                great length in this lesson, but the
                following table will prove an
                invaluable reference:-

                Decimal Binary Hexadecimal
                   0     0000      0
                   1     0001      1
                   2     0010      2
                   3     0011      3
                   4     0100      4
                   5     0101      5
                   6     0110      6
                   7     0111      7
                   8     1000      8
                   9     1001      9
                  10     1010      A
                  11     1011      B
                  12     1100      C
                  13     1101      D
                  14     1110      E
                  15     1111      F
                Examples follow this lesson.


LESSON 16   -   Binary Coded Decimal Notation
                The instruction DAA (decimal adjust
                accumulator) is introduced.
                Examples follow this lesson.


LESSON 17   -   Positive & Negative Number Notation
                The instructions introduced are CPL
                (complement) and NEG (negate). As well
                as the overflow and sign flags. A table
                of the effects of all instructions on
                the overflow and sign flags is given
                in appendix (A).
                Examples follow this lesson.


LESSON 18   -   Parity
                The parity flag and its uses are
                introduced.
                A table of the effects of all
                instructions on the parity flag is given
                in appendix (A).


LESSON 19   -   The flag register and AF register
                pair


LESSON 20   -   Sign & P/V flags in instructions
                the following instructions are covered:

JP PO,nn        CALL P0,nn  RET PO   Parity odd = 0
JP PE,nn        CALL PE,nn  RET PE   Parity even = 1
JP P,nn         CALL P,nn   RET P    Sign +ve
JP M,nn         CALL M,nn   RET M    Sign -ve
                If the condition is not met, the program
                will not jump, call a subroutine or
                return.
                Examples follow this lesson.


LESSON 21   -   Bit Manipulation
                The following instructions are covered:
SET n,r         Where n is the bit number 0-7.
SET n,(HL)
RES n,r
RES n,(HL)
BIT n,r
BIT n,(HL)
                Examples follow this lesson


LESSON 22   -   Logical Instructions
                The following instructions are covered:
AND n
AND r
AND (HL)
OR n
OR r
OR (HL)
XOR n
XOR r
XOR (HL)
                Examples follow this lesson


LESSON 23   -   Shift Instructions
                Shift instructions are pictorially
                illustrated in appendix (B).
                The following Instructions are covered:
SRA r           Divides +ve and -ve numbers by 2.
SRA (HL)
SRL r           Divides +ve numbers 0 - 255 by 2.
SRL (HL)
SLA r           Multiplies +ve and -ve numbers by 2.
SLA (HL)
                Examples follow this lesson.


LESSON 24   -   Rotate Instructions
                Rotate instructions are pictorially
                illustrated in appendix (B).
                The following instructions are covered:
RLC r           Rotate r left carry duplicates
RLC (HL)
RLCA            Rotate A left  carry duplicates
RL r            Rotate r and carry left
RL (HL)
RLA             Rotate A and carry left
RRC r           Rotate r right, carry duplicates
RRC (HL)
RRCA            Rotate A right, carry duplicates
RR r            Rotate r and carry right
RR (HL)
RRA             Rotate A and carry right
                Examples follow this lesson


LESSON 25   -   Decimal Rotate
                Decimal rotate instructions are pictorially
                illustrated in appendix (B).
                The following lnstructlons are covered:
RLD             Rotate left decimal (x10)
RRD             Rotate right decimal(/10)
                Examples follow this lesson.


LESSON 26   -   Index Registers.

                The IX or IY registers can replace the
                HL register in all instructions except
                ADC HL,dd SBC HL,dd and EX DE,HL
                The following instructions are covered:
LD r,(IX+d)     LD IX,nn       LD SP,IX
LD (IX+d),r     LD IX,(nn)
LD (IX+d),n     LD (nn),IX     EX (SP),IX
ADD A,(IX+d)    INC (IX,d)     AND (IX+d)
ADC A,(IX+d)	DEC (IX,d)     OR (IX+d)
SUB (IX+d)                     XOR (IX+d)
SBC A,(IX+d)    CP (IX+d)
ADD IX,dd       INC IX         DEC IX
SLA (IX+d)      SRA (IX+d)     SRL (IX+d)
RLC (IX+d)      RL (IX+d)      RRC (IX+d)
RR (IX+d)
SET n,(IX+d)    RES n,(IX+d)   BIT n,(IX+d)
JP (IX)
                Examples follow this lesson.


LESSON 27   -   The Alternative Set Of Registers
                The following instructions are covered:
EX AF,AF'       Exchanges the contents of AF and AF'
EXX             Exchanges BC,DE and HL, with BC',DE'
                and HL' respectively.
                Examples follow this lesson


LESSON 28   -   Input And Output Instructions
                The following lnstructions are covered:
IN A,(N)        Where n is the number of the input
IN r,(C)        port (0-255)
IN F,(n)
OUT (n),A
OUT (C),r
                Examples follow this lesson


LESSON 29   -   Block Instructions


LESSON 30   -   Block Transfer Instructions
                The following instructions are covered:

LDI             Pointer incremented
LDIR            Pointer incremented and repeated
                until number found or BC=0
LDD             Pointer decremented
LDDR            Pointer decremented and repeated
                until number found or BC=0
                Examples follow this lesson


LESSON 31   -   Block Search
                The following instructions are covered:

CPI             Pointer incremented
CPIR            Pointer incremented and repeated until
                number found or BC=0
CPD             Pointer decremented
CPDR            Pointer decremented and repeated until
                number found or BC=0
                Examples follow this lesson


LESSON 32   -   Block Input/Output Instructions
                The block input instructions covered are:
INI             Incrementing
INIR            Incrementing and repeating
IND             Decrementing
INDR            Decrementing and repeating

                The block output instructions covered are:
OUTI            Incrementing
OTIR            Incrementing and repeating
OUTD            Decrementing
OTDR            Decrementing and repeating
                Examples follow this lesson


LESSON 33   -   Processor Control Instructions
                The following instructions are covered:

NOP
HALT
RST n           Where n = 00H 08H 10H 18H 20H 28H 30H or 38H

LD A,R
LD R,A
LD A,I
LD I,A
                Examples of the use of the refresh
                register follow this lesson.


LESSON 34   -   Interrupts
                The following instructions are covered:

EI              Enable interrupts
DI              Disable interrupts
IM0         )
IM1         )   Interrupt modes
IM2         )
RETI            Return from interrupt
RETN            Return from non-maskable interrupt


LESSON 35   -   Finale


GLOSSARY

Assembly language - A language using mnemonics to
represent machine code operations. A low-level
language. An assembly language program can not
itself be run until it is assembled.

BINARY - Two. In binary arithmetic the digits 0
and 1 are used to represent numbers.

BINARY CODED DECIMAL (BCD) - A system where a nibble
represents one decimal number, therefore a byte
can represent two decimal numbers.

BIT - One single binary digit. Either a one or a zero.

BUG - An error or undesirable aspect in a program,
which prevents a program from working correctly or
not at all.

BYTE - A group of binary bits. Usually 8, considered
as one unit.

CHARACTER - An element of a set of symbols, such as
a letter or number, or special symbol.

CHIP - Common name for integrated circuit. Derived
from the small piece of silicon on which the
integrated circuit is chemically formed.

COMPUTER - A machine that accepts data, acts upon it,
and supplies the results of the processing as a result
of certain instructions. A collective noun
describing the processor and I/O devices.

CRASH - Term used to describe the computer 'locking up'
and not accepting any input from the keyboard. The
only solution is to turn the computer off and then on
again.

CURSOR - A flashing thin line used to indicate where
data is expected to be entered on a VDU.

DATA - A piece of information which the computer can
process.

EDITING - The process of changing data before it is
committed to the processor.

EXECUTE - To carry out the instructions in a program.
A microprocessor executes a program by reading and
acting on the instructions.

GRAPHICS - Term describing the display of data in
pictorial form. Pictures on screen are displayed
using pixels.

HARDWARE - Parts of the computer that physically
exist, the computer and a printer for example.

HEXADECIMAL - A number base using 16 different
digits for each number column. The digits 0-9
and A-F are commonly used.

INSTRUCTlON - A certain action to be taken by the
processor. A machine code program is made up of
instructions.

MACHINE CODE - Binary representation of the
instructions of the microprocessor. Machine code
can be acted upon by the microprocessor without any
further translation.

MEMORY - Collection of integrated circuits in which
data is stored. Each binary bit is stored as an
electrical signal within the IC. Memory is
classified as ROM or ram and its size is measured K
(kilobytes).

MICROPROCESSOR - An integrated circuit that contains
all the components to perform the basic data
processlng operations, all in one package. A
microprocessor must be connected to memory and I/0
devices before it can be used.

MNEMONIC - A group of 3-4 characters representing
a machine code instruction. Each mnemonic is
translated by an assembler into a machine code
instruction.

NIBBLE - A group of four bits. There are two nibbles
per byte.

OBJECT PROGRAM - A program in machine code. The source
program, which cannot be executed by the processor,
is assembled by the assembler which generates an object
program. This object program resides in memory, and
can be executed by the processor.

OPERATING SYSTEM - A machine code program, part of the
systems software, which enables the processor to
perform the data processing and control functions.

PAGE - When used in conjunction with memory, means 256
bytes of memory.

PROGRAM - A collection of instructions to make the
microprocessor perform a certain task.

RAM - Random access memory. This kind of memory
may be written to or read from. This kind of memory
is used to store the program that is being developed.
If you turn the computer off, all data contained in
RAM will be lost.

ROM - Read only memory. This kind of memory is set
up at the factory where the computer ls made. It
usually houses the operating system and other
programs necessary each time the computer is turned
on. Turning the computer off and then back on again
has no effect on ROM.

SOFTWARE - A non-physical part of a computer such as
a program.

SOURCE PROGRAM - The program that consists of
mnemonics that can be understood by humans. This
program cannot be executed until it is assembled.


APPENDIX A
                             Effect Of Instructions On Flags
                              Single Register Instructions

Instruction                      Carry   Zero   P/V    Sign
ALL LD...............              +      +      +      +
EXCEPT LD A,I & LD A,R             +      !      !(1)   !
ADD, ADC, SUB, SBC, CP             !      !      v      !
INC, DEC                           +      !      v      !
DAA                                !      !      p      !
NEG                                !      !      p      !
Shift & Rotate specific. on A      !      +      +      +
RLD, RDD                           +      !      p      !
All other shift & rotates on r     !      !      p      !
AND, OR, XOR                       0      !      p      !
BIT                                +      !      ?      ?
SET, RES                           +      +      +      +
CCF                                !      +      +      +
SCF                                1      +      +      +


                             Effect Of Instructions On Flags
                                Register Pair Operations

Instruction                      Carry   Zero   P/V    Sign
All LD instructions                +      +      +      +
All exchange instructions          +      +      +      +
ADD                                !      +      +      +
ADC, SBC                           !      !      v      !
INC, DEC                           +      +      +      +
PUSH, POP                          +      +      +      +


NOTATION:   +  Not affected          v  P/V owerflow
            p  P/V parity            0  Flag reset
            1  Flag set              ?  Flag state unknown
            !  Affected according
               to instruction
			   

                             Effect Of Instructions On Flags
                               Miscellaneous Instructions

Instruction                      Carry   Zero   P/V    Sign
All JP, JR, CALLS, RET & DJNZ      +      +      +      +
LDI, LDD                           +      +      !(2)   +
LDIR, LDDR                         +      +      0      +
CPI, CPIR, CPD, CPDR               +      !(3)   !(2)   !
IN A,(n) OUT(n),A                  +      +      +      +
OUT (C),r                          +      +      +      +
IN R,(C)                           +      !      p      !
INI, IND, OUTI, OUTD               +      !(4)   ?      ?
INIR, INDR, OTIR, OTDR             +      1      ?      ?
NOP, HALT, DI, EI, IM              +      +      +      +

NOTES:	(1)	P/V displays state of interrupt enable flag
        (2)	P/V	= 0 if BC = 0 IF NOT P/V = 1
        (3)	Z =	1 IF A = (HL) IF NOT Z = 0
        (4)	Z =	1 IF B = 0    IF NOT Z = 0


APPENDIX B

                    Shift & Rotate Instructions
                       Pictorial Description

                        �����������������������Ŀ
                 ���Ŀ  � ������������������Ŀ  �
RLC, RLCA        � C <���Ĵ 7              0 <���
                 �����    ��������������������

              ���������������������������������Ŀ
              �  ���Ŀ    ������������������Ŀ  �
RL, RLA       ��Ĵ C <���Ĵ 7              0 <���
                 �����    ��������������������

                       �����������������������Ŀ
                       �  ������������������Ŀ �  ���Ŀ
RRC, RRCA              ���> 7              0 �����> C �
                          ��������������������    �����

                       ���������������������������������Ŀ
                       �  ������������������Ŀ    ���Ŀ  �
RR, RRA                ���> 7              0 �����> C ����
                          ��������������������    �����


                 ���Ŀ    ������������������Ŀ
SLA              � C <���Ĵ 7              0 <��� 0
                 �����    ��������������������


                          ������������������Ŀ    ���Ŀ
SRA                   ����> 7              0 �����> C �
                      �   ��������������������    �����
                      �������

                          ������������������Ŀ    ���Ŀ
SRL                   ����> 7              0 �����> C �
                          ��������������������    �����

                              ���������������������Ŀ
                �����������������Ŀ    �������������\/��Ŀ
RLD           A � 7    4 � 3    0 �    � 7    4 � 3    0 � (HL)
                ��������������^����    ������^������������
                              �������������  ��������

                              �����������Ŀ  ������Ŀ
                �����������������Ŀ    ���\/��������\/��Ŀ
RRD           A � 7    4 � 3    0 �    � 7    4 � 3    0 � (HL)
                ��������������^����    �������������������
                              �����������������������

