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



Write the detailed procedure here 


## Program:
```
/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: varsha.g
RegisterNumber:  22002003
*/
1.) For HALF SUBTRACTOR:
module half_sub(a,b,diff,b_out);
input a,b;
wire d;
output diff,b_out;
xor (diff,a,b);
not (d,a);
and (b_out,d,b);
endmodule

2.)For FULL SUBTRACTOR:
module full_sub(b_out,diff,a,b,c_in);
output b_out,diff;
input a,b,c_in;
wire w1,w4,w5,w6;
xor (diff,a,b,c_in);
not (w1,a);
and (w4,w1,b);
and (w5,w1,c_in);
and (w6,b,c_in);
or (b_out,w4,w5,w6);
endmodule

```
## Output:

## Truthtable
1.for halfsubtractor:

![image](https://user-images.githubusercontent.com/119288183/229424974-c5f7a8c3-0206-4fcb-816e-0f34253363e4.png)

2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/119288183/229426422-2081fce5-b17f-493f-afd8-a4b234cd2345.png)


##  RTL realization
1.for halfsubtractor:

![image](https://user-images.githubusercontent.com/119288183/229426602-9ae02921-3477-4d79-9576-9cb4bf945157.png)

2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/119288183/229426680-0d19e0ae-29ea-42c2-adea-c0e49f26b3a6.png)



## Timing diagram

1.for halfsubtractor:

![image](https://user-images.githubusercontent.com/119288183/229426835-c0f0eb30-a844-4e2a-8e08-051981695e42.png)

2.For FULL SUBTRACTOR:

![image](https://user-images.githubusercontent.com/119288183/229426926-62b8da02-c97c-476f-a3bb-3f5b4d983af3.png)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
