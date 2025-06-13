# Emergency Recovery Procedures

## Context Loss Recovery

### Symptoms
- Claude doesn't remember recent project decisions
- Having to re-explain game mechanics or architecture
- Contradictory suggestions from previous sessions
- Unclear about current development stage or priorities

### Recovery Steps

#### 1. Immediate Assessment
```markdown
# Emergency Context Recovery Protocol

I've lost context about this project's current state. Please help me reconstruct our situation:

## 🔍 CONVERSATION ANALYSIS
**Recent History Review:**
- Analyze the last 10-15 conversation exchanges
- Identify what we were working on most recently
- Extract any recent technical decisions or changes
- Note any blockers or issues mentioned

## 📋 PROJECT STATE RECONSTRUCTION
**Current Development Status:**
- What stage are we in (Exploration/Prototype/Development/Production)?
- What's our current sprint or focus area?
- What features are completed vs in-progress vs planned?
- What's our technology stack and architecture approach?

**Recent Technical Decisions:**
- What architectural choices have we made recently?
- Are there any new patterns or approaches we've adopted?
- What trade-offs have we accepted in recent sessions?

## 📚 KNOWLEDGE BASE ASSESSMENT
**Documentation Gaps:**
- What important information isn't documented that should be?
- Are there recent decisions that need to be captured?
- What patterns or learnings should be added to our knowledge base?

## 🎯 IMMEDIATE NEXT STEPS
**Priority Clarification:**
- What should be our immediate focus for this session?
- Are there any urgent blockers to address?
- What's the most important task to complete next?

## 📝 RECOMMENDED UPDATES
**Project Configuration Updates:**
- Does our project description need updating?
- Should our custom instructions be revised?
- What knowledge base files need immediate attention?

Provide a comprehensive reconstruction to get us back on track.
```

#### 2. Documentation Review
- Check session logs in `knowledge-base/development/session-logs/`
- Review recent decisions in `knowledge-base/development/decision-history.md`
- Update project description if needed

#### 3. Knowledge Base Refresh
- Re-upload critical documents to Claude Project
- Update project instructions with current focus
- Archive outdated information

## Technical Issues Recovery

### Game Won't Load

#### Symptoms
- Blank screen or error messages
- JavaScript console errors
- Performance issues

#### Recovery Steps
```bash
# 1. Check browser console
# F12 -> Console tab
# Look for error messages

# 2. Revert to last working version
git log --oneline -10  # See recent commits
git checkout [last-working-commit]

# 3. Test in clean environment
# Open in incognito/private browsing
# Try different browser

# 4. Check file integrity
# Ensure index.html is complete
# Verify no corrupted files
```

### Performance Degradation

#### Symptoms
- Frame rate drops below 30fps
- Stuttering animations
- High memory usage
- Unresponsive controls

#### Recovery Steps
```javascript
// 1. Enable performance monitoring
function enableDebugMode() {
  window.gameDebug = {
    frameTime: [],
    avgFrameTime: function() {
      const avg = this.frameTime.reduce((a,b) => a+b) / this.frameTime.length;
      console.log(`Average frame time: ${avg.toFixed(2)}ms`);
      return avg;
    },
    clearFrameData: function() {
      this.frameTime = [];
    }
  };
}

// 2. Identify performance bottlenecks
// Use browser DevTools Performance tab
// Profile 5-10 seconds of gameplay
// Look for long tasks or memory leaks

// 3. Disable features systematically
// Comment out particle effects
// Reduce node count
// Simplify rendering
```

### Repository Issues

#### Corrupted Git Repository
```bash
# 1. Check repository status
git status
git log --oneline -5

# 2. If corrupted, clone fresh copy
cd ..
git clone https://github.com/AndersPier/neural-nexus-game.git neural-nexus-game-backup
cd neural-nexus-game-backup

# 3. Copy work in progress
# Manually copy changes from original directory
```

#### Lost Commits
```bash
# 1. Check reflog
git reflog

# 2. Find lost commit
git show [commit-hash]

# 3. Recover if needed
git cherry-pick [commit-hash]
```

## Development Environment Recovery

### Editor/IDE Issues
```bash
# 1. Reset editor settings
# VS Code: Command Palette -> "Reload Window"
# Other editors: Close and restart

# 2. Clear editor cache
# VS Code: Remove .vscode/settings.json if corrupted

# 3. Verify file associations
# Ensure .html, .js, .css files open correctly
```

### Browser Issues
```bash
# 1. Clear browser cache
# Chrome: Ctrl+Shift+Delete
# Firefox: Ctrl+Shift+Delete
# Safari: Develop -> Empty Caches

# 2. Disable extensions
# Test in incognito/private mode
# Disable ad blockers and dev extensions

# 3. Reset browser if needed
# Create new browser profile
# Test with different browser entirely
```

## Project Health Recovery

### Architecture Drift

#### Symptoms
- Code doesn't follow established patterns
- Inconsistent naming conventions
- Technical debt accumulating
- Features not integrating well

#### Recovery Process
```markdown
# Architecture Drift Analysis and Recovery

Our current implementation seems to have drifted from our original architectural intentions. Please help analyze and resolve this:

## 🏗️ CURRENT STATE ANALYSIS
**Implementation Reality:**
- Document how our current code is actually structured
- Identify the patterns we're actually using (not what we planned)
- Note any informal conventions that have emerged
- Assess the current data flow and component relationships

**Deviation Assessment:**
- Compare current implementation with our documented architecture
- Identify specific areas where we've diverged from the plan
- Analyze when and why these deviations occurred
- Determine if deviations were conscious decisions or gradual drift

## ⚖️ DRIFT EVALUATION
**Beneficial Drift (Should Embrace):**
- Which deviations have actually improved our architecture?
- What patterns emerged organically that work better than planned?
- Are there performance or maintainability improvements from drift?

**Harmful Drift (Should Correct):**
- Which deviations are causing problems or technical debt?
- What inconsistencies make the codebase harder to maintain?
- Are there security or performance regressions from drift?

## 🎯 RESOLUTION STRATEGY
**Immediate Actions (This Sprint):**
1. [Action] - [Rationale] - [Effort estimate]

**Short-term Alignment (Next 2-4 weeks):**
1. [Action] - [Rationale] - [Effort estimate]

**Long-term Architecture Evolution:**
1. [Action] - [Rationale] - [Effort estimate]

Provide specific, actionable recommendations for resolving architecture uncertainty.
```

## Prevention Strategies

### Daily Habits
- Always complete session end consolidation
- Commit changes frequently with clear messages
- Test on multiple devices regularly
- Document architectural decisions immediately

### Weekly Reviews
- Assess project health honestly
- Update documentation and knowledge base
- Plan upcoming work clearly
- Archive completed work

### Monthly Audits
- Review codebase for consistency
- Assess technical debt levels
- Update development workflows
- Validate architectural decisions

## Emergency Contacts

### Technical Resources
- **MDN Web Docs**: https://developer.mozilla.org/
- **Canvas API Reference**: https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API
- **Performance Optimization**: https://web.dev/performance/

### Community Support
- **Stack Overflow**: For specific technical issues
- **GitHub Discussions**: For project-specific questions
- **Discord/Reddit**: Game development communities

### Backup Plans
- **Repository Backup**: Always maintain local and cloud copies
- **Documentation Backup**: Export knowledge base regularly
- **Contact Lists**: Maintain list of helpful community members

Remember: Most "emergencies" can be prevented with good daily habits. When they do occur, stay calm and work through recovery procedures systematically.
