![image](https://github.com/user-attachments/assets/7f226b55-0a55-4c57-9ce6-802a8bd29a3e)

# GkRNN — Continuity-Aware Multivariate Domaining of Geochemical Drillhole Data

**Author:** Keyumars Anvari  
**Supervisor:** Professor Jörg Benndorf  
**Affiliation:** Department of Mine Surveying and Geodesy, TU Bergakademie Freiberg, Germany

---

## 📄 Project Description

This repository contains a compact, method-only implementation of **GkRNN**, a hybrid geostatistical–AI workflow for generating continuity-aware, depth-ordered geological domains from multivariate geochemical drillhole data. The approach mirrors **Figure 4** and **Algorithm 1** of the published workflow and is designed for transparent scientific reproducibility.

The script assumes that irregular assays have already been **composited** into fixed depth intervals and **CLR-transformed**. From there, the workflow:

- captures **joint spatial continuity** using kernel variogram matrices,
- embeds samples into a **low-dimensional spectral space**,
- selects an **optimal number of clusters**,
- enforces geological depth ordering using a **Markov–HMM structure**,
- refines sequences with an **LSTM model**, and
- applies geological **post-processing** (minimum thickness, max units per hole).

This produces coherent, stratigraphically consistent domains that reflect both geochemical relationships and spatial structure.

---

## 🔗 Citation

If you use this script, please cite:

**Anvari, K. & Benndorf, J. (2024)**  
*Automated 3D Multivariate Domaining of a Mine Tailings Deposit Using a Continuity-Aware Geostatistical–AI Workflow*,  
Minerals 15(12), 1249.  
https://www.mdpi.com/2075-163X/15/12/1249

---

## 🛠️ Features

- **Joint Spatial Continuity:** Kernelized direct and cross variogram matrices with PSD correction  
- **Spectral Embedding:** Continuity-aware low-dimensional representation of samples  
- **Elbow-Based Clustering:** Automatic k-selection in spectral space  
- **Depthwise Stratigraphic Ordering:** Re-labeling clusters by median depth  
- **Markov–HMM Smoothing:** Enforces geologically plausible transitions  
- **LSTM Refinement:** Sliding-window sequence learning with Markov-consistency  
- **Geological Post-Processing:** Minimum thickness merge + maximum units per borehole  
- **Clean Configuration:** All settings controlled via a single dataclass  
- **Data-Agnostic:** No dataset included, no hardcoded variable names  

---

## 🗺️ Workflow Overview

1. Load composited + CLR-transformed drillhole data  
2. Build short-range spatial pairs  
3. Estimate kernelized variogram matrices across lag distances  
4. Construct continuity-based similarity + spatial proximity similarity  
5. Form the joint affinity matrix  
6. Compute spectral embedding of the normalized graph Laplacian  
7. Select optimal k using elbow analysis  
8. Perform k-means clustering in spectral space  
9. Reorder clusters by median depth (stratigraphic ordering)  
10. Apply HMM smoothing using a constrained Markov transition model  
11. Build sliding-window sequences and train the LSTM  
12. Apply LSTM refinement with majority voting  
13. Enforce minimum thickness and max units per borehole  
14. Export final domaining results and transition matrix  

---

## 📚 Dependencies

Install requirements:

```bash
pip install -r requirements.txt

```

**Main libraries used:**
- `pandas`
- `numpy`
- 'scipy'
- `matplotlib`
- 'scikit-learn'
- 'tensorflow'

---

## 🚀 How to Run

1. Clone the repository or download the files.
2. Prepare a CSV file containing:
   - borehole ID
   - X, Y, Z coordinates
   - CLR-transformed geochemical variables
3. Edit configuration inside the script:
 ```bash
CFG.data_csv = "your_input.csv"
CFG.GEOCHEM_COLUMNS = ("clr1", "clr2", ...)
```
4. Run.

---

## 📈 Example Outputs

- k-means cluster labels
- Depth-ordered labels
- HMM-smoothed zones
- LSTM-refined sequences
- Final geological domains after post-processing

---

## ⚠️ Notes

- Compositing + CLR transformation must be done before using this script
- Fully method-oriented implementation (no dataset included)
- Suitable for reproducible research and educational demonstrations


---

## 📬 Contact

For any questions, suggestions, or collaboration interests:

> Keyumars Anvari  
> Department of Mine Surveying and Geodesy, TU Bergakademie Freiberg  
> Email:
keyumarsanvari@gmail.com
Kayumars.Anvari@doktorand.tu-freiberg.de

---
