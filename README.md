# Single-Cell Transcriptomic Profiling: Identifying Immune Subpopulations and Potential Drug Targets

## 📌 Project Overview
This repository contains a comprehensive single-cell RNA sequencing (scRNA-seq) analysis pipeline developed in Python. The primary objective is to identify distinct immune cell subpopulations and explore potential therapeutic targets through the lens of a clinical pharmacist. 

This foundational pipeline demonstrates my methodological readiness for advanced multi-omics integration projects, particularly focusing on complex immune-mediated diseases such as ARDS and Sepsis.

## 🛠️ Methods & Workflow
The analysis was conducted using the `Scanpy` library in Python, strictly following standard bioinformatics workflows:
* **Data Quality Control (QC):** Filtered out low-quality cells (high mitochondrial gene expression > 5%) and potential doublets.
* **Normalization & Dimensionality Reduction:** Log-normalized the data, extracted highly variable genes, and applied PCA and UMAP.
* **Clustering & Annotation:** Grouped cells using the Leiden algorithm (resolution=0.5) and identified marker genes using the Wilcoxon rank-sum test. Successfully annotated key immune clusters (e.g., CD4+ T cells, B cells, Macrophages) based on specific gene expression profiles.

## 📊 Results
* Filtered the dataset to a robust subset of **2,638 high-quality cells** and **13,656 genes**.
* Identified 6 distinct cell clusters.
* Extracted the top marker genes for each cluster (e.g., *CST3* for Macrophages, *MS4A1* for B cells, *IL7R* for T cells).

## 💊 Pharmacist's Perspective (Translational Insights)
As a clinical hospital pharmacist with experience in chemoinformatics, I aim to bridge the gap between computational data and clinical application (Drug Repositioning). 
For instance, Cluster 2 demonstrated significantly high expression of *MS4A1* (CD20). If such specific B-cell endotypes are identified as drivers in severe ARDS or Sepsis pathology, it provides a data-driven rationale for exploring existing targeted therapies, such as **Rituximab (anti-CD20 monoclonal antibody)**, for precision medicine.

## 🚀 Future Directions: Multi-Omics Integration
While scRNA-seq provides critical transcriptomic insights, true endotype resolution requires a multi-modal approach. My immediate next step is to implement multi-omics integration (e.g., combining scRNA-seq with surface protein data like CITE-seq using `muon` or `MOFA+`) to uncover hidden immune states that cannot be captured by a single omics layer.
