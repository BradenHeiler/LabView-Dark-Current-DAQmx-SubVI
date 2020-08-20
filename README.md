# LabView-Dark-Current-DAQmx-SubVI
LabView Code for Controlling Solenoid Actuators



Main.vi:
This is the main Labview program. A version of the brute force 
algorithm has been decided on and implemented in this version. All
the dependancies are found in the Dependancies directory. 
It requires you to specify the port and line numbers of the 4 pins
(data, sync, clear, write). On the datasheet this corresponds to 
( SER, RCLK, SRCLR, SRCLK) respectively. It has been agreed that:
data pin  - port 0, line 0
sync pin  - port 0, line 1
write pin - port 0, line 2
clear pin - port 0, line 3

All previous code is located in Archive. 


Some Dependancies

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



TODO:
Figure out a better way to stop the program immediatly. Currently, the 
stop button just stops the next iteration which will take at most 10min 
to do. 

Utilize shift register error checking in the main code. Currently a vi
that reads the current state of the shift register is found in the 
"Check for Shift Reg Error" directory.

Make some corrections to the currents that are displayed after the test.

Implement some sort of eclipsed time, current iteration number isn't working


