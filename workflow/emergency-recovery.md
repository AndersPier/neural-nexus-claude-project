# Emergency Recovery Procedures

## Context Loss Recovery

### When to Use
- Claude loses track of current project state
- Conversation context becomes unclear
- Previous decisions seem forgotten
- Development momentum stalls due to confusion

### Emergency Context Recovery Protocol

```
# Emergency Context Recovery

I've lost context about this Neural Nexus project's current state. Please help me reconstruct our situation:

## 🔍 CONVERSATION ANALYSIS
**Recent History Review:**
- Analyze the last 10-15 conversation exchanges in this project
- Identify what we were working on most recently
- Extract any recent technical decisions or changes made
- Note any blockers, issues, or priorities mentioned
- Determine current development stage (Exploration/Prototype/Development/Production)

## 📋 PROJECT STATE RECONSTRUCTION
**Current Development Status:**
- What stage are we in and what are the success criteria?
- What's our current sprint or focus area?
- What features are completed vs in-progress vs planned?
- What's our established technology stack and architecture approach?
- What performance targets and constraints are we working within?

**Recent Technical Decisions:**
- What architectural choices have we made recently?
- Are there any new patterns or approaches we've adopted?
- What trade-offs have we accepted in recent sessions?
- Any specific implementation details or constraints to remember?

## 📚 KNOWLEDGE BASE ASSESSMENT
**Documentation Gaps:**
- What important information isn't documented that should be?
- Are there recent decisions that need to be captured in our knowledge base?
- What patterns or learnings should be added for future reference?
- Any outdated information that needs updating?

## 🎯 IMMEDIATE NEXT STEPS
**Priority Clarification:**
- What should be our immediate focus for this session?
- Are there any urgent blockers or issues to address?
- What's the most important task to complete next?
- Any time-sensitive decisions or deadlines approaching?

## 📝 RECOMMENDED UPDATES
**Project Configuration Updates:**
- Does our project description need updating based on current reality?
- Should our custom instructions be revised for current stage?
- What knowledge base files need immediate attention or updates?
- Any templates or workflows that need refinement?

Provide a comprehensive reconstruction to get us back on track efficiently.
```

### Post-Recovery Actions
1. **Immediate Documentation**: Update knowledge base with recovered context
2. **Decision Logging**: Record any clarified or rediscovered decisions
3. **Workflow Adjustment**: Refine processes to prevent future context loss
4. **Knowledge Base Cleanup**: Remove outdated or conflicting information

## Performance Degradation Recovery

### When to Use
- Game running significantly slower than target frame rates
- Memory usage increasing over time or exceeding limits
- User experience degraded compared to previous versions
- Performance issues blocking further development

### Performance Recovery Protocol

```
# Performance Degradation Analysis and Recovery

Neural Nexus performance has degraded below our targets. Please help identify and resolve performance issues:

## 📊 PERFORMANCE BASELINE ESTABLISHMENT
**Historical Performance Review:**
- What were our original performance targets for desktop and mobile?
- What benchmarks did we establish in earlier development stages?
- When did we last measure performance comprehensively?
- What were our best-ever performance metrics and under what conditions?

**Current Performance Reality:**
- What are our current measured performance metrics across target devices?
- Where specifically are we seeing degradation (frame rate, memory, load time)?
- How severe is the performance impact on actual user experience?
- Are there specific features, levels, or operations that are particularly slow?

## 🔍 DEGRADATION ANALYSIS
**Timeline Investigation:**
- When did performance degradation begin (gradual vs sudden)?
- What changes, features, or code modifications coincided with performance decline?
- Can we identify specific commits, features, or decisions that impacted performance?
- Are there external factors (browser updates, device changes) affecting results?

**Root Cause Investigation:**
- Analyze database query performance and optimization opportunities
- Review frontend bundle size, loading performance, and asset optimization
- Examine API response times, bottlenecks, and potential caching improvements
- Investigate memory usage patterns and potential leaks or inefficient allocation
- Assess network request efficiency, caching effectiveness, and CDN performance

## 🎯 PERFORMANCE RECOVERY PLAN
**Quick Wins (Can implement immediately):**
1. [Optimization] - [Expected impact] - [Implementation time]
2. [Optimization] - [Expected impact] - [Implementation time]

**Short-term Improvements (Next 1-2 weeks):**
1. [Optimization] - [Expected impact] - [Implementation effort]
2. [Optimization] - [Expected impact] - [Implementation effort]

**Long-term Performance Strategy (Next month+):**
1. [Optimization] - [Expected impact] - [Implementation effort]
2. [Optimization] - [Expected impact] - [Implementation effort]

## 📈 MONITORING AND PREVENTION
**Performance Monitoring Setup:**
- What metrics should we track continuously to detect future regressions?
- How can we establish automated alerts for performance degradation?
- What benchmarking process should be part of our regular development workflow?

**Development Process Improvements:**
- How can we catch performance issues during development before they reach users?
- What performance testing should be mandatory before deploying changes?
- How can we make performance considerations a standard part of code review?

## 📝 DOCUMENTATION UPDATES
**Performance Documentation:**
- Update performance targets and benchmarks based on current capabilities
- Document optimization techniques that work specifically for our technology stack
- Create performance troubleshooting guides for common issues and solutions

Provide a specific, measurable plan to restore performance and maintain it going forward.
```

## Technical Debt Crisis Recovery

### When to Use
- Development velocity significantly slowed by accumulated technical debt
- Code quality degraded to point where adding features is extremely difficult
- Bug frequency increased due to complex, unmaintainable code
- Team morale suffering due to frustrating development experience

### Technical Debt Crisis Protocol

```
# Technical Debt Crisis Management and Recovery

Technical debt in Neural Nexus has accumulated to the point where it's significantly impacting our development velocity and code quality. Please help assess and manage this debt systematically:

## 📊 DEBT ASSESSMENT AND CATALOGING
**Comprehensive Debt Inventory:**
- Identify all areas of significant technical debt in our codebase by category
- Categorize debt by type: code quality, architecture, security, performance, documentation, testing
- Assess the age and growth rate of each debt item over our development timeline
- Estimate the current impact of each debt area on development velocity and system reliability

**Debt Impact Analysis:**
- How is current technical debt blocking or significantly slowing new feature development?
- What features, improvements, or optimizations are we unable to implement due to existing debt?
- How is accumulated debt affecting code reliability, bug rates, and system stability?
- What's the risk assessment of debt causing system failures, security vulnerabilities, or user experience problems?

## ⚖️ DEBT PRIORITIZATION MATRIX
**Critical Debt (Immediate Action Required - This Sprint):**
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Risk if ignored: Critical/High/Med]
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Risk if ignored: Critical/High/Med]

**High-Priority Debt (Address Within 2-4 Weeks):**
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Business justification]
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Business justification]

**Manageable Debt (Plan for Future Sprints):**
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Timeline to address]
- [Debt item] - [Impact: High/Med/Low] - [Effort: High/Med/Low] - [Timeline to address]

## 🚀 DEBT REDUCTION STRATEGY
**Emergency Debt Sprint (Immediate - 1 week):**
- Focus exclusively on critical debt that's completely blocking progress
- Implement quick wins that provide immediate relief to development workflow
- Apply minimum viable fixes to restore basic development velocity and system stability

**Systematic Debt Reduction (2-4 weeks):**
- Address high-priority debt systematically using dedicated sprint capacity
- Implement preventive measures and development practices to avoid creating new debt
- Establish ongoing debt monitoring, limits, and regular assessment processes

**Long-term Debt Management (Ongoing Process):**
- Implement regular debt assessment and reduction cycles as part of development workflow
- Establish team practices and development standards that minimize debt creation
- Create sustainable balance between feature development and debt management activities

## 🛡️ DEBT PREVENTION MEASURES
**Development Process Improvements:**
- Implement code review practices specifically designed to catch and prevent debt early
- Establish "Definition of Done" criteria that includes debt considerations and quality gates
- Schedule regular architecture reviews, refactoring time, and technical improvement cycles

**Technical Practices and Standards:**
- Implement automated testing frameworks to prevent regression debt and maintain code quality
- Establish documentation requirements and standards for new features and architectural changes
- Define and enforce performance, security, and maintainability standards for all new code

## 📈 PROGRESS TRACKING AND ACCOUNTABILITY
**Debt Metrics and Monitoring:**
- How will we measure technical debt reduction progress objectively?
- What early warning indicators should we monitor to prevent debt accumulation?
- How will we track and maintain the balance between feature development and debt management?

**Success Criteria and Milestones:**
- Define specific, measurable goals for debt reduction with clear timelines
- Establish project milestones and checkpoints to assess progress and adjust strategy
- Identify clear success criteria for when we've successfully managed the debt crisis

Provide a concrete, time-bound plan to systematically reduce technical debt while maintaining development momentum and preventing future debt accumulation.
```

### Post-Recovery Actions
1. **Process Integration**: Make debt prevention part of regular workflow
2. **Team Training**: Ensure everyone understands debt prevention practices
3. **Monitoring Setup**: Implement ongoing debt tracking and alerts
4. **Regular Reviews**: Schedule periodic debt assessment sessions

## Best Practices for Emergency Prevention

### Proactive Measures
1. **Regular Health Checks**: Weekly project health assessments
2. **Documentation Discipline**: Update docs immediately when making decisions
3. **Decision Tracking**: Maintain clear decision history with rationale
4. **Context Preservation**: Never skip session end consolidation
5. **Performance Monitoring**: Continuous performance tracking and alerting

### Early Warning Systems
```javascript
// Emergency warning indicators to watch for
const emergencyIndicators = {
  contextLoss: [
    'Repeating previously answered questions',
    'Contradicting earlier decisions', 
    'Unclear about current project state',
    'Asking for information already provided'
  ],
  
  performanceDrift: [
    'Frame rate below targets consistently',
    'Memory usage trending upward',
    'User complaints about responsiveness',
    'Load times increasing over time'
  ],
  
  technicalDebt: [
    'Feature development velocity slowing',
    'Bug frequency increasing',
    'Code changes requiring extensive refactoring',
    'Team avoiding certain areas of codebase'
  ]
};
```

### Recovery Success Metrics
- **Context Recovery**: Clear understanding of current state and priorities
- **Performance Recovery**: Metrics back within target ranges
- **Debt Recovery**: Development velocity restored, bug frequency reduced
- **Process Improvement**: Prevention measures implemented and working

Remember: Emergency recovery is about getting back on track quickly, not perfect solutions. Focus on immediate restoration first, then systematic improvement.