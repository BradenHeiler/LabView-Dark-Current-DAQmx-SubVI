# LabView-Dark-Current-DAQmx-SubVI
LabView Code for Controlling Solenoid Actuators

Basic LED ON Off:
This Labview Program is used to control one of the digital I/O
pins to turn a LED on and off. Use it as a sanity check to see
if everything is working.

boolean to bit string:
Labview program in development

DAQmx.Dark.Current.main:
This is the main Labview program that will send 8 bits to the circuit.
It requires you to specify the port and line numbers of the 4 pins
(data, sync, clear, write). On the datasheet this corresponds to 
( SER, RCLK, SRCLR, SRCLK) respectively. 

DAQmx.Dark.Current.SubVI.SendData:
This is a subvi that controls sending the bits to the shift registers.
Simply wire the data, sync, clear, and write tasks that are ongoing and
specify the bit string to be sent to the shift register.

5 Pin Control:
This allows you to manually control 5 pins to operate the shift register
manually. 