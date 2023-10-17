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


</details>

# Day 11 Introduction to SOC


<details>
<summary>Introduction to SOC</summary>
<br>
	
-System-on-Chip (SoC) is a term commonly used in the field of VLSI (Very Large-Scale Integration) design. It refers to an integrated circuit (IC) that integrates all the components of a computer or other electronic system onto a single chip. In this article, we will delve into the basics of SoC and discuss its importance in the VLSI industry.

-SoC is the result of the advancement in VLSI technology, where designers can integrate millions of transistors, logic gates, and other components onto a single chip. This integration of components on a single chip has revolutionized the electronics industry by enabling the creation of smaller, more efficient, and more powerful electronic devices.

-SoC integrates all the components of a computer or electronic system onto a single chip. The components of SoC typically include microprocessors, memory, I/O interfaces, digital signal processors, and other custom-designed components. The design of SoC is complex, and it requires the designer to have a deep understanding of all the components and how they interact with each other.

-SoC has many benefits. First, it reduces the number of components and connections required to build an electronic system, thereby reducing the overall cost of the system. Second, it improves the performance of the system by reducing the communication latency between the components. Third, it reduces the power consumption of the system, as the components can be optimized to work together and consume less power. For example, consider the case of a smartphone. In a traditional design, the smartphone would require separate chips for the processor, memory, and other components. However, with an SoC, all of these components can be integrated onto a single chip, reducing the overall size of the smartphone and making it more power-efficient.

-Another advantage of SoCs is that they offer greater flexibility and scalability compared to traditional designs. With an SoC, designers can add or remove components as needed, making it easier to customize the design to suit specific requirements. This is particularly useful in applications such as IoT devices, where different devices may require different combinations of components. In addition to smartphones and IoT devices, SoCs are also used in a range of other applications, including automotive, aerospace, and defense. For example, an automotive SoC may include components for navigation, entertainment, and safety features, all on a single chip.

-Another great example of SoC is the Raspberry Pi. The Raspberry Pi is a small single-board computer that was designed with the aim of promoting the teaching of basic computer science in schools. It has an ARM-based processor, memory, I/O interfaces, and other components all integrated onto a single chip. The Raspberry Pi has become very popular among hobbyists and educators, as it is a low-cost, low-power, and versatile computing platform.

-In conclusion, SoC is a critical component in the field of VLSI design. It enables the creation of smaller, more efficient, and more powerful electronic devices by integrating all the components of a computer or electronic system onto a single chip. With the continued growth of the semiconductor industry, it is likely that SoCs will become even more prevalent in the coming years.



 </details>
 <details>
<summary>Snapdragon 730 octa core</summary>


-The Snapdragon 730 is a mobile system-on-chip (SoC) developed by Qualcomm. It was announced in April 2019 and is part of the Snapdragon 7 series, which is known for offering a good balance of performance and power efficiency for mid-range smartphones. Here are some key features of the Snapdragon 730:

1. CPU: The Snapdragon 730 features an octa-core CPU (Central Processing Unit) based on Qualcomm's Kryo architecture. It consists of two clusters of cores:

Two high-performance cores (Kryo 470 Gold) clocked at up to 2.2 GHz.
Six power-efficient cores (Kryo 470 Silver) clocked at up to 1.8 GHz.
GPU: It comes with the Adreno 618 GPU, which provides good gaming and graphics performance for mid-range devices.

2. AI Capabilities: The Snapdragon 730 includes Qualcomm's Hexagon 688 DSP (Digital Signal Processor) for AI (Artificial Intelligence) and machine learning tasks, which can enhance camera capabilities and other AI-driven features.

3. Modem: It features the Qualcomm Snapdragon X15 LTE modem, which supports fast 4G LTE connectivity.

4. Camera Support: The Snapdragon 730 supports up to 48 MP single-camera or 22 MP dual-camera setups. It also has various camera enhancements and features, including support for computer vision and AI-based image processing.

5. Process Technology: It is manufactured using an 8nm process technology, which helps in achieving a balance between performance and power efficiency.

6. Connectivity: The SoC includes support for Wi-Fi 6 (802.11ax) and Bluetooth 5.0 for wireless connectivity.

7. Display Support: It supports Full HD+ displays with HDR10 and HDR10+ support for improved display quality.

Overall, the Snapdragon 730 is designed for mid-range smartphones and offers a good mix of performance, power efficiency, and AI capabilities, making it suitable for a wide range of applications, including gaming and photography. Please note that since my knowledge is based on information available up to September 2021, there may have been newer SoCs released by Qualcomm with improved features and capabilities since then.





</details>
<details>
<summary>Video Summary</summary>

Chips are made using extremely pure mono crystalline Silicon ingot called bull with only one impurity for every 10 million silicon atoms.

These silicon bulls are fabricated in different diameters, common ones are 100mm,150mm,200mm,300mm

Transitors are built on p and n conductive layers that exist in a doped wafer. These are smallest control units in microchips.

Semiconductor Manufacturing Process Summary:

Design and Layout: The process begins with the design of the integrated circuit (IC) or microchip. Engineers use specialized software to create a detailed layout of the chips specifying the location and arrangement of transistors, interconnects, and other components.

Mask Creation: The chip's design is used to create a series of photomasks, which are high-precision templates that define the patterns to be etched onto the silicon wafer during fabrication.

Wafer Preparation: Silicon wafers, typically made from highly purified single-crystal silicon, are cleaned and polished to create a flat, defect-free surface. The wafers are also coated with a thin layer of material, such as silicon dioxide (oxide), to act as an insulator.

Photolithography: Photomasks are used in a photolithography process to project the chip's design onto the silicon wafer. Ultraviolet (UV) light or deep ultraviolet (DUV) light is passed through the masks to define the circuit patterns on the wafer's surface.

Etching: After photolithography, a chemical or plasma etching process is used to remove excess material from the wafer's surface, leaving behind the desired patterns. This step defines the locations of transistors, interconnects, and other features. There can be etched using wet or plasma etching.

Ion Implantation: Dopant ions (such as boron or phosphorus) are implanted into the silicon wafer to modify its electrical properties, creating N-type and P-type regions necessary for transistor operation.

Deposition: Thin layers of materials (such as metal or dielectrics) are deposited onto the wafer's surface using techniques like chemical vapor deposition (CVD) or physical vapor deposition (PVD). These layers form the conductive pathways and insulating barriers on the chip.

Chemical Mechanical Polishing (CMP) : CMP is used to planarize the wafer's surface, ensuring a uniform thickness of deposited material across the chip.

Lithography and Etching (Repeated): Multiple iterations of lithography and etching are performed to create the various layers of the chip, including the metal interconnect layers that link transistors and components.

Annealing: Heat treatments, called annealing, are applied to activate dopants, relieve stress, and improve the performance and reliability of the semiconductor materials.

Testing and Inspection : At various stages of manufacturing, the wafers undergo extensive testing and inspection to identify defects, verify functionality, and ensure quality.

Dicing: The processed wafer contains multiple chips separated a tiny space between them called as scribe line . This processed wafer is cut into individual chips using a process called dicing. Each chip will become a separate microchip.

Packaging : The individual microchips are placed into packages that protect them from environmental factors and facilitate connection to external circuits. Packaging also includes adding pins or balls for electrical connections.

These microchips should be made in clean room . A clean room is a controlled environment designed to minimize contamination and maintain specific environmental conditions critical to the fabrication of integrated circuits and other microelectronics devices. Clean rooms are essential for ensuring the reliability and performance of semiconductor components.
 
</details>


 </details>

# Day 12 Baby SOC Modelling


<details>
<summary>Task</summary>
	
 **Priority Encoder**: In Digital System Circuit, an Encoder is a combinational circuit that takes 2n  input signal lines and encodes them into n output signal lines. When the enable is true i.e., the corresponding input signal lines display the equivalent binary bit output. 

For example, 8:3 Encoder has 8 input lines and 3 output lines, 4:2 Encoder has 4 input lines and 2 output lines, and so on. 

 An 8:3 Priority Encoder has seven input lines i.e., i0 to i7, and three output lines y2, y1, and y0. In 8:3 Priority Encoder i7 have the highest priority and i0 the lowest. 

 **Truth Table**:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/Screenshot_2023_0925_122701.jpg">

**Logic Symbol**:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/Screenshot_2023_0925_122726.jpg">

 **Verilog Code**:Most of the programming deals with software development and design but Verilog HDL is a hardware description language that is used to design electronics design. Verilog provides designers to design the devices based on different levels of abstraction that include: Gate Level, Data Flow, Switch Level, and Behavioral modeling. 

*Behavior Modeling*:
Behavioral Model which is the highest level of abstraction, Since we are using Behavioral Modeling we shall write the code using if-else to ensure the Priority Encoder input values. By using the if condition the output values are assigned based on the priority. 

```ruby
module priorityencoder_83(en,i,y);
  // declare
  input en;
  input [7:0]i;
  // store and declare output values
  output reg [2:0]y;
  always @(en,i)
  begin
    if(en==1)
      begin
        // priority encoder
        // if condition to choose 
        // output based on priority. 
        if(i[7]==1) y=3'b111;
        else if(i[6]==1) y=3'b110;
        else if(i[5]==1) y=3'b101;
        else if(i[4]==1) y=3'b100;
        else if(i[3]==1) y=3'b011;
        else if(i[2]==1) y=3'b010;
        else if(i[1]==1) y=3'b001;
        else
        y=3'b000;
      end
     // if enable is zero, there is
     // an high impedance value. 
    else y=3'bzzz;
  end
endmodule

```

**Priority Encoder TestBench** :
Testbench: Behaviour
A Testbench is a simulation block that is used to provide inputs to the design block. The best way to write Testbench is having is a good insight into the truth table. Once you have the truth table ready provide the input values inside the testbench.

```ruby

module tb;
  reg [7:0]i;
  reg en;
  wire [2:0]y;
  
  // instantiate the model: creating 
  // instance for block diagram 
  priorityencoder_83 dut(en,i,y);
  initial
    begin
      // monitor is used to display the information. 
      $monitor("en=%b i=%b y=%b",en,i,y);
      // since en and i are input values, 
      // provide values to en and i. 
      en=1; i=128;#5
      en=1; i=64;#5
      en=1; i=32;#5
      en=1; i=16;#5
      en=1; i=8;#5
      en=1; i=4;#5
      en=1; i=2;#5
      en=1; i=0;#5
      en=0; i=8'bx; 
end

initial 
begin
$dumpfile ("dump.vcd");
$dumpvars;
#40 $finish;
end
endmodule
```


**Waveform**:
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/waveform_of%20prio_encoder.png">


</details>
<details>
<summary>VSD BabySOC</summary>


**RISC Vs CISC**:

 -RISC and CISC are two different types of computer architectures that are used to design the microprocessors that are found in computers. The fundamental difference between RISC and CISC is that RISC (Reduced Instruction Set Computer) includes simple instructions and takes one cycle, while the CISC (Complex Instruction Set Computer) includes complex instructions and takes multiple cycles.

**RISC** :
-In the RISC architecture, the instruction set of the computer system is simplified to reduce the execution time. RISC architecture has a small set of instructions that generally includes register-to-register operations.

-The RISC architecture uses comparatively a simple instruction format that is easy to decode. The instruction length can be fixed and aligned to word boundaries. RISC processors can execute only one instruction per clock cycle.

The following are some important characteristics of a RISC Processor −
     
     -A RISC processor has a few instructions.

     -RISC processor has a few addressing modes.

     -In the RISC processor, all operations are performed within the registers of the CPU.

     -RISC processor can be of fixed-length.

     -RISC can be hardwired rather than micro-programmed control.

     -RISC is used for single-cycle instruction execution.

     -RISC processor has easily decodable instruction format.

-RISC architectures are characterized by a small, simple instruction set and a highly efficient execution pipeline. This allows RISC processors to execute instructions quickly, but it also means that they can only perform a limited number of tasks.

**CISC**:

-The CISC architecture comprises a complex instruction set. A CISC processor has a variable-length instruction format. In this processor architecture, the instructions that require register operands can take only two bytes.

-In a CISC processor architecture, the instructions which require two memory addresses can take five bytes to comprise the complete instruction code. Therefore, in a CISC processor, the execution of instructions may take a varying number of clock cycles. The CISC processor also provides direct manipulation of operands that are stored in the memory.

-The primary objective of the CISC processor architecture is to support a single machine instruction for each statement that is written in a high-level programming language.

-The following are the important characteristics of a CISC processor architecture −

       -CISC can have variable-length instruction formats.

       -It supports a set of a large number of instructions, typically from 100 to 250 instructions.

       -It has a large variety of addressing modes, typically from 5 to 20 different modes.

      -CISC has some instructions which perform specialized tasks and are used infrequently.

-CISC architectures have a large, complex instruction set and a less efficient execution pipeline. This allows CISC processors to perform a wider range of tasks, but they are not as fast as RISC processors when executing instructions.

**Why RISC is preferred**:

-Simpler instructions: RISC processors use a smaller set of simple instructions, which makes them easier to decode and execute quickly. This results in faster processing times.
-Faster execution: Because RISC processors have a simpler instruction set, they can execute instructions faster than CISC processors.
-Lower power consumption: RISC processors consume less power than CISC processors, making them ideal for portable devices

**Conclusion**:

The most significant difference between RISC and CISC architectures is the size and complexity of the instruction set. RISC is a microprocessor architecture that uses a small instruction set of uniform length that allows fast execution, while the CISC architecture is one that offers hundreds of instructions of different sizes that allows the users to perform a wider range of tasks.


**Modelling the RVMYTH**:

RVMYTH core is a simple RISCV-based CPU, introduced in a workshop by RedwoodEDA and VSD.
Verilog code and test bench are attached here: verilog code & Test Bench

*waveform*:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/outputwave_myth_code.png">

**Modelling the DAC**:

A Digital to Analog Converter commonly referred as DAC, D/A or D2A is a device that converts binary values (0s and 1s) to a set of continuous analog voltages.
Verilog code and test bench are attached here: verilog code & Test Bench
The whole digital to analog conversion process is a scaling operation – the binary count is mapped to a certain voltage range, with 0V being the minimum( and the maximum voltage being the maximum input binary voltage i.e 3.3V in our case.

*waveform*:
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/waveform_of_DAC.png">

*We can also calculate the corresponding anolog value*.

```ruby
Consider the below data:
 Vref = 3.3V
 N = 10
 Digital Data = (0101111010)2 = (378)10
 Anolog Data = (D) x (Vref) / (2N - 1)
 Anolog Data = (378) x (3.3) / 210 -1) = 1.219354838709677 V
```
*waveform*:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/output%20wave_vsdbaby.png">

**Modelling the PLL**:

A phase-locked loop (PLL) is an electronic circuit with a voltage or voltage-driven oscillator that constantly adjusts to match the frequency of an input signal. PLLs are used to generate, stabilize, modulate, demodulate, filter or recover a signal.
Verilog code and test bench are attached here: verilog code & Test Bench

*Block Diagram*:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/pllll1.png">


*waveform*:
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/waveform_of_pll.png">



**Modelling the SoC**:

Now interconnect all the three IPs and execute at once.
Verilog code and test bench are attached here: verilog code & Test Bench


*waveform*:
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/Samsungpd%23day%2012/waveform_combine.png">


Commands used:
```ruby
iverilog design.v testbench.v -o op.out
./op.out
gtwave design_tb.vcd
```
 </details>

# Day 13 Post-Synthesis simulation


<details>
<summary>Post_Synthesis of Priority Encoder</summary>


The Priority Encoder output as discussed for the pre-synthesis simulation matches with the post-simulation output.The following are the sequnece of steps for simulating the output.

```ruby
iverilog full_add_net.v tb_add4.v primitives.v sky130_fd_sc_hd.v
./a.out
gtkwave tb_full_add_4.vcd
```
The iverilog command uses the simulated gatelevel netlist and the same testbench for post-synthesis simulation. The ./a.out dumps the vcd format file with respect to netlist. The gtkwave is used to view the waveform. The post-simulation output is as follows:

*waveform*:
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/waveform_of%20prio_encoder.png">

So, The output of post-synthesis and pre-synthesis exactly matches so the logical corectness of the design is verified.

The inputs a and b are given to each full adder and the carry from previous stage is given as input to the next stage. The following sequence of commands writes the netlist and ddc format as follows:

```ruby
read_verilog add4.v
link
compile_ultra
write -f verilog -out full_add_net.v
write -f ddc -out full_add.ddc
```
The read_db command is not used as the target_library and link_library are previously set to sky130 technology .db. The schematic of the full-adder can be viewed as follows:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/schematic_of%20prio_encoder1.png">


</details>
<details>
<summary>Post-Synthesis of BabySOC</summary>

The Post-synthesis of the RISC-V processor RYMYTH is as follows:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/waveform_of%20mythcore_gls.png">

The commands used for generating the out netlist are as follows:

```ruby
read_verilog mythcore_test.v
link
compile_ultra
write -f verilog -out rvmyth_net.v
```

The netlist being written here as out is the output of the clk_gate as it is default in code. So, the current_design is changed to core and the netlist is written out as follows:

```ruby
current_design core
write -f verilog -out rvmyth_net.v
```
The processor output increments in the same way as at the pre-synthesis stage, So, the logic is properly defined. The following commands are used to simulate the output waveform.

```ruby
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 rvmyth_net.v tb_mythcore_test.v primitives.v sky130_fd_sc_hd.v
./a.out
gtkwave tb_mythcore_test.vcd
```
The post-synthesis of the BabySoC is as follows:

The following commands are used to simulate the output waveform.

```ruby
iverilog -DFUNCTIONAL -DUNIT_DELAY=#1 rvmyth_net.v testbench.v primitives.v sky130_fd_sc_hd.v avsddac.v avsdpll.v vsdbabysoc.v
./a.out
gtkwave dump.vcd
```

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day13/waveform_babysoc_gls.png">

</details>


 </details>

# Day 14 Post-Synthesis simulation


<details>
<summary>Introduction</summary>
	
**1.Introduction**

In VLSI (Very Large Scale Integration) design, a "PVT corner" refers to a specific set of process, voltage, and temperature conditions under which a semiconductor chip or integrated circuit (IC) is designed and tested. PVT corners are essential for ensuring that a chip operates reliably under various operating conditions. Let's break down the components of PVT:

   1.1. **Process (P)**: This component refers to the specific manufacturing process used to create the semiconductor device. Semiconductor manufacturing processes can have variations, and PVT corners help take these variations into account. Different processes can lead to variations in transistor characteristics and other properties of the semiconductor.
   
   1.2. **Voltage (V)**: Voltage refers to the operating voltage supplied to the integrated circuit. Chips are designed to work within a specific range of voltages, and different PVT corners may test the chip's performance at various voltage levels, including nominal voltage, minimum voltage, and maximum voltage. This ensures that the chip operates reliably under different voltage conditions.
   
   1.3. **Temperature (T)**: Temperature refers to the ambient temperature at which the chip operates. Like voltage, temperature can affect the performance of a semiconductor device. PVT corners typically include testing at different temperature levels, such as room temperature (25°C), high-temperature (elevated temperature), and low-temperature conditions.

2. **Designing and testing a chip under different PVT corners is crucial for several reasons**:

      2.1. **Reliability**: It ensures that the chip functions reliably across a range of conditions. This is particularly important in applications where the chip may be exposed to extreme temperatures or voltage fluctuations.

      2.2. **Performance Optimization**: By testing under different PVT corners, designers can optimize the chip's performance for various scenarios. For example, a chip may need to operate efficiently at both low and high temperatures.

      2.3. **Manufacturing Variability**: Semiconductor manufacturing processes can have variations from one manufacturing run to another. Testing under different PVT corners helps account for these variations and ensures that the chip meets its specifications.

      2.4. **Worst-Case Analysis**: PVT corner testing often includes a "worst-case" scenario, where the chip is tested under the most extreme conditions (e.g., highest temperature and lowest voltage). This helps identify potential failure points and design weaknesses.
- PVT corners are critical for meeting the design specifications, ensuring reliability, and achieving optimal performance for semiconductor devices. Designers use tools and simulations to assess how the chip performs under different PVT conditions and make necessary adjustments to the design to meet these requirements.

3. **Relationship Between PVT**

In VLSI (Very Large Scale Integration) design, the relationship between PVT (Process, Voltage, and Temperature) is fundamental and plays a crucial role in the design, manufacturing, and testing of semiconductor devices. The relationship can be understood as follows:

3.1. **Process Variation (P)**:
            Impact on Voltage and Temperature: The manufacturing process of semiconductor devices can have inherent variations, leading to differences in transistor characteristics, gate lengths, doping levels, and other factors. These process variations directly affect how the chip operates under different voltage and temperature conditions.Design Margins: To account for process variations, designers often need to add design margins, which are extra performance allowances, to ensure that the chip will function correctly even under the worst-case process conditions.

3.2 **Voltage Variation (V)**
Impact on Process and Temperature: The operating voltage supplied to a chip affects its power consumption, speed, and reliability. Different voltage levels may be applied to test the chip's performance under various conditions.

*Dynamic Voltage Scaling (DVS)*: In some cases, chips are designed with dynamic voltage scaling capabilities, allowing them to adjust their operating voltage to optimize power consumption and performance depending on the workload and temperature conditions.

 3.3 **Temperature Variation (T)**:
*Impact on Process and Voltage*: Temperature has a significant impact on the electrical characteristics of semiconductor devices. As temperature increases, the mobility of charge carriers in transistors changes, affecting their performance. Chips must be tested at different temperatures to ensure proper functionality across the specified operating range.
      *Thermal Management*: In VLSI design, thermal management strategies, such as heat sinks, fans, and thermal simulations, are used to control the temperature of the chip and maintain it within acceptable limits.

The relationship between PVT factors is intricate because changes in one factor can affect the others. For example:
Process variations can affect the electrical characteristics of transistors, which, in turn, can impact the voltage levels required for proper operation.
Voltage changes can result in power dissipation, which can increase the chip's temperature.
Temperature fluctuations can affect transistor performance and alter the required voltage levels for reliable operation.
Designers must carefully consider the interplay between these factors to ensure that the chip meets its performance and reliability specifications under various PVT conditions. This often involves extensive simulations, modeling, and testing at different PVT corners to validate the chip's functionality and robustness.
Ultimately, achieving a successful VLSI design involves a delicate balance between these PVT factors to ensure that the semiconductor device operates reliably and efficiently across a range of real-world operating conditions.

4. **Slack**:
   
    PVT corners are essential in VLSI design because semiconductor devices' behavior can vary significantly based on these parameters. Characterizing a design at various PVT corners helps ensure that the circuit or device will function correctly and within specified performance limits under a range of real-world operating conditions.
        Designers use PVT corners to analyze the worst-case performance, optimize for power, or achieve a balance between performance, power consumption, and other design goals. It's important to consider and account for process, voltage, and temperature variations to create robust and reliable integrated circuits.
        TNS (Total Negative Slack), WNS (Worst Negative Slack), and WHS (Worst Hold Slack) are terms used in the context of timing analysis in digital integrated circuit design. These terms are used to evaluate the timing performance of a circuit and ensure that it meets the specified timing requirements.

      4.1 **TNS (Total Negative Slack)**: TNS represents the sum of the negative slack across all paths in a circuit. Slack is the amount of time by which a signal can be delayed without violating the specified timing constraints. A negative slack indicates that a path violates its timing requirements. TNS provides an overall view of how much timing violation exists in the entire design.

      4.2 **WNS (Worst Negative Slack)**: WNS is the most critical or largest negative slack among all paths in the circuit. It represents the timing violation that is closest to breaching the specified timing constraints. Addressing the WNS is crucial in design optimization and fixes, as it determines the worst-case timing scenario in the circuit.

      4.3. **WHS (Worst Hold Slack)**: WHS is similar to WNS but specifically relates to hold timing violations. Hold timing refers to the minimum amount of time that data must be held stable after a clock edge to ensure correct operation. WHS identifies the path with the largest negative slack with respect to hold timing, indicating the worst-case hold violation in the design.

      These metrics are critical for timing closure in the VLSI design process. Designers use various techniques such as gate resizing, buffer insertion, clock skew adjustment, and pipeline optimization to address negative slack, minimize WNS, and ensure that the circuit meets its timing requirements. Achieving good TNS and eliminating WNS and WHS is essential to ensure the circuit operates reliably and within the specified timing bounds.

</details>
<details>
<summary>Labs</summary>

Steps

1.Get all the .lib files by cloning https://github.com/Geetima2021/vsdpcvrd.git

2. Delete the lines from the .lib with the error stated. (REPEAT THIS FOR ALL THE .LIB)

3. After deleting the lines , load LC shell and convert it into .db using the following commands

    ```ruby
    read_lib <library_name>
     write_lib <library_name> -f db -o <name_of_the_db_file>
```

 4. Now generate a constaraint file

```ruby
set_units -time ns
create_clock -name MYCLK -per 2 [get_pins {pll/CLK}];

set_clock_latency -source 1 [get_clocks MYCLK]
set_clock_uncertainty -setup 0.5 [get_clocks MYCLK]; 
set_clock_uncertainty -hold 0.4 [get_clocks MYCLK]; 

set_input_delay -max 1 -clock \[get_clocks MYCLK] [all_inputs];
set_input_delay -min 0.5 -clock \[get_clocks MYCLK] [all_inputs];
set_output_delay -max 1 -clock \[get_clocks MYCLK] [all_outputs];
set_output_delay -min 0.5 -clock \[get_clocks MYCLK] [all_outputs];

set_input_transition -max 0.2 \[all_inputs];
set_input_transition -min 0.1 \[all_inputs];

set_max_area  800;

set_load -max 0.2 \[all_outputs];
set_load -min 0.1 \[all_outputs];

```

Now set the required db files (sky130.db,avsddac.db,avsdpll.db), read the design , link the library and do compile_ultra

Commands for implementing this are as follows

```ruby
set target_library { <sky130_PVT_corner> , avsddac.db , avsdpll.db}
set link_library {* sky130_PVT_corner> , avsddac.db , avsdpll.db}
read_verilog vsdbabysoc.v
link
source <constraints_file_name>
compile_ultra
report_qor
```

**Output**:
1.For sky130_fd_sc_hd__ff_100C_1v65 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ff_1v65.png">
 
2.For sky130_fd_sc_hd__ff_100C_1v95 
  <img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ff_100c_1v95.png">
  
3.For sky130_fd_sc_hd__ff_n40C_1v56
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ff_n40c_1v56.png">

4.For sky130_fd_sc_hd__ff_n40C_1v65 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ff_n40c_1v65.png">

5.For sky130_fd_sc_hd__ff_n40C_1v76
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ff_n40c_1v76.png">

6.For sky130_fd_sc_hd__ss_100C_1v40
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_100c_1v40.png">

7.For sky130_fd_sc_hd__ss_100C_1v60
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_100c_1v60.png">

8.For sky130_fd_sc_hd__ss_n40C_1v28 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_n40c_1v28.png">

9.For sky130_fd_sc_hd__ss_n40C_1v35 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_n40c_1v35.png">

10.For sky130_fd_sc_hd__ss_n40C_1v40 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_n40c_1v40.png">

11.For sky130_fd_sc_hd__ss_n40C_1v44
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_n40c_1v44.png">

12.For sky130_fd_sc_hd__ss_n40C_1v76 
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/ss_n40c_1v76.png">

13.For sky130_fd_sc_hd__tt_025C_1v80
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/tt_025c_1v80.png">

**Table and Graph for setup**

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/SETUP_TABLE.JPG">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/WNS_SETUP.JPG">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/TNS_SETUP.JPG">


**Table and Graph for setup**

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/HOLD_TABLE.JPG">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/WNS_HOLD.JPG">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day14/TNS_HOLD.JPG">



**Observation**

Hold violations are more prone in faster cells and setup is more prone in slower cells.

The worst corner for setup is ss_n40C_1v28 , if this corner is satisfied then all the others will be satisfied automatically.

The best PVT corner is ff_n40C_1v76 as it has no setup violation and very minimal hold violation.



</details>



</details>

# Day 15 Inception of open source EDA, openLANE and sky130PDK


<details>
<summary>Introduction</summary>
	
**1.Introduction to QFN-48, RISC-5(ISA), software and hardware**

A QFN-48 package is a type of surface mount device (SMD) package commonly used in electronics to house integrated circuits (ICs) or chips. QFN stands for Quad Flat No-Lead, and the "48" in QFN-48 indicates the number of pins or pads on the package. Here's an introduction to some key components and concepts related to QFN-48 packages:

**1.Package**: The QFN-48 package is a compact, square or rectangular-shaped component designed to protect and provide electrical connections to an integrated circuit or chip. It has a flat bottom with exposed metal pads for soldering onto a printed circuit board (PCB).

**2.Chip**: The chip, also known as the integrated circuit or IC, is the core of the electronic component. It contains the active electronic components, transistors, resistors, and other elements necessary to perform specific functions, such as processing data or amplifying signals.

**3.Pads**: In the context of a QFN-48 package, pads refer to the metal areas on the bottom of the package that make electrical contact with the PCB. These pads are usually arranged in a grid pattern around the edges of the package, and they are used for soldering the QFN package onto the PCB.

**4.Core Die**: The core die is the actual semiconductor chip within the QFN-48 package. It is a small, silicon-based wafer on which the electronic circuitry is fabricated. The core die is connected to the metal pads on the package, allowing it to communicate with the outside world through these electrical connections.

**5.IPs (Intellectual Property)**: In the context of electronics and semiconductor design, IPs refer to Intellectual Property blocks or modules. These are pre-designed and pre-verified functional blocks that can be integrated into a chip's design to save time and effort. IPs are often used for common functions like microprocessors, memory, communication interfaces, or analog circuitry. Chip designers can license or purchase these IPs from third-party vendors to incorporate them into their chip designs, reducing the need to design these components from scratch.

In summary, a QFN-48 package is a specific type of surface mount package used to house integrated circuits (chips). The package has metal pads on the bottom that connect to the core die inside the chip. Designers may use IPs to incorporate pre-designed functional blocks into the chip's design, which can streamline the development process and improve efficiency in creating complex electronic devices

**RISC-5 Instruction set Architecture**:
standard "RISC-5" instruction set architecture (ISA) in the field of computer architecture. However, there are several RISC (Reduced Instruction Set Computer) architectures with various versions and extensions developed by different organizations and researchers.

One of the well-known RISC architectures is RISC-V, which you might be referring to as "RISC-5." RISC-V is an open-source ISA that has gained popularity for its flexibility, simplicity, and extensibility. It is designed to be highly customizable, allowing designers to tailor the instruction set to meet the specific needs of their applications or hardware implementations.

The RISC-V ISA is based on several principles commonly found in RISC architectures:

1.*Simplicity*: RISC-V simplifies the instruction set by reducing the number of instructions and addressing modes, which can lead to more efficient and predictable performance.

2.*Load-Store Architecture*: RISC-V, like most RISC architectures, uses a load-store architecture. This means that arithmetic and logical operations typically involve registers, and memory access is performed through specific load and store instructions.

3.*Fixed-Length Instructions*: Instructions in RISC-V are typically of fixed length, making instruction fetching and decoding straightforward.

4.*Register-Based*: RISC-V architectures often have a set of registers that instructions operate on. These registers are typically general-purpose and can be used for various operations.

5.*Pipeline Friendly*: RISC architectures are designed to be easily pipelined, which can improve instruction throughput and overall performance.

It's important to note that the "5" in "RISC-5" does not correspond to a specific version or extension of the RISC-V ISA. Instead, RISC-V has different standard extensions denoted by single-letter mnemonics like "I" for integer instructions, "M" for integer multiplication and division, "A" for atomic instructions, and so on. Depending on the specific needs of a system or application, designers can choose which extensions to include in their RISC-V implementation.

Please keep in mind that developments in computer architecture may have occurred since my last knowledge update in September 2021. If "RISC-5" refers to a specific ISA that has emerged after that date, I recommend consulting more recent sources for the most up-to-date information.


**connection between system software and hardware**
The connection between application software, system software, and hardware in a computer system is crucial for the overall functioning of the system. These three components work together in a layered fashion, with each layer serving a specific purpose. Here's an overview of the connection between these components:

1.*Hardware*:

Hardware is the physical component of a computer system, including the CPU, memory, storage devices, input/output devices (e.g., keyboard, mouse, display), and various other peripherals.
It provides the raw computational power and resources necessary for running software.

2.*System Software*:

System software serves as an intermediary between hardware and application software.
The operating system (OS) is a core component of system software. It manages hardware resources, including CPU scheduling, memory management, file system operations, and device drivers.
Device drivers are software components that allow the OS to communicate with specific hardware devices.
System software provides a platform for running application software by abstracting the hardware complexities and providing a set of services and APIs (Application Programming Interfaces) for applications to utilize.

3.*Application Software*:

Application software includes all the programs and applications that users interact with directly to perform specific tasks or functions, such as word processors, web browsers, games, and business applications.
Application software relies on system software to access hardware resources and perform tasks. It uses APIs and services provided by the operating system to access files, display graphics, receive input, and communicate over networks.
Application software abstracts the underlying system and hardware details from the user, allowing them to interact with the computer system in a user-friendly manner.

Here's a simplified illustration of how these components interact:

1. The user interacts with application software (e.g., a word processing program).
2. The application software issues requests and commands for various tasks, such as saving a document or printing.
3. The application software communicates these requests to the operating system via system calls or APIs.
4. The operating system, as part of system software, manages the hardware resources required to fulfill the requests. For example, it may allocate memory for the document, manage the printer connection, or retrieve data from storage.
5. The operating system communicates with hardware through device drivers and manages the hardware operations necessary to complete the tasks.
6. The results or output are then relayed back through the layers, and the user sees the intended action or outcome on the application software's interface.
This layered approach to computer architecture allows for abstraction, efficiency, and flexibility, enabling various applications to run on diverse hardware platforms with minimal modification. It also ensures that hardware resources are shared and managed efficiently among multiple applications running concurrently on the same system.


</details>
<details>
<summary>SOC Design and openLANE</summary>
	
SOC (System-on-Chip) design is a complex process of integrating various hardware and software components into a single chip to perform specific functions or tasks. OpenLANE, on the other hand, is an open-source ASIC (Application-Specific Integrated Circuit) design flow automation tool that simplifies the process of designing and manufacturing custom chips. Let's explore how SOC design and OpenLANE are related:

**1.SOC Design Overview**:

SOC design involves the integration of multiple components, including CPUs, GPUs, memory, input/output interfaces, and custom hardware accelerators, onto a single chip.
It requires expertise in hardware architecture, digital design, verification, physical design, and manufacturing processes.
SOC designers need to make critical decisions regarding chip architecture, power management, clocking, communication protocols, and more.

**2.OpenLANE**:

OpenLANE is an open-source ASIC design flow that automates many of the steps involved in designing a custom chip.
It is built on open-source EDA (Electronic Design Automation) tools and aims to make ASIC design more accessible to a broader community of designers.
OpenLANE includes tools for synthesis, place and route, clock tree synthesis, and more, all integrated into a single pipeline.
It provides a set of scripts and methodologies that automate the steps required to convert a chip design from RTL (Register Transfer Level) description to a manufacturable GDSII file.
The connection between SOC design and OpenLANE lies in OpenLANE's ability to streamline and simplify the design and manufacturing process for custom chips. SOC designers can use OpenLANE to:

*1.Rapidly Prototype*: OpenLANE allows designers to quickly prototype and experiment with custom ASIC designs without the need for a proprietary design flow.

*2.Reduce Costs*: By utilizing open-source tools and methodologies, OpenLANE can significantly reduce the cost of custom chip development compared to proprietary EDA tools.

*3.Improve Accessibility*: OpenLANE's open-source nature makes it accessible to a wide range of designers, including academic researchers, startups, and hobbyists.

*4.Optimize for Specific Requirements*: SOC designers can use OpenLANE to optimize their chip designs for specific requirements, such as low power, high performance, or specialized functions.

In summary, SOC design is a complex process that involves integrating various hardware and software components into a single chip. OpenLANE is a valuable tool that simplifies the ASIC design flow, making SOC design more accessible and cost-effective for a broader range of designers. It can be used to automate many of the design and manufacturing steps, ultimately helping bring custom chips to market more efficiently.




</details>
<details>
<summary>open source ASIC Design flow</summary>

An open-source ASIC (Application-Specific Integrated Circuit) design flow refers to the use of open-source software tools and methodologies for the entire process of designing and manufacturing custom integrated circuits. Open-source ASIC design flows provide an alternative to proprietary Electronic Design Automation (EDA) tools, making chip design more accessible, cost-effective, and transparent. Here is an overview of the steps and components typically involved in an open-source ASIC design flow:

*1.Specification and Design*:
  -Define the specifications and requirements for the ASIC.
 - Create a high-level architectural design of the chip, including the overall functionality and major components.
  
*2.RTL Design*:
-Write the RTL (Register Transfer Level) description of the digital logic using a hardware description language (HDL) such as Verilog or VHDL.
-Design custom digital blocks and IP (Intellectual Property) cores, if necessary.

*3.Verification*:
-Perform simulation and verification of the RTL design using open-source simulation tools like Icarus Verilog or Verilator.
-Write testbenches to verify the correctness of the design.

*4.Synthesis*:
-Use open-source synthesis tools like Yosys to convert the RTL design into a gate-level netlist.
-Optimize the design for area, power, and timing constraints.

*5.Physical Design*:
-Perform floorplanning to allocate space for different components on the chip.
-Use open-source tools like Magic or KLayout for layout design.
-Perform placement and routing using tools like OpenROAD or Qflow.

*6.Clock Tree Synthesis (CTS)*:
-Generate a clock tree to distribute clock signals evenly across the chip using open-source CTS tools.

*7.DRC (Design Rule Check) and LVS (Layout vs. Schematic)*:
-Verify the layout against design rules and ensure it matches the RTL description using open-source tools like Netgen or Magic.

*8.Static Timing Analysis (STA)*:
-Analyze the design to ensure that it meets timing requirements using open-source STA tools like OpenSTA or TritonRoute.

*9.Simulation and Post-Layout Verification*:
-Perform post-layout simulation and verification to ensure that the final layout meets functional and timing requirements.

*10.Mask Generation*:
-Generate the GDSII file, which contains the physical mask data necessary for manufacturing.

*11.Manufacturing*:
-Send the GDSII file to a semiconductor foundry for the fabrication of physical ASICs.

*12.Testing and Characterization*:
-Once the chips are fabricated, they are tested and characterized to ensure they meet the specifications.

*13.Packaging and Integration*:
-Package the ASICs and integrate them into the target system.

Throughout the open-source ASIC design flow, various open-source EDA tools and scripts are used to perform different tasks, from RTL design to manufacturing preparation. By using open-source tools, designers can reduce costs, increase transparency, and collaborate with a broader community of engineers and researchers in the development of custom integrated circuits. It also promotes innovation and democratizes chip design by making the entire process more accessible.


</details>
<details>
<summary>LABS</summary>

**Skywater130 PDK Files**

 The skywater130 PDK contains 3 directories:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/first.png">

1. skywater-pdk : It contains all pdk related files (.lib,.lef)
2. open-pdks : It contains scripts that bridge the compatibility gap between closed-source and open-source PDKs for Electronic Design Automation (EDA) tools.
3. sky130A : It contains open source compatible EDA files.
   
   
The commands for invoking Openlane
```ruby
docker
flow.tcl -interactive
```
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_000000001_first.png">

Importing the package
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/second.png">

Preparing Design:

The "prep" phase sets up the file structure for your design within OpenLane.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_less_merger_lef_7.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_less_confi_8.png">

Inside a runs folder a folder is created with date is created

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_run_file_crt_5.png">

Config file in the new directory shows the default parameters taken by the run.

After running the command run_synthesis
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_no%20of%20cell_10.png">
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_run_synthesis_9.png">






</details>

# Day 16 Good floorplan Vs Bad floorplan and introduction to library cell


<details>
<summary>Chip Floorplan Considerations</summary>

1. **Utilization Factor  and Aspect Ratio**:
   
Utilization factor and aspect ratio are concepts often used in engineering and design to assess and optimize the efficiency and performance of various systems or structures, including buildings, machines, and materials. Here's an explanation of each term:

**Utilization Factor**:

Utilization factor, also known as the duty cycle or load factor, is a measure of how efficiently a particular system or resource is being used or utilized over a specific period of time.
It is typically expressed as a ratio or percentage and indicates the portion of time or capacity that a system is actively in use compared to its total available capacity.
The formula for utilization factor is:
Utilization Factor = (Actual Usage) / (Maximum Capacity)
A high utilization factor indicates efficient and effective use of the resource, while a low utilization factor may suggest inefficiency or underutilization.
Example: In manufacturing, if a machine is operational for 8 hours in a 24-hour day, its utilization factor would be 8/24 = 1/3 or 33.33%.

**Aspect Ratio**:

Aspect ratio refers to the proportional relationship between the length and width (or height) of an object, system, or structure. It is commonly used in various fields, including architecture, aviation, and engineering.
Aspect ratio is often expressed as a simple ratio, such as 4:3 or 16:9, or as a decimal value. In the context of rectangular shapes, it is the ratio of the longer dimension to the shorter dimension.
For example, in the case of a rectangular building, the aspect ratio would be the ratio of its length to its width.
Example: If a rectangular building has a length of 60 meters and a width of 30 meters, the aspect ratio would be 60/30 = 2.

In aerodynamics, aspect ratio is used to describe the shape of aircraft wings. Wings with a higher aspect ratio (longer and narrower) tend to have better aerodynamic performance and higher lift-to-drag ratios.
Optimizing the utilization factor and aspect ratio can help improve efficiency, reduce waste, and enhance the performance of systems and structures in various applications. Engineers and designers often consider these factors when designing and evaluating different solutions.




-Height and Width of core and die Let us consider a simple netlist that has a reg-reg timing path with 2 flops and 2 combinational gates as follows:

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/1.png">

The dimensions of core and die are the summation of the area of standard cells present in the design. Let us assume that the area of the standard cell as 1sq. unit and the area of flipflop as 1 sq. unit. So, the minimum area occupied by the netlist is 4 sq. units, however may be placed.

A core is the section of a chip where the fundamental logic of a design is placed. A die, which consists of core, is a small semiconductor material specimen on which the fundamental circuit is fabricated. The core is encapsulated with the die. When our design is placed on the core, the logic cells completely occupy the area of the core i.e., the utilization of area is 100%. So, Utilization factor = Area occupied by netlist/Total area of the core When the utilization factor is 1, there is no space left on die for any other optimization. So, ideally the utilization factor used is 50-60%.

Aspect Ratio = Height/Width Whenever the aspect ratio is 1, it signifies a square chip. Otherwise, it is a rectangle. Let us now consider the following example that has a utilization factor of 0.5 and aspect ratio of 0.5. The length of the die is 2 units and height is 4 units. So, aspect ratio=2/4=0.5. The area required by the logic is 4 units so the utilization factor = 4/2x4=1/2=0.5.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/2.png">

Let us consider another core with area of 4x4 sq.units with the same netlist. So, The utilization factor now would be (2x2)/(4x4)= 0.25. So, Only 25% of area is utilized, the reamining area can be used for optimization.The aspect ratio here is 1, so it is a square chip.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/3.png">

**2.concept of Pre-placed Cells**:

Pre-placed cells, also known as pre-placed blocks or predefined blocks, are a concept used in digital integrated circuit design. They are an integral part of the process of designing complex integrated circuits, such as microprocessors, memory chips, and other digital systems. The concept involves designing and specifying certain predefined blocks or cells that are already created and optimized for specific functions, and then integrating these blocks into the overall circuit design. Here's an explanation of the concept:

*Custom vs. Standard Cells*:

In digital integrated circuit design, there are two main approaches: custom design and standard cell design.
Custom design involves creating every individual transistor and interconnect in the circuit, which can be highly time-consuming and labor-intensive. It is typically used for very specialized and high-performance applications.
Standard cell design, on the other hand, relies on pre-designed and pre-characterized cells or blocks. These standard cells are reusable and come in various sizes and functions, such as logic gates (AND, OR, etc.), flip-flops, multiplexers, and more.

*Pre-placed Cells**:

Pre-placed cells are a subset of standard cells. They are specific standard cells that are selected and positioned manually or with the help of automated tools in certain critical or specialized areas of the chip.
These pre-placed cells are often used for functions that require specialized optimization or are critical to the performance of the circuit.
Designers choose pre-placed cells based on their specific needs and knowledge of the circuit's requirements.

*Advantages*:

Pre-placed cells offer several advantages in chip design:
Performance Optimization: Designers can manually select and optimize the performance-critical parts of the circuit.
Customization: Specialized cells can be used for functions that may not be adequately addressed by standard cells.
Control: It provides greater control over the placement and utilization of critical components.

*Disadvantages*:

Complexity: Manually placing pre-placed cells can be complex and time-consuming.
Limited Reusability: Pre-placed cells are specific to the current design and may not be as reusable as standard cells.
Increased Design Time: Integrating pre-placed cells requires careful planning and may increase the overall design time.

*Application*:

Pre-placed cells are often used in high-performance digital designs where achieving specific speed, power, or area goals is critical.
They can also be used in mixed-signal designs, where digital and analog components are combined, and custom analog blocks need to be integrated.
In summary, pre-placed cells are a strategy used in digital integrated circuit design to combine the benefits of standard cells with the customization and performance optimization of specific blocks. Designers strategically place these predefined blocks in critical areas of the chip to meet the design's requirements efficiently.

Location of Preplaced Cells Preplaced cells are the piece of combinational logic such as macros, IPs that is being reused multiple times. The preplaced cells are placed based on the design scenario.The location of the preplaced cells need to be very well-defined. The preplaced cells can be understood with an example. Let us consider a combinational logic with 100k gates that can be granularised. Let us divide the circuit into two parts that can be seperated as two blocks. 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/4.png">

The IO pins of these blocks are extended and are seperated as two different IP modules, where the logic in the block is a black box. These blocks can be used multiple times on the netlist and designed only once. In other words, the block is designed as an IP and defined as blackbox in the main netlist and can be reused.

These models functionality defined once and reused on the chip. This is done before actual placement and routing. The location of these cells is usually fixed. The arrangement of these IPs is referrred as floorplanning. These IPs have user-defined locations, hence are placed in chip before automated place and route, and are called as pre-placed cells. The tool places the remaining logical cells in the design onto chip. The tool do not touch the location of these pre-placed cells.

These pre-placed cells needs to be surrounded with decoupling capacitors. When the output of a logic gate changes from 0 to 1, an amount of current is demanded by the output capacitance of the gate. It is the responsibility of Vdd to supply the necessary voltage for switching the logic in the design.Similary, From logic 1 to 0, the Vss should be able to handle the discharged currents by logic in the design. The physical wires that connect the design will have a drop as they have resistance, inductance and capacitance. 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/5.png">

During switching operation, the circuit demands switching current. There will be a voltage drop across them and voltage will be Vdd-IRdrop. If this value goes below noise margin, due to IR drop, the logic 1 at output won't be detected as 1 at the input of circuit. As shown, any voltage between Vol and Vil is considered logic '0' and voltage between Voh and Vih is considered as logic '1' and the voltage between Vil and Vih is undefined region as the voltage may rise to Vih or degrade to Vil.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsung_pd%23day15/img_run_synthesis_9.png">


**3. De-coupling Capacitor**:

A decoupling capacitor, often simply called a bypass capacitor or a noise-reduction capacitor, is an electronic component used in electronic circuits to reduce or eliminate voltage ripples, noise, and fluctuations in the power supply lines. It plays a crucial role in ensuring stable and reliable operation of digital and analog electronic devices. Here's how a decoupling capacitor works and why it's important:

**Voltage Stabilization**: Electronic circuits require a stable and consistent supply voltage to operate correctly. However, power supplies often have small fluctuations or noise due to various factors, including switching of other components on the same power rail, variations in the power source itself, or electromagnetic interference. These voltage fluctuations can disrupt the proper operation of sensitive components like microprocessors, memory, and other integrated circuits.

**Capacitor Basics**: A decoupling capacitor is typically a small ceramic or tantalum capacitor connected in parallel to the power supply lines of a device or integrated circuit. Capacitors store electrical charge and can release it quickly when needed. They act as a kind of "reservoir" of electrical energy.

**Filtering Noise**: When the supply voltage experiences a momentary drop or spike, the decoupling capacitor can discharge or charge to compensate for these fluctuations almost instantaneously. This rapid response effectively filters out the high-frequency noise and keeps the voltage across the component or IC stable.

**Parasitic Effects**: Besides noise reduction, decoupling capacitors also help counteract parasitic inductance and resistance in the power supply traces on a printed circuit board (PCB). These parasitic effects can cause voltage drops during rapid changes in current demand. The decoupling capacitor provides a nearby source of energy, minimizing these voltage drops.

**Placement Matters**: Decoupling capacitors should be placed as close as possible to the power pins of the component they are protecting. This minimizes the length of the power traces and ensures the capacitor can respond quickly to changes in current demand.

**Values and Types**: The choice of decoupling capacitor value and type depends on the application. Smaller ceramic capacitors (e.g., 0.1 µF) are commonly used for high-frequency noise suppression, while larger electrolytic capacitors may be used for filtering lower-frequency fluctuations. The choice often involves a combination of capacitors to address a range of frequencies effectively.

In summary, a decoupling capacitor is a crucial component in electronic circuits, helping to maintain stable and noise-free power supplies for sensitive components. It ensures that electronic devices operate reliably and without glitches, making it an essential consideration in circuit design.

The decoupling capacitors helps to overcome the noise due to long distance from the supply voltage. So, Addition of decoupling capacitor in parallel with circuit is done. So, Every time the circuit switches, it draws current from decoupling capacitor (Cd) as the RL network is used to replenish the charge into Cd. 


<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/6.png">


Addition of decoupling capacitor will avoid the problems of crosstalk and degradation of logic.

**4.Power Planning**:

Power planning is a crucial aspect of integrated circuit (IC) design that focuses on ensuring the efficient distribution of power throughout the chip while minimizing power consumption and maintaining signal integrity. It involves careful consideration of how power is supplied to various parts of the IC, how power is distributed, and how to manage power delivery to meet performance and reliability requirements. Here are some key aspects of power planning in IC design:

*Power Distribution Network (PDN)*:
The power distribution network consists of metal layers, power rails, and a network of power delivery components (such as power gates, voltage regulators, and decoupling capacitors) that ensure a stable and consistent supply of power to all the components on the chip.

*Voltage Domains*:
Many modern ICs have multiple voltage domains with varying power requirements. Power planning involves defining these voltage domains and ensuring that each domain receives the appropriate voltage levels and noise isolation.

*Decoupling Capacitors*:
Decoupling capacitors are strategically placed throughout the chip to filter out high-frequency noise and provide instantaneous current during switching. Proper placement and sizing of decoupling capacitors are critical for maintaining signal integrity.

*Power Gating*:
Power gating is a technique used to turn off power to specific sections or blocks of the chip when they are not in use. This helps reduce power consumption in idle or standby modes.

*Clock Distribution*:
Power planning also includes the distribution of clock signals, which must be synchronized with the power delivery network to ensure that clock signals are clean and that clock domains operate correctly.

*Signal Integrity*:
Power planning must consider the impact on signal integrity. Proper power distribution minimizes voltage drops and noise, which can affect the quality of digital signals.

*Thermal Considerations*:
Power planning takes into account the generation of heat within the IC. Efficient power delivery and distribution can help manage thermal issues and prevent hotspots.

*Electromigration and IR Drop Analysis*:
Electromigration is a phenomenon where metal atoms migrate due to the flow of current, potentially causing failures. IR drop analysis is performed to ensure that voltage drops do not violate design specifications.

*Low-Power Design Techniques*:
Power planning often involves the use of low-power design techniques such as clock gating, data gating, and voltage scaling to reduce dynamic and static power consumption.

*Simulation and Analysis*:
Engineers use specialized tools for power analysis and simulation to verify that the power delivery network meets the design requirements, including voltage levels, noise margins, and power consumption.

*Iterative Process*:
Power planning is an iterative process that may involve multiple design iterations to optimize power distribution and minimize power-related issues.
Effective power planning is essential to achieving the desired performance, power efficiency, and reliability in modern integrated circuits, especially in applications where power consumption is a critical concern, such as mobile devices, IoT devices, and battery-powered systems.

The macros requires the current for each cell in the design when reused.Let us assume a design where it ocntains various macros surrounded with decoupling capacitors. The Power Supply Vdd and Vss are connected as shown to each macro.Now, let the two macros connected as shown be the driver and load. The signal should propagate from the driver to load without any degradation. Assume that the driver is sending logic 0 to logic 1 to the load. It is not feasible to add decoupling capacitor to each cell in the logic. The critical blocks are added with decoupling capacitor. Consider the connect is a 16-bit bus, that has 16-bit logic, that is it charges and discharges as shown. The logic at output is connected to an inverter. This means all the capacitors which were charged to 'V' volts will have to discharge to '0' volts through single ground tap point. This will cause a bump in Ground tap point. If this bump exceeds the noise margin level, the output will be in a undefined region. (In undefined region, the output becomes unpredictable). 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/7.png">

Also, all capacitors which were 0 volts will charge to V volts through single Vdd tap point. This causes a voltage droop. If it goes beyond noise margin, it again becomes unpredictable. All this occur due to a single Vdd point, if there are multiples power supply points then each capacitor can charge and discharge from its nearest points as shown. So, Powermesh is the exact solution to mitigate voltage droops and ground bounces.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/8.png">

**5.Pin Placement and Logical cell placement blockage**:

In integrated circuit (IC) design, pin placement and logical cell placement are critical steps in the physical design phase. They involve determining the physical locations of pins (input and output connections) and logical cells (standard cells or custom-designed functional blocks) on the chip's layout. Blockages are also used in the placement process to reserve areas on the chip for specific purposes or to prevent certain components from being placed in those areas. Here's an overview of pin placement, logical cell placement, and blockages in IC design:

*Pin Placement*:

The connectivity information between the gates is coded using VHDL/verilog language and is called the netlist. Let us consider an example. There are two timing paths driven by different clocks, two timing paths driven by two (interclocks)clocks (alternate flops) and preplaced cells are connected in the design as shown.

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/9.png">

The pins are usually placed in the region between die and the core. This area is reserved for pin location. The logical cell placement blockage is used to avoid tool from inserting cells in this region. Let us consider that the input ports are connected on the left hand side and the output ports are connected on the right hand side. The ordering of the ports is random, it depends on where the cells are planned to place. The flipflops should not be placed on the preplaced cells, because their location is fixed. The clock port drives the cells continuously, so the least resistance path is required for the clock.


*Logical Cell Placement*:

Logical cells are the building blocks of the digital circuitry within the IC. They can be standard cells (pre-designed functional blocks like AND gates, flip-flops, etc.) or custom-designed blocks for specific functions.
Logical cell placement determines where these cells are physically located on the chip's silicon die.
Placement algorithms aim to optimize factors such as signal delay, power consumption, and area utilization.

*Blockages*:

Blockages are reserved areas on the chip where no logic cells or routing can be placed. They are used for various purposes:

Keep-Out Regions: Blockages can be used to define regions that must be kept clear for specific reasons, such as accommodating external connectors, avoiding sensitive analog components, or leaving space for test structures.

Power and Ground Grids: Blockages are used to reserve space for power and ground grids, ensuring that there is enough room for the distribution of power and ground across the chip.

Custom Circuitry: In mixed-signal IC design, blockages can reserve space for custom analog circuitry that requires isolation from digital components.

Routing Channels: Blockages may define areas where routing channels are allowed, ensuring there's enough room for signal traces.

Isolation: Blockages can isolate sensitive regions from noisy or high-power areas to prevent interference.
Blockages are typically defined using design rules and constraints provided by the IC design tools.

*Timing and Optimization*:

The placement of pins, logical cells, and blockages can significantly impact the overall performance of the IC in terms of speed, power, and area.
Timing-driven placement algorithms aim to optimize the placement to meet specific performance goals, such as maximum clock frequency.
Placement tools may use iterative algorithms to improve placement based on timing, power, and area constraints.

*Iterative Process*:

The placement process is often iterative, involving multiple runs of placement tools to fine-tune the arrangement of pins, cells, and blockages.
Effective pin placement, logical cell placement, and blockage definition are crucial for achieving a well-balanced IC design that meets the desired performance, power, and area requirements while adhering to design constraints and objectives. These steps are part of the broader physical design process in semiconductor manufacturing.

**6. Step to run floorplan using openLANE and Labs**:

OpenLANE is an open-source digital ASIC (Application-Specific Integrated Circuit) design flow that includes various stages of ASIC design, including floorplanning. Floorplanning is the process of determining the approximate placement of logical cells, I/O pads, and power distribution on a semiconductor die. Below are the steps to run floorplanning using OpenLANE:

*Setup Environment:*
Open a terminal and navigate to the directory where OpenLANE is installed.

*Prepare Your Design*:
Create or obtain the RTL (Register Transfer Level) description of your digital design. This is typically provided as Verilog or VHDL files.

*Design Configuration*:
Specify your design and configuration in the OpenLANE configuration file (designs/design_name/config.tcl). You need to provide details like your target technology, design name, library paths, and other parameters relevant to your design.

*Floorplanning:*
Run the floorplanning stage using OpenLANE. In the terminal, execute the following command, replacing design_name with the name of your design:

bash
```ruby
./flow.tcl -design design_name -init_design -tag floorplan
```
This command will initiate the floorplanning process for your design.

*Review Floorplan Results*:
After the floorplanning process is complete, you can examine the results, including the generated floorplan and floorplan-related reports, in the designs/design_name/runs/floorplan directory.

*Refinement*:
Depending on the results of the initial floorplanning, you may need to refine the floorplan to meet specific design goals or constraints.
Adjustments may include optimizing the placement of logical cells, I/O pads, power grid structures, and blockages.

*Iterate as Necessary*:
Floorplanning is an iterative process, and you may need to run the floorplanning stage multiple times while refining the floorplan until you achieve the desired results.

*Document and Analyze*:
Document your floorplan decisions and analyze the floorplan's impact on aspects like signal routing, power distribution, and overall chip performance.

*Continue with the Design Flow*:
Once you are satisfied with the floorplan, you can proceed with the subsequent stages of the OpenLANE design flow, including placement, routing, and physical verification.
It's important to note that the specific steps and configuration parameters may vary depending on your design, target technology, and design goals. Therefore, you should refer to the OpenLANE documentation and the documentation for your specific technology library for detailed guidance on using OpenLANE for floorplanning and the entire 
ASIC design flow.


**Labs**
Running the floorplan using the command *run_floorplan*
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/8.png">

</details>
<details>
<summary>Labs (Floorplan using openLANE) </summary>

Running the floorplan using the command run_floorplan

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/run_floorplan_rpt_4.png">

The values chosen are chosen based on set of prioprities, the least pripriority is for floorplan.tcl then config.tcl in designs and the highest is for sky130A_sky130_fd_sc_hd.tcl

1.floorplan.tcl

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/floorplaning_default_rpt_2.png">

2.config.tcl in design chacha folder

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/confi.tcl_rpt_3.png">

3. sky130A_sky130_fd_sc_hd.tcl in chacha directory

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/io_place_log_rpt_5.png">

The values chosen in our case are utilization ratio 35 , vertical metal layer as 2 , horizonatal metal layer as 3

The reult is stored as .def file

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/floorplan_def_7.png">

command to invoke magic is
```ruby
magic -T <path_of_tech_file> lef read <path_of_lef_file> def read <path_of_def_file>
```

The floorplan in magic is as follows



<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/floorplan_sch_8.png">

As the mode is set to 1 all the pins are equidistant

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/floorplan_sch_detail_9.png">

We can select and check its metal layer by just selecting it in magic and giving what command in tkkon2.3



<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/8.png">

<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/8.png">




</details>
<details>
<summary>Library Binding and Placement</summary>

**1. Netlist Binding and initial place design**:


Netlist binding and initial placement design are important steps in the physical design of integrated circuits (ICs). These steps involve associating logical components from a netlist with physical locations on a semiconductor die or chip. Here's an overview of these two processes:

Netlist Binding:

Netlist binding is the process of mapping logical components and connections from a high-level or RTL (Register-Transfer Level) design description to their corresponding physical representations. This step bridges the gap between the logical and physical domains, setting the stage for the subsequent stages of physical design. The key aspects of netlist binding include:

Cell Mapping: Assign logical cells or gates from the library to the components specified in the netlist. For example, map AND gates, OR gates, flip-flops, and other logical elements to their physical representations in the technology library.

Pin Assignment: Determine the physical locations (coordinates) of each pin on the cells. This step is critical for ensuring that connections between cells are feasible and optimized for performance.

Logical-to-Physical Connection: Create physical connections (wires and interconnects) between the pins of logical cells based on the netlist's connectivity information. These connections will be further optimized in later stages.

Constraint Consideration: Account for design constraints, such as timing, power, and area requirements, during netlist binding. These constraints influence the placement and routing of cells.

Initial Place Design:

Initial place design, also known as placement, is the process of determining the initial physical positions of logical cells or gates on the semiconductor die or chip. The goal is to find an arrangement that optimizes various aspects of the design, including signal timing, power consumption, and area utilization. The key aspects of initial place design include:

Floorplanning: Create a preliminary floorplan that defines the approximate locations and sizes of functional blocks or regions within the chip. This includes areas for logic cells, I/O pads, memory, and other components.

Cell Placement: Determine the placement of individual cells or gates within their designated regions. Optimize the placement to minimize signal delays, reduce power consumption, and adhere to design constraints.

Legalization: Ensure that the placement of cells is "legal" and complies with design rules and manufacturing constraints, such as minimum spacing, alignment, and clearances.

Timing-Driven Placement: Consider the timing requirements of the design when placing cells. Place critical cells and clocked elements strategically to minimize critical path delays.

Power Planning: Plan the distribution of power and ground networks to ensure that all cells have access to stable power supplies and that voltage drops are within acceptable limits.

Iterative Refinement: Initial placement is often an iterative process, as placement decisions can impact other stages of physical design. Refinement is done to improve overall design quality.

Both netlist binding and initial place design are foundational steps in the physical design flow of integrated circuits. They set the stage for subsequent stages such as routing, clock tree synthesis, and physical verification. The goal is to achieve a well-balanced placement that meets performance goals while adhering to manufacturing constraints and design specifications.


**2.Optimize placement using estimated wire-length and capacitance**



Optimizing placement using estimated wirelength and capacitance is a common technique in physical design automation for integrated circuits. This approach focuses on improving the initial placement of logical cells by considering the estimated wirelength (interconnect length) and capacitance (interconnect capacitance) between the cells. The goal is to minimize signal delays, reduce power consumption, and improve overall circuit performance. Here's how this optimization process typically works:

Initial Placement:

Start with an initial placement of logical cells on the chip's layout. This placement may be generated through floorplanning and initial placement algorithms.
Wirelength Estimation:

Estimate the total wirelength or interconnect length between all pairs of logical cells in the current placement. This estimation can be based on factors like Manhattan distance or other distance metrics between cell centroids.
Capacitance Estimation:

Estimate the interconnect capacitance associated with each net (interconnecting wires) in the design. The capacitance estimation considers the length, width, and layer stack of the wires.
Calculate Signal Delay:

Using the estimated wirelength and capacitance values, calculate the signal delay for each net or signal path in the design. The delay estimation can be based on the RC time constant, where R represents the resistance and C represents the capacitance.
Objective Function:

Define an objective function that combines wirelength and capacitance with other optimization goals, such as minimizing total signal delay or power consumption. The specific form of the objective function depends on the design goals and constraints.
Placement Optimization Algorithm:

Apply a placement optimization algorithm that aims to minimize the objective function. Common optimization techniques include simulated annealing, genetic algorithms, and gradient descent methods.
Iterative Refinement:

The optimization algorithm iteratively adjusts the placement of cells to reduce wirelength and minimize capacitance-induced signal delays. During each iteration, the algorithm may swap, move, or perturb cell positions while respecting placement constraints.
Timing-Driven Considerations:

In many cases, the placement optimization is timing-driven, meaning it prioritizes reducing signal delays for critical paths and meeting required timing constraints.
Convergence:

The optimization process continues until a convergence criterion is met, such as a specified number of iterations or when the objective function reaches a satisfactory value.
Final Placement:

Once the optimization process is complete, the resulting placement is considered the final optimized placement, which should provide improved wirelength and capacitance characteristics.
Verification and Analysis:

Verify the final placement using timing analysis, power analysis, and other verification techniques to ensure that it meets the design requirements and constraints.
Optimizing placement using wirelength and capacitance estimation is a valuable technique for improving the performance of digital integrated circuits. It helps balance the trade-offs between area utilization, signal timing, and power consumption, ultimately leading to more efficient and high-performance designs

**3.Final placement optimization**:


Final placement optimization is a crucial step in the physical design of integrated circuits (ICs). It involves refining the initial placement of logical cells to meet design objectives and constraints, such as optimizing timing, power, and area utilization. Here are the key aspects and techniques involved in final placement optimization:

Objective Function Definition:

Define an objective function that quantifies the quality of the placement. The objective function may include multiple factors, such as wirelength minimization, timing optimization, and power reduction.
Wirelength Minimization:

Minimize the total wirelength or interconnect length between logical cells. This helps reduce signal propagation delays and power consumption associated with interconnects.
Timing-Driven Placement:

Prioritize timing-driven placement to meet critical path requirements. Identify critical paths and ensure that the placement minimizes delays along these paths. This is essential for achieving the desired operating frequency.
Power Optimization:

Optimize power consumption by considering the proximity of cells to reduce coupling capacitance and minimize dynamic power. Techniques like placement-aware clock gating can also be employed.
Area Constraints:

Adhere to area constraints and floorplan requirements while optimizing the placement. Ensure that the placement fits within the specified chip area and adheres to blockages and design rules.
Iterative Algorithms:

Employ iterative placement optimization algorithms, such as simulated annealing, genetic algorithms, or gradient-based methods. These algorithms iteratively adjust the positions of cells to improve the objective function.
Legalization:

Ensure that the placement remains legal and complies with design rules and constraints throughout the optimization process. Legalization may involve adjusting the positions of cells to meet spacing and alignment requirements.
Congestion Mitigation:

Address congestion issues that arise during placement optimization. Congestion occurs when certain regions of the chip become densely populated with cells. Techniques like congestion-aware placement can help alleviate this problem.
Noise and Signal Integrity:

Consider signal integrity and noise issues during placement optimization. Optimize cell locations to minimize cross-talk and electromagnetic interference (EMI) while meeting signal timing requirements.
Clock Tree Synthesis (CTS):

If applicable, integrate clock tree synthesis with placement optimization to ensure that clock signals are distributed efficiently and with minimal skew.
Timing Constraints and Feedback:

Continuously monitor and enforce timing constraints during placement optimization. Feedback from timing analysis tools can guide the placement adjustments to meet timing goals.
Post-Placement Optimization:

After final placement, perform post-placement optimization steps, such as detailed routing and buffer insertion, to further refine the design for better timing and power characteristics.
Verification and Analysis:

Verify the final placement using various analyses, including static timing analysis (STA), power analysis, and signal integrity checks, to ensure that it meets design specifications and constraints.
Convergence Criteria:

Establish convergence criteria for the optimization process, such as a maximum number of iterations or a target objective function value.
Documentation:

Document the final placement and any design trade-offs made during the optimization process. This documentation is crucial for future reference and collaboration with other design teams.
Final placement optimization is an iterative and resource-intensive process, and the specific techniques used may vary depending on the design goals and constraints. Achieving an optimal placement is essential for the overall performance and manufacturability of digital integrated circuits.





**4.Need for libraries and characterization**:
Libraries and characterization are essential components of the design and development process for digital integrated circuits. They serve crucial roles in ensuring the accuracy, efficiency, and reliability of circuit design. Here's why libraries and characterization are necessary:

Component Reusability:

Libraries provide a collection of pre-designed and pre-characterized building blocks, such as logic gates, flip-flops, and memory cells. These components can be reused across various projects, saving time and effort in the design process.
Standardization:

Libraries adhere to industry-standard specifications and design rules. This standardization ensures consistency and compatibility in designs, making it easier to integrate third-party IP (intellectual property) and collaborate across different design teams and organizations.
Characterization for Accuracy:

Characterization involves detailed testing and simulation of library components under various operating conditions. This process produces accurate models and data that reflect the real-world behavior of the components. Without characterization, designers would rely on theoretical models, which may not accurately represent the physical behavior of the components.
Timing Analysis:

Characterization data, such as delay, setup time, and hold time, are crucial for timing analysis during the design process. They help ensure that signals meet their timing requirements and that the circuit operates reliably at the desired clock frequency.
Power Analysis:

Characterization provides information on power consumption for different library components. Power data is vital for estimating the overall power consumption of a chip and optimizing it for low power operation.
Area Estimation:

Libraries include information about the physical size (area) of each component. This data is essential for estimating the chip's total area utilization and ensuring that it fits within the available silicon area.
Manufacturability:

Libraries consider manufacturing process parameters, such as transistor sizes and process-specific design rules. This helps designers create designs that are manufacturable within a specific semiconductor technology.
Simulation and Validation:

Characterization data allows designers to simulate and validate their designs with high accuracy. It enables designers to identify and address potential issues early in the design process, reducing the risk of costly errors and redesigns.
IP Integration:

Libraries often include intellectual property (IP) blocks, such as analog components, communication interfaces, and processors. These IP blocks are characterized and tested to ensure seamless integration into custom designs.
Efficiency and Productivity:

Using pre-characterized libraries significantly improves design efficiency and productivity. Designers can focus on the high-level aspects of their projects without needing to design and validate every component from scratch.
Quality Assurance:

Libraries and characterization data undergo rigorous quality assurance processes to ensure their accuracy and reliability. This quality assurance contributes to the overall quality and robustness of the final design.
In summary, libraries and characterization are fundamental tools in the field of digital integrated circuit design. They facilitate component reuse, standardization, accuracy, and efficiency in the design process, ultimately leading to the development of reliable and high-performance integrated circuits.

**5.Congestion aware placement using RePlace**:


</details>
<details>
<summary>Cell Design and characterization flows</summary>

**1.Inputs for cell design flow**:

The cell design flow, which involves the creation and optimization of standard cells for digital integrated circuits, encompasses several important steps and considerations. Here are the key inputs and steps in the cell design flow:

*Specification and Requirements:*
Clearly define the specifications and requirements of the standard cell library. This includes factors like the target technology (e.g., CMOS, FinFET), voltage levels, maximum operating frequency, power consumption, and the desired library variants (e.g., low-power, high-speed).

*Technology Data:*
Gather or access technology-specific data, such as the process design kit (PDK), which includes information about transistor sizes, metal layers, interconnects, and other technology-specific parameters. The PDK is essential for designing cells that are compatible with the target manufacturing process.

*Cell Characterization:*
Perform transistor-level characterization of the library cells. This involves simulating the behavior of individual standard cells to generate data on their timing characteristics (delay, setup time, hold time), power consumption, and area usage under various operating conditions.

*Cell Templates:*
Create cell templates or templates for different logic functions (AND gates, OR gates, flip-flops, etc.). These templates serve as the basis for designing individual cells.

*Transistor Sizing:*
Determine the appropriate transistor sizes for each cell based on performance and power considerations. The sizing is a crucial aspect of cell optimization.

*Layout Design:*
Design the physical layout of each standard cell. This involves placing and connecting transistors and other components to create the cell's logic functionality.
Adhere to design rules and manufacturing constraints provided by the PDK to ensure manufacturability.

*Liberty Format*:
Generate Liberty format files (.lib) for each standard cell. These files contain timing, power, and area information and are used by synthesis tools during the design of larger digital circuits.

*Timing Models:*
Develop timing models that describe the cell's behavior under different operating conditions (e.g., corner cases, voltage levels). Timing models include delay, setup time, hold time, and other timing-related information.

*Functional Verification:*
Perform functional verification of each standard cell to ensure it performs its intended logic function correctly.

*Physical Verification:*
Perform physical verification checks, such as Design Rule Checking (DRC) and Layout vs. Schematic (LVS), to ensure that the cell layout complies with the manufacturing process rules.

*Power Analysis:*
Conduct power analysis to estimate the power consumption of each standard cell under different operating conditions and load scenarios.

*Library Characterization*:
Characterize the entire standard cell library as a whole, considering corner cases and variations, to create a comprehensive library characterization database.

*Documentation*:
Create documentation for the standard cell library, including datasheets, usage guidelines, and documentation on how to integrate the library into the design flow.

*Quality Assurance*:
Implement a rigorous quality assurance process to validate the accuracy and reliability of the standard cells.

*Release and Integration*:
Once the library is validated and meets all requirements, it can be released for integration into larger digital design projects.
The cell design flow is an essential part of ASIC (Application-Specific Integrated Circuit) and FPGA (Field-Programmable Gate Array) design processes, providing the fundamental building blocks for designing complex digital circuits. The quality and efficiency of the cell design flow directly impact the performance, power consumption, and manufacturability of digital integrated circuits.

**2.Circuit Design step**:

Circuit design is a systematic process used to create electronic circuits for various applications, from simple analog circuits to complex digital integrated circuits. The process typically involves several steps to ensure that the circuit meets the desired functionality, performance, and reliability requirements. Here are the key steps in the circuit design process:

*Define Requirements and Specifications:*
Begin by clearly defining the requirements and specifications of the circuit. Understand the purpose of the circuit, its input and output characteristics, power requirements, operating conditions, and any specific constraints or standards it must meet.

*Conceptual Design:*
Create a high-level conceptual design or block diagram of the circuit. Identify the major functional blocks and their interconnections. This step helps in visualizing the overall architecture of the circuit.

*Component Selection:*
Choose electronic components, such as resistors, capacitors, transistors, integrated circuits, and sensors, based on the circuit's requirements. Consider factors like component tolerances, voltage and current ratings, and availability.

*Schematic Design:*
Create a detailed schematic diagram of the circuit using a schematic capture tool. Represent each component and its connections accurately. Pay attention to signal paths, power distribution, and ground connections.

*Simulate and Analyze:*
Use circuit simulation software to analyze and validate the design. Simulate the circuit's behavior under various operating conditions to ensure it meets the desired performance and functionality.

*Component Footprint and PCB Layout:*
If the circuit is to be implemented on a printed circuit board (PCB), create component footprints and design the PCB layout. Consider factors like component placement, routing, and signal integrity.

*BOM (Bill of Materials) Generation:*
Create a BOM that lists all the components needed for the circuit. Include part numbers, quantities, and suppliers.

*Prototyping:*
Build a prototype of the circuit on a breadboard or PCB. Verify that the physical implementation matches the schematic and that the circuit behaves as expected.

*Testing and Debugging:*
Test the prototype rigorously to ensure it meets the specifications. Debug and troubleshoot any issues that arise during testing.

*Optimization:*
Optimize the circuit for factors like power consumption, size, cost, and performance. Make necessary adjustments to improve efficiency and meet design goals.

*Documentation:*
Create comprehensive documentation for the circuit, including schematics, PCB layout files, assembly instructions, and user manuals. Well-documented designs are essential for future reference and replication.

*Compliance and Certification:*
If the circuit must adhere to specific standards or regulations (e.g., safety standards, electromagnetic compatibility), perform the necessary tests and obtain certifications as required.

*Production and Manufacturing:*
Once the design is finalized and tested, it can be sent for production. Ensure that the manufacturing process aligns with the design specifications and quality standards.

*Lifecycle Management:*
Continuously monitor and manage the circuit's lifecycle, including updates, maintenance, and potential redesigns as technology evolves or requirements change.

*Quality Assurance:*
Implement quality assurance practices throughout the design process to ensure the circuit meets all performance and reliability standards.

*Documentation Updates:*
Keep documentation up to date with any design changes or improvements made during the product's lifecycle.
Circuit design is an iterative process, and designers may revisit various steps as they refine and optimize the circuit to meet evolving requirements or address issues discovered during testing and deployment. Effective communication and collaboration among multidisciplinary teams of engineers (electrical, mechanical, software, etc.) are essential for successful circuit design projects.

**3.Layout Design step**:

Layout design, also known as physical design, is a critical phase in integrated circuit (IC) design that involves translating a schematic or logical representation of a circuit into the physical layout on a silicon wafer or printed circuit board (PCB). This process includes determining the physical placement and interconnection of transistors, gates, and other components. Below are the key steps in layout design:

*Schematic-to-Layout Translation:*
Start with a schematic diagram that represents the logical connections and components in your circuit. This schematic serves as a blueprint for the layout.

*Floorplanning:*
Create a floorplan that defines the overall arrangement of different functional blocks or areas on the chip or PCB. Allocate space for components, power grid, clock distribution, and I/O pads.

*Component Placement:*
Place individual components (transistors, gates, etc.) onto the layout according to the floorplan. Ensure that components are placed optimally to minimize signal delay, power consumption, and area usage.

*Routing:*
Create the interconnections (wires) between components based on the schematic connections. Consider routing constraints, such as minimum wire widths, spacing, and layers.

*Power Distribution:*
Design the power distribution network to deliver a stable and low-noise power supply to all components. Include power rails, ground lines, and decoupling capacitors to reduce voltage drops and noise.

*Signal Integrity:*
Ensure signal integrity by minimizing signal propagation delays, avoiding cross-talk between neighboring signals, and maintaining controlled impedance for high-speed signals.

*Clock Tree Synthesis (CTS):*
If your design includes clocked elements, create a clock tree to distribute clock signals to various parts of the chip efficiently and with minimal skew.

*Design Rule Checking (DRC):*
Perform DRC checks to verify that the layout adheres to manufacturing-specific design rules, such as minimum feature sizes, spacing, and other constraints defined by the technology process.

*Layout vs. Schematic (LVS) Verification:*
Compare the physical layout with the original schematic to ensure that they match. LVS checks for consistency in connectivity and component placement.

*Extraction and Parasitic Modeling:*
Extract parasitic elements (e.g., capacitance and resistance) from the layout and create accurate models for use in simulation tools. These models account for real-world effects on signal behavior.

*Design for Manufacturing (DFM):*
Consider design for manufacturing principles to enhance yield and manufacturability. Address manufacturing issues early in the design to prevent costly rework.

*Electromigration and IR Drop Analysis:*
Analyze the layout for potential electromigration issues, where excessive current density can cause metal migration. Also, perform IR drop analysis to ensure that power and ground distribution meet voltage requirements.

*Physical Verification:*
Run physical verification tools to check for compliance with additional design rules, such as antenna rules, well-tap rules, and more.

*Tapeout:*
Prepare the final layout for tapeout, which is the process of sending the design data to a semiconductor foundry for fabrication or to a PCB manufacturer for PCB production.

*Documentation:*
Create comprehensive documentation that includes the layout files, design rules, constraints, and any other information needed for future reference and collaboration.

*Post-Layout Simulation:*
Perform post-layout simulation to verify the circuit's performance based on the extracted parasitic elements and to ensure that it meets the desired specifications.

*Iterative Optimization:*
Iterate through the layout design process to optimize the layout for performance, power, and area while addressing any identified issues.
Layout design is a complex and iterative process that requires a deep understanding of semiconductor technology, manufacturing processes, and electronic design principles. Collaboration with teams specializing in physical design and verification is essential for successful layout design in modern semiconductor and PCB industries.

**4.Typical characterization flow**:

Characterization is a critical step in the design and verification of digital integrated circuits. It involves analyzing and documenting the electrical behavior of the circuit over a range of operating conditions and corner cases. Characterization provides valuable data for ensuring the circuit meets its performance, power, and timing specifications. Here's a typical characterization flow for digital integrated circuits:

*Define Objectives:*
Clearly define the objectives and goals of the characterization process. Identify the key parameters and metrics to be characterized, such as delay, power consumption, and setup/hold times.

*Select Testbenches:*
Choose appropriate testbenches and input vectors that cover a wide range of operating conditions. This includes different input patterns, clock frequencies, and environmental conditions (e.g., temperature, voltage variations).

*Setup Simulation Environment:*
Set up the simulation environment using electronic design automation (EDA) tools. Ensure that the simulation setup accurately represents the target technology, including the process parameters, libraries, and design constraints.

*Corner Cases:*
Identify corner cases, which are extreme or worst-case scenarios that the circuit may encounter. These include process corners (fast, slow, typical), temperature extremes, and voltage variations.

*Monte Carlo Analysis:*
Conduct Monte Carlo analysis to account for manufacturing process variations. This involves running simulations with randomized process parameter values to assess the circuit's sensitivity to manufacturing variations.

*Static Timing Analysis (STA):*
Perform static timing analysis to measure critical path delays, setup times, and hold times for different operating conditions. Ensure that the circuit meets its timing requirements.

*Power Analysis:*
Analyze power consumption under various conditions, including active, standby, and power-down modes. Characterize dynamic and static power for different input patterns and frequencies.

*Noise and Signal Integrity Analysis:*
Evaluate noise margins and signal integrity by simulating noise-induced glitches and verifying that signals meet their logic level requirements.

*Functional Verification:*
Verify that the circuit functions correctly under all operating conditions. Ensure that it produces the expected outputs for various input vectors.

*Generate Characterization Reports:*
Generate detailed characterization reports that include all measured data, simulation results, and statistical analysis. These reports serve as a reference for circuit performance and are valuable for design validation.

*Create Libraries:*
Based on the characterization data, create libraries or models (e.g., Liberty format) that describe the circuit's behavior under different conditions. These libraries are used in subsequent stages of the design flow, such as synthesis and place-and-route.
 
*Optimization and Iteration:*
Review the characterization results to identify areas for optimization. Iterate through the design and characterization process to improve performance, reduce power consumption, and meet specifications.

*Documentation and Compliance:*
Document all relevant data, assumptions, and methodologies used in the characterization process. Ensure that the design complies with industry standards and specifications.

*Review and Validation:*
Review the characterization results with cross-functional teams, including design, verification, and manufacturing experts, to validate the circuit's performance and reliability.

*Tapeout and Production:*
Once characterization is complete and the circuit meets all requirements, proceed with the tapeout process to prepare the design for fabrication or production.

*Post-Silicon Validation (for ASICs):*
After the silicon chip is manufactured, conduct post-silicon validation to compare real-world measurements with the characterization data. This step helps verify that the chip behaves as expected.
A well-executed characterization flow is crucial for ensuring that digital integrated circuits perform reliably across a range of operating conditions and manufacturing variations. It provides confidence that the circuit will meet its intended specifications and requirements in real-world applications.

</details>
<details>
<summary>Genral Timing characterization Parameter </summary>

**1. Timing threshold definition**:

In digital integrated circuit design, timing thresholds are critical parameters used to specify the acceptable timing margins or constraints for various signals within the circuit. These thresholds help ensure that the circuit operates correctly and reliably by defining when signals should arrive at their destinations with respect to clock edges. Here are some common timing threshold definitions:

*Setup Time (Tsu)*:
Setup time is the minimum time before the clock edge at which a data input signal (e.g., a flip-flop's D input) must be stable and valid for the flip-flop to correctly capture the data.
Mathematically, it is defined as Tsu = T_clk - T_data, where T_clk is the clock edge time, and T_data is the data input transition time.
Violating the setup time can lead to metastability issues or incorrect data capture.

*Hold Time (Thold)*:
Hold time is the minimum time after the clock edge during which the data input signal must remain stable and valid for the flip-flop to correctly capture the data.
Mathematically, it is defined as Thold = T_data - T_clk, where T_data is the data input transition time, and T_clk is the clock edge time.
Violating the hold time can lead to data corruption.

*Clock-to-Q Delay (Tcq):*
Clock-to-Q delay is the time it takes for a flip-flop's output (Q) to change after a clock edge.
It is crucial for determining the maximum clock frequency at which the circuit can operate reliably.
Violating the clock-to-Q delay can result in timing violations and race conditions.

*Propagation Delay (Tpd):*
Propagation delay represents the time it takes for a signal to travel through a combinational logic path from the input to the output.
It includes both the input delay and the gate delay.
Violating the propagation delay can lead to incorrect signal timing and logic errors.

*Clock Skew*:
Clock skew is the variation in arrival times of the clock signal at different flip-flops within the same clock domain.
It can cause timing violations and affect circuit performance.
Designers often aim to minimize clock skew to ensure synchronous operation.

*Max Frequency (Fmax)*:
Max frequency is the highest clock frequency at which the circuit can operate while meeting all timing constraints.
It is determined by the critical path delay, which includes setup and propagation times.
Achieving a higher Fmax is a common goal in design optimization.

*Setup Slack and Hold Slack*:
Slack represents the amount of time by which a signal's timing margin exceeds or falls short of the required setup or hold time.
Positive slack indicates that the timing margin is met, while negative slack indicates a timing violation.
Slack values are important for identifying critical paths and areas for optimization.
These timing thresholds and constraints are essential for ensuring the correct and reliable operation of digital circuits. Designers use various tools and methodologies, including static timing analysis (STA), to verify that these timing thresholds are met during the design process. Meeting these timing constraints is crucial for achieving the desired performance and functionality of digital integrated circuits

**2. Propagation delay and transition time**

Propagation delay and transition time are important timing parameters in digital integrated circuit design. They both play crucial roles in determining the speed and performance of digital circuits. Let's explore each of these concepts:

1.*Propagation Delay*:

Propagation delay, often denoted as Tpd, is the time it takes for a change in the input of a digital gate or circuit to propagate through the gate and appear at its output.
It represents the time delay associated with the signal as it travels through the logic gates, wires, and interconnects in the digital circuit.
Propagation delay is typically measured from the point where the input signal reaches 50% of its final value to the point where the output signal reaches 50% of its final value.
Propagation delay is a key factor in determining the overall speed of a digital circuit. Short propagation delays enable faster operation, while longer delays limit the maximum clock frequency at which the circuit can operate.

2.*Transition Time (or Propagation Time)*:
Transition time, often denoted as Ttr or Tt, refers to the time it takes for the signal to change from one logic level to another within a digital circuit.
It measures the time it takes for the signal to transition from the 10% point (low-to-high transition) to the 90% point (high-to-low transition) of its full voltage swing.
Transition time is a critical parameter for evaluating the signal integrity and timing characteristics of a digital circuit.
Transition Time

Transition time affects the shape and quality of the signal waveform and can impact the setup and hold times of downstream flip-flops or logic gates.
A shorter transition time allows for faster signal switching, which can be advantageous in high-speed designs.
In summary, propagation delay measures the time it takes for a signal to traverse a digital circuit from input to output, while transition time measures the time it takes for a signal to change between logic levels. Both parameters are essential in digital circuit analysis and design, as they influence circuit speed, timing, and signal quality. Designers use these values to ensure that the circuit meets timing constraints and operates reliably at the desired clock frequency.









</details>
<details>
<summary>Labs (Placement using openLANE) </summary>


As the mode is set to 1 all the pins are equidistant
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/placement_rpt_10.png">


The placement in the magic is as follows

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/placement_sch_11.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day16/placement_sch_detail_12.png">

The placement of different images can be seen in the below image





</details>

# Day 17 Design library cell using Magic Layout and ngspice characterization

<details>
<summary>IO Placer Revised</summary>
	
We can change the allignment of the Input/output pins by the changing the FP_IO_MODE. By Default it is set to 1. This can be changed by using the below command
```ruby
set ::env(FP_IO_MODE) 2
```
Before changing the mode the layout in magic

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/floorplan_1.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/floorplan_detail_2.png">

After changing the mode 2

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/readme_floorplan_3.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/floorplan_tcl_4.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/floorplan_layout_aftr_set_2_5.png">

</details>
<details>

<summary>spice simulation for CMOS inverter</summary>

SPICE (Simulation Program with Integrated Circuit Emphasis) is a widely used tool for simulating electronic circuits, including CMOS inverters. To perform a SPICE simulation for a CMOS inverter, you typically need to follow these steps:

1. Create the CMOS Inverter Circuit: You'll need to define the CMOS inverter circuit in a SPICE-compatible format. In this case, a CMOS inverter consists of an NMOS transistor and a PMOS transistor connected in series. Here's an example of a simple CMOS inverter circuit:

Copy code
```ruby
* CMOS Inverter
.model nmos NMOS
.model pmos PMOS
Vdd 1 0 DC 5V
Vin 2 0 DC 0V
M1 3 2 1 1 NMOS
M2 3 2 0 0 PMOS
.DC Vin 0V 5V 0.1V
.PRINT DC V(2) V(3)
.END
```
In this example, M1 is the NMOS transistor, M2 is the PMOS transistor, Vdd is the power supply voltage, and Vin is the input voltage.

2. Specify Model Parameters: You should specify the model parameters for the NMOS and PMOS transistors, including threshold voltage (Vth), channel length (L), channel width (W), mobility, and other relevant parameters. These parameters depend on the technology node and the specific transistors being used.

3. Simulation Commands: Include simulation commands in your SPICE input file to define the type of analysis you want to perform. Common types of analyses for CMOS inverters include DC analysis, transient analysis, and AC analysis.

4. DC Analysis: Simulates the behavior of the circuit under constant (DC) input voltage. In the example above, .DC Vin 0V 5V 0.1V performs a DC sweep of input voltage from 0V to 5V in 0.1V steps.

5. Transient Analysis: Simulates the behavior of the circuit over time. You can apply a pulse or step input and observe how the output voltage changes over time.

6. AC Analysis: Analyzes the frequency response of the circuit. Useful for examining gain, bandwidth, and other AC characteristics.

7. Run the Simulation: Use a SPICE simulator such as LTspice, HSPICE, or ngspice to run the simulation. The specific commands and syntax may vary slightly depending on the simulator you are using.

8. Analyze Simulation Results: After the simulation is complete, you can analyze the results to understand how the CMOS inverter behaves under different input conditions. Common parameters to examine include the input/output characteristics, voltage transfer curve (VTC), rise/fall times, and propagation delay.

9. Optimize and Fine-Tune: Based on the simulation results, you can optimize and fine-tune your CMOS inverter circuit to meet your design specifications and requirements.

SPICE simulations are an essential part of integrated circuit design and allow engineers to predict and understand the behavior of circuits before they are physically fabricated.


-The First task is to create a SPICE Deck file which contains the connectivity information of netlist ,inputs provided, tap points to view outputs.The SPICE is created by defining component connectivity, component values, identifying the nodes and naming them.
-A substrate is a component or pin that requires connectivity information and can be used to adjust the threshold voltages of NMOS and PMOS transistors. The orientation of the substrate pin differs between NMOS and PMOS symbols. Determining the value of output load capacitance involves extensive computational analysis.
-To define the component values for PMOS and NMOS, specifically the W/L ratios (e.g., 0.375μ/0.25μ), it is often assumed that they share the same values, even though PMOS should ideally be twice the size of NMOS. The specified output -capacitance is typically 10fF, and the applied gate voltage is commonly a multiple of the channel length, such as 2.5V. A node is identified when a component is positioned between two nodes.

The defination of components f an CMOS Inverter is as below
```ruby
M1 out in vdd vdd pmos W=0.375u L=0.25u
M2 out in 0 0 nmos W=0.375u W=0.25u
cload out 0 10f
Vdd vdd 0 2.5
Vin in 0 2.5
```
M1 component is the PMOS whose drain is connected to OUT , Gate is connected to IN , Substrate and Source are connected to vdd.It also contains the W/L ratio.
M2 component is the NMOS whose drain is connected to OUT , Gate is connected to IN , Substrate and Source are connected to 0.It also contains the W/L ratio.
The load capacitance is connected between out port and ground and the value is 10fF. Similarly, the supply voltages are connected between groud and respective nodes and the voltage is 2.5V.
The Simulation commands are as follows
```ruby
.op
.dc Vin 0 2.5 0.05
.LIB "tsmc_025um_model.mod" CMOS_MODELS
.end
```
This command implies that gate voltage is varied from 0 to 2.5V in steps of 0.05V. This is done to note the output characteristics with respect to input voltage. The model file must be described as follows that contains the complete model description of NMOS and PMOS of the length.

The layout of the CMOS inverter is as follows

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/spice%20file%20created_6.png">


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/vim_spice_7.png">


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/vim_spice_code_8.png">
</details>
<details>


<summary>16 Mask CMOS fabrication process</summary>

The term "16-mask CMOS fabrication" refers to the process of manufacturing complementary metal-oxide-semiconductor (CMOS) integrated circuits using 16 distinct photolithography masks. CMOS technology is widely used in the semiconductor industry for building digital and analog integrated circuits, including microprocessors, memory chips, and various other electronic devices. Each mask in the fabrication process plays a crucial role in defining different aspects of the integrated circuit's design and functionality.

Here is a general overview of the steps involved in a typical 16-mask CMOS fabrication process:

1. Substrate Preparation: The process starts with a silicon wafer, which serves as the base material. The wafer is cleaned and polished to remove impurities.

2. Oxidation: A thin layer of silicon dioxide (SiO2) is grown or deposited on the wafer's surface. This oxide layer serves as an insulating layer and can be used to create gate oxides for transistors.

3. N-Well and P-Well Formation: The wafer is then exposed to a mask to define areas for N-wells (for NMOS transistors) and P-wells (for PMOS transistors). These regions are implanted or diffused with the appropriate dopants to create the desired conductivity types.

4. Gate Oxide Formation: Another mask is used to define the areas where gate oxides will be formed for the transistors. The gate oxide insulates the gate electrode from the semiconductor material.

5. Gate Electrode Formation: A mask is employed to define the gate electrode areas for both NMOS and PMOS transistors. Polysilicon is typically used for gate electrodes.

6. Source/Drain Implantation: Masks are used to define the source and drain regions of the transistors. Dopants are implanted or diffused into the silicon to create the necessary regions.

7. Interlayer Dielectric (ILD) Deposition: A layer of insulating material (often SiO2) is deposited and planarized. This layer isolates different components and provides a foundation for the metal interconnect layers.

8. Contact and Via Formation: Masks are used to define contact holes and vias in the ILD, allowing for connections between different layers of the integrated circuit.

9. Metal Layer Deposition: Metal layers are deposited, and masks are used to define the metal interconnects that connect various parts of the circuit.

10. Passivation Layer: A final mask may be used to define openings for a passivation layer, which protects the integrated circuit and provides a smooth surface.

11. Testing and Inspection: The fabricated wafer is tested and inspected to ensure it meets the desired specifications.

12. Dicing: The wafer is cut into individual chips.

13. Packaging: Each chip is packaged for protection and connection to external devices.

The specific details of each mask and the exact fabrication steps can vary depending on the desired circuit and technology node. Advanced semiconductor processes may require even more masks and complex steps. The goal is to create functional and reliable integrated circuits with a high level of precision and performance.


**CMOS Inverter layout in Magic**

When a poly crosses n-diffusion it is NMOS

In Magic if we select that and give what in tkcon window we get

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/inv%20layout_output_y1.png">

When a poly crosses n-diffusion it is PMOS

In Magic if we select that and give what in tkcon window we get


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/inv%20layout_pmos_what_y2.png">

The connection of Y with the drain of PMOS and NMOS is as shown in the figure

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/inv%20layout_nmos_what_y3.png">


The other connection of Source of PMOS and Source of NMOS are as follows

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/inv%20layout_pmos_source_y4.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/inv%20layout_nmos_source_y5.png">

</details>
<details>
<summary>Labs on DRC</summary>

First we need to clone the open_pdks.git from RTimothyEdwards
These are list of various .mags in the directory



The met3.mag is as shown below
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img1x.PNG">

Now we see that rule 3.4 is not the visible one but we can visualize it as follows

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img19.PNG">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img18.PNG">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img17.PNG">

Now we load poly

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img16.png">

<img  width="1085" alt="" src="">


These violations can be rectified by editing the .tech files drc rules

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img15.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img14.png">


The other violations and their corrections are as follows

1.First we need to copy the 3 poly metal and paste it into 2 different places and add pmos and nmos substrate and contact. This is to fix the issue with poly resistor spacing to diff and tap.Then we edit the .tech files to rectify this.


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img12.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img11.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img10.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img09.png">

Second one is describing DRC errors as geometrical construct

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img07.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img06.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img05.png">

Shrinking the Nwell to fix the NMOS 6 drc violation

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img04.png">


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img03.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img02.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day18/img01.png">


</details>

# Day 18 Pre-layout timing analysis and importance of good clock tree

<details>
<summary>Timing modelling using delay tables</summary>

**Lab 1: Lab steps to convert grid info to track info**

*Lab steps to convert grid info to track info*

 **Library Exchange Format (LEF)**
-A specification in which representing the physical layout of an integrated circuit in an ASCII format
-It includes design rules and abstract information about the standard cells
-LEF only has basic information required at that level to serve the purpose of the concerned CAD tool
-Containing information on input, output, power and group port, does not consists logic path information
*Objective*: extract LEF file from .mag file and then plug the file into the picorv32a flow (previous is standard cell library)

-Main guidelines:
1. The input and output ports must lie on the intersection of the vertical and horizontal tracks
2.The width of standard cell should be on the track pitch, and the height should be on the track vertical pitch

```ruby
~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd
vim tracks.info
```

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
magic -T sky130A.tech sky130_inv.mag
```
*Track information (using during routing stage) routes can go over the track/layer (metal traces)*

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_layout_2.png">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/track%20info_1.png">


**Lab 2: Lab steps to convert magic layout to std cell LEF**

 *Lab steps to convert magic layout to std cell LEF*
-We need to only define layers, not ports in layout
-Ports definitions are required when we want to extract LEF file
-Ports will be defined as pins of a macro

*How to define ports?*

    Select port --> edit --> Text --> fill those required information

Note: For A; and Y in locali while for VPWR and VGND in metal1
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_layout_A_input_3.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_layout_Y_output_4.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_layout_top_pmos_5.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_layout_BOTTOM_NMOS_6.png">

Then, define classes of ports

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/inv_port%20vgnd_7.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/port_8.png">


    Extract the LEF file

    In tkcon
```ruby
save sky130A_vsdinv.mag
```
    Checking the saved file
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
ls
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/create%20_vsdinv.mag_file_9.png">

```ruby
magic -T sky130A.tech sky130_vsdinv.mag
```
    In tkcon
```ruby
lef write
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/created_lef_file_10.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/lef_file_detail_11.png">

*vim sky130_vsdinv.lef*

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/lib_typical_12.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/lib_slow_13.png">


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/lib_fast_14.png">

**Lab 3: Introduction to timing libs and steps to include new cell in synthesis**

**Introduction to timing libs and steps to include new cell in synthesis**
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
cp sky130A_vsdinv.lef /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/libs
cp sky130_fd_sc_hd__* /home/nur.nazahah.mohd.amri/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/
vim config.tcl
```
*Modifying config.tcl file*

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/config_tcl_16A.png">


```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
make mount
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 13-01_14-09 -overwrite      (Check run date at ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs)
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
run_synthesis
```

Successfully invoke openlane and doing synthesis

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/synthesis%20successful.png">


**Theory 1: Introduction to delay tables**

**Introduction to delay tables**

-With the use of gates for clock nets, such as shown in the below figure, which is the method known as clock gating, we can ensure no dynamic switching and short circuit power consumed by the clock tree, during the time the clock gets gated.


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/123.png">



1. We need to look into the timing characteristics of the buffer, in the case where we want to swap out the buffer for a gate.
2.For each level of buffering, we should have an identical buffer being used, and each node should be driving the same node.
3.Keep in mind that the load at the output will be varying, and since the load of one buffer is varying, the input transition of the following buffer will also vary.
4.This means that we will have a variety of delays.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/1234.png">

1. The delay table is characterized based on varying the input transition and output load of a cell, against the delay of that cell.
2. Each cell will have its own delay table for different sizes and threshold tables.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/12345.png">

**Theory 2: Delay table usage**

**Delay table usage**

-Each type of cell will be having its own individual delay table, as the internal pmos and nmos width/length ratio gets varied, the resistance changes, then RC constant  -gets varied as well, meaning the delay of each cell gets varied.
-The values of delay which are not available in the table are extrapolated based on the given data.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/32.png">


-Similarly, the ways on how we have a delay table, we will also have a characterization table for input transition.
-The latency at the endpoints will be the sum of the delays of each individual cell in that path.
-The total skew value between two endpoints will be non-zero if the output load driven for a cell is varied, meaning different delay numbers are seen between endpoints,   this is why it is preferred to have the nodes at each level driving the same load.
-Another case in which we can retain the skew to be zero in the presence of varied load, is by using a different buffer size at the same level that can achieve the same level of delay as the other buffer in same level based on its delay table.
-These are factors which should be looked into in the early stages of the clock tree design stage.
-Now we must look into power aware CTS, where we have to consider endpoints which are only active under certain conditions.
-In this case, we do not need to propagate the clock into those cells during the period of inactivity.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/321.png">

**Lab 4: Lab steps to configure synthesis settings to fix slack and include vsdinv**

**Lab steps to configure synthesis settings to fix slack and include vsdinv**
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
-SYNTH_STRATEGY: control the area and timing
-SYNTH_BUFFERING: control if we want to buffer high fanout net
-SYNTH_SIZING: control in cell sizing instead of buffering
-SYNTH_DRIVING_CELL: ensure more drive strength cell to drive input

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/synth_strategy.png">

In openlane terminal

```ruby
echo $::env(SYNTH_STRATEGY)
set ::env(SYNTH_STRATEGY) "DELAY 0"
echo $::env(SYNTH_STRATEGY)
echo $::env(SYNTH_BUFFERING)
echo $::env(SYNTH_SIZING)
set ::env(SYNTH_SIZING) 1
echo $::env(SYNTH_SIZING)
echo $::env(SYNTH_DRIVING_CELL)
```
-With SYNTH_STRATEGY of Delay 0, the tool will focus more on optimizing/minimizing the delay, index can be 0 to 3 where 3 is the most optimized for timing (sacrificing more area).
-SYNTH_BUFFERING of 1 ensures cell buffer will be used on high fanout cells to reduce delay due to high capacitance load.
-SYNTH_SIZING of 1 will enable cell sizing where cell will be upsize or downsized as needed to meet timing.
-SYNTH_DRIVING_CELL is the cell used to drive the input ports and is vital for cells with a lot of fan-outs since it needs higher drive strength (larger driving cell needed).

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
rm -rf picorv32a.synthesis.v
```
In openlane terminal

```ruby
run_synthesis
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/synth_strategy_4.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/synth_wns_tns_0000_5.png">

In openlane
```ruby
run_floorplan
```

After that run_placement, another error will occur relating to remove_buffers, the solution is to comment the call to remove_buffers_from_nets in OpenLane/scripts/tcl_commands/placement.tcl.

After successfully running placement, runs/[date]/results/placement/picorv32.def will be created.

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/openroad
vim or_basic_mp.tcl
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands
vim floorplan.tcl
```
*Modification in gvim*

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/macro%20comment_6.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/macro%20comment__2___7.png">

In openlane
```ruby
run_floorplan
run_placement
```
In terminal

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/placement
magic -T ~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/placement_getcell.png">
</details>
<details>

<summary>Timing analysis with ideal clocks using openSTA</summary>
	
**Theory 1: Setup timing analysis and introduction to flip-flop setup time**
**Setup timing analysis and introduction to flip-flop setup time**

-At the zero time stamp, there is one clock edge that reaches the launch flop.
-At T time stamp, the second rising edge reaches the capture flop. Any analysis that needs to be done is between 0 and T. For the combinational circuit to work, the combinational delay needs to be less than the period, T.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/xy.png">

-Looking at more practical scenarios and how the flop works, there will be a delay within the internal flop circuitry, between mux 1 and mux 2.
-These internal delays will restrict the combinational delay requirements.
-This internal delay is known as the setup time, and this setup time needs to be subtracted away from the complete clock period T.
-Now the capture flop has enough time for it to compute the data within the flop and ensure the data is ready at Q by the time the second rise edge of clock reach.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/xyz.png">


**Theory 2: Introduction to clock jitter and uncertainty**

**Introduction to clock jitter and uncertainty**
**Jitter**
Deviation of a clock edge from its ideal location

Typically caused by clock generator circuitry, noise, power supply variations, interference from nearby circuitry etc. Jitter is a contributing factor to the design margin specified for timing closure

The next practical scenario to take into consideration is jitter.

The clock is expected to reach the clock pin at exactly 0s or at Ts, but in real scenarios, the clock signal may not be able to reach at the exact moment, as the clock source generation may have its own built-in variation.

This is known as jitter, the temporary variation of the clock period.

The combinational delay will become more stringent as a result. Thus we change our combinational delay to factor in the uncertainty factor from the jitter.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/k1.png">

The combinational delay of a path will look as shown above.
The next challenge comes in performing timing analysis with multiple ideal clocks.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/k2.png">

**Lab 1: Lab steps to configure OpenSTA for post-synth timing analysis**
**Lab steps to configure OpenSTA for post-synth timing analysis**

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
vim pre_sta.conf                                          (For pre-layout timing analysis)
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/pre_sta_tcl0.01.png">

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src
vim my_base.sdc
cd ~/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign/libs
vim sky130_fd_sc_hd__typical.lib
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/pre_sta_sdc_0.02.png">

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/setup_for%20presta_0.03.png">



**Lab 2: Lab steps to optimize synthesis to reduce setup violations**

**Lab steps to optimize synthesis to reduce setup violations**

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/hold_for_presta_0.03.png">

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/readme_config_21.png">

In openlane
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
echo $::env(SYNTH_MAX_FANOUT)
set ::env(SYNTH_MAX_FANOUT) 4
```
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
rm -rf picorv32a.synthesis.v
```
In openlane
```ruby
run_synthesis
```
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane
sta pre_sta.conf
report_net -connections _18242_                           
replace_cell _41952_ sky130_fd_sc_hd__dfxtp_4             (Pick the highest fanout, cap, slew and replace the worst violations of the cell by increasing drive strength --> upsize cell from 2 to 4)
report_checks -fields {net cap dlew input pins} -digits 4
report_tns
report_wns
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/fanout_set_22.png">


</details>
<details>



<summary>Clock tree synthesis TritonCTS and signal integrity</summary>

**Theory 1: Clock tree routing and buffering using H-Tree algorithm**
**Clock tree routing and buffering using H-Tree algorithm**

-Clock tree synthesis is done to propagate the clock signals to all the clock pins in the design.
-However, a good clock tree needs to be designed to take into account the skew between the clock pins due to long routing.
-Through the use of H-tree, which is a smarter implementation for a clock tree design, that is designed based on the distances between the clock pins in the design between the clock port.
-This is to give a skew value as close to 0 as possible by having the clock signals reach all the cells at the same time.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/p1.png">

-The next step is to perform clock tree buffering.
-The wires for the clock routes each will have resistances and huge number of capacitances, and with the long routing, there will be signal integrity issues.
-Thus, to maintain the signal integrity, we need buffering on these nets.
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/p2.png">

**Theory 2: Crosstalk and clock net shielding**
**Crosstalk and clock net shielding**

-Another topic to understand before moving to using real clocks is clock net shielding.
-Clock nets are the critical nets in the design, we build the clock tree to ensure there is a minimum skew.
-However, if there is any cross talk that happens and affect the clock signals, that will affect the design very badly.
-By shielding, we are protecting the clock nets from the outside world, avoiding glitches and delta delays from occurring.
-If a glitch occurs on the clock net, incorrect data in the memory will cause inaccurate functionality for the design.
-The shield can be connected to ground or to Vdd, as long as there is no switching activity occurring.
-Critical data nets are also necessary to be shielded.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/a1.png">

**Lab 1: Lab steps to run CTS using TritonCTS**

**Lab steps to run CTS using TritonCTS**

In sta terminal
```ruby
write_verilog ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis.v
```
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/13-01_14-09/results/synthesis
ls -lrt picorv32a.synthesis.v
date
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/synthesis%20successful.png">

In openlane
```ruby
run_floorplan
run_placement
run_cts
```
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
**Lab 2: Lab steps to verify CTS runs**

**Lab steps to verify CTS runs**

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/tcl_commands
vim cts.tcl
```
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk_2_or_cts_4.png">

Each stage has its own .tcl file, except synthesis since it is not in openroad
```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/scripts/openroad
vim or_cts.tcl
```
In openlane
```ruby
echo $::env(LIB_TYPICAL)
echo $::env(CURRENT_DEF)
echo $::env(CTS_MAX_CAP)
echo $::env(CTS_CLK_BUFFER_LIST)
echo $::env(CTS_ROOT_BUFFER)
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk3_echo%20define_3.png">


</details>
<details>
<summary>Timing analysis with real clocks using openSTA</summary>

**Theory 1: Setup timing analysis using real clocks**
**Setup timing analysis using real clocks**

-After buffer has been added in, more clock network delay has been introduced and it will combining all the delays.
-With real clocks, we will need to have buffers inserted into the clock path to ensure the clock signal integrity.
-Because of the buffer introduction, the clock edge will reach the clock pin with consideration to the delays of the buffers inserted.
-The clock network delay will also need to take into consideration the delays from the buffers inserted.
-The window will become shifted as a result of the delays from the buffers inserted.
-The skew for this design will now be the difference between the deltas, and the equation for setup timing analysis will also changed based on the image shown.
-If the data arrival time is higher than the data required time, then we will have negative slack on the path, meaning we have violations.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/b1.png">


-For hold timing analysis, where the capture edge is on the o clock rise edge, the combinational delay should be greater than the hold time of the flop.
-Hold time refers to the second mux delay, which is the time required for the data to be sent after the clock edge within the flop.
-So the data needs to be arrived after the hold time, so the new data can be captured into the flop, after existing data is launched out.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/b2.png">

**Theory 2: Hold timing analysis using real clocks**

**Hold timing analysis using real clocks**

-Introducing more real factors into our design for hold analysis will yield the below equation for hold timing.
-Jitter for the launch clock and capture flop will not need to be taken into consideration as the design is on the 0 clock edge, and the arrival difference for the capture and launch flop will be the same.
-So, the uncertainty should be kept low for the hold analysis.
-The slack formula will be --> data arrival time – data required time
-If data required time is higher, we will have negative slack, meaning the timing path for hold will be violated.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/c1.png">

-For the timing path setup for real clocks, we need to take into considerations the deltas that were mentioned earlier.
-For delta1, will be launch clock network delay, while delta2, will be capture clock network delay.
-The equations for setup time and hold time are shown below.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/c2.png">

**Lab 1: Lab steps to analyze timing with real clocks using OpenSTA**

**Lab steps to analyze timing with real clocks using OpenSTA**

In openlane

```ruby
openroad                                                                                                       (Invoking openroad)
read_lef /openLANE_flow/designs/picorv32a/runs/13-01_14-09/tmp/merged.lef
read_def /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/cts/picorv32a.cts.def
write_db pico_cts.db
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty -max $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read_liberty -min $::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
set_propagated_clock [all_clocks]
read_sdc designs/picorv32a/src/my_base.sdc
report_checks -path_delay min_max -format full_clock_expanded -digits 4
```
This step is not practical, therefore it violated.


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_final_roadmap.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_openroad_final.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk_4_hold_report_2.png">


**Lab 2: Lab steps to execute OpenSTA with right timing libraries and CTS assignment**

**Lab steps to execute OpenSTA with right timing libraries and CTS assignment**

    Continuing from previous lab
```ruby
exit        (Exit openroad)
openroad
read_db pico_cts.db
read_verilog /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/synthesis/picorv32a.synthesis_cts.v
read_liberty $::env(LIB_SYNTH_COMPLETE)
link_design picorv32a
read_sdc designs/picorv32a/src/my_base.sdc
set_propagated_clock [all_clocks]
report_checks -path_delay min_max -fields {slew trans net cap input pin} -format full_clock_expanded
echo $::env(CTS_CLK_BUFFER_LIST)                              (To see the list of buffers)
```

Both timing are already met after post CTS
The tool picked small cell first to meet the skew and area
skew values are within 10% of the max clock period

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_openroad_final.png">


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/setup%20repot%20aftr%20run_23.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_buffername.png">

**Lab 3: Lab steps to observe impact of bigger CTS buffers on setup and hold timing**

**Lab steps to observe impact of bigger CTS buffers on setup and hold timing**

In openlane
```ruby
exit 
echo $::env(CTS_CLK_BUFFER_LIST)
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]
echo $::env(CURRENT_DEF)
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/13-01_14-09/results/placement/picorv32a.placement.def
run_cts
```

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_final_roadmap.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_final_report.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk_4_hold_report_2.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day19/disk4_last.png">


</details>


</details>


 </details>

# Day 19 Final steps for RTL2GDS

<details>
<summary>Routing and design rule check (DRC)</summary>
	
**Theory 1: Introduction to Maze Routing using Lee's algorithm**

**Introduction to Maze Routing using Lee's algorithm**

**Routing stage**
 -Maze Routing-Lee’s Algorithm [Lee 1961]: Algorithm to find the shortest path between two nodes in a grid

*Routing*: the process of creating the physical wire connections within the design in which it helps in determining the best way of routing that can be done between two endpoints, the source, and the target, with the shortest distance as well as the least number of zig-zag turns.

 -However, the algorithm needs to be aware of any blockages set that hinders any routing to be done in the particular area.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x1.png">


*Steps in Lee's Algorithm*

1. Create the routing grid behind the floorplan

2. The two points were created which are the source and target

   -Algorithm will look for the best route to connect the two points with the help of the routing grid

3. The tool will label the grid ground (adjacent of horizontal and vertical grid)

    -However, it did not label the grid under the blockage and at the boundary

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x2.png">

**Theory 2: Lee's Algorithm conclusion**

**Lee's Algorithm conclusion**

1.It is preferable to choose the LHS instead of RHS of the figure below

2.It is because the chosen route in the LHS figure got the best route which is less bending (L-shaped) rather than the RHS figure

Therefore, LHS figure will proceed to do the global routing

3.Performing the routing for 1 route will be fairly simple, but when we have millions of start and endpoints to route between, this method will consume a lot of time and memory

4. Maze routing consumes more time and memory if the design is huge

5. There are some algorithms that can help to reduce the time and memory consumption such as line-search algorithm, stanner-tree algorithm


<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x3.png">

**Theory 3: Design Rule Check**

**Design Rule Check**

1. Design Rule Check (DRC): the rules that should be followed whenever the routing of the design is performed.

2. One of the rules may be the minimal wire width, where the width of the wire should be no less than a specified amount based on the limitations of the fabrication process.

3. Another rule that is based on the fabrication process of lithography is the wire pitch, where the centre-to-centre distance between 2 wires should be no smaller than a certain distance.

4. Another rule includes wire spacing rule, where distance between 2 wires should be no smaller than a certain distance.

5. These are many rules that the tool needs to take into account when performing the routing of the design.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x4.png">

1. One type of DRC violation is a signal short, where two wires that are not intended to be connected becomes in contact on the same layer.

2. This could lead to functional failure, so this needs to be taken care of.

3. To fix this, we need to simply moving one of the wires onto a different metal layer.

4. However, please keep in mind that there are new drc rules that need to be taken into account.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x5.png">

**New drc rules after fixing**

**Via width** where the width of the via should be no less than a certain value.

**Via spacing** where the distance between 2 vias cannot be less than a specific distance.

Most of these DRC rules come from the lithographic process and the limitations that come with the technology.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x6.png">

Performing parasitic extraction, where the resistances and capacitances of the wires are extracted and will be used for further processes.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x7.png">
</details>

<details>
<summary>Power Distribution Network and routing</summary>

**Lab 1: Lab steps to build power distribution network**

**Lab steps to build power distribution network**

If exited from openlane

```ruby
cd work/tools/openlane_working_dir/openlane
make mount
pwd
ls -ltr
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag 
```

Note: If we want to retain the configurations from the last openlane job, we need to use ```rubyprep -design -tag.``` If we want to create a fresh run with new configurations but without changing the tag name, we need to use ```rubyprep -design -tag -overwrite.```

In openlane

```ruby
echo $::env(CURRENT_DEF)    (Ensure current_def is on the CTS stage)
gen_pdn                     (To generate power distribution network)
```
-Error encountered during “gen_pdn” in which the stage cannot perform routing as current_def has not changed to floorplan.pdn

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/routing_strategy.png">


**Lab 2: Lab steps from power straps to std cell power**
**Lab steps from power straps to std cell power**

This is just a review on PDN

If the power and ground rails has a pitch of 2.72, thus the customized inverter cell will have a height of 2.72 or else the power and ground rails will not be able to power up the cell.

As shown below, power and ground flows from power/ground pads --> power/ground ring --> power/ground straps --> power/ground rails.

Source: https://github.com/AngeloJacobo/OpenLANE-Sky130-Physical-Design-Workshop#timing-analysis-with-real-clocks

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x8.png">

**Lab 3: Basics of global and detail routing and configure TritonRoute**

**Basics of global and detail routing and configure TritonRoute**

```ruby
echo $::env(CURRENT_DEF)            (Ensure the def file of pdn has been created)
echo $::env(ROUTING_STRATEGY)
run_routing
```

```ruby
cd ~/Desktop/work/tools/openlane_working_dir/openlane/configuration
vim README.md
```
    Assuming power distribution network has been successfully generated without being encountered by any error

<img  width="1085" alt="" src="">

<img  width="1085" alt="" src="">


</details>
<details>
<summary>TritonRoute Features</summary>

**Theory 1: TritonRoute feature 1 - Honors pre-processed route guides**

**TritonRoute feature 1 - Honors pre-processed route guides**

OpenLane routing stage consists of two stages:
**Global Routing:** Form routing guides that can route all the nets. The tool used is FastRoute.
**Detailed Routing:** Uses the global routing's guide to connect the pins with the least amount of wire and bends. The tool used is TritonRoute.

**Triton Route**

-In fast routing, a rough routing draft is created.

-Fast routing is the engine which is used for global routing.

-During global routing, the region is divided into grid cells, which acts as a route guide for the TritonRoute to be used for the detail routing, where an algorithm is used to find the best connectivity between the points.

-It honours the preprocessed route guides (obtained after fast routes), wherein the tool attempts as much as possible to route within route guides.

-The tool assumes route guides for each net satisfies inter-guide connectivity.

-Triton route works on proposed MILP (Mixed integer liner programming) based panel routing scheme with intra-layer parallel and inter-layer sequential routing framework, to finds the best way to perform the routing.

-Intra-layer refers to the routing within a layer, while inter-layer routing refers to routing between layers, through the uses of vias.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x9.png">


**Theory 2: TritonRoute Feature 2 & 3 - Inter-guide connectivity and intra- & inter-layer routing**

**TritonRoute Feature 2 & 3 - Inter-guide connectivity and intra- & inter-layer routing**

-Preprocessed guides should have unit width and must be in the preferred direction of the layer.

-Global route is done by fast route, and the output would be the routing guide.

-The initial route guides are transformed into the preprocessed guides through splitting, merging, and bridging.

-Whenever the tool detected the route guide with non-preferred direction, it divides the route guide into unit widths, and then the route with preferred direction is merged, while the non-preferred direction route is bridged to be a route on another layer, which is the preferred direction for routing.

-This way, parallel routing with higher layers are avoided, as well as avoiding parallel plate capacitance.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x10.png">

 -Each layer or panel will have its own preferred routing direction assigned to it, in which the routes should be formed.

-Routing in higher layers will begin only once the routing the bottom layers have been completed.

-Two guides are connected if they are on the same metal layer with touching edges, or if they are on neighbouring metal layers with a non-zero vertically overlapped area.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x11.png">

-Each unconnected terminal i.e. pin of a standard cell instance, should have its pin shape overlapped by a route guide.

-The purple box in the RHS figure below would be the routing guide on the metal 1 layer that would overlap with the unconnected terminal.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x12.png">

**Theory 3: TritonRoute method to handle connectivity**

**TritonRoute method to handle connectivity**

-Inputs file needed for TritonRoute are the LEF file, DEF file, and the Preprocessed route guides.

-Outputs from the TritonRoute would be a detailed routing solution with optimized wire-length and via count.

-Constraints needed in TritonRoute are the route guide honouring, connectivity constraints and design rules.

**TritonRoute method**

TritonRoute handles connectivity through 2 ways
Access Point (AP)
Access Point Cluster (APC)

**Access point:** on-grid point on the metal layer of the route guide, and is used to connect to lower-layer segments, upper-layer segments, pins or IO ports.

**Access Point Cluster:** a union of all Access Points derived from the same lower-layer segment, upper-layer guide, a pin or an IO port.

Access point refers to the point where the via can be placed to allow connectivity between layers.

The objective of the Mixed Integer Liner Programming (MILP) is to connect one access point to another optimally.
Choose one of the access points where the via should be dropped
Determining how the first access point will be connected to the next access point.

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x13.png">


**Lab 1: Routing topology algorithm and final files list post-route**

**Routing topology algorithm and final files list post-route**

**Optimization algorithm for routing topology**

-For each APC, the algorithm needs to find the cost associated with the distance between 2 APCs which are the minimum spanning tree, MST, between the APCs and the costs.

*The objective of the algorithm*
-To find the minimal and most optimal point between the 2 APCs.
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_day20/x14.png">

-There are 3 violations as shown in the figure below

-TritonRoute strategy = 0 is chosen right now

-If TritonRoute strategy = 14 is chosen, the violations might be 0 but it might take some time to finish running

-Therefore, we need to fix the violations manually

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/errorrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrrr.png">
<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/errorrrr11111111111111.png">

<img  width="1085" alt="" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/2222222222222222errorrrr00000000000001.png">

</details>
