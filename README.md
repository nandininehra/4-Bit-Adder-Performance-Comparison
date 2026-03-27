# 4-Bit-Adder-Performance-Comparison

# 4-Bit Adder Performance Comparison (RCA vs CLA)

## 📌 Overview

This project implements and compares two fundamental digital adders:

* Ripple Carry Adder (RCA)
* Carry Look-Ahead Adder (CLA)

The objective is to analyze timing performance and understand how carry propagation impacts delay in digital circuits.

---

## ⚙️ Design Details

### Ripple Carry Adder (RCA)

* Built using cascaded full adders
* Carry propagates sequentially from LSB to MSB
* Simple design but higher delay

### Carry Look-Ahead Adder (CLA)

* Uses Generate (G) and Propagate (P) logic
* Carry computed in parallel
* Faster than RCA but more complex

---

## ⏱️ Simulation Setup

* Language: Verilog/SystemVerilog
* Simulator: Icarus Verilog
* Waveform Viewer: GTKWave
* Gate delay modeled using `#5` to visualize timing differences

---

## 🔍 Key Observations

### 1. Delay Behavior

* RCA output shows **multiple intermediate transitions** before stabilizing
* CLA output stabilizes **faster with minimal transitions**

### 2. Carry Propagation

* RCA exhibits **sequential carry propagation**
* CLA computes carry **in parallel**

### 3. Critical Path

* RCA critical path is the carry chain across all bits
* CLA reduces critical path using parallel logic

---

## 📊 Waveform Analysis

The waveform below demonstrates the difference in timing behavior:

* RCA output transitions through intermediate states (1110 → 1100 → 1000 → 0000)
* CLA output stabilizes quickly
* Carry-out (cout_rca) appears later than (cout_cla)

![Waveform](waveform.png)

---

## 🚀 Key Learning Outcomes

* Understanding of timing delays in combinational circuits
* Difference between sequential and parallel carry computation
* Importance of critical path in digital design
* Practical exposure to waveform-based timing analysis

---

## 📁 Files

* `design.sv` → Contains full adder, RCA, and CLA implementations
* `testbench.sv` → Testbench for applying inputs and observing outputs
* `waveform.png` → Simulation waveform showing delay comparison

---

## 💡 Conclusion

The project demonstrates that CLA significantly reduces delay compared to RCA by eliminating ripple carry dependency, making it more suitable for high-speed digital systems.
