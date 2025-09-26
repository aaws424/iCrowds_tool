# Fluid iCrowd Simulation System - User Documentation
## Overview
The **Fluid System** is a dynamic crowd simulation tool that transforms static crowd distributions into living, moving populations. It takes pre-made density layouts from other systems and brings them to life with realistic movement behaviors.

## Core Components

### Input Module
**Purpose**: Import and process static crowd distributions

**Parameters**:
- **Density Source**
  - Terrain: Base surface for crowd placement
  - Distribution Type: Method of agent distribution
  - Crowds Objects: Reference objects for density calculation
  - Input Density object/objects: Pre-configured density setups

- **Distribution Controls**
  - Distance Min: Minimum spacing between agents
  - Density Max: Maximum agent concentration
  - Seed: Randomization seed for variation
  - Mask Vertex Group: Vertex-based placement restrictions

- **Animation Setup**
  - Agent animation configurations and behaviors

### Motion Engine
**Purpose**: Control agent movement characteristics and physics

**Settings**:
- **Walk Speed**: Normal movement velocity (m/s)
- **Run Speed**: Fast movement velocity (m/s) 
- **Max Speed**: Velocity cap for all movements (m/s)
- **Relax Iterations**: Physics smoothing passes for natural movement

### Movement Control Systems
**Purpose**: Direct agent flow and behavior patterns

#### Path-Based Movement
- **Flow Curve**: Single guiding path for agent direction
- **Flow Curves**: Multiple path networks for complex routing
- *Behavior: Agents follow curve direction and flow*

#### Attraction System
- **Attract**: Enable/disable attraction behavior
- **Attracters**: Target objects that pull agents toward them
- *Behavior: Agents naturally move toward attractive points*

#### Repulsion System  
- **Repel**: Enable/disable repulsion behavior
- **Repelers**: Objects that agents avoid
- *Behavior: Agents maintain distance from repulsive elements*

## Workflow

### Phase 1: Distribution Setup
1. Create static crowd layout using Walkers or City systems
2. Export density configuration and agent placements

### Phase 2: Fluid System Integration  
1. Import static distribution into Fluid system
2. Configure density parameters and terrain matching
3. Set up animation behaviors for agents

### Phase 3: Movement Control
1. **Path-based Flow**: Add curves to guide agent direction
2. **Attraction Points**: Place objects to pull agents toward goals
3. **Repulsion Zones**: Set up barriers and avoidance areas
4. **Motion Tuning**: Adjust speeds and physics for realism

### Phase 4: Simulation
1. Activate real-time movement simulation
2. Monitor agent interactions and flow patterns
3. Adjust parameters dynamically during runtime

## Use Cases

### Urban Scenarios
- Pedestrian flows through city streets
- Crowd movement in public squares
- Emergency evacuation simulations

### Entertainment Applications
- Animated crowds in films/games
- Event planning and crowd management
- Architectural visualization with living populations

### Technical Applications
- Traffic flow analysis
- Space utilization studies
- Behavioral pattern research

## Key Features

- **Real-time Control**: Adjust parameters while simulation runs
- **Multi-method Movement**: Combine paths, attraction, and repulsion
- **Physics-based**: Natural collision avoidance and flow dynamics
- **Scalable**: Handle from small groups to massive crowds
- **Interoperable**: Works with various static distribution systems

