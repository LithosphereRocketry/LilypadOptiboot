# LilypadOptiboot

Running at 3.3V the Atmega 328P microcontroller is limited to 8MHz.  One can compile for this case in the Arduino IDE using the Lilypad Board, which runs at 8MHz.

The Atmega 328P based Lilypad uses an external 8 MHz oscillator, but one can also use the internal oscillator at this frequency.  The bootloader in the Arduino IDE sets the low fuse to 0xFF, which directs the chip to use an external oscillator.  This will brick the chip in a system with no oscillator, requiring  high-voltage programming or the connection of an external oscillator to bring it back.  (Setting this fuse to 0xE2 would instruct it to use the internal  oscillator instead.)

This project adds a new bootloader option for the Atmega 328P runnning at 8 MHz on the internal oscillator.  It also uses the optiboot bootloader, saving 1.5k of code space.
