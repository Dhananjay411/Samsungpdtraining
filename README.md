# Samsungpdtraining
- [Day-0-Installation](#Day-0-Installation)
- [Day-1-Introduction to Verilog RTL Design and Synthesis](#Day-1-Introduction-to-Verilog-RTL-Design-and-Synthesis)
- [Day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style](#Day-2-Timing-libs,-hierarchical-vs-flat-synthesis-and-efficient-flop-coding-style)
- [Day-3-Combinational and sequential logic optimizations](#Day-3-Combinational-and-sequential-logic-optimizations)
- [Day-4-Gate level simulation(GLS), Blocking Vs Non Blocking and Synthesis Simulation mismatch](#Day-4-Gate-level-simulation(GLS),-Blocking-Vs-Non-Blocking-and-Synthesis-Simulation-mismatch)
- [Day-5-DFT](#Day-5-DFT)
  
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





 # Day-3-Combinational and sequential logic optimizations 


 <details>
 <summary> Introduction to Optimization</summary>

 **Optimization** : Optimization in Very Large Scale Integration (VLSI) design plays a crucial role in achieving efficient and high-performance integrated circuits. VLSI refers to the process of designing and fabricating complex electronic circuits on a single semiconductor chip. Optimization in VLSI encompasses various techniques and methodologies aimed at improving the performance, power consumption, area utilization, and manufacturability of these integrated circuits. Here's an introduction to optimization in VLSI:

 Objective: The primary objective of optimization in VLSI is to find the best set of parameters or configurations that meet specific design goals while minimizing or maximizing certain criteria. These goals typically include maximizing performance (e.g., speed), minimizing power consumption, reducing chip area, and enhancing reliability.

 Design Trade-offs: VLSI design involves a series of trade-offs between conflicting design goals. For example, increasing the clock frequency to improve performance may lead to higher power consumption and heat generation. Optimization aims to strike the right balance between these trade-offs.

 Design Flow: The VLSI design process typically consists of several stages, including architectural design, logic design, circuit design, physical design, and manufacturing. Optimization techniques are applied at each stage to improve the overall design quality.

 *Optimization Techniques* :

 1.  Architectural Optimization: At the architectural level, designers optimize the high-level structure of the chip. This involves choosing the right algorithms and data paths to achieve the desired functionality while minimizing resource usage.

 2. Logic Optimization: Logic optimization focuses on optimizing the gate-level implementation of the design. Techniques like Boolean logic minimization, retiming, and technology mapping are used to reduce the number of gates and improve performance.

 3. Circuit Optimization: At the circuit level, designers optimize the individual components, such as transistors and interconnects. Techniques like sizing transistors, wire sizing, and transistor-level optimization are employed to reduce power consumption and area usage.

 4. Physical Design Optimization: Physical design optimization deals with placement and routing of components on the chip. Algorithms are used to minimize wire length, reduce congestion, and ensure manufacturability.

  **Tools** : VLSI designers rely on various electronic design automation (EDA) tools to perform optimization. These tools use mathematical algorithms and heuristics to explore the design space and find optimal solutions.
 
  **Metrics** : To evaluate the effectiveness of optimizations, designers use metrics such as delay (for performance), power consumption, area (chip size), and reliability. These metrics help in quantifying the trade-offs and making informed design decisions.

  **Advanced Topics** : VLSI optimization also involves advanced topics such as low-power design, noise analysis, thermal optimization, and manufacturability-driven design. These considerations are critical for modern VLSI chips, especially in applications like mobile devices and data centers.

 **Challenges** : VLSI optimization is challenging due to the increasing complexity of designs, the need for multi-objective optimization, and the impact of manufacturing variability. Designers must adapt to new technologies and methodologies to meet the demands of cutting-edge semiconductor devices.

 In summary, optimization is a fundamental aspect of VLSI design, helping to achieve high-performance and energy-efficient integrated circuits. It involves a combination of architectural, logic, circuit, and physical design optimizations, and it is facilitated by specialized tools and metrics that guide designers in making informed decisions throughout the design process.
 
 

 
 </details>


 <details>
 <summary>Combinational Logic Optimization with examples</summary>

 **Combinational Logic Optimization** Combinational logic optimization is the process of simplifying and improving the efficiency of combinational logic circuits without changing their functionality. Combinational logic circuits are digital circuits where the output depends only on the current input values, and there are no memory elements like flip-flops involved.

 The primary goals of combinational logic optimization are to reduce the following aspects:

 Gate Count: By minimizing the number of logic gates in the circuit, you can reduce the cost of hardware implementation and potentially increase the speed of the circuit.

 **Propagation Delay**: Combinational logic circuits have a certain propagation delay, which is the time it takes for an input change to propagate through the circuit and produce a valid output. Reducing propagation delay can lead to faster circuit operation.

 **Power Consumption**: Fewer gates and shorter signal paths generally result in lower power consumption, which is critical in battery-powered devices and for reducing heat generation in electronic systems.

 There are various techniques for combinational logic optimization:

 **Algebraic Simplification**: Boolean algebra can be used to simplify logic expressions. Techniques like Karnaugh maps (K-maps) and Quine-McCluskey minimization help identify redundant terms and simplify logical expressions.

 **Gate-Level Optimization**: Transformations such as factoring, distribution, and rearranging terms can be applied to minimize the number of gates and reduce gate delays.

 **Technology Mapping**: Choosing the appropriate logic gates for a particular technology can significantly impact optimization. Different gate types have different propagation delays and power characteristics. Technology mapping matches the logic design to the available gates in the target technology.

 **Common Subexpression Elimination**: Identify and eliminate common subexpressions, which are portions of the logic that appear in multiple places in the circuit. Replacing them with a single instance can reduce gate count and improve performance.

 **Logic Reordering**: By rearranging the order in which logic operations are performed, you can reduce the critical path delay and optimize the circuit's performance.

 **Don't-Care Conditions** : Utilize don't-care conditions in truth tables to optimize the logic. Don't-care conditions indicate that the output value doesn't matter for certain input combinations, allowing for simplification.

 **Optimizing for Area vs. Speed** : Depending on the application, you may optimize for gate count (area) or propagation delay (speed). These goals can sometimes be conflicting, and designers need to strike a balance based on the specific requirements of the circuit.

 **Advanced Synthesis Tools** : Modern synthesis tools, used in digital design, perform sophisticated optimizations automatically, taking into account various constraints and objectives, including area, speed, and power.

 Combinational logic optimization is a crucial step in digital design because it can significantly impact the performance, cost, and power consumption of digital circuits. It's often an iterative process where designers refine the logic until the desired balance between performance  and resource utilization is achieved.
 
 squeeze the logic to get most optimized design in terms of area and power. There are various techniques for optimizing the circuit
 
 - constant propagation(Direct propagation)
 - Boolean Logic Optimization(K-Means ,QUine Mckluskey)
   
 **Constant Propogation** : Constant Propagation is an optimization technique employed by synthesis tools to minimize hardware implementation. This is achieved by optimizing away the logic for which parameters are configured to keep it disabled. This technique is not limited to module boundaries and the hardware can be optimized away both inside and outside.

 **Example on Constant Propogation** 
 <img  width="1085" alt="tran_level_impl" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/transistor%20level%20implemention.jpg">

 Consider the above  combinational circuit it consists of and and nor gate, so it requires 6 CMOS transistor to implement , if A is made constant value 0 then A&B will give 0 then 0 and C are given to NOR gate which reduces the expression to C compliment(C`) i.e basically a inverter . By making an input constant we can reduce this combinational circuit to an inverter which can impleneted using only 2 CMOS transistor thus reducing the hardware implementation

 **Example for Boolean Logic optimization**
 consider a concurrent statement a?(b?c:(c?a:0)):(!c) , this statement is realized using multiple multiplexers. Simplying this equation using boolean reduction techniques we get the output as ~(a^b)

 The command to optimize the circuit in yosys is **opt_clean -purge**.

 **Example - 1**

 RTL Design Code
 ```ruby
 module opt_check (input a , input b , output y);
	assign y = a?b:0;
 endmodule
 ```
 Synthesized circuit

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/opt_check_1.v_1.png">
 
 **Example-2**
 RTL Design Code
 ```ruby
 module opt_check (input a , input b , output y);
	assign y = a?1:b;
 endmodule
 ```
 Synthesized circuit

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/right_opt_check_2.v_2.png"> 

 **Example-3**
 RTL Design Code
 ```ruby
 module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
 endmodule

 ```
 Synthesized circuit

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/opt_check3_diag.png"> 

 **Example-4**
 RTL Design Code
 ```ruby
 module opt_check4 (input a , input b , input c , output y);
	assign y = a?(b?(a & c ):c):(!c);
 endmodule


 ```
 Synthesized circuit

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/opt_check_4_diag.png"> 

 **Example 5**
 There is a multi-module  on this we need to try and optimize it 
 The commands used for this are :

 **read_liberty -lib <library_path>**

 **read_verilog <verilog_file>**

 **synth -top <module_name>**

 **opt_clean -purge**

 **abc -liberty <library_path>**

 **flatten**



 **Example 5**
 RTL Design code
 ```ruby
 module sub_module(input a , input b , output y);
	assign y = a & b;
 endmodule

 module multiple_module_opt2(input a , input b , input c , input d , output y);
	wire n1,n2,n3;
	sub_module U1 (.a(a) , .b(1'b0) , .y(n1));
	sub_module U2 (.a(b), .b(c) , .y(n2));
	sub_module U3 (.a(n2), .b(d) , .y(n3));
	sub_module U4 (.a(n3), .b(n1) , .y(y));
 endmodule
 ```
 Before flatten
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/opt_2.png"> 

 After flatten
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/opt_2.2.png">

 **Example 6**
 RTL Design code
 ```ruby
	module sub_module1(input a , input b , output y);
	 assign y = a & b;
	endmodule

	module sub_module2(input a , input b , output y);
	 assign y = a^b;
	endmodule

	module multiple_module_opt(input a , input b , input c , input d , output y);
	wire n1,n2,n3;
	sub_module1 U1 (.a(a) , .b(1'b1) , .y(n1));
	sub_module2 U2 (.a(n1), .b(1'b0) , .y(n2));
	sub_module2 U3 (.a(b), .b(d) , .y(n3));

	assign y = c | (b & n1); 
	endmodule

 ```
 Before flatten
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/m1.png"> 

 After flatten
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/m2.png">

 </details>

 <details>
 <summary>Sequential Logic optimization</summary>

 There are various techniques for Sequential Logic Optimization
 
 - Sequentialal constant propagation
 
 - Advanced 
 	- State Optimization
  
  	- Retiming
   
   	- Sequential Logic cloning

 **Sequential Constant Propogation**


 Sequential constant propagation is a compiler optimization technique used to identify and replace variables with their constant values in a sequential fashion, typically within a code block or function. This optimization aims to eliminate unnecessary variable assignments and calculations by recognizing that certain variables have constant values throughout the execution of the program.

 The process of sequential constant propagation typically involves the following steps:

 **Data Flow Analysis** : The compiler performs data flow analysis to track the flow of values through the program. It analyzes how values are assigned to variables and how those variables are used in subsequent operations.

 **Constant Identification** : During this analysis, the compiler identifies variables that have constant values. These are variables whose values never change after their initial assignment.

 **Propagation** : Once constants are identified, the compiler replaces all occurrences of these constant variables with their respective constant values. This replacement occurs sequentially, one variable at a time, within the relevant code block or function.

 **Dead Code Elimination** : After each constant is propagated, the compiler may also perform dead code elimination. This process involves removing code that becomes unreachable or redundant due to constant propagation. For example, if a conditional statement always evaluates to true or false because of constant propagation, the corresponding branch of code can be eliminated.

 Consider a case where asynchronous reset D Flip-flop is fed with d = 0(i.e GND) always so the output will always be 0 irrespective of the timing or circuit.

 Asynchronous reset
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/Asy_rst.jpg">

 *Advanced*

 **State Optimisation**: This is optimisation of unused state. Using this technique we can come up with most optimised state machine.

 **Cloning** : It is an optimization technique that duplicates a cell to reduce the load on heavily loaded cell. This technique is usually preffered while performing *PHYSICAL AWARE SYNTHESIS*. Lets consider a flop A which is connected to flop B and flop C through a combination logic. If B and C are placed far from A in the flooerplan, there is a routing path delay. To avoid this, we connect A to two intermediate flops and then from these flops the output is sent to B and C thereby decreasing the delay. This process is called cloning since we are generating two new flops with same functionality as A.

 **Retiming** : Sequential circuits can be optimised by retiming. The combinational section of the circuitry is unaffected as it only rearranges the registers in the circuit.
 It is a powerful sequential optimization technique used to move registers across the combinational logic or to optimize the number of registers to improve performance via power-delay trade-off, without changing the input-output behavior of the circuit.

 **Example 1**
 Here flop is inferred in output 
 ```ruby
 module dff_const1(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b0;
		else
			q <= 1'b1;
	end
 endmodule
 ```
 Simulation

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_1.png">

 synthesized circuit

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_dff_const_1.png">

 **Example 2**
 Here flop is not inferred in output 
 ```ruby
 module dff_const2(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b1;
		else
			q <= 1'b1;
	end
 endmodule

 ```
 Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_2.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_dff_const_2.png">

**Example 3**
 
```ruby
module dff_const3(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b0;
		end
		else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule


```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_3.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_dff_const_3.png">

**Example 4**

```ruby
	module dff_const4(input clk, input reset, output reg q);
	reg q1;

	always @(posedge clk, posedge reset)
	begin
		if(reset)
		begin
			q <= 1'b1;
			q1 <= 1'b1;
		end
	else
		begin
			q1 <= 1'b1;
			q <= q1;
		end
	end
	endmodule

```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_4.png.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_dff_const_4.png">

**Example 5**

```ruby
	module dff_const5(input clk, input reset, output reg q);
	reg q1;
	always @(posedge clk, posedge reset)
		begin
			if(reset)
			begin
				q <= 1'b0;
				q1 <= 1'b0;
			end
		else
			begin
				q1 <= 1'b1;
				q <= q1;
			end
		end
	endmodule
```
Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_5.png">

synthesized circuit

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_dff_const_5.png">

</details>

<details>
	
 <summary>Sequential optimization of unused outputs</summary>

 **Example 1**
 ```ruby
	module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = count[0];
	always @(posedge clk ,posedge reset)
	begin
		if(reset)
			count <= 3'b000;
		else
			count <= count + 1;
	end
	endmodule
```
synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/counter_opt_rep.png">


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/sch_counter%20up_3_bit.png">

This is a 3 bit counter with output only LSB so instead of 3 d-flip flop only 1 is used

**Updated Counter**
```ruby
module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = {count[2:0]==3'b100};
	always @(posedge clk ,posedge reset)
	begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
	end
endmodule
```
synthesis

All the other blocks are for incrementing the counter but the output is from 3 input NOR gate

```ruby
module counter_opt (input clk , input reset , output q);
	reg [2:0] count;
	assign q = {count[2:0]==3'b100};
	always @(posedge clk ,posedge reset)
	begin
	if(reset)
		count <= 3'b000;
	else
		count <= count + 1;
	end
endmodule
```
synthesis

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/updated_counter_rep.png">


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/counter_%5B2%3A0%5D.png">

</details>

## Day 4 Gate level simulation(GLS), Blocking Vs Non Blocking and Synthesis Simulation mismatch

 <details>
 <summary>Gate level synthesis,blocking vs non blocking , Synthesis simulation mismatch</summary>

 **Gate level Synthesis** 
 Gate-level simulation is a crucial aspect of digital electronic design and verification. It plays a fundamental role in ensuring that digital circuits, such as integrated circuits (ICs) and field-programmable gate arrays (FPGAs), function correctly before they are manufactured or deployed in real-world applications. In this simulation method, the behavior of a digital circuit is modeled and analyzed at the gate level, which is the lowest level of abstraction in digital design. Let's explore the key aspects and importance of gate-level simulation in more detail.

 **1. Abstraction Level** : Gate-level simulation operates at a low level of abstraction, focusing on individual logic gates (e.g., AND, OR, NOT gates) and flip-flops. This level of detail allows for a precise analysis of the circuit's behavior, making it suitable for detecting timing issues, glitches, and other low-level problems.
 
 **2. Modeling Gates** : In gate-level simulation, the digital circuit is described using a hardware description language (HDL) such as VHDL or Verilog. Each gate in the circuit is modeled as an instance of a specific gate type, and their interconnections are defined.
 
 **3. Event-Driven Simulation** : Gate-level simulation typically uses an event-driven approach. It simulates the circuit's behavior in discrete time steps, where events like input changes trigger updates in the circuit's state. This allows for accurate modeling of combinatorial and sequential logic.
 
 **4. Timing Analysis** : Timing is critical in digital circuits, and gate-level simulation helps identify issues related to clock domains, setup time, hold time, and propagation delays. Timing violations can lead to incorrect operation or even circuit failure.
 
 **5. Verification** :Gate-level simulation is an essential step in the verification process for digital designs. Designers can verify that the circuit behaves as intended, meets the specified requirements, and produces the correct output for various input scenarios.
 
 **6. Debugging** : When discrepancies or errors are detected during gate-level simulation, designers can trace the problem to specific gates or connections, facilitating efficient debugging and correction of the design.
 
 **7. Power Analysis** :Power consumption is a critical concern in modern electronic devices. Gate-level simulation can estimate power consumption by analyzing the switching activity of gates, helping designers optimize for low power.
 
 **8. Scalability** : Gate-level simulation is scalable, allowing designers to simulate both small and complex digital circuits. However, larger designs may require substantial computational resources and simulation time.
 
 **9. Transition to Higher Abstraction Levels** : Once gate-level simulation verifies the correctness of the digital design, designers can progress to higher levels of abstraction, such as RTL (Register-Transfer Level) simulation, which focuses on functional behavior, or even higher levels like algorithmic modeling.
  In summary, gate-level simulation is a vital step in the digital design and verification process. It provides a detailed and accurate representation of digital circuits, enabling designers to identify and rectify issues related to functionality, timing, and power consumption before moving forward with the physical implementation of the design. This thorough validation process helps ensure the reliability and correctness of digital systems in various applications, from microprocessors to consumer electronics and beyond.

 
 
  **Why Gate level Synthesis (GLS)** 

 -Gate-level synthesis is an essential step in the process of designing digital integrated circuits (ICs) and field-programmable gate arrays (FPGAs). It involves translating a higher-level hardware description into a netlist of logic gates and flip-flops. Gate-level synthesis serves several important purposes in the digital design flow:

 **Translation of High-Level Descriptions** : Gate-level synthesis takes a high-level hardware description, typically written in a hardware description language (HDL) like VHDL or Verilog, and converts it into a netlist consisting of logic gates (AND, OR, NOT, etc.) and flip-flops. This transformation bridges the gap between the designer's abstract design intent and the low-level hardware description required for physical implementation.
 
 **Optimization** : During gate-level synthesis, the synthesis tool applies various optimizations to improve the design's performance, area, and power consumption. These optimizations can include logic simplification, technology mapping (selecting the best gates from a library), and resource sharing (using fewer gates to perform the same function). Optimization ensures that the resulting hardware is efficient and meets specified design constraints.
 
 **Technology Mapping** : Gate-level synthesis involves mapping the abstract design onto the target technology library. This step selects the most suitable gates and flip-flops from the library based on their electrical characteristics and the design's requirements. Different libraries may have varying gate delays, sizes, and power characteristics, so technology mapping is crucial for optimizing the design for a specific manufacturing process or FPGA technology.
 
 **Timing Analysis** : Gate-level synthesis tools perform detailed timing analysis to ensure that the synthesized design meets timing constraints. Timing constraints include clock-to-q delays for flip-flops, setup and hold times, and maximum operating frequencies. Timing closure ensures that the design can operate reliably at the desired clock frequency.
 
 **Area and Power Estimation** : Gate-level synthesis provides estimates of the design's area (the number of logic gates used) and power consumption. This information is essential for estimating chip size, power dissipation, and thermal considerations. It helps designers make informed decisions and trade-offs in terms of area, performance, and power consumption.
 
 **Verification and Debugging** : Once the design is synthesized into gates, designers can perform gate-level simulation and debugging to ensure that the synthesized logic functions correctly and matches the intended behavior described at higher levels of abstraction. This step helps identify and correct any synthesis-related issues.
 
 **Compatibility with Physical Design Tools** : The gate-level netlist generated during synthesis is used as input to physical design tools, such as place-and-route tools, which determine the physical layout of the IC or FPGA. A gate-level netlist is necessary for the physical design process, where the chip's physical components are placed on the silicon substrate and connected.
 
 **Support for Multiple Technologies** : Gate-level synthesis allows designers to target different manufacturing processes or FPGA families by changing the technology library used for mapping. This flexibility enables designers to adapt their designs to various application-specific requirements and constraints.
 
 In summary, gate-level synthesis is a critical step in the digital design flow that transforms abstract hardware descriptions into a form suitable for physical implementation. It plays a pivotal role in optimizing performance, area, and power consumption while ensuring that the design meets timing requirements and is ready for subsequent physical design and manufacturing processes.
 
 -To verify logic correctness of design after synthesis

 - If GLS is run with delay annotion then it can be used for timing analysis 

 - To identify errors that might occur due to signal progation delay.

 - As Design become more and more complex it becomes difficult to predict their behaviour accurately,GLS offers a comprehensive and a detailed view of circuit operation

 
 
 
 **Synthesis Simulation Mismatch** 

 Synthesis simulation mismatch refers to discrepancies or differences in behavior between a design simulation and the actual hardware implementation of a digital circuit after it has been synthesized. This phenomenon can occur for several reasons and can be a significant concern in digital design. Here are some common causes of synthesis simulation mismatch:

 **Abstraction Levels** : Simulation and synthesis operate at different levels of abstraction. High-level simulations, such as RTL (Register-Transfer Level) simulations, may not capture all the intricacies and details of the gate-level synthesis process. Differences in abstraction levels can lead to behavioral discrepancies.

 **Timing and Clock Domains** : Synthesis tools consider intricate timing details like clock-to-q delays, setup times, and hold times. If the simulation does not accurately model these aspects or if the constraints are not correctly defined, it can lead to timing issues and mismatch between simulation and synthesis.

 **Synthesis Optimizations** : Synthesis tools apply various optimizations to improve performance, area, and power. These optimizations may result in a different circuit structure than what was originally simulated. For instance, logic simplifications, resource sharing, and technology mapping can change the circuit's behavior.

 **Glitches and Race Conditions** : In gate-level simulation, glitches and race conditions may occur due to propagation delays and signal transitions. These issues may be less pronounced in higher-level simulations but can become significant at the gate level, leading to mismatched behavior.

 **Simulation Models** : Sometimes, the simulation models used in the design and verification phase may not precisely match the actual behavior of the synthesized gates and flip-flops. Differences in models can cause discrepancies.

 **Uninitialized or Don't-Care Values** : In simulation, signals are often initialized or set to don't-care values for convenience. In synthesis, however, these values may have specific behavior. Mismatch can occur if these differences are not accounted for.

 **Clock Domain Crossing Issues** : Asynchronous signals that cross clock domains can lead to synchronization problems. These issues might not be apparent in higher-level simulations but can cause problems after synthesis.

 **Undetected Constraints** : Constraints, such as clock and timing constraints, must be accurately defined and enforced during synthesis. If constraints are incorrectly specified or not enforced, it can lead to behavior mismatches.

 **Tool and Technology Variability** : Different synthesis tools and target technologies (FPGAs, ASICs, etc.) may produce variations in the final hardware implementation. Each tool and technology may have unique synthesis algorithms and libraries, leading to mismatches.

 **Simulation Setup** : Sometimes, simulation setups may not accurately reflect real-world operating conditions or constraints. Proper simulation setup is crucial for catching behavioral mismatches early.
   To address synthesis simulation mismatch, it is essential to:

 Ensure that the simulation models and simulation setup accurately reflect the behavior of the synthesized design.
 Carefully define and enforce constraints to capture timing and clock domain considerations.
 Perform gate-level simulations to verify the design's behavior after synthesis, helping to identify and rectify any mismatches.
 Use consistent libraries and technology settings throughout the design process.
 Cross-verify the design using different tools and technologies, if possible, to identify any tool-specific issues.
 Addressing synthesis simulation mismatch is critical for ensuring that the digital circuit behaves as intended in real hardware. Detecting and resolving these discrepancies early in the design process can save time and resources in the long run and help prevent costly post-silicon errors.
 
 Synthesis simulation mismatch denotes the disparities between the anticipated behavior of a circuit as simulated during design and its real-world performance after fabrication. This discrepancy is attributed to factors such as process variations, parasitic effects, and inaccuracies in simulation models. It's a critical concern to guarantee the functional alignment of the manufactured circuit with its intended design.

 Synthesis simulation mismatched are mainly caused because of the following reasons 

 - Missing sensitivity list
 - Blocking vs Non Blocking assignments
 - Non standard verilog code

 **Missing sensitivity list**
 The absence of a complete sensitivity list in VLSI design can give rise to problems. In hardware description languages (HDL) like Verilog, a sensitivity list is utilized to specify the inputs that should activate the execution of a specific process or code block. Inadequate or missing signals in the sensitivity list can lead to inaccurate or unforeseen behavior of the circuit during synthesis or simulation. Ensuring an accurate representation of inputs impacting the logic within a process is vital.

 As the synthesizer does not look for sensitivity list and it looks only statements in the procedural block , it infers correct circuit and if we simulate the netlist code , there will be synthesis simulation mismatch. In to order tackle this issue this issue it is important to check the behaviour of the circuit first and then match it with the expected output seen in the simulation. 

 **Blocking Vs Non Blocking Assignments**

 *Blocking statements*A blocking statement must be executed before the execution of the statements that follow it in a sequential block. In the example below the first time statement to get executed is a = b followed by


 Example of blocking assignment 
 ```ruby
 
	a = b;
	out_d = 0;
     {carry,sum} = in+sum_in
 
 ```
 Improper use of blocking assignments in the always block can lead to synthesis simulation mismatch 

 *Non Blocking statements* Nonblocking statements allow you to schedule assignments without blocking the procedural flow. You can use the nonblocking procedural statement whenever you want to make several register assignments within the same time step without regard to order or dependence upon each other. It means that nonblocking statements resemble actual hardware more than blocking assignments.

 Example of non blocking assignment 

 ```ruby

always @posedge(clk) begin
	a <= b;
	d <= c;
 end
 ```
Inside always block it is always a good practise to use non blocking assignment statements

Example of blocking and non blocking in delay format

```ruby
     module block_nonblock();
     reg a, b, c, d , e, f ;
  
   // Blocking assignments
   initial begin
   a = #10 1'b1;// The simulator assigns 1 to a at time 10
    b = #20 1'b0;// The simulator assigns 0 to b at time 30
     c = #40 1'b1;// The simulator assigns 1 to c at time 70
   end
  
  // Nonblocking assignments
  initial begin
    d <=  #10  1'b1;// The simulator assigns 1 to d at time 10
    e <=  #20  1'b0;// The simulator assigns 0 to e at time 20
    f  <=  #40  1'b1;// The simulator assigns 1 to f at time 40
  end
    
  endmodule

 ```
Blocking Assignment with synthesis output
```ruby
module blocking (clk,a,c);
input clk;
input a;
output c;
 
wire clk;
wire a;
reg c;
reg b;
  
always @ (posedge clk )
begin
 b = a;
 c = b;
end
   
endmodule
```
synthesis diagram
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/blocking.png">

Non Blocking Assignment with synthesis output
```ruby
module nonblocking (clk,a,c);
input clk;
input a;
output c;
 
wire clk;
wire a;
reg c;
reg b;
  
always @ (posedge clk )
begin
  b <= a;
  c <= b;
end
   
endmodule
 ```
Synthesis diagram
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/non_blocking.png">
 </details>




 <details>

 <summary>Labs on GLS (Simulation synthesis mismatch)</summary>
 
 **Example 1** 
 
 In this example there is no mismatch between the RTL Design simulated wave and Netlist simulated wave.
 ```ruby
module ternary_operator_mux (input i0 , input i1 , input sel , output y);
	assign y = sel?i1:i0;
endmodule
```
simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/waveform%20of%20%20ternary%20operator%20mux.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/sch_ternary_mux.png">

Netlist Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/gls_for%20ternary_wave.png">

In this we see that when select line is 0 , Output follows i0 and when select line is 1 output follows i1. This is same for both the simulations so there is no mismatch.

**Example 2**
Consider a example of mux.In this always block is triggered only when the select line is changed.
```ruby
module bad_mux (input i0 , input i1 , input sel , output reg y);
	always @ (sel)
	begin
		if(sel)
			y <= i1;
		else 
			y <= i0;
	end
endmodule
```
Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/waveform%20of%20bad%20mux.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/bad_sch.png">

Netlist Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/gls_for%20bad%20mux.png">

In this we can see that there is simulation synthesis mismatch , in the RTL design simulation we see that output is changing only when select line is changing but thats not the correct functionality of a mux , the output should change when either the input or select line is changed , this is reflected in the netlist simulation.

**Example 3**
Consider a example of mux.In this the always block is triggered when there is a change in either input or select line. 
```ruby
module good_mux (input i0 , input i1 , input sel , output reg y);
	always @ (*)
	begin
		if(sel)
			y <= i1;
		else 
			y <= i0;
	end
endmodule
```
Simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/waveform%20of%20good%20mux.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/sch_good_mux.png">

Netlist 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/gls_good_mux.png">

Here simulation output are same , i.e output changes when input or select line changes.

</details>

<details>

 <summary>Labs on synthesis simulation mismatch (Blocking statement)</summary>
 
 **Example 4** 
 Here the output depends on the past value of x which is dependent on a and b  and it appears like a imaginary flop.
 
 ```ruby
 module blocking_caveat (input a , input b , input  c, output reg d); 
reg x;
always @ (*)
	begin
	d = x & c;
	x = a | b;
end
endmodule
```

 Simulation
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/waveform%20of%20blocking%20caveat.png">

 Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/sch_blocking_ca.png"> 

Netlist simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/gls_for%20blocking.png"> 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day4/comb_ckt.jpg"> 

This a combinational circuit of or and and gate , in which the output of or gate is given as input to the and gate as shown in the figure , but in the RTL Design code blocking statements are used to define these operations in reverse direction(These statements are executed sequentially) so the and gate is getting input from the  previous output of or gate which acts as imaginary flop. As a result we are getting a different waveform in RTL design simulation , the correct waveform is  obtained  while doing netlist simulation. This causes Synthesis Simulation mismatch. This can be overcome by using non blocking assignment statements in the always block.  
</details>

# Day 6 Introduction to logic synthesis

 <details>
 <summary>Introduction</summary>
	 
 <ins> **Digital Circuit** </ins>
 
 Logic operations on binary data, which is represented as 0s and 1s, are carried out by a digital circuit, which is made up of electronic components. The basic building blocks of contemporary electronic gadgets like computers, smartphones, and digital appliances are these circuits. Because they are made to handle digital signals, digital circuits are particularly well suited for operations like data processing, storage, and transmission.

 Key components and concepts in digital circuits include:

 **Logic Gates** : Logic gates are the basic building blocks of digital circuits. They perform logical operations such as AND, OR, NOT, XOR, and others on binary inputs to produce binary outputs. Common logic gates include AND gates, OR gates, NAND gates, NOR gates, XOR gates, and NOT gates.

 **Flip-Flops** : Flip-flops are bistable multivibrators used to store a single binary bit of data. They are essential for creating memory elements in digital circuits, such as registers and memory cells.

 **Integrated Circuits (ICs)** : Integrated circuits are small semiconductor chips that contain multiple transistors and logic gates. They come in various forms, including microcontrollers, microprocessors, and application-specific ICs (ASICs). ICs are the heart of most digital devices and systems.

 **Combinational Logic** : Combinational logic circuits produce output based solely on the current inputs, without any memory of past inputs. Examples include adders, multiplexers, and decoders.

 **Sequential Logic** : Sequential logic circuits, unlike combinational circuits, have memory elements (usually flip-flops) that store information about past inputs. This allows them to perform tasks that involve sequencing or state-based operations, such as counters and shift registers.

 **Registers and Memory Units** : Registers are small, fast storage elements used to store temporary data within a digital circuit. Memory units, like RAM (Random Access Memory), provide larger storage capacity for data and program storage in computing systems.

 **Clock Signals** : Most digital circuits use clock signals to synchronize the timing of operations. Clock signals ensure that various parts of the circuit work together harmoniously, especially in sequential circuits.

 **Binary Representation** : Digital circuits operate on binary data, which is a system of representing information using two symbols: 0 and 1. Binary representation is the foundation of digital computation and information storage.

 Digital circuits are used in a wide range of applications, from basic logic gates used in simple consumer electronics to highly complex digital processors found in computers and other advanced technology. These circuits are known for their reliability, speed, and scalability, which makes them essential in modern technology.







 <ins> **Synthesis** </ins>

 As there is a rapid advancements in level of integration in VLSI design over few decades, EDA tools plays a vital role in the design, verification and debugging of larger digital circuits.EDA tools offer lot of opportunities to design variety of electronic chips containing the integrated circuits. To meet the functional and performance goals within a design time schedule and cost associated with it presents the scope for EDA tools.Synopsys Design Compiler (DC) is one such EDA tool used to perform the logic synthesis of complex digital circuits to produce fast and area efficient ASIC designs by incorporating the standard cell libraries and user defined gate arrays. Design compiler tool supports wide range of hierarchical and flat design styles and optimizes both combinational and sequential designs. It also explore design trade-offs involving design constraints such as timing, area, and power under various loading, temperature, and voltage
 conditions.
  Also, EDA tools are minimizing time in designing complex ICs, eliminating manufacturing errors, reducing
 manufacturing costs, optimizing the IC design and simplicity of usage. The better performance with good
 quality of results can be achieved by meeting the desired timing and area goals poses a challenge in the logic
 synthesis of hierarchical modular design using DC tool. Logic Synthesis is a process of converting a high-level description of the design into an optimized gate-level representation given a standard-cell library and design constraints. It is a highly automated procedure that bridges the gap between high-level synthesis and physical design automation. FEV method used for checking the logical
 equivalence between the RTL and netlist. It has become essential part of the design flow and has leveraged for later hand edit such Engineering Change Order (ECO). It is an exhaustive verification method that verifies design functionality completely without the use of test vectors.

 **LOGIC SYNTHESIS** : Logic Synthesis is a process of converting a high-level description of the design into an optimized gate-level representation given a standard-cell library and design constraints. The mathematical foundation of logic synthesis is the intersection of logic and algebra often known as Boolean algebra. It is a highly automated procedure that bridges the gap between high-level synthesis and physical design automation. 
  Logic Synthesis has wide scope in the design of digital systems whose synchronous behavior and implementation is
 focused most by the synthesis methodologies. The amount of design automation and logic synthesis efforts depends
 heavily on the market oriented decisions that influence the design styles chosen in implementing a product. Logic
 synthesis first translates the RTL description in verilog to components extracted from technology independent Generic
 TECHnology (GTECH) and DesignWare libraries. 
 Then, it optimized with suitable optimization rules and algorithms and mapped to technology dependent library
 cells. There are three levels of optimization can be performed in the synthesis process and are Architectural
 optimization, Logic level optimization and Gate level optimizations 
 
 **Architectural Optimization** : Optimization at the architectural level works on the HDL description and includes high level synthesis tasks
 such as sharing common sub expressions, resources, selecting DesignWare implementations, reordering
 operators and identifying arithmetic expressions for data path synthesis. High level synthesis tasks occurs only during
 the optimization of an unmapped design and are based on user defined constraints and coding style.

 **Logic Level Optimization** : Logic level optimization works on the GTECH netlist and has two processes: Structuring and Flattening. Structuring process is constraint based and is best applied to
 non critical timing paths. It basically adds intermediate variables and logic structures to a design which results in
 smaller area. Flattening process aim is to convert combinational logic paths of the design to a to level, Sum of
 Product representation. It is independent of constraints and
 suitable for speed optimization.

 **Gate level Optimization** : Optimization at gate level works on the generic netlist created by the logic synthesis to produce technology specific netlist. It involves mapping, delay optimization and
 design rule fixing processes. The mapping process uses gates from target technology libraries to generate a gate
 level implementation of the design to meet timing and area requirements. Delay optimization goal is to fix violations
 introduces in the mapping phase due to delay. Design rule fixing used to correct design rule violations by inserting
 buffers or resizing existing cells. 

 **Compilation Techniques** : The RTL design can be compiled in two ways in the synthesis process and are Top Down compile and Bottom
 Up compile. In the top down approach, top level model and all its sub modules are compiled together. The advantage of
 using this method is that it provides push button approach and takes care of interblock dependencies. Top down
 approach can be used for a design that does not include memories.
 Top level design having memory blocks can be replaced by interface models and then it can be compiled using this
 method. The memory requirements for the instantiation of sub-designs can be greatly reduced by replacing memories
 with interface modules. In the Bottom Up approach, the large designs are compiled using divide and conquer method
 and require less memory as compared to Top - Down compile. 
 The constraints are applied to sub-designs individually, and then they are compiled separately and included in top
 level design. The sub designs are characterized based worst violations, characterize captures timing and environment
 information of each cell referenced in the design

 <ins> **.lib file** </ins>
 Lib file is a short form of Liberty Timing file. Liberty syntax is followed to write a .lib file. LIB file is an ASCII representation of timing and power parameter associated with cells inside the standard cell library of a particular technology node. Lib file is basically a timing model file which contains cell delay, cell transition time, setup and hold time requirement of the cell. So Lib file basically contains the timing and electrical characteristics of a cell or macros. Lib file is generated and provided to ASIC designer by a standard cell library vendor or Foundry if the foundry provides a standard cell library. 
 The information inside the Lib file can be divided into two main parts, in the first part, it contains some information which is common for all the standard cells. To understand it better have a look in the following snapshot of the Lib file.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/lib_file_comman1.png">
 
 The common part of Lib file contains
 1. Library name and technology name
 2. Units (of time, power, voltage, current, resistance and capacitance)
 3. Value of operating condition ( process, voltage and temperature) Max, Min and Typical

 Based on operating conditions there are three different lib files for Max, Min and Typical corners. In the second part of Lib file, it contains cell-specific information for each cell. The part of Lib file which contains cell-specific information is shown below.
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/Lib_cell_part2.png">

 
 Cell-specific information in Lib file is mainly

 1. Cell name
 2. PG Pin name
 3. Area of cell
 4. Leakage power in respect of input pins logic state
 5. Pins details
    5.1 Pin name
    5.2 Pin direction
    5.3 Internal power
    5.4 Capacitance
    5.5 Raise capacitance
    5.6 Fall Capacitance
    5.7 Fanout load

 A snapshot of Lib file for the pin part is given below
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/Lib_pin%20part3.png">

 Timing and power parameter of a cell is obtained by simulating the cell in a variety of operating conditions and data are represented in the Lib file. There are two main techniques to characterize a cell and generated the Lib file.
 CCS (Composite Current Source)
 NLDM (Non-Linear Delay Model)
 In CCS technique current source is used whereas in NLDM technique voltage source is used to model and derive the Lib parameters. Based on CCS and NLDM technique used for characterizing the cell, we call the corresponding Lib file is CCS Lib file and NLDM Lib file. Since CCS technique is having more controlling parameters as compare to NLDM technique, So CCS Lib file is more accurate. NLDM Lib file has lesser run time mean fast run compare to CCS Lib and also the size of the NLDM file is lesser than that of CCS Lib file.

 <ins> **Constraints** </ins>

 In VLSI design, constraints are essential parameters and limitations that guide the development process to ensure that the resulting integrated circuits (ICs) meet specific performance, timing, and functionality requirements. These constraints play a crucial role in achieving a successful VLSI design.


 </details>

 <details>

 <summary>DC Compiler</summary>

 **Design Compiler** , often abbreviated as DC, is a high-level synthesis tool developed by Synopsys, a leading provider of EDA solutions. It plays a pivotal role in the process of designing complex integrated circuits (ICs) and is an integral part of modern VLSI design flows.

 Important terms used 
 - **Synopsys Design Constraints(SDC)** : These are the design constraints which are supplied to DC to enable appropriate optimization suitable for achieving the best implementation.
 - **.lib** : Design Library which contains the Standard cells.
 - **.db** : Same as .lib but in a different format. DC understands libraries in .db format
 - **.ddc** : Synopsys propreitary format for storing the design information. DC can write out and read in DDC.
 - **Design** : RTL files which has the behavioral model of the design.

 <ins> **DC synthesis flow** </ins>

 ```ruby
		Read STD Cell/tech.lib
			 ↓
		Read Design (Verilog and Design.lib)
			 ↓
		Read SDC
			 ↓
		Link the Design
			 ↓
		Synthesize
			 ↓
		Generate Report and analyse QoR
			 ↓
		Write out the Netlist
  ```
 The DC compiler does not understand .lib , so the .lib is converted to .db format. lib format is for user reference.

 <ins>**Labs on DC Compiler**</ins>

 **Invoking DC compiler**
 First we need to enable C shell and then invoke dC shell with the commands shown below

 ```ruby
 >> csh
  >> dc_shell
 ```
 Then we echo target library and link_library which returns an imaginary pointer library namely your library, which needs to be set.
 ```ruby
 >>>echo $target_library
 >>>echo $link_library
 ```
 Consider a example of a Mux connected to D Flip flop as ahown in the figure as follows

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/first.png">

 The RTL design code is 
 ```ruby
 module lab1_flop_with_en ( input res , input clk , input d , input en , output reg q);
 always @ (posedge clk , posedge res)
 begin
	if(res)
		q <= 1'b0;
	else if(en)
		q <= d;	
 end
 endmodule
 ```
 Synthesis of this design code can be done using the following commands
 ```ruby
 read_verilog <path of design file>
 read_db <path of .db>
 write -f verilog -out <net_filename>
 ```
 
 This generates the netlist file but it consists of some seqgen library as shown in the figure and not the .db file even though we have read the .db file, This is beacuse we didn't set link and target library,

 

 To set the link_library and target_library we use the following commands
 ```ruby
 set target_library <path of .db>
 set link_library { * path of the .db }
 link
 compile
 write -f verilog -out <net_filename>
 ```
 After compiling the we get the output as shown in the figure

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/lab1_flop.png">

 The generated netlist

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/lab1_with_sky130.png">


 **Labs on Design Vision**

 Design Vision is a widely used Electronic Design Automation (EDA) tool in the field of VLSI. It is developed by Synopsys and is primarily used for logic synthesis, formal verification, and other essential tasks in the VLSI design flow.

 To launch Design Vision we need to enable c shell and then give design Vision
 ```ruby
 csh
 design_vision
 ```
 After launching the design_vison first we need to the net to .ddc which is read by Design_vision tool which can be done by using the below command
 ```ruby
  write -f ddc -out <filename_name>
 ```
 Then we can start GUI and then read the .ddc file generated above. This ddc file contains all the information of the tool memory of that particular session. ddc is synopys proprietary format i.e it can be read only br synopsys tools.When the .db is read it automatically reads the linked .db file as shown in the below figure. 

 If we want to see the gate level implementation then we need to double click the module.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/sch_lab1_ddc.png">

 **Lab on .synopsys_dc.setup**

 Consider a case where there are multiple .db files used and we cannot skip any of them , then it is nearly impossible to indvidually set all the .db files. In order to resolve this we can create a file namely *.synopsys_dc.setup* file in home diresctory of workspace.

 When dc_shell is invoked, the shell looks the .synopsys_dc.setup file in user_home_directory. The order of priority is, if file exists in user_home_directory then that will be picked and the installed (default) is ignored. If not found, then installed one is picked. All repetitive tasks which are needed for tool setup can be pointed in this file. So when the dc_shell is invoked all the .dbs are set automatically
 
 The .synopys_dc.setup file for the above example of mux and d flip flop is as follows

 ```ruby
 set target_library /home/pavday.s/DC_WORKSHOP/lib/sky130_fd_sc_hd_tt_025c_1v80.db
 set link_library {* $target_library }
 ```

 </details>

 <details>

 <summary>Tcl scripting</summary>
 Tcl, short for "Tool Command Language," is a dynamic and interpreted scripting language that was created to serve as a simple and efficient scripting tool. Tcl is known for its ease of use, flexibility, and extensibility, making it widely adopted in various domains.
 
 This is widely used language in VLSI

 Basic Tcl Commands

 Assigning a variable
  ```ruby
 set a 10
 ser b 10
 set a [expr $a + $b]
 ```

 if else condition

 ```ruby
 if { condition } {
 <statements>
 } else {
 <statements>
 }
 ```
 while loop

 ```ruby
 while {<condition>} {
 /statements
 }
 ```
 For loop

 ```ruby
 for {<looping variable>} {condition} {incr/decr} {
 /statements
 }

 ```
 For each 

 ```ruby
 foreach var list{
 statement
 }
 ```

 For each in the case of collection

 ```ruby
 foreach_in_collection var collection {
 statement
 }
 ```

 Labs on TCL

 Example 1 on assigning the variable and for loop

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/tcl1_while.png">

 Example 2 on while loop

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/while_expr_1.png">

 Example 3 is tool specific it returns the collection of all the standard cells containing and in the .lib file, it is done using

 ```ruby
 get_lib_cells */*and*
 ```
 when we try to print this collection we get _sel3 which is basically a pointer address. Collection is basically the collection of pointers

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/sel_line.png">

 To get the cell name we need to use the command as used in the below screenshot

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/int1">

 These codes can be written in tickle file

 Consider a example 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/script.png">


 output

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/cell_script.png">

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day6/day6/printing_mul1.png">



 </details>


# Day 7 Basics of STA

 <details>
	 
 <summary>Introduction to STA(Static Timing Analysis)</summary>

 **Static Timing Analysis** 
 Static timing analysis (STA) is a method of validating the timing performance of a design by checking all possible paths for timing violations. STA breaks a design down into timing paths, calculates the signal propagation delay along each path, and checks for violations of timing constraints inside the design and at the input/output interface.
  Another way to perform timing analysis is to use dynamic simulation, which determines the full behavior of the circuit for a given set of input stimulus vectors. Compared to dynamic simulation, static timing analysis is much faster because it is not necessary to simulate the logical operation of the circuit. STA is also more thorough because it checks all timing paths, not just the logical conditions that are sensitized by a set of test vectors. However, STA can only check the timing, not the functionality, of a circuit design.

  **How does STA work?**

  When performing timing analysis, STA first breaks down the design into timing paths. Each timing path consists of the following elements:

 *Startpoint* . The start of a timing path where data is launched by a clock edge or where the data must be available at a specific time. Every startpoint must be either an input port or a register clock pin.
 *Combinational logic network*. Elements that have no memory or internal state. Combinational logic can contain  AND, OR, XOR, and inverter elements, but cannot contain flip-flops, latches, registers, or RAM.
 *Endpoint* . The end of a timing path where data is captured by a clock edge or where the data must be available at a specific time. Every endpoint must be either a register data input pin or an output port.
 The following figure shows the timing paths in a simple design example:

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sta_path.JPG">

 in this example, each logic cloud represents a combinational logic network each path start at a data launch point,passes through some combinational logic, and ends at  a data capture point.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sta%20path%201.JPG">

 A combinational logic cloud might contain multiple paths, as shown in the following figure. STA uses the longest path to calculate a maximum delay and the shortest path to calculate a minimum delay.


 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sta_3.JPG">
 

 STA also considers the following types of paths for timing analysis:

 *Clock path*. A path from a clock input port or cell pin, through one or more buffers or inverters, to the clock pin of a sequential element; for data setup and hold checks.
 *Clock-gating path*. A path from an input port to a clock-gating element; for clock-gating setup and hold checks.
 *Asynchronous path*. A path from an input port to an asynchronous set or clear pin of a sequential element; for recovery and removal checks.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sta_4.JPG">
 

 After breaking down a design into a set of timing paths, an STA tool calculates the delay along each path. The total delay of a path is the sum of all cell and net delays in the path.

 Cell delay is the amount of delay from input to output of a logic gate in a path. In the absence of back-annotated delay information from an SDF file, the tool calculates the cell delay from delay tables provided in the logic library for the cell.

 Typically, a delay table lists the amount of delay as a function of one or more variables, such as input transition time and output load capacitance. From these table entries, the tool calculates each cell delay.

 Net delay is the amount of delay from the output of a cell to the input of the next cell in a timing path. This delay is caused by the parasitic capacitance of the interconnection between the two cells, combined with net resistance and the limited drive strength of the cell driving the net.

 STA then checks for violations of timing constraints, such as setup and hold constraints:

 A setup constraint specifies how much time is necessary for data to be available at the input of a sequential device before the clock edge that captures the data in the device. This constraint enforces a maximum delay on the data path relative to the clock edge.
 A hold constraint specifies how much time is necessary for data to be stable at the input of a sequential device after the clock edge that captures the data in the device. This constraint enforces a minimum delay on the data path relative to the clock edge.

 The following example shows how STA checks setup and hold constraints for a flip-flop:


 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sta_5.JPG">


 For this example, assume that the flip-flops are defined in the logic library to have a minimum setup time of 1.0 time units and a minimum hold time of 0.0 time units. The clock period is defined in the tool to be 10 time units. The time unit size, such as ns or ps, is specified in the logic library.

 By default, the tool assumes that signals are propagated through each data path in one clock cycle. Therefore, when the tool performs a setup check, it verifies that the data launched from FF1 reaches FF2 within one clock cycle, and arrives at least 1.0 time unit before the data gets captured by the next clock edge at FF2. If the data path delay is too long, it is reported as a timing violation. For this setup check, the tool considers the longest possible delay along the data path and the shortest possible delay along the clock path between FF1 and FF2.

 When the tool performs a hold check, it verifies that the data launched from FF1 reaches FF2 no sooner than the capture clock edge for the previous clock cycle. This check ensures that the data already existing at the input of FF2 remains stable long enough after the clock edge that captures data for the previous cycle. For this hold check, the tool considers the shortest possible delay along the data path and the longest possible delay along the clock path between FF1 and FF2. A hold violation can occur if the clock path has a long delay.

 If certain paths are not intended to operate according to the default setup and hold behavior assumed by the STA tool, you need to specify those paths as timing exceptions. Otherwise, the tool might incorrectly report those paths as having timing violations.

 An STA tool may let you specify the following types of exceptions:

 *False path*. A path that is never sensitized due to the logic configuration, expected data sequence, or operating mode.
 *Multicycle path*. A path designed to take more than one clock cycle from launch to capture.
 *Minimum or maximum delay path*. A path that must meet a delay constraint that you explicitly specify as a time value.

 **Delay** 

 Delay refers to the time it takes for a signal to propagate from one point in a digital circuit to another. Delay is a critical parameter in design because it affects the performance, power consumption, and reliability of the integrated circuit.

 A *Max Delay Constraint* refers to a design specification or requirement that imposes an upper limit on the delay a signal can experience while propagating through a specific path or circuit within an integrated circuit. Consider a example of 2 D flip flop connected with a combinational logic in between them.
 
 Tck >= Tcq + Tcomb + Tst

 "Min Delay constraint" refers to a design specification or requirement that sets a minimum allowable delay for a signal to propagate through a specific path or circuit within an integrated circuit. This constraint is used to ensure that certain signals within the circuit do not propagate too quickly, which can lead to timing violations and potential operational issues.
 
 Thold < Tcq + Tcomb

 Delay can well understood with the water bucket analogy , consider a case in which 2 buckets of 5 gallon each are being filled using the inflow of water from 2 separate pipes whose inflows are 1 gallon per minute and 5 gallon per minute respectively. The time taken by the bucket 1 to fill from 20 % to 80% is 3 min and for the other one it is 0.6 min. This case can be corelatted in VLSI as follows.

 Inflow water => Inflow of current
 
 Pipe 1 with higher inflow => less trasnsition delay
 
 Pipe 2 with lower inflow  => high transition delay

 The size of the bucket also matters , which can be correlated with the load capacitance.

 Delay of the cell is a function of **input transition** and **load capacitance**

 **Timing Arc**

  A timing arc defines the propagation of signals through logic gates/nets and defines a timing relationship between two related pins. Timing arc is one of the components of a timing path. Static timing analysis works on the concept of timing paths. Each path starts from either primary input or a register and ends at a primary output or a register. In-between, the path traverses through what are known as timing arcs. We can define a timing arc as an indivisible path/constraint from one pin to another that tells EDA tool to consider the path/relationship between the pins. For instance, AND, NAND, NOT, full adder cell etc. gates have arcs from each input pin to each output pin. Also, sequential cells such as flops and latches have arcs from clock pin to output pins and data pins


 <img  width="1085" alt="" src=" https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/timing%20arc.JPG">

 **Terminology** : The common terminology related to timing arcs is as follows:
 *Source pin*: The pin from which timing arc originates (pin IN1 and IN2 for cell arcs, pin OUT for net arc in figure1). This also means constraining pin in case of setup/hold timing checks (for example clock is source pin for setup check)
 *Sink pin*: The pin at which timing arc ends (pin OUT for cell arc, pin AND2/IN2 for net arc in figure2). This also means constrained pin in case of setup/hold timing arcs (for example data pin is sink pin for setup check)


 **Cell arcs and net arcs**: Timing arcs can be categorized into two categories based upon the type of element they are associated with – cell arcs and net arcs.
 *Cell arcs*: These are between an input pin and output pin of a cell. In other words, source pin is an input pin of a cell and sink pin a pin of the same cell (output pin in case of delay arcs and input pin in case of timing check arcs). In the figure shown above, arcs (IN1 -> OUT) and (IN2 -> OUT) are cell arcs. Cell arcs are further divided into sequential and combinational arcs as discussed below.
 *Net arcs*: These arcs are between driver pin of a net and load pin of a net. In other words, source pin is an output pin of one cell and sink pin is an input pin of another cell. In the figure shown above, arc (OUT -> IN2) is a net arc. Net arcs are always delay timing arcs.
 
 **Timing sense of an arc**: Timing sense of an arc is defined as the sense of traversal from source pin of the timing arc to the sink pin of the timing arc. Timing sense is also called as "unateness" of timing arc. Timing sense can be ‘positive unate’, ‘negative unate’ and ‘non-unate’.
 *Positive unate timing arc*: The unateness of an arc is said to be positive unate if rise transition at the source pin causes rise transition (if at all) at sink pin and vice-versa.  Cells of type AND, OR gate etc. have positive unate arcs. All net arcs are positive unate arcs.
 *Negative unate timing arc*: The unateness of an arc is said to be negative unate if rise transition at the source pin causes fall transition at the sink pin and vice-versa. NAND, NOR and Inverter have negative unate arcs.
 *Non unate timing arcs*: If there is no such relationship between the source and sink pins of a timing arc, the arc is said to be non-unate. XOR and XNOR gates have non-unate timing arcs.


 **From what source timing arcs are picked**: For cell arcs, the existence of a timing arc is picked from liberty files. The cell has a function defined that identifies if the arc is there from its input (say ‘x’) to output (say ‘y’). In most of the cases, the value (delay, unateness, sd condition etc) of the arc is also picked from liberty; but in case you have read SDF, the delay is picked from SDF (Standard Delay Format) file (other properties picked from liberty in this case also). On the other hand, for net arcs, the existence of arc is picked from connectivity information (netlist). The net arcs are calculated based on the parasitic values given in SPEF (Standard Parasitics Exchange Format) file, or SDF (like in case above).

 **Importance of timing arcs**: Timing arcs have a very important role in VLSI design industry. Whole of the optimization process right from gate level netlist till final signoff revolves around timing arcs. The presence of correct timing arcs in liberty file is very essential for high quality signoff or there may not be correlation between simulation and silicon).


 *Combinational Sequential Cells Timing arcs* 
 cell arcs can be sequential or combinational. Sequential arcs are between the clock pin of a sequential cell and either input or output pin. Setup and hold arcs are between input data pin and clock pin and are termed as timing check arcs as they constrain a form of timing relationship between a set of signals. Sequential delay arc is between clock pin and output pin of sequential elements. An example of sequential delay arc is clk to q delay arc in a flip-flop.  On the other hand, combinational arcs are between an input data and output data pin of a combinational cell or block. 


  **Constraints** 

 In VLSI (Very Large Scale Integration) design, **constraints** are specifications and limitations applied to various aspects of the design process to ensure that the resulting integrated circuit meets its intended requirements and performs as expected. These constraints play a crucial role in guiding the design and verification of VLSI circuits.

 Why constraints ?

 Consider a circuit as shown in the figure

 ![image](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/pqrst.png)


 Here if the setup time for all the components is 0.5 ns and and propagation delay of the selected gates are 0.5 ns and 0.7 ns for not and and gate respectively.

 Tck for path from 1st flop is 2.2 ns 

 Tck for path from 2nd clk is 1.7 ns

 The max delay is 2.2 ns which is called the critical path as it detemines the clock frequeny

 In practical cases we set the working frequency and then calculate the required propogation delay. In this example if the Tck path from the 1st flop setup time and clock to q delay is almost fixed 0.5 ns if we need to make this work at clock frequency of 200 MHz i.e 2 ns which implies the and gate propogation delay should be 1 ns . so who will tell the tool to pick the and gate with proper propagtion delay of 1 ns instead of 1.2 ns . So for this we need constraints

 **Timing paths** in VLSI  design are specific routes or signal paths within a digital circuit where the timing characteristics, including signal propagation delays, setup times, hold times, and clock-to-q delays, are analyzed to ensure the circuit's correct and reliable operation. These paths are crucial for timing analysis and play a central role in achieving the desired performance and functionality of the integrated circuit. Timing paths typically include a starting point (often a flip-flop or input pin), a set of logic gates and interconnections, and an ending point (another flip-flop or output pin). 

 Start points of timing path

 - Input ports
 - Clock pins of regs

 End point of timing path

 - Output ports
 - D pin of D flip flop / D Latch


 Always the timing path start at one of the start point and ends at one of the end point

 Clock -> D (Reg 2 Reg)

 Clock  -> Output port (I/O timing path)

 input port -> D (I/O timing path)

 input port -> Output port (These should not be present)


 Consider the circuit 

 ![image](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/asdfg.png)


 - In this Reg 2 Reg is constrained by clock
  
 - Reg to out is constrained by Output external delay , load and clock . 

 - In 2 Reg is constrained by input external delay ,clock, input transition.
 
 In addition to this Input transition delays are also constrained as signal transition are not ideal . As we know that delays are function of input transition and load capacitance they both need to be constrained.


 </details>

 <details>

 <summary> Labs </summary>

 Timing File (.lib) consists of ASCII representations of Timing, Area, and Power associated with the Standard cell. The Naming convention in the timing file follows PVT format (Process, Voltage, Temperature). For example, the standard library used in our case was sky130_fd_sc_hd_tt_025C_1v8, this name suggests that we are using 130 nm technology and the process is typical, temperature is 25C, and 1.8 V represents the voltage.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/lib_with%20pvt">

 The timing File also consists of the technology used for standard cells as in the above example it is CMOS, it also specifies the delay model, unit of time, unit of voltage, unit of resistance, and many other units.

  This also includes different different flavours of the same logic gates.

 .lib also contains leakage power , area , timing sense of each different flavours of gate cells.

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/delay_model_lookup_table">

 A Look-Up Table (LUT) in a Liberty file is a component that defines the logical behavior and timing characteristics of a combinational logic cell within a digital library. Liberty files are used in the electronic design automation (EDA) industry to represent libraries of standard cells that can be used in VLSI (Very Large Scale Integration) design.

 index1 represents input transition , index2 represeents output load capacitance

 example of and2_1 gate index table

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/e731f71ac7b93042821dee66ad994eae01ef8d6f/day7/and2_index.png">

 A Boolean function is considered "unate" if it satisfies the unateness property, which relates to the behavior of the function with respect to the input variables. Unate functions are important in logic optimization and simplification processes, such as those used in logic synthesis and minimization.

 There are two main types of unateness:

 Positive Unate Function: A Boolean function is considered positive unate with respect to a particular input variable if, for any assignment of values to the other input variables, the function either remains constant or increases as the specified input variable transitions from 0 to 1. In other words, the function depends only on the positive (1) values of that input variable.

 Negative Unate Function: A Boolean function is considered negative unate with respect to a particular input variable if, for any assignment of values to the other input variables, the function either remains constant or decreases as the specified input variable transitions from 0 to 1. In this case, the function depends only on the negative (0) values of that input variable.

 And gate is an example of positive Unateness

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/commit/e410ab3cfe36125c72503c2676bb9feba040148b">

 Comparing 2 differnt flavour of and gates namely and2_1 and and2_2 , we see that area of and2_2 > and2_1

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/connection_p_n_well">

 Sequential flops have clock pin as true

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/delay_model_area">

 Unnateness of D flip flop negative edge triggered

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/sdf_unnate_clk.png">

 Unateness of D latch positive edge triggered 

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/latch_ri_fl">

 **lab on .lib in dc_compiler** 

 example 1 : to print all the sequential gates 

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/dlrt_cell">

 example 2 : prints the library linked

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/colletionof%20pin">

 example 3: Prints the list of cells from the collection

 <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/azx.png">

 example 4: prints the pins associated with the gate cell and functionality of a particular gate

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/ing4.png">

 example 5: prints the pins along with the direction of and2_0 gate 

 <img  width="1085" alt="lib_dir_and" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/ing3.png">

 example 6: prints the pins along with the direction of nand4b_1 gate 

 <img  width="1085" alt="nand4b_1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/ing2.png">

 it also prints the boolean expression i.e function of that cell

 example 7: prints the pins along with the direction of and4bb_2 gate 

 <img  width="1085" alt="and4bb_1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/ing1.png">

 it also prints the boolean expression i.e function of that cell

  example 8: A tcl program which takes the list of cells as input and prints the output pins along with its functionality

 ```ruby
  set mylist [list sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_1 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_2 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_4 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2_8 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_1 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_2 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand2b_4 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_1 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_2 \
 sky130_fd_sc_hd__tt_025C_1v80/sky130_fd_sc_hd__nand3_4 ];

 foreach var $mylist {
  foreach_in_collection var_pins [get_lib_pins ${var}/* ] {
      set pin_name [get_object_name $var_pins];
      set pin_dir [get_lib_attribute $pin_name direction];
      if { $pin_dir == 2 } {


          set pin_func [get_lib_attribute $pin_name function];

          echo $pin_name $pin_dir $pin_func ;
       }
    }
 } 
```
 <img  width="1085" alt="tclpgm1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/dc_tcl_pgm1.png">

 example 9: Prints the attributes of the cell/pin

 <img  width="1085" alt="pinattri" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/dc_attri2.png">

 <img  width="1085" alt="pinattri1" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/day_7/attribute">


 </details>


# Day 9 Optimizations

 <details>
	 
 <summary>Introduction to Combinational and Sequential Optimization</summary>


 Optimization in VLSI design is a crucial aspect of creating efficient and high-performance integrated circuits (ICs). VLSI optimization involves improving various aspects of IC design, such as power consumption, area utilization, timing, and manufacturability.


 The goals of optimization :

   - Cost based Optimization
     
     	- Optimization till cost is met
     	- Over optimization of one goal can harm other goals.

   - Performance Optimization:

       - Speed: Improve the operational speed of the IC by minimizing delays, optimizing critical paths, and ensuring that the design meets specified timing requirements.
       - Throughput: Enhance the overall system throughput by optimizing data flow and minimizing bottlenecks in the circuit.

   - Power Optimization:

        - Dynamic Power: Minimize dynamic power consumption to extend battery life in portable devices and reduce power dissipation in data centers.
        - Static Power: Reduce static power (leakage power) to lower overall power consumption when the IC is in standby or idle mode.

 **Types of Optimisation**

 *Layout Optimization*:
 Layout optimization is a critical aspect of physical design. It involves placing and routing the transistors in a way that minimizes the distance between them and maximizes the speed of the signal flow. A well-optimized layout can significantly reduce power consumption and increase the circuit’s speed.

 *Clock Tree Synthesis*:
 The clock signal is used to synchronize the operation of the VLSI circuit. It involves distributing the clock signal across the chip, which ensures that all the circuits receive the signal at the same time. This optimization technique can significantly reduce the clock skew and improve the circuit’s performance.

 *Power Optimization*:
 Power optimization is a crucial factor in VLSI design. Excessive power consumption can lead to overheating, which can damage the circuit. Power optimization techniques such as voltage scaling and clock gating can reduce the circuit’s power consumption without affecting its performance.

 *Signal Integrity*:
 Signal integrity is the measure of the signal’s quality as it propagates through the circuit. Any noise or distortion in the signal can affect the circuit’s performance. Signal integrity optimization techniques such as power supply noise reduction and signal shielding can improve the signal quality and increase the circuit’s reliability.

 *Thermal Optimization*:
 VLSI circuits generate a lot of heat, and excessive heat can affect their performance and reliability. Thermal optimization techniques such as thermal vias, thermal pads, and heat sinks can efficiently dissipate the heat generated by the circuit and improve its reliability.

 
   - Goals for Synthesis
          
     	- Meet Timing
     	
     	- Meet Area
     	
     	- Meet power

 **Combination logic Optimisation**

 **Combinational Logic Optimization** A combinational circuit is one for which the output value is determined solely by the values of the inputs. Such a circuit can be represented by a truth table and computes a Boolean function. The design of an optimized logic circuit that
 implements a desired Boolean function is of interest.
    Karnaugh map and Quine-Mc Cluskey method are the popular traditional gate minimization techniques. Karnaugh maps are useful in minimization of circuits only up to six variables and according to Qunie-Mc Cluskey is not very time efficient. 
 The design of an optimized logic circuit that implements a desired Boolean function is of interest. Optimization can be performed in terms of different objectives. They include optimizing the number of gates, the number of levels, the number of transistors of the circuit.
 squeeze the logic to get most optimized design in terms of area and power. There are various techniques for optimizing the circuit
 
 - constant propagation(Direct propagation)
 - Boolean Logic Optimization(K-Means ,QUine Mckluskey)
   
 **Constant Propogation** is an optimization technique used by  synthesis tools to minimize hardware implementation.Constant propagation prevents situations in which values are copied from one place or variable to another only to assign their value to a different variable.

 **Example on Constant Propogation** 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.51.23.jpeg">

 Consider the above  combinational circuit it consists of and and nor gate, so it requires 6 CMOS transistor to implement , if A is made constant value 0 then A&B will give 0 then 0 and C are given to NOR gate which reduces the expression to C compliment(C`) i.e basically a inverter . By making an input constant we can reduce this combinational circuit to an inverter which can impleneted using only 2 CMOS transistor thus reducing the hardware implementation

 **Example on Boolean Logic optimization**

consider a concurrent statement a?(b?c:(c?a:0)):(!c) , this statement is realized using multiple multiplexers. Simplying this equation using boolean reduction techniques we get the output as ~(a^b).

**Resource Sharing**

Resource sharing in VLSI design refers to the practice of efficiently utilizing hardware resources, such as logic gates, memory elements, or functional units, to reduce the overall area, power consumption, and complexity of an integrated circuit (IC). Resource sharing is a fundamental technique in VLSI design and is often employed to optimize the use of limited resources while maintaining or improving the desired functionality.

Consider a example , y = sel ? (a*b) : (c*d) 

The schematic of the above expression is as shown in the figure

![WhatsApp Image 2023-09-13 at 21 54 49](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.47.44.jpeg)

We see that in order to implement this we need two multipliers which consume a lot of area, So instead of using 2 multipliersnwe can reduce to one multiplier and use 2 MUX as shown in the figure

![WhatsApp Image 2023-09-13 at 21 55 36](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.47.30.jpeg)

**Logic Sharing**

Logic sharing in VLSI design refers to the practice of reusing or sharing logical elements, such as gates or functional blocks, to reduce the overall complexity, area, and power consumption of an integrated circuit (IC). This technique is commonly used to optimize chip designs while ensuring that the desired functionality is maintained.

Consider 2 equations

y = a & b & c

z = (a & b) | c

Here a & b is a common logic between y and z , so we can use the same logic for both the cases

![WhatsApp Image 2023-09-13 at 22 55 36](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.31.48.jpeg)

**Preferential vs Balanced implementation**

consider the below equation

y = a & b & c & d & e

this can be implemented in 2 ways as shown in the figure ,

![WhatsApp Image 2023-09-13 at 23 03 01](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.34.26.jpeg)

In the first case input to y delay is same for all 5 variables so this is a case of Balanced implementation.

In the second case input to y delay is different for the variable , this is case of sequential implementation

Out of this which one is selected is decided by the *constraints*

**Sequential Optimization**

Basic Sequential Optimization

- Sequential Constant propagation
- Retiming
- Unused Flop Removal
- Clock Gating

  	

Advanced

- State Optimization
- Sequential logic cloning

Consider a case where asynchronous reset D Flip-flop is fed with d = 0(i.e GND) always so the output will always be 0 irrespective of the timing or circuit.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2020.38.22.jpeg">

**Optimization of Unloaded Outputs**

Optimizing unloaded outputs typically involves reduction of power consumption , area, delay for unused or idle pins . It refers to flip-flops whose outputs are not connected to any subsequent logic gates or do not affect the functionality of the overall circuit. so these flip flops can be removed thus retaining the function and reducing the area , power of the design.

**Controlling sequential optimization**

- compile_seqmap_propagate_constants If this variable is not set to true, the sequential constant propagating circuits are retained in circuit and not optimized.
- compile_delete_unloaded_sequential_cells If the variable is not set to true, it doesn't remove the counter cells as discussed, it retains all counters in the circuit.
- compile_register_replication If the variable is set to true, this replicates the registers in cloning optimization so that timing is met.
    
</details>

<details>

 <summary> Labs on Sequential and Combinational Optimization </summary>

 1. **Opt_check**
    
    The RTL code of the opt_check is as follows
    ```ruby
    module opt_check (input a , input b , input c , output y1, output y2);
	wire a1;
	assign y1 = a?b:0;
	assign y2 = ~((a1 & b) | c);
	assign a1 = 1'b0;
    endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check1.0.png">

    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%201.1.png">
    
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/sch_opt_check%201..0.png">

2. **Opt_check2**

   The RTL code of the opt_check is as follows
    ```ruby
   module opt_check2 (input a , input b , output y);
	assign y = a?1:b;
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%202.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/sch_opt_check%202.png">

3. **Opt_check3**
   
    The RTL code of the opt_check is as follows
    ```ruby
   module opt_check3 (input a , input b, input c , output y);
	assign y = a?(c?b:0):0;
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%203.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/sch_opt_check%203.png">

4. **Opt_check4**
   
   The RTL code of the opt_check is as follows
    ```ruby
   module opt_check4 (input a , input b , input c , output y);
 	assign y = a?(b?(a & c ):c):(!c);
   endmodule
    ```
    The report after linking the compiling the above design is as follows
    
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%204.png">
    
    The schematic in design vision is as follows
    	
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/sch_opt_check%204.png">

    After constraining the maximum delay to 60 ps and setting the cell size of U$ to xnor2_4 we get the violated report

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%204_for_size_cell_xnor_2_4.png">

    After again compiling it using compile_ultra we get the faster cell i.e xnor2_1
   
    <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/report_opt_check%204_formax_delay0.06.png">

**Resource Sharing**

 Consider the example 
 ```ruby
module resource_sharing_mult_check (input [3:0] a , input [3:0] b, input [3:0] c , input [3:0] d, output [7:0] y  , input sel);
	assign y = sel ? (a*b) : (c*d);

endmodule
```

    
  <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_sch__2_resource_2.png">
  
    The report before adding constraint to the design are as follows

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_timing_1.png">
 
     Area 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_area_1.png">

Then constraining with max_delay 2.5 ns 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_sch__2_resource_2.2.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_timing_all_outputs_0.1.png">

 Area 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_area_2.png">


After this we set the max_delay to 0.1 ns , the report and area are as follows 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_sch__3_resource_3.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_timing_3_aftr_2.5_max_delay.png">

 Area 

 <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_area_3.png">
  

After this we set maximum area using the below command

*set_max_area 800*

The area and report for the above case are as follows

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/926d326bc0f90e3c773c8f4cbd73c9e905299f94/day9/lab2_areaopt_area.png">
    
   <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_report_timing_4_significant%204%20delay_3.png">

   <img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab2_sch_set_area_800.png"> 




**Labs on Sequential Optimizations**

**Tie cells**

Tie cells also known as tie-high and tie-low cells, are components used in vlsi design to ensure that specific signal are held at a predetermined logic value regardless of input condition. These cells are particularlly useful in preventing floating or undefined states in digital circuit.

**dff_const**
  ```ruby
   module dff_const1(input clk, input reset, output reg q);
	always @(posedge clk, posedge reset)
	begin
		if(reset)
			q <= 1'b0;
		else
			q <= 1'b1;
	end

  endmodule
  ```
As it is not a sequential constant we see the flop as shown in the figure 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const2.png">

**dff_const2**
```ruby
module dff_const2(input clk, input reset, output reg q);
always @(posedge clk, posedge reset)
begin
	if(reset)
		q <= 1'b1;
	else
		q <= 1'b1;
end

endmodule
```
It is a sequential constant propagation so th flops are optimized

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const2.2.png">

In some cases we don't need to simplify the circuit in that case we can use the following command to prevent constant sequential propagation

set compile_seqmap_propagate_constants false

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const2.png">

**dff_const3**
```ruby
module dff_const3(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
This is not an example of sequential constant propagation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const3.png>

**dff_const4**
```ruby
module dff_const4(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b1;
		q1 <= 1'b1;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const4.png">

**dff_const5**
```ruby
module dff_const5(input clk, input reset, output reg q);
reg q1;

always @(posedge clk, posedge reset)
begin
	if(reset)
	begin
		q <= 1'b0;
		q1 <= 1'b0;
	end
	else
	begin
		q1 <= 1'b1;
		q <= q1;
	end
end

endmodule
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab3_sch_dff_const5.png">
</details>



<details>
<summary> Special Optimizations</summary>

### Register Retiming
Regiater Retiming is also known as Pipelining.Pipelining is a technique that breaks combinational paths by inserting registers.
This can be explained through an example. Let us consider the following design with a huge combinational delay of 48ns and the setup of flops can be 1ns each. This is the critical path of the design, hence limiting the circuit to operate at a frequency of 20MHz. 
This can be avoided by adding more flops to the design. As these new reg2reg paths have huge positive slack upto 48ns. The combinational logic can be sliced and shared among this flipflops. Thus improving the performance of the design. 
![vid1_1](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/asdfghjkl.png)

The tool do not share the logic equally, it optimizes the design to the extent. So, If it is shared as shown, the delay of the design now will be 20ns in the critical path. This, Improving the performance of the design to 50 MHz. 
If the design is optimized, the intermediate values cannot be defined. So, The optimization of tool is hard to calculate. SO, Any bug in subsequent design makes debugging more complex. The repercussion of not using it is sub-optimal design and using is complex behaviour at intermediate stages.
#### Lab
The following code is a 4-bit multiplier multiplying two 4-bit numbers and three 8-bit registers through which data is propagated to output.
![lab3_6](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retiming_verilog_code.png)

![lab3_](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retiming_report_1.png)


The following images show the synthesized design withGUI of multiplier(sub_module) and complete design.
![lab3_8_1](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retiming_whole_diag_1.png)
![lab3_8_2](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retiming_report_1.png)

The following image shows the timing path which violates worst delay in the design at input port.
![lab3_10](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retimingreport_timing_1.46.png)

The following image is obtained after using the command as follows:
```bash
dc_shell> compile_ultra -retime
```
![lab3_11](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retiming_sch_aftr-retime.png)

Now the violated slack has reduced and violation is at output delay.
![lab3_12](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retimingreport_timing_0.08.png)


### Boundary Optimization
The Boundary Optimization can be explained through an example. Consider a top module having internal sub module, the combinational logic at output port of sub module and external logic can be optimized such that area or power consumation reduces.It dissolves the boundary of the submodule, merges the logic to obtain the opyimal logic and implements the design. So, The optimization os done without any regard to boundary such that design is remodelled. The optimization do not preserve the hierarchy so the intermediate signals in the netlist were removed by the tool in optization. So, Debugging becomes complex as some hierarchical modules and intermediate signals are absent.
The Boundary optimizations are done using the switch as follows:
- set_boundary_optimization <design> true|false
```bash
set_boundary_optimization u_im false
```
#### Lab
The folowing image shows the behavioral code of boundary_check.v.
![lab3_1](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab4_boundry_opt_verilog_code.png)

In the following code, im is the internal module which is a 3-bit counter. Upon reaching, 111 it gives cnt_roll as enable to 4-bit register.
The following image shows that the design consists of 3-bit counter and 4-bit register with asynchronous reset
![lab3_2](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab5_boundry_opt_linking%20the%20dc_shell.png)

The following image shows the design with hierarchical module u_im in the design. The Boundary Optimization is not done in this design
![lab3_5](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab5_boundry_opt_sch_1_no_bnr.png)

The Boundary optimized design is as follows:
![lab3_3](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab5_sch_only_u_im_pin.png)


During functional ECOs, If any bugs occur, it can be directly changed in netlist only if hierarchies are preserved, otherwise the synthesis run of complete design may take huge time.
There is no thumb rule to set the set_boundary_optimization to either true or false. It completely depends on the need of design.

### Multi-Cycle Paths
Let us consider the following design. Assume all the flops work at some clock frequency of 100MHz. The multiplier may have a delay of 15ns, and the total delay might account to 16ns. 
![vidi-1-2](https://github.com/Dhananjay411/Samsungpdtraining/commit/65305ebbe107667adb27ac908aff16ccec8f9c6c)

But the design implies the output requires two clock cycles to get data. The enable to select requires one clock cycle and select to output requires another clock cycle. 
Such timing paths are defined as multi-cycle paths so that tool do not over optimize the design. The over optimization may cause violations at other paths which is unnecessary.
#### How paths are timed MCP?
For a single cycle path, the setup check is done at the consecutive edge of the flop and hold is done at the same edge of the flop.
*Hold is always checked edge before setup.*
For a half cycle path, the setup check is done at the subsequent fall edge of the flop and hold is done at the previous falling edge of the flop. In a half cycle path, setup is very stringent and hold is relaxed.
Fir a multicycle path, the -setup switch specifies the number of cycles after the launch edge, it needs to check setup and the -hold switch specifies the number of cycles the launch edge moves to check with capture.

This definition of multi-cycle path is done as follows:
```tcl
set_multicycle_path -setup 2 -to prod_reg[*]/D -through [all_inputs]
set_multicycle_path -hold 1 -to prod_reg[*]/D -through [all_inputs]
```
The above commands for a clock period of 5ns check setup from 0ns to 10ns at capture and hold at 0ns for both the flops.
This can be done after careful understanding of design else single cycle paths shiuld not be defined that may corrupts the whole design.
#### Lab
The following image shows the behavioral code of mcp_check.v
![lab4_1](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/mcp_code_ssssssss1.png)

The following image shows that the design constains a 16-bit register for multiplier output and a flop for enable.
![lab4_2](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/mcp_code_lllllllllkl2.png)

The following image shows the constraints defined in a tcl file for mcp_check
  
  RTL Design code
```ruby
*Lab*

The RTL design code 
```ruby
module mcp_check (input clk , input res  , input [7:0] a , input [7:0] b, input en , output reg [15:0] prod);

reg valid; 

always @ (posedge clk , posedge res)
begin
	if(res)
		valid <= 1'b0;
	else 
		valid <= en;
end



always @ (posedge clk , posedge res)
begin
	if(res)
		prod <= 16'b0;
	else if (valid)
		prod <= a * b;
end

endmodule
```

The following image shows the initial violation before compilation and the violation after compilation
![37](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab_sec_last_red_verilog_.v_file.png)

Now, the multi-cycle path is set and the violated slack is reduced as follows:
![lab4_5](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab_sec_last_sch_without_buf_1.png)

The command should infer about the startpoint also because the single cycle paths should never get affected(relaxed) because of multi cycle paths.
The following image shows that all timing paths met the setup violation.
![89](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/last_verilog_mcp_console_2_script.png)

So, After defining hold, the timing is met as follows:
![1213](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/reg_retimingreport_timing_1.46.png)

#### False Paths
False paths are the paths that are invalid for STA.If the launch and capture flops have no temporal correlation between edges, then the path can be regarded as false path.
Different clocks are not always asyncronous, the clocks generated from same master and master will have a relation which can't make it a false path. 
The path from a constant selection line of multiplexer to register cannot be a timing path, so considered as false path.
The false path can be specified as
```tcl
set_false_path –through <>
```

### Isolating Outputs
When there are more number of outputs to be connected after implementation of design, this may cause a violation of internal delays as cell delay is a function of load capacitance. Inorder to avoid internal failure, we isolate by inserting a buffer at output port. So, the buffer drives the external load.Now, the internal paths are decoupled from output paths..This is illustrated in the following design.
![load](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/WhatsApp%20Image%202023-09-14%20at%2022.55.53.jpeg)
The command to isolate ports is:
```tcl
set_isolate_ports -type buffer [get_ports OUT_Y]
```
#### Lab
Let us consider the behavioral code of check_boundary as before. The following image shows the synthesized design before dissolving the boundary.

After dissolving the boundary, there is no isolation implemented. So, By using set_isolate_ports command the design is isolated from external load.
![lab3_15_1](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab_sec_last_sch_without_buf_1.png)

After insertion of buffers, the design is as follows:
![lab3_15_2](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day9/lab_sec_last_sch_with_buf_1.png)

</details>

# Day 10 QOR


<details>
<summary>Summary</summary>
<br>
	
The following constraints are defined for a synthesis.tcl to constrain a design
- clock : Master clock, generated clock and virtual clock (if any)
    create_clock, create_generated_clock
- Practicalities of clock :Latency and  Uncertainty (Skew + jitter for pre-cts and jitter for post-cts)
   set_clock_uncertainty, set_clock_uncertainty
- Input delay and output delay
set_input_delay, set_output_delay
- Input transition/Driving cell
   set_input_transition, set_driving_cell
- Output load
   set_load
- max capacitance, max transition and area
   set_max_capacitance, set_max_transition, set_max_area

The DC flow for synthesizing netlist is
- read_verilog
- read_db
- check_design
- source constraints
- check_timing
- compile_ultra
- report_constraints -all_violators
- report_area
- report_timing
- write

The various synthesis knobs for optimization are
- Boundary Optimization
- Retiming
- Constant Propagation
- Unused flop removal
- Isolate ports

 When all these constraints are met with good margin, the QOR is good. The DC flow can be illustrated as follows:
 ![flow](https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/day10_1.png)




</details>
<details>
<summary>Report Timing</summary>
<br>	

Quality checks in Very Large Scale Integration (VLSI) design and manufacturing are crucial to ensure the reliability and functionality of integrated circuits (ICs). VLSI quality checks involve various stages of the design and manufacturing process to identify and rectify potential issues.Quality checks in VLSI are iterative and continuous throughout the design and manufacturing process to guarantee the reliability, performance, and manufacturability of integrated circuits. Advanced simulation and verification tools are often used to automate and streamline these checks.

Propagation delay, in the context of digital electronics and integrated circuits, refers to the time it takes for an electrical signal to travel from the input of a digital logic gate or circuit to its output. It is a critical parameter in digital design because it affects the speed and performance of the circuit. Propagation delay is typically measured in time units, such as nanoseconds (ns) or picoseconds (ps), and it depends on various factors, including the specific technology used, the length of interconnecting wires, and the complexity of the circuit.

Rising Edge Propagation Delay (tpdr): This is the time it takes for the output signal to transition from a low (0) to a high (1) level after the input signal has made a similar transition.

Falling Edge Propagation Delay (tpdf): This is the time it takes for the output signal to transition from a high (1) to a low (0) level after the input signal has made a similar transition.

We know that Rise to fall delay is not same as fall to rise delay as mobility of electrons and holes are not same.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/111111.jpg">

In this we can see that in the first case when both A and B are 0 the output Y is 1 , which implies That both a and b help helps in charging the capacitor, but in the next case when either A/B is 1 only the other one charges the capacitor so , it is clear that A to Y delay is not same as B to Y delay


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/13333.jpg">

Inverter gate :

A rise -> Y fall (0.5 ns)

A fall -> Y rise (0.4 ns)

AND gate :

A rise -> Y rise (0.7 ns)

A fall -> Y fall (0.65 ns)

B rise -> Y rise (0.65 ns)

B fall -> Y fall (0.6 ns)

Now the different timing paths along with delays are as follows

DFFA(Clk -> Q r) -> INV(A r) -> INV(Y f) -> AND(A f) -> AND(Y f) -> DFFC(f)

0.5 + 0.5 + 0.65 = 1.65ns

DFFA(Clk -> Q f) -> INV(A f) -> INV(Y r) -> AND(A r) -> AND(Y r) -> DFFC(f)

0.4 + 0.4 + 0.7 = 1.5ns

DFFA(Clk -> Q r) -> AND(B r) -> AND(Y r) -> DFFC(r)

0.5 + 0.65 = 1.15 ns

DFFA(Clk -> Q f) -> AND(B f) -> AND(Y f) -> DFFC(f)

0.4 + 0.6 = 1.0 ns

The path with the highest delay is 1st path so that path is called the critical path. Critical path is the one which decides the operating frequency of that circuit

report_timing -from DFFA/CLK -to DFFC/D -delay max

we get the first path

report_timing -from DFFA/CLK -to DFFC/D -delay min

we get the second path

report_timing -delay min -to DFFC/D

we get fourth path

report_timing -delay max -to DFFC/D

we get the **first path*8

report_timing -delay max -rise_to DFFC/D

we get the second path

report_timing -delay max -fall_to DFFC/D

we get the first path

Now consider the clock period as 5 ns, setup time is 0.5 ns and hold time is 0.4 ns.

DFFA(Clk -> Q r) -> INV(A r) -> INV(Y f) -> AND(A f) -> AND(Y f) -> DFFC(f)

0.5 + 0.5 + 0.65 = 1.65ns

This time is called as arrival time

The required time is Clock period - setup time

5 - 0.5 = 4.5ns

setup slack = Required - Arrival (4.5 - 1.65 = 2.85 ns)

For Hold setup

The hold time is 0.1 ns

Required time = hold time + uncertainity = 0.1 + 0 = 0.1 ns

DFFA(Clk -> Q f) -> AND(B f) -> AND(Y f) -> DFFC(f)

0.4 + 0.6 = 1.0 ns

This is the arrival time

Hold slack = Arrival - required (1 - 0.1 = 0.9 ns)

Now consider another example


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/122222.jpg">

report_timing -max_paths 2

This returns the worst slack from each pin end . In this case the path with slacks -1.2 ns and -1.0 ns

report_timing -max_paths 2 -nworst 2

This returns the worst slack , In this case it is -1.2 ns and 1.1 ns


</details>
<details>
<summary>Labs</summary>
<br>	




The example used in this lab has the following design code
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_verilog_code_2.png">

When we report_timing along with capacitance trans nets input, This is for setup check as we can see path type is max , launch edge is 0 ns and capture edge is 10 ns. Also we can see that slack is required time - arrival time


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_report_timing_1.1___4.png">

When we give report_timing -from IN_A

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_min_report_timing_9.png">

When we give report_timing -rise_from IN_A -sig 4 -trans -inp -cap -nets

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_report_timing_1.2___5.png">

When we give report_timing -rise_from IN_A -to REGA_reg/D -sig 4 -trans -inp -cap -nets , we can see that there is mismatch in rise to fall delay and fall to rise delay as compared with second report.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_report_timing_compare_rpt1_rpt2_6.png">

When we give report_timing -delay min -from IN_A we can see that this is for hold check as we can see path type is min , launch edge is 0 ns and capture edge is 0 ns. Also we can see that slack is arrival time - required time

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_min_report_timing_10.png">

When we give report_timing -thr U15/Y
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_min_report_timing_9.png">

When we give report_timing -thr U15/Y -delay min

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_1_min_report_timing_10.png">


Checking whether the deign is loaded correctly or is there any Human error

Reading the design , after linking

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_check_design_1.png">

check_timing this showed all the paths were unconstrained

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_check_timing_2.png">

report_constraints ,This gives the default value of the constraints
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_constraint_3.png">

After adding constraints to the design when we give check_timing
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_check_design_4.png">

when we give report_timing

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_check_timing_5.png">

report_constraints

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

Consider a case of 128 : 1 Mux

Design Code

```ruby

module mux_generate ( input [127:0] in, input [6:0] sel, output reg y);
integer k;
always @ (*)
begin
for(k = 0; k < 128; k=k+1) begin
	if(k == sel)
		y = in[k];
end
end
endmodule
```

write -f verilog -out

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

We constraint the max delay using command

set_max_delay -from [all_inputs] -to [all_outputs] 3.5

We set the max capacitance

set_max_capacitance 0.025 [current_design]

report_timing we see its violated

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">


report_constraints -all_violators
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

when we do compile_ultra

report_constraints
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

report_timing
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

Consider another example of 128 bit enable
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

after reading this code and compiling this code

report_timing -from en -inp -nets -caps we see that there are 128 fanouts
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

after setting the max cap as 0.03

report_constraints
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

after compile_ultra

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

Now viewing this in Design_vison by writing out ddc
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

Now set the trans constraints

Before compile ultra report_constraints
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

After compile ultra

report_constraints
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

check_timing

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">

report_timing -nosplit -sig 4 -inp -trans -cap

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day10/lab_2_report_const_6.png">





 




 
 
