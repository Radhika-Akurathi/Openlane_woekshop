# Circuit Design and Spice simulations
This repository explains the characterization of nfet device from sky130 technology and also explains the difference in characteristics as the channel length decreases(basically how it differs as it moves to lower nodes) and also explains the robustness of CMOS inverter.

# Table of Contents
- [Spice netlist for output characteristics of nfet device](#spice-netlist-for-output-characteristics-of-nfet-device)

# Spice netlist for output characteristics of nfet device

*Model Description

.param temp=27

*Including sky130 library files

.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=0.65 l=0.25

R1 in n1 55

Vdd vdd 0 1.8V

Vin in 0 1.8V

*simulation commands

.op 

.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.end


The above spice netlist gives the output transfer characteristic of nfet_01v8 mos device from sky130 technology. Here, the supply voltage of 1.8V is taken and drain to source voltage (Vds) is sweeped from 0 to 1.8V with a step of 0.1V and the gate to source voltage (Vgs) is sweeped from 0 to 1.8V with a step of 0.2V.

From the Ids vs Vds curve we can observe the linear and saturation region and in saturation region the line has to be constant(flat line) but because it is slightly dependant on Vds voltage it can be observed from the waveform that there is slight increase in Ids in saturation region. This variation can be defined from lambda.


