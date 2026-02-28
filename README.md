
# F-GWAS-and-AD

**Latent microbiome factor GWAS construction using GenomicSEM and downstream Alzheimer’s disease (AD) integrative analyses**

---

## 🔬 Overview

This repository contains the full computational pipeline for constructing latent gut microbiome genetic factors using GenomicSEM and integrating them with Alzheimer’s disease (AD) genomics and single-cell transcriptomic analyses.

The workflow includes:

* Microbiome GWAS formatting and quality control
* Univariate and multivariate LDSC
* GenomicSEM latent factor GWAS construction
* MiXeR genetic overlap analysis
* condFDR / conjFDR pleiotropy analyses
* PLACO+ pleiotropy testing
* COLOC colocalization
* TWAS integration
* Single-cell integration (scPagwas, gsMap)
* Virtual gene perturbation (scTenifoldKnk)
* Downstream pathway analyses

---

# 📦 Data Availability

Derived data generated in this study are publicly available via Zenodo:

**Concept DOI (recommended for citation):**
[https://doi.org/10.5281/zenodo.18809619](https://doi.org/10.5281/zenodo.18809619)

**Version v1:**
[https://doi.org/10.5281/zenodo.18809620](https://doi.org/10.5281/zenodo.18809620)

Zenodo repository includes:

* F1.txt – GWAS summary statistics for latent factor F1
* F2.txt – GWAS summary statistics for latent factor F2
* F3.txt – GWAS summary statistics for latent factor F3
* F4.txt – GWAS summary statistics for latent factor F4
* MSSM_AD_20k.rds – Downsampled single-cell dataset
* MSSM_L6_final.rds – L6 neuron subset
* MSSM_OPC_final.rds – OPC subset
* MSSM_pvalb_final.rds – PVALB interneuron subset
* MSSM_SST_final.rds – SST interneuron subset

Original GWAS summary statistics (MiBioGen, AD GWAS, FINRISK) were obtained from their respective public consortia and are not redistributed here.

---

# 🗂 Repository Structure

```
01. format_mibiogen_gwas
02. was_qc_and_allele_alignment
03. ldsc_microbiome_vs_AD
04. LatentMicrobiome_GWAS_GenomicSEM
05. MIXER
06. conjFDR
07. PLACO+
08. COLOC
09. TWAS
10. MSSM for scpagwas
11. scpagwas
12. gsmap
13. MSSM for KNK
14. scTenifoldKnk
15. pathways after KNK
```

---

## 🔹 01. format_mibiogen_gwas

Standardization of MiBioGen GWAS summary statistics into unified format:
SNP, CHR, BP, A1, A2, BETA, SE, P, N

---

## 🔹 02. was_qc_and_allele_alignment

Allele harmonization with 1000G reference panel and QC filtering:

* ATCG filter
* MAF ≥ 0.01
* MHC exclusion
* Duplicate SNP removal

---

## 🔹 03. ldsc_microbiome_vs_AD

Univariate LDSC analysis to estimate:

* SNP-heritability
* Genetic covariance
* Genetic correlation between microbiome traits and AD

---

## 🔹 04. LatentMicrobiome_GWAS_GenomicSEM

Core GenomicSEM workflow:

* Multivariate LDSC
* Exploratory Factor Analysis (EFA)
* Confirmatory Factor Analysis (CFA)
* Genome-wide factor GWAS construction

This step produces F1–F4 GWAS summary statistics.

---

## 🔹 05. MIXER

MiXeR analysis to quantify genome-wide polygenic overlap between:

* Latent microbiome factors
* AD
* FINRISK species-level traits

---

## 🔹 06. conjFDR

Conditional and conjunctional FDR analyses to detect shared loci between microbiome factors and AD.

---

## 🔹 07. PLACO+

Pleiotropic analysis using PLACO+ framework.

---

## 🔹 08. COLOC

Colocalization analysis of shared loci using COLOC.

---

## 🔹 09. TWAS

Transcriptome-wide association analysis integrating brain eQTL datasets.

---

## 🔹 10. MSSM for scpagwas

Processing of MSSM single-nucleus RNA-seq dataset for scPagwas integration.

---

## 🔹 11. scpagwas

Integration of microbiome factor GWAS signals with single-cell transcriptomic profiles.

---

## 🔹 12. gsmap

Genetically informed spatial mapping of cells for complex traits (gsMap).

---

## 🔹 13. MSSM for KNK

Preparation of cell-type-specific datasets for virtual gene perturbation.

---

## 🔹 14. scTenifoldKnk

Virtual gene knockout analysis to identify downstream regulatory convergence.

---

## 🔹 15. pathways after KNK

Pathway enrichment and functional convergence analysis following virtual perturbation.

---

# ⚙ Software Requirements

* R (≥ 4.2)
* GenomicSEM
* LDSC
* MiXeR
* MATLAB (for pleioFDR)
* Seurat
* Scanpy
* scPagwas
* scTenifoldKnk

Detailed package versions are provided within each script.

---



