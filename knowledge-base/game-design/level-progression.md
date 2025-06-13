# Level Progression Design

## Difficulty Scaling Framework

### Core Progression Principles
1. **Gradual Complexity Introduction**: Each level adds manageable new challenge
2. **Pattern Recognition Development**: Allow players to learn through repetition
3. **Flow State Maintenance**: Balance challenge and skill to prevent frustration
4. **Confidence Building**: Occasional easier levels to maintain player motivation
5. **Skill Transfer**: Later levels build on patterns learned earlier

### Level Structure by Stage

#### Beginner Levels (1-5)
**Purpose**: Teach core mechanics and build confidence

```javascript
const beginnerLevels = {
  nodeCount: 3-4,
  connectionCount: 2-3,
  timeLimit: 60,
  patterns: [
    'simple_chain',      // A→B→C
    'triangle',          // A↔B↔C↔A
    'star_simple',       // A→B,C,D
    'parallel_lines'     // A→B, C→D
  ],
  objectives: [
    'Learn click and drag mechanics',
    'Understand dotted line targets', 
    'Develop basic pattern recognition',
    'Build confidence with success'
  ]
};
```

#### Intermediate Levels (6-15)
**Purpose**: Develop pattern recognition and spatial reasoning

```javascript
const intermediateLevels = {
  nodeCount: 4-7,
  connectionCount: 3-6,
  timeLimit: 50-55,
  patterns: [
    'hub_networks',      // Central node connects to others
    'chain_branches',    // Main chain with side branches
    'symmetric_patterns', // Mirror patterns
    'grid_subsets'       // Partial grid connections
  ],
  objectives: [
    'Recognize hub and spoke patterns',
    'Handle multiple connection points',
    'Develop systematic approach',
    'Improve time management'
  ]
};
```

#### Advanced Levels (16-25)
**Purpose**: Challenge spatial reasoning and strategy

```javascript
const advancedLevels = {
  nodeCount: 7-10,
  connectionCount: 6-12,
  timeLimit: 40-50,
  patterns: [
    'complex_webs',      // Highly interconnected
    'layered_networks',  // Multiple connection layers
    'asymmetric_designs', // Non-obvious patterns
    'efficiency_puzzles'  // Optimal path challenges
  ],
  objectives: [
    'Handle complex interconnections',
    'Develop strategic thinking',
    'Master time pressure',
    'Recognize advanced patterns'
  ]
};
```

#### Expert Levels (26+)
**Purpose**: Master-level challenges for dedicated players

```javascript
const expertLevels = {
  nodeCount: 10-12,
  connectionCount: 8-16,
  timeLimit: 30-45,
  patterns: [
    'maximum_complexity', // Dense interconnections
    'puzzle_variants',    // Special rules or constraints
    'artistic_patterns',  // Beautiful but complex designs
    'speed_challenges'    // Time-focused difficulties
  ],
  objectives: [
    'Perfect pattern recognition',
    'Master advanced strategies',
    'Handle maximum complexity',
    'Achieve expert-level flow'
  ]
};
```

## Pattern Type Definitions

### Basic Patterns (Levels 1-5)
```javascript
const basicPatterns = {
  linear_chain: {
    description: 'Simple A→B→C→D sequence',
    difficulty: 1,
    nodeRange: [3, 4],
    connectionFormula: 'nodes - 1'
  },
  
  simple_triangle: {
    description: 'Three nodes all connected',
    difficulty: 2, 
    nodeRange: [3, 3],
    connectionFormula: '3'
  },
  
  basic_star: {
    description: 'One central hub with spokes',
    difficulty: 2,
    nodeRange: [4, 5],
    connectionFormula: 'nodes - 1'
  }
};
```

### Intermediate Patterns (Levels 6-15)
```javascript
const intermediatePatterns = {
  branched_tree: {
    description: 'Tree structure with multiple branches',
    difficulty: 3,
    nodeRange: [5, 7],
    connectionFormula: 'nodes - 1 + Math.floor(nodes/3)'
  },
  
  partial_mesh: {
    description: 'Partially connected mesh network',
    difficulty: 4,
    nodeRange: [6, 8],
    connectionFormula: 'Math.floor(nodes * 1.5)'
  },
  
  symmetric_design: {
    description: 'Symmetrical connection patterns',
    difficulty: 4,
    nodeRange: [6, 8],
    connectionFormula: 'varies by symmetry type'
  }
};
```

### Advanced Patterns (Levels 16+)
```javascript
const advancedPatterns = {
  dense_network: {
    description: 'Highly interconnected nodes',
    difficulty: 5,
    nodeRange: [8, 12],
    connectionFormula: 'Math.floor(nodes * 2)'
  },
  
  layered_structure: {
    description: 'Multiple connection layers',
    difficulty: 5,
    nodeRange: [9, 12],
    connectionFormula: 'complex algorithm'
  },
  
  efficiency_puzzle: {
    description: 'Optimal path challenges',
    difficulty: 6,
    nodeRange: [10, 12],
    connectionFormula: 'maximum complexity'
  }
};
```

## Difficulty Adjustment Algorithm

### Dynamic Difficulty
```javascript
function calculateLevelDifficulty(level) {
  const baseNodeCount = 3;
  const nodeGrowthRate = 0.3;
  const maxNodes = 12;
  
  // Gradually increase node count
  const nodeCount = Math.min(
    Math.floor(baseNodeCount + level * nodeGrowthRate),
    maxNodes
  );
  
  // Connection count scales with nodes and level
  const connectionMultiplier = 1 + (level * 0.05);
  const baseConnections = nodeCount - 1;
  const connectionCount = Math.floor(baseConnections * connectionMultiplier);
  
  // Time limit decreases gradually
  const baseTime = 60;
  const timeReduction = Math.floor(level / 3) * 2;
  const timeLimit = Math.max(30, baseTime - timeReduction);
  
  return {
    nodeCount,
    connectionCount: Math.min(connectionCount, nodeCount * 2),
    timeLimit,
    complexityScore: calculateComplexity(nodeCount, connectionCount)
  };
}
```

### Complexity Scoring
```javascript
function calculateComplexity(nodeCount, connectionCount) {
  const nodeFactor = nodeCount * 0.3;
  const connectionFactor = connectionCount * 0.5;
  const densityFactor = (connectionCount / nodeCount) * 0.2;
  
  return Math.floor(nodeFactor + connectionFactor + densityFactor);
}
```

## Player Progression Metrics

### Success Indicators
- **Completion Rate**: >80% for current difficulty tier
- **Time Efficiency**: Consistent improvement in completion times
- **Pattern Recognition**: Faster start times (less hesitation)
- **Error Rate**: Fewer invalid connection attempts

### Progression Gates
```javascript
const progressionGates = {
  beginnerToIntermediate: {
    criteria: [
      'Complete levels 1-5 with >80% success rate',
      'Average completion time <45 seconds',
      'Less than 2 invalid attempts per level'
    ]
  },
  
  intermediateToAdvanced: {
    criteria: [
      'Complete levels 6-15 with >70% success rate',
      'Handle 6+ node networks confidently',
      'Demonstrate pattern recognition speed'
    ]
  },
  
  advancedToExpert: {
    criteria: [
      'Complete levels 16-25 with >60% success rate',
      'Master complex interconnected patterns',
      'Maintain performance under time pressure'
    ]
  }
};
```

## Balancing and Tuning

### Playtesting Feedback Loops
1. **Immediate Feedback**: Success/failure rates per level
2. **Completion Analytics**: Time distributions and attempt counts  
3. **Frustration Points**: Levels with high abandonment rates
4. **Flow Breaks**: Sudden difficulty spikes or boring plateaus

### Adjustment Parameters
```javascript
const tuningParameters = {
  tooEasy: {
    indicators: ['>95% completion rate', 'Average time <20 seconds'],
    adjustments: ['Add 1-2 connections', 'Reduce time limit by 5s', 'Increase pattern complexity']
  },
  
  tooHard: {
    indicators: ['<50% completion rate', 'High abandonment rate'],
    adjustments: ['Remove 1-2 connections', 'Add 10s to time limit', 'Simplify pattern type']
  },
  
  justRight: {
    indicators: ['70-85% completion rate', 'Engaged retry behavior'],
    actions: ['Maintain current parameters', 'Use as template for similar levels']
  }
};
```

### A/B Testing Framework
```javascript
const abTestingLevels = {
  testVariants: [
    {
      name: 'standard_progression',
      description: 'Current difficulty curve'
    },
    {
      name: 'gentler_slope', 
      description: 'Slower difficulty increase'
    },
    {
      name: 'steeper_challenge',
      description: 'Faster ramp to complexity'
    }
  ],
  
  metrics: [
    'level_completion_rate',
    'session_length', 
    'player_return_rate',
    'user_satisfaction_score'
  ]
};
```

## Recovery and Flow Management

### Difficulty Relief Valves
- **Confidence Boosters**: Easier levels every 5-7 levels
- **Pattern Variety**: Mix familiar and new pattern types
- **Time Flexibility**: Slightly longer time limits after difficulty spikes
- **Visual Clarity**: Ensure complex levels have clear visual hierarchy

### Player Journey Optimization
```javascript
const playerJourney = {
  onboarding: {
    levels: '1-3',
    focus: 'Mechanics mastery',
    successRate: '>90%'
  },
  
  engagement: {
    levels: '4-15', 
    focus: 'Skill development',
    successRate: '70-85%'
  },
  
  mastery: {
    levels: '16+',
    focus: 'Expert challenges', 
    successRate: '60-75%'
  }
};
```

This progression system should be continuously refined based on player data and feedback to maintain optimal challenge and engagement throughout the player's journey.