# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY:**

**JK Flip-Flop:**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure:**

/* write all the steps invloved */

1. Create the JK flip-flop Verilog/VHDL design and compile the project in Quartus.
2. Open the Simulation Waveform Editor and create a new .vwf file.
3. Insert the input and output signals (clk, j, k, q, qbar) using Node Finder.
4. Generate the clock signal and draw the required J and K input waveforms.
5. Run the functional simulation and observe the output waveforms of q and qbar.

**PROGRAM:**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by: A.B.GNANA PRAGATHIKA
RegisterNumber: 212225230075
*/

module exp4de(q,qb,j,k,clock,reset);
    input j,k,clock,reset;
    output reg q, qb;
	 
always @ (posedge (clock))

    begin 
        if (!reset)
            begin
               q <= q;
               qb <=qb;
            end   
        
else
 //Write logic for JK flipflop using if else statement for four conditions

begin
               if (j == 0 && k == 0)
                    begin
                    q <= q;
                    qb <= qb;
                    end 
		else if (j != k)
                    begin
                    q <= j;
                    qb <= k;
                    end
               else if (j == 1 && k == 1) 
                    begin 
                    q <= ~q; 
                    qb <= ~qb; 
                    end 
            end
end  
endmodule

**RTL LOGIC FOR FLIPFLOPS:**

<img width="990" height="549" alt="Screenshot 2026-06-01 113125" src="https://github.com/user-attachments/assets/eddc90fa-3bd7-4e1a-b9af-5ed0a0fd6b8d" />


**TIMING DIGRAMS FOR FLIP FLOPS:**

<img width="1032" height="546" alt="Screenshot 2026-06-01 113146" src="https://github.com/user-attachments/assets/232c9f45-f450-4e2b-85ab-f039ffb5db59" />


**RESULTS:**
Thus, JK flipflop is implemented using Quartus Software.
