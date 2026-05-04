# Bio-Inspired Multi-Objective Batch Active Learning for Skin Lesion Classification

[![DOI](https://img.shields.io/badge/DOI-10.1145/3795101.3814666-blue.svg)](https://doi.org/10.1145/3795101.3814666)
[![Conference](https://img.shields.io/badge/Conference-GECCO_Companion_'26-success.svg)](https://gecco-2026.sigevo.org/)

This repository contains the code for the paper **"Bio-Inspired Multi-Objective Batch Active Learning for Skin Lesion Classification"**, presented at the Genetic and Evolutionary Computation Conference (GECCO Companion '26), San Jose, Costa Rica.

## 📖 Overview

Deep learning models for medical image classification achieve high accuracy but rely on large, costly labeled datasets. Active Learning (AL) mitigates this by iteratively selecting informative samples under a fixed labeling budget. However, standard batch-mode AL often struggles with redundancy when relying solely on scalar uncertainty scores.

This work formulates batch-mode AL for skin lesion classification as a **Multi-Objective Optimization (MOO)** problem, explicitly balancing:
* **Informativeness** (predictive entropy)
* **Coverage** (distance to the labeled set)
* **Diversity** (density-based representativeness)

We employ bio-inspired optimizers, **NSGA-II** with set-based encoding and **MOPSO** with continuous scoring vectors, to search for Pareto-optimal batches. Evaluated on the HAM10000 dataset, our MOO approaches outperform established baselines in sample efficiency, with MOPSO attaining the highest Area Under the Learning Curve (AULC).

## 🗂️ Repository Structure

* `main.ipynb`: The core Jupyter Notebook containing the full pipeline for the experiments, including the data loading (HAM10000), model training (freeze-unfreeze protocol), and the implementation of the baseline and bio-inspired Active Learning strategies (NSGA-II, MOPSO, BADGE, k-centers, etc.).

## 🚀 Getting Started

### Prerequisites
To run the code in `main.ipynb`, you will need a standard deep learning environment. We recommend installing the following core dependencies:
* Python 3.8+
* PyTorch
* Torchvision
* NumPy, Pandas, Scikit-learn
* Matplotlib (for Pareto front visualizations)

### Running the Code
1. Clone this repository to your local machine.
2. Download the [HAM10000 Dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T) and update the data paths in the notebook accordingly.
3. Open `main.ipynb` in Jupyter Notebook or JupyterLab.
4. Run the cells sequentially to initialize the models, define the acquisition functions, and execute the Active Learning loops.

## 👥 Authors
* Nancy Kalaj, University of Trento, Italy
* Matteo Bando, University of Trento, Italy
* Šimon Rokůsek, University of Trento, Italy
* Ludovico Cappellato, University of Trento, Italy
* Erik Nielsen, University of Trento, Italy
* Stefano Genetti, University of Trento, Italy
* Giovanni Iacca, University of Trento, Italy

## 📝 Citation

If you use this code or find our work helpful in your research, please cite our paper:

```bibtex
@inproceedings{kalaj2026bio,
  author = {Kalaj, Nancy and Bando, Matteo and Rok\^{u}sek, \v{S}imon and Cappellato, Ludovico and Nielsen, Erik and Genetti, Stefano and Iacca, Giovanni},
  title = {Bio-Inspired Multi-Objective Batch Active Learning for Skin Lesion Classification},
  year = {2026},
  url = {[https://doi.org/10.1145/3795101.3814666](https://doi.org/10.1145/3795101.3814666)},
  doi = {10.1145/3795101.3814666},
  booktitle = {Genetic and Evolutionary Computation Conference (GECCO Companion '26)},
  location = {San Jose, Costa Rica},
  series = {GECCO '26}
}
