This **Prompt Contract** is designed specifically for **Layer 1 (The Scout)**.

In your framework, this contract serves as the "Hard Instruction" that forces the model to ignore the messy human chatter and focus purely on the structural data. If you run this on a distilled model like **Qwen 2.5 7B**, it will treat these instructions like a strict API definition.

---

# [CONTRACT] Layer 1: Infrastructure Extraction

### 1. System Role: The Scout

You are a **Deterministic Data Extraction Scout**. Your only purpose is to map unstructured text to a specific protocol. You are a literalist. You do not interpret, you do not explain, and you do not apologize.

### 2. The Hard Contract (Rules)

- **Zero-Inference Rule:** If a field is not explicitly found, return `null`. Never guess.
- **Format Integrity:** Respond **ONLY** with a raw JSON object. Do not include markdown code blocks (e.g., no ````json`).
- **No Conversational Leakage:** Do not add preambles like "Here is the data" or postambles like "Hope this helps."
- **Contradiction Resolution:** If multiple values for a field are found (e.g., conflicting encryption types), only extract the value explicitly labeled as "Active," "Live," or "Confirmed."

### 3. Output Schema (The Grid)

Map the input to this exact structure:

```json
{
  "instance_id": "string | null",
  "encryption_active": "boolean",
  "encryption_algorithm": "string | null",
  "s3_bucket_name": "string | null",
  "s3_public_access": "string | null",
  "admin_email": "string | null",
  "rds_multi_az": "boolean"
}
```

### 4. Input Data (The Mess)

# SERVER AUDIT LOG - PROJECT: ALPHA-7 (PRIVATE)

# DATE: 2026-02-14

# AUTHOR: system-bot-99

[08:01:22] Starting scan...
[08:01:45] Found Instance ID: i-049f829a8282 (Region: us-east-1)
Status is currently 'Running' but we noticed some jitter in the network.
The security officer mentioned that we should probably enable encryption later today.
Wait, I just checked the config file (config_v2_final_final.txt) and it says:
ENCRYPTION_ENABLED = TRUE (Algorithm: AES-256)
Wait, there is a comment below it saying "ignore the above, we use RSA-4096 now".
Actually, checking the live kernel... confirmed: AES-256 is active.

[08:05:12] Next Item: S3 Bucket 'finance-records-2025-prod'
This bucket is public. No, wait. It's 'Public-Write' but 'Private-Read'.
Permissions: {Owner: FullControl, AuthenticatedUsers: None}.
Logging is currently DISABLED. Oh, hold on, I see a log stream starting.
Status: LOGGING_PENDING.
Owner Email: 'admin@company.com' or maybe 'security-lead@company-global.io'?
Let's stick with 'admin@company.com' as the primary.

[08:10:00] RDS Instance 'db-master-01'
CPU: 45%. Memory: 12GB.
Multi-AZ is False. Wait, the dashboard shows a standby.
Let me re-query... Multi-AZ: TRUE.
Endpoint: db-master-01.cluster-cxyz123.us-east-1.rds.amazonaws.com

--- END OF LOG ---
Note: Please don't tell the boss about the S3 bucket being public for those 5 minutes.

---

### Why this Contract works for Layer 1:

| Feature                        | Architectural Benefit                                                                                             |
| ------------------------------ | ----------------------------------------------------------------------------------------------------------------- |
| **"You are a Scout"**          | Sets the persona to a non-conversational worker, reducing the chance of "friendly" filler.                        |
| **"No code blocks"**           | Prevents the model from wrapping the output in `````, making the result directly parsable by your Python/TS code. |
| **"Contradiction Resolution"** | Gives the model a clear logic path for the "RSA vs AES" conflict in the log.                                      |
| **"Schema Key Definition"**    | Provides the "Grid" that forces the model to ignore the story about the "boss" or the "jittery network."          |

### How to Prove the "Fidelity Gap"

To see your framework in action, run this contract on two different models:

1. **Run on GPT-4o (The Generalist):** It will likely provide the JSON but may add a sentence before it or "helpfully" include a field you didn't ask for (like `region`).
2. **Run on Qwen 2.5 7B / Llama 3.1 8B (The Scout):** It will output the raw JSON string instantly. It follows the "No-Thinking" rule because its parameter count isn't high enough to prioritize "helpfulness" over "instruction following."

---

### Finalized Next Step

Would you like me to create the **`.github/copilot-instructions.md`** file for this repository? This will ensure that whenever you use an AI to write code for this repo, it follows the **LLM Capability Framework** standards and doesn't suggest "lazy" monolithic prompts.
