---
description: Investigate and diagnose bugs and issues
agent: debug
model: zai-coding-plan/glm-5
---

Investigate and diagnose the following issue: $ARGUMENTS

## File Output

Save the debug report as a markdown file:
- **Location:** `./report/` folder
- **Filename format:** `DEBUG_YYYYmmdd_HHMMSS.md` (e.g., `DEBUG_20260225_143022.md`)
- Create the `./report` directory if it doesn't exist

## Debug Process

### Phase 1: Understand the Problem
1. What is the expected behavior?
2. What is the actual behavior?
3. When does it occur? (conditions, inputs)
4. Is it reproducible?
5. Any recent changes that could relate?

### Phase 2: Gather Information
- [ ] Read error messages and stack traces
- [ ] Check application logs
- [ ] Review relevant source code
- [ ] Check recent git commits
- [ ] Examine test results
- [ ] Verify environment configuration

### Phase 3: Isolate the Issue
- [ ] Create minimal reproduction
- [ ] Binary search through code
- [ ] Add logging/debugging statements
- [ ] Test hypotheses systematically

### Phase 4: Identify Root Cause
- [ ] Pinpoint exact location
- [ ] Understand why it happens
- [ ] Document the chain of events
- [ ] Verify the diagnosis

## Debug Report Format

```markdown
# 🔍 Debug Report

## Issue Summary
**Description:** [Brief description of the problem]
**Severity:** Critical | High | Medium | Low
**Status:** Diagnosed | Needs More Info | Cannot Reproduce

## Reproduction Steps
1. Step 1
2. Step 2
3. Step 3

## Evidence

### Error Messages/Stack Traces
```
[Paste relevant errors]
```

### Relevant Code Location
- **File:** `path/to/file.ts`
- **Lines:** 42-50
- **Function/Component:** `processPayment()`

## Root Cause Analysis

### The Problem
[Detailed explanation of what's wrong]

### Why It Happens
[Explanation of the underlying cause]

### Chain of Events
1. User triggers action X
2. System calls function Y
3. Function Y expects Z but receives W
4. This causes the error

## Recommended Fix Approach
[High-level suggestions for @fix agent]

## Additional Context
- Related files: [list]
- Dependencies involved: [list]
- Environment specifics: [if relevant]

## Verification
To verify the fix works:
1. [Test step 1]
2. [Test step 2]
```

## Common Bug Categories

| Category | Symptoms | Debug Approach |
|----------|----------|----------------|
| **Null Pointer** | "undefined is not a function", NPE | Check all object access, add guards |
| **Race Condition** | Intermittent failures, timing issues | Check async operations, add delays for testing |
| **Off-by-One** | Array bounds, loop issues | Check < vs <=, 0 vs 1 indexing |
| **Type Mismatch** | Unexpected behavior, silent failures | Verify types, add type checks |
| **State Issue** | Works once, fails after | Check state mutation, reset logic |
| **Memory Leak** | Slow degradation, OOM | Profile memory, check cleanup |
| **Integration** | External service failures | Check API responses, timeouts |
| **Configuration** | Works locally, fails deployed | Compare environments, check env vars |

Be systematic and methodical in your investigation.
