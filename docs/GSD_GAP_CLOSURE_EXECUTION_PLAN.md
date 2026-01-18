# GSD Documentation Gap Closure — Execution Plan

> **Purpose:** Multi-stage execution plan to address all 14 identified documentation gaps
> **Estimated Stages:** 7 stages with clean context between each
> **Repository Root:** `/home/user/get-shit-done/`

---

## Overview

This plan addresses gaps identified in the GSD Documentation Gap Analysis. Each stage is designed to complete within context budget and produces verifiable outputs.

### Gap Summary by Priority

| Priority | Count | Gaps |
|----------|-------|------|
| P0 (Critical) | 2 | User Journey corrections, PLAN.md schema |
| P1 (Important) | 6 | audit-milestone docs, Flow 4, synthesizer sections, UAT schema, plan-milestone-gaps, research distinction |
| P2 (Nice to have) | 6 | checkpoint types, --skip-verify, settings.json, .continue-here schema, discovery-phase behavior |

### Stage Sequence

```
Stage 1: Setup & Task Tracker Creation
    ↓ /clear
Stage 2: User Journey Corrections (P0)
    ↓ /clear
Stage 3: Support Components Schemas (P0/P1)
    ↓ /clear
Stage 4: Secondary Commands Enhancement (P1)
    ↓ /clear
Stage 5: Architecture Scaffolding Updates (P1)
    ↓ /clear
Stage 6: Core & Operational Updates (P2)
    ↓ /clear
Stage 7: Verification & Summary
```

---

## Repository Structure Reference

### Documentation Files (Target for Updates)

| File | Path |
|------|------|
| GSD_USER_JOURNEY.md | `docs/GSD_USER_JOURNEY.md` |
| support-components-reference.md | `docs/support-components-reference.md` |
| secondary-commands-reference.md | `docs/commands/secondary-commands-reference.md` |
| GSD_ARCHITECTURE_SCAFFOLDING.md | `GSD_ARCHITECTURE_SCAFFOLDING.md` (repo root) |
| core-commands-reference.md | `docs/commands/core-commands-reference.md` |
| operational-components-reference.md | `docs/operational-components-reference.md` |

### Source Files (Reference Material)

| Category | Path |
|----------|------|
| Command definitions | `commands/gsd/*.md` |
| Agent definitions | `agents/*.md` |
| Templates | `get-shit-done/templates/*.md` |
| Workflows | `get-shit-done/workflows/*.md` |
| References | `get-shit-done/references/*.md` |

### Output Location

All tracker and report files go to: `docs/`

---

# Stage 1: Setup & Task Tracker Creation

## Stage 1 Prompt

```
You are performing Stage 1 of a 7-stage documentation update for the GSD system.

## Objective
Create the task completion tracker document and verify access to all required source files.

## Task Tracker Instructions
Create a file at `docs/GSD_GAP_CLOSURE_TRACKER.md` with the following content:

---START OF TRACKER TEMPLATE---
# GSD Documentation Gap Closure — Task Tracker

> **Created:** [CURRENT_DATE]
> **Last Updated:** [CURRENT_DATE]
> **Current Stage:** 1 of 7

## Task Status Legend
- [ ] Not started
- [~] In progress
- [x] Complete
- [!] Blocked

---

## Stage 1: Setup & Task Tracker
- [x] Create this tracker document
- [ ] Verify source file access
- [ ] Verify output file access

## Stage 2: User Journey Corrections (P0)
- [ ] 2.1 Add MILESTONE_AUDITING state to state machine
- [ ] 2.2 Add decision points 14 and 14a for audit-milestone
- [ ] 2.3 Add Milestone Audit Flow diagram
- [ ] 2.4 Add execute-phase --gaps-only to phase loop
- [ ] 2.5 Update "Where Am I?" quick reference with audit states
- [ ] 2.6 Add session patterns D and E
- [ ] 2.7 Add Checkpoint Types Reference section

## Stage 3: Support Components Schemas (P0/P1)
- [ ] 3.1 Add PLAN.md frontmatter schema
- [ ] 3.2 Add UAT.md YAML schema
- [ ] 3.3 Add .continue-here.md schema
- [ ] 3.4 Add discovery-phase.md detailed behavior

## Stage 4: Secondary Commands Enhancement (P1)
- [ ] 4.1 Add /gsd:audit-milestone comprehensive documentation
- [ ] 4.2 Add /gsd:plan-milestone-gaps documentation
- [ ] 4.3 Clarify /gsd:research-phase vs plan-phase --skip-research

## Stage 5: Architecture Scaffolding Updates (P1)
- [ ] 5.1 Add Flow 4: Milestone Completion
- [ ] 5.2 Add gsd-research-synthesizer to Critical Agent Sections

## Stage 6: Core & Operational Updates (P2)
- [ ] 6.1 Add checkpoint types detail to core-commands-reference.md
- [ ] 6.2 Document --skip-verify flag behavior for plan-phase
- [ ] 6.3 Add settings.json schema to operational-components-reference.md

## Stage 7: Verification & Summary
- [ ] 7.1 Cross-reference all changes against source
- [ ] 7.2 Verify no regressions introduced
- [ ] 7.3 Generate completion summary report

---

## Change Log

| Stage | Task | File Modified | Status | Notes |
|-------|------|---------------|--------|-------|
| 1 | Setup | GSD_GAP_CLOSURE_TRACKER.md | Complete | Tracker created |

---
---END OF TRACKER TEMPLATE---

## Verification Steps

After creating the tracker, verify access to these source files by reading their first 10 lines:

**Documentation Files (to be updated):**
1. `docs/GSD_USER_JOURNEY.md`
2. `docs/support-components-reference.md`
3. `docs/commands/secondary-commands-reference.md`
4. `GSD_ARCHITECTURE_SCAFFOLDING.md`
5. `docs/commands/core-commands-reference.md`
6. `docs/operational-components-reference.md`

**Source Reference Files:**
7. `commands/gsd/audit-milestone.md`
8. `commands/gsd/plan-milestone-gaps.md`
9. `agents/gsd-integration-checker.md`
10. `get-shit-done/templates/phase-prompt.md`
11. `get-shit-done/references/checkpoints.md`

## Completion Criteria
- [ ] Tracker file created at `docs/GSD_GAP_CLOSURE_TRACKER.md`
- [ ] All 6 documentation files verified accessible
- [ ] Source reference files verified accessible
- [ ] Tracker tasks for Stage 1 marked complete

## Tracker Update
After completing all tasks, update the tracker:
1. Mark Stage 1 tasks as [x] complete
2. Update "Last Updated" timestamp
3. Add entries to Change Log table

Present the tracker file when complete.
```

---

# Stage 2: User Journey Corrections (P0)

## Stage 2 Prompt

```
You are performing Stage 2 of a 7-stage documentation update for the GSD system.

## Objective
Apply all corrections to GSD_USER_JOURNEY.md to fix the 5 identified inaccuracies.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stage 1 is complete.

## Source Files to Reference
Read these source files for accurate information:
- `commands/gsd/audit-milestone.md` — State machine states
- `commands/gsd/plan-milestone-gaps.md` — Decision points
- `agents/gsd-integration-checker.md` — Integration checker flow
- `CHANGELOG.md` — --gaps-only flag (v1.6.3)

## Base Document
Read `docs/GSD_USER_JOURNEY.md` as the base document.

## Tasks

### Task 2.1: State Machine Update
Add MILESTONE_AUDITING state between PHASE_COMPLETE and MILESTONE_PENDING:

```
PHASE_COMPLETE (last phase)
        │
        ▼
MILESTONE_AUDITING ◄──────────────┐
        │                          │
        │ Audit passed             │ Gaps found → plan-milestone-gaps
        ▼                          │
MILESTONE_PENDING ─────────────────┘
        │
        │ /gsd:complete-milestone
        ▼
MILESTONE_COMPLETE
```

### Task 2.2: Decision Points Table Update
In the "Milestone" section of Decision Points Catalog, ensure these rows exist:

| Point | Command | User Provides | System Creates |
|-------|---------|---------------|----------------|
| **14** | audit-milestone | Accept audit or plan gaps | MILESTONE-AUDIT.md |
| **14a** | plan-milestone-gaps | Approve gap closure phases | Gap closure phases in ROADMAP |
| **15** | complete-milestone | Version number | Archive + git tag |
| **16** | new-milestone | What's next? | New ROADMAP.md |

### Task 2.3: Add Milestone Audit Flow
Add new section "Milestone Audit Flow" after "UAT Flow":

```markdown
### Milestone Audit Flow

```
VERIFICATION.md files (all phases)
    ↓
/gsd:audit-milestone
    ├── Read all phase verifications
    ├── Aggregate tech debt and gaps
    ├── → gsd-integration-checker
    │       ├── Verify cross-phase wiring (exports → imports)
    │       ├── Verify API coverage (routes → consumers)
    │       └── Verify E2E flows (complete paths)
    │           ↓
    └── MILESTONE-AUDIT.md
            ↓
        Status: passed | gaps_found | tech_debt
            ↓
        [If gaps → /gsd:plan-milestone-gaps]
            └── Gap closure phases added to ROADMAP
                ↓
            [Phase Loop for gap phases]
```
```

### Task 2.4: Update Phase-Level Loop Diagram
Modify the gaps handling to include --gaps-only:

```
│   gaps? ─yes→ plan-phase --gaps
│        │           ↓
│        │      execute-phase --gaps-only
```

### Task 2.5: Update Quick Reference Table
Add these rows to "Where Am I?" table:

| I see... | I'm in... | Next command |
|----------|-----------|--------------|
| All phases complete, no MILESTONE-AUDIT.md | Audit pending | `/gsd:audit-milestone` |
| MILESTONE-AUDIT.md with gaps_found | Gaps need closure | `/gsd:plan-milestone-gaps` |
| MILESTONE-AUDIT.md with passed | Ready to complete | `/gsd:complete-milestone` |

### Task 2.6: Add Session Patterns D and E
Add to "Typical Session Patterns" section:

```markdown
### Pattern D: Gap Closure After Verification
```
/gsd:execute-phase 3
    ↓ (verifier finds gaps)
/clear
/gsd:plan-phase 3 --gaps
    ↓ (creates gap closure plans)
/clear
/gsd:execute-phase 3 --gaps-only
    ↓ (executes only the new gap plans)
```

### Pattern E: Milestone Gap Closure
```
/gsd:audit-milestone
    ↓ (integration checker finds cross-phase issues)
/clear
/gsd:plan-milestone-gaps
    ↓ (creates new phases to close gaps)
/clear
[Phase Loop for gap phases]
    ↓
/gsd:audit-milestone
    ↓ (re-verify)
/gsd:complete-milestone 1.0
```
```

### Task 2.7: Add Checkpoint Types Reference
Add new section before "Version" section:

```markdown
## Checkpoint Types Reference

Three checkpoint types pause execution for user input:

| Type | When Used | User Action | Example |
|------|-----------|-------------|---------|
| `human-verify` | After visible change | Confirm it looks right | "Check the login form renders correctly" |
| `human-action` | External action needed | Complete action, report | "Run database migration, confirm success" |
| `decision` | Implementation choice | Choose option | "Use JWT or sessions for auth?" |
```

## Output
Save the updated document to `docs/GSD_USER_JOURNEY.md`

## Tracker Update
After completing all tasks:
1. Read the tracker from `docs/GSD_GAP_CLOSURE_TRACKER.md`
2. Mark tasks 2.1 through 2.7 as [x] complete
3. Update "Last Updated" timestamp
4. Update "Current Stage" to 2
5. Add entries to Change Log:
   | 2 | 2.1-2.7 | GSD_USER_JOURNEY.md | Complete | All 7 corrections applied |
6. Write updated tracker back to same location

## Completion Criteria
- [ ] All 7 tasks applied to GSD_USER_JOURNEY.md
- [ ] Document saved to docs directory
- [ ] Tracker updated with Stage 2 completion
- [ ] No content from original document lost

Present both the updated User Journey document and the tracker when complete.
```

---

# Stage 3: Support Components Schemas (P0/P1)

## Stage 3 Prompt

```
You are performing Stage 3 of a 7-stage documentation update for the GSD system.

## Objective
Add missing schemas to support-components-reference.md: PLAN.md frontmatter, UAT.md, .continue-here.md, and discovery-phase behavior.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stage 2 is complete.

## Source Files to Reference
Read these source files for accurate schemas:
- `get-shit-done/templates/phase-prompt.md` — PLAN.md frontmatter
- `get-shit-done/templates/uat.md` — UAT.md schema
- `get-shit-done/references/continuation-format.md` — .continue-here.md format
- `get-shit-done/workflows/discovery-phase.md` — discovery-phase behavior

## Base Document
Read `docs/support-components-reference.md` as the base.

## Tasks

### Task 3.1: Add PLAN.md Frontmatter Schema
Add a new subsection under "Templates" section titled "### PLAN.md Frontmatter Schema":

```markdown
### PLAN.md Frontmatter Schema

Required frontmatter for `{phase}-{plan}-PLAN.md` files (see `get-shit-done/templates/phase-prompt.md`):

```yaml
---
phase: "01-foundation"           # Phase directory name
plan: "01"                       # Plan number within phase
objective: "string"              # What this plan delivers (1 sentence)
wave: 1                          # Execution order (1 = first/parallel)
depends_on: []                   # Plan IDs this depends on (e.g., ["01"])
autonomous: true                 # false = pause at checkpoints
discovery: 0                     # Discovery level 0-3
must_haves:
  truths:                        # User-observable outcomes (3-7 items)
    - "User can log in with email"
    - "Session persists across refresh"
  artifacts:                     # Files that must exist with quality bar
    - path: "src/lib/auth.ts"
      min_lines: 50
      exports: ["login", "logout", "getCurrentUser"]
    - path: "src/app/api/auth/login/route.ts"
      min_lines: 30
  key_links:                     # Connections that must exist (3-5 items)
    - source: "src/components/LoginForm.tsx"
      target: "src/app/api/auth/login/route.ts"
      method: "fetch POST"
    - source: "src/app/api/auth/login/route.ts"
      target: "prisma.user"
      method: "findUnique"
---
```

**Field Requirements:**

| Field | Required | Default | Notes |
|-------|----------|---------|-------|
| phase | Yes | — | Must match phase directory |
| plan | Yes | — | Two-digit string |
| objective | Yes | — | Single sentence |
| wave | Yes | 1 | Determines parallel execution |
| depends_on | Yes | [] | Empty for wave 1 plans |
| autonomous | No | true | Set false for checkpoints |
| discovery | No | 0 | 0=none, 1=shallow, 2=standard, 3=deep |
| must_haves | Yes | — | Verification contract |

**must_haves.truths Rules:**
- Must be user-observable (not "bcrypt installed" but "passwords are secure")
- Testable by human using the app
- 3-7 items typical

**must_haves.artifacts Rules:**
- Every artifact needs path and min_lines
- exports optional but recommended for libraries
- min_lines prevents stub acceptance

**must_haves.key_links Rules:**
- Identifies critical wiring between artifacts
- method describes connection type
- Prevents "created but not connected" failures
```

### Task 3.2: Add UAT.md YAML Schema
Add a new subsection "### UAT.md Schema" after the PLAN.md schema:

```markdown
### UAT.md Schema

Schema for `{phase}-UAT.md` files from `/gsd:verify-work` (see `get-shit-done/templates/uat.md`):

```yaml
---
phase: "01-foundation"
tested: "2026-01-18T14:30:00Z"
status: passed | issues_found
summary:
  total: 5
  passed: 4
  failed: 1
  skipped: 0
---
```

**Report Sections (in order):**
1. **Test Results Table** — Per-test status with user feedback
2. **Issues Summary** — Failed tests with diagnosis
3. **Gap Closure Plans** — If issues found, plans created
4. **Next Steps** — Routing based on results

**Test Result Entry:**
```markdown
| # | Test | Status | Notes |
|---|------|--------|-------|
| 1 | User can log in with valid credentials | ✓ Pass | — |
| 2 | Login fails with wrong password | ✓ Pass | Shows error message |
| 3 | Session persists after refresh | ✗ Fail | User reported: "Gets logged out on refresh" |
```

**Issue Entry:**
```markdown
### Issue 1: Session not persisting

**Test:** Session persists after refresh
**User Report:** Gets logged out on refresh
**Diagnosis:** Cookie not set with correct expiry
**Root Cause:** `maxAge` missing in session cookie options
**Fix Plan:** 01-03-GAP-PLAN.md created
```
```

### Task 3.3: Add .continue-here.md Schema
Add a new subsection "### Continuation File Schema":

```markdown
### Continuation File Schema

Schema for `.planning/.continue-here.md` session handoff files (see `get-shit-done/references/continuation-format.md`):

```markdown
# Continue Here

**Created:** {timestamp}
**Context:** {what was happening}
**Phase:** {current phase}
**Plan:** {current plan if applicable}

## What Was Happening

{Description of task in progress}

## Completed So Far

- [x] {completed step 1}
- [x] {completed step 2}
- [ ] {next step - IN PROGRESS}
- [ ] {remaining step}

## Next Action

{Specific instruction for resuming}

## Files Modified

- `{path}` — {what was changed}

## Open Questions

- {Any decision points or blockers}
```

**When Created:**
- Context reaches 70%+ and degradation detected
- User requests `/gsd:pause-work`
- Before checkpoint that requires `/clear`

**When Consumed:**
- `/gsd:resume-work` detects file, presents context, routes to continuation
- File deleted after successful resume

**Critical Fields:**
- "Next Action" must be specific enough to continue without re-reading context
- "Completed So Far" prevents re-doing work
- "Files Modified" allows verifying state
```

### Task 3.4: Add Discovery-Phase Behavior
Add or expand the "discovery-phase.md Details" subsection:

```markdown
### discovery-phase.md Details (Expanded)

**Purpose:** Shallow research for library/option decisions during planning. Answers "which library should we use?" not "how do we build this system?"

**Distinction from research-phase:**

| Aspect | discovery-phase | research-phase |
|--------|-----------------|----------------|
| Depth | Shallow (which library) | Deep (ecosystem knowledge) |
| Scope | Single decision | Entire phase domain |
| Output | DISCOVERY.md | {phase}-RESEARCH.md |
| Trigger | During planning when choice needed | Before planning for complex domains |
| Duration | Minutes | 10-30 minutes |

**When to Use:**
- "Should we use Prisma or Drizzle?"
- "JWT vs session cookies?"
- "Which animation library for React?"

**When NOT to Use (use research-phase instead):**
- 3D/WebGL development
- Audio processing
- Machine learning
- Game development
- Any unfamiliar domain

**Execution Flow:**
1. Identify discovery question from planning context
2. Query sources (Context7 → Official Docs → WebSearch)
3. Compare 2-4 options with pros/cons
4. Write DISCOVERY.md with recommendation
5. Mark confidence level (HIGH/MEDIUM/LOW)

**DISCOVERY.md Structure:**
```markdown
# Discovery: {Question}

## Recommendation

**Use:** {recommended option}
**Confidence:** HIGH | MEDIUM | LOW
**Reason:** {1-2 sentence justification}

## Options Considered

### {Option 1}
- Pros: {list}
- Cons: {list}
- Fit: {how it fits this project}

### {Option 2}
- Pros: {list}
- Cons: {list}
- Fit: {how it fits this project}

## Decision Factors

| Factor | {Option 1} | {Option 2} |
|--------|------------|------------|
| {Factor 1} | {rating} | {rating} |

## Sources

- {source 1} (confidence level)
- {source 2} (confidence level)
```
```

## Output
Save the updated document to `docs/support-components-reference.md`

## Tracker Update
After completing all tasks:
1. Read the tracker
2. Mark tasks 3.1 through 3.4 as [x] complete
3. Update "Last Updated" timestamp and "Current Stage" to 3
4. Add to Change Log:
   | 3 | 3.1-3.4 | support-components-reference.md | Complete | 4 schemas added |
5. Write updated tracker

## Completion Criteria
- [ ] PLAN.md frontmatter schema added with all field documentation
- [ ] UAT.md schema added with report sections
- [ ] .continue-here.md schema added with lifecycle notes
- [ ] discovery-phase behavior expanded with comparison table
- [ ] Document saved to docs directory
- [ ] Tracker updated

Present the updated support-components-reference.md and tracker when complete.
```

---

# Stage 4: Secondary Commands Enhancement (P1)

## Stage 4 Prompt

```
You are performing Stage 4 of a 7-stage documentation update for the GSD system.

## Objective
Enhance secondary-commands-reference.md with comprehensive documentation for audit-milestone, plan-milestone-gaps, and research-phase distinction.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stage 3 is complete.

## Source Files to Reference
Read these source files for accurate information:
- `commands/gsd/audit-milestone.md` — /gsd:audit-milestone details
- `commands/gsd/plan-milestone-gaps.md` — /gsd:plan-milestone-gaps details
- `commands/gsd/research-phase.md` — /gsd:research-phase details
- `agents/gsd-integration-checker.md` — Integration checker behavior

## Base Document
Read `docs/commands/secondary-commands-reference.md` as the base.

## Tasks

### Task 4.1: Add /gsd:audit-milestone Documentation
Add comprehensive section for audit-milestone (should be in Milestone Management section):

```markdown
### /gsd:audit-milestone

Verify milestone achieved its definition of done before archiving.

**Purpose:** Catches issues that pass phase-level verification but fail at system level — cross-phase wiring gaps, broken E2E flows, unmet requirements.

**Execution Flow:**
1. Determine milestone scope from ROADMAP.md
2. Read all phase VERIFICATION.md files
3. Aggregate tech debt and deferred gaps
4. Spawn gsd-integration-checker for cross-phase verification
5. Check requirements coverage from REQUIREMENTS.md
6. Generate v{version}-MILESTONE-AUDIT.md
7. Route based on status

**What Integration Checker Verifies:**

| Check | What It Catches |
|-------|-----------------|
| Export/Import wiring | Phase 1 exports function, Phase 3 never imports it |
| API coverage | Route exists but nothing calls it |
| Auth protection | Dashboard accessible without login |
| E2E flows | User signup works but login broken |

**Output:** `.planning/v{version}-MILESTONE-AUDIT.md`

**Status Values:**
- `passed` — All requirements met, integration verified, E2E flows complete
- `gaps_found` — Critical blockers exist, run `/gsd:plan-milestone-gaps`
- `tech_debt` — No blockers but accumulated deferred items need review

**Routing:**
| Status | Next Command |
|--------|--------------|
| passed | `/gsd:complete-milestone` |
| gaps_found | `/gsd:plan-milestone-gaps` |
| tech_debt | Review debt, then `/gsd:complete-milestone` or plan cleanup |

**Usage:** `/gsd:audit-milestone` or `/gsd:audit-milestone 1.0`
```

### Task 4.2: Add /gsd:plan-milestone-gaps Documentation
Add new section for plan-milestone-gaps:

```markdown
### /gsd:plan-milestone-gaps

Create phases to close all gaps identified by milestone audit.

**Purpose:** Automates gap closure planning — reads MILESTONE-AUDIT.md, groups gaps into logical phases, updates ROADMAP.md.

**Prerequisites:**
- `/gsd:audit-milestone` must have run
- v{version}-MILESTONE-AUDIT.md must exist with gaps_found or tech_debt status

**Execution Flow:**
1. Load most recent MILESTONE-AUDIT.md
2. Parse gaps from YAML frontmatter
3. Prioritize by requirement priority (must > should > nice)
4. Group related gaps into logical phases
5. Determine phase numbers (continue from highest existing)
6. Present gap closure plan for approval
7. On approval, update ROADMAP.md with new phases
8. Route to planning first gap phase

**Gap Grouping Rules:**
- Same affected phase → combine into one fix phase
- Same subsystem (auth, API, UI) → combine
- Dependency order (fix stubs before wiring)
- Keep phases focused: 2-4 tasks each

**Example:**
```
Gaps identified:
- REQ-05 (Dashboard) unsatisfied
- Integration: Auth → Dashboard missing
- Flow: "View dashboard" broken

→ Creates Phase 6: "Wire Dashboard to API"
```

**Output:** Updated ROADMAP.md with gap closure phases

**Usage:** `/gsd:plan-milestone-gaps`
```

### Task 4.3: Clarify Research-Phase vs Plan-Phase
Add clarification section or expand existing research-phase entry:

```markdown
### /gsd:research-phase vs --skip-research

**When to use /gsd:research-phase (dedicated research):**
- Complex/unfamiliar domains (3D, audio, ML, games)
- Phase requires ecosystem knowledge beyond "which library"
- You want deep research BEFORE planning starts
- Research output will be reused across multiple plans

**When to use /gsd:plan-phase (includes research):**
- Standard development (web apps, APIs, CRUD)
- Domain is familiar, just need implementation patterns
- Quick research sufficient during planning

**When to use /gsd:plan-phase --skip-research:**
- Research already done via /gsd:research-phase
- Returning to plan after interruption
- Phase is simple/mechanical (no research needed)

**Decision Matrix:**

| Domain Familiarity | Phase Complexity | Recommended Approach |
|--------------------|------------------|----------------------|
| High | Low | `plan-phase --skip-research` |
| High | High | `plan-phase` (auto-research) |
| Low | Any | `research-phase` then `plan-phase --skip-research` |
| Unknown | Any | `research-phase` first |

**Research Output Comparison:**

| Command | Output | Depth | Duration |
|---------|--------|-------|----------|
| plan-phase (auto) | {phase}-RESEARCH.md | Standard | 5-10 min |
| research-phase | {phase}-RESEARCH.md | Deep | 15-30 min |
| discovery (during planning) | DISCOVERY.md | Shallow | 2-5 min |
```

## Output
Save the updated document to `docs/commands/secondary-commands-reference.md`

## Tracker Update
After completing all tasks:
1. Read the tracker
2. Mark tasks 4.1 through 4.3 as [x] complete
3. Update "Last Updated" timestamp and "Current Stage" to 4
4. Add to Change Log:
   | 4 | 4.1-4.3 | secondary-commands-reference.md | Complete | 3 command sections added/expanded |
5. Write updated tracker

## Completion Criteria
- [ ] /gsd:audit-milestone fully documented with routing
- [ ] /gsd:plan-milestone-gaps documented with gap grouping rules
- [ ] Research-phase vs plan-phase clarified with decision matrix
- [ ] Document saved to docs/commands directory
- [ ] Tracker updated

Present the updated secondary-commands-reference.md and tracker when complete.
```

---

# Stage 5: Architecture Scaffolding Updates (P1)

## Stage 5 Prompt

```
You are performing Stage 5 of a 7-stage documentation update for the GSD system.

## Objective
Update GSD_ARCHITECTURE_SCAFFOLDING.md with Flow 4 (Milestone Completion) and add gsd-research-synthesizer to Critical Agent Sections.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stage 4 is complete.

## Source Files to Reference
Read these source files for accurate information:
- `commands/gsd/audit-milestone.md` — Milestone audit flow
- `commands/gsd/complete-milestone.md` — Complete milestone flow
- `agents/gsd-integration-checker.md` — Integration checker behavior
- `agents/gsd-research-synthesizer.md` — Research synthesizer behavior

## Base Document
Read `GSD_ARCHITECTURE_SCAFFOLDING.md` (in repo root) as the base.

## Tasks

### Task 5.1: Add Flow 4 — Milestone Completion
Add new flow after "Flow 3: Phase Execution" in the "Key Flows" section:

```markdown
### Flow 4: Milestone Completion
```
/gsd:audit-milestone
├─→ Read all phase VERIFICATION.md files
├─→ Aggregate tech debt and deferred gaps
├─→ Spawn gsd-integration-checker
│   ├─→ Build export/import map from SUMMARYs
│   ├─→ Verify export usage (connected/orphaned)
│   ├─→ Verify API coverage (routes → consumers)
│   ├─→ Verify auth protection on sensitive routes
│   └─→ Trace E2E flows (complete/broken)
├─→ Check requirements coverage from REQUIREMENTS.md
├─→ Generate v{version}-MILESTONE-AUDIT.md
└─→ Route: passed → complete, gaps → plan-gaps, tech_debt → review

/gsd:plan-milestone-gaps (if gaps found)
├─→ Load MILESTONE-AUDIT.md
├─→ Prioritize gaps by requirement priority
├─→ Group related gaps into phases
├─→ Present gap closure plan
├─→ On approval, update ROADMAP.md
└─→ Route to first gap phase

/gsd:complete-milestone {version}
├─→ Verify audit passed (or tech_debt accepted)
├─→ Archive to .planning/milestones/v{version}/
│   ├─→ v{version}-ROADMAP.md
│   └─→ v{version}-REQUIREMENTS.md
├─→ Update PROJECT.md to brownfield format
├─→ Git tag v{version}
└─→ Offer /gsd:new-milestone
```
```

### Task 5.2: Add gsd-research-synthesizer to Critical Agent Sections
Add row to the "Critical Agent Sections" table:

```markdown
| **gsd-research-synthesizer** | `<synthesis_process>`, `<cross_reference>`, `<priority_conflicts>` |
```

Also add a behavior table entry in the agent behavior section if one exists:

```markdown
### gsd-research-synthesizer — `agents/gsd-research-synthesizer.md`

| Behavior | Section | Key Rules |
|----------|---------|-----------|
| 4-file synthesis | `<synthesis_process>` | Reads STACK, FEATURES, ARCHITECTURE, PITFALLS |
| Cross-referencing | `<cross_reference>` | Validates consistency across research files |
| Priority conflicts | `<priority_conflicts>` | Resolves contradictions between sources |
| Output format | `<structured_output>` | Produces SUMMARY.md with actionable synthesis |

**Key insight:** Synthesizer runs AFTER parallel researchers complete. It doesn't do research — it reconciles and prioritizes findings from the 4 research dimensions.
```

## Output
Save the updated document to `GSD_ARCHITECTURE_SCAFFOLDING.md` (repo root)

## Tracker Update
After completing all tasks:
1. Read the tracker
2. Mark tasks 5.1 and 5.2 as [x] complete
3. Update "Last Updated" timestamp and "Current Stage" to 5
4. Add to Change Log:
   | 5 | 5.1-5.2 | GSD_ARCHITECTURE_SCAFFOLDING.md | Complete | Flow 4 + synthesizer sections added |
5. Write updated tracker

## Completion Criteria
- [ ] Flow 4: Milestone Completion added with full diagram
- [ ] gsd-research-synthesizer in Critical Agent Sections table
- [ ] Synthesizer behavior table added
- [ ] Document saved to repo root
- [ ] Tracker updated

Present the updated GSD_ARCHITECTURE_SCAFFOLDING.md and tracker when complete.
```

---

# Stage 6: Core & Operational Updates (P2)

## Stage 6 Prompt

```
You are performing Stage 6 of a 7-stage documentation update for the GSD system.

## Objective
Update core-commands-reference.md with checkpoint types and --skip-verify flag, and add settings.json schema to operational-components-reference.md.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stage 5 is complete.

## Source Files to Reference
Read these source files for accurate information:
- `get-shit-done/references/checkpoints.md` — Checkpoint types
- `commands/gsd/plan-phase.md` — --skip-verify flag
- `bin/install.js` — settings.json handling

## Base Documents
Read these documents:
- `docs/commands/core-commands-reference.md`
- `docs/operational-components-reference.md`

## Tasks

### Task 6.1: Add Checkpoint Types to Core Commands
Add new section to execute-phase documentation in core-commands-reference.md:

```markdown
### Checkpoint Types

Three checkpoint types can pause execution for user input (set `autonomous: false` in PLAN.md):

| Type | Tag | When Used | User Action |
|------|-----|-----------|-------------|
| `human-verify` | `<checkpoint:human-verify>` | After visible change | Confirm it looks/works right |
| `human-action` | `<checkpoint:human-action>` | External action needed | Complete action, report result |
| `decision` | `<checkpoint:decision>` | Implementation choice needed | Choose from options |

**human-verify Example:**
```xml
<checkpoint:human-verify>
Check that the login form renders correctly:
- Email and password fields visible
- Submit button enabled
- Error states display properly
</checkpoint:human-verify>
```

**human-action Example:**
```xml
<checkpoint:human-action>
Run the database migration:
1. Execute: `npx prisma migrate deploy`
2. Verify migration completed without errors
3. Report: success or error message
</checkpoint:human-action>
```

**decision Example:**
```xml
<checkpoint:decision>
Choose authentication strategy:
A) JWT tokens (stateless, better for API)
B) Session cookies (stateful, better for web app)
C) Both (flexibility, more complexity)
</checkpoint:decision>
```

**Checkpoint Behavior:**
- Execution pauses, context preserved
- User response recorded in SUMMARY.md
- If user reports failure, task marked incomplete
- Decisions become part of project context
```

### Task 6.2: Document --skip-verify Flag
Add to plan-phase documentation:

```markdown
### Plan-Phase Flags

| Flag | Purpose | When to Use |
|------|---------|-------------|
| `--gaps` | Gap closure mode | After verification found gaps |
| `--skip-research` | Skip phase researcher | Research already done or simple phase |
| `--skip-verify` | Skip plan-checker | Re-planning after minor changes |

**--skip-verify Details:**

Skips the gsd-plan-checker verification step. Use when:
- Making minor plan adjustments that don't affect coverage
- Re-planning after external changes (not gap closure)
- Plans are known to be complete from previous verification

**Warning:** Using --skip-verify on new plans risks:
- Missing requirements (no coverage check)
- Circular dependencies (no graph validation)
- Scope creep (no scope sanity check)

**Recommended usage:**
```
# First time planning - always verify
/gsd:plan-phase 3

# After minor edits to existing verified plans
/gsd:plan-phase 3 --skip-verify

# After gaps found - always verify gap plans
/gsd:plan-phase 3 --gaps  # (verification included)
```
```

### Task 6.3: Add settings.json Schema
Add new section to operational-components-reference.md:

```markdown
### settings.json Schema

Claude Code settings file structure managed by GSD installer (see `bin/install.js`):

**Location:** `~/.claude/settings.json`

**Full Schema:**
```json
{
  "statusLine": {
    "type": "command",
    "command": "node \"$HOME/.claude/hooks/statusline.js\""
  },
  "hooks": {
    "SessionStart": [
      {
        "matcher": "",
        "hooks": [
          {
            "type": "command",
            "command": "node \"$HOME/.claude/hooks/gsd-check-update.js\""
          }
        ]
      }
    ]
  }
}
```

**Field Descriptions:**

| Field | Purpose | Required |
|-------|---------|----------|
| `statusLine.type` | Must be "command" | Yes |
| `statusLine.command` | Path to statusline script | Yes |
| `hooks.SessionStart` | Hooks run when Claude Code starts | No |
| `hooks.SessionStart[].matcher` | Regex to match directory (empty = all) | No |
| `hooks.SessionStart[].hooks` | Array of hook commands | No |

**Installer Merge Behavior:**

When settings.json exists, installer:
1. Reads existing content
2. Preserves all non-GSD settings
3. Updates/adds statusLine configuration
4. Updates/adds SessionStart hooks
5. Writes merged result

**Manual Modification:**
- Safe to add custom hooks alongside GSD hooks
- Don't remove statusLine — breaks GSD status display
- Don't remove SessionStart hook — breaks update checks

**Troubleshooting:**

| Issue | Cause | Fix |
|-------|-------|-----|
| No status bar | statusLine missing/broken | Re-run installer |
| No update notifications | SessionStart hook missing | Re-run installer |
| Settings overwritten | Manual edit after install | Re-run installer with --force-statusline |
```

## Output
Save updated documents to:
- `docs/commands/core-commands-reference.md`
- `docs/operational-components-reference.md`

## Tracker Update
After completing all tasks:
1. Read the tracker
2. Mark tasks 6.1 through 6.3 as [x] complete
3. Update "Last Updated" timestamp and "Current Stage" to 6
4. Add to Change Log:
   | 6 | 6.1-6.2 | core-commands-reference.md | Complete | Checkpoints + flags added |
   | 6 | 6.3 | operational-components-reference.md | Complete | settings.json schema added |
5. Write updated tracker

## Completion Criteria
- [ ] Checkpoint types documented with examples
- [ ] --skip-verify flag documented with warnings
- [ ] settings.json schema documented with merge behavior
- [ ] Both documents saved to their respective locations
- [ ] Tracker updated

Present both updated documents and the tracker when complete.
```

---

# Stage 7: Verification & Summary

## Stage 7 Prompt

```
You are performing Stage 7 (final) of a 7-stage documentation update for the GSD system.

## Objective
Verify all changes are consistent, cross-reference properly, and generate a completion summary report.

## First: Load the Tracker
Read `docs/GSD_GAP_CLOSURE_TRACKER.md` to verify Stages 1-6 are complete.

## Verification Tasks

### Task 7.1: Cross-Reference Verification

Load all updated documents:
- `docs/GSD_USER_JOURNEY.md`
- `docs/support-components-reference.md`
- `docs/commands/secondary-commands-reference.md`
- `GSD_ARCHITECTURE_SCAFFOLDING.md`
- `docs/commands/core-commands-reference.md`
- `docs/operational-components-reference.md`

Verify these cross-references are consistent:

| Reference | From | To | Check |
|-----------|------|-----|-------|
| audit-milestone flow | User Journey | Secondary Commands | Flow matches documentation |
| plan-milestone-gaps | User Journey | Secondary Commands | Exists and matches |
| Checkpoint types | User Journey | Core Commands | Types match |
| PLAN.md schema | Support Components | Core Commands | Frontmatter referenced |
| Flow 4 | Architecture | Secondary Commands | Flows match |
| Integration checker | Architecture | Secondary Commands | Spawning documented |

For each cross-reference:
1. Read the source section
2. Read the target section
3. Verify terminology matches
4. Verify flows are consistent
5. Note any discrepancies

### Task 7.2: Regression Check

Verify no existing content was lost or corrupted:

1. For each updated document, compare section headings against original
2. Verify all original sections still exist
3. Verify no truncation occurred
4. Check that additions are properly integrated (not just appended)

### Task 7.3: Generate Completion Report

Create `docs/GSD_GAP_CLOSURE_REPORT.md`:

```markdown
# GSD Documentation Gap Closure — Completion Report

> **Completed:** [DATE]
> **Stages Executed:** 7
> **Total Tasks:** 21

## Summary

| Stage | Focus | Tasks | Status |
|-------|-------|-------|--------|
| 1 | Setup & Tracker | 3 | ✓ Complete |
| 2 | User Journey | 7 | ✓ Complete |
| 3 | Support Components | 4 | ✓ Complete |
| 4 | Secondary Commands | 3 | ✓ Complete |
| 5 | Architecture | 2 | ✓ Complete |
| 6 | Core & Operational | 3 | ✓ Complete |
| 7 | Verification | 3 | ✓ Complete |

## Documents Modified

| Document | Sections Added | Lines Changed |
|----------|----------------|---------------|
| GSD_USER_JOURNEY.md | [list] | ~[N] |
| support-components-reference.md | [list] | ~[N] |
| secondary-commands-reference.md | [list] | ~[N] |
| GSD_ARCHITECTURE_SCAFFOLDING.md | [list] | ~[N] |
| core-commands-reference.md | [list] | ~[N] |
| operational-components-reference.md | [list] | ~[N] |

## Gaps Closed

### P0 (Critical)
- [x] User Journey corrections (5 issues fixed)
- [x] PLAN.md frontmatter schema added

### P1 (Important)
- [x] /gsd:audit-milestone documented
- [x] /gsd:plan-milestone-gaps documented
- [x] Flow 4: Milestone Completion added
- [x] gsd-research-synthesizer sections added
- [x] UAT.md schema added
- [x] Research-phase distinction clarified

### P2 (Nice to have)
- [x] Checkpoint types documented
- [x] --skip-verify flag documented
- [x] settings.json schema added
- [x] .continue-here.md schema added
- [x] discovery-phase behavior expanded

## Cross-Reference Verification

| Check | Status | Notes |
|-------|--------|-------|
| audit-milestone consistency | [status] | [notes] |
| plan-milestone-gaps consistency | [status] | [notes] |
| Checkpoint types consistency | [status] | [notes] |
| Flow 4 consistency | [status] | [notes] |
| Schema references | [status] | [notes] |

## Regression Check

| Document | Original Sections | Status |
|----------|-------------------|--------|
| [document] | [N] sections | [status] |

## Recommendations

[Any follow-up work identified during verification]

## Files Delivered

All updated documents:
- docs/GSD_USER_JOURNEY.md
- docs/support-components-reference.md
- docs/commands/secondary-commands-reference.md
- GSD_ARCHITECTURE_SCAFFOLDING.md
- docs/commands/core-commands-reference.md
- docs/operational-components-reference.md
- docs/GSD_GAP_CLOSURE_TRACKER.md
- docs/GSD_GAP_CLOSURE_REPORT.md (this file)
```

## Tracker Final Update
1. Mark tasks 7.1 through 7.3 as [x] complete
2. Update "Current Stage" to "Complete"
3. Update "Last Updated" timestamp
4. Final Change Log entries

## Completion Criteria
- [ ] All 6 cross-references verified consistent
- [ ] No regressions in any document
- [ ] GSD_GAP_CLOSURE_REPORT.md generated
- [ ] Tracker shows all 21 tasks complete
- [ ] All files present in docs directory

Present the completion report, final tracker, and list all output files when complete.
```

---

# Execution Instructions

## For Each Stage

1. **Start fresh:** Run `/clear` before starting each stage
2. **Load prompt:** Copy the stage prompt into Claude
3. **Execute tasks:** Follow the prompt's task sequence
4. **Update tracker:** Always update the tracker at end of stage
5. **Verify outputs:** Confirm files written to correct locations
6. **Proceed:** Run `/clear` and continue to next stage

## Recovery

If a stage fails:
1. Check tracker for last completed task
2. Re-run stage from that task
3. If document corrupted, re-read original file as base

## Time Estimates

| Stage | Estimated Duration |
|-------|-------------------|
| 1 | 5 minutes |
| 2 | 15-20 minutes |
| 3 | 15-20 minutes |
| 4 | 15-20 minutes |
| 5 | 10-15 minutes |
| 6 | 15-20 minutes |
| 7 | 10-15 minutes |
| **Total** | **85-115 minutes** |

---

## Quick Reference: All Stage Prompts

| Stage | Primary Task | Output Files |
|-------|--------------|--------------|
| 1 | Create tracker | docs/GSD_GAP_CLOSURE_TRACKER.md |
| 2 | User Journey fixes | docs/GSD_USER_JOURNEY.md |
| 3 | Support schemas | docs/support-components-reference.md |
| 4 | Command docs | docs/commands/secondary-commands-reference.md |
| 5 | Architecture flow | GSD_ARCHITECTURE_SCAFFOLDING.md |
| 6 | Core + Operational | docs/commands/core-commands-reference.md, docs/operational-components-reference.md |
| 7 | Verification | docs/GSD_GAP_CLOSURE_REPORT.md |

---

## File Path Reference

### Documentation Files (to modify)

| File | Full Path |
|------|-----------|
| GSD_USER_JOURNEY.md | `docs/GSD_USER_JOURNEY.md` |
| support-components-reference.md | `docs/support-components-reference.md` |
| secondary-commands-reference.md | `docs/commands/secondary-commands-reference.md` |
| GSD_ARCHITECTURE_SCAFFOLDING.md | `GSD_ARCHITECTURE_SCAFFOLDING.md` |
| core-commands-reference.md | `docs/commands/core-commands-reference.md` |
| operational-components-reference.md | `docs/operational-components-reference.md` |

### Source Reference Files

| Category | Path Pattern |
|----------|--------------|
| Command definitions | `commands/gsd/{command}.md` |
| Agent definitions | `agents/{agent}.md` |
| Templates | `get-shit-done/templates/{template}.md` |
| Workflows | `get-shit-done/workflows/{workflow}.md` |
| References | `get-shit-done/references/{reference}.md` |
| Agent reference docs | `docs/agents/{agent}-reference.md` |

### Tracker & Reports

| File | Path |
|------|------|
| Task Tracker | `docs/GSD_GAP_CLOSURE_TRACKER.md` |
| Completion Report | `docs/GSD_GAP_CLOSURE_REPORT.md` |
