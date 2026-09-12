# Online Retail Customer Analytics

Machine learning and data-mining project for customer segmentation and segment-specific product association analysis using the UCI Online Retail dataset.

## Project Information

- Module: IT3091 - Machine Learning
- Institution: Sri Lanka Institute of Information Technology
- Group: 2026-DS-10
- Track: Guided Data Track
- Domain: Retail and E-commerce
- Primary Lens: Customer Segmentation
- Secondary Lens: Product Association and Bundling

## Business Problem

A UK-based online retailer wants to improve customer retention, marketing effectiveness, and product strategy using historical transaction data.

The project supports the following business decision:

> Which customer groups should receive loyalty, retention, reactivation, and cross-selling strategies, and which product combinations should be promoted within suitable customer segments?

## Project Objectives

1. Understand and assess the quality of the Online Retail transaction data.
2. Prepare valid customer and transaction-level datasets.
3. Engineer customer purchasing-behaviour features using RFM analysis.
4. Establish an RFM scoring baseline.
5. Compare multiple clustering methods.
6. identify interpretable customer segments.
7. Generate segment-specific product association rules.
8. Provide evidence-based business recommendations.
9. Document limitations, risks, decisions, and reproducibility information.

## Dataset

- Dataset: Online Retail
- Provider: UCI Machine Learning Repository
- Dataset page: https://archive.ics.uci.edu/dataset/352/online+retail
- DOI: https://doi.org/10.24432/C5BW33
- File: `Online_Retail.xlsx`
- Instances: 541,909 transaction rows
- Period: 01 December 2010 to 09 December 2011
- License: Creative Commons Attribution 4.0 International

Citation:

> Chen, D. (2015). Online Retail [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

The raw dataset is not stored in the GitHub repository. Each group member must download the file from the UCI dataset page, rename it to `Online_Retail.xlsx`, and place it inside:

```text
data/raw/Online_Retail.xlsx

```

## Units of Analysis

- Customer segmentation: One row represents one identified customer.
- Association-rule mining: One basket represents one valid purchase invoice.
- Segment-specific association mining: Each valid invoice is connected to its customer's final segment.

## Planned Methods

### Baseline

- RFM quantile scoring

### Clustering Alternatives

- K-Means clustering
- Agglomerative hierarchical clustering
- DBSCAN
- Gaussian Mixture Model, if justified by the analysis

### Association-Rule Mining

- Apriori
- FP-Growth, if computationally feasible
- Support, confidence, and lift evaluation

## Evaluation Strategy

The clustering methods will be compared using:

- Silhouette score
- Davies-Bouldin index
- Calinski-Harabasz score
- Cluster-size balance
- Stability under repeated runs or subsampling
- Sensitivity to preprocessing decisions
- Business interpretability

The final method will not be selected using a single metric. Statistical quality, stability, usable cluster sizes, and business meaning will be considered together.

## Team Members and Responsibilities

| Student ID | Name | Core Responsibility |
|---|---|---|
| IT24103380 | Nirmani K.H.D.T. | Data integration and feature engineering |
| IT24102621 | Lakshitha Dilshan J.K.P. | Data understanding, preprocessing, and quality assurance |
| IT24103655 | Palliyaguruge C.T. | Clustering implementation and method comparison |
| IT24103526 | Senaratne P.A.R.T. | Association-rule mining, evaluation, and recommendations |

All members will participate in problem framing, decision logging, peer review, final-report integration, reproducibility checking, and the demonstration video.

## Repository Structure

```text
online-retail-customer-analytics/
├── data/
│   ├── raw/               # Original dataset - not tracked by Git
│   └── processed/         # Generated cleaned and feature datasets
├── notebooks/             # Executable analysis notebooks
├── src/                   # Reusable Python functions
├── outputs/
│   ├── figures/           # Generated visualisations
│   └── tables/            # Generated result tables
├── documentation/         # Data dictionary and supporting logs
├── report/                # Draft and final report
├── video/                 # Demo plan and supporting material
├── decision_log.csv       # Evidence-based project decisions
├── requirements.txt       # Python dependencies
└── README.md
```

## Planned Notebook Order

```text
01_data_understanding_eda.ipynb
02_preprocessing.ipynb
03_feature_engineering.ipynb
04_clustering_comparison.ipynb
05_association_rules.ipynb
06_evaluation_recommendations.ipynb
```

The notebooks must be executed in this order.

## Reproducibility

- The original dataset must not be overwritten.
- Dataset source and fingerprint will be documented.
- A fixed random seed of `42` will be used where applicable.
- Important analytical decisions will be recorded in `decision_log.csv`.
- Python package versions will be frozen after the environment is tested.
- Notebook outputs must agree with the final report.
- AI assistance will be declared transparently in the final submission.