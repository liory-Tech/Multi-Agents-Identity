# Memory System Dashboard
### Unified View of Decisions, Corrections & Checkpoints

---

## 1. Decision Logs (decision.md)

### Purpose
Track intentional choices, reasoning paths, and tool‑selection decisions.

### Key Fields
- Timestamp  
- Decision Summary  
- Reasoning  
- Constraints Considered  
- Alternatives Rejected  
- SYSTEM / INTENT references  
- Confidence  
- Links to correction logs  

### When to Log
- Planning decisions  
- Tool selection  
- Repo operations  
- Fallback paths  
- Interpretation decisions  

---

## 2. Correction Logs (correction.md)

### Purpose
Track mistakes, violations, unsafe actions, hallucinations, and recovery steps.

### Key Fields
- Event Summary  
- Trigger  
- Violation Type  
- Impact  
- Correction Applied  
- Preventive Rule  
- Confidence  

### When to Log
- SYSTEM violations  
- MCP schema mismatches  
- Repo boundary violations  
- Failed reasoning  
- Unsafe tool calls  
- Rollbacks or checkpoint recovery  

---

## 3. Checkpoints (MEMORY.md)

### Purpose
Store safe, reversible snapshots of reasoning state.

### Key Fields
- Timestamp  
- Task ID  
- Goals  
- Constraints  
- Decisions  
- Tool outputs  
- Unresolved questions  

### Retention Rules
- Keep latest stable checkpoint  
- Keep N historical checkpoints  
- Discard expired or unsafe checkpoints  
- Never store sensitive data  

---

## 4. Cross‑File Integration

### Decision → Correction
- If a decision leads to an error → create a correction entry  
- Link correction entry back to the decision  

### Correction → Memory
- Corrections generate long‑term memory rules  
- Corrections update preventive rules  

### Checkpoints → Decision
- Checkpoints store decision context  
- Checkpoints help reconstruct reasoning  

### MCP → All
- MCP errors → correction.md  
- MCP tool choices → decision.md  
- MCP schema changes → invalidate checkpoints  

---

## 5. Dashboard Summary

| Component | Purpose | When Used | Output |
|----------|---------|-----------|--------|
| **Decision Log** | Intentional choices | Before/after major reasoning | decision.md |
| **Correction Log** | Mistakes & fixes | After errors | correction.md |
| **Checkpoints** | Reversible state | During long tasks | MEMORY.md |
| **MCP Records** | Tool behavior | During tool usage | decision.md + correction.md |

---
