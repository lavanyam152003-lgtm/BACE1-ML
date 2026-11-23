# ML-based virtual screening of BACE1 inhibitors

Notebooks and data for the manuscript "An integrative AI/ML based virtual screening approach for identification of BACE1 inhibitors in Alzheimer's disease through docking and molecular dynamics simulation".

The workflow: BACE1 bioactivity data from ChEMBL v33 were curated and labelled (active: pChEMBL ≥ 5.5), converted to descriptors and fingerprints, and used to train a Random Forest classifier. The trained model ranked an external library of 13,249 compounds, and the 20 top-ranked hits (B1–B20) were taken forward to GNINA docking and molecular dynamics.

## Notebooks

| File | Content |
|---|---|
| `molecular_descriptors.ipynb` | Calculates the six physicochemical descriptors (MolWt, LogP, NumHDonors, NumHAcceptors, TPSA, RotatableBonds) with RDKit |
| `fingerprints.ipynb` | Generates Morgan, MACCS, RDKit path and atom-pair fingerprints with RDKit and merges them with the descriptors into one feature table |
| `bsbioact - Copy - Copy - Copy.ipynb` | [CHECK: model building, e.g. preprocessing, SMOTE, classifier comparison, RFECV, Optuna tuning, screening of the external library] |
| `assignment.ipynb` | [CHECK: describe, or delete if not part of this study] |

## Training data

| File | Content |
|---|---|
| `Canonical_smiles.output.csv` | Curated ChEMBL BACE1 dataset: canonical SMILES, pChEMBL value, and activity label (18,633 compounds) |
| `smiles.csv` | [CHECK: describe] |
| `Descriptors_final.csv` | The six RDKit descriptors for each training compound, together with the SMILES, pChEMBL value and activity label |
| `bsbioactivity_prediction_data1.csv` | [CHECK: full feature table (descriptors and fingerprints) used for model training] |

## Screening of the external library

| File | Content |
|---|---|
| `external_data_bs.rar` | [CHECK: external compound library (13,249 compounds) and its features] |
| `ML_screened_compounds_bsp.rar` | [CHECK: model predictions for the external library] |
| `Top20_HitsBS.csv` | The 20 top-ranked compounds (B1–B20) taken forward to docking |
| `Top50_HitsBS.csv`, `Top100_HitsBS.csv`, `Top200_HitsBS.csv` | Larger top-ranked lists from the same ranking |

## Software

Python, RDKit, pandas, scikit-learn. [CHECK: add versions and any other packages used, e.g. imbalanced-learn, Optuna, XGBoost.] Docking was done with GNINA v1.0.1 and molecular dynamics with Desmond (Schrödinger); those input and output files are not part of this repository unless listed above.

## Citation

[Add the full reference of the paper once it is accepted.]

## Contact

[Name and email of the corresponding author]
