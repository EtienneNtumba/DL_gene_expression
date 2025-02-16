# README.md

# Single-Cell RNA-seq Analysis Pipeline

## Overview
This pipeline provides a **complete scRNA-seq analysis workflow** using **Scanpy (Python)** and **Seurat (R)**. It processes raw 10X Genomics or count matrix data, performs quality control, normalization, clustering, and differential expression analysis.

## Features
- **Preprocessing:** Quality control and filtering
- **Normalization & Scaling:** Log transformation & feature selection
- **Dimensionality Reduction:** PCA & UMAP
- **Clustering:** Cell type identification using Leiden algorithm
- **Differential Expression Analysis:** Identification of marker genes
- **Visualization:** UMAP plots, cluster heatmaps, and DEG analysis

## Installation
### **1️⃣ Python Dependencies**
```bash
pip install scanpy pandas numpy seaborn matplotlib anndata scipy scikit-learn pyyaml
```

### **2️⃣ R Dependencies (for Seurat)**
```r
install.packages(c("Seurat", "ggplot2"))
```

## Usage
### **1️⃣ Running the Scanpy Pipeline (Python)**
```bash
python main.py
```

### **2️⃣ Running the Seurat Pipeline (R)**
```r
source("seurat_analysis.R")
```

## Expected Outputs
- `processed_data.h5ad` → Processed AnnData object.
- `figures/umap_clusters.png` → Cluster visualization.
- `figures/DEGs.png` → Differentially expressed genes plot.
- `results/marker_genes.csv` → Identified marker genes for clusters.

## Configuration
Modify `config.yaml` for parameter customization:
```yaml
data:
  dataset_path: "data/sample_10x/"
qc:
  min_cells: 3
  min_genes: 200
preprocessing:
  normalization: "log1p"
dim_reduction:
  n_pcs: 30
clustering:
  resolution: 0.5
output:
  save_dir: "results/"
```

## Contributing
Feel free to submit a **pull request** or open an **issue** for improvements!

## License
This project is licensed under the **MIT License**.

---

# config.yaml
```yaml
data:
  dataset_path: "data/sample_10x/"
qc:
  min_cells: 3
  min_genes: 200
preprocessing:
  normalization: "log1p"
dim_reduction:
  n_pcs: 30
clustering:
  resolution: 0.5
output:
  save_dir: "results/"
```
# DL_gene_expression
