# titanic-rf-logistic-blend-reproduction

Self-contained reproduction of one submission from the NTU DSAI Titanic Kaggle class competition.

- Public Kaggle ROC-AUC reported for this submission: **0.78694**
- Main file: `Titanic_RF_Logistic_Blend_Reproduction.ipynb`
- Run mode: open in VS Code and choose **Run All**

## Quick start

```bash
git clone https://github.com/TayMichael/titanic-rf-logistic-blend-reproduction.git
cd titanic-rf-logistic-blend-reproduction
python -m venv .venv
```

Activate the virtual environment, then:

```bash
pip install -r requirements.txt
```

Open the `.ipynb` notebook in VS Code, select the `.venv` Python kernel, and click **Run All**.

The notebook creates a CSV in `output/` and compares it against the exact submitted reference in `reference/`.

## Files

- `data/train.csv` — labelled Titanic training data
- `data/test.csv` — Kaggle test passengers
- `data/gender_submission.csv` — required submission shape/IDs
- `reference/final_rf_target_probability_blend_candidate.csv` — exact original submitted file
- `Titanic_RF_Logistic_Blend_Reproduction.ipynb` — complete explained reproduction

## Important validation note

The notebook reproduces the original modelling pipeline. Later diagnostics showed that ordinary stratified cross-validation was optimistic because related passengers could cross folds. Group-aware validation was therefore used as a robustness check after the original submission.
