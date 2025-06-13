# Neural Nexus - Claude Project Repository

## Repository Structure

```
neural-nexus-claude-project/
├── README.md                           # This file - comprehensive project maintenance guide
├── .gitignore                          # Git ignore patterns for documentation workflow
├── LICENSE                             # MIT License for project methodology
├── project-config/
│   ├── project-description.md          # Ready-to-use Claude Project description template
│   ├── project-instructions.md         # Complete behavior instructions for Claude
│   └── stage-transition-templates.md   # Templates for moving between development stages
├── documentation/
│   ├── development-guide.md            # Technical development reference and architecture
│   ├── user-guide.md                  # Player-focused game guide and troubleshooting
│   └── game-design-decisions.md       # Complete record of design choices and rationale
├── knowledge-base/
│   ├── game-design/
│   │   ├── core-mechanics.md          # Game mechanics and connection system documentation
│   │   ├── level-progression.md       # Difficulty scaling, pattern generation, and player skill development
│   │   ├── scoring-system.md          # Points calculation and player reward systems
│   │   └── visual-design-guide.md     # Complete visual design system and styling guide
│   ├── technical/
│   │   ├── performance-optimization.md # Canvas optimization and memory management
│   │   ├── cross-platform-notes.md    # Device compatibility and responsive design
│   │   └── testing-protocols.md       # Manual testing procedures and checklists
│   └── development/
│       ├── feature-roadmap.md         # Development planning and feature prioritization
│       ├── decision-history.md        # Chronological record of all major decisions
│       └── session-logs/              # Directory for individual development session logs
│           └── README.md              # Guide for session log format and maintenance
├── templates/
│   ├── session-start-prompt.md        # Daily session startup template
│   ├── session-end-prompt.md          # Critical session consolidation template
│   ├── weekly-review-prompt.md        # Weekly project health assessment
│   └── stage-transition-prompt.md     # Comprehensive stage transition analysis
└── workflow/
    ├── daily-routine.md               # Daily development habits and best practices
    ├── emergency-recovery.md          # Comprehensive recovery procedures for all issues
    └── best-practices.md              # Development workflow optimization guidelines
```

## Getting Started with This Claude Project

### 1. Initial Setup

**Create Your Claude Project:**
1. Go to Claude Projects
2. Name it: ```
NeuralNexus - Prototype```
3. Copy the project description from `project-config/project-description.md`
4. Copy the custom instructions from `project-config/project-instructions.md`
5. Upload the documentation files to the Knowledge Base

### 2. Daily Workflow

**Start Each Session:**
```
# Use this prompt (from templates/session-start-prompt.md):
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

**End Each Session (CRITICAL):**
```
# Always use this prompt (from templates/session-end-prompt.md):
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

### 3. Knowledge Base Management

**Weekly Maintenance:**
- Update `knowledge-base/development/session-logs/` with new insights
- Refresh `knowledge-base/game-design/` with design decisions
- Add performance notes to `knowledge-base/technical/`

**Monthly Review:**
- Run stage transition assessment if ready
- Archive outdated documentation
- Update project description if stage has changed

## File Descriptions

### Core Configuration
- **project-description.md**: Current stage description for Claude Project setup
- **project-instructions.md**: Custom instructions that define Claude's behavior throughout development
- **stage-transition-templates.md**: Comprehensive templates for moving between Exploration, Prototype, Development, and Production stages

### Documentation
- **development-guide.md**: Technical reference covering architecture, performance optimization, and troubleshooting
- **user-guide.md**: Player-focused documentation with gameplay instructions and troubleshooting
- **game-design-decisions.md**: Complete record of all design choices with rationale, alternatives considered, and impact analysis

### Knowledge Base

#### Game Design
- **core-mechanics.md**: Connection system, node types, level generation, and difficulty progression documentation
- **level-progression.md**: Comprehensive difficulty scaling algorithm, pattern generation phases, player skill development, and balancing principles with A/B testing framework
- **scoring-system.md**: Points calculation, time bonuses, accuracy multipliers, and player reward psychology
- **visual-design-guide.md**: Complete visual design system including color palette, typography, layout, animations, and responsive design

#### Technical
- **performance-optimization.md**: Canvas rendering optimization, memory management, and cross-platform performance guidelines
- **cross-platform-notes.md**: Device compatibility, responsive design implementation, and touch optimization
- **testing-protocols.md**: Manual testing procedures, device compatibility checklists, and quality assurance processes

#### Development
- **feature-roadmap.md**: Development planning, feature prioritization, timeline estimates, and success criteria
- **decision-history.md**: Chronological record of all major development decisions with context, rationale, and alternatives
- **session-logs/**: Directory containing individual development session logs with standardized format and maintenance guidelines

### Templates
Ready-to-use prompts for consistent Claude Project workflow:
- **session-start-prompt.md**: Daily development session initialization with context setting and priority identification
- **session-end-prompt.md**: Critical session consolidation template for knowledge capture and progress tracking
- **weekly-review-prompt.md**: Comprehensive weekly project health assessment and planning
- **stage-transition-prompt.md**: Detailed analysis template for transitioning between development stages

### Workflow
- **daily-routine.md**: Complete daily development workflow including session management, testing procedures, and quality control
- **emergency-recovery.md**: Comprehensive recovery procedures for context loss, technical issues, architecture drift, and performance problems
- **best-practices.md**: Development workflow optimization guidelines and lessons learned

## Repository Maintenance

### Keeping Documentation Current

1. **After Each Development Session:**
   - Add key decisions to `knowledge-base/development/decision-history.md`
   - Update feature status in `knowledge-base/development/feature-roadmap.md`
   - Log any performance findings in `knowledge-base/technical/`
   - Create session log in `knowledge-base/development/session-logs/`

2. **Weekly Updates:**
   - Review and update project description if needed
   - Add new patterns to technical documentation
   - Update game design documentation with balance changes
   - Run weekly review prompt and archive results

3. **Stage Transitions:**
   - Use templates in `project-config/stage-transition-templates.md`
   - Archive current stage documentation
   - Update project name and instructions for new stage
   - Consolidate knowledge base for new stage focus

### Git Workflow

```bash
# Daily commits
git add .
git commit -m "docs: update session logs and design decisions"

# Weekly updates
git add knowledge-base/
git commit -m "docs: weekly knowledge base refresh"

# Stage transitions
git add project-config/
git commit -m "project: transition to [new-stage] stage"
git tag -a v1.0-prototype -m "Prototype stage completion"
```

## Emergency Procedures

### Context Loss Recovery
If Claude loses project context:
1. Use `workflow/emergency-recovery.md` procedures
2. Re-upload key documentation from `knowledge-base/`
3. Run context reconstruction prompt from templates

### Project Corruption
If Claude Project becomes unusable:
1. Create new project with current stage name
2. Upload all current documentation from this repository
3. Use `project-config/` files to recreate project settings

## Best Practices

### Documentation Hygiene
- Keep knowledge base under 10MB total
- Archive outdated decisions and old session logs
- Maintain clear file naming conventions
- Update templates based on what works in practice

### Workflow Discipline
- **Never skip session end consolidation** - 5 minutes saves hours later
- **Update documentation immediately** - Fresh memory = better docs
- **Use stage transitions properly** - Don't rush between stages
- **Trust the system** - Consistency compounds over time

### Quality Control
- Review documentation monthly for outdated information
- Ensure project instructions reflect current development approach
- Keep templates updated based on actual usage patterns
- Maintain clear decision history for future reference

## Success Metrics

### Project Health Indicators
- ✅ Clear next steps every session
- ✅ Consistent architectural decisions
- ✅ Growing knowledge base with relevant patterns
- ✅ Smooth stage transitions when appropriate
- ✅ Minimal context repetition needed

### Warning Signs
- 🚨 Repeating context to Claude → Emergency consolidation needed
- 🚨 Contradicting earlier decisions → Review decision history
- 🚨 Unclear next steps → Run project status reconstruction
- 🚨 Large knowledge base files → Archive and reorganize

## Contributing to This System

This repository represents a living system for maintaining Claude Projects effectively. Improvements welcome:

1. **Template Refinements**: Better prompts based on actual usage
2. **Workflow Optimizations**: More efficient daily/weekly routines
3. **Documentation Patterns**: Better organization schemes
4. **Emergency Procedures**: Additional recovery strategies

## Links and Resources

- **Game Repository**: [https://github.com/AndersPier/neural-nexus-game](https://github.com/AndersPier/neural-nexus-game)
- **Live Game**: [https://andersPier.github.io/neural-nexus-game/](https://andersPier.github.io/neural-nexus-game/)
- **Claude Projects**: [Link to your Claude Project]
- **Documentation Standards**: See `workflow/best-practices.md`

## Usage Examples

### Setting Up a New Feature
1. Review `knowledge-base/development/feature-roadmap.md` for current priorities
2. Use `templates/session-start-prompt.md` to begin development session
3. Document decisions in `knowledge-base/development/decision-history.md`
4. Update progress in feature roadmap
5. Use `templates/session-end-prompt.md` to consolidate session

### Stage Transition Process
1. Assess readiness using `project-config/stage-transition-templates.md`
2. Run comprehensive knowledge consolidation
3. Update project configuration for new stage
4. Archive previous stage documentation
5. Upload refined documentation to Claude Project

### Emergency Recovery
1. Identify issue type (context loss, technical problem, architecture drift)
2. Follow specific procedure in `workflow/emergency-recovery.md`
3. Use appropriate recovery templates
4. Update documentation based on lessons learned
5. Implement preventive measures for future

---

**Remember**: This repository is your project's memory and workflow guide. Maintain it well, and it will accelerate your development journey from idea to production.

**Last Updated**: June 2025  
**Current Stage**: Prototype Development  
**Next Review**: July 2025 (Monthly documentation review)
