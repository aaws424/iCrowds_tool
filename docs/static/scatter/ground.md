# On Ground iCrowd System - User Documentation
## Overview
The On Ground System creates natural-looking static crowds scattered across terrain, perfect for park scenes, outdoor events, queues, and social gatherings with both individual agents and social groups.

## Distribution Tab

### Basic Setup
- **View Mode**: Render - Standard visualization
- **Terrain**: On Ground Terrain - Input terrain collection for agent placement

### Distribution Types

#### 1. Singles
**Individual scattered agents**
- **Density**: 0.200 - Overall density of individual agents
- **Min Distance**: 1m - Minimum spacing between single agents
- **Seed**: 1 - Randomization pattern
- **Max Agents**: 100,000.000 - Maximum number limit

#### 2. Clusters
**Social groups and clusters**
- **Density**: 0.060 - Density of cluster centers
- **Min Distance**: 6.39m - Spacing between different clusters
- **Seed**: 0 - Randomization pattern
- **Max Clusters**: 100,000.000 - Maximum cluster count

### Distribution Controls

#### Weight Painting
- **Brush Tool**: Paint density variations directly on terrain
- **Vertex Group Mask**: Use predefined vertex groups for density control
- **Application**: Create natural density variations like pathways vs open areas

#### Sphere Mask
- **Sphere Object**: Use sphere objects to define inclusion/exclusion zones
- **Edit**: Modify sphere position and radius for precise area control

### Personal Space System
- **Relax Iterations**: 12 - Processing passes for collision resolution
- **Min Distance**: 0.500m - Minimum personal space between agents
- **Max Distance**: 1.000m - Maximum personal space buffer
- **Seed**: 0 - Randomization for personal space variation

### Cluster Variations

#### Radius Settings
- **Min Radius**: 0.000m - Smallest cluster size
- **Max Radius**: 1.000m - Largest cluster size
- **Seed**: 6 - Randomization pattern
- **Relax Iterations**: 1.329 - Cluster formation quality
- **Noise**: 1.000 - Natural variation in cluster shapes

#### Population Settings
- **Min Count**: 5 - Minimum agents per cluster
- **Max Count**: 12 - Maximum agents per cluster
- **Seed**: 0 - Randomization for cluster sizes

#### Placement Settings
- **Offset**: Random positioning variation within clusters
- **Creates**: More organic, natural-looking group formations

## Settings Tab

### Orientation Control

#### Rotation Modes
1. **Default**
   - Consistent facing direction across all agents
   - Uniform crowd appearance

2. **Randomize**
   - Random rotation per agent
   - Natural-looking varied crowd
   - **Control**: Adjust randomization intensity

3. **At Object**
   - All agents face toward target object
   - **Optional**: Add randomization for natural variation
   - **Use**: Crowds facing a stage, speaker, or point of interest

### Scale Variations
- **Size Randomization**: Control agent size variations
- **Natural Variation**: Avoid uniform, artificial appearance
- **Scale Range**: Adjust minimum and maximum size parameters

## Agent Configuration

### Input Requirements
- **Animated Agents**: Collections with idle animations
- **Multiple Collections**: Support for varied agent types
- **Probability Control**: Balance between different agent collections

### Customization
- **Custom Collections**: Import additional agent types
- **Clothing Variations**: Modify agent appearances within collections
- **Collection Blending**: Mix different agent types naturally

## Typical Workflow

1. **Terrain Setup**
   - Prepare ground terrain collection
   - Define areas using weight painting or sphere masks

2. **Singles Distribution**
   - Set density for individual agents
   - Adjust personal space for natural spacing
   - Use weight painting for area-specific density

3. **Clusters Setup**
   - Configure cluster density and spacing
   - Set cluster size variations (radius and population)
   - Adjust cluster formation parameters

4. **Orientation & Scale**
   - Choose rotation mode based on scene needs
   - Set scale variations for natural appearance
   - Fine-tune facing directions

5. **Agent Assignment**
   - Select agent collections
   - Balance probabilities between collections
   - Add custom agents if needed

## Best Practices

### For Realistic Results
- Use **Singles** for background crowds and individuals
- Use **Clusters** for social groups and gatherings
- Combine both types for most natural scenes
- Use **weight painting** to follow terrain features and paths
- Apply **personal space** to prevent agent overlapping

### Performance Optimization
- Start with lower densities and increase gradually
- Use appropriate relax iterations (higher = better quality but slower)
- Balance cluster counts with scene complexity
- Use sphere masks to limit calculations to visible areas

### Natural Appearance Tips
- Use random rotation with moderate variation
- Apply scale variations for diverse crowd
- Mix cluster sizes for organic social groups
- Use noise and offset for irregular cluster shapes

## Use Cases

- **Park scenes** with people sitting and standing
- **Outdoor events** like concerts or festivals
- **Queue simulations** for attractions or services
- **Public squares** and gathering places
- **Beach scenes** with scattered groups
- **Marketplaces** and social spaces

The On Ground System creates the most organic and natural-looking static crowds, ideal for environments where people gather informally and social dynamics are important.