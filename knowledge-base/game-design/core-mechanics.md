# Core Game Mechanics Documentation

## Connection System

### Basic Mechanics
The core gameplay revolves around connecting neural network nodes to form specific patterns. Players click and drag between nodes to create connections that match a target pattern shown as dotted lines.

### Node Types
```javascript
const nodeTypes = {
  normal: {
    color: '#333366',
    activeColor: '#00d4ff',
    description: 'Standard connection points'
  },
  source: {
    color: '#00ff64',
    description: 'Starting points for network patterns'
  },
  target: {
    color: '#ff6400', 
    description: 'End points for network completion'
  }
};
```

### Connection Rules
1. **Valid Connections**: Any node can connect to any other node
2. **Bidirectional**: All connections work in both directions
3. **No Self-Connection**: Nodes cannot connect to themselves
4. **No Duplicates**: Only one connection allowed between any two nodes
5. **Visual Feedback**: Invalid attempts show clear feedback

### Interaction Patterns
- **Desktop**: Click and drag between nodes
- **Mobile**: Tap and drag with finger
- **Feedback**: Immediate visual response to all interactions
- **Error Handling**: Graceful handling of invalid connection attempts

## Level Generation System

### Difficulty Progression
```javascript
const difficultyProgression = {
  beginner: {
    levels: '1-5',
    nodes: '3-4',
    connections: '2-3',
    timeLimit: '60s',
    focus: 'Learning basic mechanics'
  },
  intermediate: {
    levels: '6-15', 
    nodes: '4-7',
    connections: '3-6',
    timeLimit: '50-60s',
    focus: 'Pattern recognition skills'
  },
  advanced: {
    levels: '16-25',
    nodes: '7-10',
    connections: '6-12',
    timeLimit: '40-50s', 
    focus: 'Complex network strategy'
  },
  expert: {
    levels: '26+',
    nodes: '10-12',
    connections: '8-16',
    timeLimit: '30-45s',
    focus: 'Master-level challenges'
  }
};
```

### Pattern Types
1. **Linear Chains**: Simple A→B→C→D connections
2. **Hub Networks**: Central node connecting to multiple others
3. **Parallel Paths**: Multiple independent connection chains
4. **Complex Networks**: Intricate interconnected patterns
5. **Symmetrical Designs**: Balanced, aesthetically pleasing layouts

### Algorithm Approach
```javascript
function generateLevel(levelNumber) {
  const nodeCount = Math.min(5 + Math.floor(levelNumber / 2), 12);
  const connectionCount = Math.min(nodeCount - 1 + Math.floor(levelNumber / 3), nodeCount * 2);
  
  // Place nodes in circular pattern with randomization
  const nodes = generateNodePositions(nodeCount);
  
  // Generate valid connection pattern
  const targetPattern = generateConnections(nodes, connectionCount);
  
  // Ensure pattern is solvable and engaging
  return validatePattern(nodes, targetPattern);
}
```

## Scoring System

### Point Calculation
```javascript
const scoring = {
  basePoints: {
    levelComplete: 100,
    timeBonus: 10, // per second remaining
    levelMultiplier: 'level * 50'
  },
  bonuses: {
    perfectCompletion: 'no invalid attempts * 50',
    speedBonus: 'completion under 30s * 100',
    consecutiveLevels: 'streak multiplier * 25'
  }
};
```

### Example Score Calculation
```
Level 5 completion in 35 seconds with no mistakes:
- Base: 100 points
- Time bonus: 25 seconds remaining * 10 = 250 points  
- Level multiplier: 5 * 50 = 250 points
- Perfect bonus: 50 points
- Total: 650 points
```

### High Score Tracking
- Local storage persistence
- Weekly/monthly leaderboards (future)
- Achievement system integration
- Progress tracking across sessions

## Timing and Pacing

### Time Limits
```javascript
const timingSystem = {
  baseTime: 60, // seconds for level 1
  reduction: 2, // seconds reduced every 3 levels
  minimum: 30, // never less than 30 seconds
  calculation: 'Math.max(30, 60 - Math.floor(level / 3) * 2)'
};
```

### Flow State Management
- **Gradual Ramp**: Difficulty increases smoothly
- **Recovery Levels**: Occasional easier levels to maintain confidence
- **Time Pressure**: Creates urgency without panic
- **Clear Progress**: Visual indication of completion status

## Visual Feedback System

### Connection States
1. **Target Pattern**: Dotted white lines showing required connections
2. **Active Connections**: Solid colored lines for completed connections
3. **Current Drag**: Semi-transparent preview line during connection creation
4. **Invalid Attempts**: Red glow and shake animation for errors
5. **Completion**: Particle burst effects and color changes

### Node Animation
```javascript
const nodeAnimations = {
  idle: {
    pulse: 'breathing effect with sine wave',
    glow: 'subtle outer glow animation'
  },
  hover: {
    scale: '1.1x size increase',
    brightness: 'increased luminosity'
  },
  connected: {
    energy: 'flowing particles through connections',
    color: 'shift to active state'
  }
};
```

## Audio Design Framework (Planned)

### Sound Categories
```javascript
const audioDesign = {
  feedback: {
    nodeTouch: 'soft electronic blip',
    connectionMade: 'satisfying snap/lock sound',
    connectionFailed: 'gentle error tone',
    levelComplete: 'triumphant harmonic sequence'
  },
  ambient: {
    background: 'subtle electronic atmosphere',
    nodeHum: 'quiet frequency-based ambience',
    energyFlow: 'soft electrical crackling'
  },
  ui: {
    buttonPress: 'clean interface sounds',
    menuTransition: 'smooth whoosh effects'
  }
};
```

### Audio Implementation Principles
- **Subtle**: Never overwhelming or distracting
- **Responsive**: Immediate feedback for actions
- **Contextual**: Different sounds for different game states
- **Optional**: Always allow muting for accessibility
- **Performance**: Lightweight files, efficient playback

## Accessibility Considerations

### Visual Accessibility
- **Color Blind Support**: Pattern recognition doesn't rely solely on color
- **High Contrast**: Clear visual distinction between elements
- **Scalable UI**: Responsive design for different screen sizes
- **Clear Typography**: Readable fonts and appropriate sizing

### Motor Accessibility
- **Touch Targets**: Minimum 44px touch areas on mobile
- **Drag Tolerance**: Forgiving connection detection
- **Alternative Inputs**: Keyboard navigation support (future)
- **Timing Options**: Adjustable time limits (future)

### Cognitive Accessibility
- **Clear Instructions**: Obvious gameplay mechanics
- **Progressive Disclosure**: Complexity introduced gradually
- **Visual Hierarchy**: Important information is prominent
- **Consistent Patterns**: Predictable interface behavior

This documentation serves as the foundation for all game design decisions and should be updated as mechanics evolve.