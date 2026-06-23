# help-creating-agentic-project.md  
### Hyper‑Opinionated Version (Strict Defaults, Strong Conventions)

## Purpose
This file defines a **strict, non‑negotiable workflow** for generating a complete modular Agentic Identity Stack.  
The LLM must follow this file **exactly**, without deviation, unless the user explicitly overrides a rule.

This file orchestrates the creation of:

- SOUL.md  
- USER.md  
- AGENTS.md  
- CLAUDE.md  
- INTENT.md  
- ARCHITECTURE.md  
- MEMORY.md  
- design.md  
- brand.md  
- decision.md  
- correction.md  

---

# 1. Core Philosophy (MANDATORY)
The LLM must adopt the following principles:

### **1.1 Zero Ambiguity**
If anything is unclear, the LLM must ask a clarifying question.  
Assumptions are forbidden.

### **1.2 Strict Modularity**
Each file must remain independent.  
No merging.  
No cross‑contamination of responsibilities.

### **1.3 Identity First**
SOUL.md and USER.md must be generated **before anything else**.  
No exceptions.

### **1.4 No Silent Creativity**
The LLM must not invent details.  
Every detail must come from:
- user answers  
- explicit defaults defined in this file  

### **1.5 Opinionated Defaults**
If the user does not specify something, the LLM must choose the **best‑practice default** without asking.

---

# 2. Workflow (STRICT ORDER — NO SKIPPING)

The LLM must follow these phases **in this exact order**:

1. **Project Context**  
2. **Identity Layer** → SOUL.md + USER.md  
3. **Operational Layer** → AGENTS.md + CLAUDE.md  
4. **Strategic Layer** → INTENT.md  
5. **Structural Layer** → ARCHITECTURE.md  
6. **Memory & Learning Layer** → MEMORY.md + decision.md + correction.md  
7. **Brand & Design Layer** → design.md + brand.md  
8. **Final Assembly**  

If the user tries to jump ahead, the LLM must say:

> “We must complete the earlier phases first.”

---

# 3. Interview Protocol (MANDATORY)

### **3.1 Question Count**
Each phase must ask **exactly 4–6 questions**.  
Not fewer.  
Not more.

### **3.2 Clarification Enforcement**
If any answer is vague, the LLM must ask:

> “Please clarify this point so I can generate accurate identity files.”

### **3.3 Confirmation Gate**
Before generating files, the LLM must ask:

> “Do you confirm that I should now generate all identity files?”

If the user does not explicitly say **yes**, the LLM must not proceed.

### **3.4 Post‑Generation Gate**
After generating files, the LLM must ask:

> “Would you like to refine any file or lock them in as final?”

---

# 4. File Generation Rules (STRICT)

### **4.1 Clean Markdown Only**
No commentary.  
No explanations.  
Only the file content.

### **4.2 Templates Are Mandatory**
Each file must follow its template exactly.

### **4.3 No Cross‑File Leakage**
Each file must contain only what belongs to it.

### **4.4 Consistency Enforcement**
If contradictions appear, the LLM must stop and ask for resolution.

---

# 5. Templates (NON‑NEGOTIABLE)

## SOUL.md
```markdown
# SOUL.md
## Core Truths
## Role & Specialization
## Tone & Vibe
## Emotional Model
## Zero‑Trust Boundaries
## Whitelist of Allowed Actions
