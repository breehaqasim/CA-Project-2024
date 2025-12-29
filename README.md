# 🧠 RISC-V Pipelined Processor

This repository contains the implementation of a **5-stage pipelined RISC-V processor** developed as part of the **Computer Architecture** course at **Habib University (Spring 2024)**. The project focuses on designing, simulating, and evaluating both **single-cycle** and **pipelined** RISC-V processors, with a complete execution of the **bubble sort algorithm** as a benchmark workload.

---

## 👥 Team
- **Breeha Qasim** – Group Member  
- **Ashbah Faisal** – Group Member  
- **Rameez Wasif** – Group Member  

**Research Assistant:** Maham Tabassum  
**Course Instructor:** Dr. Tariq Kamal  

---

## 📌 Project Overview
The project involved building a functional RISC-V processor from the ground up and progressively enhancing it with pipelining and hazard handling mechanisms. The primary goals were to understand instruction-level parallelism, pipeline behavior, and performance trade-offs between different processor architectures.

Key objectives included:
- Translating a **bubble sort algorithm** from pseudocode to **RISC-V assembly**
- Executing and validating the assembly code using the **Venus simulator**
- Implementing the algorithm on a **single-cycle RISC-V processor**
- Extending the design to a **5-stage pipelined RISC-V processor**
- Designing and integrating **hazard detection and forwarding units**
- Comparing performance between single-cycle and pipelined implementations

---

## 🏗 Architecture Details

### 🔹 Single-Cycle Processor
- Modified from a previous lab implementation
- Updates made to:
  - Instruction Memory
  - Data Memory
  - Register File
  - ALU and ALU Control
  - Branch and Control Units
- Successfully executes the bubble sort algorithm without pipelining

### 🔹 Pipelined Processor
The pipelined processor follows a classic **5-stage RISC-V pipeline**:
- **IF** – Instruction Fetch  
- **ID** – Instruction Decode  
- **EX** – Execute  
- **MEM** – Memory Access  
- **WB** – Write Back  

Pipeline registers implemented:
- IF/ID  
- ID/EX  
- EX/MEM  
- MEM/WB  

Each stage was individually tested to ensure correct instruction flow.

---

## ⚠️ Hazard Detection & Forwarding
To ensure correct execution, the processor includes:
- **Hazard Detection Unit**  
  - Detects data, control, and structural hazards  
  - Inserts pipeline stalls when required (especially load-use hazards)

- **Forwarding Unit**
  - Forwards data between pipeline stages to minimize stalls
  - Reduces performance penalties caused by data dependencies

---

## 🧪 Testing & Simulation
- Bubble sort execution validated through simulation outputs
- Additional test cases (e.g., `addi x5, x0, 2`) used to trace instruction flow
- Pipeline behavior observed and debugged through waveform analysis

---

## 📊 Performance Comparison
| Processor Type | Execution Time |
|----------------|---------------|
| Single-Cycle   | ~1000 ns |
| Pipelined      | >1000 ns |

Although pipelining typically improves performance, the **pipelined processor performed slower** in this case due to:
- Frequent pipeline stalls
- Hazard handling overhead

This highlights real-world trade-offs in processor design.

---

## 🚧 Challenges Faced
- Limited support for double-word instructions in the **Venus simulator**
- Complexity in implementing **branch-equal instructions**
- Managing pipeline hazards without compromising correctness

Each challenge required research and iterative debugging to resolve.

---

## 📚 References
- *Computer Organization and Design: The Hardware/Software Interface (RISC-V Edition)*  
  David A. Patterson, John L. Hennessy

---

## 📂 Repository Contents
- Verilog source files for single-cycle and pipelined processors  
- Hazard detection and forwarding modules  
- Simulation test cases and outputs  
- Project report and supporting documentation  

---

## 🔗 Project Repository
https://github.com/breehaqasim/CA-Project-2024
