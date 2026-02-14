---
description: Implement fixes for issues from review or bugs from tests
agent: fix
model: zai-coding-plan/glm-5
---

Implement fixes for: $ARGUMENTS

## Input Sources

This command expects an Issue List or Bug List from:
- `@reviewer` → Issue List (ISSUE-001, ISSUE-002, etc.)
- `@tester` → Bug List (BUG-001, BUG-002, etc.)

## Fix Process

### Phase 1: Parse Input
```
1. Extract all issues/bugs
2. Sort by severity (Critical → Important → Suggestion)
3. Group by file
```

### Phase 2: Implement Fixes
```
For each issue/bug (Critical first):
1. Read affected file
2. Locate problematic code
3. Apply minimal fix
4. Verify fix works
```

### Phase 3: Verify
```
1. Run all tests
2. Check for regressions
3. Confirm all issues resolved
```

## REQUIRED Output Format

```markdown
# 🔧 Fix Report

## Input Summary
**Source:** @reviewer | @tester
**Total Issues/Bugs:** [count]
**Fixed:** [count] | **Skipped:** [count]

## Fixes Implemented

### ISSUE-001/BUG-001: [Title] ✅
- **File:** `src/file.ts`
- **Lines:** 42-50
- **Fix Applied:**
```diff
- // Before
+ // After
```
- **Status:** ✅ Fixed

[... repeat for all fixes ...]

## Summary

| ID | Title | Severity | Status |
|----|-------|----------|--------|
| ISSUE-001 | [title] | 🔴 Critical | ✅ Fixed |

## Files Modified
| File | Changes | Lines |
|------|---------|-------|
| `src/file.ts` | 2 fixes | +5, -2 |

## Verification
- [x] All fixes implemented
- [x] All tests passing
- [x] No regressions

---
**Next:** `@tester please verify the fixes`
```

## Fix Principles

1. **Fix Critical issues first**
2. **Make minimal changes**
3. **Address root cause**
4. **Add regression tests**

Implement clean, safe fixes for all issues/bugs.
