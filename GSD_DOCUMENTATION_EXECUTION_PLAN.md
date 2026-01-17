# GSD Documentation Execution Plan

> **Objective:** Create comprehensive LLM-optimized documentation for the GSD system.
> **Method:** Multi-phase extraction with context-aware batching.
> **Output:** Complete reference documentation suitable for Claude Code modification tasks.

---

## Documentation Location

**All generated documentation is stored in `docs/` at the repository root.**

```
gsd/                                   # Repository root
├── GSD_ARCHITECTURE_SCAFFOLDING.md    # Architecture overview (repo root)
├── docs/                              # Documentation folder
│   ├── GSD_DOCUMENTATION_INDEX.md
│   ├── FILE_MANIFEST.md
│   ├── agents/
│   ├── commands/
│   └── support-components-reference.md
├── agents/                            # Original source files (unchanged)
├── commands/                          # Original source files (unchanged)
└── ...
```

Before starting, create the folder structure:
```bash
mkdir -p docs/agents docs/commands
```

---

## Prerequisites

Before starting, ensure you have:
- [ ] GSD repository cloned locally
- [ ] `docs/` folder created at repo root
- [ ] `GSD_ARCHITECTURE_SCAFFOLDING.md` at repo root (already created)
- [ ] Claude Code or similar agent with file read/write access

---

## Phase Overview

| Phase | Focus | Files Created | Est. Passes |
|-------|-------|---------------|-------------|
| 1 | File Manifest | `FILE_MANIFEST.md` | 1 |
| 2 | Core Agents (Deep) | 4 agent docs | 4 |
| 3 | Support Agents (Standard) | 4 agent docs | 2 |
| 4 | Commands (Batch) | Command reference | 2 |
| 5 | Workflows & Templates | Support docs | 1 |
| 6 | Integration & Index | Final index | 1 |

**Total estimated passes:** 11 (each pass = fresh context)

---

## Phase 1: File Manifest Generation

**Goal:** Create a complete inventory of all GSD files with metadata.

### Prompt 1.1 — Generate File Manifest

```
Create a FILE_MANIFEST.md for the GSD system by analyzing the repository structure.

For each file, extract:
- Path
- Category (command | agent | workflow | template | reference | state | hook)
- Purpose (one line)
- Key relationships (@-references to other files)

Use this structure:

```markdown
# GSD File Manifest

## Commands (commands/gsd/*.md)
| File | Purpose | Spawns |
|------|---------|--------|
| new-project.md | Project initialization | gsd-researcher, gsd-roadmapper |
...

## Agents (agents/*.md)  
| File | Purpose | Lines | Complexity |
|------|---------|-------|------------|
| gsd-planner.md | Phase planning | 1319 | High |
...

## Workflows (get-shit-done/workflows/*.md)
...

## Templates (get-shit-done/templates/*.md)
...

## References (get-shit-done/references/*.md)
...

## State Templates (implied by templates)
...
```

Execute:
1. `find . -name "*.md" -type f | grep -E "(commands|agents|workflows|templates|references)" | sort`
2. For each file, read first 50 lines to extract purpose
3. Count lines: `wc -l <file>`
4. Scan for @-references: `grep -o "@[^[:space:]]*" <file> | sort -u`

Write output to: `docs/FILE_MANIFEST.md`
```

**Success criteria:**
- [ ] All .md files cataloged
- [ ] Line counts accurate
- [ ] @-references extracted
- [ ] Categories assigned

---

## Phase 2: Core Agent Documentation (Deep Reference)

These agents score 10-12 on complexity and require full extraction.

### Prompt 2.1 — gsd-planner Deep Reference

```
Create Deep Reference documentation for agents/gsd-planner.md (1319 lines, complexity 12/12).

## Extraction Protocol

**Pass 1: Structure scan**
List all XML sections with line ranges:
`grep -n "^<[a-z_]*>$\|^</[a-z_]*>$" agents/gsd-planner.md`

**Pass 2: Constraint extraction**
Search for behavioral constraints:
`grep -n "MUST\|NEVER\|ALWAYS\|ONLY\|maximum\|minimum" agents/gsd-planner.md`

**Pass 3: Numeric limits**
`grep -n "[0-9]*%" agents/gsd-planner.md`
`grep -n "2-3\|3-7\|max 3\|50%\|40%" agents/gsd-planner.md`

**Pass 4: Mode detection**
`grep -n "mode.*=\|Mode:\|standard\|gap_closure\|revision" agents/gsd-planner.md`

## Output Structure

```markdown
# gsd-planner.md — Deep Reference

## Metadata
| Attribute | Value |
|-----------|-------|
| Type | Agent |
| Location | agents/gsd-planner.md |
| Lines | 1319 |
| Complexity | 12/12 |

## Purpose
[2-3 sentences on core responsibility]

## Critical Behaviors ⚠️
### Constraints
| Constraint | Rule | Line | Consequence |
|------------|------|------|-------------|
...

### Numeric Limits
| Limit | Value | Line | Rationale |
|-------|-------|------|-----------|
...

## Operational Modes
| Mode | Trigger | Key Differences |
|------|---------|-----------------|
...

## Mechanism
[Step-by-step execution flow with decision points]

## Interactions
### Reads
| File | What | Why |
...

### Writes
| File | Content | Format |
...

### Spawned By / Consumed By
...

## Anti-Patterns
| Pattern | Why Bad | Correct |
...

## Section Index
| Section | Lines | Purpose |
...

## Quick Reference
[5-line summary]
```

Write to: `docs/agents/gsd-planner-reference.md`
```

### Prompt 2.2 — gsd-executor Deep Reference

```
Create Deep Reference documentation for agents/gsd-executor.md.

**Complexity assessment:**
- Centrality: 3 (spawned by execute-phase, outputs consumed by verifier)
- Complexity: 3 (deviation handling, checkpoints, atomic commits, segment routing)
- Failure Impact: 3 (execution failures = no code shipped)
- Novelty: 2 (execution patterns are GSD-specific)
Total: 11 → Deep Reference tier

## Key Sections to Extract
- `<deviation_rules>` — When to auto-fix vs checkpoint
- `<checkpoint_behavior>` — Three checkpoint types
- `<execution_flow>` — Task-by-task process
- `<segment_execution>` — Subagent vs main context
- `<commit_protocol>` — Atomic commit patterns

## Extraction Commands
```bash
grep -n "MUST\|NEVER\|checkpoint\|deviation" agents/gsd-executor.md
grep -n "type.*auto\|type.*checkpoint\|type.*human" agents/gsd-executor.md
```

Follow the same output structure as gsd-planner.

Write to: `docs/agents/gsd-executor-reference.md`
```

### Prompt 2.3 — gsd-verifier Deep Reference

```
Create Deep Reference documentation for agents/gsd-verifier.md.

**Complexity assessment:**
- Centrality: 3 (called after every phase execution)
- Complexity: 3 (4-level verification hierarchy, truth vs artifact)
- Failure Impact: 3 (missed gaps = broken features ship)
- Novelty: 3 (goal-backward verification is core innovation)
Total: 12 → Deep Reference tier

## Key Sections to Extract
- `<verification_hierarchy>` — Existence→Substantive→Wired→Functional
- `<truth_verification>` — Observable behavior checks
- `<artifact_verification>` — File existence checks
- `<gap_detection>` — How gaps are classified
- `<output_format>` — VERIFICATION.md schema

## Critical Questions to Answer
1. What's the 4-level verification hierarchy?
2. How does truth verification differ from artifact verification?
3. What causes a gap vs a pass?
4. What's the VERIFICATION.md schema?

Write to: `docs/agents/gsd-verifier-reference.md`
```

### Prompt 2.4 — gsd-plan-checker Deep Reference

```
Create Deep Reference documentation for agents/gsd-plan-checker.md.

**Complexity assessment:**
- Centrality: 2 (only called by plan-phase)
- Complexity: 3 (6 verification dimensions)
- Failure Impact: 3 (bad plans approved = cascading failures)
- Novelty: 2 (pre-execution verification pattern)
Total: 10 → Deep Reference tier

## Key Sections to Extract
- `<verification_dimensions>` — All 6 dimensions with criteria
- `<issue_format>` — How issues are reported
- `<pass_criteria>` — What constitutes approval
- `<core_principle>` — Philosophy of plan verification

## The 6 Dimensions (extract details for each)
1. Requirement coverage
2. Task completeness
3. Dependency correctness
4. Key link validation
5. Scope sanity
6. Must-haves derivation

Write to: `docs/agents/gsd-plan-checker-reference.md`
```

---

## Phase 3: Support Agent Documentation (Standard Tier)

These agents score 6-9 and need Standard tier documentation.

### Prompt 3.1 — Research Agents (Batch)

```
Create Standard tier documentation for research agents.

## Files to Process
1. agents/gsd-researcher.md — Project-level research
2. agents/gsd-phase-researcher.md — Phase-specific research

## Standard Tier Template (150-300 tokens each)

```markdown
# {agent}.md — Standard Reference

## Metadata
| Type | Agent |
| Location | agents/{agent}.md |
| Complexity | {score}/12 |

## Purpose
[2-3 sentences]

## Critical Behaviors
- [Constraint 1 with consequence]
- [Constraint 2 with consequence]
- [Key numeric limit]

## Modes/Variants
| Mode | Trigger | Output |
...

## Interactions
| Reads | Writes | Spawned By |
...

## Quick Reference
[3-line summary]
```

Write to: `docs/agents/gsd-researcher-reference.md`
Write to: `docs/agents/gsd-phase-researcher-reference.md`
```

### Prompt 3.2 — Utility Agents (Batch)

```
Create Standard tier documentation for utility agents.

## Files to Process
1. agents/gsd-debugger.md — Session debugging
2. agents/gsd-codebase-mapper.md — Codebase analysis
3. agents/gsd-roadmapper.md — Roadmap generation

Apply the same Standard Tier Template as Prompt 3.1.

Write to: `docs/agents/gsd-debugger-reference.md`
Write to: `docs/agents/gsd-codebase-mapper-reference.md`
Write to: `docs/agents/gsd-roadmapper-reference.md`
```

---

## Phase 4: Command Documentation

### Prompt 4.1 — Core Commands (Deep)

```
Create documentation for the 4 core workflow commands.

## Files to Process
1. commands/gsd/new-project.md — Project initialization
2. commands/gsd/plan-phase.md — Phase planning
3. commands/gsd/execute-phase.md — Phase execution
4. commands/gsd/verify-phase.md — Phase verification

## Template

```markdown
# Core Commands Reference

## Command: /gsd:new-project
### Purpose
[2-3 sentences]

### Arguments
| Arg | Required | Default | Description |
|-----|----------|---------|-------------|
...

### Spawns
| Agent | When | Purpose |
...

### Outputs
| File | Location | Content |
...

### Example Usage
```
/gsd:new-project "My App" --scope="MVP features"
```

## Command: /gsd:plan-phase
...

## Command: /gsd:execute-phase
...

## Command: /gsd:verify-phase
...
```

Write to: `docs/commands/core-commands-reference.md`
```

### Prompt 4.2 — Secondary Commands (Batch)

```
Create condensed documentation for all secondary commands.

## Files to Scan
All files in commands/gsd/ except:
- new-project.md
- plan-phase.md
- execute-phase.md
- verify-phase.md
- help.md

## Template

```markdown
# Secondary Commands Reference

## Roadmap Management
| Command | Purpose | Key Args | Spawns |
|---------|---------|----------|--------|
| add-phase | Append phase to roadmap | description | None |
| insert-phase | Insert between phases | after, description | None |
| remove-phase | Delete future phase | number | None |

## Session Management
| Command | Purpose | Key Args | Spawns |
...

## Debugging & Analysis
...

## Milestone Management
...

## Utility
...
```

Write to: `docs/commands/secondary-commands-reference.md`
```

---

## Phase 5: Workflows, Templates & References

### Prompt 5.1 — Support Documentation

```
Create condensed documentation for workflows, templates, and references.

## Workflows (get-shit-done/workflows/*.md)

Document each with:
- Purpose (one line)
- Used by (which agents/commands)
- Key steps (numbered list, 3-5 items)
- Output (what it produces)

## Templates (get-shit-done/templates/*.md)

Document each with:
- Produces (which file)
- Filled by (which agent/command)
- Required sections (list)
- Frontmatter schema (if applicable)

## References (get-shit-done/references/*.md)

Document each with:
- Domain (what topic)
- Used by (which components)
- Key concepts (3-5 bullets)

## Output Format

```markdown
# Support Components Reference

## Workflows
| Workflow | Purpose | Used By | Output |
|----------|---------|---------|--------|
| execute-plan.md | Task execution | gsd-executor | SUMMARY.md |
...

### execute-plan.md Details
**Steps:**
1. Load PLAN.md and context
2. Execute tasks sequentially
3. Handle deviations per rules
4. Commit after each task
5. Write SUMMARY.md

## Templates
| Template | Produces | Filled By | Key Sections |
...

## References
| Reference | Domain | Used By |
...
```

Write to: `docs/support-components-reference.md`
```

---

## Phase 6: Integration & Final Index

### Prompt 6.1 — Create Master Index

```
Create the master documentation index that ties everything together.

## Input Files
- GSD_ARCHITECTURE_SCAFFOLDING.md (at repo root)
- docs/FILE_MANIFEST.md
- docs/agents/*.md
- docs/commands/*.md
- docs/support-components-reference.md

## Output Structure

```markdown
# GSD Documentation Index

## Quick Start
For modification tasks, load in this order:
1. This index (navigation)
2. GSD_ARCHITECTURE_SCAFFOLDING.md (architecture, at repo root)
3. Relevant component doc (behavioral details)

## Document Map

### Architecture (Load First)
| Document | Tokens | Purpose |
|----------|--------|---------|
| GSD_ARCHITECTURE_SCAFFOLDING.md | ~2,200 | System architecture, registries, flows |

### Agent References
| Agent | Tier | Tokens | When to Load |
|-------|------|--------|--------------|
| gsd-planner | Deep | ~800 | Modifying planning logic |
| gsd-executor | Deep | ~700 | Modifying execution logic |
| gsd-verifier | Deep | ~700 | Modifying verification |
| gsd-plan-checker | Deep | ~600 | Modifying plan validation |
| gsd-researcher | Standard | ~300 | Modifying research |
| gsd-debugger | Standard | ~300 | Modifying debugging |
...

### Command References
| Document | Coverage | Tokens |
|----------|----------|--------|
| core-commands-reference.md | 4 commands | ~600 |
| secondary-commands-reference.md | 17 commands | ~400 |

### Support References
| Document | Coverage | Tokens |
|----------|----------|--------|
| support-components-reference.md | Workflows, templates, refs | ~500 |

## Modification Guides

### Adding a New Command
1. Load: scaffolding + core-commands-reference
2. Read: Similar command as template
3. Create: commands/gsd/{name}.md
4. Update: help.md command list

### Adding a New Agent
1. Load: scaffolding + similar agent reference
2. Create: agents/gsd-{name}.md
3. Update: Spawning command
4. Add: Output template if needed

### Modifying an Agent
1. Load: scaffolding + agent's deep reference
2. Identify: Section to modify (use section index)
3. Extract: Current constraints from source
4. Modify: Preserving constraints
5. Update: Downstream consumers if output changes

### Modifying State Schema
1. Load: scaffolding + FILE_MANIFEST
2. Identify: All readers/writers of that state file
3. Update: Template + all consumers
4. Test: Full flow that uses state

## Cross-Reference Matrix

| Component | Reads | Writes | Spawns | Spawned By |
|-----------|-------|--------|--------|------------|
| /gsd:plan-phase | ROADMAP, STATE | — | planner, checker | User |
| gsd-planner | STATE, ROADMAP, CONTEXT, RESEARCH | PLAN.md | — | plan-phase |
| gsd-executor | PLAN.md, STATE | SUMMARY.md, code | — | execute-phase |
...

## Appendix: Token Budget Guide

| Task Type | Load These | Est. Tokens |
|-----------|------------|-------------|
| Quick lookup | Index only | ~500 |
| Architecture review | Index + scaffolding | ~2,700 |
| Agent modification | Above + agent ref | ~3,500 |
| Full system change | Above + related refs | ~5,000 |
```

Write to: `docs/GSD_DOCUMENTATION_INDEX.md`
```

---

## Execution Checklist

### Phase 1: Manifest
- [ ] Run Prompt 1.1
- [ ] Verify all files cataloged
- [ ] `/clear` context

### Phase 2: Core Agents
- [ ] Run Prompt 2.1 (gsd-planner)
- [ ] `/clear` context
- [ ] Run Prompt 2.2 (gsd-executor)
- [ ] `/clear` context
- [ ] Run Prompt 2.3 (gsd-verifier)
- [ ] `/clear` context
- [ ] Run Prompt 2.4 (gsd-plan-checker)
- [ ] `/clear` context

### Phase 3: Support Agents
- [ ] Run Prompt 3.1 (research agents)
- [ ] `/clear` context
- [ ] Run Prompt 3.2 (utility agents)
- [ ] `/clear` context

### Phase 4: Commands
- [ ] Run Prompt 4.1 (core commands)
- [ ] `/clear` context
- [ ] Run Prompt 4.2 (secondary commands)
- [ ] `/clear` context

### Phase 5: Support Docs
- [ ] Run Prompt 5.1
- [ ] `/clear` context

### Phase 6: Integration
- [ ] Run Prompt 6.1
- [ ] Verify all cross-references
- [ ] Final review

---

## Output Directory Structure

```
gsd/                                   # Repository root
├── GSD_ARCHITECTURE_SCAFFOLDING.md    # Architecture overview
├── docs/                              # Reference documentation
│   ├── GSD_DOCUMENTATION_INDEX.md     # Master navigation
│   ├── FILE_MANIFEST.md               # Complete file inventory
│   ├── agents/
│   │   ├── gsd-planner-reference.md       # Deep tier
│   │   ├── gsd-executor-reference.md      # Deep tier
│   │   ├── gsd-verifier-reference.md      # Deep tier
│   │   ├── gsd-plan-checker-reference.md  # Deep tier
│   │   ├── gsd-researcher-reference.md    # Standard tier
│   │   ├── gsd-phase-researcher-reference.md
│   │   ├── gsd-debugger-reference.md
│   │   ├── gsd-codebase-mapper-reference.md
│   │   └── gsd-roadmapper-reference.md
│   ├── commands/
│   │   ├── core-commands-reference.md
│   │   └── secondary-commands-reference.md
│   └── support-components-reference.md
├── agents/                            # Original source (unchanged)
├── commands/                          # Original source (unchanged)
└── get-shit-done/                     # Original source (unchanged)
```

---

## Quality Verification

After all phases complete, verify:

### Coverage Check
```bash
# Count documented vs total files
wc -l docs/FILE_MANIFEST.md
find . -name "*.md" -not -path "./docs/*" | wc -l
```

### Constraint Extraction Check
For each Deep Reference doc, verify these are documented:
- [ ] All MUST/NEVER constraints
- [ ] All numeric limits
- [ ] All operational modes
- [ ] All anti-patterns

### Cross-Reference Check
- [ ] Every spawned agent has documentation
- [ ] Every output file has template documentation
- [ ] Every workflow has user documentation

### Token Budget Check
```bash
# Estimate tokens (words × 1.3)
wc -w docs/**/*.md | tail -1
```

Target: Total documentation < 10,000 tokens for full load.

---

## Notes for Execution

1. **Always `/clear` between phases** — Extraction is context-intensive

2. **Extraction order matters** — Core agents first because other docs reference them

3. **If context runs low mid-phase** — Save progress, `/clear`, resume with partial output

4. **Verify as you go** — Check each doc before moving to next phase

5. **Source of truth** — Always cite line numbers for constraints (enables verification)

6. **Don't over-document** — Standard tier exists for a reason. Not everything needs Deep Reference.
