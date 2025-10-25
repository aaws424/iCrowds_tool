# On Curve iCrowd System - User Documentation
## Overview
The On Curve System creates organized lines and queues of agents following curve paths, ideal for simulating waiting lines, processional movements, and structured formations.

## Distribution Tab

### Basic Setup
- **View Mode**: Render - Standard visualization mode
- **Terrain**: On Curve Terrain - Input terrain for ground alignment

### Distribution Types

#### 1. Radius Based Distribution
**Agents distributed around curve points based on radius**
- **Radius Control**: Edit curve points in Edit Mode and use **Alt+S** to scale radius at each point
- **Radius Multiplier**: 512.000 - Global multiplier for all radius values
- **Effect**: More agents in areas with larger radius values

#### 2. Count Based Distribution
**Fixed number of agents per curve**
- **Min (Per Curve)**: 50 - Minimum agents per curve
- **Max (Per Curve)**: 100 - Maximum agents per curve
- **System**: Randomly selects between min/max for each curve

#### 3. Min Distance Distribution
**Agents spaced by minimum distance**
- **Length**: 0.2 m - Minimum spacing between agents
- **Use**: Evenly spaced queues and lines

### Global Limits
- **Max Agents Num**: 100,000.000 - Total maximum agents in system

### Positioning Controls

#### Personal Space
- **Relax Iterations**: 12 - Processing passes for collision resolution
- **Min Distance**: 0.500 m - Minimum space between agents
- **Max Distance**: 1.000 m - Maximum personal buffer
- **Seed**: 2 - Randomization pattern

#### Position Variation
- **Position Variation**: 2.934 - Random offset from perfect curve alignment
- **Seed**: 86 - Randomization pattern
- **Effect**: Creates natural, imperfect lines instead of perfect grid

## Settings Tab

### Orientation Control

#### Rotation Modes
1. **Default**
   - Consistent facing direction
   - Uniform appearance along curves

2. **Randomize**
   - Random rotation per agent
   - Natural variation in facing directions

3. **At Object**
   - All agents face toward target object
   - Optional randomization for natural look

#### Up Direction
- **Value**: 1.000 - Controls alignment with terrain normals
- **Function**: Keeps agents properly oriented to ground surface
- **Adjustment**: Higher values increase terrain following

### Scale Variation
- **Min Scale**: 0.900 - Smallest agent size
- **Max Scale**: 1.000 - Largest agent size
- **Seed**: 0 - Randomization pattern
- **Effect**: Natural size variation in crowd

## Agent Configuration

### Input Requirements
- **Animated Agents**: Collections with idle animations
- **Multiple Collections**: Support for varied agent types
- **Probability Control**: Balance between different agent collections

### Customization
- **Custom Collections**: Import additional agent types
- **Clothing Variations**: Modify agent appearances
- **Collection Blending**: Mix different agent types

## Curve Editing Guide

### Radius-Based Setup
1. Select curve object
2. Enter Edit Mode (Tab)
3. Select curve points where you want more agents
4. Press **Alt+S** and drag to increase radius
5. Larger radius = more agents around that point

### Curve Types
- **Open Curves**: Lines and queues
- **Closed Curves**: Circular formations and surrounding areas
- **Multiple Curves**: Complex formations and multiple lines

## Typical Workflow

1. **Curve Creation**
   - Draw curves representing desired lines or formations
   - Adjust radius at key points for density variation
   - Set curve object in distribution panel

2. **Distribution Setup**
   - Choose distribution type (Radius/Count/Min Distance)
   - Set agent limits and spacing parameters
   - Adjust position variation for natural look

3. **Orientation & Scale**
   - Set rotation mode based on scene needs
   - Adjust up direction for proper ground alignment
   - Configure scale variations

4. **Agent Assignment**
   - Select agent collections
   - Balance probabilities between collections
   - Fine-tune appearance variations

## Best Practices

### For Realistic Lines
- Use **position variation** to avoid perfect grid patterns
- Combine **min distance** with **personal space** for natural spacing
- Use **radius based** for areas needing higher density
- Apply slight **scale variation** for diverse crowds

### Curve Setup Tips
- Use smoother curves for more natural agent distribution
- Adjust radius gradually for smooth density transitions
- Test different distribution types for each scene need
- Use multiple simple curves instead of one complex curve

### Performance Optimization
- Use appropriate relax iterations (12 is good for quality)
- Set realistic max agent counts
- Balance position variation with performance needs
- Use simpler curves for large-scale simulations

## Use Cases

- **Waiting lines** for attractions, security, or ticketing
- **Processional movements** in ceremonies or events
- **Queue simulations** for retail or services
- **Formation patterns** for military or performance groups
- **Surrounding areas** around objects or stages
- **Path lining** for parades or special events

The On Curve System provides precise control over linear and curved formations, making it ideal for any scenario requiring organized lines, queues, or structured crowd arrangements.