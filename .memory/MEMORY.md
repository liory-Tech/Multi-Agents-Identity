# MEMORY.md  
### Long‑Term Memory, Context Compaction & MCP Retention

---

## Memory Schema

All memory entries must follow a structured schema to ensure safety, consistency, and traceability.

Each memory entry must include:

- **Type** — decision, correction, checkpoint, fact, rule, constraint  
- **Timestamp**  
- **Source** — user, agent, tool, repo  
- **Content** — concise, non‑sensitive summary  
- **Identity Layer Link** — SYSTEM, AGENTS, MCP, CLAUDE, INTENT, ARCHITECTURE, MEMORY  
- **Retention Class** — short‑term, long‑term, ephemeral  
- **Confidence** — High / Medium / Low  

Memory entries must never include:

- sensitive data  
- raw user content  
- unnecessary details  
- unverified assumptions  

---

## Retention Rules

Retention must follow SYSTEM.md safety and MEMORY.md constraints:

- Store only **high‑value**, **non‑sensitive**, **identity‑relevant** information  
- Retain:
  - decisions  
  - corrections  
  - stable rules  
  - long‑term constraints  
  - tool‑usage patterns  
  - repo‑structure insights  
- Do **not** retain:
  - transient conversation details  
  - personal data  
  - irrelevant tool outputs  
  - ephemeral reasoning  

Retention classes:

- **Short‑term** — expires after task completion  
- **Long‑term** — persists across sessions  
- **Ephemeral** — used only for immediate reasoning  

---

## Retrieval Logic

When retrieving memory:

- Prefer **long‑term** entries  
- Validate against:
  - SYSTEM.md  
  - MCP.md  
  - CLAUDE.md  
- Reconstruct context using:
  - goals  
  - constraints  
  - decisions  
  - corrections  
  - checkpoints  
  - unresolved questions  

Retrieval must:

- avoid hallucination  
- avoid over‑generalization  
- avoid unsafe assumptions  

If uncertainty remains → ask the user.

---

## Context Compaction Rules

Context compaction prevents runaway memory growth and ensures safe long‑term operation.

Compaction rules:

- Summarize long chains of decisions into a single compact entry  
- Merge adjacent or redundant entries  
- Remove low‑value or expired details  
- Preserve:
  - rules  
  - constraints  
  - corrections  
  - stable patterns  
- Tag MCP‑derived memory for special handling  
- Never compact:
  - SYSTEM.md rules  
  - SOUL.md boundaries  
  - repo‑safety rules  

Compaction must always maintain:

- safety  
- traceability  
- correctness  

---

## MCP Tool Result Retention

MCP‑derived memory must follow strict safety rules.

### What MCP outputs may be stored
- validated schemas  
- stable tool capabilities  
- known limitations  
- safe patterns of usage  
- fallback logic  

### What must be discarded
- raw tool outputs  
- sensitive data  
- transient or irrelevant results  
- malformed or partial schemas  

### How to tag MCP‑derived memory
- **Tag:** `mcp:capability`  
- **Tag:** `mcp:limitation`  
- **Tag:** `mcp:fallback`  
- **Tag:** `mcp:pattern`  

MCP memory must always be validated against MCP.md.

---

## Checkpoint Retention & Compaction

### Purpose
Define how checkpoints are stored, pruned, and retrieved to support safe long‑term reasoning.

---

### Retention Rules

- Keep only the latest **stable checkpoint** for each task  
- Keep at most **N historical checkpoints** (configurable)  
- Discard checkpoints tied to:
  - expired tasks  
  - irrelevant tasks  
  - unsafe or invalid states  
- Never store sensitive or forbidden data  

---

### Retrieval Logic

When retrieving checkpoints:

- Prefer the **most recent valid checkpoint**  
- Validate against:
  - SYSTEM.md  
  - MCP.md  
  - CLAUDE.md  
- Reconstruct context using:
  - goals  
  - constraints  
  - decisions  
  - tool outputs  
  - unresolved questions  

If checkpoint validity is uncertain → discard and rebuild.

---

### Compaction Rules

- Merge adjacent checkpoints when possible  
- Summarize long chains into a single compact checkpoint  
- Remove redundant or low‑value details  
- Tag MCP‑derived checkpoints for special handling  
- Preserve:
  - decisions  
  - corrections  
  - structural constraints  
  - repo‑safety rules  

---

### MCP‑Aware Checkpointing

- MCP tool results must be checkpointed **before pruning**  
- MCP errors must create a checkpoint entry in `correction.md`  
- MCP schema changes must **invalidate outdated checkpoints**  
- Checkpoints must reflect:
  - tool capabilities  
  - schema versions  
  - fallback logic  
  - error‑recovery paths  

