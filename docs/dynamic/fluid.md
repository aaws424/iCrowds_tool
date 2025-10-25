# Fluid iCrowd System - User Documentation
## Overview

The Fluid System is an alternative agent distribution and control system that provides three distinct distribution methods and specialized control objects to influence agent movement and behavior.

## Distribution

### View Mode
- **Render**: Standard visualization mode for agent distribution

### Terrain Configuration
- **Fluid Terrain**: Enable fluid-based terrain interactions

### Distribution Types

The system supports three distribution methods:

#### 1. Distribute On Terrain
- Distributes agents across the entire input terrain surface
- **Weight Paint**: Use brush tools to paint distribution density on specific terrain areas
- **Vertex Group Mask**: Utilize vertex groups to control agent placement

#### 2. Distribute On Vertex
- Places agents specifically on mesh vertices
- Provides precise control over agent positioning

#### 3. Crowd System Distribution
- Integrates with external crowd systems
- Takes existing instances and replaces them with dynamic agents
- Enables migration from static crowds to interactive agent systems

### Distribution Parameters

- **Distance Min**: Minimum spacing between agents (0.5 m)
- **Density Max**: Maximum agent density (1.000)
- **Seed**: Randomization seed for distribution patterns (0)

### Weight Painting
- **Brush Tool**: Interactive painting interface for density control
- **Vertex Group Mask**: Use predefined vertex groups as distribution masks

## Settings

### Speed Thresholds
- **Walk Speed**: 0.010 m/s - Agents use walking animation below this speed
- **Run Speed**: 1.000 m/s - Agents switch to running animation above this speed
- **Max Speed**: 1.000 m/s - Absolute maximum movement speed

### Collision Prevention
- **Relax Iterations**: 1 iteration - Controls how agents avoid passing through each other
  - Higher values increase collision avoidance quality
  - Lower values improve performance

## Control Objects

### Three Control Types

Users can input single objects or collections for each control type:

#### 1. Flow Curves
- **Function**: Agents follow the tangent direction of curves
- **Zone of Effect**: Controlled by curve radius
- **Editing**:
  - Select curve points in Edit Mode
  - Use **Alt+S** to scale radius up or down
  - Larger radius = wider influence area

#### 2. Attracters
- **Function**: Pull agents toward the object location
- **Radius Control**: Object scale determines attraction area
- **Recommended**: Use empty sphere objects for clear visualization

#### 3. Repelers
- **Function**: Push agents away from object location
- **Radius Control**: Object scale determines repulsion area
- **Recommended**: Use empty sphere objects for clear visualization

## Agents Configuration

### Predefined Agent Collections
- **Male Agents**:
  - mem Idle
  - mem Walk
  - mem Run
- **Female Agents**:
  - women Idle
  - women Walk
  - women Run

### Agent Management

#### Density Control
- **Probability**: 0.500 - Controls spawn likelihood of agent collections

#### Agent Settings
- Separate configuration for Male and Female agents
- Gender-specific behavior and appearance settings

#### Customization Options
- **Include/Discard**: Add or remove agents from simulation
- **Customize Individual Agents**: Modify specific agent instances (e.g., man1)
- **Change Clothes**: Swap clothing and appearance elements
- **Change Action**: Modify animation behaviors
- **Include All**: Apply changes to entire agent groups

### Custom Agent Creation
- **Object**: Reference to agent mesh object
- **Collection**: Agent group organization
- **Agent Mesh**: 3D model reference
- **Agent Armature**: Animation skeleton and rigging
- **Gender**: Male/Female classification for behavior rules

## Workflow

1. **Distribution Setup**:
   - Choose distribution type (Terrain/Vertex/Crowd System)
   - Configure density and spacing parameters
   - Use weight painting for area-specific control

2. **Agent Configuration**:
   - Select agent collections and probabilities
   - Customize individual agents as needed
   - Add custom agents if required

3. **Control Placement**:
   - Add Flow Curves for guided movement paths
   - Place Attracters at points of interest
   - Use Repelers to block areas or create obstacles

4. **Simulation Tuning**:
   - Adjust speed thresholds for animation transitions
   - Set relax iterations for collision quality
   - Fine-tune control object radii and positions

## Best Practices

- Use empty spheres for attracter/repeler objects for clear visualization
- Test flow curves with varying radii to create natural movement patterns
- Balance agent density with performance considerations
- Use weight painting to create realistic concentration areas
- Start with lower relax iterations and increase if collision issues occur

This Fluid System provides flexible agent distribution and sophisticated movement control, enabling complex crowd simulations with natural-looking behaviors and interactions.