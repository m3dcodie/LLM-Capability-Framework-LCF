# LLM Capability Framework (LCF)

**Stop over-paying for intelligence.** The LLM Capability Framework (LCF) is an architectural standard for mapping tasks to the most efficient model, token strategy, and reasoning layer.

In a 2026 production environment, "Vibe Coding" isn't enough. LCF provides the structural rigor needed to build reliable, cost-effective agentic systems by separating **Structural Alignment** from **Cognitive Reasoning**.

---

## 📖 Table of Contents

- [The 6-Layer Architecture](https://www.google.com/search?q=%23-the-6-layer-architecture)
- [Core Philosophy: The Scout & The Auditor](https://www.google.com/search?q=%23-core-philosophy)
- [Layer 1: Data Extraction](https://www.google.com/search?q=%23-layer-1-data-extraction)
- [Multi-Step Patterns](https://www.google.com/search?q=%23-multi-step-patterns)
- [AI-Native Integration (llms.txt)](https://www.google.com/search?q=%23-ai-native-integration)
- [Contributing](https://www.google.com/search?q=%23-contributing)

---

## 🏗 The 6-Layer Architecture

Every LLM task fits into one primary capability layer. By identifying the layer, you can choose the correct model parameter count and reasoning mode.

| Layer  | Name               | Primary Objective                      | Ideal Model Class      |
| ------ | ------------------ | -------------------------------------- | ---------------------- |
| **L1** | **Extraction**     | Unstructured Structured mapping.       | 4B-14B Distilled       |
| **L2** | **Transformation** | Format/Language/Style conversion.      | 8B-32B General         |
| **L3** | **Interpretation** | Intent, Sentiment, and Classification. | 14B-70B Logic-heavy    |
| **L4** | **Synthesis**      | Merging disparate data points.         | 70B+ Frontier          |
| **L5** | **Communication**  | Persona-driven human interaction.      | 32B+ Fine-tuned        |
| **L6** | **Agency**         | Recursive decomposition & tool-use.    | o1/o3 Reasoning models |

---

## 🛡 Core Philosophy

### The Scout & The Auditor

LCF mandates a separation of concerns.

- **The Scout (Layer 1):** A small, fast model (e.g., Qwen 2.5 Coder) focused on **Fidelity**. It moves data without thinking.
- **The Auditor (Layer 4/6):** A large, deep model (e.g., Claude 3.5 Sonnet) focused on **Logic**. It checks the Scout's work against organizational policy.

---

## ⚡ Layer 1: Data Extraction

Layer 1 is the **Normalization Layer**. It eliminates the entropy of natural language by forcing it into a repeatable structure (JSON, TOON, CSV, etc.).

### Key Principles

- **Literalism:** No grammar fixes, no commentary.
- **Format-Agnostic:** While JSON is the default, LCF supports **TOON** (Token-Oriented) for 40% cost reduction in high-volume tasks.
- **Constraint Compliance:** Hard adherence to [Prompt Contracts](https://github.com/m3dcodie/prompt-contract).

---

## 🔄 Multi-Step Patterns

LCF provides standardized execution patterns for high-reliability scenarios:

1. **Sequential Pipeline (Scout-Auditor):** High reliability for infrastructure and legal audits.
2. **Consensus Swarm:** Three small models voting on extraction to achieve "Frontier-level" accuracy at 1/10th the cost.
3. **Reflexive Loop:** Automatic self-correction when syntax validation (Pydantic/CSV Lint) fails.

---

## 🤖 AI-Native Integration

This repository is optimized for **AI Coding Agents** (Cursor, Windsurf, GitHub Copilot).

- **`llms.txt`**: A machine-readable sitemap for agents.
- **`.github/copilot-instructions.md`**: Best practices for AI contributors to ensure code stays within framework boundaries.

---

## 🤝 Contributing

We welcome contributions to the **Pattern Library** and **Fidelity Benchmarks**.

1. Review the [Layer 1 Standard](https://www.google.com/search?q=./1_Capability_Layers/layer_1_extraction.md).
2. Open a PR with your architectural pattern or model benchmark.
