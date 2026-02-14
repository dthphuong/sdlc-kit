---
name: sdlc-workflow
description: Complete Software Development Life Cycle workflow orchestration
---
# SDLC Workflow

Comprehensive guide for managing the complete software development life cycle from requirements to deployment.

## Overview

This skill provides structured workflows for each phase of the SDLC, ensuring quality and consistency across all development activities.

## SDLC Phases

### Phase 1: Planning & Requirements
**Duration:** 10-15% of project time
**Owner:** @planner
**Activities:**
- Requirements gathering
- Stakeholder interviews
- User story creation
- Acceptance criteria definition
- Risk assessment
- Initial estimation

**Deliverables:**
- [ ] Requirements document
- [ ] User stories with acceptance criteria
- [ ] Initial risk register
- [ ] Project timeline

**Quality Gates:**
- [ ] All stakeholders signed off
- [ ] Requirements are testable
- [ ] Dependencies identified
- [ ] Budget approved

### Phase 2: Design & Architecture
**Duration:** 15-20% of project time
**Owner:** @planner + @researcher
**Activities:**
- System architecture design
- Database schema design
- API contract definition
- UI/UX wireframes
- Technology stack selection
- Security planning

**Deliverables:**
- [ ] Architecture document
- [ ] Database design
- [ ] API specifications
- [ ] UI/UX mockups
- [ ] Technical decisions log

**Quality Gates:**
- [ ] Architecture review completed
- [ ] Security review passed
- [ ] Performance requirements addressed
- [ ] Scalability considered

### Phase 3: Development
**Duration:** 40-50% of project time
**Owner:** Development team
**Activities:**
- Feature implementation
- Code review
- Unit testing
- Integration development
- Documentation

**Deliverables:**
- [ ] Working code
- [ ] Unit tests
- [ ] Code documentation
- [ ] Technical documentation

**Quality Gates:**
- [ ] Code reviewed and approved
- [ ] Tests passing (>80% coverage)
- [ ] No critical security issues
- [ ] Documentation complete

### Phase 4: Testing
**Duration:** 15-20% of project time
**Owner:** @tester
**Activities:**
- Integration testing
- System testing
- Performance testing
- Security testing
- User acceptance testing
- Regression testing

**Deliverables:**
- [ ] Test cases
- [ ] Test results
- [ ] Bug reports
- [ ] Test coverage report

**Quality Gates:**
- [ ] All test cases executed
- [ ] No critical bugs open
- [ ] Performance benchmarks met
- [ ] UAT signed off

### Phase 5: Deployment
**Duration:** 5-10% of project time
**Owner:** @devops
**Activities:**
- Environment setup
- Deployment automation
- Data migration
- Monitoring setup
- Rollback planning

**Deliverables:**
- [ ] Deployment scripts
- [ ] Infrastructure as Code
- [ ] Monitoring dashboards
- [ ] Runbooks

**Quality Gates:**
- [ ] Staging deployment successful
- [ ] Smoke tests passing
- [ ] Monitoring active
- [ ] Rollback tested

### Phase 6: Maintenance & Support
**Duration:** Ongoing
**Owner:** @devops + Development team
**Activities:**
- Bug fixes
- Performance optimization
- Security patches
- Feature enhancements
- Documentation updates

**Deliverables:**
- [ ] Bug fixes
- [ ] Performance reports
- [ ] Security updates
- [ ] Updated documentation

## Workflow Templates

### Feature Development Workflow

```markdown
## Feature: [Name]

### Sprint Planning
- [ ] Story estimated
- [ ] Tasks identified
- [ ] Dependencies mapped
- [ ] Sprint goal defined

### Development Cycle
Day 1-2: Design & Setup
- [ ] Create feature branch
- [ ] Implement design
- [ ] Set up tests

Day 3-5: Implementation
- [ ] Core functionality
- [ ] Unit tests
- [ ] Integration

Day 6-7: Review & Polish
- [ ] Code review
- [ ] Address feedback
- [ ] Documentation

### Delivery
- [ ] Merge to develop
- [ ] Deploy to staging
- [ ] QA verification
- [ ] Merge to main
```

### Bug Fix Workflow

```markdown
## Bug: [Description]

### Triage (Day 1)
- [ ] Bug reproduced
- [ ] Severity assessed
- [ ] Root cause identified
- [ ] Fix approach decided

### Fix Implementation (Day 2)
- [ ] Create hotfix branch
- [ ] Implement fix
- [ ] Add regression test
- [ ] Code review

### Deployment (Day 3)
- [ ] Deploy to staging
- [ ] Verify fix
- [ ] Deploy to production
- [ ] Monitor for issues
```

### Release Workflow

```markdown
## Release: v[Version]

### Pre-Release (Week -1)
- [ ] Feature freeze
- [ ] Code complete
- [ ] Regression testing
- [ ] Security audit
- [ ] Documentation updated

### Release Prep (Day -2)
- [ ] Release notes drafted
- [ ] Changelog updated
- [ ] Version bumped
- [ ] Release branch created

### Release Day
- [ ] Final smoke tests
- [ ] Deploy to production
- [ ] Monitor metrics
- [ ] Announce release
- [ ] Update documentation
```

## Estimation Guidelines

### Story Points Scale
- **1 point:** Simple change, < 2 hours
- **2 points:** Straightforward, 2-4 hours
- **3 points:** Moderate complexity, 4-8 hours
- **5 points:** Complex, 1-2 days
- **8 points:** Very complex, 2-3 days
- **13 points:** Epic, needs breakdown

### Estimation Factors
- Complexity of logic
- Integration requirements
- Testing effort
- Documentation needs
- Unknowns and risks

## Risk Management

### Common Risks
| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Scope creep | High | High | Strict change control |
| Technical debt | Medium | Medium | Regular refactoring sprints |
| Resource availability | Medium | High | Cross-training, documentation |
| Integration issues | Medium | High | Early integration testing |
| Performance problems | Low | High | Performance testing in CI |

### Risk Response Plan
1. **Identify:** Regular risk assessment meetings
2. **Analyze:** Impact and probability assessment
3. **Plan:** Mitigation strategies
4. **Monitor:** Weekly risk review
5. **Act:** Execute mitigation when triggered

## Communication Plan

### Daily
- Standup meetings (15 min)
- Blocker resolution

### Weekly
- Sprint review
- Retrospective
- Planning session

### Milestone
- Demo to stakeholders
- Architecture review
- Security review

## Metrics & KPIs

### Development Metrics
- Velocity (story points/sprint)
- Cycle time (days)
- Lead time (days)
- Code coverage (%)
- Bug rate (bugs/feature)

### Quality Metrics
- Defect density
- Test coverage
- Code review turnaround
- Documentation completeness

### Delivery Metrics
- On-time delivery rate
- Sprint completion rate
- Release frequency
- Mean time to recovery

## Tools & Templates

### Required Templates
- Requirements document
- Architecture decision record
- Test plan
- Release checklist
- Post-mortem report

### Recommended Tools
- Issue tracking: Jira, GitHub Issues
- Documentation: Confluence, Notion
- Diagrams: Lucidchart, Draw.io
- Communication: Slack, Teams
- Version control: Git

## Best Practices

1. **Start with requirements** - Don't skip planning
2. **Design before coding** - Architecture first
3. **Test early and often** - Continuous testing
4. **Review everything** - Code, design, docs
5. **Document decisions** - Future you will thank you
6. **Automate repetitive tasks** - CI/CD is essential
7. **Monitor and measure** - Data-driven decisions
8. **Iterate and improve** - Continuous improvement
