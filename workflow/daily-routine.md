# Daily Development Routine

## Session Start Routine (2-3 minutes)

### 1. Environment Setup
```bash
# Open development environment
code neural-nexus-game/  # or your preferred editor
open http://localhost:8000  # if using local server
```

### 2. Context Refresh
Use the session start prompt:
```markdown
Neural Nexus development check-in:
- What game feature are we working on today?
- Any performance issues or player feedback from last session?
- Which devices should we test the latest changes on?
- Priority focus: gameplay mechanics, visual polish, or technical optimization?
```

### 3. Quick System Check
- [ ] Game loads without errors
- [ ] Core mechanics working (try connecting a few nodes)
- [ ] No obvious visual glitches
- [ ] Performance feels smooth (check browser DevTools if needed)

## During Development

### Focus Techniques
- **Pomodoro Method**: 25-minute focused work sessions
- **Single Feature Focus**: Complete one feature before starting another
- **Test Early, Test Often**: Check changes on target devices frequently
- **Document Decisions**: Note why you chose specific approaches

### Testing Workflow
```markdown
# After each significant change:
1. Test on desktop browser
2. Test on mobile device (if applicable)
3. Check performance (F12 -> Performance tab)
4. Verify no console errors
```

### Version Control Habits
```bash
# Commit frequently with clear messages
git add .
git commit -m "feat: add audio system with 5 core sound effects"

# Push at natural breakpoints
git push origin main
```

## Session End Routine (5 minutes)

### 1. Save Everything
- Save all open files
- Commit current changes (even if incomplete)
- Push to remote repository

### 2. Session Consolidation
**CRITICAL**: Always use the session end prompt:
```markdown
Neural Nexus session wrap-up:

**ACCOMPLISHED TODAY:**
- [Specific features implemented or bugs fixed]

**GAME DESIGN DECISIONS:**
- [Choices made and reasoning]

**NEXT SESSION PRIORITY:**
- [Most important task]

**GAME HEALTH:** [Green/Yellow/Red]
- Performance: [status]
- Fun factor: [assessment]
- Technical debt: [level]

**TESTING NOTES:**
- [Devices tested, feedback received]
```

### 3. Environment Cleanup
- Close unnecessary browser tabs
- Stop local development servers
- Clear desktop clutter
- Update task tracking (if used)

## Weekly Routines

### Friday: Weekly Review
- Run comprehensive weekly review prompt
- Update knowledge base with new discoveries
- Plan next week's priorities
- Archive completed session logs

### Sunday: Week Prep
- Review roadmap and current priorities
- Set up development environment for Monday
- Clear any accumulated technical or organizational debt

## Best Practices

### Energy Management
- **Peak Hours**: Schedule complex work during your most alert time
- **Break Frequency**: Take 5-10 minute breaks every hour
- **Context Switching**: Minimize task switching within sessions
- **Deep Work**: Block distractions during focused development time

### Quality Control
- **Performance First**: Always check frame rate after changes
- **Cross-Platform**: Test on different devices and browsers
- **User Perspective**: Regularly play the game as a user would
- **Code Review**: Self-review code before committing

### Motivation Maintenance
- **Visible Progress**: Keep a list of completed features
- **Share Updates**: Show progress to friends or online communities
- **Celebrate Wins**: Acknowledge when features work well
- **Learn from Setbacks**: Document what doesn't work and why

## Red Flags

If you notice these patterns, take corrective action:

- 🚨 **Skipping session end consolidation** → Context will be lost
- 🚨 **Working on multiple features simultaneously** → Focus on one
- 🚨 **Ignoring performance impacts** → Technical debt accumulates
- 🚨 **Not testing on target devices** → User experience suffers
- 🚨 **Unclear about next priorities** → Run weekly review

## Troubleshooting

### Lost Motivation
- Review completed features list
- Play the game and appreciate what works
- Read positive user feedback (if available)
- Set smaller, achievable goals

### Technical Confusion
- Return to last working state
- Break problem into smaller pieces
- Search for similar solutions online
- Ask for help in development communities

### Time Management Issues
- Track actual time spent on different activities
- Identify and eliminate time wasters
- Set realistic daily goals
- Use time-boxing techniques

Remember: Consistency beats intensity. Regular small progress is better than sporadic large efforts.
