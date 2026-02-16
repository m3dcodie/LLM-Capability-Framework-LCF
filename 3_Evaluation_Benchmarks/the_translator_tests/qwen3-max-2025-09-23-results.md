# Benchmark: Qwen3-Max Transformation (L2)

**Date:** 2026-02-16  
**Model:** `qwen3-max-2025-09-23`  
**Task:** JSON to Markdown Transformation

## Performance Metrics

- **Temporal Velocity (TTFT):** 2.0 seconds
- **Output Format:** Markdown
- **Constraint Adherence:** High (Followed structural headers)

## Observations

- **Summary Quality:** Strong technical summary.
- **Data Loss:** **Significant.** The model omitted the "Guinness World Record" and "AWS SoluLearn" certifications present in the Layer 1 JSON.
- **Fidelity Note:** Prioritizes conciseness over entity preservation.

## Verdict

**Status: FAIL (Fidelity Drifts)** Recommended only for internal-facing, low-stakes summaries where speed is the primary constraint.
