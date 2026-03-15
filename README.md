# Assignment 2 - Simon's Algorithm
### Quantum Computing | Sujoy Dey

---

## Repository Contents

| File | Description |
|------|-------------|
| `Sujoy_Dey_Assignment_2_Part_A.ipynb` | Simon's Algorithm for the reference 3-bit secret string **s = 011** |
| `Sujoy_Dey_Assignment_2_Part_B_C.ipynb` | Simon's Algorithm for the 5-bit secret string **s = 10110** + Classical Post-Processing |
| `Sujoy_Dey_Assignment_2_Report.docx` | Full written report covering Parts A, B, and C |
| `README.md` | This file |

---

## Chosen 5-bit Secret String

```
s = 10110
```

---

## How to Run the Notebooks

### Prerequisites

Make sure you have the following installed:

```bash
pip install qiskit qiskit-aer pylatexenc matplotlib
```

### Part A - Reference Implementation (s = 011)

Open and run `Sujoy_Dey_Assignment_2_Part_A.ipynb` from top to bottom.

- Implements Simon's Algorithm for the 3-bit secret string `s = 011`
- Uses a 6-qubit circuit (3 query + 3 ancilla)
- Runs 2000 shots on the Qiskit Aer simulator
- Expected output: only the 4 valid strings `{000, 011, 100, 111}` appear

### Part B & C - 5-bit Implementation + Classical Solver

Open and run `Sujoy_Dey_Assignment_2_Part_B___C.ipynb` from top to bottom.

- **Part B**: Implements Simon's Algorithm for the 5-bit secret string `s = 10110`
  - Uses a 10-qubit circuit (5 query + 5 ancilla)
  - Runs 2000 shots on the Qiskit Aer simulator
  - Outputs 15 valid non-trivial bit strings satisfying `u · s = 0 (mod 2)`
- **Part C**: Classical post-processing
  - Constructs the system of equations `Us = 0 (mod 2)`
  - Brute-force searches all 31 non-zero 5-bit candidates
  - Recovers and verifies the secret string

---

## Recovered Value of s

The classical post-processing in Part C successfully recovered:

```
s = 10110
```

This matches the original secret string encoded in the Simon oracle, confirming the algorithm worked correctly end-to-end.

---

## Key Results Summary

| Part | Secret String | Valid Strings Measured | Recovered s |
|------|--------------|------------------------|-------------|
| A    | `011` (3-bit) | `{000, 011, 100, 111}` - all 4 valid | N/A (reference) |
| B & C | `10110` (5-bit) | 15 non-trivial + `00000` - all 16 valid | `10110` ✓ |
