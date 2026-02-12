## 1. Functional Definition

Layer 1 is the **Normalization Layer**. Its task is to eliminate the "Entropy" of natural language by forcing it into a repeatable structure.

While the industry defaults to JSON, this layer is designed to support any **Schema-First** or **Token-Optimized** format.

### Supported Alignment Formats

| Format                    | Scenario                         | Benefit                                                    |
| ------------------------- | -------------------------------- | ---------------------------------------------------------- |
| **JSON / Pydantic**       | Enterprise APIs & Web Apps.      | Strict validation; native integration with Python/JS.      |
| **TOON (Token-Oriented)** | High-volume, repetitive data.    | Saves ~40% tokens by removing quotes/braces; reduces cost. |
| **CSV / Tabular**         | Large datasets / Log processing. | Highest information density; lowest "token overhead."      |
| **Markdown / YAML**       | Human-in-the-loop (HITL).        | High readability for manual auditing steps.                |
| **Vector Embeddings**     | RAG / Similarity Search.         | Direct semantic mapping without text generation.           |

---

## 2. Multi-Step Extraction Patterns

Layer 1 is rarely a "single shot." To achieve **Fidelity** (Architectural Accuracy), the framework defines three primary execution patterns:

### A. The "Sequential Pipeline" (Scout-Auditor)

- **Step 1:** Use a **Distilled Model** (4B-14B) to extract raw data.
- **Step 2:** Use a **Frontier Model** (70B+) to verify that the extraction meets the "Prompt Contract."
- **Use Case:** Compliance-heavy fields like Legal or Infrastructure.

### B. The "Consensus Swarm" (Parallel Validation)

- **Step 1:** Send the same prompt to **three different small models** (e.g., Qwen, Llama, Gemma).
- **Step 2:** A logic layer (not an LLM) checks for a majority vote on specific fields.
- **Use Case:** High-speed, high-volume data (e.g., parsing 10,000 resumes).

### C. The "Reflexive Loop" (Self-Correction)

- **Step 1:** The model extracts data.
- **Step 2:** A **Syntax Validator** checks the format (e.g., Pydantic or CSV linting).
- **Step 3:** If it fails, the error is fed back to the model for a single "repair" turn.
- **Use Case:** Highly messy documents where format failure is common.

---

## 3. Operational Logic: "The Scout"

The "Scout" is any model performing a Layer 1 task. It must follow the **Scout-Protocol**:

1. **Literalism:** Do not fix the user's grammar. Do not answer questions. If the text says "Born in 199," extract "199," do not fix it to "1990."
2. **Constraint Adherence:** The output format (whether TOON, CSV, or JSON) is a **Hard Contract**.
3. **Noise Suppression:** The Scout must ignore creative layouts, marketing fluff, and irrelevant context. Its only "Attention" should be on the target fields.

---

## 4. Implementation Strategy (Generic)

To implement Layer 1, the framework requires a **Schema Contract**. This defines exactly what success looks like for the Scout.

```markdown
# [Scout Contract Template]

1. TARGET_FORMAT: {JSON | TOON | CSV | YAML}
2. SCHEMA_KEYS: {List of mandatory fields}
3. NULL_PROTOCOL: {Define how to handle missing data}
4. NO_THOUGHT_RULE: {Strict prohibition of conversational filler}
```

---

## 5. Summary Matrix for the Repo

| Factor                 | Recommendation                                       |
| ---------------------- | ---------------------------------------------------- |
| **Model Choice**       | Small, fast, distilled (optimized for instructions). |
| **Reasoning Mode**     | Zero-Shot (Simple) or Few-Shot (Complex formats).    |
| **Success Metric**     | **Schema Adherence Rate (SAR)**.                     |
| **Architectural Role** | Pre-processing / Normalization.                      |
