# Walkers System Documentation

## Overview

The Walkers System is a specialized crowd simulation tool designed for controlled pedestrian movement along predefined paths. This system creates organized lane-based traffic flow with configurable agent behavior and path following.

## Distribution

### Viewer
- **Render**: Standard visualization mode for agent display

### Terrain Configuration
- **Collection**: Terrain setup consistent with other systems in the suite

### Distribution Setup

#### Path Definition
- **Distribution Object**: Input a collection of curves that define walking paths
- **Walkers Curve**: Curves act as the central guide for lane generation
- **Edit**: Modify curve properties and placement

#### Density Control
- **Density**: 1.000 - Controls the number of people distributed across lanes
- **Randomness**: 1.000 - Randomizes walker distribution along the lanes
- **Seed**: 0 - Randomization seed for consistent patterns

#### Collision Avoidance
- **Personal Space**: Individual buffer zone for each agent
- **Min**: 0.000 - Minimum personal space distance
- **Max**: 1.000 - Maximum personal space distance
- **Seed**: 0 - Randomization seed for personal space variation

**Note**: Personal space system activates when System Type is set to Physics (not Animation)

## Settings

### Agent Lifecycle
- **Loop Type**: Controls agent behavior at path endpoints
  - **Respawn**: Agents reappear at the start when reaching the end
  - **Delete**: Agents are removed from simulation when reaching the end

### System Configuration
- **System Type**: 
  - **Animation**: Uses animated movement (default)
  - **Physics**: Enables physical interactions and collision avoidance

### Lane Management

#### Lane Generation
- **Count**: 4 - Number of lane instances generated left and right of input curves
- **Direction**: 0.632 - Controls lane direction variation
  - Values > 0.5 create opposing traffic flows
  - Some agents move forward, others move in reverse direction

#### Movement Variation
- **Noise**: Adds natural variation to agent movement
  - **Power**: 1.000 - Strength of noise influence
  - **Offset**: 0.000 - Base offset for noise pattern
  - **Scale**: 0.100 - Size of noise pattern effect

#### Speed Control
- **Speed**: 1.000 - Controls the movement speed of all agents

## Agents Configuration

### Agent Collections
- **Single Collection Input**: Unlike other systems, accepts only one collection type
- **Animated Walking Meshes**: Collection must contain pre-animated walking animation meshes
- **No Gender Separation**: All agents use the same animation collection

### Simplified Agent Management
- No individual agent customization (clothes, actions)
- No probability settings for different agent types
- Focus on uniform crowd behavior rather than individual variation

## Workflow

1. **Path Creation**:
   - Create and position guide curves for desired walking paths
   - Organize curves into a collection for system input

2. **Distribution Setup**:
   - Set lane count for path width
   - Adjust density for crowd size
   - Configure personal space for collision avoidance

3. **Behavior Configuration**:
   - Choose loop type (respawn or delete)
   - Set system type (animation or physics)
   - Adjust direction for traffic flow patterns

4. **Movement Tuning**:
   - Set base movement speed
   - Add noise for natural movement variation
   - Fine-tune lane directions for realistic traffic patterns

## Key Features

- **Lane-Based System**: Automatically generates multiple lanes from single curves
- **Bidirectional Traffic**: Direction parameter creates natural opposing flows
- **Consistent Animation**: All agents use the same walking animation collection
- **Controlled Density**: Precise control over agent distribution along paths
- **Collision Awareness**: Personal space system prevents agent overlap

## Use Cases

- Sidewalk and pedestrian walkway simulations
- Museum or exhibition visitor flow
- Emergency egress and crowd movement studies
- Architectural planning for public spaces
- Traffic flow analysis for urban planning

This Walkers System provides a streamlined approach for creating organized pedestrian movement patterns with minimal setup complexity, ideal for architectural visualization and urban planning applications where controlled crowd flow is essential.