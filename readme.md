# 16 Bit CPU

16-Bit CPU made in Logisim

This is fully functional CPU for which you can write your own program in his assembly.

## Instructions

  1. Zero Adress instructions

      - HALT  - 0000 0000 - Shuts down the processor
      - RTS - 0000 0001  - Returns from subroutine
      - RTI	  - 0000 0010  - Returns from interrupt routine
      - ASL  - 0000 0011  - Aritmethic shift left
      - POPPSW  - 0000 0100  - Pops PSW from the stack
      - PUSH  - 0000 0101  - Pushes Accumulator to the stack
      - POP  - 0000 0110  - Pops  Accumulator from the stack
  2. Branch instructions

      - BEQL  - 0001 0000  - Branches to PC+Third byte if PSWZ=1
      - BNEQ  - 0001 0001  - Branches to PC+Third byte if PSWZ=0
      - BLEQU  - 0001 0010  - Branches to PC+Third byte if ( PSWC + PSWZ )=1
      - BLSS  - 0001 0011  - Branches to PC+Third byte if ( PSWN xor PSWV) =1
      - JLEQ  - 0001 0100  - Jumps to the address given by the 3rd and 4th instruction byte
      - JMP  - 0010 0000  - Jumps to the address given by the 2rd and 3th instruction byte
      - JSR  - 0010 0001  - Jumps to the address given by the 2rd and 3th instruction byte
  3.  Adress instructions

      - LD  - 0011 0000  - Loads into the Accumulator
      - ST  - 0011 0001  - Stores to the memory location
      - JADR  - 0011 0010  - Jumps to the address
      - TST  - 0011 0011  - "Logical and" ("&")  of the Accumulator and second operand without changing the accumulator value, thus only updating PSW
      - XOR  - 0011 0100  - XOR with changing the accumulator
      - STRLEN  - 0011 0101  - Measures length of a string, operand is a pointer to the string, 00h  is regarded as the end of the string character

## Types of addressing

  - immed  - Operand is given in instruction Bytes
  - memdir  - Memory location of operand is in instruction Bytes
  - regdir  - Register which stores the operand is given in instructions Bytes
  - memind  - Memory location which stores the memory location of operand is given in instructions Bytes
  - preincr  - Increment of instruction Bytes gives us register which has operand
  - postdec  - Register which stores the operand is given in instructions Bytes, which are to be decremented after instruction
  - regindpom  - Memory location of operand = Content of given register + next instruction Byte
  
