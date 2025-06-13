# Neural Nexus - Claude Project Repository

## Repository Structure

```
neural-nexus-claude-project/
├── README.md                           # This file - project maintenance guide
├── .gitignore                          # Git ignore patterns
├── project-config/
│   ├── project-description.md          # Current project description template
│   ├── project-instructions.md         # Custom instructions for Claude
│   └── stage-transition-templates.md   # Templates for moving between stages
├── documentation/
│   ├── development-guide.md            # Technical development documentation
│   ├── user-guide.md                  # Player-focused game guide
│   └── game-design-decisions.md       # Record of design choices and rationale
├── knowledge-base/
│   ├── game-design/
│   │   ├── core-mechanics.md
│   │   ├── level-progression.md
│   │   ├── scoring-system.md
│   │   └── visual-design-guide.md
│   ├── technical/
│   │   ├── performance-optimization.md
│   │   ├── cross-platform-notes.md
│   │   └── testing-protocols.md
│   └── development/
│       ├── feature-roadmap.md
│       ├── session-logs/
│       └── decision-history.md
├── templates/
│   ├── session-start-prompt.md
│   ├── session-end-prompt.md
│   ├── weekly-review-prompt.md
│   └── stage-transition-prompt.md
└── workflow/
    ├── daily-routine.md
    ├── emergency-recovery.md
    └── best-practices.md
```

## Getting Started with This Claude Project

### 1. Initial Setup

**Create Your Claude Project:**
1. Go to Claude Projects
2. Name it: `NeuralNexus - Prototype`
3. Copy the project description from `project-config/project-description.md`
4. Copy the custom instructions from `project-config/project-instructions.md`
5. Upload the documentation files to the Knowledge Base

### 2. Daily Workflow

**Start Each Session:**
```bash
# Use this prompt (from templates/session-start-prompt.md):
Neural Nexus development check-in:
- What game feature are we working on today?
- Any performance issues or player feedback from last session?
- Which devices should we test the latest changes on?
- Priority focus: gameplay mechanics, visual polish, or technical optimization?
```

**End Each Session:**
```bash
# Always use this prompt (from templates/session-end-prompt.md):
# [See full template in templates/ directory]
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

## Repository Maintenance

### Keeping Documentation Current

1. **After Each Development Session:**
   - Add key decisions to `knowledge-base/development/decision-history.md`
   - Update feature status in `knowledge-base/development/feature-roadmap.md`
   - Log any performance findings in `knowledge-base/technical/`

2. **Weekly Updates:**
   - Review and update project description if needed
   - Add new patterns to technical documentation
   - Update game design documentation with balance changes

3. **Stage Transitions:**
   - Use templates in `project-config/stage-transition-templates.md`
   - Archive current stage documentation
   - Update project name and instructions for new stage

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

## File Descriptions

### Core Configuration
- **project-description.md**: Current stage description for Claude Project
- **project-instructions.md**: Custom instructions that define Claude's behavior
- **stage-transition-templates.md**: Templates for moving between development stages

### Documentation
- **development-guide.md**: Technical reference for building the game
- **user-guide.md**: Player-focused documentation and troubleshooting
- **game-design-decisions.md**: Record of design choices and their rationale

### Knowledge Base
Organized documentation that gets uploaded to Claude Projects:
- **game-design/**: Mechanics, progression, scoring, visual design
- **technical/**: Performance, cross-platform compatibility, testing
- **development/**: Feature roadmap, session logs, decision history

### Templates
Ready-to-use prompts for consistent Claude Project workflow:
- **session-start-prompt.md**: Beginning of each development session
- **session-end-prompt.md**: End of session consolidation (CRITICAL)
- **weekly-review-prompt.md**: Friday progress review
- **stage-transition-prompt.md**: Moving between development stages

## Links and Resources

- **Game Repository**: [https://github.com/AndersPier/neural-nexus-game](https://github.com/AndersPier/neural-nexus-game)
- **Claude Projects**: [Link to your Claude Project]

---

**Remember**: This repository is your project's memory and workflow guide. Maintain it well, and it will accelerate your development journey from idea to production.

**Last Updated**: June 2025
**Current Stage**: Prototype Development