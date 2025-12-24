# UART TX/RX (Verilog) – FPGA Ready

##  Project Overview
This project implements a complete **UART Transmitter and Receiver** in **Verilog HDL**, designed and verified through simulation and FPGA synthesis using **Xilinx Vivado 2022.2**.

The design supports:
- 8-bit data
- No parity
- 1 stop bit (8N1)
- Parameterized baud rate generation

A loopback testbench is used to validate correct TX → RX functionality.

---

##  Modules Implemented

### 1. Baud Rate Generator (`baud_gen.v`)
- Generates `baud_tick` and `half_baud_tick`
- Parameterized for clock frequency and baud rate
- Uses counters and clock enable logic

### 2. UART Transmitter (`uart_tx.v`)
- Handles start bit, data bits, and stop bit
- FSM-based implementation
- Shifts data LSB first

### 3. UART Receiver (`uart_rx.v`)
- Samples data at half-baud
- Reconstructs received byte
- Detects framing and parity errors

### 4. Top Module (`uart_top.v`)
- Integrates TX, RX, and baud generator
- Designed for FPGA synthesis

---

##  Simulation
- Loopback testbench verifies TX output is correctly received by RX
- Simulated using Vivado simulator
- Waveforms captured for verification

---

##  FPGA Synthesis
- Target Device: **xc7a12ticsg325-1L**
- Tool: **Xilinx Vivado 2022.2**
- Successfully synthesized with low resource utilization

### Resource Utilization Summary
- Slice LUTs: 28
- Slice Registers: 34
- BUFG: 1
- DSPs: 0
- BRAM: 0

Full utilization report is included in the `docs/` folder.

---

## 📂 Project Structure
UART_final/
├── rtl/
│ ├── baud_gen.v
│ ├── uart_tx.v
│ ├── uart_rx.v
│ └── uart_top.v
├── tb/
│ └── uart_loopback_tb.v
├── docs/
│ ├── baud_gen_utilization_synth.pdf
│ ├── clock_utilization.png
│ └── synthesized_netlist.png
└── README.md

---

## Tools Used
- Verilog HDL
- Xilinx Vivado 2022.2
- Windows 10

---

## 👤 Author
**Aswin S**  
Electronics and Communication Engineering  
FPGA / Digital Design Enthusiast
