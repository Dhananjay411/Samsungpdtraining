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



# Day 8 Advanced Constraints

 <details>
 <summary> Clock Terminology </summary>

 **clock** : Clock is a signal used for synchronization when the data passes through the storage elements like flip-flops and latches. It is to ensure that the correct data is captured in each sequential element. The waveform of a basic clock is as shown below.
 
 <img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/CLOCK1.jpg">
  
 **Clock sources** :
 In an ASIC design, clock can be generated from sources like PLLS or Crystal Oscillators. PLL or Phase Locked Loop is a circuit which generates the clock signal with reference to an input signal. It has a circultry to compare between the reference and the feedback signal to keep the output phase locked to the input. Crystal Oscillator uses the mechanical resonance of a vibrating crystal to generate an output clock signal. The output from a crystal oscillator is precise

  **Clock Tree** :
  Clocks are distributed to the sink points. They are sequential elements through clock trees or clock distribution networks. Clock tree is a collection of buffers or inverters. An ideal clock tree has the same number of levels of buffers/inverters from the source to the sinks. This promises equal delay of the clock from a single source to all sinks, which means zero clock skew. A clock tree gives balanced fanout too. 
  
 **Clock Types**: 
 
 *Master clocks*: These are clocks which get defined at the main clock source like oscillator/PLL. In a chip master clock can be defined at some clock input ports too. When we define these master clocks, proper frequency and source information should be given. Uncertainty also should be specified. 
 Generated clocks
 *Generated clocks* : These are divider/multiplier clocks which get generated from a master clock. Mostly these are defined at the output of a clock divider like flip flop or mux. When we define a generated clock, its source clock, the generation point, division ratio and uncertainty value should be provided. Generated clocks can be also defined at any point, if we need to define some exception wrt this clock. 

 *Virtual clock* : These are clocks used to time the input/output port. These are imaginary clocks defined only with the clock waveform and not having any source/generation point. 
 Virtual clocks are needed to constrain the input ports to register timing paths and reg to output port timing paths.

 <img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/VIRTUAL-CLOCKS.jpg">

 Since this timing path in the actual scenario cannot be checked as such when we are in our chip, we imagine the external device and proceed. So we define a 'virtual' clock which represent's FF2's clock. Also we constrain the output port OUT with this clock. We should specify the external delay outside the chip as output delay. To define the virtual clock just give create clock without any generation point.
 
 create_clock-name CLK_10-waveform {0 2.5} -period 5 
 
 The waveform of CLK 10 should be the same as CLK real. Also the latency of CLK_10 should be defined as same as the insertion delay of CLK_real. 
 Why can't we define the output delay wrt the real clock itself? 
 TECHNOLO 

 If we define so, tool cannot calculate any propagated clock latency to the output port, since it does not have any physical path. Propagated clock latency will be there for the Lor anyways. So the analysis will be for setup and optimistic for hold since capture clock delay is not there at all. Same explanations hold good for input 
 too We know that when the when the clock is constrained , Actually clock period gets constrained , which in turn limits the combinational delay i.e

 Tclk >= Tcq + Tcomb + Tst
 
 Tcomb <= Tclk - (Tcq + Tst)
 
 Clock Generator are a critical component of VLSI (Very Large Scale Integration) circuits, playing a fundamental role in synchronizing various components of an integrated circuit (IC). They provide clock signals that control the timing of digital operations within the IC. Clock generators are designed to produce clock signals with specific characteristics, such as frequency, duty cycle, and phase, to meet the requirements of the overall system.
 
 Types of clock generators
 
*Oscillators* : These are widely used as clock generators. They generate continuous periodic signals without an external input. Common types include RC oscillators, LC oscillators, and crystal oscillators.
 
*Phase-Locked Loops (PLLs)* : PLLs are versatile clock generators that can generate clock signals with adjustable frequency and phase. They are often used for clock synchronization and multiplication.
 
*Delay-Locked Loops (DLLs)* : DLLs are used to align the phase of a clock signal with respect to another reference clock signal.
 
*Ring Oscillators* : These are simple but effective oscillators often used for generating clock signals with relatively low frequencies.
 
*Crystal Oscillators* : They are highly stable and accurate oscillators that use piezoelectric crystals to generate clock signals.
  
 **skew** :
 
 In simplest words, Clock Skew is the time difference between arrival of the same edge of a clock signal at the Clock pin of the capture flop and launch flop. Any signal     takes some time to travel from one point to another. The time taken by Clock signal to reach from clock source to the clock pin of a particular flip flop is called as       Clock latency. Clock skew can also be termed as the difference between the capture clock latency and the launch clock latency for a set of flops
 
 <img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew1.JPG">
 
 The launch clock latency is 0ns and the capture clock latency is 2.5ns. The difference between the two is 2.5ns-0ns = 2.5ns which is the value of clock skew.

*Reason for Skew in a design*  
Just imagine a flip flop placed just close to the clock source and an another flip flop which placed at the far end of the core area. Due to the difference between the lengths of the interconnects, the skew cannot be zero in practical cases. To accommodate this, a user specified value is given to have accurate pre-CTS timing results.
After the clock tree is built, the actual skew values are available and the uncertainty only consists of Jitter value alone. 

<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew2.JPG">

In the above diagram, Consider a flip-flop (FF1) which has the minimum latency and FFn which has the highest latency. Two terms can be defined from the above figure.

*Local Skew*: The latency difference between two related flops in a design is called as local skew. Suppose, FF1 (Launch flop) and FF2 (Capture flop) are two related flops.


*Global Skew*: The clock latency difference between two non related flops or the difference between the longest clock path and the shortest clock path in the design is called global skew. Suppose, FF1 has the minimum and FFn has the maximum value of clock latency in the design.

*Positive and Negative Skew* :

<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew3.JPG">

In this scenario, the capture clock latency is more than the launch clock latency, and hence clock skew is positive. Positive skew is good for the setup timing. Since the capture clock is delayed by 2.5ns due to the addition of skew, the timing path has (1 clock period + Skew margin) to meet the setup requirement.
 
 On the other hand, positive skew is bad for hold timing. Due to positive skew, the capture edge has shifted to the right. If the data path delay is less, in that case the data launched from the launch flop will reach the D pin of capture flop before the capture clock edge reaches the clock pin of capture flop which will result in the overwriting of the previous data stored at capture flop.


<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew4.JPG">

Negative Skew is good for hold timing because the new launch is delayed by skew value. Due to the delay of the new data launch, the previous data will be effectively captured and won't be overwritten. But at the same time, negative skew is bad for setup timing.

*Useful Skew*:

The skew which is purposely added in the design to meet the timing, especially in the clock paths where timing is failing so that timing is passed in that path. But useful skew cannot be added blindly. This needs to be done carefully by making sure the margin is available in previous and the next timing path. Uncontrolled addition of skew can lead to more timing violations instead of fixing them. It can be used to fix both setup and hold violations. Let's explain with the help of a simple example:

<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew5.JPG">

In the above circuit, for the simplification let's take the skew value to be zero. Due to the large value of Tcombo1, there is a setup violation of 2ps. Due to a small value of Tcombo2, the setup slack is +4ps but the hold is violating by 1ps. Now assume that the data path is fully optimized in both the stages. Since there is a positive hold slack of 3ps in the first stage and a positive setup slack of 4ps in the second stage, by using the slack margins both timing paths can be fixed. Here comes the concept of useful skew to meet timing.

<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew6.JPG">

Let's add a buffer of delay 2ps in the Clock path of FF2 which will help in meeting the setup timing in the first path by pushing the capture clock. Since we have a good margin for setup slack in the second stage, it will not violate the setup time there.

The hold time was violating in the second path by 1ps which also got resolved because the buffer addition delayed the data launch in the second path by 2ps. Since we had a good margin for hold slack in the first stage, it will not violate the hold timing there. In this way, useful skew helps meeting timing.

Harmful Skew:

Where adding some skew to the failing paths can help in fixing timing violations, too much skew can cause violations.

If a large positive skew is added in the design, in that case, the capture clock will arrive after a long time and if the data path delay is small between the two flops, the data may reach the D pin of capture flop even before the capture edge reaches the clock pin of capture flop and may overwrite the previously latched data, resulting in Hold violation.

If a large negative is added in the design, in that case, the clock edge will reach the capture flop long before the launch flop. In this case, the new launch will be delayed. If the data path between the two flops is more, the launched data will get less to propagate to the D pin of capture flop and may reach very late resulting in Setup violation.

A hold violation is more dangerous than a setup violation as it cannot be fixed by decreasing the clock frequency.

What if there is actually zero skew in the design?

<img width="1085" alt="Timing libraries" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/skew7.JPG">

1. In the given figure, due to some Clock Jitter if the clock at FF3 gets delayed by a small interval of time, the new data launched by FF2 might reach D pin of FF3 very soon because of short path, resulting in the corruption of previous data at D pin of FF3, leading in Hold violation.
2. If the design has zero skew, which means all the flipflops in the design are getting clock at the same time. As we know, clock is the highest switching element in the design and a major contributor to the overall dynamic power consumption of the design. A chip consists of millions of flops. If all the flip flops switch at the same time, there will be a huge dynamic power dissipation in the design.
3. If one flip flop is placed closer to the clock source pin and another flip flop which is placed little far from the clock source pin, both are related, then to make the skew as zero, the tool would have added a large number of clock buffers and inverters in the clock path which will result in more area consumption and high utilization.

**clock Modelling**

 We should model the clock for
1. period
2. Source latency
3. Clock skew
4. Clock Network
5. Clock Network latency
   
</details>
	
 <details>
 <summary>Labs on Advanced Constrains </summary>



**Exploring Cells, Pins and Ports:**

- First synthesis is done in dc_shell using following commands:

```
> csh
> dc_shell                                        // invoking DC Shell
>> read_verilog lab8_circuit.v                            // reading the design
>> link
>> compile_ultra
>> write -f verilog -out netlist.v
>> write -f verilog -out lab1.ddc       
```

- Below is the schematic of the synthesized design:
<p align="center">
 <img width="1080" alt="l1_schem.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/sch_2_15.png">
</p>
  
- Now different cells, pins and ports of design and how to get their attributes are given below:

**Cells:**

- `get_cells` is the command used to list all the standard cells present in the design.
- Following snippet will list all the cells and their corresponding library name.

```
foreach_in_collection my_cells [get_cells * -hier] {
	set my_cell_name [get_object_name $my_cells];
	set rname [get_attribute [get_cells $my_cell_name] ref_name];
	echo $my_cell_name $rname;
}
```

- Output:
<p align="center">
 <img width="540" alt="l1_get_cells1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/referance_name_cell_7.png"> 
 </p>

**Ports:**

- `get_ports` is the command used to list all the input and output ports present in the design.
- Following snippet will list all the ports and also print if they are input and output pin.

```
foreach_in_collection my_port [get_ports *] {                      
       set my_port_name [get_object_name $my_port];                
       set dir [get_attribute [get_ports $my_port_name] direction];
       echo $my_port_name $dir;                                    
}
```

- Output:
<p align="center">
   <img width="540" alt="l1_getports2.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/get_port_collection_4.png"> 
</p>

**Pins:**

- `get_pins` is the command used to list all the input and output pins of standard cells present in the design.
- Following snippet will list all the pins and also print if they are input and output pin.

```
foreach_in_collection my_pin [get_pins *] {  
	set pin_name [get_object_name $my_pin]; 
	set dir [get_attribute $pin_name direction];
	echo $pin_name $dir;
}
```

- Output:
<p align="center">
  <img width="540" alt="l2_getpins1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/get_pins.png">
</p>

- Another example using `get_pins` is given below where the snippet will check whether the input pin is connected to clock and print those which are clock pins.

```
foreach_in_collection my_pin [get_pins *] { 
	set pin_name [get_object_name $my_pin];               
	set dir [get_attribute $pin_name direction];          
	if { [regexp $dir in ] } {                            
		if { [get_attribute [get_pins $pin_name] clock] } {   
			echo $pin_name;                                       
} } }
``` 

- Output: 
<p align="center">
  <img width="540" alt="l2_getpins2.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/clock_pins1.png"> 
</p>

**Creating Clock:** 

- `create_clock` is the command used to create a clock.
- Following command will create a clock with different attributes.

```
// 50% duty cylce starting with rising edge 
create_clock -name MYClk -per 10 [get_ports clk] -wave {0,5}
// 50% duty cycle starting with falling edge
create_clock -name MYClk -per 10 [get_ports clk] -wave {5,10}
// 25% duty cycle
create_clock -name MYClk -per 10 [get_ports clk] -wave {0,2.5}
```

- Following snippet will print all th clock pins and clock source they are connected to:

```
foreach_in_collection my_pin [get_pins *] {  
  set pin_name [get_object_name $my_pin];                
  set dir [get_attribute $pin_name direction];           
  if { [regexp $dir in ] } {                             
    if { [get_attribute [get_pins $pin_name] clock] } {  
      set clk [get_attribute [get_pins $pin_name] clocks];
      set clk_name [get_object_name $clk];  
      echo $pin_name $dir $clk_name;                                        
  }                                                      
 }                                                      
}    
```

- Output: 
<p align="center">
  <img width="300" alt="l3_getclk3_tcllo.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/tcl_query_clk_pin_script_output11.png"> 
</p>

**Report Timing:** 

- Syntax:

```
report_timing -from startpoint -to endpoint -delay_type maxormin -cap -nets -trans
```

- Above command will generate the timing report from specified startpoint to endpoint. And we can see set-up and hold specific reports using -delay_type attribute and other constraints like capacitance, transition and fanout information will also be provided.

**Setting latency and uncertainity:**

- Before setting up the latency and uncertainity, below timing report for set-up(max) and hold(min) is generated to ease the comparison.
- For example REGB to REGC path is considered:
<p align="center">
  <img alt="l4_timingrep_before1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/set_clk_latency_uncertanity.png" >

</p>

- As expected clock network delay is given 0ns. Now add latency and uncertainity to the design using following commands:

```
set_clock_latency -source 2 [get_clocks MYClk]
set_clock_latency 1 [get_clocks MYClk]
set_clock_uncertainty -hold 0.1 [get_clocks MYClk]
set_clock_uncertainty -setup 0.5 [get_clocks MYClk]
```

- Now generate the timing report again using `report_timing -from REGB_reg/CLK -to REGC_reg/D -delay_type max` and `report_timing -from REGB_reg/CLK -to REGC_reg/D -delay_type min` .
 <p align="center">
  <img alt="l4_timrep1_max.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_with_slack.png" >
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="l4_timrep2_min.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_with_slack_met_latency%20_uncertanity.png">
</p> 

- From above report we can observe the following:
   - Set-up: Slack decreased from 9.55 to 9.05.
   - Hold  : Slack decreased from 0.38 to 0.29.

**Constraining the IO:**

*Setting Up Input Delay:*
- Below commands are used to set input delay:

```
set_input_delay -max 5 -clock [get_clock MYCLK] [get_ports IN_A]
set_input_delay -max 5 -clock [get_clock MYCLK] [get_ports IN_B]
set_input_delay -min 1 -clock [get_clock MYClk] [get_ports IN_A]
set_input_delay -min 1 -clock [get_clock MYClk] [get_ports IN_B]
```

- Since there are two inputs constrain both of these input 'IN_A' and 'IN_B' separately for max and min.
- Now generate the timing report using `report_timing -from IN_A -transition_time -capacitance -nets -delay_type max`  and `report_timing -from IN_A -transition_time -capacitance -nets -delay_type min`. 
 <p align="center">
  <img alt="l5_timrep2_max.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing%20with%20apply%20load%20slack%20met.png" >
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="l5_timrep2_min.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png">
</p> 

- If we were to generate the timing report without constraining the input delay tool will tell us that the path is 'un-constrained' but now we can see the timing report and we can see the effect of that constraint is added under `input external delay` 

*Setting Up Input Transition:*
- Below are the commands used to set up input transition:

```
set_input_transition -max 0.3 [get_ports IN_A]
set_input_transition -max 0.3 [get_ports IN_B]
set_input_transition -min 0.1 [get_ports IN_B]
set_input_transition -min 0.1 [get_ports IN_A]
```

- Now generate the timing report using same commands previously used i.e `report_timing -from IN_A -transition_time -capacitance -nets -delay_type max`  and `report_timing -from IN_A -transition_time -capacitance -nets -delay_type min`.
 <p align="center">
  <img alt="l5_timrep3_max.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png"45%" >
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="l5_timrep3_min.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png">
</p> 

- From above timing report we can see the effect of this under `IN_A (in)` and  we can observe the following:
   - Set-up: Slack decreased from 4.1 to 4.08.
   - Hold  : Slack improved  from 0.99 to 1.02.

*Setting Up Output Delay:*
- Below are the commands used to set up output delay:

```
set_output_delay -max 5 -clock [get_clock MYClk] [get_ports OUT_Y]
set_output_delay -min 1 -clock [get_clock MYClk] [get_ports OUT_Y]

```

- Now generate the timing report using  commands  `report_timing -to OUT_Y -transition_time -capacitance -nets -delay_type max`  and `report_timing -to OUT_Y -transition_time -capacitance -nets -delay_type min`.

  <img alt="l5_timrep4_max.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png" >


-  If we were to generate the timing report without constraining the output delay tool will tell us that the path is 'un-constrained' but now we can see the timing report and we can see the effect of that constraint(`output external delay`) is subtracted from required time.

*Setting Up Output Load:*

```
set_load -max 0.4 [get_ports OUT_Y]
set_load -min 0.1 [get_ports OUT_Y]
```

- We can now generate timing report and observe the effect of output load on the design.
<p align="center">
  <img alt="l5_timrep5_max.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png >

- We can see the changes in `OUT_Y (net)` and there's a increase in slack for hold and decrease in slack for set-up.

*Generated Clock:*

- Generated clocks are additional clock signals created by the designer to meet the specific timing needs of different parts of the design.
- They are generated by dividing, multiplying, or modifying the primary clock signal using various clock generation circuits or modules.
- Generated clock can identified with `G` annotation under attributes.
- Follwoing is the command used to generate generated clock:

```
create_generated_clock -name MYGEN_Clk -master MYClk -source [get_ports clk] -div 1 [get_ports out_clk]
report_clocks
get_attribute [get_clocks MYGEN_Clk] is_generated```


- But to inform the tool to use this generated clock as the reference clock for out_clk and constraining w.r.t generated clock use following commands to specify

```
set_clock_latency -max 1 [get_clocks MYGEN_Clk]
set_output_delay -max 5  -clock [get_clocks MYGEN_Clk] [get_ports OUT_Y]
set_output_delay -min 1  -clock [get_clocks MYGEN_Clk] [get_ports OUT_Y]
```

-Now generate the timing report using command  `report_timing -to OUT_Y -delay_type max` and `report_timing -to OUT_Y -delay_type min > gen_timrep1_min`.

- Now consider an other example with following code:

```
module lab8 circuit (input rst, input clk , input IN_A , input IN_B , output OUT_Y , output out_clk output reg out_div_clk)
reg REGA, REGB , REGC ;
always @ (posedge clk , posedge rst )
begin
	if(rst)
	begin
		REGA <= 1'b0 ;
		REGB <= 1'b0 ;
		REGC <= 1'b0 ;
		out_div_clk <= 1'b0 ;
	end
	else
	begin
		REGA= IN_A | IN_B;
		REGB<- IN_A ^ IN_B;
		REGC <= !(REGA & REGB) ;
		out_div_clk <= ~out_div_clk
	end
end

assign OUT_Y = ~REGC ;

assign out_clk = clk;

endmodule
```

- Now reset the design using `reset_design` and read the above verilog file
- Link and compile the the design.
- To add the constraints we can source the following TCL script in DC shell instead of individually defining each constraints:

```
create clock -name MYCLK -per 10 [get _ports_clk];
set _clock_latency -source 2 [get clocks MYCLK];
set_clock_latency 1 [get_clocks MYCLK]:
set_clock_uncertainty -setup 0.5 [get clocks MYCLK];
set_clock_uncertainty -hold 0.1 [get clocks MYCLK];
set_input_delay -max 5 -clock [get clocks MYCLK] [get_ports IN_ Al;
set _input_delay -max 5 -clock [get clocks MYCLK] [get_ports IN_B];
set_input-delay -min 1 -clock [get clocks MYCLK] [get_ports IN A];
set _input_delay -min 1 -clock [get clocks MYCLK] [get ports IN_B];
set_input_transition -max 0.4 [get_ports IN_A];
set_input_transition -max 0.4 [get_ports IN_B];
set_input_transition -min 0.1 [get_ports IN_A];
set_input_transition -min 0.1 [get_ports IN_B];
create_generated_clock -name MYGEN_CLK - master MYCLK -source [get_ports clk] -div 1 [<get_ports out_clk]
create_generated_clock -name MYGEN_DIV_CLK - master MYCLK -source [get_ports clk] -div 2 [<get_ports out_div_clk];
set_output_delay -max 5 -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
set_output_delay -min 1 -clock [get_clocks MYGEN_CLK] [get_ports OUT_Y];
set_load -max 0.4 [get_ports OUT_Y];
set_load -min 0.1 [get_ports OUT_Y];
```

- Now using  `report_clocks` command we can observe the two generated clock MYGEN_CLK  which is same as source clk and MYGEN_DIV_CLK which has its frequency divided by 2.
<p></p>
<p align="center">
  <img width="300" alt="l2_gen_getports.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png"  >
</p>

- This design is completely constrained.



*Virtual Clock and set_driving_cell:*
<p align="center">
  <img width="300" alt="circuit.jpg" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png"  >
</p>

- For above design we can model the constraint using follwoing methods :
    1) Using command `set_max_latency 1.0 -from [get_ports IN_C] -to [get_ports OUT_Z]` we can model the max delay of the combinational circuit.
    2) Another way is to create a virtual clock setting input and output delay w.r.t virtual clock. Following are the commands used

1) set_driving_cell:
   
- `set_max_latency 1.0 -from [get_ports IN_C] -to [get_ports OUT_Z]` is the command used to contsrain the input and output ports.
- Before setting the latency timing report will give path is unconstrained So the after running the above command we will get following output:
- Outputs:
<p align="center">
  <img alt="l14_setmax_timrep.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png" >
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="l14_setmax_timrep1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png">
</p> 

- Since design is not compiled after setting the constraints it is not optimized and it shows negative slack which means presence of violations. Now compile the design using command `compile_ultra` and below timing report(right) is generated using command `report_timing -to OUT_Z`.

  
2) Virtual clock:
   
- Vitual clock is a clock created without a clock defination point.
- To contrain the IO using this method following commands are used:

```
// for virtual clock there's no clock defination and latency
create_clock -name MY_VClk -period -5
set_output_delay -max 2.5 -clock MY_VClk [get_ports OUT_Z]
set_input_delay -max 1.5 -clock MY_VClk [get_ports IN_C]
set_input_delay -max 1.5 -clock MY_VClk [get_ports IN_B]
```

- Outputs:
<p align="center">
  <img alt="l14_vclk_timrep.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png" >
&nbsp; &nbsp; &nbsp; &nbsp;
  <img alt="l14_vclk_timrep1.png" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd%23day8/report_timing_1.png">
</p> 

- In generate the timing report(left one) using `report_timing -from IN_d -to OUT_Z ` as expected without optimization it has resulted in violation.
- To get rid of violtion compile the design again using command `compile_ultra` and generate the timing report again. From timinng report one the right side we can observe that tool has optimized the design to '0' slack.



*Special case:*

- Lets consider case where there are two flops on input/output of top level and one of the flop has active low clock i.e it's sensitive clock edge is falling edge.
- To constrain this design we have specify the tool that delay is w.r.t to falling edge of the clock and it can be done using following command:

```
set_input_delay -max 3 -clock clk -clock_fall -add [get_ports IN_A]
set_output_delay -max 3 -clock clk -clock_fall -add [get_ports OUT_Y]
// -clock will specify the falling edge
// -add will make sure previously set input delay is not overwritten
```

*set_driving_cell:*

- While set_input_transition is used for top level primary design when the interface specifications are provided(IO ports of the chip).
- But when we are working inside the design if we know the cell driving the input pin then `set_driving_cell` will make more sense and provide better accuracy.
- Following is the syntax to use the command:
- `set_driving_cell -lib_cell nameoflibcell [all_inputs]` 






 




 
 
