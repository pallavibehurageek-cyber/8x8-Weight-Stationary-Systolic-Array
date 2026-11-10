# SPI Interface Simulation

This directory contains the SPI-to-systolic-array integration wrapper and a transaction-level testbench. It reuses the shared SPI slave RTL in `../verilog/rtl/spi_slave.sv`; no duplicate copy is maintained here.

## SPI command bytes

| Command | Function |
|---|---|
| `0x01` | Load eight weights into the selected row |
| `0x02` | Load an eight-element activation vector |
| `0x03` | Read the 256-bit partial-sum result |
| `0x04` | Reset the array |

## Run the simulation

From the repository root, with Icarus Verilog installed:

```bash
iverilog -g2012 -s spi_tb -o spi_tb.vvp \
  verilog/rtl/pe.sv \
  verilog/rtl/systolic_array.sv \
  verilog/rtl/spi_slave.sv \
  SPI_Interface/systolic_array_spi_top.sv \
  SPI_Interface/spi_tb.sv
vvp spi_tb.vvp
```

The testbench writes `spi_wave.vcd` for waveform inspection.
