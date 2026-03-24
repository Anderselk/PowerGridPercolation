# PowerGridPercolation
Simulation of cascading failures in power grids using percolation theory on 2D lattice networks, identifying critical tolerance thresholds for system-wide blackouts.
# Power Grid Cascading Failures as Percolation

## Overview
Modern electrical grids are vulnerable to cascading failures, where a single transmission line fault can trigger widespread outages. This project models such failures using **percolation theory**, exploring whether power grid cascades exhibit phase-transition behavior similar to classical percolation systems.

Using a 2D lattice network representation of a power grid, this simulation investigates how **tolerance margins** (capacity buffers) influence the likelihood of large-scale failures.

---

## Key Question
> Does the margin between operating load and transmission capacity exhibit a **critical threshold** beyond which cascading failures are avoided?

---

## Model Description

### Network Structure
- Grid: \( L \times L \) 2D lattice
- Nodes: substations
- Edges: transmission lines
- Boundary: non-periodic

## Cascade Algorithm

1. **Initial Failure**
   - Random edge removal

2. **Load Redistribution**
   - Failed edge load redistributed to neighboring edges

3. **Failure Check**
   - Edges exceeding capacity fail

4. **Iteration**
   - Repeat until equilibrium

## Simulation Parameters

| Parameter | Values |
|----------|--------|
| Grid Size \(L\) | 12, 20, 30 |
| Tolerance \( \tau \) | 0.1 → 0.9 |
| Step Size | 0.04 |
| Trials per config | 15 |

---

## Results

### Phase Transition Behavior
- Identified a **critical tolerance**:
  \[
  Tau ~ 0.42
  \]

- Regimes:
  - **Fully Cascaded**: \( Tau < 0.14 \)
  - **Partial Cascades**: \( 0.14 < Tau < 0.42 \)
  - **Stable**: \( Tau > 0.42 \)

### Key Insights
- Small increases in tolerance dramatically reduce cascade risk
- Larger grids are **more vulnerable** to cascading failures
- Behavior resembles—but differs from—classical percolation

---

## Example Visualizations

### Edge Survival Probability vs Tolerance
- Sharp transition near \( Tau ~ 0.42 \)

### Cascade Size vs Tolerance
- Rapid drop-off in failures as tolerance increases

---

## Installation

```bash
git clone https://github.com/yourusername/power-grid-cascade-percolation.git
cd power-grid-cascade-percolation
pip install numpy networkx matplotlib
