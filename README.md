# Coffee Shop Optimizer ☕

A Linear Algebra entrepreneurial modeling project that uses a **5-variable system of linear equations** to find the optimal daily production mix for a coffee shop — verified through a Python CLI simulator.

---

## About

This project applies Linear Algebra to a real-world business problem. Given five product categories and five operational constraints (revenue, budget, labor, milk supply, and capacity), the goal is to find the exact production quantities that satisfy all constraints simultaneously.

The system was first solved manually using Row Reduction (RREF) and then verified computationally using Python.

Built as part of my Linear Algebra coursework at Lahore Garrison University.

> **Note:** This was a group project. I was personally responsible for the complete mathematical modeling, Python implementation, and technical documentation.

---

## The Business Problem

**"The Daily Grind"** coffee shop needs to determine how many units of each product to prepare daily to hit a $1,420 revenue target — without exceeding its ingredient budget, labor hours, or storage capacity.

### Products
| Variable | Product |
|----------|---------|
| E | Espresso |
| D | Drip Coffee |
| T | Specialty Tea |
| P | Pastries |
| B | Bottled Beverages |

### Constraints (System of Equations)
```
Revenue:   5E + 3D + 4T + 4P + 3B = 1420
Budget:    1E + 0.5D + 0.8T + 1.2P + 0.5B = 294
Labor:     4E + 1D + 2T + 1P + 0.5B = 520
Milk:      10E + 5T = 700
Capacity:  E + D + T + P + B = 400
```

### Solution (via RREF)
```
Espresso (E):          40 units
Drip Coffee (D):      100 units
Specialty Tea (T):     60 units
Pastries (P):          80 units
Bottled Beverages (B): 120 units
```

---

## Python Simulator

The `la_project_coffee_shope.py` file is an interactive CLI simulator that:

- Displays a live dashboard with revenue, cost, and gross profit per product
- Tracks 5 Key Performance Indicators (KPIs) in real time
- Allows adjusting quantities, operational limits, and unit costs
- Validates all constraints and flags violations instantly

### How to Run

**Requirements:** Python 3.x, `numpy`, `tabulate`

```bash
pip install numpy tabulate
python la_project_coffee_shope.py
```

### Simulator Menu
```
1: Adjust Qty
2: Adjust Limits
3: Adjust Costs
4: Reset
5: Exit
```

---

## Key Insight

> *"To reach the $1,420 goal, the shop must sell the specific mix of 40/100/60/80/120 — it is the only combination that satisfies budget, labor, milk supply, and capacity simultaneously."*

---

## Tech Stack

- Language: Python 3
- Libraries: NumPy, Tabulate
- Math: Linear Algebra (RREF, Matrix Inversion)
- Interface: Command Line (CLI)

---

## Author

**Asma Amin**
BSIT Student — Lahore Garrison University
