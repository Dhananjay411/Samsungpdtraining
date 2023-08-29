# Samsungpdtraining
- [Day-0-Installation](#Day-0-Installation)
- [Day-1-Introduction to Verilog RTL Design and Synthesis](#Day-1-Introduction-to-Verilog-RTL-Design-and-Synthesis)
- [Day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style](#Day-2-Timing-libs,-hierarchical-vs-flat-synthesis-and-efficient-flop-coding-style)
- [Day-3-Combinational and sequential logic optimizations](#Day-3-Combinational-and-sequential-logic-optimizations)
  
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
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_3.png">

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
<img  width="1085" alt="hand_writ_exam" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_/%23Day3/gtkwave_dff_const_3.png">
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

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/bad_sch.png">

Netlist Simulation

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/bad_gls.png">

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

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_rtl.png">

Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_sch.png">

Netlist 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/good_gls.png">

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
 
 <img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_rtl.png">

 Schematic 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_sch.png"> 

Netlist simulation 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/487d88bd65ce2da9dd49d224ea4c740c05be586e/day4/blk_gls.png"> 

<img  width="1085" alt="hand_writ_exam" src="https://github.com/AbhishekChinchani/Samsung_pd/blob/2ea9ca60553c829f9162484cb1e4049c3064443c/day4/20230829_085956.jpg"> 

This a combinational circuit of or and and gate , in which the output of or gate is given as input to the and gate as shown in the figure , but in the RTL Design code blocking statements are used to define these operations in reverse direction(These statements are executed sequentially) so the and gate is getting input from the  previous output of or gate which acts as imaginary flop. As a result we are getting a different waveform in RTL design simulation , the correct waveform is  obtained  while doing netlist simulation. This causes Synthesis Simulation mismatch. This can be overcome by using non blocking assignment statements in the always block.  
</details>






