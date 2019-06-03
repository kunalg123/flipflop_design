# flipflop_design
This project has files needed to design and characterise flipflop
Follow below steps to download Layout and run SPICE
git clone https://github.com/kunalg123/flipflop_design.git
magic -T min2.tech inv2.mag & --> This will open a MAGIC window with minimum sized inverter layout
With the above step, you can review the inverter, zoom in, zoom out, look into all layers and so on. To learn more about how the layout was drawn, what is tech file and what are its layers, refer to my below online "Custom Layout" course:
https://www.udemy.com/vlsi-academy-custom-layout/

To simulate the above Layout, use the below command
ngspice inv2.spice 
This command will run SPICE simulations, and will give you a ngspice terminal, like below.
ngspice 2 -> 
Type the below on ngspice terminal to see the input and output waveforms
ngspice 2 -> plot V(out) vs time V(in)
Review the waveform for rise delay and fall delay. To learn more about Circuit design and SPICE simulations, refer to my below online "Circuit design and SPICE simulations" course:
https://www.udemy.com/vlsi-academy-circuit-design/
https://www.udemy.com/vlsi-academy-circuit-design-part2/

You can now close magic window and ngspice window by typing "exit" in their respective terminals
Follow above similar steps for nand gate. Replace "inv2.mag" with "nand1.mag" and "inv2.spice" with "nand1.spice"
This time, on ngspice terminal type below commands to review the A->Y delay and B->Y delay
ngspice 2 -> plot V(out) vs time 
ngspice 2 -> plot V(a) V(b)
This will open 2 windows. Expand them and review waveforms. Refer to above online "Circuit design and SPICE simulations" courses

Now, to see how D-FF was built using both inv2 and nand1, repeat all above steps by replacing "nand1.mag" with "dff.mag" and "nand1.spice" to "dff.spice" 
On ngspice terminal, type below 2 commands
ngspice 2 -> plot V(q) V(clk)
ngspice 2 -> plot V(din)
This will plot output 'q' with respect to 'clk'. You will observe, except at clock edge at 6.3ns and 16.3ns, at all other rising clock edge, it violates setup time
To know more of flip-flop timing characterization, refer to my below online course on "Library Characterization and Modelling"
https://www.udemy.com/vlsi-academy-library-characterization-part-1/

All the best
Happy designing and learning...
