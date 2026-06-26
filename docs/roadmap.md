# AI Engineer Execution Roadmap
### Official Day 1: 2026-06-23 (Tuesday) · Target finish: ~2026-11-07 (~138 calendar days)

This roadmap is designed for a full-time office schedule from **11:00 am to 6:00 pm** and aims to finish covering the full tracker without burnout. It is a staged execution plan with clear outputs, not a task dump.

**Tracker Day numbers below are a content/topic reference only — they no longer map 1:1 to calendar days.** The tracker's full curriculum, in its original order, is stretched from 120 to **~138 calendar days**. Nothing from the tracker is skipped — every topic and deliverable is still covered, in the same sequence — the pace is just more humane, especially in the densest stretches (Transformers/RAG, the multi-agent-framework block, and the coding-interview sprint). Each phase below shows both its **Tracker Day range** (look up exact tasks in the PDF/xlsx) and its **actual calendar date range** (what you follow day to day).

This does trim the buffer before the Jan 2027 interview-readiness target from ~2.5 months to ~2 months — still comfortable, just worth knowing.

---

## 1. Operating principles
1. Survive the schedule first; optimize later.
2. One main objective per day.
3. Build while learning.
4. Keep documentation small and useful.
5. Ship fewer repos, but make them good.
6. Trust the daily log and commit history over memory.
7. Prefer simple, readable code and plain-English explanations over clever-but-dense ones — for example, structuring from-scratch model parameters as separate named attributes (`weights`, `bias`) rather than one combined vector. (Locked in on Day 2 — full detail in `memory-log.md` Section 3.)

---

## 2. Sustainable time split

### Weekdays
Use the same rhythm most days.

| Time | Use |
|---|---|
| 7:00–8:45 am | Deep work: learn one concept and implement it |
| 8:45–9:15 am | Quick recap, write notes, capture questions |
| 11:00 am–6:00 pm | Office work |
| 7:45–8:45 pm | Light coding / DSA / revision |
| 9:00–9:30 pm | Journal update + git commit |
| 9:30 pm onward | Stop. Recover. Sleep on time. |

### Weekend
| Day | Use |
|---|---|
| Saturday | 4–5 hours deep build + 1 hour cleanup |
| Sunday | 2–3 hours review + planning, then rest |

### Burnout control
- Keep one lighter day each week.
- If work is heavy, protect the morning block and reduce the evening block.
- Never try to "catch up" by doubling everything in one night.
- If energy is low, cut scope before cutting sleep.

---

## 3. Daily operating template

### Start of day
1. Read the one-sentence goal.
2. Open the repo and notebook from the previous session.
3. Write the date and objective at the top of the working note.
4. Decide the single deliverable for the day.

### During the study block
1. Learn the concept.
2. Implement it.
3. Test it.
4. Record results.
5. Stop when the deliverable is complete.

### End of day
1. Write a short summary of what was learned.
2. Save the notebook or script.
3. Export only useful plots.
4. Update the daily journal file.
5. Commit once with a clear message.
6. Write tomorrow's first task in one line.
7. When the chat ends with **"End of day"**, use it as the handoff signal to close the day, update the next-day scope, and record the actual results before starting anything new.
8. The "End of day" handoff returns a fixed set of files to commit: the dated daily note, updated `memory-log.md`, updated `roadmap.md`, updated `STATUS.md`, the active project's updated `README.md`, and — on any day you solved a DSA problem — the solution file (Section 7 template) plus the updated `dsa-practice` README row. *(Set expanded 2026-06-25 to also include `roadmap.md`, the project README, and the DSA solution file.)*

---

## 4. What to note every day
Keep the daily note small and structured.

Record:
- date
- objective
- what was actually done
- key concepts learned
- one code snippet or formula if important
- metric/result if any
- blocker if any
- next step for tomorrow

Do not turn the note into a long essay.

---

## 5. What to commit every day
Commit only useful, reproducible work.

Typical commit contents:
- notebook or script changes
- README updates (the active project's `README.md` is refreshed every day at "End of day" so it never lags behind the code — convention added 2026-06-25)
- exported plots that matter
- requirements changes if a new package is truly needed
- small data artifacts only if they are meant for the repo

Do not commit:
- tracker PDF/xlsx
- scratch files
- temporary outputs
- notebook checkpoints
- duplicate plots
- half-finished junk

Commit message pattern:
- `day1: iris setup and split`
- `day2: baseline classifiers`
- `day3: validation and comparison`

---

## 6. Tracker content, extended pace (Tracker Days unchanged, calendar stretched to ~138 days)

### Phase 1 — ML Foundations · Tracker Days 1–10 · Calendar: Jun 23 – Jul 4, 2026 (12 days)
**Topics:** supervised/unsupervised/RL, linear & logistic regression, trees/ensembles, k-means/PCA, feature engineering pipelines, NumPy MLP + backprop, CNNs, RNN/LSTM.
**Deliverables:** Iris/Titanic classifier, tabular XGBoost project, k-means segmentation, reusable sklearn pipeline, NumPy MLP from scratch, CIFAR-10 CNN, LSTM sentiment model.
**Exit criteria:** explain the full ML project lifecycle and bias-variance tradeoff; train and compare at least 3 model families end to end.

> **Current cursor (2026-06-26):** Tracker Days 1–4 done — baselines, regression-from-scratch, trees/ensembles, and k-means/PCA segmentation (Project 3). **Next: Tracker Day 5** — feature engineering, encoding, scaling, missing-data handling, and a reusable `sklearn` `Pipeline` + `ColumnTransformer`. Project 2 (`02-tabular-ml-project`) reopens for the deferred SMOTE / `scale_pos_weight` imbalance deep-dive and feature engineering. Project 1 may briefly reopen to add its scaling pipeline.

### Phase 2 — Deep Learning, Transformers & RAG · Tracker Days 11–20 · Calendar: Jul 5 – Jul 17, 2026 (13 days)
**Topics:** self-attention/Transformer architecture, nanoGPT, pretrain vs fine-tune vs RLHF/DPO/LoRA, BPE tokenization, prompt engineering, LangChain memory, embeddings & semantic search, RAG architecture, advanced RAG (reranking, hybrid search).
**Deliverables:** self-attention from scratch, nanoGPT on tiny-shakespeare, LoRA fine-tune, BPE tokenizer, structured-output extractor, chatbot with memory, semantic search engine, end-to-end RAG app, RAG + reranker/hybrid upgrade.
**Exit criteria:** walk through how GPT generates a token; explain a full RAG pipeline end to end.
*(Densest stretch in the original tracker — given the extra 3 days here.)*

### Phase 3 — RAG, Serving, Deployment & MLOps · Tracker Days 21–30 · Calendar: Jul 18 – Jul 28, 2026 (11 days)
**Topics:** RAG evaluation (RAGAS/DeepEval), LLM serving internals (vLLM, KV cache), function/tool calling, guardrails & output validation, FastAPI + Docker deployment, MLOps/LLMOps + CI evals, fine-tuning in practice, Anthropic's agent patterns.
**Deliverables:** RAG eval harness, served local model with latency benchmark, tool-calling app, guarded tool-using app, Dockerized FastAPI RAG service, CI with automated evals, a domain fine-tune, the augmented-LLM pattern (LLM+retrieval+tools+memory), a router workflow.
**Exit criteria:** describe the modern AI-engineering stack; explain how you'd deploy an LLM app to production.

### Phase 4 — Agentic AI: Design, Frameworks & MCP · Tracker Days 31–40 · Calendar: Jul 29 – Aug 9, 2026 (12 days)
**Topics:** multi-agent roles/handoffs, agent fundamentals (HF Agents Course), agent memory (short/long-term, episodic, semantic), LangGraph, CrewAI, AutoGen, Model Context Protocol.
**Deliverables:** a 3-agent paper design, your first agent from scratch, an agent with persistent memory, a LangGraph state machine, a CrewAI multi-agent crew, a coder+reviewer AutoGen pair, a custom MCP server, RAG+tools+multi-agent combined into one assistant.
**Exit criteria:** explain a full agent-loop iteration; know when *not* to build an agent; explain MCP vs. plain function calling.
*(Four new frameworks in one stretch — given 2 extra days to not skim them.)*

### Phase 5 — Agent Orchestration & Capstone · Tracker Days 41–50 · Calendar: Aug 10 – Aug 20, 2026 (11 days)
**Topics:** agent evaluation, control-plane concepts, failure modes & reliability (budgets/timeouts/retries), scaling agents (queues/concurrency), observability & tracing (Langfuse), then a 4-day capstone build.
**Deliverables:** an agent eval suite, a control-plane design (scheduler+state store+monitor), guardrailed orchestration, a task-queue worker model, full tracing/dashboards, and the capstone itself: core loop + memory + multi-agent + MCP + guardrails, deployed with a demo and README.
**Exit criteria:** ship and present one ambitious, end-to-end agentic system.

### Phase 6 — AI System Design + Interview Onramp · Tracker Days 51–60 · Calendar: Aug 21 – Sep 1, 2026 (12 days)
**Topics:** LLM API gateway design, RAG-at-scale design, multi-tenant agent platform design, recommendation/ranking system design, batch vs. stream data pipelines, the end-to-end ML/LLM design framework + rubric, first coding-interview patterns (arrays/hashing/two-pointer/sliding-window/stack/BST/graphs), behavioral STAR method.
**Deliverables:** 5 design docs, a timed "Design ChatGPT" mock, your first structured LeetCode sets, 8 STAR stories from your own projects.
**Exit criteria:** design a production RAG system, an LLM gateway, and an agent platform on paper, and defend the tradeoffs.

### Phase 7 — Interview Mastery: Tracks Begin · Tracker Days 61–70 · Calendar: Sep 2 – Sep 15, 2026 (14 days)
**Topics:** coding-pattern sprints (trees, graphs, 1-D/2-D DP, greedy, intervals, heaps, backtracking) at a humane daily rate (see Section 7 — this is the stretch that absorbs the de-loaded coding sprint), paired with AI-theory rapid-fire drills, 3 timed system-design mocks (RAG Q&A product, agent platform, scalable LLM serving).
**Deliverables:** full coverage of all 7 coding patterns, 3 refined design docs, weakness-targeted re-solves of your hardest missed problems.
**Exit criteria:** hold your own across coding + AI theory + design under time pressure, back to back.
*(Biggest single extension — 4 extra days, specifically to bring the coding pace down from the tracker's original 7–8/day.)*

### Phase 8 — Interview Mastery: Deepening · Tracker Days 71–80 · Calendar: Sep 16 – Sep 26, 2026 (11 days)
**Topics:** full recorded mock rounds — coding, AI/DL theory, system design, behavioral — each followed by a self-review + patch cycle; final coding/theory/design sprints; 2-minute project pitches for your top 5 repos.
**Deliverables:** 4 recorded mock rounds with debriefs, a reusable design template, polished pitches for your flagship projects.
**Exit criteria:** run a full mixed mock loop and produce a concrete, prioritized improvement list.

### Phase 9 — Interview Mastery: Mock Loops · Tracker Days 81–90 · Calendar: Sep 27 – Oct 6, 2026 (10 days)
**Topics:** two full recorded onsite-loop simulations, resume/LinkedIn/portfolio alignment, a 1–5 self-assessment across all four tracks, then a light maintenance rotation (coding/theory/design/behavioral, one per day).
**Deliverables:** 2 full-loop debriefs, an aligned resume-to-project mapping, a portfolio health check (all repos clean, links live).
**Exit criteria:** you can honestly rate yourself ready (4–5/5) on at least 3 of the 4 tracks.

### Phase 10 — Advanced Topics + Active Interviewing · Tracker Days 91–100 · Calendar: Oct 7 – Oct 17, 2026 (11 days)
**Topics:** Mixture-of-Experts & long-context techniques, agentic RAG/GraphRAG, DSPy, multimodal (vision-language) models, AI safety & red-teaming, LLM cost optimization, then a full theory sweep across the whole curriculum.
**Deliverables:** small demos for each advanced topic, a responsible-AI checklist added to your capstone, a cost audit of one of your apps, first real applications go out.
**Exit criteria:** comprehensive rapid-fire across everything — ML → DL → LLM → RAG → agents → serving → safety — without notes.

### Phase 11 — Active Interviewing & Maintenance · Tracker Days 101–110 · Calendar: Oct 18 – Oct 27, 2026 (10 days)
**Topics:** a steady daily maintenance rotation (coding, system design, behavioral, AI theory — one focus per day) layered under real interview activity and debriefs.
**Deliverables:** ongoing interview debriefs, cheat sheets kept current, applications tracked.
**Exit criteria:** the maintenance rhythm holds steady even while real interviews are happening.

### Phase 12 — Final Interviews, Offers & Wrap-Up · Tracker Days 111–120 · Calendar: Oct 28 – Nov 7, 2026 (11 days)
**Topics:** same maintenance rotation continues, plus negotiation and offer-evaluation prep, plus a concrete ongoing-learning plan for after the finish line.
**Deliverables:** final portfolio confirmation, a self-certification across all four tracks, a written post-finish learning plan.
**Exit criteria:** job-ready, with a clear story for why you are moving into AI engineering — and a plan for what you keep learning next.

---

## 7. Coding / DSA practice track (runs in parallel, every day)

| Stretch | Calendar range | Pace | Notes |
|---|---|---|---|
| Light habit | Phases 1–6 (Jun 23 – Sep 1) | **1 problem/day** (Easy→Medium, ~20–30 min) | Arrays, Strings, HashMap, Two Pointers, Sliding Window, Stack, Binary Search, Linked List, Trees, Graphs — builds the habit without competing with the heavier ML/DL/RAG/Agents focus of these days |
| Coding-focused stretch | Phase 7 (Sep 2 – Sep 15, 14 days) | **3–4 problems/day** | DP (1-D & 2-D), Greedy, Intervals, Heaps, Backtracking — same patterns the tracker assigns on Days 57–65, deliberately spread over more days instead of the tracker's original 7–8/day |
| Continued practice | Phase 8 (Sep 16 – Sep 26, 11 days) | **3–4 problems/day** | Mixed patterns, mock-paced, same gentler rate carried forward instead of stepping up |
| Maintenance / active interviewing | Phases 9–12 (Sep 27 – Nov 7) | **2–4 problems/day**, timed, mixed | Unchanged — this pace was never the problem |

List: NeetCode 150 (or Blind 75 first), solved roughly in the pattern order above. Rough total by the finish line: **~200–230 problems** *(estimate — total rises slightly since the timeline is longer, even though the daily peak is lower)*, several patterns repeated 2–3×.

**Solution-file convention (`dsa-practice` repo).** One folder per pattern, one file per problem, each file starting with this fixed header comment block, then the code (locked 2026-06-25; canonical copy in `memory-log.md` Section 3):

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

On a day you solved a problem, the solution file (in the right pattern folder) and the `dsa-practice` README progress-table row are handed back at "End of day" alongside the usual closeout files.

---

## 8. Portfolio strategy
- Prefer 6–8 strong, polished repos over a pile of shallow ones.
- Suggested flagship repo set:
  - `01-ml-foundations-iris`
  - `02-tabular-ml-project`
  - `03-transformer-rag-llm-apps` (Phases 2–3 work consolidated)
  - `04-agentic-mcp-capstone` (Phases 4–5 work consolidated)
  - `05-system-design-portfolio` (Phase 6 design docs)
  - `06-dsa-leetcode-log`
  - `07-automotive-ai-capstone`
- Keep the portfolio balanced across classical ML, deep learning/RAG, agents, system design, and one domain capstone.
- Note: the tracker itself lists ~26 distinct project tasks across 120 days. This strategy deliberately *consolidates* many of them as notebooks/sections inside the 6–8 flagship repos above, rather than shipping each as its own repo — fewer, more polished repos over more, shallower ones.

### Repo structure
Each project repo should generally contain:
```text
repo/
├── README.md
├── requirements.txt
├── notebooks/
├── src/
├── images/
└── data/   (only if the dataset is meant to live in the repo)
```

### README must answer
- What is this project?
- Why does it matter?
- What data was used?
- What methods were tried?
- What worked best?
- What were the tradeoffs?
- How do I run it?

### Hygiene
- Keep `main` clean.
- Use a feature branch only when the change is bigger than a single session.
- Reuse helper functions.
- Remove dead code.
- Export only useful figures.
- Keep filenames stable.
- Avoid cluttering the repo with too many notebooks.

---

## 10. Finish criteria for the full tracker (~138 days)
By the finish line (~Nov 7, 2026), you should have:
- a clean GitHub portfolio,
- 6–8 serious repos,
- a strong RAG project,
- one agentic project,
- system design notes,
- ~200–230 LeetCode problems solved across all major patterns (estimate),
- interview-ready coding and behavioral preparation,
- and a clear story for why you are moving into AI engineering.

That is the finish line — every tracker topic covered, none skipped, just paced to actually stick.
