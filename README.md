# Samsungpdtraining
- [Day-0-Installation](Day-0-Installation)
- [Day-1-Introduction to Verilog RTL Design and Synthesis](Day-1-Introduction-to-Verilog-RTL-Design-and-Synthesis)
- [day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style](day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style)
  
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




## Day-2-Timing libs, hierarchical vs flat synthesis and efficient flop coding style

 <details>
 <summary>Introduction to Timing libs, hierachical synthesis, flat synthesis, Flop coding style </summary>
	 
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
 cell compare
<img width="1085" alt=" cell compare" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/samsungpd_%23day2/cell_compare_1.png">

 
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



**various flop coding style and optimisation**: 

There are several coding styles and optimization techniques for designing flip-flops (flops) in hardware description languages (HDLs) like VHDL and Verilog. The choice of coding style and optimization technique depends on factors such as the design's requirements, target technology, and personal or organizational preferences. Here are various flop coding styles and optimization techniques:

1. Edge-Triggered vs. Level-Sensitive: Flip-flops can be edge-triggered or level-sensitive. Edge-triggered flops are more common in synchronous digital design, as they provide clear and predictable behavior. Level-sensitive flops (latches) are used sparingly and typically for specialized purposes, as they can lead to complex timing issues.

2. Synchronous Reset and Asynchronous Reset: Flip-flops can have either synchronous or asynchronous reset signals. Synchronous resets are recommended for most designs because they simplify timing analysis. Asynchronous resets can introduce glitches and timing challenges, but they are sometimes necessary for specific functionalities.

3. Clock Polarity: Depending on the hardware platform and design requirements, flip-flops can be sensitive to either the rising edge (positive-edge-triggered) or falling edge (negative-edge-triggered) of the clock signal. Choose the appropriate clock polarity for your design.

4. Clear and Preset Inputs: Some flip-flops include clear (CLR) and preset (PR) inputs to asynchronously force the output to certain states. These inputs should be used sparingly and with caution, as they can complicate design and introduce race conditions.

5. Register Initialization: Initialize flip-flop registers to known values at power-up or reset. This ensures predictable behavior during initialization.

6. Register Packing: When dealing with large designs, packing multiple flip-flops into a single register can reduce resource usage. This is especially useful when your FPGA or ASIC technology supports this optimization.

7. Use of "always" Blocks (Verilog) or "process" Statements (VHDL): These constructs define the behavior of flip-flops. Ensure that your sensitivity list is appropriately defined and does not lead to unintentional latches or complex logic.

8. Reset Synchronizers: When using asynchronous resets, employ reset synchronizers to synchronize the asynchronous reset signal with the clock domain to avoid metastability issues.

9. Clock Gating: Clock gating involves using logic gates to selectively enable or disable the clock signal to certain flip-flops. This can reduce power consumption when not all flip-flops need to toggle on every clock cycle. However, use it judiciously, as it can add complexity.

10. Group Related Signals: Organize flip-flops and their associated signals into logical groups or modules to improve code readability and maintainability.

11. Use of State Machines: For complex sequential logic, consider using state machines to control the behavior of flip-flops and other logic elements. State machines can help simplify complex control flow.

12. Clock Domain Crossing (CDC) Considerations: When signals cross between different clock domains, use synchronization techniques such as two-flop synchronizers to avoid metastability issues.

13. Timing Constraints: Define proper setup and hold time constraints for your flip-flops to ensure correct operation and meet timing requirements.

14. Simulation and Verification: Thoroughly simulate and verify your flip-flops and their interactions within the design to catch any functional or timing issues.

15. Documentation: Document your flip-flop code, including the purpose of each flip-flop, constraints, and any non-standard coding practices. Good documentation aids in understanding and maintaining the design.

Effective flop coding and optimization require a deep understanding of the design's requirements, the target hardware, and the specific constraints and goals of the project. Regularly reviewing and optimizing your code as you progress through the design process is essential for achieving an efficient and reliable design

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
<img width="1085" alt="netlist" 

<img width="1085" alt="netlist" src="https://github.com/Dhananjay411/Samsungpdtraining/blob/master/simplifield_yosys.JPG">
</details>
