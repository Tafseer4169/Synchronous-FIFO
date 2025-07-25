---

# 📦 **Synchronous FIFO (First-In-First-Out) Buffer**

The **Synchronous FIFO** module is a parameterizable Verilog implementation of a First-In-First-Out buffer. It is fully synchronous with respect to the system clock and supports configurable data width and depth. This design is ideal for buffered data transfer between producer and consumer modules in FPGA and ASIC designs.

---

## 🧠 **Key Features**

### ⚙️ **Synchronous Operation**

- Fully clocked design with a single system clock (`clk`).
- No asynchronous resets or dual-clock complications.

### 📐 **Parameterized Design**

- `data_width`: Customize the width of each FIFO entry (default 32 bits).
- `fifo_depth`: Configure the number of entries in the FIFO (default 8 entries).

### 🧭 **Control Signals**

- `wr_en` and `rd_en`: Control read and write actions.
- `full` and `empty`: Flags for buffer status.
- `cs`: Chip select to enable FIFO access.
- `rst_n`: Active-low synchronous reset.

### 🧮 **Pointer Logic**

- Automatically handles write and read pointer wrap-around using modular arithmetic.
- Supports circular buffer operation with proper full/empty detection logic.

---

## 🧩 **Port Descriptions**

| Signal        | Direction | Description                            |
|---------------|-----------|----------------------------------------|
| `clk`         | Input     | System clock                           |
| `rst_n`       | Input     | Active-low reset                       |
| `cs`          | Input     | Chip select / enable                   |
| `wr_en`       | Input     | Write enable                           |
| `rd_en`       | Input     | Read enable                            |
| `data_in`     | Input     | Data input to FIFO                     |
| `data_out`    | Output    | Data output from FIFO                  |
| `full`        | Output    | FIFO is full (cannot write)            |
| `empty`       | Output    | FIFO is empty (cannot read)            |

---

## 🏗️ **Architecture Overview**

The FIFO buffer is implemented as:

- A **register array** to store data.
- **Write and read pointers** to manage enqueue and dequeue operations.
- **Full and empty flag logic** based on pointer comparison.
- No simultaneous read and write to same location allowed on same clock cycle.

---

## 🔧 **Tools & Technologies**

- **Verilog HDL**
- **Behavioral modeling**
- Simulatable using:
  - **ModelSim**
  - **Vivado**
  - **Icarus Verilog**
  - Any standard Verilog simulator

---



---

## 📁 **Directory Structure**



---

## 📚 **License**

This project is released under the **MIT License**.  
Feel free to use, modify, and distribute this design with proper attribution.

---

**Thanks for checking out the Synchronous FIFO project!**  
Contributions, testbenches, or improvements are welcome — feel free to open issues or PRs.

---


