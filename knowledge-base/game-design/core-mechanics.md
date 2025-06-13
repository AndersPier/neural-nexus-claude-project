# Core Mechanics - Neural Nexus

## Connection System

### Basic Mechanics
The core gameplay revolves around creating connections between nodes by dragging from one node to another. This system is designed to be:

- **Intuitive**: Natural click/drag or tap/drag interaction
- **Responsive**: Immediate visual feedback for all actions
- **Forgiving**: Clear indication of valid targets and actions
- **Accessible**: Works consistently across all devices and input methods

### Node Types and Behavior

#### Source Nodes (Green - #00ff64)
- **Purpose**: Starting points for network patterns
- **Visual**: Bright green color with enhanced glow
- **Behavior**: Often serve as connection origins in level patterns
- **Player Guidance**: Usually good starting points for solving puzzles

#### Normal Nodes (Blue - #333366/#00d4ff)
- **Purpose**: Standard connection points
- **Visual**: Blue color that brightens when connected
- **Behavior**: Can connect to any other node
- **Player Guidance**: Form the majority of puzzle elements

#### Target Nodes (Orange - #ff6400)
- **Purpose**: End points for network patterns
- **Visual**: Orange color with distinctive glow
- **Behavior**: Often serve as connection destinations
- **Player Guidance**: Usually good final connection points

### Connection Rules

#### Valid Connections
```javascript
// Connection validation logic
function canConnect(nodeA, nodeB) {
  return nodeA !== nodeB &&                    // Can't connect to self
         !connectionExists(nodeA, nodeB) &&    // No duplicate connections
         nodeA.type !== 'disabled' &&          // Node must be active
         nodeB.type !== 'disabled';            // Target must be active
}
```

#### Visual Feedback System
- **Hover State**: Nodes highlight when mouse/touch approaches
- **Drag Preview**: Dotted line shows connection being created
- **Success State**: Solid colored line with particle effects
- **Error State**: Red flash for invalid connection attempts
- **Completion State**: Energy flow animation through completed connections

### Pattern Matching System

#### Target Pattern Display
- **Visual Representation**: Faint dotted white lines (#ffffff with 0.3 opacity)
- **Line Style**: 5px dash, 5px gap pattern
- **Stroke Width**: 2px for clear visibility without overwhelming
- **Update Frequency**: Static display, updates only on level change

#### Completion Detection
```javascript
function checkLevelComplete() {
  const madeConnections = gameState.connections.map(conn => 
    [Math.min(conn.nodeA.id, conn.nodeB.id), Math.max(conn.nodeA.id, conn.nodeB.id)]
  );
  
  const targetConnections = gameState.targetPattern.map(([a, b]) => 
    [Math.min(a, b), Math.max(a, b)]
  );
  
  return targetConnections.every(target => 
    madeConnections.some(made => made[0] === target[0] && made[1] === target[1])
  );
}
```

### Input Handling

#### Mouse Events
- **mousedown**: Initiate connection drag
- **mousemove**: Update drag preview (throttled to 60fps)
- **mouseup**: Complete or cancel connection

#### Touch Events
- **touchstart**: Begin touch interaction
- **touchmove**: Update touch drag (with preventDefault)
- **touchend**: Finalize touch connection

#### Cross-Platform Considerations
```javascript
// Unified event handling
function getEventPosition(event) {
  const rect = canvas.getBoundingClientRect();
  
  if (event.touches) {
    // Touch event
    return {
      x: event.touches[0].clientX - rect.left,
      y: event.touches[0].clientY - rect.top
    };
  } else {
    // Mouse event
    return {
      x: event.clientX - rect.left,
      y: event.clientY - rect.top
    };
  }
}
```

## Difficulty Progression

### Level Generation Algorithm

#### Node Count Scaling
```javascript
const nodeCount = Math.min(5 + Math.floor(level * 0.7), 12);
```
- **Level 1-3**: 5-6 nodes (learning phase)
- **Level 4-10**: 6-9 nodes (skill building)
- **Level 11-20**: 9-12 nodes (challenge phase)
- **Level 21+**: 12 nodes (mastery phase)

#### Connection Complexity
```javascript
const connectionCount = Math.min(
  nodeCount - 1 + Math.floor(level / 2), 
  nodeCount * 2
);
```
- **Early Levels**: Minimum spanning tree patterns
- **Mid Levels**: Additional parallel paths
- **Late Levels**: Near-complete graphs with strategic complexity

#### Timing Progression
```javascript
const timeLimit = Math.max(45, 60 - Math.floor(level / 3) * 2);
```
- **Level 1-2**: 60 seconds (generous learning time)
- **Level 3-5**: 58 seconds (slight pressure introduction)
- **Level 6-8**: 56 seconds (building urgency)
- **Level 9+**: Continues decreasing to minimum of 45 seconds

### Pattern Design Philosophy

#### Early Game (Levels 1-5)
- **Simple chains**: A→B→C linear patterns
- **Basic shapes**: Triangles and simple stars
- **Clear structure**: Obvious starting and ending points
- **Minimal complexity**: 3-5 connections maximum

#### Mid Game (Levels 6-15)
- **Hub patterns**: Central nodes with multiple connections
- **Parallel paths**: Multiple connection chains
- **Symmetrical designs**: Balanced, aesthetically pleasing patterns
- **Moderate complexity**: 5-8 connections

#### Late Game (Levels 16+)
- **Complex networks**: Interconnected webs of connections
- **Strategic puzzles**: Require planning and optimization
- **Near-complete graphs**: Most nodes connect to most others
- **High complexity**: 8-12 connections

## Performance Optimization

### Node Rendering Optimization
```javascript
// Efficient node drawing with minimal canvas operations
function drawNode(node) {
  const time = Date.now() * 0.003;
  const pulse = Math.sin(time + node.pulsePhase) * 0.2 + 1;
  
  // Pre-calculate positions to avoid repeated math
  const x = node.x;
  const y = node.y;
  const radius = node.radius * pulse;
  
  // Batch similar drawing operations
  ctx.save();
  drawNodeGlow(x, y, radius, node.type);
  drawNodeCore(x, y, radius, node.type);
  drawNodeHighlight(x, y, radius);
  ctx.restore();
}
```

### Connection System Performance
- **Event Throttling**: Mouse/touch events limited to 60fps
- **Hit Detection**: Optimized circle-point collision detection
- **Rendering**: Batched line drawing operations
- **Memory**: Reuse connection objects instead of creating new ones

### Success Metrics
- **Completion Rate**: >80% for first 10 levels
- **Engagement**: Average 5+ minute sessions
- **Retention**: >60% return for second session
- **Performance**: 60fps on desktop, 30fps+ on mobile