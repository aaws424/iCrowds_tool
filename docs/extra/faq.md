# iCrowds Systems - Frequently Asked Questions

## General Questions

**Q: What's the difference between dynamic and static systems?**
A: Dynamic systems have moving agents with autonomous behaviors, while static systems place agents in fixed positions for background crowds.

**Q: What's the maximum number of agents supported?**
A: Most systems support up to 100,000 agents, but performance depends on your hardware and scene complexity.

**Q: Can I mix different systems in one scene?**
A: Yes! Combine systems like Walkers for paths + City for plazas + Stadium for seating areas.

**Q: How do I control where agents appear?**
A: Use weight painting, sphere masks, or vertex groups to define density areas.

## Dynamic Systems Questions

### City System
**Q: How do agents decide where to go?**
A: Agents have needs (hunger, sleep, fun, bladder) and pathfind to nearest relevant activities when needs get low.

**Q: What's the difference between walk and run speeds?**
A: Below walk speed = idle, between walk/run = walking animation, above run speed = running animation.

**Q: How does pathfinding detail affect performance?**
A: Lower values = faster simulation but less precise navigation. Use lower values for large scenes.

### Fluid System
**Q: How do flow curves work?**
A: Agents follow curve tangents. Use Alt+S in edit mode to scale radius and control zone of effect.

**Q: What's the purpose of relax iterations?**
A: Higher values prevent agents from passing through each other but cost performance.

**Q: Can attracters/repelers be animated?**
A: Yes! Animate the control objects to create dynamic crowd movements.

### Walkers System
**Q: What's the difference between respawn and delete modes?**
A: Respawn recycles agents at the start; delete removes them when they reach the end.

**Q: How do I create bidirectional traffic?**
A: Adjust the direction parameter above 0.5 to make some lanes go opposite directions.

## Static Systems Questions

### Stadium System
**Q: Which distribution type should I use?**
A: Use On Face for bleachers, On Instance for pre-built seats, On Collection for organized sections, On Vertex for precise seating.

**Q: How do I make some sections have different agent types?**
A: Use face attributes or instance attributes to assign different agent collections to different areas.

### Scatter Systems (On Ground/Curve/Vertex)
**Q: When should I use On Ground vs On Curve vs On Vertex?**
A: On Ground for natural crowds, On Curve for lines/queues, On Vertex for precise formations.

**Q: How do I prevent agents from overlapping?**
A: Use personal space settings and increase relax iterations.

**Q: Why are my agents floating or sinking?**
A: Adjust the up direction parameter and ensure your terrain is properly aligned.

## Technical Questions

**Q: How do I improve performance with many agents?**
A: Reduce pathfinding detail, lower relax iterations, use simpler agent meshes, and limit max agents.

**Q: Why aren't my agents moving?**
A: Check that activities are properly assigned, colliders are set up, and speed thresholds are correct.

**Q: How do I create custom agents?**
A: Prepare animated meshes with armatures, then add them through the custom agents panel in any system.

**Q: What does the seed parameter do?**
A: It ensures reproducible random patterns. Same seed = same agent distribution every time.

**Q: How do I make agents face different directions?**
A: Use the random rotation mode or At Object mode with randomization for natural variation.

## Troubleshooting

**Q: Agents are passing through each other**
A: Increase relax iterations and personal space settings.

**Q: Crowds look too uniform and artificial**
A: Add rotation randomization, scale variation, and position variation.

**Q: Simulation is running too fast/slow**
A: Adjust time scale for need depletion rates and speed scalars for movement speeds.

**Q: Agents stuck or not pathfinding properly**
A: Check collision objects, ensure activities are accessible, and increase pathfinding detail.