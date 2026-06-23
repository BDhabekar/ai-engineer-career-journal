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

### Dataset-specific facts
- Dataset-specific conventions (exact split calls, column setup, random seeds for a given project) live in that **project's own README** — not in this file.
- While a project is actively in progress, also upload its README alongside the usual 4 reference files when continuing work on that specific project, so the conventions are available in a fresh chat.
- If a later project's convention becomes a durable global rule, promote it into the sections above — otherwise keep it local to the project.

### DSA / coding practice
- Pace: 1 problem/day (light habit, Phases 1–6) → 3–4/day (the tracker's DP/greedy/heaps/backtracking patterns, now spread over more days instead of the tracker's original 7–8/day) → 2–4/day (maintenance, unchanged).
- List: NeetCode 150 / Blind 75, solved in pattern order. Target ~200–230 problems by the finish line (estimate).
- Full detail in `roadmap.md` Section 7.
- **Coding practice lives in its own repo** (e.g. `dsa-practice`), separate from both the journal repo and the numbered ML project repos:
  - one folder per pattern, named to match the tracker's Day 57–65 groupings (`arrays-hashing`, `two-pointers`, `sliding-window`, `stack`, `binary-search`, `linked-list`, `trees-bst`, `graphs`, `dp-1d`, `dp-2d-greedy-intervals`, `heaps-backtracking`),
  - one file per problem, each starting with a header comment: problem name, link, pattern, difficulty, approach (1-2 lines), time/space complexity,
  - a root `README.md` acting as a progress-tracker table (date, problem, pattern, difficulty, link, complexity),
  - commit messages short and specific, e.g. `dsa: two-sum (arrays-hashing)`, one commit per problem (or a small same-sitting batch).
  - Daily journal notes stay high-level about DSA ("solved 1 problem") — the coding repo's own README carries the per-problem detail.

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
- `dsa-practice` repo structure and templates (README tracker + solution-file convention) proposed today — first commit (Two Sum) done.
- Current phase: **Phase 1 — ML Foundations** (Tracker Days 1–10, calendar Jun 23 – Jul 4), Iris as the practice dataset. On track; Day 2 is next.
- Current priority:
  1. keep the daily routine sustainable,
  2. push commits consistently across all three repos (journal, ML project, dsa-practice),
  3. keep repo structures simple and stable,
  4. avoid burnout.

---

## 6. Daily execution protocol
- Before work: write the day's objective in one sentence.
- During work: keep one notebook or one code path active; avoid task hopping.
- After work: record only what was actually completed.
- Every day should end with:
  - one short note,
  - one clean commit,
  - one next-step line for tomorrow.
- When the chat ends with the phrase **"End of day"**, treat it as the formal closeout signal: update the roadmap with the next day's scope and update this memory log with the actual completed work, blockers, and durable decisions.
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
