# DC16 : a 16-bit breadboard computer :computer:

## About
The 'dc16' (name and project inspired by the [jdh8](https://www.youtube.com/watch?v=7A1SzIIKMho)) is a work-in-progress 16 bit RISC computer build on breadboards.  After taking ECE243 - Digital Systems - at UofT, I was fascinated by how processors work at a low level and wanted to try my hand at building my own, along with an assembler to go along with it.

## Pictures
in the imgs/ folder, you can see the current modules I have built.  Right now the ALU, memory, registers (partially), and clock are bulit.  *Download the images for better viewing, as github previews them a bit odd*    
  
There is a reasoning behind the different colours of wire you will see within each module, summarized here:  
* :red_circle: **RED** - pins tied to VCC (5V)
* :black_circle: **BLACK** - pins tied to GND (0V)
* :green_book: **GREEN** - data lines, alongside blue
* :blue_book: **BLUE** - data lines, alongside green
* :white_circle: **WHITE** - connections to the clock
* :ledger: **YELLOW** - control lines

I try to stick to these guidelines as much as I can, but sometimes I will have to deviate (ex yellow and white as data lines sometimes, as I would run out of green and blue :) )

## Modules
### ALU
The ALU is capable of performing addition and subtraction of 16-bit numbers, also complete with a flags register containing a zero (Z), carry (C) and negative (N) flag.  

### MEMORY
The memory is 16 kbyte of SRAM, formed through the parallel connection to 2 8x8K chips.  It has 2 operating modes: run mode, where the processor controls the address through the memory address register, data through the bus and write controls through control logic, and programming mode, where address and data are controlled manually (currently by DIP switches, soon by arduino program loader), along with manual write controls.

### REGISTERS
There will be 6 general purpose 16-bit registers within the processor, along with a program counter, stack pointer, and one of the 6 general registers later serving as a link register.

### CLOCK
The clock can be switched between modes: manual and auto. In manual mode, the push of a button will pulse the clock one cycle.  In auto mode, the clock will run automatically and frequency can be controlled by means of a potentiometer.  Currently supports clock speeds between ~1Hz -> ~2kHz, with faster speeds achievable through a different potentiometer.  Credit to ben eater for the nice clock design.

## Next Steps
The next modues i'll be building are the stack pointer, program counter, register decoder (access all registers through one control module), and control logic.  After all that careful wiring ill be making a program in c++ to program the EEPROMS responsible for the control logic, and then an assembler so that I can write some programs for the computer.  After that, i'll probably make a program loader just to make programming it easier.  After that, who knows.  I'll have some fun with it :smile:
