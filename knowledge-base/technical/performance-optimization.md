# Performance Optimization Guide

## Current Performance Targets

### Frame Rate Goals
- **Desktop**: Consistent 60fps on mid-range hardware (2019+)
- **Mobile**: Minimum 30fps on devices from 2020+
- **Tablet**: 45-60fps for smooth touch interaction
- **Degradation Strategy**: Reduce particle effects before dropping frame rate

### Memory Usage Targets
- **Desktop**: <100MB during gameplay
- **Mobile**: <50MB during gameplay
- **Peak Usage**: <150MB during intensive scenes (level completion effects)

### Loading Performance
- **Initial Load**: <3 seconds on 3G connection
- **Level Transition**: <500ms between levels
- **Asset Loading**: Progressive where possible

## Canvas Optimization Techniques

### Efficient Rendering
```javascript
// Use requestAnimationFrame for smooth animation
function gameLoop() {
  // Limit updates to 60fps maximum
  requestAnimationFrame(gameLoop);
  
  // Only redraw if something changed
  if (gameState.needsRedraw) {
    render();
    gameState.needsRedraw = false;
  }
}

// Efficient canvas clearing
function clearCanvas() {
  // Fastest method for full clear
  ctx.clearRect(0, 0, canvas.width, canvas.height);
}
```

### Drawing Optimization
```javascript
// Batch similar drawing operations
function drawConnections() {
  ctx.lineWidth = 3;
  
  gameState.connections.forEach(connection => {
    const gradient = ctx.createLinearGradient(
      connection.nodeA.x, connection.nodeA.y,
      connection.nodeB.x, connection.nodeB.y
    );
    gradient.addColorStop(0, '#00d4ff');
    gradient.addColorStop(0.5, '#ff00ff');
    gradient.addColorStop(1, '#00d4ff');
    
    ctx.strokeStyle = gradient;
    ctx.beginPath();
    ctx.moveTo(connection.nodeA.x, connection.nodeA.y);
    ctx.lineTo(connection.nodeB.x, connection.nodeB.y);
    ctx.stroke();
  });
}
```

## Memory Management

### Object Pooling for Particles
```javascript
class ParticlePool {
  constructor(initialSize = 100) {
    this.pool = [];
    this.active = [];
    
    // Pre-create objects
    for (let i = 0; i < initialSize; i++) {
      this.pool.push(new Particle());
    }
  }
  
  acquire() {
    let particle = this.pool.pop();
    if (!particle) {
      particle = new Particle();
    }
    this.active.push(particle);
    return particle;
  }
  
  release(particle) {
    const index = this.active.indexOf(particle);
    if (index !== -1) {
      this.active.splice(index, 1);
      particle.reset();
      this.pool.push(particle);
    }
  }
}
```

## Performance Monitoring

### Frame Rate Monitoring
```javascript
class PerformanceMonitor {
  constructor() {
    this.frameTimes = [];
    this.lastTime = performance.now();
    this.frameCount = 0;
  }
  
  update() {
    const currentTime = performance.now();
    const frameTime = currentTime - this.lastTime;
    this.lastTime = currentTime;
    
    this.frameTimes.push(frameTime);
    if (this.frameTimes.length > 60) {
      this.frameTimes.shift();
    }
    
    this.frameCount++;
    
    // Log performance every 5 seconds
    if (this.frameCount % 300 === 0) {
      this.logPerformance();
    }
  }
  
  logPerformance() {
    const avgFrameTime = this.frameTimes.reduce((a, b) => a + b) / this.frameTimes.length;
    const fps = 1000 / avgFrameTime;
    
    console.log(`Performance: ${fps.toFixed(1)} fps (${avgFrameTime.toFixed(1)}ms avg frame time)`);
    
    if (performance.memory) {
      const memory = performance.memory.usedJSHeapSize / 1024 / 1024;
      console.log(`Memory usage: ${memory.toFixed(1)} MB`);
    }
  }
}
```

### Memory Leak Prevention
```javascript
// Proper cleanup patterns
function cleanupLevel() {
  // Remove all event listeners
  gameState.nodes.forEach(node => {
    if (node.cleanup) node.cleanup();
  });
  
  // Clear arrays properly
  gameState.nodes.length = 0;
  gameState.connections.length = 0;
  gameState.particles.length = 0;
  
  // Clear any timers
  clearInterval(gameState.timerId);
  gameState.timerId = null;
}
```

## Mobile Optimizations

### Touch Performance
```javascript
// Throttle touch events to 60fps max
const throttledTouchMove = throttle((e) => {
  e.preventDefault();
  handleTouchMove(e);
}, 16);

canvas.addEventListener('touchmove', throttledTouchMove, {passive: false});
```

### Battery Optimization
```javascript
// Reduce frame rate when tab is not visible
document.addEventListener('visibilitychange', () => {
  if (document.hidden) {
    gameState.targetFPS = 15; // Reduce to save battery
  } else {
    gameState.targetFPS = 60; // Resume full speed
  }
});
```

## Performance Testing Checklist

### Manual Testing
- [ ] 60fps on desktop Chrome/Firefox/Safari
- [ ] 30fps+ on iPhone 12 Safari
- [ ] 30fps+ on Android Chrome (mid-range device)
- [ ] No frame drops during particle effects
- [ ] Smooth level transitions
- [ ] Memory usage stable over 20+ levels

### Automated Monitoring
```javascript
// Performance testing helper
if (location.hostname === 'localhost') {
  window.performanceTest = {
    monitor: new PerformanceMonitor(),
    logMemory: () => {
      if (performance.memory) {
        const used = Math.round(performance.memory.usedJSHeapSize / 1024 / 1024);
        const total = Math.round(performance.memory.totalJSHeapSize / 1024 / 1024);
        console.log(`Memory: ${used}MB / ${total}MB`);
      }
    },
    startProfiling: () => {
      console.profile('Game Performance');
    },
    stopProfiling: () => {
      console.profileEnd('Game Performance');
    }
  };
}
```

This guide should be updated as new optimization techniques are discovered and performance targets evolve.