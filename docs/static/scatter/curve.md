# iCrowds Static On Curve Documentation

## Overview
The **Static On Curve** system is a specialized tool for distributing agents along curves with intelligent density control based on curve radius. It enables artists to create natural-looking formations that follow paths, roads, or custom trajectories with radius-driven population density.

## Core Components

### Global Inputs
**Purpose**: Define the base environment and agent sources

**Parameters**:
- **Terrain**: Reference surface for agent placement
- **Agents**: Source objects or collections for distribution
- **Agent Input Type**: Switch between Object or Collection input methods

### Curve Distribution System
**Purpose**: Control agent placement along curves with radius-based density

#### Density Panel
**Placement Methods**:
- **Curve**: Target curve object for agent distribution
- **Density Type**: Method for calculating agent placement
- **Max**: Maximum number of agents along the curve

#### Count-Based Distribution
**Fixed Quantity Control**:
- **Count Min**: Minimum number of agents to place
- **Count Max**: Maximum number of agents to place

#### Length-Based Distribution
**Density-per-Length Control**:
- **Length**: Agents per unit length of the curve

#### Radius Multiplier Panel
**Curve Radius Integration**:
- **Radius Multiplier**: Scale factor for curve radius influence on density
- *Feature: Use Alt+S curve point scaling to drive agent density variations*

### Personal Space
**Purpose**: Maintain natural spacing between agents along the curve

**Parameters**:
- **Relax Iterations**: Physics smoothing passes for optimal spacing
- **Space Min**: Minimum distance between adjacent agents
- **Space Max**: Maximum allowable spacing
- **Space Seed**: Randomization for organic spacing variation

### Rotation
**Purpose**: Control agent orientation along the curve path

**Parameters**:
- **Up Direction**: Surface normal alignment for agents
- **Look Direction**: Forward orientation (typically follows curve direction)

### Random
**Purpose**: Introduce controlled variation for natural results

**Parameters**:
- **Random Min**: Minimum random placement offset
- **Random Max**: Maximum random placement offset  
- **Random Seed**: Randomization control for reproducible results

### At Object Panel
**Purpose**: Object-based placement along curves

**Parameters**:
- **At Object**: Specific object targets for placement
- **Add Randomness**: Introduce variation to object-based placement

### Position Variation
**Purpose**: Fine-tune agent positioning relative to the curve

**Parameters**:
- **Position Variation**: Amount of positional randomness
- **Position Seed**: Randomization control for position variations

### Scale Variations
**Purpose**: Create size diversity among agents

**Parameters**:
- **Scale Variation**: Enable/disable agent size variations

## Key Innovation: Radius-Driven Density

### Curve Radius Control
**Unique Feature**: The system uses the curve's radius (adjusted with **Alt+S**) to dynamically control agent density:

- **Wider Radius Areas**: Higher agent density and more spacing flexibility
- **Narrower Radius Areas**: Lower agent density with tighter constraints
- **Variable Radius Curves**: Create natural density gradients along paths

### Radius Multiplier Application
- **Multiplier > 1.0**: Amplify the radius's effect on density
- **Multiplier < 1.0**: Reduce the radius's influence
- **Multiplier = 0.0**: Disable radius-based density control

## Workflow

### Phase 1: Curve Preparation
1. Create or import the target curve object
2. Use **Alt+S** to scale curve points' radius for density control
3. Adjust radius variations to define density hotspots and sparse areas

### Phase 2: Agent and Curve Setup
1. Select the target curve for distribution
2. Choose agent objects or collections
3. Set Agent Input Type (Object or Collection)

### Phase 3: Distribution Method Selection
**Option A: Count-Based Placement**
1. Set Count Min/Max for fixed agent quantities
2. System automatically distributes along curve length

**Option B: Density-Based Placement**  
1. Set Length parameter for agents per unit distance
2. Density automatically adapts to curve radius variations

### Phase 4: Radius Integration
1. Adjust Radius Multiplier to control radius influence
2. Fine-tune how curve point scaling affects density
3. Balance between radius-driven and uniform distribution

### Phase 5: Spacing and Variation
1. Configure Personal Space for natural agent separation
2. Set Rotation parameters for proper orientation
3. Add Random and Position variations for organic look
4. Enable Scale Variations for size diversity

### Phase 6: Refinement
1. Use At Object for specific placement requirements
2. Adjust randomization seeds for controlled variation
3. Fine-tune Max parameter to limit total agents

## Use Cases

### Road and Path Populations
- pedestrians along sidewalks
- vehicles on roads
- street furniture along pathways

### Event and Ceremony Layouts
- audience seating along procession routes
- participants in parade formations
- vendors along festival paths

### Natural Formations
- trees along riverbanks
- rocks along geological faults
- plants following terrain contours

### Architectural Applications
- people in queue lines
- furniture along building perimeters
- decorative elements along architectural features

## Advanced Techniques

### Dynamic Density Gradients
- Use gradually changing radius to create smooth density transitions
- Create crowded-to-sparse effects along paths
- Simulate natural gathering and dispersion patterns

### Multi-Curve Networks
- Distribute across multiple curves for complex layouts
- Use different radius settings for varied density zones
- Create hierarchical distribution patterns

### Animation Preparation
- Set up static formations for later fluid system integration
- Pre-define natural starting positions for dynamic simulations
- Create baseline distributions for motion systems

## Key Features

- **Radius-Driven Density**: Unique curve radius control over agent distribution
- **Dual Distribution Methods**: Choose between count-based or density-based placement
- **Adaptive Spacing**: Automatic adjustment based on curve characteristics
- **Non-Linear Control**: Curve point radius scaling for localized density effects
- **Natural Orientation**: Automatic rotation following curve direction
- **Artist-Friendly**: Visual curve editing with immediate density feedback

The Static On Curve system provides intuitive control over path-based agent distribution, leveraging Blender's native curve editing tools to create natural, radius-driven population densities that adapt intelligently to path width variations.