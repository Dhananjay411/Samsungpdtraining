# Samsungpdtraining
- [Day-0-Installation](#Day-0-Installation)
- [Day-1-Introduction to Verilog RTL Design and Synthesis](#Day-1-Introduction-to-Verilog-RTL-Design-and-Synthesis)
- [Day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style](day-2-Timing-libs,-hierarchical-vs-flat-synthesis-and efficient-flop-coding-style)
  
## Day-0-Installation

 <details>
 <summary>dc_shell</summary>
Design Compiler is the command line interface of Synopsys synthesis tool. It includes innovative topographical technology that enables a predictable flow resulting in faster time to results.It is invoked using the command dc_shell    

Below is the screenshot showing the successful launch:

<img width="1085" alt="dc_shell" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/dc_shell.png">
</details>

 <details>
 <summary>icc2_shell </summary>
ICC2 compiler is a complete netlist-to-GDSII implementation system that includes early design exploration and prototyping, detailed design planning, block implementation, chip assembly, and sign-off-driven design closure. It is invoked using the command icc2_shell     

Below is the screenshot showing the successful launch:

<img width="1085" alt="icc2_shell" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/icc2_shell.png">
</details>


<details>
 <summary>lc_shell</summary>
Library Compiler (LC) parses this textual information for completeness and correctness, before converting it to a format, used globally by all Synopsys applications. It is invoked using the command lc_shell.   

Below is the screenshot showing the successful launch:

<img width="1085" alt="lc_shell" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/lc_shell.png">
</details>
 

<details>
 <summary>pt_shell</summary>
PrimeTime is a Static Timing Analysis (STA) tool from Synopsys. This is a simple description to use PrimeTime for the VLSI class project. It is invoked using the command pt_shell   

Below is the screenshot showing the successful launch:

<img width="1085" alt="pt_shell" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/pt_shell1.png">
</details>
 
<details>
 <summary>gtkwave</summary>
GTKWave is the best free wave viewer and is the recommended viewer by the Icarus Verilog simulation tool. The GTKWave software is used as a simulation tool to verify the Verilog design code through a test bench. It is invoked using the command gtkwave.   

Below is the screenshot showing the successful launch:

<img width="1085" alt="gtkwave" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/gtkwave.JPG">
</details>

<details>
 <summary>yosys</summary>
Yosys is a framework for RTL synthesis. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. It is invoked using the command yosys.

Below is the screenshot showing the successful launch:

<img width="1085" alt="yosys" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd_%23day0/yosys.JPG">
</details>

<details>
 <summary> Summary </summary>
	
I invoked all the shells using the given commands and attached corresponding screenshots

</details>	

## Day-1-Introduction to Verilog RTL Design and Synthesis

 <details>
 <summary>Introduction to RTL-Design, Test-bench, Simulators</summary>
	 
 **RTL**:  Register Transfer Level is a method of describing what happens to data as it is transferred from one register (or state holding device) to another. the designer should specify how the data flows between the registers and how the design processes the data.
 

 
**Testbench**: it is a code module that describes the stimulus to a logic design and checks whether the design's outputs match its              specification. it is used for the verification of the digital hardware design. verification required to ensure the design meets the timing and  funcationality requirements. it is used to simulate and analyze designs without the need for any physical hardware or any hardware device. the  most important advantage of this is that you can inspect every signal/ variable (reg, wire in verilog) in the design. 

**Simulator**: RTL design is checked for adherence to its design specification using simulation by giving simple inputs.
 It is a design abstraction that models a synchronous digital circuit in terms of the data flow between hardware registers, and the logical operations performed on those signals. In RTL code we write code for combinational and sequential circuits like that of HDL, and VHDL.
 The tool used for this purpose is called Simulator. The simulator looks at the input changes and then evaluates the output. It produces an output in the form of a .vcd file.  

</details>	
 <details>
 <summary>Labs on examples of iverilog and gtkwave</summary>

 We performed all the lab examples on the Linux operating system.

 **Iverilog**: Icarus Verilog is an implementation of the Verilog hardware description language compiler that generates netlists in the desired format (EDIF). It supports the 1995, 2001 and 2005 versions of the standard, portions of SystemVerilog, and some extensions.

 **Gtkwave**: GTKWave is a fully featured GTK+ based wave viewer for Unix, Win32, and Mac OSX which reads LXT, LXT2, VZT, FST, and GHW files as well as standard Verilog VCD/EVCD files and allows their viewing.

 We made a directory namely VLSI and inside that directory we cloned vsdflow repository. This repository consists of the required .lib files and verilog codes for practice. 

 Below is the output wave form in gtkwave generated by performing a simulation of good_mux using iverilog. 
 
 The syntax of the code is: iverilog RTL_design_code Testbench
 


<img width="1085" alt="gtkwaveform" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/gtkwave_waveform.JPG">
RTL design code of the 2:1 MUX
<img width="1085" alt="good_mux_design_code" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/good_mux_design_code.JPG">
Testbench for 2:1 MUX
<img width="1085" alt="testbench" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/testbench.JPG">

</details>
<details>
 <summary>Introduction to Yosys</summary>

 **Synthesis**: Synthesis in VLSI is the process of converting your code (program) into a circuit. In terms of logic gates, synthesis is the process of translating an abstract design into a properly implemented chip. It is a process of converting a RTL code into a gate level netlist. The tool used for this purpose is called synthesizer.

 **Yosys** : Yosys is a framework for RTL synthesis and more. It currently has extensive Verilog-2005 support and provides a basic set of synthesis algorithms for various application domains. Yosys is the core component of most our implementation and verification flows.

**Verification of synthesized design** : In order to make sure that there are no errors in netlist we need to verify the netlist generated by synthesizer. This can be done by giving netlist and testbench to a simulator which in turn produces a .vcd file , then verifying the vcd file gtkwave. The output produced by this vcd file should be same as the one generated by the RTL design code.

**Faster Cells Vs Slower Cells** :Load in digital circuit is of Capacitence. Faster the charging or dicharging of capacitance, lesser is the celll delay. However, for a quick charge/ discharge of capacitor, we need transistors capable of sourcing more current i.e, we need WIDE TRANSISTORS.

Wider transistors have lesser delay but consume more area and power. Narrow transistors are other way around. Faster cells come with a cost of area and power.

Selection of the Cells: We'll need to guide the Synthesizer to choose the flavour of cells that is optimum for implementation of logic circuit. Keeping in view of previous observations of faster vs slower cells,to avoid hold time violations, larger circuits, sluggish circuits, we offer guidance to synthesizer in the form of Constraints.
</details>

<details>
<summary>Labs on Yosys </summary>
 We were given the overview of this tool and the basic files required to perform the experiment on 2:1 MUX. 
 
 **Procedure** : First we need to read the liberty file using the code
 
 **read_liberty -lib <path of the .lib>**
 
 Then we need read the RTL Design code

 **read_verilog <RTL_Design_file>**

 After this we need to perform synthesis 

 **synth -top <instance_name>**
 
 generating netlist

 **abc -liberty <.lib path>**
 
This Netlist can be viewed in the synthesized circuit form using the **show** command    

<img width="1085" alt="ckt" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/yosys_good_mux.JPG">
The Nestlist code 
<img width="1085" alt="netlist" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/yosys_netlist.JPG">

Simplified Netlist code 

</details>

## Day-2-Timing-libs-hierarchical-vs-flat-synthesis-and-efficient-flop-coding-styles

<details>
 <summary> Timing Library </summary>

 **Timing libs**:Timing libraries refer to a set of data files and models that provide essential information about the timing characteristics of the electronic components (gates, flip-flops, etc.) used in a digital circuit. These libraries are crucial for accurately predicting the behavior and performance of the designed integrated circuits. Here's a brief overview of timing libraries in VLSI:

 Standard Delay Format (SDF): SDF is a widely used file format for representing timing libraries in VLSI design. It contains information about the delays associated with various logic gates, interconnects, and flip-flops. SDF files are essential for static timing analysis (STA) tools to calculate the critical paths, setup times, hold times, and other timing parameters of a digital design.

 Liberty Format: Liberty is another commonly used format for representing timing libraries in VLSI. Liberty files (with a .lib extension) contain detailed timing, power, and other electrical characteristics of cells in a library. Liberty files are used by tools like synthesis tools to optimize and map a design to target technology libraries.

 Timing Models: Timing libraries typically include various timing models, such as ideal, typical, and worst-case models, for different operating conditions (e.g., corner cases like slow and fast corners). These models help designers understand how the circuit behaves under different conditions.

 Process Corners: VLSI libraries often provide information for different process corners, representing variations in manufacturing processes. These corners include typical, best-case (fast), and worst-case (slow) scenarios. Designers use this information to ensure that the circuit will work reliably across manufacturing variations.

 Clock Definitions: Libraries contain information about clock definitions, including clock-to-q delays, clock gating, and clock setup and hold times. This information is crucial for designing and verifying synchronous digital circuits.

 Cell Delay: Timing libraries provide data on cell delay, which is the time it takes for a signal to propagate through a specific logic gate. Cell delays are essential for estimating the overall delay through a logic path.

 Interconnect Models: Libraries may also include models for interconnect delays, which are critical for accurately modeling the timing behavior of wires and buses in a design.

 Power Consumption Data: Some timing libraries also include power consumption information for different cells, helping designers estimate the power consumption of their designs.

 Timing libraries play a fundamental role in the VLSI design process, enabling designers to perform static timing analysis, optimize designs for performance and power, and ensure that integrated circuits meet timing and functional specifications. These libraries are typically provided by semiconductor manufacturers or third-party vendors and are tailored to specific technology nodes and process technologies. Designers select the appropriate timing library based on the target semiconductor process and design goals.


 Timing libraries
<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/lib_1.png">
Timing libraries
<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/lib_2.png">
 nand_cell compare
<img width="1085" alt=" nand_cell compare" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/cell_compare_1.png">

  As we can see in above image, a nand gate of three different flavours are selected for discussion. Since nand is "!A&B", four different combinations of input is given along with specific leakage power. As the area is increase the delay of the cells is decrease but the power will increase. Therefore while selecting cell, synthesis tool will look for optimal cell so that it will satisfy both power, area and timing requirement.  

</details>

 <details>
  <summary>Hierarchical vs flat synthesis</summary>

   
 **hierarchical vs flat synthesis**: In the context of digital design and electronic design automation (EDA), hierarchical and flat synthesis are two different approaches to organizing and synthesizing a digital design. These approaches have distinct advantages and trade-offs, and the choice between them depends on the complexity of the design and the design goals. Let's explore both hierarchical and flat synthesis:

 **Hierarchical Synthesis**:Hierarchical synthesis involves breaking down a complex digital design into smaller, more manageable modules or blocks, often organized in a hierarchical fashion. Each module can be designed, verified, and synthesized independently. These modules can be instantiated multiple times in the design or used in other projects, promoting reusability. Hierarchical synthesis has several advantages:

 Modularity: Hierarchical synthesis encourages modular design practices, making it easier to understand, verify, and maintain a design.
 Reuse: Modules designed in one project can be reused in other projects, reducing design time.
 Parallel Development: Different teams or designers can work on different modules simultaneously, speeding up the overall design process.
 Improved Debugging: Debugging and troubleshooting are more straightforward because issues can often be isolated to specific modules.

 However, hierarchical synthesis also has some challenges:

 Interface Design: Properly defining and managing interfaces between modules is critical for successful hierarchical synthesis.
 Hierarchical Constraints: Managing timing constraints across hierarchy levels can be complex.
 Resource Utilization: Overuse of hierarchy can lead to inefficient use of resources in the synthesized design.

 **Flat Synthesis**:Flat synthesis, on the other hand, synthesizes the entire design as a single, monolithic entity without breaking it down into hierarchical modules. The advantages of flat synthesis include:

 Simplicity: Flat synthesis simplifies the design process as there is no need to manage and interface multiple hierarchical levels.
 Timing Analysis: Timing analysis can be more straightforward because all elements of the design are considered in a single context.

 However, flat synthesis has its own set of challenges:

 Scalability: Flat synthesis can become unwieldy and impractical for large, complex designs, making it difficult to manage and debug.
 Reusability: Reusing parts of the design in other projects can be more challenging when the entire design is synthesized as a single unit.
 Longer Compilation Times: Flat synthesis tends to have longer compilation times due to the complexity of analyzing and optimizing a large design.

 Choosing Between Hierarchical and Flat Synthesis:

 The choice between hierarchical and flat synthesis depends on factors such as the complexity of the design, the need for modularity and reusability, the available EDA tools, and the design team's expertise. In practice, many designs use a combination of both approaches, with critical or reusable blocks designed hierarchically, while simpler parts of the design may be synthesized flat. This hybrid approach aims to balance the benefits of both methods while mitigating their respective drawbacks. 
 
 Multiple_module verilog RTL file: 
  
 <img width="1080" alt="multiple_module_1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/multiple_module_1.png">
  
 Hierarchical Synthesis: Hierarchical synthesis divides the design into smaller modules or blocks. These blocks can be synthesized independently and reused across multiple projects. It allows us to handle the complexity by breaking it down into manageable pieces and focusing on optimizing individual blocks. Below is the sample of hierarchical synthesis:

 When we perform synthesis in yosys it generates the following schematic instead of the  above  schematic
 <img  width="1085" alt="hier" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/multiple_module_schematic.png">

 The yosys considers the module hierarchy and does mapping according to the instantiation.The netlist code for hierarchical implementation of the multiple_modules

 ```ruby
 module multiple_modules(a, b, c, y);
	  input a;
	 input b;
	 input c;
	  wire net1;
	 output y;
  sub_module1 u1 (.a(a),.b(b),.y(net1) );
  sub_module2 u2 (.a(net1),.b(c),.y(y));
endmodule

module sub_module1(a, b, y);
 wire _0_;
 wire _1_;
 wire _2_;
 input a;
 input b;
 output y;
 sky130_fd_sc_hd__and2_0 _3_ (.A(_1_),.B(_0_),.X(_2_));
 assign _1_ = b;
 assign _0_ = a;
 assign y = _2_;
endmodule

module sub_module2(a, b, y);
wire _0_;
 wire _1_;
 wire _2_;
input a;
input b;
 output y;
 sky130_fd_sc_hd__lpflow_inputiso1p_1 _3_ (.A(_1_),.SLEEP(_0_),.X(_2_) );
 assign _1_ = b;
 assign _0_ = a;
 assign y = _2_;
endmodule
```

In the netlist we can observe that separate modules namely sub_module1 sub_module2 are getting created i.e submodules are getting instanstiated not the gate cells


**Flat synthesis** : In Flat synthesis the hierarchies the flattened  out and there is a single module in the netlist i.e the gates are instantiated directly instead of submodules. We apply flat synthesis on the same  design mentioned above. The command used to perform Flat synthesis from yosys are as follows

**read_liberty -lib <path of the .lib>**
 
 **read_verilog <RTL_Design_file>**

 **synth -top <instance_name>**

 **abc -liberty <.lib path>**
 
 **flatten**

**write_verilog -noattr <File_name>**

The synthesized circuit for a flattened netlist is shown in the below image , Here submodules u1 and u2 are flattened 
<img  width="1085" alt="hier" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/multiple_module_2.2.png">

The netlist code of the flattened synthesis is as follows
```ruby

module multiple_modules(a, b, c, y);
	 wire _0_;
	 wire _1_;
	 wire _2_;
	 wire _3_;
	 wire _4_;
	 wire _5_;
	 input a;
	 input b;
	 input c;
	 wire net1;
	 wire \u1.a ;
	 wire \u1.b ;
	 wire \u1.y ;
	 wire \u2.a ;
	 wire \u2.b ;
	 wire \u2.y ;
	output y;
	 sky130_fd_sc_hd__and2_0 _6_ (
	  .A(_1_),
	 .B(_0_),
	 .X(_2_)
	);
	 sky130_fd_sc_hd__lpflow_inputiso1p_1 _7_ (
	  .A(_4_),
	  .SLEEP(_3_),
	  .X(_5_)
	 );
	 assign _4_ = \u2.b ;
	 assign _3_ = \u2.a ;
	 assign \u2.y  = _5_;
	 assign \u2.a  = net1;
	 assign \u2.b  = c;
	 assign y = \u2.y ;
	 assign _1_ = \u1.b ;
	 assign _0_ = \u1.a ;
	 assign \u1.y  = _2_;
	 assign \u1.a  = a;
	 assign \u1.b  = b;
	 assign net1 = \u1.y ;
	endmodule
```
We can see that there is a single module which consist of the gate level instantion of the two submodules .


Performing Synthesis at sub_module level is one of the good practises for the massive designs as it simplifies the debugging process . It is also helpful in cases where there many instances of the same module , Instead of synthesizing all the instances we can synthesize one and duplicate it for others and stitch them together. Here is the synthesized circuit and netlist image of the sub_module1 


<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/sub_module_1.png">
<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/sub_module1_net.png">
</details>

<details>
 <summary>Flop coding</summary>

 **Flop**: They are digital electronic circuits that are used to store information in bits as they have two stable states.Even though the input is not stable it gives stable output.
 
 **Why Flop**
 
 In a combinational circuit, the output changes after the propagation delay of the circuit once inputs are changed. During the propagation of data, if there are different paths with different propagation delays, there might be a chance of getting a *glitch* at the output. *glitch* is a signal value pulse that occurs when a logic level changes two or more times over a short period.

If there are multiple combinational circuits in the design, the occurances of glitches are more thereby making the output unstable.
To curb this drawback, we are going for flops to store the data from the cominational circuits. When a flop is used, the output of combinational circuit is stored in it and it is propagated only at the posedge or negedge of the clock so that the next combinational circuit gets a glitch free input thereby stabilising the output.

We use initialize signals or control pins called set and reset on a flop to initialize the flop, other wise a garbage value to sent out to the next combinational circuit.

**Asynchronous Reset D Flop**

Here the output signal goes low when the reset signal is high , it does not wait for the clock's edge(positive or negative edge ).i.e irrespective of the clock output changes

RTL Design code of positive edge trigerred asynchronous reset D Flop
```ruby
 module dff_asyncres ( input clk ,  input async_reset , input d , output reg q );
	always @ (posedge clk , posedge async_reset)
	begin
		if(async_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule
```
Simulation

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/tb_dff_asyncres_1.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/dff_asyncres_sche.png">

**Asynchronous set D Flop**

Here the output signal goes high when the reset signal is high , it does not wait for the clock's edge(positive or negative edge ).i.e irrespective of the clock, output changes

RTL Design code of positive edge trigerred asynchronous set D Flop
```ruby
module dff_async_set ( input clk ,  input async_set , input d , output reg q );
	always @ (posedge clk , posedge async_set)
	begin
		if(async_set)
			q <= 1'b1;
		else
			q <= d;
	end
endmodule
```
Simulation 

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/tb_async_set_2.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/commit/e8f86fd9002c05a5cc8080bee181074614aa3320">

**synchronous reset D Flop**

Here the output signal goes low whenever the reset signal is high and at the clock edge(positive or negative)

RTL Design code of positive edge trigerred synchronous reset D Flop
```ruby
module dff_syncres ( input clk , input async_reset , input sync_reset , input d , output reg q );
	always @ (posedge clk )
	begin
		if (sync_reset)
			q <= 1'b0;
		else	
			q <= d;
	end
endmodule

```
Simulation

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/syncres_3.png">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/syn_res_sch.png">

 </details>

 <details>
<summary>Optimisation Techniques</summary>




There many special cases where we don't need any additional hardwares to implement the circuit. For Example consider a case where 3 bit number is multiplied by 2 in this case we dont need any additional hardware and only needs connecting bits to the output and grounding the LSB bit,same is realized by yosys.
```ruby
module mul2 (input [2:0] a, output [3:0] y);
	assign y = a * 2;
endmodule
```
When it comes to multiplying with the powers of 2 it justs need shifting as shown in the below image

<img  width="1085" alt="hand_writ" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/mul_by_2.jpg">

Synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/opt_mul2_sch.png">

Netlist 

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/net_for_mul2.png">

The next special was multiplying a 3 bit number by 9 , the result is as shown in the below image

<img  width="1085" alt="hand_writ" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/opt_mul_9.jpg">

The  RTL  Design code

```ruby
module mul8 (input [2:0] a, output [5:0] y);
	assign y = a * 9;
endmodule
```

The synthesized circuit

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/mul8_sch.png">

Netlist 

<img  width="1085" alt="sub_module1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/mul8_net.png">
  
 </details>
