                          # LLM Capability Framework (LCF)

**Precision-Matched Intelligence.** The LLM Capability Framework (LCF) is a structural standard for mapping specific task requirements to the most effective model architecture, token strategy, and reasoning depth.

Production-grade AI systems fail when they treat the LLM as a "generalist box." LCF provides the rigor to separate **Structural Alignment** from **Cognitive Reasoning**, ensuring each component of your system is powered by a model matched to its functional requirements.

---

## 🏗 The 6-Layer Architecture

LCF categorizes every AI task into a specific capability layer. This allows architects to select models based on **Instruction Adherence**, **Reasoning Depth**, and **Contextual Breadth**.

| Layer  | Name               | Requirement Focus                         | Ideal Model Class      |
| ------ | ------------------ | ----------------------------------------- | ---------------------- |
| **L1** | **Extraction**     | Deterministic mapping; noise suppression. | 4B-14B Distilled       |
| **L2** | **Transformation** | Format/Language/Style conversion.         | 8B-32B General         |
| **L3** | **Interpretation** | Intent, Sentiment, and Classification.    | 14B-70B Logic-heavy    |
| **L4** | **Synthesis**      | Cross-context data merging.               | 70B+ Frontier          |
| **L5** | **Communication**  | Persona consistency & human nuance.       | 32B+ Fine-tuned        |
| **L6** | **Agency**         | Recursive decomposition & tool-use.       | o1/o3 Reasoning models |

---

## 🛡 Core Philosophy: Role-Based Orchestration

While models are generalists, **LCF Agents** are specialists. The framework uses a modular role system to ensure reliability.

### The Foundation: The Scout & The Auditor

- **The Scout (Layer 1-2):** Optimized for **Fidelity**. Its goal is to move and format data without "thinking" or interpreting. It is a literalist.
- **The Auditor (Layer 4/6):** Optimized for **Logic**. It takes the structured output of the Scout and verifies it against complex organizational policies or logic constraints.

### Role Expansion

The framework is extensible. Depending on your scenario, you may implement:

- **The Architect (L6):** Decomposes complex user goals into sub-tasks.
- **The Editor (L5):** Refines raw synthesis into brand-compliant communication.

---

## ⚡ Layer 1: Data Extraction (The Standard)

Layer 1 is the **Normalization Layer**. It eliminates the entropy of natural language by forcing it into a repeatable protocol (JSON, TOON, CSV, YAML, etc.).

[See extraction protocol details in [1_Capability_Layers/layer_1_extraction.md](1_Capability_Layers/layer_1_extraction.md)]

- **Objective:** Map unstructured noise to deterministic system inputs.
- **Metric:** **Schema Adherence Rate (SAR)** — The frequency of zero-deviation outputs.
- **Constraint:** Prohibits conversational fluff, summaries, or apologies.

---

## Layer 2: Transformation (The Translator)

**Role:** **Type B (The Engineer)** — Implementation-focused adaptation.

**Objective:** **Semantic Morphing** — Converting the "Zero-Entropy" JSON from Layer 1 into a specific target narrative or schema without losing fact-density.

[See transformation protocol details in [1_Capability_Layers/Layer_2_Translator.md](1_Capability_Layers/Layer_2_Translator.md)]

# Architectural Analysis: The Latency/Fidelity Trade-off

Through a multi-model "Mirror Test," we have validated a core tenet of the **LLM Capability Framework (LCF)**:
**Validation**
[See benchmark results and tests in [3_Evaluation_Benchmarks/the_translator_tests](3_Evaluation_Benchmarks/the_translator_tests)]

> **"Fidelity is a feature of persistence, not speed."**

### Key Findings:

1. **Gemini 3 Flash** (4s TTFT) outperformed **Qwen 3 Max** (2s TTFT) in **Semantic Retention (SRR)**.
2. The extra 2 seconds of latency in Gemini allowed the model to process the "Achievements" key, ensuring the **Guinness World Record** was preserved in the output.
3. **Claude 4.5 Haiku** (1.5s TTFT) remains the gold standard for **Auditing**, capable of identifying exactly where data was lost during the transformation phase.

### Final Framework Recommendation for Layer 2:

- **Primary:** Gemini 3 Flash (For production-grade fidelity).
- **Secondary:** Claude 4.5 Sonnet (For high-stylized professional prose).

---

## AI-Native Documentation

This repository includes:

- **`llms.txt`**: A machine-readable sitemap for AI coding assistants.
- **`.github/copilot-instructions.md`**: Architectural guardrails to maintain LCF standards during AI-assisted development.
