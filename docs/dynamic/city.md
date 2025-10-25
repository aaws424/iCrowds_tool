# City iCrowd Simulation System - User Documentation

## Overview

The Dynamic Behaviour System is a comprehensive simulation system that controls agent behaviors, movement, and interactions within urban environments. The system consists of three main components: Distribution, Settings, and Agents.

## Distribution

### Input Configuration
The system supports two types of urban environment inputs:

- **iCity**: Pre-built city environment
- **Custom City**: User-defined city configuration consisting of:
  - **City Ground**: Base terrain and infrastructure
  - **Colliders**: Obstacles and navigation boundaries

### Distribution Settings

#### Object Configuration
- **Custom City Ground**: Enable/disable custom ground objects
- **Colliders**: Toggle collision detection objects
- **Custom City Colliders Collection**: Organize collision objects in dedicated collections

#### Agent Scattering
- **Viewer**: Render visualization mode
- **Density Controls**:
  - **Density**: 1 meter spacing between agents
  - **Max**: Maximum of 2,000 agents
  - **Factor**: Distribution factor (default: 0.407)
  - **Seed**: Randomization seed for agent placement

#### Weight Painting
- **Vertex Group Mask**: Use vertex groups to control agent distribution density

## Settings

### Speed Configuration
- **Speed Scalar**: Global multiplier for all agent speeds (default: 1.000)
- **Walking Speed**: Threshold speed for walking animation (0.010)
- **Run Speed**: Threshold speed for running animation (1.200)
- **Max Speed**: Maximum possible speed in the system (10.000)

### Activities System

#### Activity Types
The system supports multiple activity types:
- **Fun** - Entertainment and leisure activities
- **Sleep** - Resting and sleeping locations
- **Hunger** - Food and dining locations
- **Bladder** - Restroom facilities

#### Activity Input
Users can input either:
- **Single Object**: Individual activity location
- **Collection**: Group of related activities (e.g., collection of fun locations)

#### Needs-Based Behavior
Each agent maintains dynamic needs sliders for:
- Fun
- Sleep
- Hunger
- Bladder

**Behavior Flow**:
1. When a need decreases below threshold, agent pathfinds to nearest relevant activity
2. Upon reaching activity location, the corresponding need parameter is filled
3. Agent then seeks to fulfill other deficient needs
4. Continuous cycle of need fulfillment creates emergent behavior patterns

### Debug Features

#### Movement Debugging
- **Debug Movement**: Visualizes agent movement directions
- **Path Finding Grid**: Displays navigation mesh used for pathfinding

#### Activity Debugging
- **Debug Activity**: Shows real-time needs sliders above each agent
- **Activity Indicator**: Circular icon above slider indicates current active action

### Performance Optimization

#### Path Finding
- **Path Finding Details**: Controls grid resolution (default: 1.000)
  - Lower values increase performance for large-scale simulations
  - Higher values provide more precise navigation

#### Time Management
- **Time Scale**: Controls need depletion rate (default: 0.008)
  - Higher values make needs deplete faster
  - Affects simulation pacing (e.g., agents feel sleepy more quickly)

## Agents

### Agent Collections
Pre-configured agent animation states:
- **Male Agents**: 
  - men Idle
  - men Walk  
  - men Run
- **Female Agents**:
  - women Idle
  - women Walk
  - women Run

### Density Management
- **Probability**: Controls spawn likelihood of agent collections (default: 0.500)
- **Agent Settings**: Separate configuration for Male and Female agents

### Agent Customization

#### Individual Agent Editing
- **Customize Agent**: Modify specific agent instances
- **Change Clothes**: Swap agent clothing and appearance
- **Change Action**: Modify animation behaviors
- **Include All**: Apply changes to entire agent group

#### Custom Agent Creation
Users can add custom agents or collections with:
- **Object**: Agent mesh object
- **Collection**: Agent group collection
- **Agent Mesh**: 3D model reference
- **Agent Armature**: Animation skeleton
- **Gender**: Male/Female classification

### Collection Management
- **Include**: Add agents to active simulation
- **Discard**: Remove agents from consideration

## Workflow

1. **Setup**: Configure city environment (iCity or Custom)
2. **Distribution**: Scatter agents with density controls
3. **Activities**: Place activity objects or collections
4. **Agents**: Configure agent types, probabilities, and behaviors
5. **Simulation**: Run with debug tools for monitoring
6. **Optimization**: Adjust pathfinding and time scale as needed

This system creates dynamic, emergent behaviors where agents autonomously navigate urban environments to fulfill their needs, creating realistic crowd simulation and urban activity patterns.