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
