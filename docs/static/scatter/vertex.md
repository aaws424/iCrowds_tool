# On Vertex iCrowd System - User Documentation
## Overview
The On Vertex System precisely places agents on mesh vertices, providing exact control over agent positioning for structured arrangements and specific placement requirements.

## Distribution Tab

### Basic Setup
- **View Mode**: Render - Standard visualization mode
- **Terrain**: On Curve Terrain - Ground surface for agent alignment

### Vertex Distribution
- **Mesh Object**: Input the object containing vertices for agent placement
- **Distribution**: One agent per vertex (On vertex distribution)
- **Max Agents Num**: 100,000.000 - Total maximum agents in system

### Positioning Controls

#### Personal Space
- **Relax Iterations**: 12 - Processing passes for collision resolution
- **Min Distance**: 0.500 m - Minimum space between agents
- **Max Distance**: 1.000 m - Maximum personal buffer
- **Seed**: 0 - Randomization pattern

#### Position Variation
- **Position Variation**: 0.000 - Random offset from exact vertex positions
- **Seed**: 0 - Randomization pattern
- **Usage**: Add imperfection to avoid overly perfect grid patterns

## Settings Tab

### Orientation Control

#### Rotation Modes
1. **Default**
   - Consistent facing direction for all agents
   - Uniform appearance across vertex points

2. **Random**
   - Random rotation per agent
   - Creates natural variation in facing directions

3. **At Object**
   - All agents face toward a target object
   - Useful for crowds facing a stage or point of interest

#### Up Direction
- **Default**: Automatic alignment with terrain normals
- **Function**: Ensures agents stand properly on ground surface
- **Adjustment**: Can be modified for special orientation needs

### Scale Variation
- **Min Scale**: 0.900 - Smallest agent size (90% of normal)
- **Max Scale**: 1.000 - Largest agent size (100% of normal)
- **Seed**: 0 - Randomization pattern for size variation
- **Effect**: Creates natural size diversity in the crowd

## Agent Configuration

### Input Requirements
- **Animated Agents**: Collections with idle animations
- **Multiple Collections**: Support for varied agent types
- **Probability Control**: Balance between different agent collections

### Customization
- **Custom Collections**: Import additional agent types
- **Clothing Variations**: Modify agent appearances
- **Collection Blending**: Mix different agent types naturally

## Mesh Preparation Guide

### Optimal Vertex Setup
1. **Even Distribution**: Vertices should be evenly spaced for consistent agent placement
2. **Density Control**: More vertices = more agents in that area
3. **Mesh Types**: Works with any mesh object containing vertices
4. **Vertex Groups**: Use vertex groups for selective agent placement

### Creating Vertex Patterns
- **Grid Meshes**: For organized, grid-like formations
- **Scattered Points**: For random but controlled placement
- **Custom Shapes**: Arrange vertices in specific patterns or logos

## Typical Workflow

1. **Mesh Preparation**
   - Create or select mesh with desired vertex arrangement
   - Ensure vertex density matches required agent density
   - Use vertex groups for area-specific control

2. **Distribution Setup**
   - Input mesh object into distribution panel
   - Set maximum agent count if needed
   - Adjust position variation for natural imperfection

3. **Spacing Configuration**
   - Set personal space parameters
   - Adjust relax iterations for collision quality
   - Fine-tune min/max distances

4. **Orientation & Scale**
   - Choose rotation mode based on scene requirements
   - Set scale variation for natural size diversity
   - Configure up direction for proper ground alignment

5. **Agent Assignment**
   - Select agent collections
   - Balance probabilities between collections
   - Apply customizations as needed

## Best Practices

### For Precise Placement
- Use **position variation 0.000** for exact vertex alignment
- Create custom vertex layouts for specific formations
- Use **relax iterations** to prevent agent overlapping
- Combine with **vertex groups** for complex placement patterns

### Mesh Optimization
- Use appropriate vertex density for required agent count
- Avoid overly dense meshes unless high agent count is needed
- Use simple meshes for large-scale simulations
- Test different mesh types for various formation needs

### Natural Appearance Tips
- Use **random rotation** with vertex-based placement
- Apply **scale variation** to avoid uniform look
- Use slight **position variation** to break perfect patterns
- Mix agent collections for visual diversity

## Use Cases

- **Stadium Seating**: Precise seat-by-seat placement
- **Military Formations**: Exact positional arrangements
- **Theater Audiences**: Controlled seating patterns
- **Ceremonial Events**: Structured participant placement
- **Architectural Visualization**: Precise population of spaces
- **Logo Formations**: Spelling out words or shapes with agents
- **Grid Patterns**: Organized displays and exhibitions

The On Vertex System provides the most precise control over agent positioning, making it ideal for scenarios requiring exact placement, structured formations, or specific spatial arrangements where vertex-level accuracy is essential.