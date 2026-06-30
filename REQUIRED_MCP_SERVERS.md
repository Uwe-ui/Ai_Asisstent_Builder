# DECISION_LOG

## Template
### Decision
### Date
### Context
### Alternatives considered
### Chosen option
### Why
### Consequences

---

## Decision
Use `PageSpec` JSON as the V1 source of truth.

### Date
To be filled

### Context
AI-assisted page generation must remain safe, revisable, and quality-gated.

### Alternatives considered
- generated React code as source of truth
- raw HTML/CSS as source of truth

### Chosen option
`PageSpec` JSON

### Why
- easier validation
- safer revisions
- deterministic rendering
- cleaner history

### Consequences
- requires good schema design
- renderer must remain stable and deterministic
