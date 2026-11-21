# APB Master RTL Design

## Project Overview
This project implements an APB (Advanced Peripheral Bus) Master using Verilog HDL, following the AMBA APB protocol. The design supports read and write transactions with proper protocol handshaking and wait-state handling.

## Features
- APB Master RTL design using Verilog HDL.
- Supports read and write operations.
- Implements APB protocol handshaking using PSEL, PENABLE, PWRITE, and PREADY signals.
- Supports wait-state handling during read and write transactions.
- Generates address and write data signals for APB transactions.

## APB Signals

| Signal | Description |
|---|---|
| PCLK | APB clock |
| PRESETn | Active-low reset |
| PSEL | Peripheral select |
| PENABLE | Enable signal |
| PWRITE | Read/write control |
| PADDR | Address bus |
| PWDATA | Write data bus |
| PRDATA | Read data bus |
| PREADY | Transfer ready signal |

## APB Operations

### 1. Write Operation
- Master selects the peripheral using PSEL.
- Asserts PENABLE during the access phase.
- Provides the address and write data.
- Completes the transfer when PREADY is HIGH.

### 2. Read Operation
- Master provides the address and selects the peripheral.
- Asserts PENABLE during the access phase.
- Receives read data through PRDATA.
- Completes the transfer when PREADY is HIGH.

### 3. Wait State Handling
- When PREADY is LOW, the transfer is extended.
- Master maintains the control and address signals.
- Transfer completes when PREADY becomes HIGH.

## Tools and Technologies
- **HDL:** Verilog
- **Simulation Platform:** Cadence Xcelium 25.03

## Simulation
The RTL design was simulated using EDA Playground to observe APB read, write, and wait-state transactions through simulation waveforms.

## Conclusion
Successfully implemented an APB Master supporting read and write transactions with wait-state handling according to the AMBA APB protocol.
