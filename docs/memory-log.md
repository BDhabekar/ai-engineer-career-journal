# Bharat — AI Engineer Journey Memory Log
*Purpose: compact source of truth for this journey. When this file and conversation differ, this file is the default reference. If something is unclear, ask — do not guess.*

---

## 1. Identity, goal, and timeline
- Bharat — automotive MBD / embedded engineer (Simulink, AUTOSAR, ISO 26262), based in Pune.
- Target identity: AI Engineer with strong automotive depth, especially RAG-based systems and production LLM applications.
- Official restart date for this journey: **2026-06-23 (Tuesday)**.
- The tracker's full 120 days of content is being covered, in its original order, over an **extended ~138-day calendar timeline** (target finish ~2026-11-07). Nothing is skipped — the pace is just more generous, especially in the densest stretches.
- **Tracker Day numbers are a content/topic reference only — they no longer map 1:1 to calendar days.** Use Tracker Day N to look up exact tasks in the PDF/xlsx; use the actual date for "what to do today." See `roadmap.md` Section 6 for the full phase-by-phase calendar mapping.
- Target interview-readiness window: **January 2027** (buffer after finish: ~2 months, down from ~2.5 — still comfortable).
- Journal repo: `ai-engineer-career-journal`.
- Primary project repos should use numbered prefixes, for example: `01-ml-foundations-iris`, `02-...`.

---

## 2. Source hierarchy and anti-hallucination rules
- Never invent progress, completion, metrics, dates, filenames, or conclusions.
- If something is unknown, mark it as unknown.
- If something is not done, say it is not done.
- Separate states into exactly three buckets: **not started**, **in progress**, **done**.
- Do not blur "planned", "attempted", and "completed".
- Prefer the most recent explicit instruction in the current chat, then this file, then older context.
- If a task needs a missing detail, ask a clarification question instead of guessing.
- Keep "what was built" separate from "what was learned".
- When a claim is estimated, label it as an estimate.
- Do not let a memory entry quietly overwrite a project-specific fact. If a project needs its own convention, store that convention in the project's own README.

---

## 3. Canonical facts for the whole journey
These rules apply to every future project unless a project document explicitly overrides them.

### Project definition
Every project should state:
- problem statement,
- data source,
- target / label definition,
- success metric,
- validation strategy,
- baseline,
- expected deliverable,
- known risks or caveats.

### Evaluation discipline
- Train, validation, and test must be separated in a way that matches the data type.
- Classification tasks should usually use stratified splits when labels are imbalanced or multi-class.
- Time-dependent problems must use time-aware splitting.
- Grouped data must use group-aware splitting.
- Compare models only on the same split or the same cross-validation protocol.
- A single accuracy number is not enough unless the task is trivially balanced and the business cost is symmetric.

### Reproducibility
- Fix random seeds when results need to be repeatable.
- Capture dependencies in `requirements.txt` or an equivalent environment file.
- Keep runnable instructions in the repo.
- Save useful outputs that help another person reproduce or understand the result.
- Do not treat chat output as a substitute for committed code.

### Engineering hygiene
- Use notebooks for exploration and learning.
- Move reusable logic into scripts or modules.
- Keep repo structure simple and stable.
- Export plots only when they explain an important decision.
- Prefer small, meaningful commits over large dump commits.
- Keep names stable once chosen.

### Universal modeling conventions
- Define the feature set explicitly.
- Define the target explicitly.
- Use the same preprocessing path for train/validation/test.
- Prevent leakage aggressively.
- Use the right metric for the task:
  - classification: accuracy, precision, recall, F1, ROC-AUC, confusion matrix as appropriate,
  - regression: MAE, RMSE, MAPE, R² as appropriate,
  - ranking / retrieval / generation: project-specific metrics documented in the repo.
- When comparing models, include a simple baseline.
- Do not claim a model is "best" without showing the comparison rule and the validation method.
- For from-scratch implementations, keep parameters as separate, named attributes (e.g. `weights` and `bias`) rather than packing them into one combined vector via a bias column appended to X — matches the convention used by scikit-learn, PyTorch, and the NumPy MLP coming up later in this track. *(Locked in Day 2.)*

### Explanation style
- Explain ML and code concepts in plain, jargon-light English — in chat and in notebook markdown alike.
- Define technical terms simply on first use rather than reaching for dense academic phrasing.
- Still use the necessary technical vocabulary itself (e.g. gradient descent, regularization, ROC-AUC) — the goal is clarity, not avoiding the real terms, since that vocabulary is the actual subject being learned. *(Locked in Day 2.)*

### Dataset-specific facts
- Dataset-specific conventions (exact split calls, column setup, random seeds for a given project) live in that **project's own README** — not in this file.
- While a project is actively in progress, also upload its README alongside the usual 5 reference files (tracker PDF, tracker Excel, `roadmap.md`, `memory-log.md`, the Daily Playbook) when continuing work on that specific project — **6 uploads in total** — so the conventions are available in a fresh chat. *(Upload count raised from 4 to 6 on 2026-06-25: the Daily Playbook and the active project README are now part of the standard daily upload.)*
- If a later project's convention becomes a durable global rule, promote it into the sections above — otherwise keep it local to the project.

### DSA / coding practice
- Pace: 1 problem/day (light habit, Phases 1–6) → 3–4/day (the tracker's DP/greedy/heaps/backtracking patterns, now spread over more days instead of the tracker's original 7–8/day) → 2–4/day (maintenance, unchanged).
- List: NeetCode 150 / Blind 75, solved in pattern order. Target ~200–230 problems by the finish line (estimate).
- Full detail in `roadmap.md` Section 7.
- **Coding practice lives in its own repo** (e.g. `dsa-practice`), separate from both the journal repo and the numbered ML project repos:
  - one folder per pattern, named to match the tracker's Day 57–65 groupings (`arrays-hashing`, `two-pointers`, `sliding-window`, `stack`, `binary-search`, `linked-list`, `trees-bst`, `graphs`, `dp-1d`, `dp-2d-greedy-intervals`, `heaps-backtracking`),
  - one file per problem, each starting with a header comment: problem name, link, pattern, difficulty, approach (1-2 lines), time/space complexity,
  - when exploring multiple solution approaches to the *same* problem is itself the learning objective (e.g. a hashmap vs. fixed-array space tradeoff), those approaches may live as multiple classes inside that one file — still one file per **problem**, not one file per approach,
  - a root `README.md` acting as a progress-tracker table (date, problem, pattern, difficulty, link, complexity),
  - commit messages short and specific, e.g. `dsa: two-sum (arrays-hashing)`, one commit per problem (or a small same-sitting batch).
  - Daily journal notes stay high-level about DSA ("solved 1 problem") — the coding repo's own README carries the per-problem detail.

**LeetCode/DSA solution-file header template (locked 2026-06-25).** Every solution file in `dsa-practice` starts with this exact header comment block, then the code:

```python
"""
Problem: <name>
Link: <url>
Pattern: <pattern>
Difficulty: <Easy/Medium/Hard>
Approach: <1-2 lines — the key idea>
Time: O(?)   Space: O(?)
"""

# solution code below
```

---

## 4. Repository and workflow conventions
- Store stable plans in `docs/` (`roadmap.md`, `memory-log.md`).
- Store daily work in dated files directly under `daily/` (one file per day — short and structured, not a long essay; see `roadmap.md` Section 4 for exactly what to record).
- Keep cheat sheets in a flat `cheat-sheets/` folder, one file per topic, updated in place (living documents, not dated).
- Keep mock-interview debriefs in a flat `mock-debriefs/` folder, one dated file per round (e.g. `2026-09-12-coding.md`).
- Keep real interview records in `interviews/<company-name>/`.
- `STATUS.md` is overwritten daily — always describes "right now" (phase/day, last few things done, next up, blockers). It is not history; `daily/` is.
- `milestones.md` and `resources.md` stay at the repo root.
- Keep generated assets, exported plots, and notebooks inside project repos, not inside the journal repo.
- Do not add the tracker PDF/xlsx to GitHub.
- Each project repo should have:
  - `README.md`
  - `requirements.txt`
  - `notebooks/`
  - `src/`
  - `images/`
  - a short results section and run instructions
- The active project's `README.md` is a **living document**: update it at each "End of day" to reflect that day's additions (new notebooks, plots, results), so it never lags behind the actual repo. *(Convention added 2026-06-25 — previously the README was refreshed only occasionally, which let it drift behind the work; the Iris README had to be caught up to Day 2 as a result.)*
- **Daily notebook workflow:** concepts are taught in chat; Bharat builds and practices in his *own* notebook as he goes; after studying he sends that notebook to Claude, who **refines** it into the canonical Iris/Day-2 style (rich markdown theory, LaTeX, comparison tables, interview-Q tags, result-narration cells, Built/Learned summary) **without changing his code or outputs**; the refined notebook is what Bharat commits. *(Workflow locked 2026-06-25.)*
- Commit messages should be short and specific, for example:
  - `day1: iris setup and split`
  - `day2: baseline classifiers`
  - `day3: validation and comparison`
- Journal updates should be grounded in what was actually done, not what was intended.
- A daily closeout should produce one short note, one commit, and one next-step line for tomorrow.

---

## 5. Current status
- Official reset: previous Iris exploration work is treated as warm-up.
- **Day 1 complete (2026-06-23).** Environment confirmed working; `01-ml-foundations-iris` built end-to-end (load → EDA → stratified split → baseline LogisticRegression, 0.9667 test accuracy → confusion matrix / coefficients / KNN comparison → 1 plot) and committed with README, requirements.txt, notebook, and image. 1 DSA problem solved (Two Sum, arrays-hashing).
- **Day 2 complete (2026-06-24).** Linear & logistic regression: built a from-scratch gradient descent linear regression model in NumPy on synthetic data, verified against the closed-form direct solution and `sklearn.LinearRegression` (all three agreed to 4 decimals: bias≈4.0842, weight≈2.9688). Compared batch/mini-batch/SGD convergence noise. Demonstrated L1 vs. L2 regularization (Lasso correctly zeroed 6/10 known-zero synthetic weights). Re-evaluated Day 1's exact Iris model with precision/recall/F1/ROC-AUC (macro AUC = 1.0), not just accuracy. Notebook `02_linear_regression_scratch.ipynb` + 4 plots added as a second notebook inside `01-ml-foundations-iris` (not a new repo — small foundational exercise, kept consolidated).
  - **Same-day revision:** based on direct feedback comparing two coding styles, the model class was rebuilt to use separate `weights`/`bias` attributes instead of a combined parameter vector via a bias column on X, and all notebook markdown was rewritten into plainer, less jargon-heavy English. Verified the revision changes nothing numerically (identical bias/weight/metric values) — only code clarity and prose changed. Both choices are now locked in as durable conventions (Section 3: Universal modeling conventions, Explanation style).
  - 1 DSA problem solved (Valid Anagram, arrays-hashing) — hashmap + fixed-array approaches committed to file; a one-pass hashmap variant was discussed for understanding but not added to the committed file.
- **Day 3 complete (2026-06-25).** Trees & ensembles on a new tabular project, `02-tabular-ml-project` (Titanic via seaborn). Built end-to-end in one notebook (`01_trees_ensembles_titanic.ipynb`): EDA + caught the `alive`≡`survived` leakage trap; minimal preprocessing (median age, mode embarked, sex→0/1, one-hot embarked w/ drop_first, stratified 712/179 split); a single unlimited tree shown overfitting (train 0.982 / test 0.821, depth 23); depth tuned by **5-fold stratified cross-validation** (peak depth 4, CV 0.813±0.013, held-out test 0.788) — the CV tool deferred from Day 1, now in place. Compared four model families on the same CV protocol: tree(d4) 0.813±0.013, random forest(300) 0.812±0.024, gradient boosting(defaults) 0.822±0.031, XGBoost(defaults) 0.801±0.024. Covered bagging vs boosting, feature importances (+ impurity-bias caveat → permutation importance noted), and the mild 62/38 class imbalance (judge per-class; `class_weight="balanced"` ≈ no-op at this mildness; threshold tuning 0.5→0.3 lifted survivor recall 0.725→0.812). Noted XGBoost defaults overfit small data. Practice notebook built by Bharat, then refined by Claude into the canonical style (code/outputs unchanged). 1 DSA problem solved (Group Anagrams, arrays-hashing) — sorted-key + letter-count-key approaches in one file.
- **Day 4 complete (2026-06-26).** First **unsupervised** project: `03-customer-segmentation` (UCI Wholesale Customers, 440 rows, committed to `data/` for offline reproducibility). One notebook (`01_kmeans_pca_segmentation.ipynb`): EDA → correlation heatmap (found the Grocery–Detergents 0.92 / Milk–Grocery 0.73 redundancy) → `np.log1p` + `StandardScaler` (log-before-scale, to tame the heavy right-skew before standardising) → k-means. Chose k via **elbow + silhouette together**: silhouette peaked at k=2 (0.290) with k=3 a close second (0.259) and a cliff after; elbow soft around 3. **Picked k=3 deliberately over the top-scoring k=2** — tiny separation cost, richer/more-actionable third segment; documented the reasoning (the interview-relevant move). Final fit `random_state=42, n_init=10`, sizes 213/147/80 (healthy, no degenerate cluster). **PCA(2)** for the sanity-check scatter: PC1 44.1% + PC2 27.2% = **71.3%** variance in two components — confirming the redundancy predicted from the heatmap (EDA→result loop closed). Segment profiles named three types: household/retail (0), big all-rounder (1), fresh/restaurant (2). External validation via cluster×Channel cross-tab: **cluster 2 is 98.6% Horeca (210/3)** — clustering recovered a real business category from spending alone; clusters 0 & 1 are both retail-leaning but split by **basket/volume**, a cut the binary `Channel` flag can't see — the honest nuance that justifies k=3 over k=2. Concepts covered (chat, not all coded): unsupervised vs supervised, point-in-feature-space + distance intuition, k-means assign↔update loop, points-vs-centroids (why k-means scales where hierarchical doesn't), choosing k (inertia always falls → elbow; silhouette has a real peak → max; business need breaks ties), PCA as variance-maximising directions with two uses (preprocess vs visualise), curse of dimensionality, and t-SNE/UMAP as visualise-only cousins. Practice notebook built by Bharat, refined by Claude into canonical style (code/outputs unchanged); note: histograms were not run in-notebook, so the refined version flags the skew evidence rather than fabricating an output. 1 DSA problem: **Plus One** (LeetCode 66, arrays-hashing) — Bharat's int-round-trip solution kept as documented alternative, **carry-walk committed as primary** (O(n)/O(1), language-portable, the logic the problem actually tests).
  - SMOTE and `scale_pos_weight` were named but **deliberately not implemented** (62/38 too mild to need them); parked as a **Day-5 imbalance deep-dive** — build a genuinely skewed dataset and run `scale_pos_weight` + a SMOTE-in-CV `imblearn` pipeline + threshold tuning side by side, once Pipelines are in hand.
- **Day 5 complete (2026-06-30).** Feature engineering, encoding, scaling, missing-data handling, and a reusable `sklearn` `Pipeline` + `ColumnTransformer` — new notebook in `02-tabular-ml-project` (`02_pipelines_columntransformer_titanic.ipynb`), Day-3 notebook left intact. Rebuilt Titanic preprocessing as a leak-free `ColumnTransformer`: numeric path `SimpleImputer(median, add_indicator=True)` → `StandardScaler`; categorical path `SimpleImputer(most_frequent)` → `OneHotEncoder(handle_unknown="ignore")`; assembled into `Pipeline([("pre", pre), ("model", m)])` and scored on the same 5-fold `StratifiedKFold` from Day 3. Verified in-session that the pipeline reproduced the Day-3 four-model CV baseline (~0.81–0.82) **before** adding features — the refactor changed plumbing, not results. Then added the genuinely-new pieces: a missing-`age` indicator (`add_indicator`), and engineered `family_size = sibsp + parch + 1` and `is_alone`. Final feature-included CV: tree(d4) 0.809±0.010, forest 0.798±0.019, gboost 0.822±0.035, xgb 0.809±0.024; held-out test 0.782 / 0.793 / 0.804 / 0.793. **Clean negative result, reported honestly:** the engineered features + indicator did not materially move CV (stayed in the 0.80–0.82 band) — the ensembles already extract that signal from `sibsp`/`parch`/`fare`. Keystone insight: the leak the by-hand Day-3 version still had (median computed once over all 712 training rows) is closed by the `Pipeline`, which refits every transformer inside each CV fold on that fold's training rows only. **Durable distinction locked:** a preprocessing step must live *inside* the pipeline iff it **learns a parameter from the data** (median, μ/σ, encoder vocabulary); row-wise-deterministic features (`family_size`) are leak-safe to compute up front — nulls are a red herring, learned-vs-not is the test. `pre.fit_transform` width 13 = (7 numeric + 1 age-missing indicator) + (sex 2 + embarked 3 one-hot). Trees confirmed scale-invariant (`StandardScaler` is a visible no-op for them — the "which models need scaling" lesson, seen directly). Practice notebook built by Bharat, refined by Claude into canonical style (code/outputs unchanged). 1 DSA problem: **Contains Duplicate** (LC 217, arrays-hashing, Easy) — set early-exit committed as primary, `len(set(nums)) != len(nums)` kept as documented alternative; caught a real `O(n²)` TLE first (`val in dict.values()` is a linear scan, not a hashmap lookup → fix is `val in set`, O(1)).
- `dsa-practice` repo: five problems solved so far (Two Sum, Valid Anagram, Group Anagrams, Plus One, Contains Duplicate), all arrays-hashing; templates holding.
- Current phase: **Phase 1 — ML Foundations** (Tracker Days 1–10, calendar Jun 23 – Jul 4). On track; **Tracker Days 1–5 done.** Immediate next session: the deferred **SMOTE / `scale_pos_weight` class-imbalance deep-dive** — reopen `02-tabular-ml-project` on a genuinely skewed dataset and run `scale_pos_weight` vs a SMOTE-in-CV `imblearn` pipeline vs threshold tuning, side by side (now that the `Pipeline`/`ColumnTransformer` machinery is in hand). Then **Tracker Day 6** — neural-network fundamentals + a NumPy MLP from scratch.
- Current priority:
  1. keep the daily routine sustainable,
  2. push commits consistently across all three repos (journal, ML project, dsa-practice),
  3. keep repo structures simple and stable,
  4. avoid burnout.
- **Workflow update (2026-06-25, between Day 2 and Day 3):** the Iris project `README.md` was brought up to end-of-Day-2 state (second notebook listed + a Day 2 results section). Three conventions are now locked: (1) the daily upload is **6 files** — the 5 reference files plus the active project README; (2) each "End of day" now also returns an updated `roadmap.md`, the updated project `README.md`, and — on DSA days — the solution file plus the `dsa-practice` README row, in addition to the daily note, `memory-log.md`, and `STATUS.md`; (3) the LeetCode solution-file header template is fixed (see Section 3). *(That note was written in the morning during meta-work; Day 3's learning was then completed the same day — see the Day 3 entry above.)* **Two further conventions locked at the Day 3 closeout:** (4) the daily notebook is built by Bharat and **refined by Claude** into the canonical style with code/outputs preserved (Section 4); (5) that refined notebook is itself an End-of-day deliverable (Section 6).

---

## 6. Daily execution protocol
- Before work: write the day's objective in one sentence.
- During work: keep one notebook or one code path active; avoid task hopping.
- After work: record only what was actually completed.
- Every day should end with:
  - one short note,
  - one clean commit,
  - one next-step line for tomorrow.
- When the chat ends with the phrase **"End of day"**, treat it as the formal closeout signal. Produce and hand back the full updated file set for that day:
  - the dated daily note (`daily/YYYY-MM-DD.md`),
  - updated `memory-log.md` (actual completed work, blockers, durable decisions),
  - updated `roadmap.md` (next day's scope),
  - updated `STATUS.md` (current phase/day, last few things done, next up, blockers),
  - the active project's updated `README.md`,
  - the day's **refined practice notebook** (Bharat's notebook, polished by Claude — Section 4),
  - and, on any day a DSA problem was solved, the solution file (using the Section 3 header template) plus the updated `dsa-practice` README progress row.
- If a day goes poorly, log the reason without drama and continue.
- If a day goes well, do not expand scope late at night.

---

## 7. What "done" means
- "Done" means the work runs, is understandable, and is committed.
- A notebook is not done if it only exists in memory or chat.
- A repo is not done if it has no README or cannot be reproduced.
- A learning topic is not done if it cannot be explained back in plain English.

---

## 8. Memory refresh rule
- Update this file only when a stable decision changes or the current phase changes.
- Do not use this file to store every tiny daily detail — that's what `daily/` is for.
- Use it for durable rules, locked conventions, and current status only.
- If there is a conflict, the latest day's closeout record has priority for that day's facts.
