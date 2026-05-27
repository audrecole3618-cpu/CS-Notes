# 🧠 Crash Course Computer Science Database

Welcome to the core repository for fundamental computing systems. Use this database to review architectural mechanics, logic gates, and software engineering paradigms.

---

## ⚡ Block 1: Hardware Foundations

### ⚙️ 1. Electronic Computing
* **Thermionic Valves (Vacuum Tubes):** Early digital switches that controlled electric current. Prone to overheating and high failure rates.
* **The Transistor:** The foundational bedrock of modern solid-state computing. Acts as a microscopic, high-speed electronic switch (On = `1`, Off = `0`).

### 🎛️ 2. Boolean Logic & Gates
Computers process raw data using Boolean algebra where operations yield true (`1`) or false (`0`) outputs.

* **AND Gate:** Outputs `1` **only** if all inputs are `1`.
* **OR Gate:** Outputs `1` if **at least one** input is `1`.
* **NOT Gate:** Inverts the input signal (turns `1` to `0`, and `0` to `1`).
* **XOR (Exclusive OR):** Outputs `1` only if inputs are different.

| Input A | Input B | AND Output | OR Output | XOR Output |
| :---: | :---: | :---: | :---: | :---: |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

---

## 💾 Block 2: Processors & Memory

### 🧠 1. The Central Processing Unit (CPU)
The operational core that executes programmatic instructions via the **Fetch-Decode-Execute Cycle**:
1. **Fetch:** Retrieves the next instruction from the system's Random Access Memory (RAM).
2. **Decode:** The Control Unit (CU) breaks down the instruction into primitive commands.
3. **Execute:** The Arithmetic Logic Unit (ALU) performs the mathematical or logical computation.

### 🗄️ 2. Memory Hierarchy
Data storage trades speed for capacity across different physical tiers:
* **Registers:** Ultra-fast, microscopic storage locations inside the CPU itself.
* **Cache (L1, L2, L3):** High-speed memory sitting adjacent to the CPU cores to buffer frequently used instructions.
* **RAM (Random Access Memory):** Volatile workspace memory. Fast read/write cycles, but clears completely when the system loses power.
* **Storage (SSD/HDD):** Non-volatile permanent storage for file payloads and applications.

---

## 🛠️ Quick Reference Terminal Commands
> ⚠️ **Note:** Always verify your working directory before running git execution trees.

```bash
# Push updates from your local vault up to the cloud matrix
git add .
git commit -m "Updated crash course database"
git push origin main