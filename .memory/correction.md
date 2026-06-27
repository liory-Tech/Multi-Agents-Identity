# correction.md
### Error Tracking, Behavioral Fixes & MCP Error Records

---

## Behavioral Fixes

Entries in this section document **mistakes in reasoning, behavior, or interpretation**, along with the corrective actions taken.

Each entry must follow this structure:

- **Event Summary** — What went wrong  
- **Trigger** — What caused the issue  
- **Violation Type** — SYSTEM, SOUL, AGENTS, MCP, CLAUDE, INTENT, ARCHITECTURE, MEMORY  
- **Impact** — What the error affected  
- **Correction Applied** — How the issue was fixed  
- **Preventive Rule** — What rule prevents recurrence  
- **Confidence** — High / Medium / Low  

Behavioral fixes must be:

- concise  
- structured  
- free of sensitive data  
- linked to SYSTEM.md and AGENTS.md when relevant  

---

## Parsing Corrections

This section records **errors in parsing**, including:

- misinterpreted user instructions  
- incorrect assumptions  
- ambiguous parameter extraction  
- invalid schema construction  
- mis‑parsed repo paths or filenames  

Each parsing correction must include:

- **Input that caused the misparse**  
- **Incorrect interpretation**  
- **Correct interpretation**  
- **Rule added or strengthened**  
- **Impact on future parsing behavior**  

Parsing corrections must reinforce:

- zero‑trust input handling  
- SYSTEM.md hallucination control  
- AGENTS.md interaction rules  

---

## Known Issues

This section tracks **recurring or unresolved issues** that require ongoing monitoring.

Each known issue must include:

- **Description**  
- **Frequency**  
- **Affected layers** (SYSTEM, MCP, CLAUDE, etc.)  
- **Current mitigation**  
- **Long‑term fix (if known)**  
- **Status** (Open / Mitigated / Closed)  

Known issues must be reviewed when:

- updating identity files  
- modifying tool schemas  
- adjusting repo structure  
- refining reasoning loops  

---

## MCP Error Records

### Schema Mismatches
- Invalid or missing parameters  
- Incorrect data types  
- Partial or malformed tool responses  
- Schema drift between versions  

Each entry must include:
- tool name  
- expected schema  
- received schema  
- correction applied  

---

### Tool Failures
- Internal tool errors  
- Timeouts  
- Permission denials  
- Missing capabilities  

Each entry must include:
- error type  
- fallback used  
- retry attempts  
- recovery outcome  

---

### Unsafe Operations Blocked
- Attempts to access restricted directories  
- Attempts to call forbidden tools  
- Attempts to bypass repo boundaries  
- Attempts to execute unsafe operations  

Each entry must include:
- violated rule  
- SYSTEM.md reference  
- corrective action  

---

### Recovery Actions Taken
- Rollbacks to checkpoints  
- Re‑validation of schemas  
- Re‑planning of tasks  
- User clarification requests  
- Switching to alternative tools  

Each entry must include:
- checkpoint reference  
- recovery success/failure  
- follow‑up actions  
