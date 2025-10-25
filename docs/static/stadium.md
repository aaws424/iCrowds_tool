# Stadium iCrowd System - User Documentation

## Overview
The Stadium System creates organized, static crowds for structured environments like stadiums, theaters, and auditoriums.

## Distribution Tab

### Distribution Types

#### 1. On Face
- **Requires**: A face with UV mapping (recmmend adding a plane and miving it around)
- **Function**: Distributes agents across a surface
- **Controls**:
  - **Count X**: Number of agents horizontally
  - **Count Y**: Number of agents vertically
- **Best for**: Large seating areas and bleachers

#### 2. On Instance
- **Function**: Places one agent on each instanced object
- **Example**: Geometry nodes stadium with instanced chairs
- **Use case**: Pre-arranged seating layouts

#### 3. On Collection Objects
- **Function**: Places agents on each object in a collection
- **Input**: Collection of seats or chairs
- **Use case**: Organized seating sections

#### 4. On Vertex
- **Function**: Places agents on mesh vertices
- **Setup**: Subdivide face to create vertex points
- **Use case**: Precise positioning control

### Distribution Controls

#### Fill Settings
- **Factor**: 1.000 - Controls fill density (0.000 to 1.000)
- **Seed**: 0 - Randomization seed for fill pattern

#### Weight Paint
- **Brush Tool**: Paint custom density patterns
- **Vertex Group Mask**: Use vertex weights for density control
- **Application**: Create uneven crowd distribution

#### Translation
- **Mode**: Local or Global transform space
- **X, Y, Z**: 0m - Fine-tune agent positioning
- **Use**: Adjust agent placement offsets

## Settings Tab

### Orientation & Scale

#### Default Behavior
- **Rotation**: Agents face -Y direction by default
- **Adjustment**: Modify X, Y, Z rotation angles (default: 0°)
- **Scale**: Control agent size (X:1.000, Y:1.000, Z:1.000)

#### Rotation Types

1. **Default**
   - Fixed rotation as specified
   - Consistent facing direction

2. **Randomize**
   - Random rotation per agent
   - **Control**: Adjust randomization range
   - **Use**: Natural-looking varied crowd

3. **At Object**
   - All agents face toward target object
   - **Optional**: Add randomization to object-facing
   - **Use**: Audience facing stage/screen

## Agent Configuration

### Input Collections
- **Animated Agents**: Collections with idle animations
- **Multiple Collections**: Support for varied agent types

### Probability Control
- **Method 1**: Slider-based probability per collection
- **Method 2**: Attribute-based assignment
  - **Face Attributes**: Control by UV face data
  - **Instance Attributes**: Control by instance properties
- **Example**: Different agent types for different seating sections

### Customization
- **Custom Collections**: Import additional agent types
- **Clothing Changes**: Modify agent appearances
- **Collection Probability**: Balance appearance rates

## Typical Workflow

1. **Setup Distribution**
   - Choose distribution type based on seating layout
   - Set fill factor for crowd density
   - Use weight paint for selective density

2. **Configure Orientation**
   - Set default rotation or choose random/object-facing
   - Adjust scale if needed

3. **Assign Agents**
   - Select agent collections
   - Set probabilities via slider or attributes
   - Add custom agents if required

4. **Fine-tune**
   - Adjust translations for precise positioning
   - Tune rotation randomization
   - Balance collection probabilities

## Best Practices

- Use **On Collection Objects** for pre-built stadium seats
- Use **On Face** with weight paint for organic crowd patterns
- Combine **At Object** rotation with slight randomization for natural audiences
- Use face/instance attributes for section-based crowd variety
- Start with lower fill factors and increase as needed

## Use Cases

- Sports stadium crowds
- Theater and cinema audiences
- Conference and event seating
- Concert venues
- Graduation ceremonies