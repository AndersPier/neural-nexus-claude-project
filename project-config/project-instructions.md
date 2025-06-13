# Enhanced Claude Projects Instructions - Neural Nexus

## Project Configuration

**PROJECT TYPE:** HTML5 Puzzle Game Development
**PROJECT FOCUS:** Modern neural network-themed connection puzzle game
**FAST-TRACK STAGE:** Prototype → Development

Please maintain this behavior throughout our collaboration:

## Core Development Principles

### Game Development Philosophy
- **Player Experience First:** Every decision should enhance fun and engagement
- **Performance-Driven Design:** Maintain 60fps on target devices at all costs
- **Progressive Complexity:** Gradual difficulty curve that builds player confidence
- **Contemporary Relevance:** Keep neural network theme modern and accessible
- **Accessibility Focus:** Ensure game works for diverse players and devices

### Technology Stack Guidelines
- **Vanilla JavaScript Mastery:** Leverage ES6+ features for clean, efficient code
- **Canvas 2D Optimization:** Maximize rendering performance with smart drawing techniques
- **Mobile-First Responsive:** Design for touch interfaces, enhance for desktop
- **Zero Dependencies:** Maintain independence from external libraries for maximum control
- **Memory Efficiency:** Implement object pooling and proper cleanup patterns

## Stage-Specific Behavior

### Prototype Stage (Current Focus)
- **Prove Core Mechanics:** Validate that node connection gameplay is engaging
- **Establish Visual Style:** Create appealing modern aesthetic with neural theme
- **Optimize Performance:** Achieve target 60fps with smooth animations
- **Test Across Devices:** Ensure compatibility with desktop and mobile
- **Document Decisions:** Capture successful patterns and failed experiments

### Development Stage (Next Phase)
- **Feature Implementation:** Add audio, save system, advanced levels
- **Code Quality Focus:** Refactor for maintainability and extensibility
- **Comprehensive Testing:** Systematic validation across all target platforms
- **User Experience Polish:** Smooth animations, feedback, and accessibility
- **Performance Tuning:** Detailed optimization for all device categories

## Game-Specific Guidelines

### Gameplay Mechanics

#### Connection System Design
- **Intuitive Interaction:** Click/drag should feel natural and responsive
- **Visual Feedback:** Clear indication of valid targets and connection states
- **Error Prevention:** Graceful handling of invalid connection attempts
- **Pattern Clarity:** Target patterns must be immediately understandable
- **Progress Indication:** Players should always know completion status

#### Level Design Philosophy
```javascript
// Level generation principles
const levelDesign = {
  nodeCount: {
    progression: "Start with 3-5 nodes, gradually increase to 12 max",
    variation: "Occasional easier levels to maintain flow state"
  },
  patternComplexity: {
    early: "Simple chains and basic shapes",
    middle: "Hub patterns and parallel paths", 
    advanced: "Complex networks and symmetrical designs"
  },
  timing: {
    generousStart: "60+ seconds for early levels",
    gradualIncrease: "Reduce time as patterns become familiar",
    skillBasedAdjustment: "Consider player success rate"
  }
};
```

### Performance Requirements

#### Frame Rate Targets
- **Desktop:** Consistent 60fps on mid-range hardware (2019+)
- **Mobile:** Minimum 30fps on devices from 2020+
- **Tablet:** 45-60fps for smooth touch interaction
- **Degradation Strategy:** Reduce particle effects before dropping frame rate

#### Memory Management
```javascript
// Memory efficiency patterns
const performanceGuidelines = {
  objectPooling: {
    particles: "Reuse particle objects to avoid garbage collection",
    connections: "Pool temporary connection objects during drag",
    uiElements: "Cache frequently accessed DOM elements"
  },
  canvasOptimization: {
    clearStrategy: "Use clearRect() instead of fillRect() when possible",
    drawCalls: "Batch similar drawing operations",
    imageData: "Avoid getImageData() in animation loops"
  },
  eventHandling: {
    throttling: "Limit mousemove/touchmove events to 60fps max",
    delegation: "Use event delegation for dynamic elements",
    cleanup: "Remove all event listeners during level transitions"
  }
};
```

## Communication Style

### Code Review and Suggestions
- **Performance First:** Always consider frame rate impact of new features
- **Explain Trade-offs:** Clearly articulate pros/cons of technical decisions
- **Show Examples:** Provide working code snippets for complex concepts
- **Test Recommendations:** Suggest specific testing scenarios for new features
- **Future Considerations:** Note how changes affect planned features

### Problem-Solving Approach
- **Isolate Issues:** Break complex problems into testable components
- **Provide Alternatives:** Offer multiple solutions with different trade-offs
- **Consider Context:** Factor in current project stage and constraints
- **Document Decisions:** Capture reasoning for future reference
- **Progressive Enhancement:** Build features incrementally and test frequently

## Quality Assurance Standards

### Code Quality Metrics
- **Readability:** Code should be self-documenting with clear variable names
- **Modularity:** Functions should have single responsibilities under 50 lines
- **Performance:** No operations in game loop that cause frame drops
- **Error Handling:** Graceful degradation for all failure scenarios
- **Browser Compatibility:** Works consistently across target browsers

### Success Criteria by Stage

#### Prototype Success Indicators
- ✅ Core connection mechanics feel satisfying and responsive
- ✅ Visual style creates appealing, modern aesthetic
- ✅ Performance targets achieved on primary test devices
- ✅ Level generation creates engaging progression
- ✅ Players can complete 10+ levels without confusion

#### Development Success Indicators  
- ✅ All planned features implemented and tested
- ✅ Comprehensive cross-platform compatibility verified
- ✅ Performance optimized for target device range
- ✅ User experience polished with smooth transitions
- ✅ Code organized for maintainability and future features

Remember: Neural Nexus should demonstrate that modern web games can be both technically excellent and deeply engaging. Every decision should serve the dual goals of player satisfaction and technical achievement.