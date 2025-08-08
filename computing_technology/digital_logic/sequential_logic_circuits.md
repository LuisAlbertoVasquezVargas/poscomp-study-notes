<!-- File: digital_logic/sequential_logic_circuits.md -->

# ⚙️ Sequential Logic Circuits

Sequential logic circuits are digital circuits whose outputs depend on the current inputs and the stored internal state.

---

## 🧩 Memory Elements: Latches and Flip-Flops

Memory elements store bits of information. They form the basis of sequential circuits.

---

## 🔹 SR Latch (Set-Reset Latch)

### Behavior:
- Has two inputs: `S` (Set) and `R` (Reset), and two outputs `Q` and `Q̅`.
- When `S=1` and `R=0`, sets `Q=1`.
- When `S=0` and `R=1`, resets `Q=0`.
- When `S=R=0`, holds previous state.
- `S=R=1` is an **invalid state** causing unpredictable behavior.

### NAND Gate Implementation:

- Constructed with **two cross-coupled NAND gates**.
- Inputs are active low:  
  - `S̅` and `R̅` are the NAND inputs.
- Truth table for NAND SR Latch:

| S̅ | R̅ | Q (next) | Description          |
|----|----|-----------|----------------------|
| 0  | 1  | 1         | Set                  |
| 1  | 0  | 0         | Reset                |
| 1  | 1  | Hold      | No change            |
| 0  | 0  | Invalid   | Forbidden (both low) |

---

## 🔹 D Flip-Flop (Data or Delay Flip-Flop)

### Behavior:
- One data input `D`, clock input `CLK`.
- On clock edge, output `Q` follows input `D`.
- Prevents invalid SR states by design.

### Implementation from SR Latch:

- Built as a **master-slave configuration** of SR latches.
- Input logic converts `D` and `CLK` into valid `S` and `R` signals.
- Ensures `S` and `R` are never active simultaneously.
  
### NAND Gates View:

- Additional NAND gates generate `S` and `R` signals from `D` and `CLK`.
- The master latch captures the input on one clock phase; the slave latch updates output on opposite clock phase.
- This arrangement ensures edge-triggered behavior.

---

## 🔹 JK Flip-Flop

### Behavior:
- Inputs `J` and `K`, clock input `CLK`.
- Next state logic:
  - `J=K=0`: hold current state.
  - `J=0`, `K=1`: reset (`Q=0`).
  - `J=1`, `K=0`: set (`Q=1`).
  - `J=K=1`: toggle (`Q` flips).

### Implementation from SR Latch:

- Based on a clocked SR latch with feedback loops.
- The feedback via NAND gates modifies inputs dynamically to allow toggling.
- Master-slave configuration used for edge-triggering.

### NAND Gates Explanation:

- Uses NAND gates to implement SR latch core.
- Inputs `J`, `K`, and current output feedback combine through NAND gates to control `S` and `R`.
- When `J=K=1`, feedback toggles output.

---

## 🔍 Summary of NAND Gate Memory Elements

| Element    | Inputs          | Core Structure             | Key Feature                                  |
|------------|-----------------|----------------------------|----------------------------------------------|
| SR Latch   | S, R            | Two cross-coupled NAND gates | Stores 1 bit, but `S=R=1` forbidden          |
| D Flip-Flop| D, CLK          | SR latch + input logic + master-slave | Eliminates forbidden states, edge triggered |
| JK Flip-Flop| J, K, CLK      | Clocked SR latch + feedback | Supports toggle, set, reset, hold            |

---

