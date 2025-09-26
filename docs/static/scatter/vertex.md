# iCrowds Static On Vertex Documentation

## Overview
The **Static On Vertex** system is a mesh-based distribution tool that places agents precisely on mesh vertices with controlled variation and spacing. It enables exact placement control using existing mesh topology while maintaining natural-looking variations through comprehensive randomization options.

## Core Components

### Global Inputs
**Purpose**: Define the base environment and agent sources

**Parameters**:
- **Terrain**: Reference surface for orientation and placement context
- **Agents**: Source objects or collections for vertex-based distribution
- **Agent Input Type**: Switch between Object or Collection input methods

### Vertex Distribution System
**Purpose**: Control agent placement directly on mesh vertices

#### Density Panel
**Placement Controls**:
- **Mesh**: Target mesh object whose vertices will host agents
- **Max**: Maximum number of agents to place (vertex-limited)
- *Feature: Vertex group masking for selective placement*

### Personal Space
**Purpose**: Maintain natural spacing between vertex-placed agents

**Parameters**:
- **Relax Iterations**: Physics smoothing passes for optimal vertex spacing
- **Space Min**: Minimum distance between agents on adjacent vertices
- **Space Max**: Maximum allowable spacing adjustment
- **Space Seed**: Randomization for organic spacing variation

### Position Variations
**Purpose**: Introduce controlled offsets from exact vertex positions

**Parameters**:
- **Position Variation**: Amount of positional randomness from vertex centers
- **Position Seed**: Randomization control for position variations

### Rotation Variations
**Purpose**: Control agent orientation on vertices

**Parameters**:
- **Up Direction**: Surface normal alignment for natural standing
- **Look Direction**: Forward orientation control (random or directed)

### Random
**Purpose**: Additional randomization for natural distribution

**Parameters**:
- **Random Min**: Minimum random influence
- **Random Max**: Maximum random influence
- **Random Seed**: Overall randomization control

### At Object Panel
**Purpose**: Object-specific vertex placement

**Parameters**:
- **At Object**: Target specific objects for vertex placement
- **Add Randomness**: Introduce variation to object-based placement

### Scale Variations
**Purpose**: Create size diversity among vertex-placed agents

**Parameters**:
- **Scale Variation**: Enable/disable agent size variations
- **Scale Min**: Minimum agent scale factor
- **Scale Max**: Maximum agent scale factor
- **Scale Seed**: Scale randomization control

## Key Innovation: Vertex-Based Precision with Natural Variation

### Exact Vertex Placement
**Core Feature**: Agents are placed precisely on mesh vertices while maintaining organic feel:

- **Vertex-Level Control**: Each agent corresponds to a specific vertex
- **Topology-Driven**: Distribution follows mesh edge flow and density
- **Non-Destructive**: Original mesh remains untouched

### Vertex Group Masking
**Advanced Control**: Use vertex groups to selectively enable/disable placement:

- **Density Zones**: Create high-density and sparse areas using vertex weights
- **Pattern Control**: Design specific formation patterns through vertex selection
- **Animated Masks**: Use animated vertex groups for dynamic placement changes

## Workflow

### Phase 1: Mesh Preparation
1. Create or import the target mesh with appropriate vertex density
2. Use vertex groups to define placement zones and density variations
3. Ensure mesh has sufficient vertices for desired agent count

### Phase 2: Agent and Mesh Setup
1. Select the target mesh for vertex-based distribution
2. Choose agent objects or collections
3. Set Agent Input Type (Object or Collection)

### Phase 3: Density Configuration
1. Set Max parameter to control total agent count
2. System automatically uses available vertices up to the maximum
3. Vertex group masks automatically limit placement to weighted areas

### Phase 4: Spacing and Naturalization
1. Configure Personal Space to prevent overcrowding on dense vertices
2. Adjust Position Variations for organic offsets from exact vertex positions
3. Set Rotation parameters for natural orientation

### Phase 5: Variation Controls
1. Enable Scale Variations for size diversity
2. Use Random parameters to introduce controlled chaos
3. Fine-tune randomization seeds for reproducible results

### Phase 6: Advanced Placement
1. Use At Object for specific object targeting
2. Apply additional randomness for object-based variations
3. Balance exact placement with natural-looking results

## Use Cases

### Architectural Precision
- People placed exactly on seating vertices
- Furniture on floor plan vertices
- Decorative elements on architectural features

### Event Planning
- Audience members on seating vertices
- Participants in organized formations
- Exhibits on precise layout points

### Natural Distributions
- Plants on terrain vertices following contours
- Rocks on geological feature vertices
- Animals on ecosystem analysis points

### Technical Applications
- Data visualization with agent representation
- Sensor placement simulations
- Urban planning with exact positioning

## Advanced Techniques

### Vertex Group Masking Strategies
- **Weight-Based Density**: Use vertex weights to control probability of placement
- **Pattern Creation**: Design specific formations through vertex selection
- **Animated Distributions**: Animate vertex groups for moving placement zones

### Multi-Mesh Distributions
- Combine multiple meshes for complex distributions
- Use different vertex densities for varied concentration areas
- Create hierarchical placement systems

### Hybrid Approaches
- Combine vertex placement with other distribution methods
- Use vertex system for base placement with other systems for variation
- Create layered distribution effects

## Key Features

- **Precision Placement**: Exact control through mesh vertices
- **Vertex Group Masking**: Advanced selective placement control
- **Natural Variation**: Comprehensive randomization while maintaining structure
- **Topology-Aware**: Distribution follows mesh flow and density
- **Non-Destructive**: Original mesh remains intact
- **Scalable**: Works with simple to complex meshes

## Performance Considerations

- **Vertex Count**: Performance scales with vertex quantity
- **Optimization**: Use optimized meshes with appropriate vertex density
- **LOD Strategies**: Implement level-of-detail for distant distributions

The Static On Vertex system provides the perfect balance between precision control and natural variation, allowing artists to create exact formations while maintaining organic-looking results through comprehensive variation controls and vertex group masking capabilities.