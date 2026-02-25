---
description: Create and run tests, output bug list for failures
agent: tester
model: zai-coding-plan/glm-5
---

## Configuration

<!-- USER: Edit these values as needed for your project -->
```yaml
test_coverage_target: 80        # Target test coverage percentage (e.g., 80 means 80%)
retry_attempts: 3               # Number of retry attempts when fix fails (e.g., 3 means try 3 times)
```

Create comprehensive tests for: $ARGUMENTS

## File Output

Save test reports as markdown files:
- **Location:** `./report/` folder
- **Filename format:** `TEST_REPORT_YYYYmmdd_HHMMSS.md` (e.g., `TEST_REPORT_20260225_143022.md`)
- Create the `./report` directory if it doesn't exist

## Test Requirements

### 1. Unit Tests
- [ ] Happy path scenarios
- [ ] Edge cases (empty, null, boundary values)
- [ ] Error conditions
- [ ] Invalid input handling
- [ ] All branches and paths

### 2. Integration Tests (if applicable)
- [ ] Component interactions
- [ ] Database operations
- [ ] API endpoints
- [ ] External service integrations

### 3. Test Structure
Use AAA pattern:
- **Arrange**: Set up test data
- **Act**: Execute code under test
- **Assert**: Verify results

## REQUIRED Output Format

### If Bugs Found - Output Bug List:

```markdown
# 🐛 Bug List for @fix

## Summary
**Tests Created:** [count]
**Tests Run:** [count]
**Tests Passed:** [count]
**Tests Failed:** [count]
**Bugs Found:** [count]

## Test Phase Tracking

| Phase | Failed | Fixed | Status |
|-------|--------|-------|--------|
| Initial Run | [count] | - | ❌ Fail |
| After Fix 1 | [count] | [count] | [Pass/Fail] |
| **Final** | **[count]** | **[total fixed]** | **[Pending]** |

## Bugs

### BUG-001: [Bug Title]
- **Severity:** 🔴 Critical | 🟡 High | 🟢 Medium | 🔵 Low
- **Type:** Logic Error | Type Error | Null Reference | Race Condition | Performance | Integration
- **File:** `path/to/file.ts`
- **Test Case:** `should [expected behavior]`
- **Description:** [What is failing]
- **Expected:** [What should happen]
- **Actual:** [What actually happens]
- **Reproduction:**
```typescript
it('should handle null input', () => {
  const result = processUser(null);  // Throws
  expect(result).toBeNull();
});
```
- **Suggested Fix:**
```typescript
// Fix code here
function processUser(user: User | null): Result | null {
  if (!user) return null;
  // ... rest of logic
}
```

[... repeat for each bug ...]

## Bug Priority Order
1. BUG-XXX (Critical - [reason])
2. BUG-XXX (High - [reason])

## Files to Modify
| File | Bugs | Priority |
|------|------|----------|
| `src/file.ts` | 2 | High |

---
**Next:** `@fix please fix all bugs from the test results above`
```

### If All Tests Pass - Output Test Report:

```markdown
# ✅ Test Report

## Summary
**Tests Created:** [count]
**Tests Run:** [count]
**Tests Passed:** [count] (100%)
**Coverage:** [percentage]%

## Test Phase Tracking

| Phase | Failed | Fixed | Status |
|-------|--------|-------|--------|
| Initial Run | 0 | - | ✅ Pass |
| **Final** | **0** | **0** | **✅ Pass** |

## Tests Created
| Test File | Tests | Coverage |
|-----------|-------|----------|
| `file.test.ts` | 15 | 92% |

## Coverage Breakdown
- Statements: X%
- Branches: X%
- Functions: X%
- Lines: X%

**Status:** ✅ All tests passing, no bugs found
```

## Test Template

```typescript
describe('ComponentName', () => {
  it('should return expected result for valid input', () => {
    const result = method(validInput);
    expect(result).toEqual(expected);
  });

  it('should handle null input gracefully', () => {
    const result = method(null);
    expect(result).toBeNull();
  });

  it('should throw error for invalid input', () => {
    expect(() => method(invalidInput)).toThrow();
  });
});
```

Focus on meaningful tests. If bugs found, hand off to @fix agent.
