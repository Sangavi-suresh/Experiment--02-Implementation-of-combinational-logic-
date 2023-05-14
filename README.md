# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.
 F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
 
 
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
 Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

##Using NAND gates:
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'
## Logic Diagram:
Using NOR gates NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Procedure:
Step 1: Create a project with required entities.
Step 2: Create a module along with respective file name.
Step 3: Run the respective programs for the given boolean equations.
Step 4: Run the module and get the respective RTL outputs.
Step 5: Create university program(VWF) for getting timing diagram.
Step 6: Give the respective inputs for timing diagram and obtain the results.

## Program:
/*
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
Developed by: Sangavi Suresh
RegisterNumber: 212222230130
*/
 COMBINATION 1 USING NAND OPERATION

module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R;  
assign P = C&(~B)&(~A);  
assign Q = D&(~C)&(~A);  
assign R = (~C)&B&(~A);  
assign F = (~P&~Q&~R);  
endmodule 


COMBINATION 2 USING NOR OPERATION
 
module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R,S;  
assign P = C&(~B)&A;  
assign Q = D&(~C)&A;  
assign R = C&(~B)&A;  
assign S = ~(P|Q|R);  
assign F = ~S;  
endmodule 

## RTL realization:
NAND:

![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/bfb59130-485c-454c-b709-f7edb5678a7e)

NOR:
![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/2ce21763-9285-4186-8688-85d9fd697204)


## Output:
NAND:
![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/9dc7670c-c420-4324-a9f5-0b9a8153e0ff)

NOR:
![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/4cf46794-fcfe-4ff2-8310-91f0bb00ce8f)

## Timing Diagram:
NAND:
![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/bd777c6c-4959-4a03-b273-965ecde1bd95)

NOR:
![image](https://github.com/Sangavi-suresh/Experiment--02-Implementation-of-combinational-logic-/assets/118541861/4d32ce0b-8a09-4381-899a-2476c9d7d221)

## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.
