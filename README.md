# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

1. Type the program in Quartus software.
2. Compile and run the program.
3. Generate the RTL schematic and save the logic diagram.
4. Create nodes for inputs and outputs to generate the timing diagram.
5. For different input combinations generate the timing diagram.

**PROGRAM**
```
module  ex6(s, r, clk, rst, q);
  input s, r, clk, rst;
  output reg q;

  always @(posedge clk or posedge rst)
begin
    if (rst)
    q <= 0; // Reset the flip-flop
    else
begin
      case ({s, r}) // S and R control the behavior
        2'b00: q <= q; // No change
        2'b01: q <= 0; // Reset
        2'b10: q <= 1; // Set
        2'b11: q <= 0; // Invalid state, typically treated as reset
      endcase
     end
  end
endmodule
```

 Developed by : BALA SARAVANAN K
 
 Register Number : 212224230031


**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/728d8eac-e96d-4a55-a6c5-7883247b0a43)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/bd00175b-ac3d-440c-8188-46b365df3d2b)

![image](https://github.com/user-attachments/assets/fc9946aa-a8c0-48ca-8d15-94f184cb9f30)

**RESULTS**

4 Bit Ripple Counter is implemented using verilog and validated their functionality using their functional tables.
