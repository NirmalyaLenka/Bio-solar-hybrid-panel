# Bio-Solar Hybrid Panel Simulation

A Jupyter notebook exploring a conceptual combination of photovoltaic (PV) electricity generation and algae cultivation. The current artifact is a **parameter-driven simulation**, not a connected PV/algae hardware controller or a validated energy-production model.

## Project status

- **Main entry point:** [`Bio_Solar_hybrid_panel.ipynb`](Bio_Solar_hybrid_panel.ipynb)
- **Runtime:** Python 3 notebook (Jupyter or Google Colab)
- **Current scope:** Illustrative equations, plots, a simplified heat-transfer estimate, and a Graphviz workflow diagram.
- **Validation:** The notebook was inspected for this documentation update but was not executed or scientifically validated in this pass. Saved notebook outputs are simulation outputs, not measurements from a physical system.

The notebook's embedded Colab badge currently references a different repository. To use this copy, open the notebook from this repository in GitHub, download it, or use the link below to open the file in Colab.

[Open this notebook in Google Colab](https://colab.research.google.com/github/NirmalyaLenka/Bio-solar-hybrid-panel/blob/main/Bio_Solar_hybrid_panel.ipynb)

## What the notebook models

Run the notebook cells from top to bottom.

| Section | Model / output | Important assumptions |
|---|---|---|
| Algae growth | Monod-style growth-rate curve against CO₂ concentration | Uses fixed `mu_max = 0.6 day⁻¹` and `K_s = 0.1 g/L`; not fitted to experimental data. |
| Heat transfer | Ideal energy requirement and time estimate for warming reactor water | Assumes 10 kg of water, a 5 K temperature change, and a constant 500 W heat source; heat losses and coupling efficiency are ignored. |
| CO₂ absorption | Linear curve against algae biomass concentration | Uses a fixed coefficient of 1.5; the units and coefficient need validation before quantitative use. |
| Biomass over time | ODE solution plotted over 10 days | Starts at 0.1 g/L biomass and uses constant CO₂ concentration of 0.5 g/L; light, nutrients, temperature, and other limiting factors are not modelled. |
| Workflow diagram | Graphviz diagram of the conceptual PV/algae process | The final cell writes a local `workflow_diagram.png` output file. |

## Requirements

- Python 3.8 or newer is a reasonable starting point; compatibility with a specific Python release has not been tested in this pass.
- Python packages: `numpy`, `matplotlib`, `scipy`, and `graphviz`.
- The optional workflow-diagram cell also needs the Graphviz system executable installed and available on `PATH`.

## Run locally

From the repository root:

### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install numpy matplotlib scipy graphviz notebook
jupyter notebook Bio_Solar_hybrid_panel.ipynb
```

If PowerShell blocks activation, use the Python environment according to your local execution policy or activate it from Command Prompt with `.venv\\Scripts\\activate.bat`.

### macOS / Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install numpy matplotlib scipy graphviz notebook
jupyter notebook Bio_Solar_hybrid_panel.ipynb
```

To skip the workflow diagram, run the numerical/plotting cells and skip the Graphviz cell. If you want the diagram, install Graphviz from [graphviz.org](https://graphviz.org/download/) in addition to the Python package.

## Run in Google Colab

1. Open `Bio_Solar_hybrid_panel.ipynb` using the link above or upload the notebook to Colab.
2. Run the cells in order.
3. If the Graphviz cell fails, install both the Python `graphviz` package and the system Graphviz executable in that runtime, then rerun the cell.

The notebook performs calculations and creates plots; it does not connect to a solar panel, read sensors, control pumps, or collect live data. The workflow cell writes a PNG in the notebook's working directory. No other system-level action is required by the inspected notebook.

## Repository layout

```text
.
├── Bio_Solar_hybrid_panel.ipynb        # Main simulation notebook
├── biosolar_hybrid_panel_report.docx   # Supporting report document
├── biosolar_hybrid_panel_report (1).docx
├── biosolar_hybrid_panel_report (2).docx
└── README.md                           # Setup, model assumptions, limitations
```

Three similarly named DOCX reports are present. Their contents were not available through the text-based repository reader used for this pass, so this README does not identify a canonical report version. Compare them before submitting or sharing a report.

## Known limitations

- All model parameters are hard-coded example values; there is no calibration dataset or experimental validation in the notebook.
- The heat-transfer calculation is an ideal energy balance and does not account for thermal losses, changing panel temperature, reactor geometry, or heat-transfer efficiency.
- The algae-growth model omits light saturation, nutrients, temperature, pH, contamination, and other biological constraints.
- The CO₂ absorption model is a simple linear relationship; do not treat its output as a verified capture rate.
- The notebook does not calculate net electrical energy after pumps, cooling, or other auxiliary loads.
- The embedded Colab badge inside the notebook points to a different repository; use the README link above to open this repository's copy.
- No automated tests or execution results are claimed for this maintenance pass.

## Project direction

This is an ongoing exploratory project. Biomass-based energy production remains an open challenge, and alternative approaches need to be compared using reproducible assumptions and measured data before making efficiency or sustainability claims.

## License

No license file is present in this repository. Reuse and redistribution terms are therefore not explicitly specified; add a license if you intend to publish the notebook or reports for reuse.

## Maintenance & audit

- **Audit date:** 12 November 2026
- **Scope:** Documentation update based on the actual notebook cells and root-level file listing.
- **Verification:** The notebook was inspected but not executed in this pass. The DOCX files were not opened or compared. No experimental or hardware results are claimed.
