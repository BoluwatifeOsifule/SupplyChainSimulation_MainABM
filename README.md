# Supply Chain Simulation - Agent-Based Economy Model

An agent-based modeling (ABM) simulation demonstrating supply and demand dynamics through autonomous consumer and supplier agents interacting in a spatial grid environment.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Mesa](https://img.shields.io/badge/mesa-2.0+-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## Overview

This project implements a microeconomic simulation where consumers with limited budgets interact with suppliers who have inventory to sell. Through simple transaction rules and spatial movement, the model demonstrates emergent market behavior and wealth distribution patterns.

## Features

- **Agent-Based Modeling**: Autonomous consumer and supplier agents with distinct behaviors
- **Spatial Economics**: Grid-based environment with Moore neighborhood movement
- **Market Dynamics**: Real-time supply-demand matching and transaction processing
- **Statistical Analysis**: Income and revenue distribution visualization
- **Scalable Architecture**: Configurable agent populations and simulation parameters

## Quick Start

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Installation

1. Clone the repository:
```bash
git clone https://github.com/BoluwatifeOsifule/SupplyChainSimulation_OsifuleBoluwatife.git
cd SupplyChainSimulation_OsifuleBoluwatife
```

2. Create a virtual environment (recommended):
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### Usage

Run the simulation:
```bash
python SupplyChainEffect.py
```

The simulation will:
- Execute 100 time steps
- Print progress for each step
- Display two statistical visualizations:
  - Consumer income distribution
  - Supplier revenue distribution

## How It Works

### Agent Types

#### Consumer Agent
- **Initial Income**: 50 units
- **Demand**: 5 goods
- **Behavior**: Moves randomly and purchases goods from suppliers
- **Transaction Cost**: 5 units per good

#### Supplier Agent
- **Initial Inventory**: 50 goods
- **Supply Quota**: 5 goods available
- **Behavior**: Moves randomly and sells goods to consumers
- **Revenue**: Accumulates from successful transactions

### Simulation Flow

1. **Initialization**: 4,000 consumers and 400 suppliers placed randomly on a 30×30 grid
2. **Movement**: All agents move in random directions (including diagonals)
3. **Transactions**: When agents occupy the same cell:
   - Consumer checks if they have sufficient income and demand
   - Supplier checks if they have available inventory
   - If conditions are met: goods and money are exchanged
4. **Iteration**: Process repeats for 100 time steps

## Configuration

Modify simulation parameters in `SupplyChainEffect.py`:

```python
# Model initialization
model = Economy_Model(
    C=4000,      # Number of consumers
    S=400,       # Number of suppliers
    width=30,    # Grid width
    height=30    # Grid height
)

# Simulation duration
for i in range(100):  # Number of time steps
    model.step()
```

### Agent Parameters

Customize agent attributes in their class definitions:

```python
# Consumer_Agent
self.Demand = 5        # Goods to purchase
self.income = 50       # Initial budget
self.commodities = 0   # Starting inventory

# Supplier_Agent
self.Supply = 5           # Goods available
self.produced_goods = 50  # Total inventory
self.revenue = 0          # Starting capital
```

## Output

The simulation generates two histogram plots with kernel density estimation:

1. **Consumer Income Distribution**
   - Shows wealth distribution after market interactions
   - Reveals economic inequality patterns

2. **Supplier Revenue Distribution**
   - Displays earnings across supplier population
   - Indicates market competition effects

## Technical Stack

- **Mesa**: Agent-based modeling framework
- **Matplotlib**: Data visualization
- **Seaborn**: Statistical plotting
- **NumPy**: Numerical computing

## 📁 Project Structure

```
SupplyChainSimulation_OsifuleBoluwatife/
├── SupplyChainEffect.py    # Main simulation script
├── README.md               # This file
├── requirements.txt        # Python dependencies
├── .gitignore             # Git ignore rules
└── COMMIT_GUIDELINES.md   # Contribution guidelines
```

## Research Applications

This model can be extended to study:

- Market equilibrium dynamics
- Price elasticity mechanisms
- Wealth inequality emergence
- Supply chain optimization
- Agent learning strategies
- Multi-commodity markets
- Network effects and clustering

##  Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes following our [commit guidelines](COMMIT_GUIDELINES.md)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Author

**Boluwatife Osifule**

- GitHub: [@BoluwatifeOsifule](https://github.com/BoluwatifeOsifule)

## Acknowledgments

- Built with the [Mesa](https://mesa.readthedocs.io/) framework
- Inspired by agent-based computational economics research
- Thanks to the open-source community

## References

- Epstein, J. M., & Axtell, R. (1996). Growing Artificial Societies: Social Science from the Bottom Up
- Tesfatsion, L. (2006). Agent-Based Computational Economics: A Constructive Approach to Economic Theory
- Mesa Documentation: https://mesa.readthedocs.io/

---

