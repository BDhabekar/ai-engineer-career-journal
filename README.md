# AI Engineer Career Journal — Bharat

The narrative companion to my project repos. Project repos prove what I can **build**; this repo tracks how I **learned** — daily notes, cheat sheets, mock-interview debriefs, and real interview records.

## Background
MBD/embedded engineer (Simulink, AUTOSAR, ISO 26262), 5+ years in automotive, transitioning into AI Engineering with a target specialization in automotive AI / RAG-based systems.

## Current status
See [`STATUS.md`](./STATUS.md).

## Structure

| Folder/file | What lives here |
|---|---|
| `docs/roadmap.md` | The stable execution plan — schedule, the 120-day structure (day numbers match the tracker exactly), DSA pace, portfolio strategy |
| `docs/memory-log.md` | Ground-truth conventions + anti-hallucination rules, used to keep AI-assisted study sessions consistent across fresh chats |
| `daily/` | One dated file per day — objective, what was done, key concepts, blockers, next step. Kept short by design. |
| `cheat-sheets/` | Living, topic-based reference docs, refined in place at the tracker's built-in review checkpoints |
| `mock-debriefs/` | One dated file per practice round (coding/system-design/behavioral), feeding improvements back into cheat-sheets |
| `interviews/` | Real interview records, one folder per company |
| `milestones.md` | Career-spanning highlight reel |
| `resources.md` | Bookmarked papers, courses, blogs, tools |
| `STATUS.md` | Overwritten daily — always "right now," never history |

## Related repos
- `01-ml-foundations-iris` — Phase 1 flagship project
- `06-dsa-leetcode-log` — LeetCode solutions by pattern
- *(add links as each project repo is created — see `docs/roadmap.md` Section 8 for the full flagship set)*

## Daily workflow
1. Work the day's session (fresh chat each day; upload the tracker PDF, tracker xlsx, `docs/roadmap.md`, `docs/memory-log.md` — plus the active project's README if mid-project).
2. End the session with the phrase **"End of day"** as the closeout signal.
3. Update `docs/memory-log.md` if a durable decision or phase changed.
4. Write today's entry in `daily/YYYY-MM-DD.md`.
5. Overwrite `STATUS.md`.
6. Commit everything with a short, specific message (e.g. `day1: iris setup and split`).
7. Open tomorrow's fresh chat and say "continue."
