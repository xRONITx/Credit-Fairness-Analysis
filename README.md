# CSET485 – AI and Society  
## Self-Learning Assignment #1 (Parts 1 & 2)

| Field | Value |
|-------|-------|
| Roll Number | 0035 |
| Dataset | German Credit Data (UCI Statlog) |
| Random Seed | 35 |
| Train / Test Split | 70 % / 30 % |

---

## Dataset

**German Credit Data** from the UCI Machine Learning Repository.

- URL: https://archive.ics.uci.edu/ml/machine-learning-databases/statlog/german/german.data
- Format: space-separated, no header, 20 attributes + class label
- 1000 rows: 700 good credit (approve), 300 bad credit (reject)

The notebook tries to load the dataset from the URL automatically.  
If the URL is unreachable, place `german.data` in the same folder as the notebook — the fallback path will be used automatically.

---

## How to Run

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

2. Open and run the notebook (Restart and Run All in Jupyter):
   ```bash
   jupyter notebook CSET485_Assignment1_0035.ipynb
   ```

   Or execute from the command line:
   ```bash
   python -m nbconvert --to notebook --execute --ExecutePreprocessor.timeout=400 CSET485_Assignment1_0035.ipynb --output CSET485_Assignment1_0035.ipynb
   ```

3. All output tables (CSV) and charts (PNG) are saved automatically in the `outputs/` folder.

---

## Library List

| Library | Version tested |
|---------|---------------|
| pandas | 2.1.4 |
| numpy | 1.26.4 |
| matplotlib | 3.8.2 |
| seaborn | 0.13.2 |
| scikit-learn | 1.4.0 |
| statsmodels | 0.14.x |
| nbconvert | 7.17.1 |
| jupyter | 1.x |

See `requirements.txt` for the full version constraints.

---

## Notebook Contents

| Section | Topic |
|---------|-------|
| 0 | Setup, imports, data loading |
| 1 | Data Preprocessing (missing values, encoding, outliers, scaling, 70/30 split) |
| 2 | Part 1 – OLS vs Logistic Regression comparison |
| 3 | Part 2.1 – Simpson's Paradox Hunt (statsmodels Logit, subgroup analysis) |
| 4 | Part 2.2 – Omitted-Variable Bias (duration dropped, coefficient shifts) |
| 5 | Part 2.3 – Adversarial Subset Construction (confident errors, subset profile) |
| 6 | Part 2.4 – Fairness Trade-Off Analysis (gender, DP / EO / PP across thresholds) |
| 7 | Final Summary (key numbers for PDF export) |

---

## Output Files

After running, the `outputs/` folder contains:

**CSV tables:**
- `simpsons_table.csv`
- `ovb_table.csv`
- `adversarial_comparison.csv`
- `fairness_table.csv`

**PNG charts:**
- `outlier_boxplot.png`
- `agreement_heatmap.png`
- `simpsons_coef_plot.png`
- `ovb_bar_chart.png`
- `adversarial_age_hist.png`
- `adversarial_feature_diffs.png`
- `fairness_tradeoff.png`

---

## Notes

- `random_state = 35` is used for the train-test split and all other random operations.
- No Part 3 (descriptive answers) or Part 4 (reflection essay) content is included in the notebook.
- The notebook is fully reproducible: Restart and Run All produces identical results.
- Exactly two code-cell comments exist (per assignment rules): one in the dataset loading cell, one on the line above `random_state = 35`.
