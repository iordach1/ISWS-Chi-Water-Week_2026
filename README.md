# ISWS Chicago Water Week 2026 — Participatory Groundwater Modeling

[![Illinois State Water Survey](https://img.shields.io/badge/ISWS-University%20of%20Illinois-13294B)](https://isws.illinois.edu/)
[![Illinois-Indiana Sea Grant](https://img.shields.io/badge/Funded%20by-Illinois--Indiana%20Sea%20Grant-005F86)](https://iiseagrant.org/research-project/bridging-the-gap-developing-water-resource-assessment-tools-for-the-southern-lake-michigan-region/)
[![Current](https://img.shields.io/badge/CWW%20Hosts-Current-269DB6)](https://currentwater.org/)

---

## About This Repository

This repository contains code, a base groundwater flow model, and Jupyter Notebooks for a
**virtual participatory groundwater modeling event** hosted by the
[Illinois State Water Survey (ISWS)](https://isws.illinois.edu/) at the University of Illinois
Urbana-Champaign as part of **Chicago Water Week 2026**.

The event took place on **Monday, May 4th, 2026** from 8AM - 10AM CDT via Zoom. Attendees explored groundwater
questions relevant to Chicago's South Suburbs through live experiments with a "fast-running"
MODFLOW 6 model built in Jupyter Notebook.

---

## ⚠️ Educational Use Disclaimer

The base groundwater model included in this repository is built from **real-world geology and
hydrodynamic data** for the Chicago South Suburbs project area. However, **simplifying
assumptions** have been applied to reduce the model's size and runtime so it can be run
interactively during the demonstration.

> **Results from this model and any modified versions should NOT be used for planning,
> engineering design, or decision-making purposes.** They are intended solely for
> educational exploration and to illustrate participatory groundwater modeling concepts.
> For site-specific or regulatory applications, consult a hydrogeologist and use
> a fully calibrated, peer-reviewed model.

---

## Event Overview

**What happens to our local water supply if we add a *new well*?**

**How does drought *strike back* at our water resources?**

**How does the contamination at the surface *return* to the well, and can we detect a disturbance in the capture zone?**

---

On the second day of 2026 Chicago Water Week — **Monday, May the Fourth** — join ISWS for a two-hour
participatory groundwater modeling event on Zoom, focused on Chicago's South Suburbs. The
session is part presentation, part live workshop, and part low-stakes science adventure.

Attendees will participate in short surveys and polls to prompt a series of questions and experiments with a
MODFLOW 6 model running inside Jupyter Notebook, proving that *these are the models you're
looking for.* The goal is to make groundwater modeling feel **accessible, interactive, and
genuinely useful** — moving it away from the mysterious black box and into a space where
changing inputs and assumptions affects results in real time.

**Co-hosts and lead developers:** Vlad Iordache and Daniel Abrams — Illinois State Water Survey, UIUC

*This event is affiliated with Chicago Water Week, presented by [Current](https://currentwater.org/).*

---

## Repository Structure

```
ISWS-Chi-Water-Week_2026/
├── bin/                          # MODFLOW 6 executable (platform-specific)
├── config/
│   └── environment.yml           # Conda/Mamba environment specification
├── docs/
│   └── setup_instructions.md     # Step-by-step participant setup guide
├── modflow_models/
│   └── uncalibrated_iisg_model/  # Base MODFLOW 6 model files
├── python_notebooks/
│   ├── helper_functions.py       # Shared utilities and DroughtDashboard class
│   ├── intro_base_model.ipynb    # Notebook 1 — Explore and run the base model
│   ├── new_demands.ipynb         # Notebook 2 — Add a new pumping well scenario
│   └── drought_impacts.ipynb     # Notebook 3 — Simulate and visualize drought effects
└── shapefiles/
    └── counties_5070.shp         # Illinois county boundaries (EPSG:5070)
```

---

## Getting Started

### Prerequisites

Participants need:
- A laptop or desktop computer (Windows, macOS, or Linux)
- An internet connection to clone the repository
- ~4 GB of free disk space for the model files and Python environment

### Setup Instructions

Full step-by-step instructions for installing Python (via Miniforge/Mamba), creating the
environment, installing Git, cloning this repository, and launching Jupyter are provided in:

📄 **[`docs/setup_instructions.md`](docs/setup_instructions.md)**

### Quick Start (for experienced users)

```bash
# 1. Clone the repository
git clone https://github.com/iordach1/ISWS-Chi-Water-Week_2026.git
cd ISWS-Chi-Water-Week_2026

# 2. Create the conda environment
mamba env create -f config/environment.yml

# 3. Activate the environment
conda activate state-mf6

# 4. Launch Jupyter
jupyter notebook python_notebooks/intro_base_model.ipynb
```

---

## Notebooks

| Notebook | Description |
|---|---|
| `intro_base_model.ipynb` | Load, inspect, and run the base steady-state MODFLOW 6 model. Visualize heads, water table elevations, and boundary conditions. |
| `new_demands.ipynb` | Convert the base model to a transient simulation, add new pumping wells to the model, run the simulation, and compare results to the base scenario. |
| `drought_impacts.ipynb` | Convert the base model to a transient simulation, reduce recharge to represent drought, run the simulation, and explore spatial and temporal patterns of drawdown using static maps, hydrographs, and an interactive dashboard. |

---

## Funding Acknowledgment

Model development and public outreach activities for this project are funded by the
**Illinois-Indiana Sea Grant College Program Research Grants**.

Illinois-Indiana Sea Grant is a cooperative program of Purdue University and the University
of Illinois administered through NOAA's National Sea Grant College Program in the U.S.
Department of Commerce.

---

## Contact

[**Vlad Iordache**](mailto:iordach1@illinois.edu?subject=ISWS-Chi-Water-Week_2026%20issues%2Ffeedback) — ISWS Assistant Research Scientist - Hydrogeology

[**Daniel Abrams**](mailto:dbabrams@illinois.edu?subject=ISWS-Chi-Water-Week_2026%20issues%2Ffeedback) — ISWS Principal Research Scientist - Groundwater Flow Modeling

Questions about the event or model? Open an issue in this repository or email Vlad and/or Daniel directly.

[Illinois State Water Survey - University of Illinois Urbana-Champaign](https://www.isws.illinois.edu/)
