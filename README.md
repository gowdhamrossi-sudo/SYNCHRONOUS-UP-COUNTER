### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
```
Open Quartus software and create a new Verilog file. Paste the code and save it.
Compile the program to check for errors.
Generate the RTL schematic via the RTL Viewer and save the logic diagram.
Use the Waveform Editor to assign nodes for clk, rstn, and out.
Simulate the design with different clk and rstn combinations to generate the timing diagram, and save the results.

```


**PROGRAM**
```

module exp11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
	if(!rstn)
		out<=0;
	else
		out <= out+1;
end
endmodule
```
/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: GOWTHAM M RegisterNumber: 25016844
*/

**RTL LOGIC UP COUNTER**

<img width="1503" height="858" alt="image" src="https://github.com/user-attachments/assets/3a619c2e-6bc6-4393-9e37-0c5ecedc934a" />


**TIMING DIAGRAM FOR UP COUNTER**


<img width="1540" height="820" alt="image" src="https://github.com/user-attachments/assets/27523706-0d47-4614-92a7-5e65a7c8b09c" />

**TRUTH TABLE**

<img width="741" height="377" alt="image" src="https://github.com/user-attachments/assets/0bda5871-94da-42ba-9ef5-fe1b28f597fa" />


PROGRAM FOR DOWN COUNTER
```
module exp11(out, clk, rstn);
input clk, rstn;
output reg [3:0] out;

always @(posedge clk)
begin
    if (!rstn)
        out <= 4'b1111;   // reset to max value for down counter
    else
        out <= out - 1;   // decrement
end

endmodule
```
RTL LOGIC DOWN COUNTER

<img width="1483" height="816" alt="image" src="https://github.com/user-attachments/assets/925bb0a0-2eb7-4416-83ff-1c4f48de0f37" />

TIMING DIAGRAM FOR DOWN COUNTER

<img width="1511" height="855" alt="image" src="https://github.com/user-attachments/assets/53744efc-e6a7-4640-8850-4dddcdde37d0" />


TRUTH TABLE

<img width="400" height="442" alt="image" src="https://github.com/user-attachments/assets/ab4cf0bd-d32c-4c1c-b993-cf479381c94d" />


RESULTS

Thus the Synchronous 3 bit Up counter and Down Counter is implemeted and verified.



