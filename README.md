# 32Bit_ALU Simulation

# Aim: 

Write a verilog code for 32 bit ALU supporting four logical and four arithmetic operations,use case statement and if statement for ALU behavioral modeling.

To Verify the Functionality using Test Bench.

# Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

## Design Information and Bock Diagram:

The ALU will take in two 32-bit values, and control line. An Arithmetic unit does the following task like addition subtraction, multiplication and logical operations. As the input is given in 32 bit we get 32 bit output. The arithmetic will show only one output at a time so a selector is necessary to select one of the operator.

![image](https://github.com/user-attachments/assets/e574788c-253f-46da-8468-298fe2844f7a)

### Fig 1 : Block Diagram of 32 Bit ALU 

## Creating a Work space :

Create a folder in your name (Note: Give folder name without any space) and Create a new sub-Directory name it as Exp3 or alu_32bit for the Design and open a terminal from the Sub-Directory.

## Creating Source Codes 

In the Terminal, type gedit <filename>.v (ex: gedit alu_32bit.v). 

A Blank Document opens up into which the following source code can be typed down. 

(Note : File name should be with HDL Extension)

## a)To Verify the Functionality using Test Bench

## Source Code – Using Case Statement :

(Include program here)

Use Save option or Ctrl+S to save the code or click on the save option from the top most right corner and close the text file.

## Creating Test bench:

Similarly, create your test bench using gedit <filename_tb>.v or <filename_tb>.vhdl to open a new blank document (alu_32bit_tb_case).

## Test Bench :

(Include test bench program here)

Use Save option or Ctrl+S to save the code or click on the save option from the top most right corner and close the text file.

## Functional Simulation: 

Invoke the cadence environment by type the below commands 

tcsh (Invokes C-Shell) 

source /cadence/install/cshrc (mention the path of the tools) 

(The path of cshrc could vary depending on the installation destination)
      
After this you can see the window like below 

![WhatsApp Image 2025-04-29 at 15 24 05_014257ba](https://github.com/user-attachments/assets/84e506f3-0da8-4bc8-bfc0-bc263300f843)

### Fig 2: Invoke the Cadence Environment

To Launch Simulation tool 

•linux:/> nclaunch -new& // “-new” option is used for invoking NCVERILOG for the first time for any design 

or

•linux:/> nclaunch& // On subsequent calls to NCVERILOG 


It will invoke the nclaunch window for functional simulation we can compile,elaborate and simulate it using Multiple Step .

![WhatsApp Image 2025-04-29 at 15 24 05_f134ea2a](https://github.com/user-attachments/assets/868fd644-54c6-4d66-ab52-e5fe33eaea2b)

### Fig 3: Setting Multi-step simulation

Select Multiple Step and then select “Create cds.lib File” as shown in below figure 

Click the cds.lib file and save the file by clicking on Save option 

![WhatsApp Image 2025-04-29 at 15 24 05_a70fde2a](https://github.com/user-attachments/assets/942946ab-8031-4bcb-afcc-e26c3aed7548)

### Fig 4:cds.lib file Creation

Save cds.lib file and select the correct option for cds.lib file format based on the HDL Language and Libraries used. 

Select “Don’t include any libraries (verilog design)” from “New cds.lib file” and click on “OK” as in below figure .

We are simulating verilog design without using any libraries 

A Click “OK” in the “nclaunch: Open Design Directory” window as shown in below figure 

![WhatsApp Image 2025-04-29 at 15 24 06_ba992b43](https://github.com/user-attachments/assets/45be69e7-b60f-4982-9375-6e51245e444d)

### Fig 5: Selection of Don’t include any libraries

A ‘NCLaunch window’ appears as shown in figure below

Left side you can see the HDL files. Right side of the window has worklib and snapshots directories listed. 

Worklib is the directory where all the compiled codes are stored while Snapshot will have output of elaboration which in turn goes for simulation .

To perform the function simulation, the following three steps are involved Compilation, Elaboration and Simulation. 

![WhatsApp Image 2025-04-29 at 15 24 06_bd3206c8](https://github.com/user-attachments/assets/63ed6dc4-fa26-4c24-8462-d3cb4cb44a6f)
### Fig 6: Nclaunch Window

## Step 1: Compilation:

– Process to check the correct Verilog language syntax and usage 

Inputs: Supplied are Verilog design and test bench codes 

Outputs: Compiled database created in mapped library if successful, generates report else error reported in log file 

## 	Steps for compilation: 

1. Create work/library directory (most of the latest simulation tools creates automatically)
   
2. Map the work to library created (most of the latest simulation tools creates automatically)
   
3. Run the compile command with compile options
   
i.e Cadence IES command for compile: ncverilog +access+rwc -compile fa.v 

Left side select the file and in Tools : launch verilog compiler with current selection will get enable. Click it to compile the code 

Worklib is the directory where all the compiled codes are stored while Snapshot will have output of elaboration which in turn goes for simulation 

![WhatsApp Image 2025-04-29 at 15 24 06_48f39bcf](https://github.com/user-attachments/assets/f0c0af9b-81cf-4ae6-ae15-15f2c79ee842)
### Fig 7: Compiled database in worklib

After compilation it will come under worklib you can see in right side window

Select the test bench and compile it. It will come under worklib. Under Worklib you can see the module and test-bench. 

The cds.lib file is an ASCII text file. It defines which libraries are accessible and where they are located. It contains statements that map logical library names to their physical

directory paths. For this Design, you will define a library called “worklib”

#3 Step 2: Elaboration:– 

To check the port connections in hierarchical design

Inputs: Top level design / test bench Verilog codes 

Outputs: Elaborate database updated in mapped library if successful, generates report else error reported in log file 

## 	Steps for elaboration 

– Run the elaboration command with elaborate options 

1.It builds the module hierarchy

2.Binds modules to module instances 

3.Computes parameter values

4.Checks for hierarchical names conflicts

5.It also establishes net connectivity and prepares all of this for simulation

After elaboration the file will come under snapshot. Select the test bench and simulate it.
![WhatsApp Image 2025-04-29 at 15 24 06_1f7591db](https://github.com/user-attachments/assets/fffc642d-862b-4aac-8a8e-bb05ac49df97)
## Fig 8: Elaboration Launch Option

## Step 3: Simulation: 

– Simulate with the given test vectors over a period of time to observe the output behaviour. 

Inputs: Compiled and Elaborated top level module name 

Outputs: Simulation log file, waveforms for debugging 

Simulation allow to dump design and test bench signals into a waveform 

Steps for simulation – Run the simulation command with simulator options

![WhatsApp Image 2025-04-29 at 15 23 43_d1f3101e](https://github.com/user-attachments/assets/9c7bc957-32fc-4fe1-b6db-d1c73805f541)
## Fig 9: Design Browser window for simulation
![WhatsApp Image 2025-04-29 at 15 23 43_8011a535](https://github.com/user-attachments/assets/73ce42f7-7fb1-45a2-9427-6168da549088)
## Fig 10:Simulation Waveform Window
![WhatsApp Image 2025-04-29 at 15 23 43_91721d7a](https://github.com/user-attachments/assets/4b1ca3ff-6c4c-4ceb-9569-c33ca83fc826)
## Fig 11:Simulation Waveform Window

### Result

The functionality of a 32-bit ALU was successfully verified using a test bench and simulated with the nclaunch tool.














      







