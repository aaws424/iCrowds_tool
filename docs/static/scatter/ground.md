# iCrowds Static On Ground Documentation

## Overview
The **Static On Ground** system is a comprehensive terrain-based crowd distribution tool that scatters agents across surfaces with precise control over placement, density, and grouping. It supports both individual agent placement and clustered groupings for natural-looking crowd formations.

## Core Components

### Global Inputs
**Purpose**: Define the base environment and agent sources

**Parameters**:
- **Terrain**: Base surface for agent placement
- **Agents**: Source objects or collections for scattering
- **Agent Input Type**: Switch between Object or Collection input methods

### Singles Distribution System
**Purpose**: Place individual agents with controlled spacing and variation

#### Density_Singles Panel
**Placement Controls**:
- **Density_Singles**: Overall agent concentration level
- **Min_Distance_Singles**: Minimum spacing between individual agents
- **Seed_Singles**: Randomization seed for placement variation
- **max_Singles**: Maximum number of agents to place

#### Masks_Singles
**Placement Restrictions**:
- **Vertex Group Mask_Singles**: Use vertex groups to define density areas
- **Inside Sphere Mask_Singles**: Spherical boundary constraints

#### Personal Space_Singles
**Natural Spacing**:
- **Relax Iterations_Singles**: Physics passes for optimal spacing
- **Space Min_Singles**: Minimum personal space between agents
- **Space Max_Singles**: Maximum personal space allowance
- **Space Seed_Singles**: Randomization for natural spacing variation

#### Rotation_Singles
**Orientation Control**:
- **Up Direction_Singles**: Surface normal alignment
- **Look Direction_Singles**: Forward orientation direction

#### Random_Singles
**Placement Variation**:
- **Random Min_Singles**: Minimum random offset
- **Random Max_Singles**: Maximum random offset
- **Random Seed_Singles**: Randomization control

#### At Object_Singles Panel
**Object-Based Placement**:
- **At Object_Singles**: Target objects for placement
- **Add Randomness_Singles**: Introduce variation to object-based placement

#### Scale Variations_Singles
**Size Diversity**:
- **Scale Variation_Singles**: Enable/disable size variations
- **Scale Min_Singles**: Minimum agent scale
- **Scale Max_Singles**: Maximum agent scale
- **Scale Seed_Singles**: Scale randomization control

### Clusters Distribution System
**Purpose**: Create natural group formations with clustered agent placement

#### Density_Clusters Panel
**Cluster Density**:
- **Density_Clusters**: Overall cluster concentration
- **Min Distance_Clusters**: Spacing between cluster centers
- **Seed_Clusters**: Cluster placement randomization
- **max_Clusters**: Maximum number of clusters

#### Mask_Clusters
**Cluster Placement Restrictions**:
- **Vertex Group Mask_Clusters**: Density control via vertex groups
- **Inside Sphere Mask_Clusters**: Spherical boundary for clusters

#### Cluster Variations_Clusters
**Group Configuration**:
- **Radius_Clusters**: Overall cluster size control
- **Radius Min_Clusters**: Minimum cluster radius
- **Radius Max_Clusters**: Maximum cluster radius
- **Radius Seed_Clusters**: Cluster size randomization
- **Count_Clusters**: Agents per cluster
- **Count Min_Clusters**: Minimum agents per cluster
- **Count Max_Clusters**: Maximum agents per cluster
- **Count Seed_Clusters**: Agent count randomization

#### Offset_Clusters Panel
**Placement Refinement**:
- **Offset_Clusters**: Enable cluster position offsets
- **Detail_Clusters**: Offset refinement level
- **Random Offset_Clusters**: Random position variation
- **Offset Min_Clusters**: Minimum offset distance
- **Offset Max_Clusters**: Maximum offset distance
- **Offset Seed_Clusters**: Offset randomization

#### Personal Space_Clusters
**Intra-Cluster Spacing**:
- **Relax Iterations_Clusters**: Physics smoothing within clusters
- **Space Min_Clusters**: Minimum spacing between cluster members
- **Space Max_Clusters**: Maximum spacing allowance
- **Space Seed_Clusters**: Spacing variation control

#### Rotation_Clusters
**Cluster Orientation**:
- **Up Direction_Clusters**: Surface alignment for clusters
- **Look Direction_Clusters**: Cluster facing direction

#### Random_Clusters
**Cluster Variation**:
- **Random Min_Clusters**: Minimum cluster variation
- **Random Max_Clusters**: Maximum variation range
- **Random Seed_Clusters**: Cluster randomization control

## Workflow

### Phase 1: Terrain and Agent Setup
1. Define the base terrain surface for placement
2. Select agent objects or collections for scattering
3. Choose between Object or Collection input method

### Phase 2: Distribution Method Selection
**Option A: Singles Distribution**
1. Configure density and minimum spacing parameters
2. Set up masking for controlled placement areas
3. Adjust personal space for natural agent spacing
4. Configure rotation and scale variations

**Option B: Clusters Distribution**
1. Set cluster density and spacing between groups
2. Define cluster size parameters (radius and agent count)
3. Configure intra-cluster spacing and organization
4. Apply offsets and variations for natural group formations

### Phase 3: Masking and Refinement
1. Use vertex groups to control density distribution
2. Apply spherical masks for boundary control
3. Fine-tune placement with offset and detail parameters
4. Adjust randomization seeds for controlled variation

### Phase 4: Final Adjustments
1. Review and tweak scale variations
2. Optimize personal space parameters
3. Finalize rotation and orientation settings
4. Balance randomness for natural-looking results

## Use Cases

### Natural Environments
- Scattering vegetation and natural elements
- Wildlife placement in ecosystems
- Rock and debris distribution on terrain

### Urban Planning
- Pedestrian placement in public spaces
- Street furniture and object distribution
- Park and recreational area population

### Event Scenarios
- Audience seating arrangements
- Exhibition booth placement
- Festival attendee distribution

### Architectural Visualization
- People in building environments
- Furniture and object placement in interiors
- Context population around structures

## Key Features

- **Dual Distribution Methods**: Choose between individual or clustered placement
- **Precise Density Control**: Vertex group masking for area-specific density
- **Natural Spacing Algorithms**: Physics-based personal space optimization
- **Comprehensive Randomization**: Controlled variation for organic results
- **Scalable Workflow**: Handle from small scenes to massive distributions
- **Non-Destructive Workflow**: Parameters can be adjusted iteratively

The Static On Ground system provides artist-friendly controls for creating believable, naturally distributed crowds and objects across any terrain surface, with advanced options for both individual placement and group formations.