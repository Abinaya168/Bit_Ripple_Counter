# Bit_Ripple_Counter
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

/* write all the steps invloved */

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.

 Developed by:P.Abinaya RegisterNumber:25014594
*/
```
module Bitripplecounter (
    input clk,
    input reset,
    output reg [3:0] q
);

    // LSB flip-flop
    always @(posedge clk or posedge reset)
    begin
        if (reset)
            q[0] <= 1'b0;
        else
            q[0] <= ~q[0];
    end

    // Next flip-flop
    always @(posedge q[0] or posedge reset)
    begin
        if (reset)
            q[1] <= 1'b0;
        else
            q[1] <= ~q[1];
    end

    always @(posedge q[1] or posedge reset)
    begin
        if (reset)
            q[2] <= 1'b0;
        else
            q[2] <= ~q[2];
    end

    always @(posedge q[2] or posedge reset)
    begin
        if (reset)
            q[3] <= 1'b0;
        else
            q[3] <= ~q[3];
    end

endmodule

```

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1619" height="917" alt="Screenshot 2025-12-14 103648" src="https://github.com/user-attachments/assets/f050e764-12de-4595-b581-009136d9f4aa" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="696" height="307" alt="image" src="https://github.com/user-attachments/assets/d0644c6e-b13f-4f8f-b412-729106f2305d" />

**RESULTS**
