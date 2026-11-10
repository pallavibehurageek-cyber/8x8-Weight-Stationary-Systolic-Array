# ASAP7 OpenROAD Flow Configuration

This directory contains a separate ASAP7 configuration, timing constraints, and power-grid script. It uses the flattened Yosys-compatible RTL already maintained in `verilog/rtl/`, avoiding a second copy of the same modules.

The configuration expects an OpenROAD-flow-scripts checkout with its ASAP7 platform files installed. The flow has not been run as part of this repository update, so the configuration should be treated as a starting point to validate in that environment.
