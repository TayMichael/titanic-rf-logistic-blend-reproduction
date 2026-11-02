# Verification

This notebook was executed end-to-end against the exact Titanic input files used by the competition.

- Input SHA-256 checks: PASS
- Repeated 5-fold × 3 Random Forest ROC-AUC: `0.879195`
- Repeated 5-fold × 3 target-logistic ROC-AUC: `0.882810`
- Repeated 5-fold × 3 50/50 blend ROC-AUC: `0.890222`
- Blend repeated CV SD: `0.018961`
- Reference submission: `final_rf_target_probability_blend_candidate.csv`
- Maximum absolute prediction difference after regeneration: `2.558e-13`
- Acceptance criterion: `<= 1e-12`
- Result: **PASS**

The small non-zero difference is floating-point numerical variation; the reproduced probabilities are numerically identical to the submitted reference at the stated tolerance.
