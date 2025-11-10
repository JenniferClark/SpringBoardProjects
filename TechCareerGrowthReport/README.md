# Tech Career Growth & Recommendation Forecaster

## How to Run
1. Place `data/raw/bls_occupation.xlsx` (BLS Table 1.x workbook).
2. Open **Capstone_Final_Report.ipynb** and run sections 00 → 07 in order.
3. Artifacts are written to `outputs/`:
    - `curated_modeling_table.csv`, `train_df.csv`, `test_df.csv`
    - `feature_cols.csv`, `feature_cols_numeric.csv`, `feature_cols_categorical.csv`
    - `Model_Metrics.csv`, `Model_Metrics.txt`, `Model_Metrics.json`

## Contents
- `Capstone_Final_Report.ipynb` — final, self-contained notebook (code + report).
- `data/raw/` — raw inputs (not versioned in repo if large).
- `outputs/` — generated artifacts (metrics, splits, features).
