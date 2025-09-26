# iCrowds Static Scatter Systems Overview

## Quick Reference Guide

### 🏞️ **Static On Ground**
**Best for**: Terrain-based distributions, natural environments, large-scale scattering

**Core Function**: Scatter agents across surfaces with controlled density and grouping options

**Key Features**:
- **Dual Distribution**: Choose between individual agents or clustered groups
- **Advanced Masking**: Vertex groups and spherical masks for precise placement control
- **Natural Spacing**: Physics-based personal space algorithms
- **Scale Variations**: Size diversity for organic results

**Ideal Use Cases**:
- Populating landscapes with vegetation/rocks
- Crowds in open spaces (parks, plazas)
- Large-scale environment population
- Urban street scenes with pedestrians
- Natural ecosystem simulations

---

### 🛣️ **Static On Curve** 
**Best for**: Path-based distributions, linear formations, radius-controlled density

**Core Function**: Distribute agents along curves with intelligent radius-driven density

**Key Features**:
- **Radius-Driven Density**: Use Alt+S curve scaling to control agent concentration
- **Adaptive Spacing**: Automatic adjustment based on curve width variations
- **Path Following**: Natural orientation along curve direction
- **Dual Methods**: Count-based or density-per-length placement

**Ideal Use Cases**:
- Pedestrians along sidewalks/paths
- Vehicles on roads
- Queue lines and procession formations
- Street vendors along market paths
- Parade participants along routes

---

### 📍 **Static On Vertex**
**Best for**: Precision placement, architectural layouts, exact positioning

**Core Function**: Place agents exactly on mesh vertices with controlled variation

**Key Features**:
- **Vertex-Level Precision**: Each agent placed on specific mesh vertices
- **Vertex Group Masking**: Exact control over placement patterns
- **Topology-Aware**: Distribution follows mesh edge flow
- **Structured Variation**: Natural randomness while maintaining layout

**Ideal Use Cases**:
- **Audience seating in theaters/venues**
- Furniture placement in architectural plans
- Organized formations and precise layouts
- Data visualization with exact positioning
- Exhibition booth arrangements
- Classroom or conference seating

---

## System Selection Matrix

| Scenario | Recommended System | Why |
|----------|-------------------|-----|
| **Natural landscapes** | 🏞️ On Ground | Best for organic, terrain-following distributions |
| **Paths and roads** | 🛣️ On Curve | Perfect for linear distributions with width variations |
| **Architectural precision** | 📍 On Vertex | Exact placement on predefined points |
| **Large crowds** | 🏞️ On Ground | Handles massive distributions efficiently |
| **Queue lines** | 🛣️ On Curve | Natural flow along curves |
| **Theater/venue seating** | 📍 On Vertex | Precise seat-by-seat placement |
| **Random scattering** | 🏞️ On Ground | Advanced randomization options |
| **Patterned layouts** | 📍 On Vertex | Vertex groups for exact patterns |
| **Variable density areas** | 🛣️ On Curve | Radius control for density gradients |
| **Urban planning** | 🏞️ On Ground + 🛣️ On Curve | Combine for complex city scenes |

---

## Workflow Recommendations

### **Start with On Ground when**:
- You need quick, large-scale population
- Working with natural terrains
- Don't need precise positioning
- Want maximum flexibility

### **Choose On Curve when**:
- Distribution follows paths or roads
- You need width-based density control
- Creating linear formations
- Working with existing curve networks

### **Use On Vertex when**:
- Precision placement is critical
- You have predefined layout points
- Working with architectural plans
- Need exact pattern control

---

## Pro Tips

### **Combine Systems**:
- Use **On Vertex** for key positions + **On Ground** for fill population
- **On Curve** for main paths + **On Ground** for surrounding areas
- Layer systems for complex, realistic distributions

### **Performance Considerations**:
- **On Ground**: Best for large-scale, performance-heavy scenes
- **On Curve**: Efficient for linear distributions
- **On Vertex**: Most precise but vertex-count dependent

### **Transition to Animation**:
All static systems prepare perfect starting positions for the **Fluid System** dynamic animation!

**Choose your scatter system based on placement precision needs and the natural flow of your scene!**