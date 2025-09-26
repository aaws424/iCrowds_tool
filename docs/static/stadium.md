# iCrowds Static Stadium Documentation

## Overview
The **Static Stadium** system is a specialized crowd distribution tool designed for structured seating arrangements and organized formations. It provides multiple input methods for precise agent placement on seating surfaces, instance objects, or predefined points, making it ideal for venues, theaters, and any scenario requiring organized crowd layouts.

## Core Components

### Inputs
**Purpose**: Define agent sources and distribution methods

**Parameters**:
- **Agents**: Source objects or collections for placement
- **Agent Input Type**: Switch between Object or Collection input methods
- **Input Type**: Primary distribution method selector

### Distribution Methods

#### On Face Distribution
**Purpose**: Place agents in organized grid patterns on surface faces

**Parameters**:
- **Face Uv Object**: Target face object with UV mapping (recommended: scaled/rotated plane)
- **Count X**: Number of agents along the X-axis (columns)
- **Count Y**: Number of agents along the Y-axis (rows)

*Best for: Custom seating layouts, flexible grid arrangements*

#### On Instance Distribution  
**Purpose**: Place agents on existing geometry nodes instances

**Parameters**:
- **Geo_Nodes Object**: Geometry nodes object with instances output
- *Perfect for: Chair instances, predefined seating arrangements*

#### On Collection Objects
**Purpose**: Distribute agents across objects in a collection

**Parameters**:
- **On Collection**: Target collection containing placement objects
- *Ideal for: Existing scene objects as placement points*

#### On Vertex Distribution
**Purpose**: Precise placement on mesh vertices with advanced controls

**Parameters**:
- **On Vertix**: Target mesh for vertex-based placement
- **Fill Factor**: Density control (0.0-1.0)
- **Weight Paint Fill**: Use vertex groups/weight painting for density variation

### Settings Panel
**Purpose**: Fine-tune agent orientation and variation

#### Rotation
**Orientation Control**:
- **Rotation Type**: Method for agent rotation alignment
- *Options: Face normal, object direction, custom vectors*

#### Random
**Variation Controls**:
- **Mix Factor**: Blend between perfect alignment and randomness
- **Rotation Min**: Minimum random rotation offset
- **Rotation Max**: Maximum random rotation offset  
- **Rotation Seed**: Randomization control for reproducible results

### At Object Panel
**Purpose**: Advanced instance transformation controls

**Parameters**:
- **At Object**: Target object for placement
- **Randomize**: Enable randomization features

#### Transformation Controls
**Instance Translation**:
- **Offset**: Position offset from base placement
- **Translation Local Space**: Use local coordinates for offsets

**Instance Rotation**:
- **Rotation Local Space**: Local coordinate rotation
- *Advanced orientation adjustments*

**Instance Scale**:
- **Scale Local Space**: Local coordinate scaling
- *Size variations within the formation*

## Workflow

### Phase 1: Input Method Selection
**Choose based on your scene setup:**

**Option A: On Face Method**
1. Create a plane and scale/rotate to fit seating area
2. Ensure proper UV mapping on the face
3. Set Count X/Y for grid dimensions

**Option B: On Instance Method**
1. Use Geometry Nodes to create chair/seat instances
2. Reference the GN object in the system
3. Agents automatically place on each instance

**Option C: On Collection Objects**
1. Gather placement objects into a collection
2. Reference the collection in the system
3. Agents distribute across all collection objects

**Option D: On Vertex Method**
1. Use mesh with vertex layout matching seating
2. Apply vertex groups/weight painting for density control
3. Adjust Fill Factor for overall density

### Phase 2: Agent Configuration
1. Select agent objects or collections
2. Choose Object or Collection input type
3. Set up agent properties and variations

### Phase 3: Placement Refinement
1. Adjust Rotation Type for proper orientation
2. Use Random settings for natural variation
3. Fine-tune Mix Factor for balance between order and randomness

### Phase 4: Advanced Transformations
1. Use At Object panel for specific placement adjustments
2. Apply offsets and local transformations
3. Adjust instance scaling for size variations

## Use Cases

### Venue Seating
- Theater audiences
- Stadium crowds
- Concert seating arrangements
- Lecture hall populations

### Event Planning
- Conference seating layouts
- Wedding ceremony arrangements
- Exhibition booth assignments
- Ceremonial formations

### Architectural Visualization
- Building occupancy simulations
- Space planning with populated areas
- Venue capacity testing

### Entertainment Production
- Film/TV crowd scenes in venues
- Game level population
- Virtual event planning

## Advanced Techniques

### Multi-Method Workflow
- Combine On Face for main seating + On Vertex for VIP sections
- Use On Instance for fixed seating + On Collection for special areas
- Layer methods for complex venue layouts

### Weight Painting for Density
- Paint high-density areas for premium seating
- Create sparse areas for aisles and walkways
- Animate weight maps for dynamic crowd changes

### Geometry Nodes Integration
- Create sophisticated instance patterns with GN
- Use attribute-based variations for realistic seating
- Combine with scatter systems for hybrid approaches

## Key Features

- **Multiple Input Methods**: Flexible placement options for any scenario
- **Precision Grid Control**: Exact row/column arrangements with On Face
- **Instance Awareness**: Perfect alignment with existing geometry
- **Vertex Group Integration**: Advanced density control through weight painting
- **Transformation Flexibility**: Local/global space controls for perfect alignment
- **Natural Variation**: Controlled randomness for organic-looking crowds

## Pro Tips

### Face Method Best Practices
- Use a single quad face for best results
- Ensure proper UV scaling to match venue proportions
- Adjust Count X/Y to match actual seating dimensions

### Instance Method Optimization
- Pre-generate chair instances with Geometry Nodes
- Use instances with consistent orientation for uniform results
- Combine with vertex groups for section-based variations

### Vertex Method Advanced Use
- Create vertex groups for different ticket sections
- Use weight painting for gradual density transitions
- Animate vertex weights for crowd movement simulations

The Static Stadium system provides venue-specific crowd distribution with architectural precision, offering multiple workflow options to match any seating arrangement scenario from simple theaters to complex stadium layouts.