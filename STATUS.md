# STATUS — right now

**Updated:** 2026-06-30
**Phase:** 1 — ML Foundations (Tracker Days 1–10 · calendar Jun 23 – Jul 4)
**Tracker Days done:** 1–5

## Last few things done
- **Day 5 (2026-06-30):** reusable leak-free `sklearn` `Pipeline` + `ColumnTransformer` on Titanic — median/most-frequent imputation with a missing-`age` indicator, `StandardScaler`, `OneHotEncoder(handle_unknown="ignore")`, plus `family_size`/`is_alone`. Four-model CV reproduced the Day-3 baseline (~0.80–0.82); engineered features were an honest no-op. New notebook in `02-tabular-ml-project`.
- **Day 4 (2026-06-26):** `03-customer-segmentation` — k-means + PCA, k=3 chosen over k=2 with documented reasoning; cluster 2 = 98.6% Horeca.
- **Day 3 (2026-06-25):** `02-tabular-ml-project` — trees/ensembles, 5-fold CV, mild-imbalance handling.

## Next up
1. **SMOTE / `scale_pos_weight` class-imbalance deep-dive** (deferred from Day 4) — reopen `02-tabular-ml-project` on a genuinely skewed dataset: `scale_pos_weight` vs SMOTE-in-CV `imblearn` pipeline vs threshold tuning, side by side.
2. **Tracker Day 6** — neural-network fundamentals + a NumPy MLP from scratch.

## Low-priority backlog
- Optional: retrofit Project 1 (`01-ml-foundations-iris`) with a scaling pipeline (~30 min).

## Blockers
- None.

## Repos
- `ai-engineer-career-journal` (journal) · `01-ml-foundations-iris` · `02-tabular-ml-project` (active) · `03-customer-segmentation` · `dsa-practice` (4 problems, all arrays-hashing).
