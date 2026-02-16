# Layer 2: Transformation (The Translator)

**Role:** **Type B (The Engineer)** — Implementation-focused adaptation.

**Objective:** **Semantic Morphing** — Converting the "Zero-Entropy" JSON from Layer 1 into a specific target narrative or schema without losing fact-density.

**Success Metric:** **SRR (Semantic Retention Rate)**.

---

## 1. Functional Definition

Layer 2 is the **Linguistic Bridge**. It takes the rigid, literal data extracted by the Scout and adapts it for a specific human or system context. Unlike Layer 1, which forbids creativity, Layer 2 allows for **stylistic implementation** as long as the underlying facts remain identical.

### Core Transformation Types

- **Narrative Synthesis:** JSON Professional Bio/Headline.
- **Schema Transcoding:** Standard JSON Third-party API Schema (e.g., Salesforce/Jira).
- **Tone Modulation:** Formal Fact Sheet Slack-friendly bullets.

---

## 2. Model Selection: The Engineer (Gemini 3 Flash / Claude 4.5 Sonnet)

While Layer 1 favored the literalist "Scout" (Haiku 4.5), Layer 2 requires a model with a broader **semantic grasp** and superior **instruction breadth**. The goal is a model that can synthesize a narrative without filtering out technical signal.

- **The Requirement:** The model must maintain **Semantic Retention** while adhering to stylistic constraints (e.g., "Summarize to 50 words without losing the mention of AWS CDK").
- **LCF Benchmark Result (Feb 2026):** **Gemini 3 Flash** is the current "Pareto Optimal" choice.
- **Evidence:** In head-to-head testing, Gemini 3 Flash achieved **100% SRR (Semantic Retention Rate)**, capturing high-impact entities like "Guinness World Records" that other high-speed models (Qwen 3 Max) omitted.
- **The Latency/Fidelity Trade-off:** While Gemini 3 Flash (4s) may be slower than Qwen 3 Max (2s), the extra 2 seconds of latency results in **Zero Data Loss**, making it the safer architectural choice for production-grade translation.

- **Alternative:** **Claude 4.5 Sonnet** remains the standard for high-complexity stylistic mapping where professional prose quality is as vital as factual density.

**Validation**
[See benchmark results and tests in [../3_Evaluation_Benchmarks/the_translator_tests](../3_Evaluation_Benchmarks/the_translator_tests)]

---

## 3. The Layer 2 Prompt Contract

Following the **Prompt Contract** five-layer architecture:

| Contract Layer   | Definition for Layer 2                                                                    |
| ---------------- | ----------------------------------------------------------------------------------------- |
| **1. Scope**     | **Input:** Validated JSON from Layer 1. **Boundary:** No external data ingestion allowed. |
| **2. Role**      | **Type B (Engineer):** Specialized in technical implementation and stylistic mapping.     |
| **3. Objective** | **Definition of Done:** 100% Fact Retention within [Target Format].                       |
| **4. Reasoning** | **Logic:** Parse JSON Identify Key Entities Arrange per [Tone/Style] Final Format Audit.  |
| **5. Language**  | **Interface:** Raw Markdown or Target Schema. Zero conversational leakage.                |

---

## 4. Validation: Semantic Retention Rate (SRR)

Validation in Layer 2 measures **"Semantic Drift."**

### The LCF "Mirror Test" Protocol

1. **The Transformation:** L2 Model converts JSON Text Bio.
2. **The Extraction (The Mirror):** A secondary L1 Scout extracts JSON back out of that Bio.
3. **The Delta Audit:** Compare the original JSON with the "Mirror" JSON.

- **Pass:** All technical entities (skills, dates, metrics) match.
- **Fail:** Entities were "summarized away" or hallucinated during the rewrite.
