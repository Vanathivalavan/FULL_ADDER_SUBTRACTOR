# FULL_ADDER_SUBTRACTOR
Implementation-of-Full-Adder-and-Full-subtractor-circuit
AIM:
To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

Equipments Required:

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime


#Full Adder and Full Subtractor

#Full Adder
Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.


Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin


Carry = AB + ACin + BCin

Full adder
<img width="651" height="330" alt="image" src="https://github.com/user-attachments/assets/179551e3-eb55-4181-937b-c13675f56d19" />


#Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

<img width="753" height="326" alt="image" src="https://github.com/user-attachments/assets/32386ab6-73ad-4416-95df-20245a6dcb75" />


Diff = A ⊕ B ⊕ Bin

Borrow out = A'Bin + A'B + BBin

#Procedure
Procedure for Designing a Full Adder

Define the Problem: Design a circuit that adds three one-bit binary numbers: A, B, and \(C_{in}\).Create a Truth Table: Construct a truth table showing all eight possible input combinations (for 3 inputs) and their corresponding Sum (S) and Carry-out (\(C_{out}\)) outputs.Derive Boolean Expressions: Use the truth table to derive the Boolean expressions for S and \(C_{out}\), often simplified using Karnaugh maps (K-maps).\(S=A\oplus B\oplus C_{in}\)\(C_{out}=AB+AC_{in}+BC_{in}\)Draw the Logic Diagram: Implement the simplified expressions using logic gates (XOR, AND, OR) or by using two half-adders and an OR gate.Verify the Design: Test the designed circuit, typically through simulation or on a breadboard, to verify the outputs match the truth table for all input combinations.

Procedure for Designing a Full Subtractor

Define the Problem: Design a circuit that subtracts two single bits (B and \(B_{in}\)) from a single bit (A).Create a Truth Table: Construct a truth table showing all eight possible input combinations (A, B, and \(B_{in}\)) and their corresponding Difference (D) and Borrow-out (\(B_{out}\)) outputs.Derive Boolean Expressions: Use the truth table to derive the Boolean expressions for D and \(B_{out}\), simplifying them using K-maps.\(D=A\oplus B\oplus B_{in}\)\(B_{out}=A^{\prime }B+A^{\prime }B_{in}+BB_{in}\)Draw the Logic Diagram: Implement the simplified expressions using logic gates, or by combining two half-subtractors and an OR gate.Verify the Design: Test the circuit to ensure the outputs match the truth table for all possible input combinations.


#Program:

Full Adder
```
// Full Adder in Verilog
module full_adder (
    input  wire a, b, cin,   // Inputs
    output wire sum, carry   // Outputs
);

    // Logic equations
    assign sum   = a ^ b ^ cin;                  // XOR for sum
    assign carry = (a & b) | (b & cin) | (a & cin); // Majority function for carry

endmodule
```
Full Sub
```
// Full Subtractor in Verilog
module full_subtractor (
    input  wire a, b, bin,       // Inputs
    output wire diff, borrow     // Outputs
);

    // Logic equations
    assign diff   = a ^ b ^ bin;                  // Difference
    assign borrow = (~a & b) | (~(a ^ b) & bin);  // Borrow logic

endmodule
```

#RTL Schematic:

Full Adder:
<img width="1920" height="1020" alt="Screenshot 2025-12-13 210945" src="https://github.com/user-attachments/assets/97d79a71-6167-445c-811a-d56914bf540a" />

Full Subtractor:
<img width="1920" height="1020" alt="Screenshot 2025-12-13 215731" src="https://github.com/user-attachments/assets/13e73f6b-5374-4b8c-a1d0-a5c2a0b52939" />

Output Timing Waveform

#Result: Thus, the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.

