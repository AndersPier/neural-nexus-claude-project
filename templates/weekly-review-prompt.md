# Weekly Review Prompt Template

Use this prompt every Friday to assess project health and plan ahead:

```
Neural Nexus weekly project review. Analyze and provide:

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
- **Every Friday** - End of work week review
- **Before major milestones** - Assess readiness
- **When feeling lost** - Get back on track
- **Monthly planning** - Broader strategic review

### What to Include
- **Honest Assessment** - Real progress, not wishful thinking
- **Specific Details** - Exact features, concrete blockers
- **Forward Planning** - Clear priorities for next week
- **Risk Awareness** - Potential problems and solutions

### Example Weekly Review

```
## 📈 PROGRESS SUMMARY
**Features Completed This Week:**
- Audio system integration with 5 core sound effects
- Save game functionality using localStorage
- Mobile touch optimization improving responsiveness by 25%

**Development Velocity:**
- Faster than last week (3 features vs 1 feature)
- Audio implementation went smoother than expected
- Touch optimization required less refactoring than planned

**Blockers Resolved:**
- Canvas touch events now work consistently across iOS/Android
- Audio context initialization fixed for mobile browsers
- Performance bottleneck in particle system resolved

**New Blockers Identified:**
- Safari audio autoplay policy requires user interaction
- LocalStorage size limits may affect save data for high levels
- iPhone SE screen size reveals UI scaling issues

## 🏗️ ARCHITECTURE & CODE HEALTH
**New Patterns Introduced:**
- Audio manager class with preloading and fallback handling
- Save data compression using JSON.stringify optimization
- Touch event delegation pattern for better performance

**Technical Debt Status:**
- **Created:** Temporary audio context workaround for iOS
- **Resolved:** Cleaned up particle system redundant code
- **Overall Level:** Low (minimal shortcuts, good documentation)

**Performance Impact:**
- Audio system adds 2ms to load time but improves user experience
- Save system has negligible performance impact
- Touch optimization actually improved overall responsiveness

## 📅 NEXT WEEK PLANNING
**Priority 1 (Must Complete):**
1. Tutorial system - 8 hours - Critical for user onboarding

**Priority 2 (Should Complete):**
1. Achievement system - 6 hours - Improves player retention
2. Level editor prototype - 4 hours - Future content creation

**Priority 3 (Nice to Have):**
1. Visual effect enhancements - 3 hours - Polish and appeal

## ⚠️ RISK ASSESSMENT
**Potential Issues:**
- Tutorial complexity → Keep it simple, test with real users
- Achievement data persistence → Use same save system as game progress

**Dependency Concerns:**
- No external dependencies identified this week
```

## Benefits of Weekly Reviews

- **Maintains Momentum** - Clear progress tracking prevents stagnation
- **Identifies Patterns** - Recognize what works and what doesn't
- **Prevents Debt** - Regular attention to code quality and documentation
- **Plans Strategically** - Think beyond just the next task
- **Manages Risk** - Identify problems before they become critical

## Red Flags in Weekly Reviews

- 🚨 **No completed features** → Check if tasks are too large
- 🚨 **Recurring same blockers** → Need different approach
- 🚨 **Growing technical debt** → Dedicate time to cleanup
- 🚨 **Unclear priorities** → Step back and reassess goals
- 🚨 **Performance regression** → Immediate investigation needed

Remember: Weekly reviews are investments in project health. 15 minutes every Friday prevents hours of confusion later.