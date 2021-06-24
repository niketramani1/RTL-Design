# RTL-Design using Verilog with Skywater Technology

**Day 1**: Introduction to Verilog RTL Design and Synthesis

Lab 1: Setting up the environment. CLoning the repositeries from github. 
 ![image](https://user-images.githubusercontent.com/86380243/123160881-b84b4900-d43c-11eb-82af-82d80ea0e6ee.png)
 
Lab 2: Using iverilog and gtk wave to implement good_mux.v
![image](https://user-images.githubusercontent.com/86380243/123161946-090f7180-d43e-11eb-829c-8ddff59dd943.png)

Lab3: Synthesis using Yosys for good_mux.v
![image](https://user-images.githubusercontent.com/86380243/123162359-8509b980-d43e-11eb-9fbc-f83a20d21a18.png)

Writing verilog netlist
![image](https://user-images.githubusercontent.com/86380243/123163025-432d4300-d43f-11eb-83d7-a06d2e7a2ff0.png)

**Day 2**: Timing libs, hierarchical vs flat synthesis and efficient flop coding styles

Lab1: Understanding the .lib files and the content in it. Concepts of PVT
![image](https://user-images.githubusercontent.com/86380243/123167880-2b58bd80-d445-11eb-8a9c-2c4840c4d42e.png)

Lab2: Differentiating Hierarchichal vs Flat synthesis
In hierarchical synthesis, all the modules (the top and sub modules are preserved).
Running the synthesis for multiple modules hierarchichal
![image](https://user-images.githubusercontent.com/86380243/123172932-dbc9c000-d44b-11eb-8a2b-5381a14bacf8.png)
As we can see the modules are preserved
After write_verilog we get this hierarchical netlist
![image](https://user-images.githubusercontent.com/86380243/123173621-e173d580-d44c-11eb-9855-d317ceacdcec.png)

![image](https://user-images.githubusercontent.com/86380243/123173526-bc7f6280-d44c-11eb-958f-66d1400a45fa.png)

Running the synthesis for multiple modules flat, it is a single netlist and submodules are not preserved
![image](https://user-images.githubusercontent.com/86380243/123174326-eedd8f80-d44d-11eb-88a9-6f343a180a9c.png)
After write_verilog we get this hierarchical netlist
![image](https://user-images.githubusercontent.com/86380243/123173992-724ab100-d44d-11eb-99ba-4f8f461dfba9.png)

Synthesizing only one particular submodule from multiple modules:

After synthesizing submodule1 from multiple_modules.v we get
![image](https://user-images.githubusercontent.com/86380243/123176274-2568d980-d451-11eb-8f3d-69d2d540823a.png)
As we can see only the AND gate(submodule 1) is synthesized

We do module level synthesis primarily for 2 reasons:
a) If same module instantiated multiple times in design, we need not synthesize it multiple times. Rather, we do it once and stitch them together
b) If it is a large design with many number of modules, we do the synthesis part by part basically divide and conquer

FLIP FLOPS AND THEIR SIMULATIONS AND SYNTHESIS
Why a flip flop?
Is basically used to avoid glitches when there is a series of combinational circuits.
A flip flop has to have an initial state or else the comb circuits might get some garbage values.
This can be done using the set/ reset. The set/reset can be synchronous or asynchronous. In some cases, the FF can have both synchronous and asynchronous reset at the same time.
Asynchronous is basically independent of clock and synchronous is dependent on the clock.

SIMULATIONS:
1) Aynchronous reset:
![image](https://user-images.githubusercontent.com/86380243/123180948-54d01400-d45a-11eb-8f5c-90ff127c6881.png)
![image](https://user-images.githubusercontent.com/86380243/123181231-e5a6ef80-d45a-11eb-826f-a6a6f9fe8a27.png)

2)Asynchronous set:
![image](https://user-images.githubusercontent.com/86380243/123181822-16d3ef80-d45c-11eb-8ceb-85d4fa368295.png)

3)Synchronous reset:
![image](https://user-images.githubusercontent.com/86380243/123182148-d2951f00-d45c-11eb-8031-33c2f66f7643.png)

SYNTHESIS:
1) Asynchronous reset:
![image](https://user-images.githubusercontent.com/86380243/123182792-27856500-d45e-11eb-9416-de8ba927ddcf.png)
Here there is an inverter because the dff in library is active low and we have designed an active high reset

2)Asynchronous set:
![image](https://user-images.githubusercontent.com/86380243/123183135-e3469480-d45e-11eb-80bb-d3832bc1c49e.png)

3)Synchronous reset:
![image](https://user-images.githubusercontent.com/86380243/123183304-49331c00-d45f-11eb-80b7-f2384a7eb7a3.png)

Optimizations in synthesis
Synthesizing mult_2: We can see there is no hardware as its only appending a 0
Multiplication in binary is basically shifting
![image](https://user-images.githubusercontent.com/86380243/123184415-a7f99500-d461-11eb-9ac7-68bc44b996ae.png)
The netlist will be:
![image](https://user-images.githubusercontent.com/86380243/123184799-6d442c80-d462-11eb-8aff-3b52a1fddc7e.png)

Synthesizing mult_8: We can see there is no hardware as its appending
![image](https://user-images.githubusercontent.com/86380243/123185041-0b37f700-d463-11eb-8bd1-b038a8acb95e.png)
The netlist will be: 
![image](https://user-images.githubusercontent.com/86380243/123185161-45a19400-d463-11eb-89b0-0d330087a794.png)
As we can see, its basicallay concatenating {a,a}










 
     
