# Ultra_Low_Latency_HFT
This project presents a hardware-accelerated, ultra-low latency High-Frequency Trading (HFT) system implemented on an FPGA using Xilinx Vivado.
# ⚡ Ultra Low Latency HFT on FPGA (Vivado Design)

This repository documents a **hardware-accelerated High-Frequency Trading (HFT) system**, purpose-built for ultra-low-latency execution directly on an FPGA using Xilinx Vivado. The system is designed for nanosecond-level responsiveness, bypassing traditional software stacks in favor of deterministic, parallel hardware execution.

---

##  Overview

High-frequency trading demands minimal reaction time to market data. This project leverages an FPGA-based architecture to:

- Ingest financial market data directly.
- Parse and process messages in hardware.
- Make trading decisions in a custom application layer.
- Send orders to exchanges with near-zero latency.

The system is implemented and synthesized using Vivado, with modules written in Verilog/VHDL and integrated through IP blocks and AXI interfaces.

---

##  Architecture Diagram

![Ultra Low Latency HFT Architecture](./31c6a002-c95c-469f-82e8-375246f39dd2.png)

---

## System Components

### Algo-Logic FPGA Platform

- **Stock Price Tables & Parsers**: Processes FIX, OUCH, and other financial protocols.
- **Custom Logic (Application Layer)**: Executes trading algorithms in hardware.
- **Session Management**: Handles datagram-level and IP-based message framing.
- **10G MAC Interfaces**: Multiple 10G ports support simultaneous high-speed streams.
- **SRAM Controller**: Manages ultra-fast temporary storage using GDR II SRAM.
- **CPU (Softcore/Hardcore)**: For basic coordination and state management.

###  Host PC

- Communicates via a **C++ API**.
- Runs user-space applications with **standard networking stack** and **10G MAC** interface.
- Uses **UDP links** for high-speed, low-latency interaction with the FPGA.

### Exchange Connectivity

Supports a wide range of financial protocols:
- **FIX** (Financial Information eXchange)
- **OUCH** (Nasdaq)
- **XPRS** (Direct Edge)
- **BOE** (Bats-BSX)
- **Arca Direct** (NYSE Arca)

---

## Performance Highlights

| Feature                  | Metric                     |
|--------------------------|----------------------------|
| Latency (feed-to-order)  | Sub-200ns                  |
| Clock Speed              | 250 MHz+                   |
| Ethernet Throughput      | 10Gbps x 3                 |
| FPGA Platform            | Kintex-7 / UltraScale+     |

---

##  Strengths

- **Ultra-low latency**: Avoids OS-level delays and reduces critical path to nanoseconds.
- **Parallel Processing**: Multi-port MACs enable simultaneous stream handling.
- **Direct-to-Exchange**: TCP/IP stack bypass allows raw protocol interaction.

---

##  Tech Stack

- **Xilinx Vivado** (Synthesis, IP integration, Timing Closure)
- **Verilog / VHDL**
- **AXI-lite & DMA interfaces**
- **10G Ethernet MACs**
- **Draw.io** for architectural diagrams

---



