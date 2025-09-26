# Walkers iCrowd Simulation System - User Documentation

## 1.0 System Overview

The Walkers Path System is a curve-based pedestrian animation tool that generates animated characters moving along user-defined paths. The system creates natural movement patterns around drawn curves with configurable lane behavior, density, and motion parameters.

## 2.0 Quick Start

### 2.1 Basic Setup
1. **Create a curve** in your scene
2. **Connect the curve** to "Walkers Curve" input
3. **Set Agent Object** or **Collection** for characters
4. **Adjust Count** for desired number of walkers
5. **Play timeline** to activate animation

## 3.0 Input Configuration

### 3.1 Primary Inputs
**Terrain** (Optional)
- Purpose: Ground surface for elevation matching
- Usage: Connect terrain mesh for height alignment

**Input Type**
- Purpose: Determines how paths are generated
- Options: Single curve or curve collection

**Walkers Curves/Walkers Curve**
- Purpose: Path definition for walker movement
- Usage: Connect Bézier curve or curve collection

## 4.0 Agent Configuration

### 4.1 Agent Assignment
**Object**
- Purpose: Single character object to duplicate
- Usage: Connect a mesh object with walk animation

**Collection**
- Purpose: Multiple character variations
- Usage: Connect collection of character objects

### 4.2 Path Parameters
**Lanes**
- Purpose: Number of parallel walking paths
- Effect: Creates multi-lane pedestrian flow
- Range: 1-8 (typical urban sidewalk capacity)

**Count**
- Purpose: Total number of walkers on path
- Effect: Controls pedestrian density
- Recommendation: Start with 10-20 for testing

**Direction**
- Purpose: Movement direction along curve
- Options: Forward, Reverse, Bidirectional

**Loop Type**
- Purpose: Path cycling behavior
- Options: 
  - Single Pass: One-time traversal
  - Loop: Continuous circulation
  - Ping-Pong: Forward/reverse alternation

## 5.0 Motion Control

### 5.1 Noise Parameters
**Power**
- Purpose: Intensity of path variation
- Effect: Creates natural path deviations
- Range: 0.0 (exact path) to 1.0 (maximum variation)

**Offset**
- Purpose: Lateral position variation
- Effect: Random lane positioning
- Usage: Creates organic spacing

**Scale**
- Purpose: Spatial frequency of noise
- Effect: Controls deviation pattern scale

### 5.2 Speed Management
**Speed**
- Purpose: Base movement velocity
- Units: Blender units per second
- Typical: 1.0-2.0 for walking speed

## 6.0 Density & Spacing

### 6.1 Density Control
**Density**
- Purpose: Overall walker concentration
- Effect: Multiplier for Count parameter
- Range: 0.0 (none) to 2.0 (double density)

**Randomness**
- Purpose: Distribution variation
- Effect: Irregular spacing between walkers
- Usage: Avoids robotic uniformity

**Seed**
- Purpose: Randomization control
- Effect: Unique distribution patterns

### 6.2 Personal Space Configuration
**Min/Max Space**
- Purpose: Inter-walker distance constraints
- Min: Minimum allowed distance (avoid collision)
- Max: Maximum allowed distance (maintain group cohesion)

**Seed**
- Purpose: Personal space randomization
- Effect: Natural distance variations

## 7.0 Implementation Guide

### 7.1 Basic Workflow
```
1. Create and position Bézier curve for desired path
2. Connect curve to "Walkers Curve" socket
3. Assign character object/collection to "Object" or "Collection"
4. Set Count to desired number of walkers (10-50 typical)
5. Configure Lanes for path width (2-4 for sidewalks)
6. Adjust Speed for realistic movement (1.2-1.8)
7. Enable timeline playback to activate animation
```

### 7.2 Advanced Configurations

**Multi-lane Sidewalk**
```
- Lanes: 3
- Count: 25
- Direction: Bidirectional
- Loop Type: Loop
- Power: 0.3 (subtle variation)
```

**Single-file Path**
```
- Lanes: 1
- Count: 15
- Direction: Forward
- Loop Type: Single Pass
- Power: 0.1 (minimal deviation)
```

## 8.0 Animation Integration

### 8.1 Character Requirements
- Walk cycle animation required
- Proper armature rigging for natural movement
- Scale matching to scene proportions

### 8.2 Motion Blending
- System automatically matches animation speed to path velocity
- Supports walk/run cycle blending based on speed parameter
- Root motion alignment with path curvature

## 9.0 Performance Optimization

### 9.1 Efficiency Guidelines
- Use simplified character meshes for large counts
- Limit Count to scene requirements (typically < 100)
- Use moderate Power values (0.2-0.5) for balance
- Consider instancing for identical characters

### 9.2 Quality Settings
```
High Quality:
- Count: 50-100
- Power: 0.3-0.6
- High-detail characters

Performance Mode:
- Count: 10-30
- Power: 0.1-0.3
- Low-poly characters
```

## 10.0 Use Cases

### 10.1 Urban Scenarios
- Sidewalk pedestrian flows
- Park pathway circulation
- Shopping district foot traffic
- Event venue entry/exit flows

### 10.2 Architectural Visualization
- Building entrance approaches
- Plaza and courtyard movement
- Stairway and ramp circulation
- Queue simulation for facilities

## 11.0 Troubleshooting

### 11.1 Common Issues
**Walkers Not Moving**
- Verify curve connection to correct socket
- Check timeline is playing
- Validate character objects have animations

**Uneven Spacing**
- Adjust Personal Space Min/Max values
- Reduce Randomness parameter
- Check curve resolution and length

**Unnatural Movement**
- Reduce Power parameter for straighter paths
- Adjust Speed to match animation cycle
- Verify proper character scaling

## 12.0 Technical Notes

### 12.1 Curve Requirements
- Use Bézier curves for smooth paths
- Ensure adequate curve resolution
- Avoid sharp angles for natural movement
- Closed curves work well for looped paths

### 12.2 System Integration
- Compatible with main crowd system
- Can be used alongside area-based crowds
- Supports hybrid approaches (path + free movement)

---

*Documentation Version: 1.0 | System: Walkers Path Module*