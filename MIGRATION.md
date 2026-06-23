# Migration: nested phases/ structure → flat structure
*Delete this file once migration is done — it's a one-time guide, not a permanent part of the repo.*

If you already unzipped and pushed the earlier nested version (`phases/phase-0-foundations/`, `phases/phase-1-120-day-sprint/module-0X/`, `periodic-reviews/`, `notes/`+`daily/` split), here's how to move to this flat version without losing anything you've already written.

## 1. Replace the two core docs
```bash
cp path/to/this/docs/roadmap.md      your-repo/docs/roadmap.md
cp path/to/this/docs/memory-log.md   your-repo/docs/memory-log.md
```
These are the reconciled versions — day numbers now match the tracker exactly, the DSA track is back, and Section 4 of the memory log describes this flat scheme.

## 2. Flatten daily entries
Old: `phases/<phase>/<module>/daily/YYYY-MM-DD.md` + a matching `notes/YYYY-MM-DD.md`.
New: a single `daily/YYYY-MM-DD.md` per day (short — objective, what was done, key concepts, blocker, next step; see the new `daily/_TEMPLATE.md`).

If you have real entries already: merge each day's `daily/` + `notes/` pair into one file in the new top-level `daily/`, trimmed down to the template's fields. Don't try to preserve every line — the new philosophy is intentionally more concise.

## 3. Flatten mock debriefs
Old: `mock-debriefs/coding/`, `mock-debriefs/system-design/`, `mock-debriefs/behavioral/` subfolders.
New: one flat `mock-debriefs/` folder, type recorded in the front-matter and the filename, e.g. `mock-debriefs/2026-09-12-coding.md`.

## 4. Drop `periodic-reviews/`
Weekly/monthly/quarterly reviews now just happen as a normal `daily/` entry on the tracker's own review days (Day 7, 14, 21, 28, etc.) — no separate folder needed.

## 5. Keep as-is (unaffected)
`cheat-sheets/`, `milestones.md`, `resources.md`, `interviews/`, `.gitignore`, `README.md` (replace with the updated one in this skeleton), `STATUS.md` (replace with the updated one — same job, new wording).

## 6. Commit
```bash
git add -A
git commit -m "Migrate journal to flat structure; realign roadmap/memory-log to tracker days; restore DSA track"
```
