# iCrowds Dynamic Systems

## System Overview

iCrowds provides three specialized crowd simulation systems for different scenarios:

### 1. City System
**Purpose:** Autonomous urban population simulation  
**Best For:** 
- Open-world city environments
- Agents with independent needs and behaviors
- Complex urban planning studies

**Key Features:**
- Needs-based AI (hunger, sleep, fun, bladder)
- Automatic pathfinding to activities
- High agent customization
- Debug tools for behavior monitoring

### 2. Fluid System
**Purpose:** Artist-controlled crowd movement  
**Best For:**
- Directed crowd flow
- Event and venue simulations
- Emergency evacuation planning

**Key Features:**
- Flow curves for guided movement
- Attracter/repeler objects
- Multiple distribution methods
- Physics-based collision avoidance

### 3. Walkers System
**Purpose:** Organized path-based pedestrian traffic  
**Best For:**
- Sidewalks and crosswalks
- Museum/retail visitor flow
- Structured movement patterns

**Key Features:**
- Lane-based curve following
- Bidirectional traffic flow
- Simple setup and management
- Consistent animation patterns

## Quick System Selection Guide

**Choose City System if:**
- You want autonomous, life-like behavior
- Agents should make independent decisions
- Simulating daily urban activities

**Choose Fluid System if:**
- You need precise crowd direction control
- Using attractors/repellers to shape movement
- Creating natural crowd flow patterns

**Choose Walkers System if:**
- You need organized path following
- Simulating sidewalk or lane-based traffic
- Quick setup with predictable results

## Common Workflow

1. **Setup Environment** - Prepare terrain and collision objects
2. **Select System** - Choose based on your simulation needs
3. **Configure Distribution** - Place agents using density controls
4. **Set Behaviors** - Configure speeds, activities, or paths
5. **Add Controls** - Place flow curves, attracters, or activities
6. **Run Simulation** - Monitor with debug tools as needed

## Technical Notes

- All systems support custom agent collections
- Speed thresholds control animation transitions
- Distribution uses weight painting for density control
- Systems can be combined in different scene areas

## Getting Started

1. Start with the Walkers System for simple path-based crowds
2. Use Fluid System for controlled crowd movement
3. Implement City System for complex autonomous populations

**Remember:** You can mix systems in different parts of your scene for optimal results.