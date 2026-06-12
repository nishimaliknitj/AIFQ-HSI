# AIFQ-HSI

<p align="center">



![License](https://img.shields.io/badge/License-MIT-green.svg)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-red.svg)
![Status](https://img.shields.io/badge/Build-Passing-brightgreen.svg)
![Journal](https://img.shields.io/badge/Research-Hyperspectral%20AI-orange.svg)

</p>

---

## Augmentation-Induced Feature Quality Framework for Hyperspectral Land Cover Classification

Official implementation of:

**A Statistical Framework for Evaluating Augmentation-Induced Feature Quality in Deep Spectral-Spatial Networks for Pseudo-Labeled Hyperspectral Land Cover Classification**

---

## Overview

AIFQ-HSI introduces a novel statistical framework for evaluating the quality of hyperspectral image augmentation strategies before downstream classifier training.

The framework proposes:

- Spectral Fidelity Score (SFS)
- Fisher Discriminant Ratio (FDR)
- Silhouette Coefficient (SC)
- Composite AIFQ Score
- ANOVA + Tukey HSD Statistical Validation
- AIFQ-guided Pseudo-label Refinement

---

## Framework

<p align="center">
  <img src="figures/Figure1_AIFQ_Framework.png" width="900">
</p>

---

## Key Contributions

### Novel Spectral Fidelity Score (SFS)

Measures augmentation-induced distribution shifts in deep spectral-spatial feature space using KL-divergence.

### Composite AIFQ Score

Combines:

- SFS
- FDR
- Silhouette Coefficient

into a unified augmentation quality metric.

### Statistical Validation

- One-Way ANOVA
- Tukey HSD Post-hoc Testing

for rigorous augmentation comparison.

### Pseudo-Label Refinement

Uses AIFQ scores to weight pseudo-label confidence during self-supervised learning.

---

## Repository Structure

```text
AIFQ-HSI
│
├── augmentation/
├── metrics/
├── feature_extraction/
├── pseudo_labeling/
├── statistical_analysis/
├── datasets/
├── figures/
├── results/
├── scripts/
├── benchmark_master.csv
├── requirements.txt
└── README.md
```

## Supported Datasets

| Dataset | Classes | Bands |
|----------|----------|----------|
| Indian Pines | 16 | 200 |
| Pavia University | 9 | 103 |
| Salinas | 16 | 204 |
| PRISMA | 6 | 209 |

---

## Installation

```bash
git clone https://github.com/nishimaliknitj/AIFQ-HSI.git

cd AIFQ-HSI

pip install -r requirements.txt
```

---

## Run AIFQ Evaluation

```bash
python scripts/run_aifq.py
```

---

## Statistical Analysis

```bash
python statistical_analysis/anova.py

python statistical_analysis/tukey_hsd.py
```

---

## Results

| Strategy | SFS | FDR | SC | AIFQ |
|-----------|-----------|-----------|-----------|-----------|
| Jitter | 0.745 | 8.556 | -0.035 | 0.775 |
| Geometric | 0.000 | 0.200 | -0.547 | 0.000 |
| PCA | 0.583 | 0.723 | -0.329 | 0.467 |
| GAN | 0.605 | 10.857 | -0.008 | 0.715 |
| Mixup | 0.411 | 31.560 | 0.048 | 0.786 |

---

## Citation

```bibtex
@article{malik2026aifq,
  title={A Statistical Framework for Evaluating Augmentation-Induced Feature Quality in Deep Spectral-Spatial Networks for Pseudo-Labeled Hyperspectral Land Cover Classification},
  author={Malik, Rahul and Madaan, Nishi},
  year={2026}
}
```

---

## License

MIT License

---

## Contact

Rahul Malik  
Department of Computer Science  
Galgotias University, India

Email: nishimaliknitj@gmail.com
