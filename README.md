# Cryo-EM 3D Structural Modeling Benchmark (2026)

Welcome to the official repository containing publication-grade deliverables and benchmark results evaluating state-of-the-art *de novo* 3D structure determination pipelines directly from cryo-EM density maps.

## 🔬 Study Summary & Overview
This project evaluates six cutting-edge algorithms across 12 diverse target proteins released in **2026** (Map resolutions: 1.8 Å - 3.8 Å; Sequence sizes: 400 - 1800 residues) on overall reconstruction quality, geometric properties, and computational efficiency:
*   **MICA** (Our proposed template-free structural backbone builder)
*   **EMProt**
*   **EModelX**
*   **ModelAngelo**
*   **CryoAtom**
*   **CryoZeta**

### Key Findings
*   **Backbone Accuracy**: **MICA** demonstrated outstanding, robust structural determination, achieving a **Mean TM-score of 0.9588** and **97.72% C-alpha match rates**, closely matched with high-fidelity algorithms.
*   **Geometric Fidelity**: Calculated 3D spatial properties (Centroids, bounding box scopes, and Radii of Gyration) highlight high alignment agreement against standard crystallographic structures.

---

## 📁 Deliverables Directory Structure
*   `docs/`: Contains the sanitized executable, interactive Colab Notebook replication script (`.ipynb`).
*   `results/`:
    *   `Supplementary_Table_S1_Per_Target_Results.csv`: Complete atomic match metrics, RMSD, Sequence identities, and runtimes for all 72 evaluation pairs.
    *   `Supplementary_Table_S2_Benchmark_Summary.csv`: Aggregated model statistics sorted by reconstruction efficiency.
    *   `Fig1_Benchmark_Metrics_Summary.png`: Publication bar charts for comparative criteria.
    *   `Fig2_Pairwise_TMScore_Comparisons.png`: MICA TM-score comparison scatters.
    *   `Fig3_Resolution_and_Size_Robustness.png`: Performance stability plots vs. map resolution.
    *   `Benchmark_Results_And_3D_Models.zip`: Consolidated distribution archive containing predicted coordinate models and tabular data.

---

## 🛠️ Installation & Reproduction Guide
This suite can be reproduced easily inside a Linux virtual environment with CUDA capability.

### 1. Requirements
*   Anaconda or Miniforge Package Manager
*   GCC Compiler
*   CUDA Toolkits (Compatibility verified on CUDA 11.8 / 12.x)

### 2. Setting Up Environments
Clone this repository and create the isolated Conda environments for evaluation tools:
```bash
git clone https://github.com/adelekeadeniyan/cryo-em-benchmarking-2026.git
cd cryo-em-benchmarking-2026

# Configure EMProt
mamba env create -f ./temp/repos/EMProt/environment.yml -p ./temp/envs/emprot_env -y

# Configure MICA
mamba create -y -p ./temp/envs/mica_env python=3.10 numpy biopython scipy tqdm open3d
conda run -p ./temp/envs/mica_env pip install superpose3d mrcfile pandas einops
```

### 3. Compilation of Structural Aligners
Compile USalign to compute TM-scores and structure similarity indexes:
```bash
g++ -O3 -o ./temp/bin/USalign USalign.cpp
chmod +x ./temp/bin/USalign
```

---

## 📝 Citation & Research Context
Developed at **Cheng Laboratory, University of Missouri**. Benchmark pipeline orchestrated in accordance with Nature / Communications Chemistry publication criteria (2026).
