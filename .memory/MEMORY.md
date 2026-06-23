# MEMORY.md  
### Long‑Term Memory, Context Compaction & MCP Retention

## Memory Schema
[Fill in]

## Retention Rules
[Fill in]

## Retrieval Logic
[Fill in]

## Context Compaction Rules
[Fill in]

## MCP Tool Result Retention
- What MCP outputs may be stored  
- What must be discarded  
- How to tag MCP‑derived memory  

## Checkpoint Retention & Compaction

### Purpose
Define how checkpoints are stored, pruned, and retrieved to support safe long‑term reasoning.

### Retention Rules
- Keep only the latest stable checkpoint for each task  
- Keep at most N historical checkpoints (configurable)  
- Discard checkpoints tied to expired or irrelevant tasks  
- Never store sensitive or forbidden data  

### Retrieval Logic
When retrieving checkpoints:
- Prefer the most recent valid checkpoint  
- Validate against SYSTEM.md and MCP.md  
- Reconstruct context using:  
  - goals  
  - constraints  
  - decisions  
  - tool outputs  
  - unresolved questions  

### Compaction Rules
- Merge adjacent checkpoints when possible  
- Summarize long chains into a single compact checkpoint  
- Remove redundant or low‑value details  
- Tag MCP‑derived checkpoints for special handling  

### MCP‑Aware Checkpointing
- MCP tool results must be checkpointed before pruning  
- MCP errors must create a checkpoint entry in correction.md  
- MCP schema changes must invalidate outdated checkpoints  
