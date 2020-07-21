# LabView-Dark-Current-DAQmx-SubVI
LabView Code for Controlling Solenoid Actuators



Main.vi:
This is the main Labview program that will send 8 bits to the circuit.
It requires you to specify the port and line numbers of the 4 pins
(data, sync, clear, write). On the datasheet this corresponds to 
( SER, RCLK, SRCLR, SRCLK) respectively. It has been agreed that:
data pin  - port 0, line 0
sync pin  - port 0, line 1
write pin - port 0, line 2
clear pin - port 0, line 3

Generate Boolean Array SubVI.vi:
This subVI generates the necissary bit array to pass to the send data 
subVI to turn a tube on or off. You specify the tube number and a boolean
of 0 if you want to turn the tube off and 1 if you want to turn it on.

Send Data SubVI.vi:
This is a subVI that controls sending the bits to the shift registers.
Simply wire the data, sync, clear, and write tasks that are ongoing and
specify the bit string to be sent to the shift register.

Clear Pins SubVI.vi:
This simply sends all zeroes to the shift registers. Use this whenever
Send Data is used. This stops the current flow to the solenoid valves 
after they have locked into place. 


DIRECTORIES:
Brute Force Method - This is one possible algorithm to go with. Instead
of searching for bad tubes, it just iterates over each tube measuring
its current. 

Datasheets - Contains all the datasheets for all the hardware used in this
test.

Training - Tools to be used to understand the hardware and how shift
registers work. 

Dark Current Test Copy For Experiments - dev.

Dark Current Test Copy For Experiments (sep. Sub VI Per Code Line) - dev.

