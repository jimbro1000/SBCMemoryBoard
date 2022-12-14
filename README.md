# HD6309SBC Mapped Memory Board

This is a design for memory expansion of the HD6309 single board 
computer I designed (See https://github.com/jimbro1000/HD6309sbc)

The board provides the full 64k RAM model (rather than the 50:50
RAM/ROM model) plus paged memory mapped in at $8000. The current
design includes 1MB of paged memory but can handle up to 4MB.

It is up to the programmer to make sure code is safe to handle
page swaps and avoid broken stacks, etc.

## Hardware registers

The switching of memory pages is handled by writing to address 
$FF25. The value is effectively address lines 14 to 21 of the 
extended memory.

Whichever page is selected is mapped to a base address of $8000 
for the CPU.
