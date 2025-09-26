# iCrowd Simulation Tool - Complete FAQ

## General Questions

### 🤔 **What's the difference between the four static systems?**
- **On Ground**: For scattering across surfaces/terrains (most flexible)
- **On Curve**: For path-based distributions with width control  
- **On Vertex**: For precise placement on mesh vertices
- **Stadium**: For organized seating/venue layouts with multiple input methods
- **Walkers**: For structured path-based crowd flows
- **City**: For urban environment placements with activities
- **Fluid**: For dynamic movement control (not static)

### ⚡ **Which static system is fastest for large crowds?**
**Performance Ranking**:
1. **On Ground** - Best for massive terrain scattering
2. **On Curve** - Efficient for linear path distributions  
3. **Stadium** - Optimized for organized layouts
4. **On Vertex** - Precision placement (slower with high vertex counts)
5. **Walkers** - Complex path-based logic
6. **City** - Activity system adds overhead

### 🔄 **Can I combine multiple static systems?**
**Yes! Recommended combinations**:
- **Stadium + On Ground**: Seating areas + standing crowds
- **On Curve + On Vertex**: Pathways + specific points of interest
- **Walkers + City**: Structured flows + environmental crowds
- All systems can be layered for complex scenes

## On Ground System FAQ

### 🌍 **When should I use Singles vs Clusters?**
- **Singles**: Individual people, random scattering, natural distributions
- **Clusters**: Group formations, families, conversation groups, organized patterns

### 🎯 **How does vertex group masking work?**
Paint vertex weights on your terrain:
- **White areas**: Full density
- **Black areas**: No agents
- **Gray areas**: Proportional density
- Perfect for creating natural density variations

### 📏 **What's the difference between Min Distance and Personal Space?**
- **Min Distance**: Hard limit - agents never get closer than this
- **Personal Space**: Soft constraint - system tries to maintain this distance but may vary for natural look

## On Curve System FAQ

### 🛣️ **How do I control density along curves?**
Use **curve point radius scaling**:
- Wider radius = more agents in that area
- Narrower radius = fewer agents
- Adjust **Radius Multiplier** to amplify/reduce this effect

### 📐 **Count vs Density placement?**
- **Count**: Fixed number of agents distributed along entire curve
- **Density**: Agents per unit length - automatically adjusts to curve length

### 🔄 **Can agents follow complex curved paths?**
Yes! The system automatically orients agents to follow curve direction. Use **Look Direction** settings to fine-tune.

## On Vertex System FAQ

### 📍 **What's the advantage over regular scattering?**
**Precision control**: Each agent placed on exact vertices, perfect for:
- Architectural layouts
- Predefined seating patterns
- Data visualization
- Exact formations

### 🎨 **How do I create custom patterns?**
Use vertex groups to select specific vertices:
- Create vertex group with only desired vertices
- System places agents only on selected points
- Perfect for logos, text, or specific patterns

### 📊 **Performance with high-vertex meshes?**
The system is optimized, but very dense meshes (100k+ vertices) may slow down. Use **Max** parameter to limit agent count.

## Stadium System FAQ

### 🏟️ **What are the four distribution methods?**
1. **On Face**: Grid-based placement on surfaces (most flexible)
2. **On Instance**: Use existing geometry node instances (fastest)
3. **On Collection**: Distribute across scene objects
4. **On Vertex**: Precise vertex-based control

### 💺 **Which method is best for theater seating?**
**Recommended workflow**:
1. **On Instance** with chair geometry nodes (performance)
2. **On Vertex** with seat vertex layout (precision)
3. Adjust **Fill Factor** for occupancy rate
4. Use **Rotation Type** for proper audience orientation

### 📐 **On Face method - why do I need UVs?**
UVs ensure proper grid distribution across the face. Just add a simple plane and scale it - the system handles UVs automatically.

### 🎪 **How do I create different seating sections?**
**Section control methods**:
- **Weight Painting**: Paint density variations on the surface
- **Vertex Groups**: Define different sections with vertex groups
- **Fill Factor**: Control overall occupancy percentage
- **Multi-object**: Use different agent types for different sections

## Walkers System FAQ

### 🛣️ **When should I use Walkers vs On Curve?**
- **Walkers**: Complex behaviors, lane management, structured flows
- **On Curve**: Simple path following, faster setup
- Use Walkers for intelligent crowd behaviors, On Curve for basic path following

### 📏 **How do I control agent spacing in Walkers?**
- **Personal Space Min/Max**: Sets minimum and desired distances
- **Density**: Overall crowd concentration
- **Noise**: Adds natural variation to spacing
- **Lanes**: Separate flow paths with individual control

### 🔄 **What's the difference between Lanes Count and Density?**
- **Lanes Count**: Number of parallel paths for agent flow
- **Density**: How closely agents are packed within each lane
- Use both for complex multi-lane scenarios

## City System FAQ

### 🏙️ **What makes City system unique for urban scenes?**
- **Activity-based behaviors**: Agents have states (sleep, eat, work, fun)
- **Infrastructure-aware**: Automatically respects roads, sidewalks, buildings
- **Collision management**: Built-in avoidance for urban obstacles
- **Time-based patterns**: Activities follow day/night cycles

### 🎯 **How do Activities work?**
Each activity (ADM_fun, ADM_sleep, etc.) defines:
- **Location**: Where the activity occurs
- **Timing**: When agents engage
- **Behavior**: How agents act during activities
- **Collections**: Groups of related objects

### 🌆 **Best workflow for city scenes?**
1. Set up **ICity** infrastructure (roads, sidewalks)
2. Define **Activities** and their locations
3. Configure **Density** and **Mask** for natural distribution
4. Add **Custom** elements and colliders

## Fluid System FAQ

### 🌊 **How do I transition from static to dynamic?**
Three-step process:
1. Create static distribution with any static system
2. Import into Fluid system via density inputs
3. Activate movement with curves, attractors, or repellers

### 🎮 **What movement control methods are available?**
- **Path Following**: Agents follow curve direction
- **Attraction**: Move toward target objects
- **Repulsion**: Avoid specific areas/objects
- **Combined**: Use all three simultaneously

### ⚡ **How do I control simulation speed?**
**Speed Settings**:
- **Walk Speed**: Normal movement (m/s)
- **Run Speed**: Fast movement (m/s)
- **Max Speed**: Velocity cap
- **Relax Iterations**: Physics smoothing

## Technical Issues & Performance

### ⚠️ **Agents floating above ground?**
- Check **Terrain** object is properly set
- Ensure **Up Direction** matches scene orientation
- Verify agent pivot points are correct

### 🔄 **Rotation looks wrong?**
- Adjust **Up Direction** for surface alignment
- Set **Look Direction** for forward orientation
- Use **Rotation variations** for natural randomness

### 🐌 **System running slow?**
- Reduce **Relax Iterations** (start with 3-5)
- Lower agent count with **Max** parameter
- Use simpler agent meshes during setup
- Disable viewport preview when not needed

## Workflow Tips & Best Practices

### 🎨 **How to make crowds look natural?**
- Always use **Scale** and **Rotation variations**
- Mix agent types with **Collections**
- Add **Noise** parameters to break patterns
- Use **Personal Space** ranges, not fixed distances

### 🏗️ **Best pipeline for complex scenes?**
1. **Blocking**: Simple proxies with basic systems
2. **Layout**: Refine density and distribution
3. **Animation**: Add movement with Fluid system
4. **Polish**: Fine-tune behaviors and variations

### 🎬 **Preparing for different use cases?**
**Architectural Visualization**:
- City system for environment setup
- Moderate density with natural variations

**Event Planning**:
- Walkers for structured flow patterns
- Stadium for seating arrangements

**Entertainment**:
- All systems combined for complexity
- Exaggerated behaviors for visual appeal

## Advanced Techniques

### 🌊 **Creating density gradients?**
**Methods by system**:
- **On Ground**: Vertex group painting
- **On Curve**: Vary curve radius along path
- **Stadium**: Weight painting for section density
- **City**: Activity-based density variations

### 🎭 **Mixing agent types and behaviors?**
- Use **Collections** with multiple objects
- Assign different activities to agent groups
- Create behavior variations through parameters
- Use vertex groups for type distributions

### 📱 **Optimizing for real-time/game engines?**
- Use low-poly agent meshes with LODs
- Bake animations when possible
- Reduce texture resolutions
- Use instancing for duplicate agents

## Troubleshooting Common Problems

### ❌ **No agents appearing?**
- Check **Max** parameter isn't set to 0
- Verify terrain/curve references are valid
- Ensure vertex groups aren't completely masked
- Confirm all required inputs are connected

### 🔀 **Agents clipping through each other?**
- Increase **Min Distance** or **Personal Space**
- Add more **Relax Iterations**
- Use **Space Min/Max** for tighter control

### 📐 **Scale issues between systems?**
- Consistent unit scale across all systems
- Match terrain scale to agent proportions
- Adjust **Speed** parameters relative to scene size

### 🎯 **Attract/Repel systems not working?**
- Confirm objects are properly referenced
- Check distance ranges are appropriate
- Verify systems are enabled in controls
- Test with exaggerated values first

---

**Need more help?** Check our video tutorials and example files for visual guidance on complex setups! The community forum also has advanced techniques shared by other users.