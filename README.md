# Comparative Cryo-EM 3D Protein Structure Prediction Benchmark (2026 release targets)

This repository provides a standardized evaluation suite comparing sequence-free 3D structure prediction algorithms against novel 2026 Electron Microscopy structural targets.

## Repository Structure
- **`src/`**: Cloned algorithm implementations and utility modules (MICA, EMProt, EModelX, ModelAngelo, etc.).
- **`results/`**: Consolidated scientific benchmark outputs, statistical tests, and analytical plots.
- **`docs/`**: Supporting markdown documentation, parameter specifications, and execution instructions.

## Methods Evaluated
1. **MICA** (Sequence-free framework)
2. **EMProt**
3. **EModelX**
4. **ModelAngelo**
5. **CryoAtom**
6. **CryoZeta**

## Benchmark Performance Figures
Refer to the `results/` folder for:
- **`Fig1_Average_Performance_BarChart.png`**: Multi-panel comparisons across overall metric performance.
- **`Fig3_Protein_Length_Regression.png`**: TM-score relative to target sequence lengths.
- **`Fig4_Map_Resolution_Regression.png`**: Modeling fidelity relative to target Map resolutions (Å).
