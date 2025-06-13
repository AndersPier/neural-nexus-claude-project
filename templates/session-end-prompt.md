# Session End Prompt Template

**CRITICAL: Use this prompt at the end of EVERY development session**

```
Neural Nexus session wrap-up:

**ACCOMPLISHED TODAY:**
- [Specific features implemented or bugs fixed]
- [Performance improvements or optimizations made]
- [User experience enhancements added]

**GAME DESIGN DECISIONS:**
- [Difficulty balancing choices and reasoning]
- [Visual or audio design decisions made]
- [Technical architecture choices and trade-offs]

**NEXT SESSION PRIORITY:**
- [Most important game feature or improvement to work on]
- [Specific technical goal or gameplay element]

**GAME HEALTH:** [Green/Yellow/Red]
- Performance: [60fps achieved/needs optimization/concerning issues]
- Fun factor: [highly engaging/needs refinement/major issues]
- Technical debt: [clean code/manageable/needs refactoring]

**TESTING NOTES:**
- [Devices and browsers tested on]
- [Player feedback or usability observations]
- [Performance metrics and frame rate data]

**KNOWLEDGE BASE UPDATES NEEDED:**
- [New patterns or techniques to document]
- [Design decisions to capture]
- [Performance findings to record]

Provide structured, actionable information for knowledge consolidation.
```

## Why This Is Critical

- **Context Preservation**: Ensures Claude remembers progress between sessions
- **Decision Documentation**: Captures reasoning behind choices for future reference
- **Problem Prevention**: Identifies issues before they become blockers
- **Progress Tracking**: Maintains clear development momentum
- **Knowledge Building**: Accumulates learnings systematically

## Usage Guidelines

### When to Use
- **End of every session** - No exceptions, even short sessions
- **Before major breaks** - Lunch, end of day, weekend breaks
- **After significant milestones** - Feature completion, bug fixes, optimizations

### How to Use
1. **Be Specific**: "Added audio system" not "worked on sound"
2. **Include Metrics**: Frame rates, load times, user feedback
3. **Document Reasoning**: Why you made specific design choices
4. **Set Clear Priorities**: What's most important for next session
5. **Assess Honestly**: Real project health, not wishful thinking

### Quality Examples

**Good Session End:**
```
**ACCOMPLISHED TODAY:**
- Implemented Web Audio API with 5 core sound effects (connect, complete, error, hover, success)
- Optimized touch event handling, improved iPhone responsiveness from 45fps to 58fps
- Added visual feedback for invalid connection attempts (red glow + shake animation)

**GAME DESIGN DECISIONS:**
- Sound effects kept subtle (< 0.5s duration) to avoid overwhelming fast-paced gameplay
- Touch areas increased to 44px minimum for better mobile accessibility
- Error feedback uses animation instead of blocking alerts to maintain game flow

**NEXT SESSION PRIORITY:**
- Implement save system using localStorage with progress persistence
- Add tutorial overlay for first-time players explaining connection mechanics

**GAME HEALTH:** Green
- Performance: 58fps on iPhone 12, 60fps on desktop (target achieved)
- Fun factor: Highly engaging, players completing 15+ levels in testing
- Technical debt: Clean, no shortcuts taken during audio implementation

**TESTING NOTES:**
- Tested on iPhone 12 Safari, Android Chrome, Desktop Firefox/Chrome
- 3 players tested levels 1-20, average completion time 8 minutes
- All players understood connection mechanics without explanation

**KNOWLEDGE BASE UPDATES NEEDED:**
- Document Web Audio API integration pattern for future reference
- Add touch optimization techniques to performance guide
- Record user testing methodology that worked well
```

**Poor Session End:**
```
Worked on the game today. Added some sounds and fixed a few bugs. Game seems okay. Will work on more features next time.
```

## Red Flags

If your session end includes any of these, take corrective action:

- 🚨 **Vague accomplishments** → Be more specific about what was built
- 🚨 **No performance data** → Always include frame rate and device testing
- 🚨 **Unclear next steps** → Define specific, actionable priorities
- 🚨 **No testing mentioned** → Always test changes on target devices
- 🚨 **Missing design rationale** → Explain why choices were made
- 🚨 **Technical debt ignored** → Acknowledge shortcuts and plan cleanup

## Session End Checklist

Before ending each session, ensure you have:

- [ ] Tested latest changes on at least 2 devices/browsers
- [ ] Measured performance impact of any new features
- [ ] Documented any trade-offs or design decisions made
- [ ] Identified the single most important next task
- [ ] Assessed project health honestly
- [ ] Noted any patterns worth documenting

Remember: 5 minutes of quality session consolidation saves hours of context rebuilding later.