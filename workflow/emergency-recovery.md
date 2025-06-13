# Emergency Recovery Procedures

## Context Loss Recovery

### When to Use
- Claude has lost track of project progress
- Responses don't reflect recent work or decisions
- Claude asks about things already established
- Contradictory suggestions to previous decisions

### Recovery Protocol
```
# Context Loss Emergency Recovery

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

## Performance Degradation Recovery

### Quick Performance Diagnostics
```javascript
// Emergency performance diagnostics
function emergencyPerformanceCheck() {
  console.log('=== EMERGENCY PERFORMANCE CHECK ===');
  
  // Frame rate check
  let frameCount = 0;
  let startTime = performance.now();
  
  function checkFrameRate() {
    frameCount++;
    const currentTime = performance.now();
    
    if (currentTime - startTime >= 1000) {
      console.log(`Current FPS: ${frameCount}`);
      frameCount = 0;
      startTime = currentTime;
    }
    
    requestAnimationFrame(checkFrameRate);
  }
  
  checkFrameRate();
  
  // Memory check
  if (performance.memory) {
    const memory = performance.memory;
    console.log(`Memory usage: ${(memory.usedJSHeapSize / 1024 / 1024).toFixed(2)} MB`);
    console.log(`Memory limit: ${(memory.jsHeapSizeLimit / 1024 / 1024).toFixed(2)} MB`);
  }
  
  // Canvas performance check
  const canvas = document.getElementById('gameCanvas');
  console.log(`Canvas size: ${canvas.width}x${canvas.height}`);
  
  // Active objects count
  console.log(`Active nodes: ${gameState.nodes.length}`);
  console.log(`Active connections: ${gameState.connections.length}`);
  console.log(`Active particles: ${gameState.particles.length}`);
}
```

## Technical Debt Crisis Recovery

### Crisis Indicators
- Development velocity significantly slowed
- Simple changes require extensive refactoring
- Bugs in one area cause problems elsewhere
- New developers cannot understand codebase
- Performance degrading with each new feature

### Recovery Protocol
```
# Technical Debt Crisis Management

Technical debt has accumulated to critical levels. Help me assess and create a recovery plan:

## 📊 DEBT ASSESSMENT
**Code Quality Issues:**
- Identify areas with the highest technical debt
- Assess impact on development velocity
- Find code that's difficult to understand or modify
- Locate performance bottlenecks caused by poor design

**Architectural Problems:**
- Document architectural inconsistencies
- Identify tight coupling between components
- Find areas where changes cascade unpredictably
- Assess test coverage and maintainability

## ⚖️ DEBT PRIORITIZATION
**Critical Debt (Immediate Action):**
- Issues completely blocking new development
- Security vulnerabilities or data integrity risks
- Performance problems affecting user experience

**High-Priority Debt (Address This Sprint):**
- Issues slowing development significantly
- Code that's difficult to modify safely
- Missing tests for critical functionality

**Manageable Debt (Plan for Future):**
- Cosmetic code issues
- Documentation gaps
- Minor performance optimizations

## 🚀 RECOVERY STRATEGY
**Emergency Stabilization (This Week):**
1. [Action] - [Impact] - [Effort] - [Risk]

**Systematic Debt Reduction (Next 2-4 weeks):**
1. [Action] - [Impact] - [Effort] - [Timeline]

**Prevention Measures (Ongoing):**
1. [Process] - [Benefit] - [Implementation]

Provide a concrete plan to restore development velocity while managing risk.
```

## Build/Deployment Failures

### Common Failure Modes
- Game won't load in browser
- JavaScript errors breaking functionality
- Performance degradation after deployment
- Features working locally but failing in production

### Emergency Rollback
```bash
# Quick rollback to last known good state
git log --oneline -10  # Find last good commit
git reset --hard [good-commit-hash]  # Rollback code
git push --force-with-lease origin main  # Update remote (use carefully)

# Alternative: Create hotfix
git checkout -b hotfix/emergency-fix
# Fix critical issue
git commit -m "hotfix: resolve critical issue"
git checkout main
git merge hotfix/emergency-fix
git push origin main
```

### Debugging Checklist
```markdown
**Browser Console Errors:**
- [ ] Check for JavaScript errors
- [ ] Verify all assets are loading
- [ ] Check network requests for failures
- [ ] Validate CSS is loading correctly

**Performance Issues:**
- [ ] Check frame rate in DevTools
- [ ] Monitor memory usage over time
- [ ] Verify Canvas size and resolution
- [ ] Check for memory leaks

**Functionality Broken:**
- [ ] Test core game mechanics
- [ ] Verify touch/mouse interactions
- [ ] Check level generation
- [ ] Validate score calculation

**Cross-browser Issues:**
- [ ] Test in Chrome, Firefox, Safari
- [ ] Check mobile browsers (iOS Safari, Android Chrome)
- [ ] Verify on different screen sizes
- [ ] Test with and without internet connection
```

## Project Corruption Recovery

### Signs of Corruption
- Claude Project not loading or responding
- Knowledge base files corrupted or missing
- Project instructions not being followed
- Complete loss of context across sessions

### Recovery Steps

#### 1. Backup Current State
```bash
# Clone current repositories
git clone https://github.com/AndersPier/neural-nexus-claude-project.git backup-claude-project
git clone https://github.com/AndersPier/neural-nexus-game.git backup-game

# Create recovery branch
cd neural-nexus-claude-project
git checkout -b recovery-$(date +%Y%m%d)
git push origin recovery-$(date +%Y%m%d)
```

#### 2. Create New Claude Project
```markdown
**Emergency Project Recreation:**

1. **Create New Project**: "NeuralNexus - Recovery"
2. **Copy Configuration**: Use latest project-config/ files
3. **Upload Documentation**: All knowledge-base/ files
4. **Test Context**: Run simple query to verify function
5. **Update Links**: Point to new project in documentation
```

#### 3. Validate Recovery
```
# Recovery Validation Prompt

Test the recovered project context:

**Context Verification:**
- What is the current development stage?
- What are our immediate priorities?
- What's our technology stack?
- What performance targets do we have?

**Knowledge Base Check:**
- Can you access our game design documentation?
- Do you remember our architectural decisions?
- Are our workflow templates available?

**Functionality Test:**
- Suggest next steps for audio system implementation
- Provide performance optimization recommendations
- Reference our established coding patterns

Confirm all systems are working properly.
```

## Data Loss Prevention

### Automated Backups
```bash
# Daily backup script (run via cron)
#!/bin/bash
DATE=$(date +%Y%m%d)
BACKUP_DIR="$HOME/neural-nexus-backups/$DATE"

mkdir -p "$BACKUP_DIR"

# Backup Claude Project repo
git clone https://github.com/AndersPier/neural-nexus-claude-project.git "$BACKUP_DIR/claude-project"

# Backup Game repo  
git clone https://github.com/AndersPier/neural-nexus-game.git "$BACKUP_DIR/game"

# Compress backups older than 7 days
find "$HOME/neural-nexus-backups" -type d -mtime +7 -exec tar -czf {}.tar.gz {} \; -exec rm -rf {} \;

echo "Backup completed: $BACKUP_DIR"
```

### Recovery Documentation
```markdown
# Emergency Contact Information

**Repository Locations:**
- Claude Project: https://github.com/AndersPier/neural-nexus-claude-project
- Game Repository: https://github.com/AndersPier/neural-nexus-game
- Live Game: https://andersPier.github.io/neural-nexus-game/

**Critical Files:**
- Project Config: project-config/project-description.md
- Project Instructions: project-config/project-instructions.md
- Session Templates: templates/
- Core Documentation: knowledge-base/

**Recovery Priority:**
1. Game repository (contains working product)
2. Project configuration (enables Claude workflow)
3. Knowledge base (captures decisions and patterns)
4. Templates (workflow efficiency)
```

## Prevention Strategies

### Regular Health Checks
```markdown
**Weekly Health Check:**
- [ ] Test Claude Project responsiveness
- [ ] Verify all repository links work
- [ ] Check game deployment status
- [ ] Validate documentation is current
- [ ] Confirm backup systems functioning

**Monthly Deep Check:**
- [ ] Full context recovery test
- [ ] Performance baseline verification
- [ ] Knowledge base organization review
- [ ] Template effectiveness assessment
- [ ] Emergency procedure practice run
```

### Monitoring Setup
```javascript
// Project health monitoring
class ProjectHealthMonitor {
  constructor() {
    this.healthChecks = [];
    this.alerts = [];
  }
  
  addHealthCheck(name, checkFunction, interval) {
    setInterval(() => {
      try {
        const result = checkFunction();
        this.recordHealth(name, result);
      } catch (error) {
        this.recordAlert(name, error);
      }
    }, interval);
  }
  
  recordHealth(check, result) {
    this.healthChecks.push({
      check,
      result,
      timestamp: Date.now(),
      status: result.healthy ? 'good' : 'warning'
    });
  }
  
  recordAlert(check, error) {
    this.alerts.push({
      check,
      error: error.message,
      timestamp: Date.now(),
      severity: 'high'
    });
    
    console.error(`Health check failed: ${check}`, error);
  }
  
  getHealthReport() {
    const recent = this.healthChecks.slice(-20);
    const recentAlerts = this.alerts.slice(-5);
    
    return {
      overallHealth: recent.filter(h => h.status === 'good').length / recent.length,
      recentAlerts,
      lastCheck: recent[recent.length - 1]?.timestamp
    };
  }
}
```

Remember: The best recovery is prevention. Regular consolidation, systematic documentation, and proactive monitoring prevent most emergencies from occurring.