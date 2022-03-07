Chapter 1 : The Basics
----------------------

A couple of years ago the computer press speculated on Commodore's expected
domination of the home computer market and the continuing success of the
Amiga. Events in 1994 confirmed both, though no-one could have anticipated
the eccentric mishandling of the CD32 console and the subsequent caution
with which the machine was to be regarded by manufacturers and buyers
alike.

At the back end of 1994 it was still uncertain whether the Amiga - and the
CD32 especially - would sell in quantities hoped for by Commodore, and
which would justify large investment by software houses. They didn't, and
the mighty Commodore was destroyed.

However, it hasn't been all doom and gloom. The advent of high-level
programming languages, such as Blitz Basic 2, is just one sign amongst many
that software development on the Amiga is far from dead.



1.1 Welcome to Blitz Basic
--------------------------

BASIC stands for Beginners All-Purpose Symbolic Instruction Code. It uses
an easily grasped mixture of English, numbers, strings, arithmetic signs
and parameters which will enable you to start programming without having to
learn a daunting low-level language such as Assembly Language. BASIC is a
high-level language which was first devised for education purposes only,
but during recent years it has undergone many improvements and is now
widely used throughout the Amiga world in the form of Blitz Basic 2.

A few years ago Blitz Basic was a breakthrough, the first programming
language that ran anywhere near as fast as Assembly Language (with the
obvious exception of the C language). It was developed to run solely on the
Amiga - an A500 at the time - and some of the peculiarities of that machine
have been enshrined in the language ever since.

There were a number of pretenders to Blitz Basic's crown, including AMOS,
GFA Basic and HiSoft Basic, but it built up a large following and went
through several versions and revisions - like the Amiga, but more slowly.
Blitz Basic 2 is currently up to version 1.9, the version covered in this
guide, although the information contained herein is relevant in part to all
versions of Blitz.

In its relatively short lifetime, Blitz Basic has established itself as the
most powerful BASIC dialect on the Amiga. It is certainly a highly
satisfactory package for the budding Amiga programmer - this is indicated
by the abundance of Blitz-created software in the Public Domain.

Blitz Basic is immensely powerful but does not welcome the novice. That is
not because the program is badly implemented - far from it - but because
the documentation that accompanies the software is poor and
over-complicated. Together with Blitz Basic, this guide will help you
unlock the power of your Amiga! Here goes...



1.2 Using this guide
--------------------

The following chapters provide a thorough and comprehensive index of all
the Blitz Basic tokens, as well as a valuable amount of reference material
for using Blitz Basic 2.

The commands are arranged in relevant chapters and each description follows
an identical format, for ease of reference. After the command name the
operating modes are given and they are followed by a brief explanation of
the command and the command syntax. For example:


**PRINT**
```
Mode(s):   Amiga/Blitz
Statement: print items on screen
Syntax:    Print EXPRESSION
```

This is followed by a fuller explanation and, where appropriate, an example
of the command's use.


The following conventions are used in the syntax descriptions:

* Command parameters are in capitals

* Square brackets indicate optional parameters []

* Three dots indicate that more parameters of the same format may be added
  as necessary (...)


If you are already familiar with the Blitz Basic 2 instruction set, be sure
to read through the chapters for any information that you may not know. You
may be pleasantly surprised!



1.3 Basic programming concepts
------------------------------

The Blitz Basic 2 instruction set consists of a number of reserved keywords
which perform a specific task. It includes the names of all Blitz Basic
statements, functions, commands and operators. Examples include PRINT,
EDIT$, WAITEVENT and .

Reserved words can be entered in either uppercase or lowercase, and Blitz
Basic will automatically highlight and format the keyword. You should
always separate Blitz reserved keywords from parameters, data, or other
elements of a command with spaces. This lowers the risk of Blitz Basic not
recognising a token name.


1.3.1 Functions, statements & commands
--------------------------------------

The Blitz Basic 2 instruction set comes in three different flavours:
functions, statements and commands.

Functions are Blitz Basic tokens that require parameters in parentheses,
and return a value:
```
; *** Functions example
; *** Filename - Functions.bb2

N=Abs(-10)
MouseWait
End
```

Statements are Blitz Basic tokens that only perform an action but do not
return a value. Their arguments do not require parentheses:
```
; *** Statements example
; *** Filename - Statements.bb2

NPrint "Blitz Basic 2"
MouseWait
End
```

Commands are Blitz Basic tokens that can be used as either a function or a
statement:
```
; *** Commands example
; *** Filename - Commands.bb2

ev.l=WaitEvent ; *** As a function
Waitevent      ; *** As a statement
MouseWait
End
```


1.4 Amiga Vs Blitz
------------------

Blitz Basic runs under two modes, namely Amiga mode and Blitz mode, and
some of its commands are limited in the mode under which they can run.
Although the Amiga's Operating System is very powerful, it often gets in
the way of games programmers and slows the machine down. Blitz mode chucks
the Operating System out of the window, so that Blitz Basic can talk
directly to the Amiga's hardware. Blitz mode programs run extremely fast,
and smooth scrolling and dual playfield displays can be created.

However, all Blitz reserved keywords are restricted in that they can
operate under Amiga mode, OR Blitz mode, OR both (the operating modes for
all reserved keywords are given in this guide).

The following commands (commonly known as directives) are used to
temporarily alter the Blitz Basic operating mode.


**AMIGA**
```
Mode(s):   Amiga/Blitz
Directive: enter Amiga mode
Syntax:    AMIGA
```
The AMIGA directive is used to enter Amiga mode and to return to the
Intuition environment. This is the default Blitz Basic operating mode:
```
; *** AMIGA example
; *** Filename - AMIGA.bb2

; *** Enter Blitz mode
BLITZ
; *** Create Blitz mode display
BitMap 0,320,256,3
BitMapOutput 0
Slice 0,44,3
Show 0
; *** Output some text
NPrint "Blitz mode"
VWait 100
; *** Enter Amiga mode
AMIGA
; *** Output some more text
DefaultOutput
NPrint "Amiga mode"
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**BLITZ**
```
Mode(s):   Amiga/Blitz
Directive: enter Blitz mode
Syntax:    BLITZ
```
The BLITZ directive is used to enter Blitz mode. Any further commands which
require the presence of the Operating System (such as the File access,
Window and Gadget commands) will become temporarily unavailable. File
access especially should not occur directly before you enter Blitz mode. To
ensure that this is the case, after file access insert the following line
before executing the BLITZ directive:
```
VWait 100
```
Blitz mode is not a permanent state. Once your program has finished
executing, Blitz Basic returns to Amiga mode. For example:
```
; *** BLITZ example
; *** Filename - BLITZ.bb2

; *** Enter Blitz mode
BLITZ
; *** Create Blitz mode display
BitMap 0,320,256,3
Slice 0,44,3
Show 0
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**QAMIGA**
```
Mode(s):   Amiga/Blitz
Directive: enter Quick Amiga mode
Syntax:    QAMIGA
```
The QAMIGA directive is used to enter Quick Amiga mode. Quick Amiga mode is
similar to Amiga mode, however the current display is unaffected (i.e. you
are not returned to the Intuition environment). This allows you to jump
into Amiga mode without having to corrupt a Blitz mode display. Here's an
example:
```
; *** QAMIGA example
; *** Filename - QAMIGA.bb2

; *** Enter Blitz mode
BLITZ
; *** Create Blitz mode display
BitMap 0,320,256,3
BitMapOutput 0
Slice 0,44,3
Show 0
; *** Output some text
NPrint "Blitz mode"
VWait 100
; *** Enter Quick Amiga mode
QAMIGA
; *** Output some more text
NPrint "QAmiga mode (same display)"
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.5 Label Definitions
---------------------

Alphanumeric labels can consist of letters, special characters, or numbers.
However, they must begin with an alphabetical character. This allows the
use of mnemonic labels to make your program code easier to understand.

For example, the following labels are valid:
```
Bob:
BOB:
A100:
_Print:
```

However, the following label names are not allowed:
```
1:      ; *** begins with a number, not a letter
101:    ; *** begins with a number, not a letter
Print:  ; *** Blitz Basic reserved keyword
```

Capital label names are treated differently to lowercase label names. For
example, Bob: and BOB: are recognised as two different labels by Blitz
Basic.


1.5.1 Restrictions
------------------

Alphanumeric labels are distinguished from variables by a terminating colon
\(\:\) \- a legal label cannot have a space between the name and the colon.
When you refer to a label in a GOSUB or GOTO or other control structure, do
not include the colon as part of the label name.

You cannot use any Blitz Basic reserved keyword as an alphanumeric label,
as Blitz Basic will generate an error.



1.6 Variables
-------------

Variables represent values that are used in a program. In Blitz Basic there
are two types of variable: numeric and string. A numeric variable can only
be assigned a value that is a number:
```
; *** Variables example 1
; *** Filename - Variable1.bb2

; *** Define numeric variable
A=1
; *** Output contents of variable
NPrint A
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

A string variable can only be assigned a character string value:
```
; *** Variables example 2
; *** Filename - Variable2.bb2

; *** Define string variable
A$="Blitz Basic"
; *** Output contents of variable
NPrint A$
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

You can assign a value to a variable, or it can be assigned as the result
of calculations in the program - this is known as an expression. Before a
variable is assigned a value, its value is zero (numeric variables) or null
(string variables).

While a variable name cannot be a reserved keyword, a reserved keyword
embedded in a variable name is allowed:
```
; *** Variables example 3
; *** Filename - Variable3.bb2

; *** Define numeric variable
APrint=10
; *** Output contents of variable
NPrint APrint
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

**LET**
```
Mode(s):   Amiga/Blitz
Statement: assign a value to a variable
Syntax:    Let VARIABLE=EXPRESSION
```
LET is an optional statement which is used to assign a value to a variable.
For example:
```
; *** Let example
; *** Filename - Let1.bb2

; *** Define numeric variable
Let A=1
; *** Output contents of variable
NPrint A
; *** Define numeric variable
A=1
; *** Output contents of variable
NPrint A
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

Here are some more examples of LET:
```
; *** Two Let
; *** Filename - Let2.bb2

Let A=180   ; *** Load variable A with 180
Let A=B*10  ; *** Load ten lots of variable B into A
Let B+1     ; *** Increase B by 1
Let B-1     ; *** Decrease B by 1
Let C*10    ; *** Multiply C by 10
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**EXCHANGE**
```
Mode(s):   Amiga/Blitz
Statement: swap the contents of two variables
Syntax:    Exchange A,B
```
This useful little statement swaps the contents of two variables of the
same type (i.e. A is assigned the value of B and B, the value of A). For
example:
```
; *** Exchange example
; *** Filename - Exchange.bb2

NUM=10
; *** Dimension an array
Dim RANDOM(NUM)
; *** Generate NUM (default is 10) numbers
For A=1 To NUM
  RANDOM(A)=A
Next A
Repeat
  Repeat
    ; *** Generate some random numbers
    B=Rnd(NUM)+1
  Until B0
  ; *** Swap variables
  Exchange RANDOM(B),RANDOM(NUM)
  Let C+1
Until C=NUM
; *** Output random numbers
For T=1 To NUM
  NPrint RANDOM(T)
Next T
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.7 Numeric types
-----------------

Blitz Basic currently supports six different types of variable: five
numeric types with different ranges and accuracies for numeric data, and
one string type ($) for character strings (we'll take a look at the string
type later on).


Table 1.1 : Numeric types

```
Type  Suffix Range          Accuracy Bytes Example
==========================================================
Byte  .b     +/- 128        Integer  1     Neil.b=125
Word  .w     +/- 32768      Integer  2     Dan.w=30000
Long  .l     +/- 2147483648 Integer  4     Jon.l=$dff000
Quick .q     +/- 32768.0000 1/65536  2     Richard.q=500/7
Float .f     +/- 9e18       1/10e18  4     Craig.f=4e7
```

To assign a type to a variable simply add the relevant suffix from the
above table to the variable name:
```
; *** Blitz Basic types
; *** Filename - Types.bb2

; *** Define numeric variables
BYTE.b=126
WORD.w=32767
LONG.l=3200000
QUICK.q=3.1415
FLOAT.f=3e8
; *** Output numeric variables
NPrint BYTE
NPrint WORD
NPrint LONG
NPrint QUICK
NPrint FLOAT
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```
If no suffix is used in the first reference of a variable then Blitz Basic
will assign that variable with the default type. The default type is quick,
however the DEFTYPE statement can be used to change this.



**DEFTYPE**
```
Mode(s):   Amiga/Blitz
Statement: declare a list of variables as a particular type
Syntax:    DEFTYPE.TYPE [VARIABLE[,VARIABLE2,...]
```
The DEFTYPE statement has two main uses. It can change the default type and
it can also be used to declare a list of variables as being of a particular
type (the default type is not affected). In this case, the optional
VARIABLE parameters must be included. Here is an example:
```
; *** DEFTYPE example
; *** Filename - DEFTYPE.bb2

A=Pi
; *** A is a quick
NPrint A
; *** Set default type to word
DEFTYPE.w
NPrint Pi
; *** Declare variables A and B as quicks
DEFTYPE.q A,B
A=Pi
B=Sqr(Pi)
NPrint A
NPrint B
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**SIZEOF**
```
Mode(s):  Amiga/Blitz
Function: return amount of memory a variable takes up
Syntax:   s=SizeOf.TYPE[,PATH]
```
This function returns the amount of memory, in bytes, that a variable type
takes up. If the optional PATH parameter is included then the offset from
the start of the type, to the specified entry, is returned. For example:
```
; *** SizeOf example
; *** Filename - SizeOf.bb2

; *** NewType definition
NEWTYPE.NAME
  A.l
  B.w
  C.q
End NEWTYPE
; *** Return size of NewType
NPrint SizeOf.NAME
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

1.7.1 Manipulating quick numbers
--------------------------------

As has been explained, the quick type is a fixed point type, with an
accuracy of four decimal places. Quick numbers can be manipulated with the
following functions.


**QLIMIT**
```
Mode(s):  Amiga/Blitz
Function: limit the range of a quick number
Syntax:   QLimit(QUICK,LOW,HIGH)
```
Use the QLIMIT function to limit the range of a quick number. If QUICK is
greater than or equal to LOW, and less or equal to HIGH, then the value of
QUICK is returned. If QUICK is less than LOW then LOW is returned.
Conversely, if QUICK is greater than HIGH then HIGH is returned. For
example:
```
; *** QLimit example
; *** Filename - QLimit.bb2

NPrint QLimit(100,0,90) ; *** Returns 90
NPrint QLimit(90,95,100) ; *** Returns 95
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**QWRAP**
```
Mode(s):  Amiga/Blitz
Function: wrap the result of a quick expression
Syntax:   QWrap(QUICK,LOW,HIGH)
```
QWRAP wraps the result of the quick expression if QUICK is greater than or
equal to HIGH, or less than LOW. If QUICK is less than LOW then
QUICK-LOW+HIGH is returned. If QUICK is greater than or equal to HIGH then
QUICK-HIGH+LOW is returned. Here are some examples:
```
; *** QWrap example
; *** Filename - QWrap.bb2

NPrint QWrap(-10,0,320) ; *** Returns 310
NPrint QWrap(100,0,90) ; *** Returns 10
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.8 NewTypes
------------

In addition to the six primitive types available, programmers can also
create their own custom types, or NewTypes. A NewType is a collection of
fields, similar to a database or C structure, which enables you to group
together relevant fields in one variable type.


**NEWTYPE**
```
Mode(s):   Amiga/Blitz
Statement: begin a NewType definition
Syntax:    NEWTYPE .NAME
```


**END NEWTYPE**
```
Mode(s):   Amiga/Blitz
Statement: end a NewType definition
Syntax:    End NEWTYPE
```
NEWTYPE must be followed by a list of fields, separated by colons and/or
newlines:
```
NEWTYPE .NAME
  X.w
  Y.w
  SPEED.w
End NEWTYPE
```
Once a NewType is defined, variables are assigned the new type by using a
suffix of .NAME:
```
A.NAME
```
Which would assign the contents of the "NAME" NewType to the "A" variable.


1.8.1 NewType fields
--------------------

When defining a NewType structure, field names without a suffix will be
assigned the type of the previous field:
```
NEWTYPE .NAME
  X.l
  Y
  SPEED
End NEWTYPE
```
In the above example the X field is assigned the long type, so the Y and
SPEED fields are assigned the same type.

Individual fields within a NewType variable are accessed and assigned using
the "\" character:
```
NEWTYPE .NAME
  X.w
  Y.w
  SPEED.w
End NEWTYPE
A.NAME\X=10
NPrint A\X
MouseWait
End
```
Which would assign the value 10 to the X field.

To assign values to all of the fields at once, separate the values with
commas:
```
NEWTYPE .NAME
  X.w
  Y.w
  SPEED.w
End NEWTYPE
A.NAME\X=10,20,30
NPrint A\X
```
Which would assign the values 10, 20 and 30 to the X, Y and SPEED fields
respectively.


1.8.2 Restrictions
------------------

References to string fields do not require the $ or .s suffix to be
present. The following example will generate an error:
```
NEWTYPE .NAME
  NAME$
  AGE.q
End NEWTYPE
A.NAME\NAME$="Neil Wright"
NPrint A\NAME$
MouseWait
End
```

This is the correct procedure:
```
NEWTYPE .NAME
  NAME$
  AGE.q
End NEWTYPE
A.NAME\NAME="Neil Wright"
NPrint A\NAME
MouseWait
End
```

1.8.3 NewType in action
-----------------------

Once you have gained an understanding of how NewTypes are created, the next
step is to see how they are used within a Blitz Basic program. Here is full
example:
```
; *** NEWTYPE example
; *** Filename - NEWTYPE.bb2

; *** Create NewType with three fields
NEWTYPE.NAME
  A.l
  B.w
  C.q
End NEWTYPE
; *** Assign three values to the three fields
A.NAME\A=10,20,30
; *** Output the contents of the fields
NPrint A\A
NPrint A\B
NPrint A\C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.9 Constants
-------------

A constant is a values which is defined by the programmer, but does not
change during program execution. Constants are faster than variables and do
not consume any memory. However, the following must be obeyed when using
constants:

* Constants can only hold integer values

* Constants can be used in assembler

* Constants can be used in conditional compiling evaluation

A constant is defined by adding the hash symbol (#) before a variable name.
For example, #X=100 means that the #X variable is a constant, and will
always be equal to 100. This allows the Blitz programmer to replace
meaningless numbers with mnemonic constants:
```
; *** Constants example
; *** Filename - Constants.bb2

; *** Define constants
#WIDTH=320
#HEIGHT=256
#DEPTH=3

; *** Create Blitz mode display using constants
BLITZ
BitMap 0,#WIDTH,#HEIGHT,#DEPTH
Slice 0,44,#DEPTH
Show 0
BitMapOutput 0
; *** Output contants
NPrint "Width = ",#WIDTH
NPrint "Height = ",#HEIGHT
NPrint "Depth = ",#DEPTH
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.10 Strings
------------

A string variable is one which contains text, rather than numbers. Strings
are surrounded by quotation marks and all string names must end with the
dollar ($) character. They can comprise of characters, numbers or spaces.
The example below creates a new string \(A\$) and stuffs it with the contents
of the subsequent quote marks:
```
; *** Strings example
; *** Filename - Strings1.bb2

; *** Define a numeric variable
A$="Blitz BASIC 2"
; *** Output variable
Print A$
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**MAXLEN**
```
Mode(s):   Amiga/Blitz
Statement: define maximum length of string variable
Syntax:    MaxLen "STRING"=EXPRESSION
```
The MAXLEN statement is used to define the maximum length of a string
variable. EXPRESSION specifies the maximum number of characters for the
string. This is only necessary when using the Blitz Basic commands which
require this definition (FILEREQUEST$ and FIELDS). Try the following
example:
```
; *** MaxLen example
; *** Filename - MaxLen.bb2

; *** Open a hi-res screen
Screen 0,3+8
; *** Set maximum length of variables
MaxLen PATH$=160
MaxLen FILENAME$=64
; *** Create a file requester
F$=FileRequest$("File requester",PATH$,FILENAME$)
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

Blitz Basic's string functions are extremely powerful, which is why we have
devoted the whole of Chapter 2 to them.



1.11 Blitz Basic operators
--------------------------

Operators perform mathematical or logical operations on values. When
several operators are used within the same program statement, they are
processed in a specific order. This order is dependent on the operator
list, or hierarchy. The operators found at the top of this list are
processed first. If the operators are of the same level, the leftmost one
is executed first, the rightmost last:


Table 1.2 : Blitz Basic operators

```
Operator Description                    Example
==================================================
NOT      Logical NOT                    NOT A
BITSET   A with B bit set               A BitSet B
BITCLR   A with B bit cleared           A BitClr B
BITCHG   A with B bit changed           A BitChg B
BITTST   True if A bit of B set         A BitTst B
^        Exponentiation                 A^B
LSL      A left B times (logical)       A LSL B
ASL      A left B times (arithmetical)  A ASL B
LSR      A right B times (logical)      A LSR B
ASR      A right B times (arithmetical) A ASR B
&        Logical AND                    A&B
|        Logical OR                     A|B
*        Multiply                       A*B
/        Divide                         A/B
+        Add                            A+B
-        Subtract                       A-B
=        Equal                          A=1
<>       Unequal                        AB
<=       Less than                      AB
>=       Greater than                   AB
=        Less than or equal to          A=B
=        Greater than or equal to       A=B
AND      Logical AND                    A AND B
OR       Logical OR                     A OR B
```

1.11.1 Relational operators
---------------------------

Relational operators are used to compare two values. The result of the
comparison is either true (-1) or false (0). This result can then be used
to make a decision regarding program execution. The following table lists
the relational operators:


Table 1.3 : Relational operators

```
Operator Description               Example
==========================================
=        Equal                     A=1
<>       Unequal                   AB
<        Less than                 AB
>        Greater than              AB
=        Less than or equal to     A=B
=        Greater than or equal to  A=B
```

The "=" operator compares two numerical or character string expressions.
When both are equal the logical true is returned, otherwise logical false
will be returned:
```
; *** = operator
; *** Filename - =.bb2

A=3
B=3
If A=B Then End
Repeat
Forever
```

The "", "", "=" and "=" operators serve to compare numerical and string
expressions:

* AB is true when A is greater than B
* AB is true when A is less than B
* A=B is true then A is less than or equal to B
* A=B is true when A is greater than or equal to B


The "" operator determines if two numerical or string expressions are
unequal:

* A<>B is true when A is unequal to B


When arithmetic and relational operators are combined in one expression,
the arithmetic operation is always performed first.


1.11.2 Logical operators
------------------------

Logical operators perform bit manipulation, Boolean operations, or tests on
multiple relations. Like relational operators, logical operators can be
used to make decisions regarding program execution.

A logical operator returns the result from the combination of true-false
operands. The result (in bits) is either true (-1) or false (0).

The Blitz Basic logical operators are NOT (logical complement), AND
(conjunction) and OR (disjunction).

For example:
```
; *** Logical operators
; *** Filename - Logic.bb2

NPrint NOT 3     ; *** returns -4
NPrint NOT -4    ; *** returns 3
NPrint 50 AND 40 ; *** returns 32
NPrint 12 AND 11 ; *** returns 8
NPrint 2 OR 1    ; *** returns 3
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.12 Using operators with strings
---------------------------------

A string expression consists of string constants, string variables, and
other string expressions combined by operators. There are two types of
string operation: concatenation and relation.


1.12.1 Concatenation
--------------------

Combining two strings together is called concatenation. The plus (+)
operator is used to perform concatenation. Here is an example of the use of
the operator:
```
; *** A piece of string
; *** Filename - Strings2.bb2

; *** Define string variables
A$="Blitz "
B$="Basic "
C$="is tops!"
; *** Concatenate strings
Print A$+B$+C$
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```
In the above example the "+" operator is used join together two strings.
Running the example produces the following on the screen:
```
Blitz Basic is tops!
```
Note that the other arithmetic operators (i.e. -, /, *) should not be
applied to strings.


1.12.2 Relational operators
---------------------------

Strings can also be compared using the same relational operators that are
used with numeric variables (i.e. =, , , , = and =).

With strings, the relational operators compare the ASCII codes of the
characters which comprise the string. The ASCII code system assigns a
different number to each keyboard character. If all the ASCII codes are the
same, the strings are equal. If the ASCII codes differ, the lower code
number precedes the higher.

All string constants used in comparison expressions must be enclosed in
quotation marks.

Here is an example:
```
; *** Relational operators
; *** Filename - Relation.bb2

; *** Define string variables
A$="A"
B$="B"
C$="Blitz"
D$="Basic"
; *** Evaluate variables
If A$B$ Then NPrint A$,"",B$
If B$A$ Then NPrint B$,"",A$
If C$D$ Then NPrint C$,"",D$
If C$=C$ Then NPrint C$,"=",C$
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


1.13 Arrays
-----------

An array is a list of variables of the same name that are distinguished by
subscripts (values that identify each variable or element in the array).
Arrays can be made up from any type of variable. Creation of such an array
is accomplished by the DIM statement.


**DIM**
```
Mode(s):   Amiga/Blitz
Statement: dimension an array
Syntax:    Dim ARRAY_NAME(DIMENSION LIST)
Syntax 2:  Dim List ARRAY_NAME(DIMENSION LIST)
```
The DIM statement is used to dimension (set up) an array of a given number
of numeric or string variables. In numeric arrays, DIM is followed by a
single letter or word that names the array, and one or more numeric values
(dimensions) separated by commas. String arrays are created in the same
way, however a single letter or word followed by a ($) is used for the
array name. Here is an example:
```
; *** Dim example
; *** Filename - Dim.bb2

; *** Dimension array
Dim A(20)
; *** Define array contents
For B=1 To 20
  A(B)=Int(Rnd(100))
Next B
; *** Print array contents
For C=1 To 20
  NPrint A(C)
Next C
; *** Wait for mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```

1.13.1 List arrays
------------------

The optional List parameter, if included, denotes a List array. List arrays
differ from normal arrays in that Blitz Basic keeps an internal count of
how many elements are stored in the List and an internal pointer to the
current element within the List. List arrays are restricted in size to one
dimension:
```
; *** Dim example 2
; *** Filename - Dim2.bb2

; *** Dimension List array
Dim List A(20)
; *** Define array contents
For B=1 To 20
  A(B)=Int(Rnd(100))
Next B
; *** Output List array contents
For C=1 To 20
  NPrint A(C)
Next C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**RESETLIST**
```
Mode(s):   Amiga/Blitz
Statement: reset List array to first item
Syntax:    ResetList ARRAY()
```
RESETLIST is used to set the current List array element to the first item.
This prepares the array for processing with the NEXTITEM statement. For
example:
```
; *** ResetList example
; *** Filename - ResetList.bb2

; *** Dimension List array
Dim List A(10)
; *** Process List array
While AddFirst(A())
  A()=B
  Let B+1
Wend
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**CLEARLIST**
```
Mode(s):   Amiga/Blitz
Statement: clear a List array
Syntax:    ClearList ARRAY()
```
The CLEARLIST statement clears a List array. List arrays are automatically
cleared when they are dimensioned. Here is an example:
```
; *** ClearList example
; *** Filename - ClearList.bb2

; *** Dimension List array
Dim List A(10)
; *** Process List array
While AddFirst(A())
  A()=B
  Let B+1
Wend
ClearList A()
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**ADDFIRST**
```
Mode(s):  Amiga/Blitz
Function: insert array item at the beginning of an array List
Syntax:   a=AddFirst [ARRAY()]
```
This function enables you to insert an array item at the beginning of a
List array. ADDFIRST returns (-1) if there is enough room in the array to
add an element, and (0) if no array element is available. Example:
```
; *** AddFirst example
; *** Filename - AddFirst.bb2

; *** Dimension List array
Dim List A(100)
; *** Process List array
While AddFirst(A())
  A()=B
  Let B+1
Wend
NPrint B," items added"
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**ADDLAST**
```
Mode(s):  Amiga/Blitz
Function: insert array item at the end of an array List
Syntax:   a=AddLast [ARRAY()]
```
The ADDLAST function enables you to insert an array item at the end of a
List array. It returns (-1) if there is enough room in the array to add an
element, and (0) if no array element is available. For example:
```
; *** AddLast example
; *** Filename - AddLast.bb2

; *** Dimension List array
Dim List A(100)
; *** Process List array
While AddLast(A())
  A()=B
  Let B+1
Wend
; *** Output List array contents
For C=1 To 100
  NPrint A(C)
Next C
NPrint B," items added"
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**ADDITEM**
```
Mode(s):  Amiga/Blitz
Function: insert array item after current item in array List
Syntax:   a=AddItem [ARRAY()]
```
ADDITEM enables you to insert an array item after a List array's current
item. The function returns (-1) and sets the array's "current item" pointer
to the item added if there is enough room to add an element, and (0) if no
array element is available. For example:
```
; *** AddItem example
; *** Filename - AddItem.bb2

; *** Dimension List array
Dim List A(2)
; *** Process List array
If AddFirst(A()) Then A()=1
If AddItem(A()) Then A()=2
If AddItem(A()) Then A()=3
NPrint "List array is:-"
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**KILLITEM**
```
Mode(s):   Amiga/Blitz
Statement: remove current item from array List
Syntax:    k=KillItem ARRAY()
```
The KILLITEM statement is used to delete the current item from a List
array. The "current item" pointer is then set to the item before the
deleted element. Here is an example:
```
; *** KillItem example
; *** Filename -KillItem.bb2

; *** Dimension List array
Dim List A(30)
; *** Process List array
While AddItem(A())
  A()=B
  Let B+1
Wend
ResetList A()
While NextItem(A())
  If A()/2Int(A()/2)
    KillItem A()
  EndIf
Wend
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**PREVITEM**
```
Mode(s):  Amiga/Blitz
Function: set pointer to previous item
Syntax:   p=PrevItem [ARRAY()]
```
This function sets the List array's "current item" pointer to the previous
item, allowing for backward processing of a List array. PREVITEM returns
(-1) if a previous item is available, and (0) if one is unavailable. Try
the following example:
```
; *** PrevItem example
; *** Filename - PrevItem.bb2

; *** Dimension List array
Dim List A(25)
; *** Process List array
While AddLast(A())
  A()=B
  Let B+1
Wend
If LastItem(A())
  ; *** Output List array contents
  Repeat
    NPrint A()
  Until NOT PrevItem(A())
EndIf
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**NEXTITEM**
```
Mode(s):  Amiga/Blitz
Function: set pointer to next item
Syntax:   n=NextItem [ARRAY()]
```
The NEXTITEM function sets the List array's "current item" pointer to the
next item, allowing for forward processing of a List array. It returns (-1)
if the next item is available, and (0) if one is unavailable. Example:
```
; *** NextItem example
; *** Filename - NextItem.bb2

; *** Dimension List array
Dim List A(25)
; *** Process List array
While AddLast(A())
  A()=B
  Let B+1
Wend
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**FIRSTITEM**
```
Mode(s):  Amiga/Blitz
Function: set pointer to first item
Syntax:   f=FirstItem [ARRAY()]
```
FIRSTITEM sets the "current item" pointer in a List array to the first item
in the array. The function returns (-1) if there is a first item available,
and (0) if there are no items in the List array. For example:
```
; *** FirstItem example
; *** Filename - FirstItem.bb2

; *** Dimension List array
Dim List A(25)
; *** Process List array
While AddFirst(A())
  A()=B
  Let B+1
Wend
If FirstItem(A())
  NPrint "First item = ",A()
EndIf
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**LASTITEM**
```
Mode(s):  Amiga/Blitz
Function: set pointer to last item
Syntax:   l=LastItem [ARRAY()]
```
LASTITEM sets the "current item" pointer in a List array to the last item
in the array. The function returns (-1) if there is a last item available,
and (0) if there are no items in the List array. For example:
```
; *** LastItem example
; *** Filename - LastItem.bb2

; *** Dimension List array
Dim List A(25)
; *** Process List array
While AddFirst(A())
  A()=B
  Let B+1
Wend
If LastItem(A())
  NPrint "Last item = ",A()
EndIf
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**PUSHITEM**
```
Mode(s):   Amiga/Blitz
Statement: push pointer to internal stack
Syntax:    PushItem ARRAY()
```
The PUSHITEM statement "pushes" a List array's "current item" pointer onto
an internal stack. This pointer can be recalled at a later date by POPITEM.
The internal item pointer stack can be pushed 8 times.



**POPITEM**
```
Mode(s):   Amiga/Blitz
Statement: get pointer from internal stack
Syntax:    PopItem ARRAY()
```
POPITEM retrieves a pushed "current item" pointer from the internal stack.
The ARRAY() parameter must be the name of the most recently pushed List
array. Here's an example:
```
; *** PushItem/PopItem example
; *** Filename - PopItem.bb2

; *** Dimension List array
Dim List A(10)
; *** Process List array
While AddLast(A())
  A()=B
  Let B+1
Wend
ResetList A()
While NextItem(A())
  If A()=5 Then PushItem A()
Wend
PopItem A()
KillItem A()
ResetList A()
; *** Output List array contents
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**ITEMSTACKSIZE**
```
Mode(s):   Amiga/Blitz
Statement: set push stack size
Syntax:    ItemStackSize MAXIMUM
```
This statement defines the maximum number of List array items that may be
pushed.


1.13.2 Sorting arrays
---------------------

If you were creating a database-type application, or a program that
required the contents of an array to be in order, then it would be very
time consuming to manually sort through the array. Blitz Basic provides
four statements which can be used to automatically order an array.


**SORT**
```
Mode(s):   Amiga/Blitz
Statement: sort a specified array in ascending order (default)
Syntax:    Sort ARRAY()
```
The SORT statement sorts the specified array in ascending order. The
direction of the sort may be changed using the SORTUP and SORTDOWN
statements (default is ascending). Note that NewType arrays and List arrays
cannot be sorted with this statement. Here is a full example:
```
; *** Sort example
; *** Filename - Sort.bb2

; *** Dimension an array
Dim A(10)
; *** Create an array of random numbers
For B=1 To 10
  A(B)=Int(Rnd(100))
  NPrint A(B)
Next B
NPrint ""
; *** Sort the array in ascending order
Sort A()
; *** Output array
For C=1 To 10
  NPrint A(C)
Next C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**SORTUP**
```
Mode(s):   Amiga/Blitz
Statement: force the SORT command to sort into ascending order
Syntax:    SortUp
```
Example:
```
; *** SortUp example
; *** Filename - SortUp.bb2

; *** Dimension an array
Dim A(10)
; *** Create an array of random numbers
For B=1 To 10
  A(B)=Int(Rnd(100))
Next B
; *** Sort array in ascending order
SortUp
Sort A()
; *** Output new array
For C=1 To 10
  NPrint A(C)
Next C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**SORTDOWN**
```
Mode(s):   Amiga/Blitz
Statement: force the SORT command to sort into descending order
Syntax:    SortDown
```
Example:
```
; *** SortDown example
; *** Filename - SortDown.bb2

; *** Dimension an array
Dim A(10)
; *** Create an array of random numbers
For B=1 To 10
  A(B)=Int(Rnd(100))
Next B
; *** Sort array in descending order
SortDown
Sort A()
; *** Output new array
For C=1 To 10
  NPrint A(C)
Next C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**SORTLIST**
```
Mode(s):   Amiga/Blitz
Statement: rearrange the elements in a linked list
Syntax:    SortList ARRAY()
```
The SORTLIST statement is used to rearrange the order of elements in a
Blitz Basic linked list. The order in which the items are sorted depends on
the first field of the linked list type, which must be a single integer
word:
```
; *** SortList example
; *** Filename - SortList.bb2

; *** Dimension a List array
Dim List A(10)
; *** Create a List array of random numbers
While AddLast(A())
  A()=Int(Rnd(100))
  Let B+1
Wend
ResetList A()
; *** Sort List array
SortList A(),0
; *** Output new array
While NextItem(A())
  NPrint A()
Wend
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End

```

1.14 Program control
--------------------

The following statements are used to control Blitz Basic program execution.


**END**
```
Mode(s):   Amiga/Blitz
Statement: end the current program
Syntax:    End
```
This statement serves to end the current program. Program execution may not
be continued. For example:
```
; *** End example
; *** Filename - End.bb2

NPrint "Press left mouse button to return to editor"
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End
```


**STOP**
```
Mode(s):   Amiga/Blitz
Statement: interrupt the current program
Syntax:    Stop
```
The STOP statement interrupts the current program. Program execution may be
resumed using the CONT statement:
```
; *** Stop example
; *** Filename - Stop.bb2

A=Int(Rnd(5))
NPrint "Press left mouse button to stop"
; *** Wait for a mouse click
MouseWait
; *** Stop program in its tracks
Stop
```


**CONT**
```
Mode(s):   Amiga/Blitz
Statement: continue current program
Syntax:    Cont [N]
```
This statement is only available in direct mode. CONT resumes program
execution from the instruction following the STOP statement. The optional N
parameter can be used to ignore a specified number of STOP statements after
a CONT.



1.15 Using data
---------------

What is Data? Well, 99% of all programs ever written operate on and use
data of one kind or another. Information and data are really one and the
same; we enter information into a computer and get out a different type of
information at the end of processing. So when the information is inside the
computer, we refer to it as data. Large amounts of this data can be stored
in your Blitz programs with the DATA statement.


**DATA**
```
Mode(s):   Amiga/Blitz
Statement: define data items in a program
Syntax:    Data LIST
Syntax 2:  Data .TYPE LIST
```


**READ**
```
Mode(s):   Amiga/Blitz
Statement: read data into a variable
Syntax:    Read LIST
```


**RESTORE**
```
Mode(s):   Amiga/Blitz
Statement: set the current READ pointer
Syntax:    Restore PROGRAM_LABEL
```
The DATA statement allows you to store constant values in your programs. A
data pointer is associated with the commands DATA and READ. This pointer
always points to the next DATA item to be read with the READ statement and
is set initially to the first DATA item. The data pointer can be set at a
specific DATA line with the RESTORE statement. For this purpose, a label
must be set in front of the DATA line and the data pointer set with RESTORE
PROGRAM_LABEL. If no label follows the RESTORE statement the data pointer
will be set to the very first DATA item in the program. Here is an example:
```
; *** Using Data
; *** Filename - Data.bb2

; *** Dimension a string array
Dim A$(5)
; *** Return location of program data
Restore MY_DATA
; *** Read data elements into string array
For A=1 To 5
  Read A$(A)
  NPrint A$(A)
Next A
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End

; *** Program data
MY_DATA:
Data$ "Blitz","Basic","Is","Truly","Remarkable"

When data is being read into a variable, the .TYPE of the data being read
must match the type of the variable it is being read into:
```

Table 1.4 : Data types

```
Data                    Data Type  Example
========================================================
Byte                    Data.b     Data.b=125
Word                    Data.w     Data.w=30000
Long                    Data.l     Data.l=$dff000
Quick                   Data.q     Data.q=500/7
Floating point          Data.f     Data.f 3.14,1.79
String                  Data$      Data$ "Blitz","BASIC"
```

For example:
```
; *** Using Data 2
; *** Filename - Data2.bb2

; *** Read program data into variables
Read A$,B,C.w
; *** Output variable contents
NPrint A$
NPrint B
NPrint C
; *** Wait for a mouse click
MouseWait
; *** Return to Blitz Basic 2 editor
End

; *** Program data
Data$ "Blitz" ; *** String type data
Data 39 ; *** Quick type data
Data -10 ; *** Word type data
```


1.16 End-of-Chapter summary
---------------------------

There are three different types of Blitz Basic token: functions, statements
and commands.

Functions are Blitz Basic tokens that require parameters in parentheses,
and return a value.

Statements are Blitz Basic tokens that only perform an action but do not
return a value. Their arguments do not require parentheses.

Commands are Blitz Basic tokens that can be used as either a function or a
statement, depending upon whether the arguments were in parentheses or not.

Blitz Basic 2 runs under two modes: Amiga and Blitz. For system-friendly
programs use Amiga mode and, for extra speed, throw the operating system
out of the window with Blitz mode.

Variables represent values that are used in a program. Blitz Basic supports
six different types of variable: five numeric types with different ranges
and accuracies for numeric data, and one string type ($) for character
strings. Custom types can be created with the NEWTYPE statement.

Constants are values which are defined by the programmer, but do not change
during program execution.

A string variable is one which contains text, rather than numbers. Strings
are surrounded by quotation marks and all string names must end with the
dollar ($) character.

Operators perform mathematical or logical operations on values.

An array is a list of variables of the same name that are distinguished by
subscripts (values that identify each variable or element in the array).
List arrays are limited in size to one dimension.

Program execution is stopped with the END statement.

Large amounts of data can be stored in your programs with the DATA
statement.



