# iCrowds Static Systems - Complete Overview

## Static Systems Introduction

iCrowds provides four specialized static crowd systems for different placement scenarios. Unlike dynamic systems where agents move autonomously, static systems position agents in fixed arrangements perfect for backgrounds, audiences, and structured crowds.

## System Comparison Table

| System | Placement Method | Best For | Key Features |
|--------|------------------|----------|--------------|
| **Stadium** | Face/Instance/Collection/Vertex | Structured seating | Multiple distribution types, section control |
| **On Ground** | Terrain scattering | Natural outdoor crowds | Singles + Clusters, weight painting |
| **On Curve** | Curve following | Lines & queues | Radius/count/distance control |
| **On Vertex** | Vertex-based | Precise formations | Exact positioning, grid patterns |

---

## 1. Stadium System

### Purpose
Organized seating arrangements for venues and structured environments

### Distribution Methods
- **On Face**: UV-based distribution on surfaces with X/Y count control
- **On Instance**: One agent per instanced object (chairs, seats)
- **On Collection**: Agents on each object in a collection
- **On Vertex**: Precise placement on mesh vertices

### Key Features
- **Fill Factor**: Control overall density (0.0-1.0)
- **Weight Paint**: Custom density patterns
- **Attribute Control**: Section-based agent assignment
- **Translation**: Local/global position adjustments

### Ideal Use Cases
- Sports stadiums
- Theaters and cinemas
- Conference venues
- Ceremonial seating

---

## 2. On Ground System

### Purpose
Natural-looking scattered crowds for outdoor environments

### Distribution Types
- **Singles**: Individual agents with density control
- **Clusters**: Social groups with size and radius variation

### Key Features
- **Density Control**: Overall population density
- **Cluster Variations**: Radius, count, and offset controls
- **Sphere Mask**: Object-based inclusion zones
- **Personal Space**: Automatic collision avoidance

### Ideal Use Cases
- Park scenes
- Outdoor events
- Public squares
- Beach crowds

---

## 3. On Curve System

### Purpose
Linear formations and queuing simulations

### Distribution Types
- **Radius Based**: Density varies with curve point radius
- **Count Based**: Fixed min/max agents per curve
- **Min Distance**: Evenly spaced by distance

### Key Features
- **Curve Editing**: Alt+S to adjust radius per point
- **Position Variation**: Natural offset from perfect alignment
- **Multiple Curves**: Complex formations with multiple paths
- **Length Control**: Precise spacing along curves

### Ideal Use Cases
- Waiting lines
- Processional movements
- Queue simulations
- Path lining

---

## 4. On Vertex System

### Purpose
Exact placement for precise formations and patterns

### Distribution Method
- **Vertex-based**: One agent per mesh vertex
- **Max Agents**: Global limit control
- **Exact Positioning**: Perfect grid or custom patterns

### Key Features
- **Mesh Object Input**: Any object with vertices
- **Position Variation**: Optional randomization offset
- **Vertex Groups**: Selective placement areas
- **Precise Control**: Pixel-perfect arrangements

### Ideal Use Cases
- Military formations
- Logo spelling
- Grid patterns
- Architectural population

---

## Common Features Across All Systems

### Orientation Control
- **Default**: Uniform facing direction
- **Random**: Natural variation in rotation
- **At Object**: All agents face target object

### Scale Variation
- **Min/Max Scale**: Size randomization
- **Seed Control**: Reproducible patterns

### Agent Management
- **Collection Input**: Animated agent groups
- **Probability Control**: Collection blending
- **Customization**: Clothing and appearance changes

### Performance Features
- **Max Agent Limits**: Scene optimization
- **Relax Iterations**: Collision quality vs performance
- **Seed Control**: Reproducible results

---

## Quick Selection Guide

### Choose Stadium System for:
- Venues with fixed seating
- Section-based crowd control
- Structured audience arrangements

### Choose On Ground System for:
- Natural outdoor crowds
- Social group simulations
- Organic density variations

### Choose On Curve System for:
- Lines and queues
- Processional movements
- Path-following crowds

### Choose On Vertex System for:
- Precise formations
- Custom patterns and shapes
- Exact positioning requirements

---

## Workflow Tips

1. **Start Simple**: Begin with Stadium or On Ground for most common scenarios
2. **Use Weight Painting**: Create natural density variations in all systems
3. **Combine Systems**: Mix different systems in one scene for complex crowds
4. **Test Scale**: Always verify agent sizing matches your scene scale
5. **Use Randomization**: Apply rotation and scale variations for natural results

These four static systems provide comprehensive coverage for all types of crowd placement scenarios, from highly structured venues to natural outdoor gatherings and precise formations.