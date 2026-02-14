# SDLC Agent Team & Skills Reference

Complete mapping of agents to skills and their usage in the Software Development Life Cycle.

## Overview

This project includes **10 specialized agents** and **10 corresponding skills** that work together to cover the complete SDLC.

## Agent → Skill Mapping

| Agent | Primary Skill | Purpose | Usage |
|-------|--------------|---------|-------|
| **orchestrator** | `sdlc-workflow` | Team coordination & SDLC management | @orchestrator |
| **planner** | `requirements-analysis` | Requirements & architecture | @planner |
| **researcher** | `technology-evaluation` | Tech research & comparison | @researcher |
| **debug** | `debugging` | Issue investigation & root cause analysis | @debug |
| **fix** | `bug-fixing` | Implementing safe bug fixes | @fix |
| **reviewer** | `code-review` | Code quality & security | @reviewer |
| **tester** | `testing-strategies` | QA & test creation | @tester |
| **documenter** | `technical-writing` | Documentation | @documenter |
| **git-manager** | `git-workflows` | Version control | @git-manager |
| **devops** | `devops-automation` | CI/CD & deployment | @devops |

## Skills Overview

### 1. SDLC Workflow
**Location:** `.opencode/skills/sdlc-workflow/`
**Used by:** @orchestrator
**Topics:**
- Complete SDLC phases
- Workflow templates
- Estimation guidelines
- Risk management
- Communication plans
- Metrics & KPIs

### 2. Requirements Analysis
**Location:** `.opencode/skills/requirements-analysis/`
**Used by:** @planner
**Topics:**
- Gathering techniques
- User stories
- Use cases
- Requirements workshops
- Prioritization frameworks
- Documentation templates

### 3. Technology Evaluation
**Location:** `.opencode/skills/technology-evaluation/`
**Used by:** @researcher
**Topics:**
- Evaluation frameworks
- Comparison matrices
- Cost analysis
- Proof of concept
- Decision criteria
- Research sources

### 4. Debugging
**Location:** `.opencode/skills/debugging/`
**Used by:** @debug
**Topics:**
- Debug methodology
- Root cause analysis
- Debug techniques
- Error analysis
- Environment debugging
- Debug tools reference

### 5. Bug Fixing
**Location:** `.opencode/skills/bug-fixing/`
**Used by:** @fix
**Topics:**
- Fix patterns by bug type
- Safe code changes
- Regression testing
- Error handling patterns
- Risk mitigation
- Fix verification

### 6. Code Review
**Location:** `.opencode/skills/code-review/`
**Used by:** @reviewer
**Topics:**
- Review checklists
- Security review
- Performance review
- Feedback guidelines
- Severity levels
- Code smells

### 7. Testing Strategies
**Location:** `.opencode/skills/testing-strategies/`
**Used by:** @tester
**Topics:**
- Testing pyramid
- Test types
- Test patterns
- Coverage strategies
- Test organization
- Testing tools

### 8. Technical Writing
**Location:** `.opencode/skills/technical-writing/`
**Used by:** @documenter
**Topics:**
- Documentation types
- Writing principles
- Templates (README, API, Tutorial)
- Code documentation
- Style guide

### 9. Git Workflows
**Location:** `.opencode/skills/git-workflows/`
**Used by:** @git-manager
**Topics:**
- Branching strategies
- Commit guidelines
- Common workflows
- Command reference
- Conflict resolution
- Hooks

### 10. DevOps Automation
**Location:** `.opencode/skills/devops-automation/`
**Used by:** @devops
**Topics:**
- CI/CD pipelines
- Docker containerization
- Kubernetes deployment
- Deployment strategies
- Infrastructure as Code
- Monitoring

## SDLC Phase Coverage

### Phase 1: Planning
**Agents:** @orchestrator + @planner + @researcher
**Skills:** sdlc-workflow, requirements-analysis, technology-evaluation
**Activities:**
- Requirements gathering
- Technology evaluation
- Architecture design
- Project planning

### Phase 2: Development
**Agents:** @git-manager + developers
**Skills:** git-workflows
**Activities:**
- Feature implementation
- Code organization
- Version control

### Phase 3: Debugging & Fixing
**Agents:** @debug + @fix
**Skills:** debugging, bug-fixing
**Activities:**
- Issue investigation
- Root cause analysis
- Bug fix implementation
- Regression testing

### Phase 4: Testing
**Agents:** @tester
**Skills:** testing-strategies
**Activities:**
- Test creation
- Test execution
- Coverage analysis

### Phase 5: Review
**Agents:** @reviewer
**Skills:** code-review
**Activities:**
- Code quality review
- Security audit
- Performance review

### Phase 6: Documentation
**Agents:** @documenter
**Skills:** technical-writing
**Activities:**
- API documentation
- User guides
- Technical docs

### Phase 7: Deployment
**Agents:** @devops + @git-manager
**Skills:** devops-automation, git-workflows
**Activities:**
- CI/CD pipeline
- Container deployment
- Release management

## How to Use

### Method 1: Let Agents Use Skills Automatically

Agents automatically reference their corresponding skills when working:

```
You: "Review the authentication code"

@reviewer accesses code-review skill and applies:
- Security checklist
- Performance review
- Code quality guidelines
```

### Method 2: Direct Skill Reference

You can reference skills explicitly:

```
"Use testing-strategies skill to create a comprehensive test plan"
"Follow git-workflows skill for this release process"
"Apply requirements-analysis skill to gather user requirements"
```

### Method 3: Combined Agent + Skill

Combine agents with specific skill aspects:

```
"@reviewer use the security section from code-review skill to audit authentication"
"@tester focus on E2E testing from testing-strategies skill"
"@devops implement blue/green deployment from devops-automation skill"
```

## Typical Workflows

### Feature Development

```mermaid
graph LR
    A[User Request] --> B[@orchestrator]
    B --> C[@planner]
    C --> D[@researcher]
    D --> E[Implementation]
    E --> F[@tester]
    F -->|Bug List| G{@fix}
    G -->|Fixes| F
    F -->|All Pass| H[@reviewer]
    H -->|Issue List| G
    G -->|Fixes| H
    H -->|Approved| I[@documenter]
    I --> J[@git-manager]
    J --> K[@devops]
```

**Skills Used:**
1. sdlc-workflow (orchestration)
2. requirements-analysis (planning)
3. technology-evaluation (research)
4. debugging (investigation)
5. bug-fixing (implementation)
6. testing-strategies (testing)
7. code-review (review)
8. technical-writing (docs)
9. git-workflows (version control)
10. devops-automation (deployment)

### Bug Fix Workflow

```
1. Report bug
2. @debug investigates root cause (debugging)
   → Outputs Debug Report
3. @fix implements the fix (bug-fixing)
   → Outputs Fix Report
4. @tester creates/runs regression tests (testing-strategies)
   → If bugs found: Outputs Bug List → @fix fixes → Repeat
   → If all pass: Continue
5. @reviewer reviews fix (code-review)
   → If issues found: Outputs Issue List → @fix fixes → Repeat
   → If approved: Continue
6. @git-manager creates hotfix (git-workflows)
7. @devops deploys fix (devops-automation)
```

### Review → Fix Workflow

```
@reviewer                    @fix                      @tester
    │                          │                          │
    ├─ Review code             │                          │
    ├─ Find issues             │                          │
    ├─ Output Issue List ─────►│                          │
    │                          ├─ Parse Issue List        │
    │                          ├─ Fix Critical issues     │
    │                          ├─ Fix Important issues    │
    │                          ├─ Output Fix Report       │
    │                          │                          │
    │                          ├─ Hand off ──────────────►│
    │                          │                          ├─ Run tests
    │                          │                          ├─ If bugs: Bug List → @fix
    │                          │                          └─ If pass: Done
```

### Test → Fix Workflow

```
@tester                      @fix                      @reviewer
    │                          │                          │
    ├─ Create tests            │                          │
    ├─ Run tests               │                          │
    ├─ Find bugs               │                          │
    ├─ Output Bug List ───────►│                          │
    │                          ├─ Parse Bug List          │
    │                          ├─ Fix Critical bugs       │
    │                          ├─ Fix High/Medium bugs    │
    │                          ├─ Output Fix Report       │
    │                          │                          │
    ├─ Re-run tests ◄──────────┤                          │
    ├─ If bugs: repeat ───────►│                          │
    └─ If pass: hand off ─────────────────────────────────►│
                                                       (optional review)
```

### Release Process

```
1. @orchestrator coordinates (sdlc-workflow)
2. @tester runs regression (testing-strategies)
3. @reviewer performs security audit (code-review)
4. @documenter updates docs (technical-writing)
5. @git-manager creates release (git-workflows)
6. @devops deploys to production (devops-automation)
```

## Skill Integration Points

### Shared Concepts

| Concept | Primary Skill | Referenced By |
|---------|--------------|---------------|
| Quality gates | sdlc-workflow | All agents |
| Testing requirements | requirements-analysis | tester |
| Code standards | code-review | git-manager |
| Documentation templates | technical-writing | all |
| CI/CD integration | devops-automation | git-manager |
| Review process | code-review | orchestrator |

### Cross-References

Skills reference each other:
- `sdlc-workflow` → All skills (orchestration)
- `requirements-analysis` → `testing-strategies` (test requirements)
- `code-review` → `testing-strategies` (test coverage)
- `debugging` → `bug-fixing` (diagnosis to fix)
- `bug-fixing` → `testing-strategies` (regression tests)
- `git-workflows` → `devops-automation` (CI/CD)
- `technical-writing` → All skills (documentation)

## Quick Reference Card

### When to Use Which Skill

| Need | Skill | Agent |
|------|-------|-------|
| Plan a feature | requirements-analysis | @planner |
| Evaluate technology | technology-evaluation | @researcher |
| Debug an issue | debugging | @debug |
| Fix a bug | bug-fixing | @fix |
| Review code | code-review | @reviewer |
| Create tests | testing-strategies | @tester |
| Write documentation | technical-writing | @documenter |
| Manage branches | git-workflows | @git-manager |
| Set up CI/CD | devops-automation | @devops |
| Coordinate team | sdlc-workflow | @orchestrator |

### Common Commands

```bash
# Planning
/plan feature-name           # Uses requirements-analysis

# Debugging
/debug issue-description     # Uses debugging

# Fixing
/fix bug-description         # Uses bug-fixing

# Review
/review src/module           # Uses code-review

# Testing
/test component-name         # Uses testing-strategies

# Documentation
/document api-reference      # Uses technical-writing

# Deployment
/deploy production           # Uses devops-automation

# Research
/research technology         # Uses technology-evaluation
```

## File Structure

```
.opencode/
├── agents/                  # Agent definitions
│   ├── orchestrator.md
│   ├── planner.md
│   ├── researcher.md
│   ├── debug.md
│   ├── fix.md
│   ├── reviewer.md
│   ├── tester.md
│   ├── documenter.md
│   ├── git-manager.md
│   └── devops.md
├── skills/                  # Skill knowledge bases
│   ├── sdlc-workflow/
│   ├── requirements-analysis/
│   ├── technology-evaluation/
│   ├── debugging/
│   ├── bug-fixing/
│   ├── code-review/
│   ├── testing-strategies/
│   ├── technical-writing/
│   ├── git-workflows/
│   └── devops-automation/
├── commands/                # Quick commands
│   ├── plan.md
│   ├── debug.md
│   ├── fix.md
│   ├── review.md
│   ├── test.md
│   ├── document.md
│   ├── deploy.md
│   └── research.md
└── AGENTS.md               # Team documentation
```

## Best Practices

1. **Let orchestrator coordinate** for complex tasks
2. **Use skills explicitly** for specific needs
3. **Combine agents** for comprehensive coverage
4. **Reference skills** when you need specific guidance
5. **Use commands** for quick actions
6. **Keep skills updated** as practices evolve

## Summary

The SDLC Agent Team provides:
- ✅ **10 Specialized Agents** - Expert roles for each phase
- ✅ **10 Comprehensive Skills** - Deep knowledge bases
- ✅ **8 Quick Commands** - Fast access to common tasks
- ✅ **Complete SDLC Coverage** - From planning to deployment
- ✅ **Integrated Workflow** - Agents and skills work together
- ✅ **Dedicated Debug & Fix** - Streamlined bug resolution pipeline

Your team is ready for any software development task! 🚀
