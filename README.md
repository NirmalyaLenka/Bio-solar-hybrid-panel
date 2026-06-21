# Bio-Solar Hybrid Panel Simulation

This README provides instructions for setting up and running the simulation for the Bio-Solar Hybrid Panel system, which combines solar PV panels and algae bioreactors to produce electricity and biofuel while absorbing CO₂.

---

## **Contents**
1. [Project Overview](#project-overview)
2. [Requirements](#requirements)
3. [Setup Instructions](#setup-instructions)
4. [Running the Simulation](#running-the-simulation)
5. [Simulation Components](#simulation-components)
6. [Expected Results](#expected-results)
7. [Troubleshooting](#troubleshooting)

---

## **Project Overview**
The simulation models the following processes:
- **Algae Growth Modeling**: Calculates algae growth based on CO₂ concentration.
- **Heat Transfer Simulation**: Models waste heat from solar panels increasing algae bioreactor efficiency.
- **CO₂ Absorption**: Simulates how algae biomass absorbs CO₂.
- **Full Growth Over Time**: Tracks algae biomass over days with constant CO₂ input.

---

## **Requirements**
Make sure you have the following installed:

1. **Python (>=3.8)**
2. Required Python Libraries:
    - `numpy`
    - `matplotlib`
    - `scipy`
    - `graphviz` (optional for flowcharts)

---

## **Setup Instructions**

1. Clone or download the simulation repository.
   ```bash
   git clone <repository-url>
   cd bio-solar-simulation
   ```

2. Install the required Python libraries:
   ```bash
   pip install numpy matplotlib scipy graphviz
   ```

3. (Optional) Ensure `Graphviz` is installed for generating workflow diagrams.
   - On Ubuntu/Debian:
     ```bash
     sudo apt-get install graphviz
     ```
   - On macOS:
     ```bash
     brew install graphviz
     ```

4. Open the project in your preferred IDE (e.g., VS Code, PyCharm) or text editor.

---

## **Running the Simulation**

Run the Python scripts in the following order:

1. **Algae Growth Modeling**
   ```bash
   python algae_growth.py
   ```
   - This script calculates the algae growth rate under varying CO₂ concentrations and plots the results.

2. **Heat Transfer Simulation**
   ```bash
   python heat_transfer.py
   ```
   - This script calculates the heat transfer from the solar panel to the bioreactor and estimates the time required to heat the bioreactor.

3. **CO₂ Absorption Simulation**
   ```bash
   python co2_absorption.py
   ```
   - This script models how algae biomass absorbs CO₂ as it grows.

4. **Full Growth Over Time**
   ```bash
   python algae_growth_over_time.py
   ```
   - This script tracks algae biomass growth over time using a differential equation solver.

---

## **Simulation Components**

### **1. Algae Growth Modeling**
- Uses the Monod equation to compute algae growth rates under different CO₂ concentrations.
- Generates a plot showing growth rate vs. CO₂ concentration.

### **2. Heat Transfer Simulation**
- Calculates the heat energy transferred from the solar panel to the algae bioreactor.
- Estimates the time required to warm the bioreactor using waste heat.

### **3. CO₂ Absorption**
- Simulates CO₂ absorption based on algae biomass levels.
- Produces a graph showing CO₂ absorbed vs. biomass.

### **4. Full Growth Over Time**
- Models algae growth over several days using constant CO₂ input.
- Solves the growth equation with `scipy.integrate.solve_ivp`.
- Outputs a plot of algae biomass vs. time.

---

## **Expected Results**

1. **Algae Growth Modeling**:
   - A graph showing that growth rate increases with CO₂ concentration and levels off at higher concentrations.

2. **Heat Transfer Simulation**:
   - Estimated heat energy required and time to warm the bioreactor.

3. **CO₂ Absorption**:
   - A graph showing a linear relationship between algae biomass and CO₂ absorption.

4. **Full Growth Over Time**:
   - A graph tracking algae biomass over time, showing exponential growth initially, then slowing as it saturates.

---

## **Troubleshooting**

1. **Missing Libraries**
   - Ensure all required libraries are installed with:
     ```bash
     pip install -r requirements.txt
     ```

2. **Graphviz Errors**
   - Ensure Graphviz is correctly installed. Check its version:
     ```bash
     dot -V
     ```

3. **Script Errors**
   - Check the console output for specific error messages and ensure parameters in the script are correctly set.

---

For additional support, refer to the project documentation or contact the project team.
## this is a ongoing project if anyone see this please contact to my whats app or gmail this means a lot and make me very happy 21-06-2026 (last updated).
as for now the algie power production is not that good i am trying a new method stay tuned for that.

