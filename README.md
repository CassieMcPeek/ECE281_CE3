ECE281_CE3
==========

Elevator CE
# Moore Elevator
![alt text] (https://raw.github.com/CassieMcPeek/ECE281_CE3/master/Moore_Testbench_Screenshot.JPG "Moore Screenshot")

The Moore testbench waveform is correct because the elevator starts at the first floor and then proceeds to move to the second floor
at the rising edge of the clock. It will remain there for 3 clock periods. After that, it goes to the third floor for an additional
3 clock periods and then moves to the fourth floor for 3 more clock periods. Then it will go back to the first floor.
It will move through the second and third floors on the way down but does not stop until it reaches the first floor.

# Mealy Elevator
![alt text] (https://raw.github.com/CassieMcPeek/ECE281_CE3/master/Mealy_Testbench_Screenshot.JPG "Moore Screenshot")
The mealy testbench waveform is correst because the elevator will move to each floor and wait there for 3 clock periods. 
The "next floor" output matches the next floor that is indicated by the floor output. The elevator then goes back down to the first floor
and remains there. I chose to have the elevators stop at each floor for 3 clock cycles instead of 2. 
