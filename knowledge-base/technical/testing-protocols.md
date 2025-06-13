# Manual Testing Protocols

## Testing Overview

Neural Nexus testing focuses on cross-platform compatibility, performance validation, and user experience verification. Since we use vanilla HTML/JavaScript, testing is primarily manual with some automated performance monitoring.

## Pre-Testing Setup

### Test Environment Preparation
```bash
# 1. Set up local test server
python -m http.server 8000
# or
npx http-server -p 8000

# 2. Clear browser caches
# Chrome: Ctrl+Shift+Delete
# Firefox: Ctrl+Shift+Delete  
# Safari: Cmd+Option+E

# 3. Open browser developer tools
# Chrome: F12 or Ctrl+Shift+I
# Firefox: F12 or Ctrl+Shift+I
# Safari: Cmd+Option+I
```

### Testing Devices Required
- **Desktop**: Windows/Mac/Linux with Chrome, Firefox, Safari, Edge
- **Mobile**: iPhone (iOS 14+), Android (Chrome 90+)
- **Tablet**: iPad, Android tablet
- **Network**: Test on both WiFi and mobile data

## Core Functionality Testing

### Game Mechanics Validation

#### Connection System Testing
```markdown
**Test**: Basic node connections
- [ ] Click and drag creates connection preview line
- [ ] Releasing on valid target creates solid connection
- [ ] Releasing on invalid target cancels connection
- [ ] Cannot connect node to itself
- [ ] Cannot create duplicate connections
- [ ] Visual feedback shows connection success/failure

**Test**: Pattern matching  
- [ ] Dotted target lines display correctly
- [ ] Created connections match visual style of targets
- [ ] Level completion triggers when all patterns matched
- [ ] Partial completion shows progress clearly
- [ ] Level completion animation plays smoothly

**Test**: Timer functionality
- [ ] Timer counts down from correct starting value
- [ ] Timer display updates every second
- [ ] Game over triggers at 0 seconds
- [ ] Time bonus calculated correctly in scoring
- [ ] Timer pauses during level completion animation
```

#### Level Progression Testing
```markdown
**Test**: Level generation
- [ ] Level 1 starts with 3-4 nodes
- [ ] Node count increases gradually with level
- [ ] Connection complexity scales appropriately  
- [ ] Patterns remain solvable at all levels
- [ ] Time limits decrease gradually but remain fair

**Test**: Scoring system
- [ ] Base points awarded for level completion (100)
- [ ] Time bonus calculated correctly (10 per second)
- [ ] Level multiplier applied (level * 50)
- [ ] Score displays update immediately
- [ ] High scores persist during session
```

### Performance Testing Protocol

#### Frame Rate Monitoring
```javascript
// Add to console for testing
let frameCount = 0;
let lastTime = performance.now();

function monitorFPS() {
  frameCount++;
  const currentTime = performance.now();
  
  if (currentTime - lastTime >= 1000) {
    console.log(`FPS: ${frameCount}`);
    frameCount = 0;
    lastTime = currentTime;
  }
  
  requestAnimationFrame(monitorFPS);
}

monitorFPS();
```

#### Performance Targets
```markdown
**Desktop Requirements**:
- [ ] 60fps during normal gameplay
- [ ] 45+fps during particle effects
- [ ] <100ms input lag for connections
- [ ] <500ms level transition time
- [ ] <2 second load time on broadband

**Mobile Requirements**:
- [ ] 30fps during normal gameplay  
- [ ] 20+fps during particle effects
- [ ] <150ms input lag for connections
- [ ] <1 second level transition time
- [ ] <5 second load time on 3G
```

#### Memory Usage Testing
```javascript
// Monitor memory usage (Chrome only)
setInterval(() => {
  if (performance.memory) {
    const used = Math.round(performance.memory.usedJSHeapSize / 1024 / 1024);
    const total = Math.round(performance.memory.totalJSHeapSize / 1024 / 1024);
    console.log(`Memory: ${used}MB / ${total}MB`);
  }
}, 5000);
```

## Cross-Platform Testing

### Desktop Browser Testing

#### Chrome Testing Checklist
```markdown
**Chrome (Windows/Mac/Linux)**:
- [ ] All game mechanics function correctly
- [ ] 60fps performance achieved
- [ ] Audio context initializes properly (when implemented)
- [ ] LocalStorage saves/loads correctly
- [ ] Canvas rendering crisp on high-DPI displays
- [ ] Particle effects smooth and performant
- [ ] No console errors during gameplay
- [ ] DevTools performance profile shows no bottlenecks
```

#### Firefox Testing Checklist  
```markdown
**Firefox (Windows/Mac/Linux)**:
- [ ] All game mechanics function correctly
- [ ] 45+fps performance achieved
- [ ] CSS animations smooth
- [ ] Canvas gradients render correctly
- [ ] Touch events work on Firefox mobile
- [ ] No compatibility warnings in console
- [ ] Memory usage stable over time
```

#### Safari Testing Checklist
```markdown
**Safari (Mac/iOS)**:
- [ ] All game mechanics function correctly
- [ ] Touch events preventDefault works correctly
- [ ] Canvas rendering optimized for webkit
- [ ] Audio context requires user interaction (expected)
- [ ] Performance acceptable on older devices
- [ ] iOS Safari specific touch handling works
- [ ] No webkit-specific rendering issues
```

### Mobile Device Testing

#### iOS Testing Protocol
```markdown
**iPhone Testing (Safari)**:
Device: [iPhone model and iOS version]
- [ ] Touch and drag gestures responsive
- [ ] No accidental scrolling during gameplay
- [ ] Orientation changes handled gracefully
- [ ] Performance targets met (30+fps)
- [ ] Battery usage reasonable during play
- [ ] Add to Home Screen functionality works
- [ ] No UI elements cut off in different orientations

**Test Procedure**:
1. Load game in Safari
2. Test portrait and landscape modes
3. Play 5+ levels continuously 
4. Monitor performance in Settings > Battery
5. Test Add to Home Screen experience
6. Verify offline functionality (after initial load)
```

#### Android Testing Protocol
```markdown
**Android Testing (Chrome)**:
Device: [Android model and version]
- [ ] Touch events register accurately
- [ ] Pinch-to-zoom disabled properly
- [ ] Back button doesn't interfere with game
- [ ] Performance targets met
- [ ] Chrome custom tabs work correctly
- [ ] PWA installation prompts (when implemented)
- [ ] Hardware acceleration enabled

**Test Procedure**:
1. Load game in Chrome mobile
2. Test various screen sizes and densities
3. Monitor GPU rendering in Chrome DevTools
4. Test with battery saver mode enabled
5. Verify performance with background apps running
```

### Responsive Design Testing

#### Screen Size Validation
```markdown
**Breakpoint Testing**:
- [ ] 320px width (iPhone SE): Game playable, no horizontal scroll
- [ ] 768px width (tablet portrait): Optimal layout and sizing
- [ ] 1024px width (tablet landscape): Full features visible
- [ ] 1200px+ width (desktop): Centered layout, no awkward stretching

**Touch Target Testing**:
- [ ] All nodes minimum 44px touch area
- [ ] Connection drag targets adequate size
- [ ] UI buttons easily tappable
- [ ] No accidental touches on adjacent elements
```

## User Experience Testing

### First-Time Player Experience
```markdown
**Onboarding Flow**:
- [ ] Game loads within performance targets
- [ ] Instructions clear and understandable
- [ ] First level appropriately simple
- [ ] Success provides positive reinforcement
- [ ] Failure gives constructive guidance
- [ ] Controls feel intuitive without explanation

**New Player Test Protocol**:
1. Find someone unfamiliar with the game
2. Observe without providing guidance
3. Note confusion points and difficulty spikes  
4. Record completion rates for first 5 levels
5. Gather feedback on controls and clarity
6. Document suggested improvements
```

### Accessibility Testing

#### Visual Accessibility
```markdown
**Color and Contrast**:
- [ ] Game playable without color (simulated colorblindness)
- [ ] Sufficient contrast ratios (4.5:1 minimum)
- [ ] Important information not conveyed by color alone
- [ ] High contrast mode support (where available)

**Visual Clarity**:
- [ ] Text readable at minimum supported sizes
- [ ] Game elements clearly distinguishable
- [ ] Animation not excessive or distracting
- [ ] Important UI elements prominently placed
```

#### Motor Accessibility
```markdown
**Input Accessibility**:
- [ ] Touch targets meet accessibility guidelines (44px+)
- [ ] Drag distance requirements reasonable
- [ ] No time pressure that prevents careful input
- [ ] Game playable with limited mobility
- [ ] Alternative input methods possible (future)
```

## Regression Testing

### Pre-Release Testing Suite
```markdown
**Before Each Release**:
1. **Smoke Test** (15 minutes):
   - [ ] Game loads on all target browsers
   - [ ] Basic gameplay functions work
   - [ ] No obvious visual regressions
   - [ ] Performance within acceptable range

2. **Core Features Test** (30 minutes):
   - [ ] Complete gameplay flow 1-10 levels
   - [ ] All mechanics function correctly  
   - [ ] Cross-platform compatibility verified
   - [ ] Performance targets maintained

3. **Edge Case Testing** (15 minutes):
   - [ ] Rapid clicking doesn't break game
   - [ ] Network interruption handled gracefully
   - [ ] Large numbers don't break UI
   - [ ] Memory leaks not detected over extended play
```

### Issue Tracking and Reporting

#### Bug Report Template
```markdown
**Bug Report Format**:
- **Title**: [Brief description]
- **Severity**: Critical/High/Medium/Low
- **Device**: [Browser/OS/Device model]
- **Steps to Reproduce**: [Numbered list]
- **Expected Result**: [What should happen]
- **Actual Result**: [What actually happens]
- **Screenshot/Video**: [If applicable]
- **Console Errors**: [Any JavaScript errors]
- **Workaround**: [If known]
```

#### Performance Issue Template
```markdown
**Performance Issue Format**:
- **Issue**: [FPS drops, memory leaks, etc.]
- **Device**: [Detailed specs]
- **Measurement**: [Specific numbers]
- **Target**: [Performance goal]
- **Conditions**: [When issue occurs]
- **Profile Data**: [DevTools performance data]
- **Reproduction**: [Steps to reproduce]
```

## Automated Testing Setup

### Basic Performance Monitoring
```javascript
// Performance testing helper
class GameTester {
  constructor() {
    this.frameTimes = [];
    this.lastFrameTime = performance.now();
    this.testRunning = false;
  }
  
  startTest() {
    this.testRunning = true;
    this.frameTimes = [];
    console.log('Performance test started');
    this.measureFrame();
  }
  
  measureFrame() {
    if (!this.testRunning) return;
    
    const now = performance.now();
    const frameTime = now - this.lastFrameTime;
    this.frameTimes.push(frameTime);
    this.lastFrameTime = now;
    
    if (this.frameTimes.length > 300) { // 5 seconds at 60fps
      this.reportResults();
      return;
    }
    
    requestAnimationFrame(() => this.measureFrame());
  }
  
  reportResults() {
    const avgFrameTime = this.frameTimes.reduce((a, b) => a + b) / this.frameTimes.length;
    const fps = 1000 / avgFrameTime;
    const minFrameTime = Math.min(...this.frameTimes);
    const maxFrameTime = Math.max(...this.frameTimes);
    
    console.log(`Performance Test Results:
      Average FPS: ${fps.toFixed(1)}
      Min Frame Time: ${minFrameTime.toFixed(1)}ms
      Max Frame Time: ${maxFrameTime.toFixed(1)}ms
      Frames Tested: ${this.frameTimes.length}`);
    
    this.testRunning = false;
  }
}

// Usage: new GameTester().startTest();
```

### Continuous Integration Testing
```bash
# Future CI/CD pipeline for automated testing
# .github/workflows/test.yml template

name: Game Testing
on: [push, pull_request]
jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '18'
      - name: Install dependencies
        run: npm install
      - name: Run Lighthouse
        run: npm run lighthouse
      - name: Upload results
        uses: actions/upload-artifact@v2
        with:
          name: lighthouse-results
          path: performance-*.json
```

This testing protocol should be executed before every release and adapted based on discovered issues and platform changes.