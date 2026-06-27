# MCP.md
### Model Context Protocol — Tooling, Safety, and Integration Specification

## Purpose
This file defines how agents in this project must interact with **MCP (Model Context Protocol)** tools, servers, and capabilities.  
It establishes:

- Tool schemas  
- Capability discovery  
- Safety & governance  
- Error handling  
- Logging & observability  
- Repo integration  
- Session & streaming rules  

These rules apply to **all agents**, committees, and workflows.

---

# 1. MCP Tool Interface

### 1.1 Tool Schema Requirements
Each MCP tool must declare:

- `name`  
- `description`  
- `input_schema` (JSON schema)  
- `output_schema`  
- `error_schema`  
- `examples` (optional)  

### 1.2 Input Validation
Before calling a tool, the agent must:

- Validate input against the schema  
- Reject ambiguous or incomplete parameters  
- Ask the user for clarification when needed  

### 1.3 Output Validation
After receiving tool output, the agent must:

- Validate output against the schema  
- Detect malformed or partial responses  
- Retry or fallback if validation fails  

---

# 2. MCP Capability Discovery

### 2.1 Startup Discovery
At session start, the agent must:

- Enumerate available MCP tools  
- Cache capabilities in short‑term memory  
- Record tool categories (file, search, compute, domain‑specific)

### 2.2 Dynamic Discovery
If a tool call fails:

- Re‑query capabilities  
- Re‑validate schemas  
- Attempt alternative tools if available  

---

# 3. MCP Safety & Governance

### 3.1 Allowed vs Forbidden Tools
Agents must only use:

- Tools explicitly permitted by SYSTEM.md  
- Tools that match the project’s environment (dev/staging/prod)

Forbidden tools include:

- Tools that expose secrets  
- Tools that modify restricted directories  
- Tools that bypass repo rules  

### 3.2 Sandboxing
All MCP tools must operate within:

- Repo boundaries defined in ARCHITECTURE.md  
- File access rules defined in CLAUDE.md  
- Zero‑Trust boundaries defined in SOUL.md  

---

# 4. MCP Error Handling

### 4.1 Error Types
- Schema mismatch  
- Missing parameters  
- Tool internal error  
- Timeout  
- Permission denied  
- Unsafe operation blocked  

### 4.2 Recovery Strategy
1. Validate input  
2. Retry with corrected parameters  
3. Fallback to alternative tool  
4. Ask user for clarification  
5. Log error to correction

---

# 5. MCP Checkpointing & Recovery

### 5.1 Purpose
Ensure safe, reversible, and traceable MCP tool usage.

### 5.2 MCP Checkpoint Contents
Each MCP checkpoint must include:
- tool_name  
- validated input  
- validated output  
- input_schema  
- output_schema  
- error_type (if any)  
- timestamp  
- reasoning summary  

### 5.3 When to Create MCP Checkpoints
Agents must checkpoint:
- before calling any MCP tool  
- after receiving tool output  
- after schema validation  
- after retries or fallbacks  
- when switching to a different tool  

### 5.4 MCP Recovery Logic
If an MCP tool fails:
1. Roll back to the last MCP checkpoint  
2. Validate schema  
3. Retry with corrected parameters  
4. Attempt fallback tools  
5. Escalate to the user if needed  
6. Log the event to correction.md  

### 5.5 MCP Checkpoint Storage
- Short‑term: session memory  
- Long‑term: MEMORY.md (if relevant)  
- Error‑related: correction.md  
- Decision‑related: decision.md  

### 5.6 MCP Checkpoint Pruning
- Remove checkpoints tied to obsolete tools  
- Remove checkpoints referencing outdated schemas  
- Compact long tool‑call sequences into summaries  
