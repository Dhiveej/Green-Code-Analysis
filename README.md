# Python Energy Microscope Dataset

This dataset provides detailed measurements of energy consumption, execution time, and carbon footprint for five Python execution methods across 15 benchmark algorithms. The dataset supports research in green computing, sustainability metrics, and energy-efficient software development.

## 📁 Directory Structure

```

PYTHON-ENERGY-MICROSCOPE-DATASET/
│
├── aggregate/                      # Aggregated average metrics (per algorithm per method)
│   ├── carbon\_footprint.csv
│   ├── energy\_com.csv
│   └── time\_com.csv
│
├── analysis/                       # Derived metrics, normalized values, scores
│   ├── carbon\_nom\_score.csv
│   ├── energy\_nom\_score.csv
│   ├── energy\_vs\_carbon\_vs\_time.csv
│   ├── green\_score\_components\_means.csv
│   ├── green\_score\_ranking.csv
│   ├── std\_summary.csv
│   └── time\_nom\_score.csv
│
├── cpython/                        # Raw measurements (50 runs each)
│   ├── energy/
│   │   ├── <15 benchmark CSVs>
│   │   └── energy\_avg.csv
│   └── time/
│       ├── <15 benchmark CSVs>
│       └── time\_avg.csv
│
├── ctypes/                         # Same structure for ctypes
│   ├── energy/
│   └── time/
│
├── cython/                         # Same structure for cython
│   ├── energy/
│   └── time/
│
├── pycompile/                      # Same structure for py\_compile
│   ├── energy/
│   └── time/
│
├── pypy/                           # Same structure for PyPy
│   ├── energy/
│   └── time/
│
├── inputs/                         # Benchmark scripts and config inputs (optional)
│
├── LICENSE                         # MIT License
├── README.md                       # This file
└── system\_info.json                # Hardware and OS details of the test environment

````

| File Path                                   | Description                                                            |
| ------------------------------------------- | ---------------------------------------------------------------------- |
| `aggregate/energy_com.csv`                  | Average energy consumption (μJ) per algorithm per execution method     |
| `aggregate/time_com.csv`                    | Average execution time (s) per algorithm per execution method          |
| `aggregate/carbon_footprint.csv`            | Derived carbon footprint (gCO₂eq) using conversion factor              |
| `analysis/energy_nom_score.csv`             | Normalized energy scores (min-max scaled)                              |
| `analysis/time_nom_score.csv`               | Normalized time scores (min-max scaled)                                |
| `analysis/carbon_nom_score.csv`             | Normalized carbon scores (min-max scaled)                              |
| `analysis/energy_vs_carbon_vs_time.csv`     | Combined view of normalized energy, carbon, and time                   |
| `analysis/green_score_components_means.csv` | Mean of normalized energy, time, and carbon per method                 |
| `analysis/green_score_ranking.csv`          | Final GreenScore and ranking per method                                |
| `analysis/std_summary.csv`                  | Standard deviation of energy, time, and carbon across benchmarks       |
| `<method>/energy/<algorithm>.csv`           | Raw energy (μJ) measurements for each of the 15 benchmarks (50 trials) |
| `<method>/time/<algorithm>.csv`             | Raw time (s) measurements for each of the 15 benchmarks (50 trials)    |
| `<method>/energy_avg.csv`                   | Per-algorithm average energy (μJ) for a method                         |
| `<method>/time_avg.csv`                     | Per-algorithm average time (s) for a method                            |
| `system_info.json`                          | System specs used for all benchmarks (CPU, RAM, OS, etc.)              |


## 💻 Execution Methods

The following Python execution methods were analyzed:

- `cpython` — Standard Python interpreter
- `ctypes` — Native C bindings
- `cython` — Compiled Python extensions using C
- `pycompile` — Precompiled Python bytecode
- `pypy` — JIT-enabled Python interpreter

Each method was evaluated using:

- 15 CLBG-style benchmarks
- 50 repeated runs for each method–algorithm pair
- CPU energy via `pyRAPL` (Intel RAPL interface)
- Time via `time.time()`
- Carbon estimation using 0.000475 gCO₂eq per J

## 📊 Metrics Collected

| Metric              | Unit       | Source                  |
|---------------------|------------|--------------------------|
| Energy Consumption  | μJ         | pyRAPL (Intel RAPL)     |
| Execution Time      | s          | Python `time` module     |
| Carbon Footprint    | gCO₂eq     | Derived from energy     |
| GreenScore          | Unitless   | Weighted normalized mean|

## 📦 Notable Files

| File                                      | Description |
|-------------------------------------------|-------------|
| `aggregate/energy_com.csv`               | Average energy per benchmark/method |
| `analysis/green_score_ranking.csv`       | GreenScore (composite metric) ranking |
| `analysis/std_summary.csv`               | Standard deviations for metrics |
| `system_info.json`                       | Hardware and environment config |

## 📜 License

![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)

## 📚 Citation

If you use this dataset in your research, please cite:

```bibtex
@misc{python_energy_microscope_2025,
  title = {Python Energy Microscope Dataset},
  author = {Shadab Turja, M. F. and contributors},
  howpublished = {\url{https://www.kaggle.com/datasets/YOUR_USERNAME/python-energy-microscope-dataset}},
  year = {2025},
  note = {Accessed: 2025-06}
}
````

## 🤝 Contributing

Contributions are welcome. Please open an issue or pull request for improvements or corrections.

## 🔍 More Info

This dataset supports the paper:
**"Python Under the Microscope: A Comparative Energy Analysis of Execution Methods"**
(Submitted to a Q1 journal in sustainable computing / green software engineering.)