ECE281_CE3
==========

I am having trouble getting the correct version of the Moore shell VHDL to upload on here. For some reason, it uploaded the blank shell code without any of my changes on it. I tried re-pushing the code, but that did not work. Here is a copy of what the corrected code should look like.

--COMPLETE THE NEXT STATE LOGIC ASSIGNMENTS FOR FLOORS 3 AND 4
				when floor3 =>
					if (up_down = '1' and stop = '0') then 
						floor_state <= floor4;
					elsif (up_down = '0' and stop = '0') then 
						floor_state <= floor2;	
					else
						floor_state <= floor3;	
					end if;
				when floor4 =>
					if (up_down = '0' and stop = '0') then 
						floor_state <= floor3;	
					else 
						floor_state <= floor4;
					end if;
				
				--This line accounts for phantom states
				when others =>  
					floor_state <= floor1;
			end case;
		end if;
	end if;
end process;

-- Here you define your output logic. Finish the statements below
floor <= "0001" when (floor_state = floor1) else
			"0010" when (floor_state = floor2) else
			"0011" when (floor_state = floor3) else
			"0100" when (floor_state = floor4) else
			"0001";

end Behavioral;

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


Documentation: I referred to my class notes for the syntax of both processes as well as cases. I had a little trouble with the syntax for the if and elsif statements,I was putting elseif instead of elsif, but soon resolved those.
