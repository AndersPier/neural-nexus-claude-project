# Level Progression Design

## Difficulty Scaling Philosophy

### Core Principles
1. **Gradual Learning Curve**: Each level introduces complexity at a manageable pace
2. **Flow State Maintenance**: Difficulty increases to match growing player skill
3. **Recovery Levels**: Occasional easier levels to prevent frustration
4. **Skill Validation**: Regular challenges that test mastered concepts

### Mathematical Progression
```javascript
const levelProgression = {
  // Node count progression
  nodeCount: (level) => Math.min(3 + Math.floor(level / 2), 12),
  
  // Connection complexity
  connectionCount: (level) => {
    const nodes = nodeCount(level);
    return Math.min(nodes - 1 + Math.floor(level / 3), nodes * 1.5);
  },
  
  // Time pressure
  timeLimit: (level) => Math.max(30, 60 - Math.floor(level / 3) * 2),
  
  // Pattern complexity score
  complexityScore: (level) => Math.min(level * 0.8 + 2, 10)
};
```

## Level Archetypes

### Tutorial Levels (1-3)
**Purpose**: Teach basic mechanics
**Node Count**: 3-4
**Pattern Types**: Simple chains, basic shapes
**Time Limit**: 60 seconds (generous)

```javascript
// Example Level 1 pattern
const level1 = {
  nodes: 3,
  pattern: [[0, 1], [1, 2]], // Simple chain A→B→C
  type: 'linear_chain',
  tutorial: 'Connect the nodes by dragging from one to another'
};

// Example Level 2 pattern  
const level2 = {
  nodes: 4,
  pattern: [[0, 1], [0, 2], [0, 3]], // Hub pattern
  type: 'hub',
  tutorial: 'One node can connect to multiple others'
};
```

### Skill Building Levels (4-10)
**Purpose**: Develop pattern recognition
**Node Count**: 4-6
**Pattern Types**: Hubs, simple networks, parallel chains
**Time Limit**: 55-60 seconds

```javascript
// Level design templates
const skillBuildingTemplates = {
  doubleHub: {
    description: 'Two hub nodes with overlapping connections',
    complexity: 4,
    example: [[0, 2], [0, 3], [1, 2], [1, 3]]
  },
  
  parallelChains: {
    description: 'Multiple independent connection chains',
    complexity: 3,
    example: [[0, 1], [1, 2], [3, 4], [4, 5]]
  },
  
  triangle: {
    description: 'Basic geometric shape',
    complexity: 3,
    example: [[0, 1], [1, 2], [2, 0]]
  }
};
```

### Challenge Levels (11-20)
**Purpose**: Test mastery with complex patterns
**Node Count**: 6-9
**Pattern Types**: Complex networks, geometric shapes, asymmetric designs
**Time Limit**: 45-55 seconds

```javascript
const challengeTemplates = {
  star: {
    description: 'Central hub with outer ring connections',
    complexity: 6,
    nodeCount: 7,
    centerNode: true
  },
  
  mesh: {
    description: 'Highly interconnected network',
    complexity: 7,
    connectionDensity: 0.6 // 60% of possible connections
  },
  
  symmetrical: {
    description: 'Mirror-image patterns',
    complexity: 5,
    symmetryType: 'vertical' // or 'horizontal', 'rotational'
  }
};
```

### Master Levels (21+)
**Purpose**: Ultimate skill test
**Node Count**: 9-12
**Pattern Types**: Complex geometric shapes, dense networks, multi-hub systems
**Time Limit**: 30-45 seconds

## Pattern Generation Algorithm

### Basic Algorithm
```javascript
function generateLevelPattern(levelNumber) {
  const config = getLevelConfig(levelNumber);
  const nodes = generateNodePositions(config.nodeCount);
  const pattern = generateConnectionPattern(nodes, config);
  
  return {
    nodes,
    targetConnections: pattern,
    timeLimit: config.timeLimit,
    complexity: calculateComplexity(pattern)
  };
}

function getLevelConfig(level) {
  if (level <= 3) return tutorialConfig(level);
  if (level <= 10) return skillBuildingConfig(level);
  if (level <= 20) return challengeConfig(level);
  return masterConfig(level);
}
```

### Pattern Validation
```javascript
function validatePattern(nodes, connections) {
  const checks = {
    isConnected: validateConnectivity(nodes, connections),
    hasReasonableComplexity: validateComplexity(connections),
    isAesthetic: validateAesthetics(nodes, connections),
    isSolvable: validateSolvability(connections)
  };
  
  return Object.values(checks).every(check => check === true);
}

function validateConnectivity(nodes, connections) {
  // Ensure all nodes are part of the pattern (no isolated nodes)
  const connectedNodes = new Set();
  connections.forEach(([a, b]) => {
    connectedNodes.add(a);
    connectedNodes.add(b);
  });
  
  return connectedNodes.size === nodes.length;
}
```

## Difficulty Balancing

### Complexity Factors
```javascript
const complexityFactors = {
  nodeCount: {
    weight: 2.0,
    calculate: (nodes) => nodes
  },
  
  connectionDensity: {
    weight: 1.5,
    calculate: (connections, nodes) => connections.length / (nodes * (nodes - 1) / 2)
  },
  
  patternSymmetry: {
    weight: -0.5, // Symmetric patterns are easier
    calculate: (connections) => calculateSymmetryScore(connections)
  },
  
  crossingConnections: {
    weight: 1.0,
    calculate: (connections, nodePositions) => countCrossings(connections, nodePositions)
  }
};

function calculateLevelComplexity(level) {
  let totalComplexity = 0;
  
  Object.entries(complexityFactors).forEach(([factor, config]) => {
    const value = config.calculate(level);
    totalComplexity += value * config.weight;
  });
  
  return totalComplexity;
}
```

### Dynamic Difficulty Adjustment
```javascript
class DifficultyAdjuster {
  constructor() {
    this.playerPerformance = [];
    this.adjustmentThreshold = 3; // Adjust after 3 consecutive fails/successes
  }
  
  recordPerformance(level, completed, timeRemaining) {
    this.playerPerformance.push({
      level,
      completed,
      timeRemaining,
      timestamp: Date.now()
    });
    
    this.considerAdjustment();
  }
  
  considerAdjustment() {
    const recent = this.playerPerformance.slice(-this.adjustmentThreshold);
    
    if (recent.length < this.adjustmentThreshold) return;
    
    const allFailed = recent.every(p => !p.completed);
    const allSucceeded = recent.every(p => p.completed && p.timeRemaining > 10);
    
    if (allFailed) {
      this.suggestEasierLevel();
    } else if (allSucceeded) {
      this.suggestHarderLevel();
    }
  }
  
  suggestEasierLevel() {
    // Reduce complexity by decreasing connections or increasing time
    console.log('Player struggling - suggest reducing complexity');
  }
  
  suggestHarderLevel() {
    // Increase complexity or reduce time
    console.log('Player excelling - suggest increasing complexity');
  }
}
```

## Level Testing and Validation

### Playtesting Metrics
```javascript
const playtestingMetrics = {
  completionRate: {
    target: '>80% for levels 1-10, >60% for levels 11-20, >40% for levels 21+',
    measure: (attempts, completions) => completions / attempts
  },
  
  averageTime: {
    target: '50-80% of time limit used',
    measure: (completionTimes, timeLimit) => completionTimes.reduce((a, b) => a + b) / completionTimes.length / timeLimit
  },
  
  retryRate: {
    target: '<30% of players retry level',
    measure: (retries, attempts) => retries / attempts
  },
  
  engagementScore: {
    target: 'Players continue to next level >90% of time',
    measure: (continuations, completions) => continuations / completions
  }
};
```

### A/B Testing Framework
```javascript
class LevelTester {
  constructor() {
    this.variants = {};
    this.results = {};
  }
  
  addVariant(levelNumber, variantName, pattern) {
    if (!this.variants[levelNumber]) {
      this.variants[levelNumber] = {};
    }
    this.variants[levelNumber][variantName] = pattern;
  }
  
  getVariantForPlayer(levelNumber, playerId) {
    const variants = Object.keys(this.variants[levelNumber] || {});
    if (variants.length === 0) return null;
    
    // Deterministic assignment based on player ID
    const variantIndex = hashPlayerId(playerId) % variants.length;
    return variants[variantIndex];
  }
  
  recordResult(levelNumber, variantName, result) {
    const key = `${levelNumber}-${variantName}`;
    if (!this.results[key]) {
      this.results[key] = [];
    }
    this.results[key].push(result);
  }
  
  analyzeResults(levelNumber) {
    const variants = this.variants[levelNumber];
    const analysis = {};
    
    Object.keys(variants).forEach(variant => {
      const results = this.results[`${levelNumber}-${variant}`] || [];
      analysis[variant] = {
        completionRate: results.filter(r => r.completed).length / results.length,
        averageTime: results.reduce((sum, r) => sum + r.timeUsed, 0) / results.length,
        playerFeedback: results.map(r => r.satisfaction).filter(Boolean)
      };
    });
    
    return analysis;
  }
}
```

## Special Level Types

### Bonus Levels
**Frequency**: Every 10 levels
**Purpose**: Reward progress with fun, creative challenges
**Characteristics**: Unique mechanics, relaxed time pressure, special visual effects

### Recovery Levels
**Frequency**: After 3 consecutive failures
**Purpose**: Rebuild confidence and momentum
**Characteristics**: Slightly easier than expected, familiar patterns, generous time

### Skill Check Levels
**Frequency**: Levels 10, 20, 30, etc.
**Purpose**: Validate mastery before advancing to next tier
**Characteristics**: Comprehensive challenge using all learned concepts

This progression system ensures players remain engaged while being appropriately challenged throughout their journey.