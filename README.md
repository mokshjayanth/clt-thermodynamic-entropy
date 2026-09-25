# Thermodynamic Entropy Through the Central Limit Theorem

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mokshjayanth/clt-thermodynamic-entropy/blob/main/notebooks/molecular_distribution_demo.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22967985.svg)](https://doi.org/10.5281/zenodo.22967985)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

An interactive pedagogical demonstration showing how the Central Limit Theorem explains the emergence of thermodynamic behavior in macroscopic systems.

## Overview

This repository contains an interactive Jupyter notebook that models N ink molecules diffusing in water, demonstrating how microscopic randomness leads to deterministic macroscopic behavior through the Central Limit Theorem, with relative fluctuations scaling as **1/√N**.

### Key Demonstration

- For small systems (N ~ 10²): Distribution is noticeably spread out
- For medium systems (N ~ 10⁶): Distribution narrows significantly  
- For macroscopic systems (N ~ 10²³): Relative width σ/μ ~ 3 × 10⁻¹² → essentially deterministic

This explains **why thermodynamic systems appear deterministic** despite being fundamentally statistical!

## Quick Start (No Installation Required)

### Google Colab
Click the "Open in Colab" badge above to run the notebook instantly in your browser with zero setup.

## Local Installation

### Prerequisites
- Python 3.9 or higher (tested on 3.11 and 3.14)
- pip or conda

### Setup

```bash
# Clone the repository
git clone https://github.com/mokshjayanth/clt-thermodynamic-entropy.git
cd clt-thermodynamic-entropy

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter notebook
jupyter notebook notebooks/molecular_distribution_demo.ipynb
```

### Using Conda (Alternative)

```bash
# Create the environment from the provided specification
conda env create -f environment.yml
conda activate clt-entropy

# Launch notebook
jupyter notebook notebooks/molecular_distribution_demo.ipynb
```

## Features

### Interactive Visualizations
- **Adjustable System Size**: From 10² to 10²³ molecules (1 mole)
- **Multiple Modes**: 
  - Smooth curves (Normal PDF approximation)
  - Discrete bars (Exact Binomial PMF for N ≤ 10⁶; every discrete plot is the exact PMF)
  - Combined view with entropy overlay
- **Real-time Updates**: Interactive sliders and dropdowns
- **Statistical Analysis**: Automatic computation of key metrics

### Mathematical Rigor
- **Exact Binomial Calculations**: Uses logarithmic methods for numerical stability
- **Central Limit Theorem**: Demonstrates convergence to normal distribution
- **Entropy Calculations**: Shows connection to thermodynamic entropy
- **Scaling Laws**: Visualizes the 1/√N scaling of relative fluctuations

## Educational Content

The notebook includes:
- Step-by-step mathematical derivations
- Interactive exercises and experiments
- Technical implementation notes
- Connections to thermodynamic principles
- Visualization best practices for scientific computing

## Use Cases

### For Students
- Visualize the Central Limit Theorem in action
- Understand the statistical basis of thermodynamics
- Explore how microscopic randomness yields macroscopic determinism

### For Educators
- Ready-to-use teaching demonstration
- Interactive exercises for classroom or self-study
- Publication-quality visualizations

### For Researchers
- Reproducible computational framework
- Extensible code for related problems
- Reference implementation of exact vs. approximate methods

## Scientific Background

This work demonstrates that:

1. **Binomial Statistics**: Each of N molecules independently chooses left or right half
2. **CLT Application**: For large N, distribution becomes normal with μ = N/2, σ = √(N/4)
3. **Relative Width**: σ/μ = 1/√N → vanishes for macroscopic systems
4. **Entropy Connection**: Most probable state (50/50) = maximum entropy state

### Key Result

For N = 10²³ (one mole), the relative width is σ/μ ≈ 3.16 × 10⁻¹² (that is, ~3 × 10⁻¹⁰ percent), making deviations from uniform distribution essentially unobservable. This explains the apparent determinism of macroscopic thermodynamics!

## Repository Structure

```
clt-thermodynamic-entropy/
├── README.md                              # This file
├── LICENSE                                # MIT License
├── CITATION.cff                           # Software citation metadata
├── requirements.txt                       # Python dependencies (pip)
├── environment.yml                        # Conda environment specification
├── notebooks/
│   └── molecular_distribution_demo.ipynb  # Main interactive notebook
└── .gitignore                             # Git ignore rules
```

## Example Visualizations

The notebook generates:
- Interactive probability distribution plots
- Statistical summary cards
- Entropy curves
- Scaling law demonstrations
- Convergence analyses

All visualizations use Plotly for publication-quality interactive graphics.

## Technical Details

### Computational Methods
- **Exact Binomial**: Computed for N ≤ 10⁶ using log-space arithmetic
- **Normal Approximation**: Applied for N > 10⁶ to avoid overflow
- **Log-Gamma Factorials**: `scipy.special.gammaln` gives machine-precision log(n!) at every N
  (the Stirling series is derived in the notebook for insight, but is not used for the plotted values,
  since dropping its 1/(12n) term inflates the total probability by ~0.25% at N = 10²)

### Performance
- Optimized for real-time interactivity
- Handles systems up to N = 10²³ (Avogadro scale)
- Automatic method selection based on system size

## Citation

This code accompanies the preprint:

**"Understanding Thermodynamic Entropy Through the Central Limit Theorem: A Pedagogical Framework"**

If you use this code in your research or teaching, please cite:

```bibtex
@misc{GR2026thermodynamic,
  author    = {Moksh Jayanth GR},
  title     = {Understanding Thermodynamic Entropy Through the Central Limit Theorem: A Pedagogical Framework},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.22967985},
  url       = {https://doi.org/10.5281/zenodo.22967985},
  note      = {Preprint}
}
```

> **Status:** Preprint, deposited on Zenodo — [10.5281/zenodo.22967985](https://doi.org/10.5281/zenodo.22967985).
> Not peer reviewed. This entry will be updated if and when the manuscript is
> published in a journal.

## Contributing

Contributions are welcome! Please feel free to:
- Report bugs or issues
- Suggest enhancements
- Submit pull requests
- Share how you're using this in teaching or research

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Note**: This is a pedagogical demonstration. For production thermodynamic simulations, consider specialized packages like LAMMPS, GROMACS, or ASE.

---
