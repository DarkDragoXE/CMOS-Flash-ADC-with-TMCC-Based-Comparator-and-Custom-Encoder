# Flash ADC using TMCC and Custom CMOS Logic

This project presents the complete transistor-level design of a **3-bit Flash Analog-to-Digital Converter (ADC)** implemented in **Cadence Virtuoso** using **Threshold-Modulated Current Comparator (TMCC)** architecture.  
The ADC converts an analog input into its digital equivalent using fully custom CMOS logic — from comparators to the encoder — without relying on standard cells.

---

## Overview

The Flash ADC is designed to demonstrate a fast, low-latency conversion process using **TMCC comparators** for analog threshold detection, **custom CMOS logic gates** for signal cleaning, and a **thermometer-to-binary encoder** for digital output generation.  
All blocks are implemented and simulated at the transistor level using **gpdk180 nm CMOS technology**.

---

## Architecture

### 1. TMCC Comparator Stage
- Designed using **Threshold-Modulated Current Comparator (TMCC)** logic.
- Detects when the input voltage exceeds predefined reference levels.
- Converts voltage differences into modulated output currents.
- Generates a **thermometer code** based on comparator activation sequence.

### 2. Logic Conversion Stage
- TMCC outputs are converted to valid digital logic levels using **custom CMOS AND gates**.
- Each AND gate is designed at transistor level using pMOS and nMOS transistors.
- Provides clean logic transitions and level restoration for encoder input.

### 3. Encoder Stage
- Implements a **thermometer-to-binary encoding** scheme using **4-input OR gates**.
- OR gates are built using complementary CMOS logic for speed and minimal power.
- Combines adjacent high bits to form binary outputs representing quantized levels.
- Produces a final 3-bit binary code corresponding to the analog input range.

---

## Design Highlights
- **Fully custom transistor-level design** — no standard logic cells used.
- **TMCC comparators** improve detection sensitivity and speed.
- **Complementary CMOS logic** for all AND/OR gates ensures clean switching.
- **Hierarchical encoder** converts thermometer code to binary output.
- **Simulation verified** in Cadence Virtuoso with Spectre simulator.

---

## Tools and Technology
| Category | Specification |
|-----------|----------------|
| Design Environment | Cadence Virtuoso (ADE L) |
| Simulation Engine | Spectre |
| Technology Node | gpdk180 nm CMOS |
| Supply Voltage | 1.2 V |
| Logic Type | Custom CMOS (pMOS + nMOS) |

---

## Simulation Results
- Verified **comparator functionality** through transient and DC analysis.
- Observed smooth thermometer-to-binary transitions across input voltage range.
- Logic network demonstrated correct binary encoding with minimal propagation delay.
- The design achieved **high-speed performance** suitable for mixed-signal systems.

---


