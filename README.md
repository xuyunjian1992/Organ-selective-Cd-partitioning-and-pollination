# Elemental-defence-and-pollinator-exposure

Data and code accompanying the manuscript:

**Organ-selective cadmium partitioning reconciles elemental defense with pollination in an invasive plant**

Yunjian Xu^1,2,#^, Yaqi Li^1,2,3,#^, Shan Wu^1,2,#^, Demei Hu^1,2^, Yulin Li^1,2,4^, Yi Wang^1,2,\*^

^1^ State Key Laboratory of Vegetation Structure, Function and Construction (VegLab), Yunnan University, Kunming 650500, China
^2^ Yunnan Key Laboratory of Biological Adaptation, Conservation and Utilization, Institute of Biodiversity, School of Ecology and Environmental Science, Yunnan University, Kunming 650500, China
^3^ Tropical and Subtropical Cash Crops Research Institute, Yunnan Academy of Agricultural Sciences, Baoshan 678000, China
^4^ Southwest Survey and Planning Institute of National Forestry and Grassland Administration, Kunming 650031, China
^#^ These authors contributed equally. \*Correspondence: yiwang@ynu.edu.cn

---

## Overview

This repository contains the source data underlying all main and supplementary figures, and the R code used for the microbial co-occurrence network analysis. Raw 16S rRNA amplicon sequencing data have been deposited at NCBI under BioProject **PRJNA1403731**.

The study compares the invasive Cd hyperaccumulator *Phytolacca americana* with its native congener *P. acinosa* under a Cd gradient (0, 3, 15, 30 mg kg⁻¹), traces plant-derived Cd into the pollinator *Apis cerana* using ¹¹¹Cd/¹¹³Cd stable isotopes, evaluates the effect of acute Cd exposure on bee survival and gut microbiota, synthesizes evidence of metal tolerance/accumulation across 64 invasive plant species, and profiles pollen eDNA and heavy metals in wild honey samples from China.

## Repository structure

```
├── README.md
├── code/
│   └── microbial_cooccurrence_network_analysis.R   # Co-occurrence network analysis (Fig. 3C)
└── data/
    ├── Figure1/    # Reproductive traits and floral Cd accumulation (Fig. 1)
    ├── Figure2/    # Nectar sugar, bee visitation, stable Cd isotope transfer (Fig. 2)
    ├── Figure3/    # Bee survival, gut microbiota and predicted functions (Fig. 3)
    ├── Figure4/    # Literature-synthesis matrix, honey pollen eDNA, regression (Fig. 4)
    ├── FigureS1/   # Growth traits (Fig. S1)
    ├── FigureS2/   # Additional reproductive traits (Fig. S2)
    ├── FigureS3/   # Root/leaf Cd and translocation factor (Fig. S3)
    ├── FigureS4/   # Heavy metal concentrations in honey (Fig. S4)
    └── network/    # ASV tables and taxonomy used by the R script
```

## Data files

All spreadsheets contain a single sheet named `Data` with one header row. Missing values indicate samples below the detection limit or lost during processing.

### data/Figure1/

| File | Description | Columns |
|---|---|---|
| `Fig1B_nectar_Cd_concentration.xlsx` | Nectar Cd concentration (Fig. 1B) | Species; Treatment; Cd concentration (mg kg⁻¹) |
| `Fig1C_flower_bud_number.xlsx` | Number of flower buds per plant (Fig. 1C) | Species; Treatment; Flower bud number |
| `Fig1D_pollen_number.xlsx` | Pollen quantity per flower (Fig. 1D) | Species; Treatment; Pollen number |
| `Fig1E_flower_Cd_concentration.xlsx` | Flower Cd concentration (Fig. 1E) | Species; Treatment; Cd concentration (mg kg⁻¹) |
| `Fig1F_inflorescence_number.xlsx` | Number of inflorescences per plant (Fig. 1F) | Species; Treatment; Inflorescence number |
| `Fig1G_pollen_Cd_concentration.xlsx` | Pollen Cd concentration (Fig. 1G) | Species; Treatment; Cd concentration (mg kg⁻¹) |

### data/Figure2/

| File | Description | Columns |
|---|---|---|
| `Fig2B_nectar_sugar_concentration.xlsx` | Nectar sucrose concentration (Fig. 2B) | Species; Nectar sugar concentration (%) |
| `Fig2C_bee_visitation_frequency.xlsx` | *A. cerana* visitation frequency (Fig. 2C) | Species; Bee visitation frequency (visits flower⁻¹ h⁻¹) |
| `Fig2DE_stable_Cd_isotope_transfer.xlsx` | ¹¹¹Cd/¹¹³Cd signals in worker bees after 7 days of feeding on labelled pollen (Fig. 2D, E) | Plant species; Plant isotope label; 113Cd signal (µg g⁻¹); 111Cd signal (µg g⁻¹) |

### data/Figure3/

| File | Description | Columns |
|---|---|---|
| `Fig3B_bee_survival_under_Cd_exposure.xlsx` | Survival records of *A. cerana* workers orally exposed to 3 mg L⁻¹ Cd (as CdCl₂) or control (Fig. 3B) | Group; Days; Status used in survival analysis (1 = death event, 0 = censored) |
| `Fig3D_top30_genera_mean_abundance.xlsx` | Mean relative abundance of the top 30 bacterial genera in bee guts (Fig. 3D) | Genus; Control mean abundance (%); Cd-treatment mean abundance (%) |
| `Fig3E_predicted_KEGG_level2_functions.xlsx` | PICRUSt2-predicted KEGG level-2 pathway abundances per sample (Fig. 3E) | KEGG Level 2 pathway; Control1–3; Cd treatment1–3 (%) |
| `Fig3F_regressions_genera_vs_functions.xlsx` | Per-sample values used in the correlations between decreased genera and downregulated pathways (Fig. 3F) | Sample; Mean abundance of decreased genera (%); six pathway columns (%) |

### data/Figure4/

| File | Description | Columns |
|---|---|---|
| `Fig4A_invasive_plant_heavy_metal_matrix.xlsx` | Literature-synthesis evidence matrix for 64 invasive plant species × 19 metals/metalloids (Fig. 4A); codes: 0 = no evidence, 1 = tolerance, 2 = accumulation, 3 = hyperaccumulation; supporting references in Table S2 of the manuscript | Species; Al, As, B, Ba, Co, Cr, Cs, Cu, Fe, Hg, Li, Mn, Ni, Pb, Sr, U, V, Zn, Cd |
| `Fig4D_invasive_plant_relative_abundance_in_honey.xlsx` | Relative abundance (fraction of total plant reads) of 19 invasive plant taxa detected by ITS2 pollen eDNA metabarcoding in six honey samples (Fig. 4D) | Invasive plant taxon; ZJ; HNa; CQ; HeN; SC; AH |
| `Fig4E_regression_abundance_vs_metals.xlsx` | Data points used in the exploratory regression between invasive plant pollen abundance and honey heavy metal concentration (Fig. 4E); values are transformed coordinates used for plotting | Invasive plant abundance; Heavy metal concentration |

### data/FigureS1/

| File | Description | Columns |
|---|---|---|
| `FigS1A_plant_height.xlsx` | Plant height (Fig. S1A) | Species; Treatment; Plant height (cm) |
| `FigS1B_aboveground_biomass.xlsx` | Aboveground dry biomass (Fig. S1B) | Species; Treatment; Aboveground biomass (g) |
| `FigS1C_root_biomass.xlsx` | Root dry biomass (Fig. S1C) | Species; Treatment; Root biomass (g) |
| `FigS1D_total_biomass.xlsx` | Total dry biomass (Fig. S1D) | Species; Treatment; Total biomass (g) |

### data/FigureS2/

| File | Description | Columns |
|---|---|---|
| `FigS2A_pollen_viability.xlsx` | Pollen viability (Fig. S2A) | Species; Treatment; Pollen viability (proportion, 0–1) |
| `FigS2B_fruit_number.xlsx` | Fruit number per plant (Fig. S2B) | Species; Treatment; Fruit number |
| `FigS2C_seed_number.xlsx` | Seed number per plant (Fig. S2C) | Species; Treatment; Seed number |

### data/FigureS3/

| File | Description | Columns |
|---|---|---|
| `FigS3A_root_Cd_concentration.xlsx` | Root Cd concentration (Fig. S3A) | Species; Treatment; Root Cd concentration (mg kg⁻¹) |
| `FigS3B_leaf_Cd_concentration.xlsx` | Leaf Cd concentration (Fig. S3B) | Species; Treatment; Leaf Cd concentration (mg kg⁻¹) |
| `FigS3C_Cd_translocation_factor.xlsx` | Cd translocation factor, leaf-to-root concentration ratio (Fig. S3C) | Species; Treatment; Cd translocation factor |

### data/FigureS4/

| File | Description | Columns |
|---|---|---|
| `FigS4_honey_heavy_metal_concentrations.xlsx` | As, Cd, Hg and Pb concentrations in honey samples from six locations (Fig. S4); each location–metal combination has up to four analytical replicates | Metal; Location; Concentration (mg kg⁻¹) |

### data/network/

| File | Description |
|---|---|
| `CK_ASV_abundance_table.csv` | ASV absolute-abundance (read count) table for the three control gut samples (rows = ASVs, columns = CK1–CK3) |
| `Cd_ASV_abundance_table.csv` | ASV absolute-abundance (read count) table for the three Cd-treated gut samples (rows = ASVs, columns = Cd1–Cd3) |
| `ASV_phylum_taxonomy.csv` | Phylum-level taxonomy for each ASV, used for node annotation in the networks |

### Shared column definitions

- **Species**: *P. americana* (invasive) or *P. acinosa* (native congener).
- **Treatment**: CK = control (0 mg kg⁻¹ Cd); L = low (3 mg kg⁻¹); M = medium (15 mg kg⁻¹); H = high (30 mg kg⁻¹).
- **Location / honey sample codes**: ZJ = Zhejiang; HNa = Hainan; CQ = Chongqing; HeN = Henan; SC = Sichuan; AH = Anhui.

## Code

`code/microbial_cooccurrence_network_analysis.R` reproduces the gut microbial co-occurrence networks of Fig. 3C (Spearman correlations, |ρ| ≥ 0.6, P < 0.05, FDR-adjusted; fast-greedy module detection) using the [microeco](https://github.com/ChiLiubio/microeco) package.

**Usage**

```r
# R >= 4.2; packages: microeco, ggplot2, rgexf, igraph
# Run from the repository root so that relative paths resolve:
source("code/microbial_cooccurrence_network_analysis.R")
```

Outputs (network .gexf files, node/edge tables, adjacency matrices, network attributes, and .rds objects) are written to `output/`.

## Related data

- Raw 16S rRNA amplicon sequences: NCBI BioProject [PRJNA1403731](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA1403731).
- The full ASV table with complete taxonomic annotation (Table S1), the literature-synthesis reference list (Table S2), and the full honey pollen eDNA species table (Table S3) are provided as supplementary tables of the manuscript.

## License

These data are made available for academic research and verification purposes. Please cite the manuscript when reusing the data.
