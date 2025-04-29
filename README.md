![image](https://github.com/user-attachments/assets/7f226b55-0a55-4c57-9ce6-802a8bd29a3e)

# Automated Clustering of Geochemical Data

**Author:** Keyumars Anvari  
**Supervisor:** Professor Jörg Benndorf  
**Affiliation:** Department of Mine Surveying and Geodesy, TU Bergakademie Freiberg, Germany

---

## 📄 Project Description

This project automates the preprocessing, clustering, analysis, and visualization of geochemical data collected from boreholes.  
The goal is to identify patterns and structures within multi-element geochemical datasets using geostatistics and machine learning techniques and to prepare the data for sequential modeling through a Recurrent Neural Network (RNN).

The workflow integrates:
- Optimal cluster determination
- Joint spatial continuity analysis
- Dimensionality reduction
- Sequence generation for RNN models
- 2D and 3D data visualization

The results provide insights into the hidden spatial structures of geochemical properties, helping researchers better understand subsurface variability.

---

## 🛠️ Features

- **Data Preprocessing:** Cleaning and structuring geochemical data from boreholes.
- **Pairwise Visualization:** Generating pair plots to explore variable relationships.
- **Optimal Clustering:** Automatically finding the best number of clusters using a customized elbow method (`autoelbow_rupakbob`).
- **Spatial Continuity Analysis:** Evaluating joint spatial continuity based on Kernel Density Estimation (KDE) techniques.
- **3D Geostatistical Visualization:** Visualizing borehole data and clusters in 3D space.
- **RNN Sequence Preparation:** Generating input sequences for training deep learning models.
- **Deep Learning (RNN):** Building and training a multi-layer SimpleRNN model to predict cluster labels.
- **Performance Evaluation:** Plotting training/validation accuracy, calculating confusion matrices.
- **Comprehensive Output:** Saving combined clustering results to an Excel file for further analysis.

---

## 🗺️ Workflow Overview

1. Load and clean geochemical data.
2. Explore pairwise relationships using seaborn.
3. Calculate distance matrices.
4. Determine the optimal number of clusters for each borehole.
5. Perform KMeans clustering.
6. Analyze joint spatial continuity across samples.
7. Prepare sequences augmented with spatial distances for RNN modeling.
8. Train a deep Recurrent Neural Network (SimpleRNN layers).
9. Evaluate and visualize the results (2D plots, 3D scatter plots).
10. Save clustering outcomes into a unified Excel file.

---

## 📚 Dependencies

Make sure you have Python 3.8+ installed.

Install the required libraries with:

```bash
pip install -r requirements.txt
```

**Main libraries used:**
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `scipy`
- `tensorflow`
- `pykrige`
- `pyvista`
- `autoelbow-rupakbob` (custom)

---

## 🚀 How to Run

1. Clone the repository or download the files.
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Automated_Clustering_for_geochemical.ipynb
   ```
4. Run each cell step-by-step.

---

## 📈 Example Outputs

- **Pair Plots** of geochemical variables.
- **Elbow plots** to determine optimal clusters.
- **Clustered scatterplots** (PCA-reduced space).
- **3D geological models** colored by clusters.
- **Training and validation curves** for the RNN model.
- **Excel output** summarizing all clustering results.

---

## ⚠️ Notes

- The clustering heavily relies on correct distance calculations between samples; ensure your borehole data is properly cleaned.
- The `autoelbow_rupakbob` package may need manual installation if it's not available on standard Python repositories.
- This project uses SimpleRNN layers, which are best suited for small to medium-sized datasets. For larger datasets, LSTM or GRU could be considered.
- Visualization performance might be slower for very large datasets (e.g., > 10,000 points).


---

## 📬 Contact

For any questions, suggestions, or collaboration interests:

> Keyumars Anvari  
> Department of Mine Surveying and Geodesy, TU Bergakademie Freiberg  
> Email: keyumarsanvari@gmail.com

---
