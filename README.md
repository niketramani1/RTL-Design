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

Lab1: Understanding the .lib files and the content in it
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
![image](https://user-images.githubusercontent.com/86380243/123173992-724ab100-d44d-11eb-99ba-4f8f461dfba9.png)






 
     
