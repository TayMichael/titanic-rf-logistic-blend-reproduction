# Verification

This repo was executed end-to-end before publication.

- Python: 3.13.5
- pandas: 2.2.3
- NumPy: 2.3.5
- scikit-learn: 1.8.0
- Reference file: `final_rf_target_probability_blend_candidate.csv`
- Maximum absolute prediction difference after regeneration: `2.558e-13`
- Acceptance criterion: `<= 1e-12`
- Result: **PASS**

The small non-zero difference is floating-point numerical variation; the reproduced probabilities are numerically identical to the submitted reference at the stated tolerance.
