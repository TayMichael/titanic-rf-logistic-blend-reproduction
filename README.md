# Titanic RF + Target-Logistic Blend Reproduction

Reproducible, explained notebook for the NTU DSAI Titanic Kaggle class competition submission that achieved a **public ROC-AUC of 0.78694**.

## What this repo reproduces

The final prediction is a **50/50 probability blend** of:

1. Random Forest
2. Target-encoded Logistic Regression

The notebook recreates the feature engineering, trains both models, averages their survival probabilities, writes the Kaggle submission CSV, and compares the regenerated probabilities against the exact submitted reference file.

## Run in VS Code

```bash
git clone https://github.com/TayMichael/titanic-rf-logistic-blend-reproduction.git
cd titanic-rf-logistic-blend-reproduction
python -m venv .venv
```

Activate the virtual environment, then install dependencies:

```bash
pip install -r requirements.txt
```

Open:

`Titanic_RF_Logistic_Blend_Reproduction.ipynb`

Select the `.venv` Python kernel and click **Run All**.

## Data

The repo does not duplicate the standard Titanic source CSVs. On first execution the notebook automatically downloads the exact byte-identical `train.csv`, `test.csv`, and `gender_submission.csv` from a public GitHub mirror and verifies their SHA-256 hashes before modelling. If any input differs, the notebook stops.

## Key files

- `Titanic_RF_Logistic_Blend_Reproduction.ipynb` — complete explained reproduction
- `reference/final_rf_target_probability_blend_candidate.csv` — exact submitted reference predictions
- `requirements.txt` — Python dependencies
- `VERIFICATION.md` — reproduction evidence

The generated submission is written to:

`output/final_rf_target_probability_blend_candidate.csv`

## Original modelling results

- Repeated 5-fold × 3 Random Forest ROC-AUC: **0.879195**
- Repeated 5-fold × 3 target-logistic ROC-AUC: **0.882810**
- Repeated 5-fold × 3 50/50 blend ROC-AUC: **0.890222**
- Kaggle public ROC-AUC: **0.78694**

## Validation caveat

Later diagnostics showed that ordinary stratified cross-validation was optimistic because related passengers could cross folds. Group-aware validation was therefore used as a robustness check. The notebook preserves the actual submitted modelling route and explains this limitation rather than hiding it.
