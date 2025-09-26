# iCrowd Simulation Tool Documentation

## Overview

A comprehensive crowd simulation system designed for architectural visualization, urban planning, film production, and game development. This tool provides both static distribution and dynamic movement capabilities through integrated systems that work together seamlessly.

## System Architecture

### Static Distribution Systems

**On Ground System**
- Terrain-based scattering across surfaces
- Flexible density control with vertex group masking
- Support for individual agents and cluster formations
- Natural variation with noise and randomization

**On Curve System** 
- Path-based distributions with width control
- Curve radius scaling for dynamic density
- Automatic agent orientation along paths
- Count-based or density-based placement options

**On Vertex System**
- Precision placement on mesh vertices
- Custom patterns through vertex group selection
- Ideal for architectural layouts and exact formations
- Weight painting support for density gradients

**Stadium System**
- Organized seating and venue layouts
- Four input methods: On Face, On Instance, On Collection, On Vertex
- Grid-based control for row/column arrangements
- Rotation and transformation controls for perfect alignment

**Walkers System**
- Structured path-based crowd flows
- Lane management with count and direction control
- Personal space and density management
- Noise parameters for natural variations

**City System**
- Urban environment placements
- Activity-based behaviors (sleep, eat, work, fun)
- Infrastructure-aware distribution (roads, sidewalks)
- Collision management and time-based patterns

### Dynamic Control System

**Fluid System**
- Real-time movement simulation
- Multiple control methods: Path following, Attraction, Repulsion
- Physics-based behaviors with speed controls
- Integration with all static distribution systems

## Key Features

### Distribution Capabilities
- Multiple static systems for different scenarios
- Vertex group masking for precise control
- Density gradients and natural variations
- Support for individual agents and collections

### Movement Control
- Path following with curve-based direction
- Attraction/repulsion systems for goal-oriented behavior
- Real-time parameter adjustment
- Physics-based collision avoidance

### Performance Optimization
- Scalable from small groups to massive crowds
- Baking capabilities for complex simulations
- LOD support for real-time applications
- Efficient memory management

## Workflow Integration

### Standard Pipeline
1. **Static Placement**: Choose appropriate static system for initial distribution
2. **Density Refinement**: Adjust parameters and masking for desired layout
3. **Dynamic Activation**: Import static setup into Fluid system for movement
4. **Behavior Tuning**: Configure paths, attractors, and repellers
5. **Final Polish**: Adjust variations and performance settings

### System Combinations
- **Urban Scenes**: City system + Fluid system
- **Structured Events**: Walkers system + Stadium system  
- **Architectural Visualization**: On Vertex system + Fluid system
- **Complex Productions**: Combined use of all systems

## Getting Started

### Quick Start Guides
- Basic terrain scattering with On Ground system
- Path-based crowds with On Curve system
- Venue seating with Stadium system
- Dynamic crowds with Fluid system

### System Selection Guide
- **For natural environments**: On Ground system
- **For path-based flows**: On Curve or Walkers systems
- **For precise placements**: On Vertex system
- **For venue seating**: Stadium system
- **For urban environments**: City system
- **For dynamic movement**: Fluid system

## Documentation Structure

### System Documentation
- Detailed parameter explanations for each system
- Workflow examples and use cases
- Performance optimization guidelines
- Troubleshooting common issues

### Tutorial Section
- Step-by-step project tutorials
- Video demonstrations
- Example files and templates
- Advanced technique showcases

### FAQ & Support
- Common questions and solutions
- Technical troubleshooting
- Best practices and tips
- Community resources

## Technical Specifications

### Compatibility
- Node-based workflow integration
- Standard 3D modeling software compatibility
- Export capabilities for game engines and renderers
- Cross-platform performance optimization

### System Requirements
- Detailed hardware recommendations
- Memory and processing requirements
- GPU acceleration support
- Scalability considerations

## Support Resources

### Learning Materials
- Video tutorials for all skill levels
- Interactive example files
- Project templates and presets
- Community showcase gallery

### Community & Updates
- User forum for questions and sharing
- Regular system updates and improvements
- Feature request system
- Bug reporting and tracking

---

*This documentation covers the complete crowd simulation ecosystem. Use the navigation to explore specific systems or jump to tutorials for hands-on learning.*