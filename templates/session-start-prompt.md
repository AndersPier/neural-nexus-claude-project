# Session Start Prompt Template

Use this prompt at the beginning of each development session:

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

## Usage Notes

- **Always use at session start** - helps Claude understand current context
- **Modify based on stage** - adjust focus areas for Exploration/Prototype/Development
- **Include specific concerns** - mention any particular issues you're facing
- **Set clear priorities** - helps focus the session on what matters most

## Example Usage

```
Neural Nexus development check-in:

**SESSION FOCUS:**
- Working on audio system integration today
- Touch controls felt sluggish on iPhone testing yesterday
- Need to test on Android Chrome and desktop Firefox
- Priority: technical optimization for mobile performance

**QUICK STATUS:**
- Core game mechanics working well, particle effects smooth
- Players report confusion about dotted line patterns on smaller screens
- Getting 45fps on iPhone 12, want to improve to 55+fps

**TODAY'S GOALS:**
- Implement Web Audio API for sound effects
- Optimize touch event handling for better responsiveness
- Test pattern visibility improvements on mobile devices
```