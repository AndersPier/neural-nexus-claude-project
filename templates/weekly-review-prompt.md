# Weekly Review Prompt Template

Use this prompt every Friday to assess project health and plan ahead:

```
Neural Nexus weekly project review:

## 📈 PROGRESS SUMMARY
**Features Completed This Week:**
- [List completed features with brief description]

**Development Velocity:**
- [Faster/Steady/Slower than last week]
- [Explanation of velocity changes]

**Blockers Resolved:**
- [Issues that were solved this week]

**New Blockers Identified:**
- [Issues that came up this week]

## 🏗️ ARCHITECTURE & CODE HEALTH
**New Patterns Introduced:**
- [Any new coding patterns or architectural decisions]

**Technical Debt Status:**
- **Created:** [New debt incurred this week]
- **Resolved:** [Debt paid down this week]
- **Overall Level:** [Low/Medium/High with trend]

**Performance Impact:**
- [Any performance changes from new code]

**Security Considerations:**
- [New security implications or improvements]

## 📚 KNOWLEDGE BASE HEALTH
**Documentation Needing Updates:**
- [Outdated docs identified]

**New Documentation Required:**
- [Patterns or decisions to document]

**Knowledge Gaps Identified:**
- [Areas where we need better documentation]

## 📅 NEXT WEEK PLANNING
**Priority 1 (Must Complete):**
1. [Task] - [Estimated hours] - [Why critical]

**Priority 2 (Should Complete):**
1. [Task] - [Estimated hours] - [Business value]

**Priority 3 (Nice to Have):**
1. [Task] - [Estimated hours] - [Future benefit]

## ⚠️ RISK ASSESSMENT
**Potential Issues:**
- [Risk] → [Mitigation strategy]
- [Risk] → [Mitigation strategy]

**Dependency Concerns:**
- [External dependency] → [Backup plan]

Format response as structured markdown for easy knowledge base addition.
```

## Usage Guidelines

### When to Use
- **Every Friday** - End of week review and planning
- **Before stage transitions** - Comprehensive assessment
- **After major milestones** - Project health check
- **When feeling stuck** - Identify blockers and solutions

### How to Use
1. **Be Honest**: Realistic assessment of progress and challenges
2. **Include Metrics**: Specific numbers where possible (frame rates, completion times)
3. **Plan Realistically**: Set achievable goals for next week
4. **Document Decisions**: Capture reasoning behind architectural choices
5. **Assess Risks**: Identify potential problems before they become critical

### Quality Example

```
## 📈 PROGRESS SUMMARY
**Features Completed This Week:**
- Web Audio API integration with 5 sound effects (connect, complete, error, ambient, success)
- Save system using localStorage with progress persistence across sessions
- Tutorial overlay system for first-time players with interactive guidance

**Development Velocity:**
- Faster than last week (completed 3 major features vs 2 last week)
- Benefiting from established patterns and workflow efficiency

**Blockers Resolved:**
- Audio latency issues on mobile Safari resolved with Web Audio context initialization
- Touch event conflicts with scroll gestures fixed using passive: false

**New Blockers Identified:**
- localStorage size limits becoming concern with detailed progress tracking
- Level generation algorithm needs optimization for complex patterns

## 🏗️ ARCHITECTURE & CODE HEALTH
**New Patterns Introduced:**
- Audio manager singleton pattern for centralized sound control
- Observer pattern for game state changes and UI updates

**Technical Debt Status:**
- **Created:** Temporary hardcoded audio file paths (needs asset loading system)
- **Resolved:** Refactored particle system to use object pooling
- **Overall Level:** Low (well-managed, no critical issues)

**Performance Impact:**
- Audio system adds ~50KB to bundle size, no frame rate impact
- Save system negligible performance impact, < 1ms operations

## 📅 NEXT WEEK PLANNING
**Priority 1 (Must Complete):**
1. Power-up system foundation - 12 hours - Core gameplay enhancement ready for testing

**Priority 2 (Should Complete):**
1. Achievement system basic framework - 8 hours - Player engagement and retention
2. Level editor prototype - 6 hours - User-generated content potential

**Priority 3 (Nice to Have):**
1. Advanced particle effects for power-ups - 4 hours - Visual polish enhancement
```

## Success Indicators

A good weekly review should result in:
- ✅ Clear understanding of actual progress vs planned progress
- ✅ Realistic goals for the upcoming week
- ✅ Identified risks with mitigation strategies
- ✅ Updated documentation priorities
- ✅ Maintained or improved development velocity

## Red Flags

Watch for these warning signs in your weekly reviews:
- 🚨 **Consistently missing goals** → Reevaluate planning approach
- 🚨 **Growing technical debt** → Allocate time for cleanup
- 🚨 **Unclear priorities** → Better goal setting needed
- 🚨 **No performance metrics** → Add measurement and monitoring
- 🚨 **Avoiding difficult tasks** → Break down into smaller pieces

Remember: The weekly review is your opportunity to course-correct before problems become critical. Be honest about challenges and celebrate genuine progress.