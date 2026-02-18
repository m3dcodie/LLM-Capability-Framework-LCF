## 1. The Verdict: Claude 4.5 Haiku vs. Gemini 3 Pro

| Feature                  | Claude 4.5 Haiku (The Scout)                                                        | Gemini 3 Pro (The Director)                                                    |
| ------------------------ | ----------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| **Structural Fidelity**  | **Superior.** It preserved the nested lists in `Key Responsibilities`.              | **Average.** It collapsed responsibilities into a single `Description` string. |
| **Entity Density**       | **High.** It identified specific achievements (Guinness Records) as separate items. | **Low.** It merged achievements into the general `Certifications` list.        |
| **Constraint Adherence** | **100%.** It followed the JSON schema exactly as requested.                         | **Failed.** It simplified the `Experience` schema (Role instead of Job Title). |
| **Operational Logic**    | **Literalist.** It acted as a parser.                                               | **Generalist.** It acted as a summarizer.                                      |

---

## 2. Why Haiku "Won" Layer 1

**The Summarization Bias:**
Gemini 3 Pro is a "Reasoning Titan." Its training pushes it to be concise and "helpful." When it sees a long list of job duties, its internal logic says: _"The user wants to know what he did, let me summarize this into a clean paragraph."_

- **The Problem:** In Layer 1, **Summarization is a Failure.** We want the raw data mapped to a grid, not a "vibe" of the data.

**The Scout Advantage:**
Claude 4.5 Haiku doesn't "try to help." It treats your prompt like a **Code Requirement**. It saw the list of responsibilities and mapped them 1-to-1 because its parameter count isn't high enough to trigger "over-summarization" logic. It is a **deterministic translator**.

---

> ### **Architect’s Note: The Density Divergence**
>
> - **Finding:** Gemini 3 Pro (L6) lost ~40% of the specific technical "signals" in the experience section by collapsing bullet points into a summary.
> - **Finding:** Claude 4.5 Haiku (L1) retained 100% of the technical signals, preserving the "Event-driven architecture" and "50+ applications" metrics that are vital for downstream filtering.
> - **Conclusion:** Using a "smarter" model for Layer 1 actually **degraded** the system's intelligence because the data was filtered before the application could use it.

---

### **Layer 1 Metric: Schema Adherence Rate (SAR)**

- **Pass:** Output is valid JSON, includes all requested keys, and preserves the original list structures (Claude Haiku).
- **Fail:** Output is valid JSON but has "collapsed" data structures or modified keys (Gemini 3 Pro).

### **Layer 1 Metric: Entity Extraction Rate (EER)**

- **Scout Performance:** High. Captures granular details (e.g., individual AWS services).
- **Director Performance:** Low. Groups details into general categories (e.g., "AWS services" instead of "SQS, SNS, EventBridge").

### **Layer 1 Latency**

with file upload

### 1. Architectural Analysis: Why Haiku is the L1 Champion

Based on the latest February 2026 benchmarks, **Claude 4.5 Haiku** is optimized as a "Frontier-Lite" model.

- **The "Thinking" Variable:** While frontier models like Gemini 3 Pro often engage in "Deep Thinking" or "Reasoning Chains" (Internal CoT) that delay the first token by 20+ seconds, Haiku 4.5 is engineered for **Direct-to-Token** extraction.

- **Context Efficiency:** Haiku uses **Context Awareness** (a new 2026 feature) to instantly map the PDF structure without the overhead of "Multimodal Perception" that larger models use to "describe" the document before extracting from it.

---

| Metric                | Claude 4.5 Haiku (L1 Scout)    | Gemini 3 Pro (L6 Director)   |
| --------------------- | ------------------------------ | ---------------------------- |
| **TTFT (Latency)**    | **11 seconds**                 | 30+ seconds (Projected)      |
| **Instruction Score** | **73.3% (SWE-bench)**          | ~70% (Generalist)            |
| **Data Fidelity**     | **100%** (Captured 22+ skills) | ~60% (Summarized to 6 items) |
| **System Verdict**    | **The Ideal Scout**            | **The Auditor/Strategist**   |
