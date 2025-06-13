# Daily Development Workflow

## Morning Routine (5 minutes)

### Session Startup Checklist
- [ ] Pull latest changes from both repositories
- [ ] Review yesterday's session end notes
- [ ] Check current sprint priorities
- [ ] Open development environment (browser, devtools, editor)
- [ ] Quick game test to confirm current state

### Session Start Prompt
Use this prompt in Claude Projects to begin each session:

```
Neural Nexus development check-in:

**SESSION FOCUS:**
- What game feature are we working on today?
- Any performance issues or player feedback from last session?
- Which devices should we test the latest changes on?
- Priority focus: gameplay mechanics, visual polish, or technical optimization?

**QUICK STATUS:**
- Current build status and any blockers?
- Recent player testing feedback or observations?
- Performance metrics from last session?

**TODAY'S GOALS:**
- Primary objective for this session?
- Secondary tasks if time permits?
- Any experimental features to explore?

Keep response concise and action-oriented to start productive development.
```

## During Development

### Code Quality Habits
- **Test Early, Test Often**: Check changes on multiple devices every 30 minutes
- **Small Commits**: Commit working features individually with clear messages
- **Performance Monitoring**: Watch frame rate in DevTools during development
- **User Experience**: Consider player perspective with every change

### Documentation While Coding
- **Decision Tracking**: Note why you chose specific approaches
- **Pattern Recording**: Document reusable code patterns in knowledge base
- **Issue Logging**: Record any bugs or odd behaviors for later investigation
- **Performance Notes**: Track frame rate impacts of new features

## End of Session (5 minutes - CRITICAL)

### Session End Prompt
**NEVER skip this step** - Use the session end prompt from templates:

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
```

### Post-Session Tasks
- [ ] Commit all changes with descriptive messages
- [ ] Update feature roadmap if priorities shifted
- [ ] Add any new patterns to knowledge base
- [ ] Test final state on at least 2 different devices
- [ ] Push changes to repository

## Weekly Routine (Fridays, 15 minutes)

### Weekly Review Process
1. **Run weekly review prompt** (see templates/weekly-review-prompt.md)
2. **Update project documentation** based on week's learnings
3. **Assess roadmap progress** and adjust if needed
4. **Archive completed features** and plan next week
5. **Clean up knowledge base** - remove outdated information

### Git Maintenance
```bash
# Weekly repository maintenance
git fetch origin
git status
git log --oneline --since="1 week ago"

# Tag weekly milestones
git tag -a week-$(date +%Y%m%d) -m "Weekly milestone: [summary of accomplishments]"
git push --tags

# Clean up branches if using feature branches
git branch --merged | grep -v main | xargs -n 1 git branch -d
```

## Emergency Procedures

### When Things Go Wrong

#### Game Broken After Changes
1. **Don't panic** - check browser console for errors
2. **Revert last commit** if needed: `git reset --hard HEAD~1`
3. **Use browser DevTools** to debug step by step
4. **Test in incognito mode** to rule out cache issues
5. **Ask Claude for help** with specific error messages

#### Lost Context in Claude Project
1. **Use emergency recovery prompt** from templates
2. **Re-upload key documentation** from knowledge base
3. **Run project status reconstruction**
4. **Continue with current session goals**

#### Performance Suddenly Degraded
1. **Profile in browser DevTools** to identify bottleneck
2. **Check recent commits** for performance-impacting changes
3. **Test on different devices** to isolate issue
4. **Use performance monitoring** tools from knowledge base

## Productivity Tips

### Focus Techniques
- **Pomodoro Method**: 25 min focused work, 5 min break
- **Feature Boxing**: Complete one small feature before starting another
- **Device Rotation**: Test on different devices throughout day
- **Player Perspective**: Regularly play your own game as a user

### Avoiding Common Pitfalls
- **Feature Creep**: Stick to current sprint goals
- **Perfect Code Syndrome**: Prototype first, optimize later
- **Testing Neglect**: Test immediately after each change
- **Documentation Debt**: Update docs as you code, not later

### Energy Management
- **Morning**: Complex features and architecture decisions
- **Afternoon**: Testing, optimization, and polish
- **Evening**: Documentation and planning
- **When Tired**: Testing on devices, organizing knowledge base

## Success Metrics

### Daily Success Indicators
- ✅ Clear progress on current sprint goal
- ✅ No performance regressions introduced
- ✅ All changes tested on mobile and desktop
- ✅ Session properly documented and consolidated
- ✅ Next session has clear starting point

### Weekly Success Indicators
- ✅ Sprint goals on track or completed
- ✅ Technical debt managed (not growing)
- ✅ Knowledge base updated with new learnings
- ✅ Performance targets maintained
- ✅ Player experience improving measurably

### Warning Signs
- 🚨 Repeating same tasks (may indicate unclear goals)
- 🚨 Frame rate declining (performance debt accumulating)
- 🚨 Unclear next steps (need better planning)
- 🚨 Skipping session consolidation (context will be lost)
- 🚨 Not testing on devices (mobile issues building up)

## Tools and Setup

### Essential Browser DevTools
- **Console**: Error monitoring and debug logging
- **Performance**: Frame rate and memory profiling
- **Network**: Asset loading analysis
- **Device Toolbar**: Mobile testing and responsive design
- **Lighthouse**: Performance auditing

### Development Environment
```bash
# Essential tools for productive development
brew install --cask google-chrome  # Primary testing browser
brew install --cask firefox        # Cross-browser testing
brew install python                # Local server (python -m http.server)
brew install git                   # Version control

# Optional but recommended
brew install --cask visual-studio-code  # Code editor
brew install node                       # For future build tools
```

### Git Workflow
```bash
# Daily workflow
git status                    # Check current state
git add .                     # Stage changes
git commit -m "feat: add X"   # Commit with clear message
git push origin main          # Push to repository

# Branch workflow (for larger features)
git checkout -b feature/audio-system
# ... work on feature ...
git checkout main
git merge feature/audio-system
git branch -d feature/audio-system
```

Remember: Consistency in daily workflow creates compound improvements over time. The small overhead of proper documentation and testing pays huge dividends in development velocity and code quality.