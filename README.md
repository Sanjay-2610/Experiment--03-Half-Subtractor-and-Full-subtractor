# Experiment--03-Half-Subtractor-and-Full-subtractor
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



Connect the supply(+5V) to the cirucit. Switch ON the main switch if the output is 1,then the led glows.


## Program:
### Half Subtractor
```verilog
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Sanjay Ragavendar M K
RegisterNumber:  212222100045
*/
module half_sub(x,y,d,b);
input x,y;
output d,b;
wire x1;
xor(d,a,b);
not(x1,x);
and(b,x1,y);
endmodule
```
### Full Subtractor
```verilog
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Sanjay Ragavendar M K
RegisterNumber:  212222100045
*/
module full_sub(a,b,c,d,bo);
input a,b,c;
output d,bo;
wire w1,w2,w3,w4,w5;
xor(w1,b,c);
xor(d,w1,a);
not(w2,b);
and(w5,w2,c);
not(w3,w1);
and(w4,w2,a);
or(bo,w4,w5);
endmodule
```
## Output:

##  RTL realization
### Half Subtractor
![rtl_half_subtractor](https://user-images.githubusercontent.com/91368803/232930926-da8e1b34-bede-4eb1-b3b3-0b17b4ea4ceb.png)
### Full Subtractor
![rtl_full_subtractor](https://user-images.githubusercontent.com/91368803/232930941-ffd36622-0ca2-4bc1-9b52-54584f11fbea.png)


## Timing diagram 
### Half Subtractor
![timing_half_subtractor](https://user-images.githubusercontent.com/91368803/232931077-1829e9d0-a92c-43b2-a55a-d898d1cdbab3.png)
### Full Subtractor
![timing_full_subtractor](https://user-images.githubusercontent.com/91368803/232931094-2a5f29e8-e0e9-4252-96d0-da9b9fc82fca.png)


## Truth Table
### Half Subtractor
![truth_table_half_subtractor](https://user-images.githubusercontent.com/91368803/232931282-b85f8411-34f0-48c2-a12f-eaa9046caa99.png)

### Full Subtractor
![truth_table_full_subtractor](https://user-images.githubusercontent.com/91368803/232931299-f54dc5c5-2833-4ab0-906d-6c20a263df2d.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
