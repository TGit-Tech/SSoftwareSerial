# SSoftwareSerial
Arduinos Software Serial Library that frees PCINT1_vect Pin Change Interrupt for LCD Keypad Shield Button Interrupts

This is an exact copy of files at https://github.com/arduino/Arduino/tree/master/hardware/arduino/avr/libraries/SoftwareSerial

Except one line that has been commented out at:
Line #235 in SoftwareSerial.cpp

#if defined(PCINT1_vect)
//ISR(PCINT1_vect, ISR_ALIASOF(PCINT0_vect));
#endif

Which allows a Pin Change Interrupt Service Routine on A0 for LCD Keypad button presses.
Pin Change seems to work digitally so only the Up, Down, and Right buttons trigger the interrupt.
