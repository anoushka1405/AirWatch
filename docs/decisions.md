# AirWatch Engineering Decisions

This document records the important engineering and architectural decisions made throughout the project.

---

## Decision 001 — Project Structure

**Date:** 2026-07-10

### Decision
Organize the project using pipeline-based modules (`ingestion`, `preprocessing`, `database`, `analysis`, `ml`, and `utils`) instead of placing all code in a single directory.

### Rationale
This mirrors the lifecycle of the data and keeps responsibilities separated, making the codebase easier to maintain and extend.

### Alternatives Considered
- A single `src/` folder
- Notebook-only development

### Status
Accepted

---

## Decision 002 — Ignore Generated Files

**Date:** 2026-07-10

### Decision
Ignore virtual environments, Python cache files, processed datasets, and other generated artifacts using `.gitignore`.

### Rationale
The repository should contain source code and documentation, not generated files. This keeps the project lightweight, reproducible, and easy to clone.

### Status
Accepted

## Decision: Data ingestion approach

Date: 2026-07-10

For the first version of AirWatch, we will use historical air quality CSV data instead of building an API pipeline.

Reason:
- Faster to validate database schema and analytics workflow
- Easier reproducibility
- Raw data can be stored unchanged before processing

Future improvement:
- Add live API ingestion once the core pipeline is stable.