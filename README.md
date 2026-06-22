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

The `la_project_coffee_shope.py` file is an interactive CLI simulator that brings the mathematical model to life. It lets you test, adjust, and verify the production plan in real time — making it useful for any coffee shop, not just The Daily Grind.

### How to Run

**Requirements:** Python 3.x, `numpy`, `tabulate`

```bash
pip install numpy tabulate
python la_project_coffee_shope.py
```

---

### What the Simulator Shows

Every time you make a change, the simulator instantly refreshes a full dashboard:

**Product Table** — shows each product with:
- Current quantity being produced
- Unit cost (how much it costs to make one)
- Total cost (unit cost × quantity)
- Revenue generated (price × quantity)
- Gross profit (revenue − total cost)

**Key Performance Indicators (KPIs)** — 5 live checks that tell you if your plan is working:

| KPI | What it checks |
|-----|---------------|
| Total Units | Are you within storage/service capacity? |
| Total Revenue | Are you hitting your daily revenue target? |
| Total Budget | Are you staying within ingredient budget? |
| Milk Usage | Are you within your milk supply limit? |
| Staff Labor | Are your staff working within their shift hours? |

Each KPI shows ✅ if the constraint is satisfied or ❌ with a warning (e.g. OVER BUDGET, OVERTIME) if violated.

---

### Simulator Menu — Full Breakdown

```
1: Adjust Qty       → Change production quantities for any product
2: Adjust Limits    → Change your business goals and constraints
3: Adjust Costs     → Change the unit cost of any product
4: Reset            → Restore all values back to the original solution
5: Exit             → Close the simulator
```

#### Option 1 — Adjust Quantities
Change how many units of each product you want to produce today.
Enter 5 values separated by commas (one per product). Use `0` to keep a product unchanged.
```
Example: 30, 0, 0, 0, 0  → changes only Espresso to 30, keeps everything else
```
The dashboard instantly updates to show how this affects revenue, cost, and all KPIs.

#### Option 2 — Adjust Limits *(use this for any shop!)*
Change your business goals and operational constraints to match your real-world numbers.
Enter 5 values: Revenue target, Budget, Milk supply, Labor time, Capacity.
```
Example: 1500, 300, 0, 600, 0  → updates revenue target to $1500, budget to $300, labor to 600 min
```
> 💡 This is what makes the simulator work for **any coffee shop** — just plug in your own targets and constraints and the dashboard recalculates everything instantly.

#### Option 3 — Adjust Costs
Change the unit cost of making each product (useful for testing price fluctuations).
Enter 5 values, use `0` to keep a product's cost unchanged.
```
Example: 2.0, 0, 1.2, 0, 0  → changes Espresso cost to $2.00, Tea cost to $1.20
```
This helps answer questions like *"what happens to our profit if milk prices go up?"*

#### Option 4 — Reset
Restores all quantities, limits, and costs back to the mathematically optimal solution (40/100/60/80/120) so you can start a fresh analysis.

---

### Sensitivity Analysis

By combining options 1, 2, and 3 you can run **"what-if" scenarios**:
- What if we run out of milk halfway through the day?
- What if labor costs increase?
- What if we want to target $2,000 revenue instead?

The simulator flags every constraint violation in real time, helping make smarter data-driven decisions.

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

## A Note on Development Process

This project was developed using **AI-assisted development** as part of my learning workflow. I used AI tools to help structure the Python simulator, debug constraint logic, and improve the dashboard layout — however, the mathematical modeling, RREF solution, and all core decisions were worked through and understood by me personally.

I believe using AI as a thinking partner is a real and valuable skill in modern software development. My approach involved:
- Working through the system of equations and matrix operations myself first
- Using AI to help translate the mathematical model into working Python code
- Critically reviewing every suggestion and verifying it against the manual solution
- Making my own modifications to add features like dynamic cost adjustment and real-time KPI tracking
- Testing all scenarios including edge cases where constraints are violated

The combination of manual mathematical reasoning and AI-assisted coding is exactly how modern data-driven tools are built — this project reflects that workflow honestly.

---

## Author

**Asma Amin**
BSIT Student — Lahore Garrison University
