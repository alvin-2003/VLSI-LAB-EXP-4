# VLSI-LAB-EXP-4
SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

AIM: 
 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7
Spartan6 FPGA

**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)


JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)


D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)


COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)


  
PROCEDURE:
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.

# VERILOG CODE
```
module srff(s,r,clk,rst,q);
input s,r,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({s,r})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=1'bX;
endcase
end
end
endmodule
```
OUTPUT WAVEFORM
![321309519-fde5adbc-d127-43c7-9c3a-c97e33c69621](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/59cfacc6-57c3-4e2a-b6d0-f0819debd2a6)

# JK FLIPFLOP
# Logic Diagram:
![321309704-fe2a5529-43ac-4082-8cac-c76d3b0e7b7c](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/9a9504f1-6a2c-49cd-bad9-88f7acd2f79e)

# verlog code:
```
module jkff(j,k,clk,rst,q);
input j,k,clk,rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=0;
else
begin
case({j,k})
2'b00:q=q;
2'b01:q=0;
2'b10:q=1;
2'b11:q=~q;
endcase
end
end
endmodule
```
# Output:
![321310017-b12acba8-0471-448a-8dc6-4bc19cde4bc3](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/98349fd1-e185-4003-a206-d38a4b4294e5)

# T FLIPFLOP
# Logic Diagram:
![321310411-697518d6-da49-48c9-85b5-91688460a237](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/b8bb5788-b1c1-421a-97cd-cbf8ba3be6d8)
# verilog code:
```
module tff(clk,rst,t,q);
input clk,rst,t;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else if (t==0)
q=q;
else
q=~q;
end
endmodule
```
# Output:
![321310826-1d84bc96-d7b9-44bf-9f1b-b1793188a121](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/ebf14724-4843-414a-a9ca-90baa57fc53c)

# D FLIPFLOP
# Logic Diagram:
![321311726-d09dddf0-3f9f-4e6d-9f69-3787c39000d2](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/8d1c54b6-b0b6-43c1-83f8-9aff94e79a02)
# verilog code:
```
module dff(d,clk,rst,q);
input d,clk,rst;
output reg q;
always @(posedge clk)
begin
if (rst==1)
q=1'b0;
else
q=d;
end
endmodule
```
# Output:
![321312052-0daf167d-d841-4311-8c4a-278de39d27c4](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/d013a5d1-3afb-4590-9941-c875c4c4f351)

# COUNTER
#Logic Diagram:
![321312544-15be6215-2b4d-48e6-8f2e-d6932e27e3b0](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/340d2020-ec62-4ea8-9aba-01d8391a8ed0)
# Updown Counter:
# Logic Diagram:
![321313073-19856d87-24ca-4363-84aa-12799c6fecc6](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/43faddbb-f6ad-4d18-8a17-2690e79680f2)

# verilog code:
```
module udc(clk,rst,updown,out);
input clk,rst,updown;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1)
out=4'b0000;
else if(updown==1)
out=out+1;
else
out=out-1;
end
endmodule
```
# Output:
![321313237-fd74457f-1f35-4e94-a628-5efff9ba956f](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/1b8ba23d-a9e3-4adf-9063-11dd44683e67)

# Mod-10 Counter:
# Logic Diagram:
![321313412-637add02-e848-4f74-a8b8-9e183a68df4b](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/144380ab-f053-4533-9080-d0a2d71bd637)

# verilog code:
```
module mod10(clk,rst,out);
input clk,rst;
output reg [3:0]out;
always@(posedge clk)
begin
if (rst==1 | out==4'b1001)
out=4'b0000;
else
out=out+1;
end
endmodule
```
# Output:
![321313630-20fb126a-6ff9-48a3-876f-64c9b710f28c](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/54b41dfc-f1df-4581-ba8c-23fb7487fde1)

# Ripple Carry Counter:
# Logic Diagram:
![321313815-c8966ae1-c506-4bfc-a6e3-028ea15d87a2](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/c391e93f-42fb-4442-a519-e960db067217)

# verilog code:
```
module tff(q,clk,rst);
input clk,rst;
output q;
wire d;
dff df1(q,d,clk,rst);
not n1(d,q);
endmodule

module dff(q,d,clk,rst);
input d,clk,rst;
output q;
reg q;
always @(posedge clk or posedge rst)
begin
if (rst)
q=1'b0;
else 
q=d;
end
endmodule

module rcc(clk,rst,q);
input clk,rst;
output [3:0]q;
tff tf1(q[0],clk,rst);
tff tf2(q[1],q[0],rst);
tff tf3(q[2],q[1],rst);
tff tf4(q[3],q[2],rst);
endmodule
```
# Output:
![321314073-9738870c-f3e1-40a5-87be-5a6cb680ca91](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/163816866/67beaf52-9332-4c15-a836-d40b34a67656)

# RESULT:
Hence SR, JK, T, D - FLIPFLOP, COUNTER DESIGN are simulated and synthesised using Xilinx ISE.




