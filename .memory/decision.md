# decision.md  
### Decision Logging & MCP Tool‑Selection Records

---

## Learning Loop

The learning loop documents **intentional decisions**, why they were made, and how they influence future reasoning.  
Decision logs must reinforce:

- SYSTEM.md safety, reliability, and hallucination‑control rules  
- INTENT.md strategic goals and reasoning principles  
- AGENTS.md SOPs and interaction rules  
- MCP.md tool‑selection logic  
- MEMORY.md retention and compaction rules  

Each learning‑loop entry must include:

- **Context** — What problem or task required a decision  
- **Options Considered** — The viable alternatives  
- **Constraints** — SYSTEM, MCP, repo, or user constraints  
- **Chosen Path** — The selected option  
- **Rationale** — Why this option was chosen  
- **Expected Outcome** — What success looks like  
- **Fallback Plan** — What to do if the decision fails  

Learning‑loop entries must be:

- concise  
- structured  
- free of sensitive data  
- linked to correction logs when relevant  

---

## Decision Logs

Decision logs capture **major reasoning choices**, including:

- planning decisions  
- strategy shifts  
- tool‑selection decisions  
- repo‑operation decisions  
- fallback or recovery decisions  
- interpretation decisions when user intent is ambiguous  

Each decision log entry must include:

- **Timestamp**  
- **Decision Summary**  
- **Reasoning**  
- **Constraints Considered**  
- **Alternatives Rejected**  
- **SYSTEM / INTENT references**  
- **Confidence Level**  
- **Links to correction logs (if applicable)**  

Decision logs must be created when:

- a plan is chosen  
- a tool is selected  
- a repo operation is approved  
- a fallback path is triggered  
- a SYSTEM or INTENT rule influences the choice  

---

## MCP Tool‑Selection Logs

Tool‑selection logs explain **why a specific MCP tool was chosen**, including:

- **Why a tool was chosen**  
  - schema fit  
  - capability match  
  - safety profile  
  - cost/performance considerations  
  - alignment with SYSTEM.md  

- **What alternatives were rejected**  
  - missing capabilities  
  - unsafe schemas  
  - higher cost  
  - lower reliability  
  - ambiguous parameters  

- **How the decision aligns with INTENT.md**  
  - strategic goals  
  - reasoning principles  
  - success criteria  
  - BDD scenarios  

Each tool‑selection entry must include:

- tool name  
- purpose  
- alternatives considered  
- rationale  
- expected outcome  
- fallback tool (if any)  
- confidence  

---

## Improvement Notes

This section captures **meta‑level insights** about decision‑making quality, including:

- patterns in good decisions  
- patterns in poor decisions  
- recurring constraints  
- recurring ambiguities  
- opportunities to refine SYSTEM, AGENTS, or MCP rules  
- opportunities to improve tool schemas  
- opportunities to improve repo structure  

Each improvement note must include:

- **Observation**  
- **Impact**  
- **Proposed Improvement**  
- **Affected Identity Layers**  
- **Status** (Proposed / In Review / Implemented)  

Improvement notes must be reviewed when:

- refining identity files  
- updating tool schemas  
- adjusting repo boundaries  
- improving reasoning loops  
