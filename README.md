# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure

It can be implemented using two half subtractors and one OR gate as: Giving one half subtractor the inputs A and B that gives outputs Diff1 and B1. 
Giving second half subtractor inputs Bin and Diff1 from first subtractor that gives outputs B2 and D (difference for the full subtractor).

## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: Sanjay Ragavendar M K

RegisterNumber:  212222100045
*/
```
HALF_SUBTRACTOR :
```
module Halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```
FULL_SUBTRACTOR :
```
module FulLsub(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```
## Output:

## Truthtable
## Half Subractor
![image](https://user-images.githubusercontent.com/118343698/233010188-fed844da-9448-441f-98f2-00b348484c55.png)
## Full Subractor
![image](https://user-images.githubusercontent.com/118343698/233010238-63f92445-9a1a-40f9-851b-ef688ec5a102.png)



##  RTL realization
## Half Subractor
![image](https://github.com/JoyceBeulah/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118343698/3e77ebf7-c5ee-49e7-85c4-9c9eb0c15814)
## Full Subractor
![image](https://github.com/JoyceBeulah/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/118343698/913c8808-2337-4a36-8cc9-7c58f7b4fee2)

## Timing diagram 
## Half Subractor
![image](https://user-images.githubusercontent.com/118343698/233009935-357b3035-4b71-4648-998b-57b63d359cb7.png)
## Full Subractor
![image](https://user-images.githubusercontent.com/118343698/233010064-811a6281-4b1f-466a-a93e-3407de5632e0.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
