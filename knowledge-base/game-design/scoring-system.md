# Scoring System - Neural Nexus

## Overview

The Neural Nexus scoring system is designed to reward both speed and accuracy while providing clear progression feedback to players. The system balances immediate gratification with long-term engagement.

## Core Scoring Components

### 1. Base Level Score
**Formula:** `100 points × level number`

**Rationale:**
- Provides increasing rewards for higher levels
- Simple calculation that players can understand
- Scales with difficulty progression
- Encourages continued play to reach higher levels

**Examples:**
- Level 1 completion: 100 points
- Level 5 completion: 500 points  
- Level 10 completion: 1,000 points
- Level 25 completion: 2,500 points

### 2. Time Bonus
**Formula:** `10 points × seconds remaining`

**Rationale:**
- Rewards efficient play without penalizing thoughtful players
- Creates tension between speed and accuracy
- Provides variable reward based on performance
- Encourages replay to improve times

**Implementation:**
```javascript
function calculateTimeBonus(timeLeft) {
  return timeLeft * 10;
}

// Example: Complete level with 15 seconds remaining = 150 bonus points
```

**Time Allocation by Level:**
- Levels 1-3: 60 seconds (generous learning time)
- Levels 4-6: 58 seconds (slight pressure)
- Levels 7-9: 56 seconds (building urgency)
- Levels 10+: Decreasing by 2 seconds every 3 levels (minimum 45 seconds)

### 3. Accuracy Multiplier (Future Feature)
**Planned Formula:** `1.0x - 2.0x based on mistakes`

**Design Concept:**
- Perfect completion (no invalid connections): 2.0x multiplier
- 1-2 mistakes: 1.5x multiplier
- 3-4 mistakes: 1.2x multiplier
- 5+ mistakes: 1.0x multiplier (base score)

## Scoring Psychology

### Immediate Feedback
**Visual Score Updates:**
- Points appear immediately upon level completion
- Animated number counting creates satisfaction
- Color coding indicates performance level
- Sound effects reinforce positive achievements

**Score Breakdown Display:**
```markdown
Level Complete!
Base Score: 500 points (Level 5)
Time Bonus: 180 points (18 seconds)
Total: 680 points
```

### Progress Indicators
**Cumulative Score Tracking:**
- Total score displayed prominently during gameplay
- Score history maintained in local storage (future)
- Personal best tracking for each level (future)
- Global leaderboards consideration (far future)

## Technical Implementation

### Score Calculation Function
```javascript
function calculateLevelScore(level, timeLeft, mistakes = 0) {
  const baseScore = 100 * level;
  const timeBonus = timeLeft * 10;
  const accuracyMultiplier = calculateAccuracyMultiplier(mistakes);
  
  const totalScore = Math.floor((baseScore + timeBonus) * accuracyMultiplier);
  
  return {
    baseScore,
    timeBonus,
    accuracyMultiplier,
    totalScore
  };
}
```

### Score Update Animation
```javascript
function animateScoreUpdate(newScore, oldScore) {
  const scoreDifference = newScore - oldScore;
  const duration = 1000; // 1 second
  const startTime = Date.now();
  
  function updateDisplay() {
    const elapsed = Date.now() - startTime;
    const progress = Math.min(elapsed / duration, 1);
    
    // Ease-out animation curve
    const easedProgress = 1 - Math.pow(1 - progress, 3);
    const currentScore = Math.floor(oldScore + (scoreDifference * easedProgress));
    
    document.getElementById('score').textContent = currentScore;
    
    if (progress < 1) {
      requestAnimationFrame(updateDisplay);
    }
  }
  
  updateDisplay();
}
```

## Balancing Considerations

### Preventing Score Inflation
**Design Safeguards:**
- Time limits prevent excessive farming
- Increasing difficulty maintains challenge
- Score scaling ensures later levels are more rewarding
- No score for incomplete levels

### Encouraging Healthy Play Patterns
**Positive Behaviors Rewarded:**
- Completing levels efficiently (time bonus)
- Progressing to harder content (base score scaling)
- Maintaining accuracy (future multiplier system)

**Avoiding Negative Patterns:**
- No penalty for taking time to think
- No score reduction for failed attempts
- Restart without penalty encourages experimentation

## Future Enhancements

### Achievement Integration
**Score-Based Achievements:**
- "High Scorer": Reach 10,000 total points
- "Speed Demon": Earn 500+ time bonus in single level
- "Perfectionist": Complete 10 levels with perfect accuracy
- "Marathon Runner": Reach level 50

### Daily Challenges
**Special Scoring Modes:**
- Speed run mode: Maximum time bonus
- Accuracy mode: Perfect connections required
- Endurance mode: Consecutive level completion
- Efficiency mode: Minimum connection path scoring

### Leaderboards
**Competition Features:**
- Daily high scores
- Weekly challenges
- Global rankings
- Friend comparisons

Last Updated: June 2025
Next Review: Monthly with user feedback analysis
