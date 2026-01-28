# Ragdoll iCrowd System - User Documentation

**Version:** 2.0.0 | **Last Updated:** January 21, 2026

---

## Introduction

The iCrowds Ragdoll System enables the creation of dynamic crowds that blend animated motion with realistic physics simulation. This system is designed for generating walking or running crowds that can transition to a ragdoll state upon encountering triggers such as obstacles or designated danger zones. It is suitable for action sequences, simulations of accidents, or any scenario requiring interactive crowd behavior.

The system supports both pre-built character assets and user-provided custom rigs.

---

## Table of Contents

1. [Quick Start Guide](#quick-start-guide)
2. [System Overview](#system-overview)
3. [Working with Agents](#working-with-agents)
4. [Agent Distribution](#agent-distribution)
5. [Motion Controls](#motion-controls)
6. [Ragdoll Triggers](#ragdoll-triggers)
7. [Creating Custom Ragdoll Characters](#creating-custom-ragdoll-characters)
8. [Animation & NLA System](#animation-nla-system)
9. [Physics Fine-Tuning](#physics-fine-tuning)
10. [Baking for Final Render](#baking-for-final-render)
11. [Troubleshooting](#troubleshooting)
12. [Technical Reference](#technical-reference)

---

<a name="quick-start-guide"></a>
## 1. Quick Start Guide

Follow these steps to quickly set up a basic ragdoll crowd simulation.

### Step 1: Create the System
1. In Blender, navigate to the **N-panel** and select the **iCrowds** tab.
2. Click **START EDITOR**.
3. Select **DYNAMIC** and click **→ Ragdoll System**.

A new crowd controller object will appear in your scene.

### Step 2: Define the Walking Surface
1. In the **Control** tab, ensure you are in **Scatter** mode.
2. Locate the **Navigation Mesh** field.
3. Select a mesh object to serve as the ground or floor.
   *Note: A simple plane is sufficient for initial testing.*

### Step 3: Add Characters
1. Switch to the **Agents** tab.
2. Click the **+** button to create a new agent group.
3. Open **Agents Settings**, select **MEN** or **WOMEN**.
4. Browse the character thumbnails and click **Include** on your chosen agents.

### Step 4: Populate and Simulate
1. Return to the **Control** tab.
2. Switch from **Scatter** to **Ragdoll** mode.
3. Click the **Populate** button.
4. Press **Play** on the timeline to begin the simulation.

Your characters should now be walking within the scene.

---

<a name="system-overview"></a>
## 2. System Overview

The Ragdoll System operates using a dual-armature architecture for each character, enabling a seamless transition between animation and physics.

### Dual-Armature Architecture
Each character is controlled by two armatures:
*   **Anim_Arm:** Drives the character using standard walk, run, and idle animations.
*   **RBD_Arm:** A physics-driven duplicate that takes control when ragdoll mode is activated.

Under normal conditions, `Anim_Arm` is active. When a ragdoll trigger condition is met, control switches instantaneously to `RBD_Arm`, initiating a physics-based simulation.

### Automated Animation Blending
The system reads the speed attribute from the geometry nodes simulation and automatically blends between animation states:
*   **Idle:** Plays when the agent's speed is below the defined walking threshold.
*   **Walk:** Blends in as speed increases above the idle threshold.
*   **Run:** Blends in when speed exceeds the running threshold.

---

<a name="working-with-agents"></a>
## 3. Working with Agents

### Using Pre-Built Characters
The system includes 20 pre-rigged and animated characters (10 men, 10 women).

**To Add Pre-Built Characters:**
1. Navigate to the **Agents** tab.
2. Select a category (**MEN** or **WOMEN**).
3. Browse the thumbnail gallery.
4. Click **Include** to add an agent, or **Discard** to remove it.

**Additional Features:**
*   **Clothing Variation:** Apply different outfits to agents.
*   **Level of Detail (LOD):** Toggle between high and low-poly versions for performance management.

### Agent Groups and Probability
Characters can be organized into groups. A probability weight controls the frequency of each group's appearance during population.

**Example Setup:**
*   Group "Office Workers" with Probability: 0.7 (appears in ~70% of spawns).
*   Group "Construction" with Probability: 0.3 (appears in ~30% of spawns).

**To Set Probability:**
1. Select a group from the list in the **Agents** tab.
2. Adjust the **Probability** slider that appears.
   *Note: Probabilities are relative weights and do not need to sum to 1.0.*

---

<a name="agent-distribution"></a>
## 4. Agent Distribution

Three methods are available for placing agents in the scene.

### Option 1: iCrowds Objects
*Best for precise placement and specific formations.*
1. Set **Distribution Type** to `iCrowds Objects`.
2. Assign your custom placement object.
3. Edit the object to add or modify individual spawn points.

### Option 2: Scatter on Terrain
*Best for natural, random crowd distribution.*
Agents are randomly placed across the assigned navigation mesh.

| Setting | Description |
|---------|-------------|
| **Distance Min** | Minimum allowable space between agents to prevent clipping. |
| **Density Max** | Controls how densely agents are packed in the area. |
| **Seed** | Changes the random number generator seed for different arrangements. |
| **Mask Vertex Group** | A vertex group painted on the navigation mesh to define areas where agents should NOT spawn. |

### Option 3: Distribute on Vertex
*Best for grid-like or precisely organized placement (e.g., stadium seating).*
1. Create a mesh where each vertex represents one agent's spawn location.
2. Assign this mesh to the **Object** field in the distribution settings.

### Agent Rotation Control
Control the initial facing direction of agents:

| Mode | Description |
|------|-------------|
| **Look Direction** | All agents face a consistent global direction. |
| **Look at Object** | All agents orient towards a specified target object. |
| **Random** | Agents face random directions for a natural look. |

---

<a name="motion-controls"></a>
## 5. Motion Controls

Motion behavior is configured in the **Control** → **Motion** tab.

### Speed Thresholds
These values define the transitions between animation states based on agent speed.

| Setting | Default Value | Description |
|---------|---------|---------------|
| **Idle → Walk Threshold** | 0.100 m/s | Speeds below this value use the Idle animation. |
| **Walk → Run Threshold** | 1.000 m/s | Speeds above this value use the Run animation. Speeds between the two thresholds use Walk. |
| **Max Speed** | 1.000 m/s | The maximum movement speed for any agent. |
| **Relax Iterations** | 1 | Higher values produce smoother agent-to-agent avoidance at a computational cost. |

### Movement Influencers
Guide crowd flow using curves and force fields.

#### Flow Curves
Agents are influenced to follow drawn curve objects.
*   **Flow Curve:** A single curve for agents to follow.
*   **Flow Curves:** A collection of curves for complex path networks.
*   **Flow Speed:** Controls the strength of the attraction to the curves.

#### Attractors
Objects that pull agents toward them (e.g., exits, stages).
*   Can be a single object or a collection.

#### Repellers
Objects that push agents away (e.g., barriers, hazards).
*   Agents will attempt to navigate around these objects.

### Personal Space Configuration
Control the minimum distance agents maintain from each other.

| Setting | Effect |
|---------|--------|
| **Personal Space** | The radius of space each agent tries to keep clear. |
| **Relax Iterations** | Higher values yield more consistent spacing (increased compute). |

---

<a name="ragdoll-triggers"></a>
## 6. Ragdoll Triggers

Define the conditions under which agents switch from animation to physics (ragdoll) mode.

### Trigger Objects
Agents become ragdolls upon colliding with designated trigger objects.
1. Create a mesh object to act as a trigger (e.g., a cube or sphere).
2. In **Movement** → **Ragdoll** section, assign it to **Ragdoll Trigger**.
3. Adjust **Trigger Margin** to fine-tune the activation proximity.
*For multiple triggers, use a collection assigned to **Ragdoll Triggers**.*

### Distance-Based Triggers
Activate ragdoll based on the distance an agent has traveled.

| Setting | Description |
|---------|---------|
| **Trigger on Distance** | Enable this mode. |
| **Min Distance** | The minimum travel distance before triggering is possible. |
| **Max Distance** | The distance at which triggering becomes certain. |
| **Seed** | Introduces randomness to which agents trigger within the range. |

### Speed-Based Triggers
Activate ragdoll when an agent's speed falls outside a defined range.

| Setting | Description |
|---------|---------|
| **Trigger on Speed** | Enable this mode. |
| **Min Speed** | The lower speed bound for triggering. |
| **Max Speed** | The upper speed bound for triggering. |
| **Seed** | Adds randomness to the triggering. |

---

<a name="creating-custom-ragdoll-characters"></a>
## 7. Creating Custom Ragdoll Characters

You can integrate your own character rigs into the system.

### Character Requirements
Your character asset must include:
*   A fully rigged **armature**.
*   A **mesh** skinned to the armature.
*   Proper **vertex groups** with names matching the bone names.
*   Animation actions (Idle, Walk, Run are recommended).

### Integration Process

#### 1. Prepare Your Character
Ensure your character rig functions correctly with its animations in Blender.

#### 2. Access the Custom Agent Panel
1. Go to the **Agents** tab.
2. Click **Custom Ragdoll**.

#### 3. Assign Armature and Mesh
1. Select your character's armature in the **Armature** picker.
2. Select the character mesh in the **Agent Mesh** picker.

#### 4. Generate Physics Bones
This creates the collision shapes and constraints needed for ragdoll physics.
1. Enter **Pose Mode** for your selected armature.
2. Select the bones you wish to be driven by physics (e.g., spine, limbs, head).
3. Click **Generate RBD Bones**.
   *Capsule collision shapes will appear around the selected bones.*

#### 5. Add and Enable the Character
1. Click **Add Custom Agent** to register the character.
2. Toggle **Use in Scatter** to ON. The system will now use your custom character.

### Result of "Generate RBD Bones"
For each selected bone, the operator creates:
*   `RB_[BoneName]`: A capsule-shaped rigid body for collision.
*   `RB_Con_[BoneName]`: A physics constraint (joint) object.
*   `[YourArmature]_RBD`: A duplicate armature linked to the physics system.
It also configures the necessary modifiers to enable the dual-armature switching.

---

<a name="animation-nla-system"></a>
## 8. Animation & NLA System

### Default Animation Tracks
The system uses Blender's Non-Linear Animation (NLA) system with three default tracks per character:

| Track | Activation Condition |
|-------|----------------------|
| **Idle** | Agent speed < Idle→Walk Threshold. |
| **Walk** | Agent speed is between Idle→Walk and Walk→Run Thresholds. |
| **Run** | Agent speed > Walk→Run Threshold. |

The system crossfades between these tracks based on the real-time speed attribute.

### Adding Custom Animation Tracks
You can add additional animation actions to an agent.
1. After populating, go to **Ragdoll Settings**.
2. Select an armature from the list.
3. Expand **Animation Settings**.
4. Click **Add Animation Strip**.
5. Assign an existing action to the new strip.

### Animation Sync
If an animation appears to play at the wrong speed, sync it to its action length:
1. Locate the animation track in the list within **Animation Settings**.
2. Click the **Sync** button next to it.

### Animation Variety
To avoid uniformity, the system automatically:
*   Applies a random offset to the start frame of each agent's animation cycle.
*   Can alternate between different actions assigned to the same track type.

---

<a name="physics-fine-tuning"></a>
## 9. Physics Fine-Tuning

### Per-Bone Physics Properties
After generating RBD bones, you can adjust individual bone physics in the **RBD Settings** panel.

| Property | Effect |
|----------|--------|
| **Mass** | Influences inertia and response to forces. |
| **Friction** | Affects sliding behavior on surfaces. |
| **Bounciness** | Controls restitution upon impact. |
| **Mesh Scale** | Scales the collision capsule dimensions. |

### Joint Rotation Limits
Define the range of motion for physics joints.
1. Select a bone from the list in **RBD Settings**.
2. Expand **Rotation Limits**.
3. Adjust the **Min** and **Max** values for the X, Y, and Z axes.

**Example - Elbow Joint:**
*   X Axis (Primary bend): Min = 0°, Max = 140°.
*   Y & Z Axes (Secondary wobble): Min = -10°, Max = 10°.

### Joint Springs
Add spring-like behavior to help joints maintain a rest pose.

| Setting | Effect |
|---------|--------|
| **Use Spring** | Enables spring physics on the selected axis. |
| **Stiffness** | The strength with which the joint returns to its rest position. |
| **Damping** | Reduces oscillation from the spring force. |

### Global Physics Notes
*   Always run a physics simulation preview to verify behavior.
*   Adjust the **Trigger Margin** if activation occurs too early or late.
*   Ensure your ground/navigation mesh has a Rigid Body collision type assigned.

---

<a name="baking-for-final-render"></a>
## 10. Baking for Final Render

Baking converts the physics simulation and procedural animation into standard keyframe animation. This ensures smooth playback and consistent rendering.

### Baking Procedure

#### For a Single Character:
1. Select the character's armature from the list in **Ragdoll Settings**.
2. Click **Bake Selected**.
3. Define the Start and End frame range.
4. Optionally, enable **Delete RBD Bones** to clean up physics objects post-bake.
5. Click OK.

#### For All Characters:
1. Use the **Bake All** operator for a more efficient batch process.

### Result of Baking
The bake operator generates keyframes for:
*   All bone location and rotation data.
*   The overall object transformation (location, rotation, scale).
*   The visibility states of the armature-switching modifiers.

### Post-Bake Cleanup
If **Delete RBD Bones** was enabled, all rigid body capsules, constraints, and the physics armature duplicate will be automatically removed, leaving a clean, keyframed character ready for rendering.

**Warning:** Baking is a destructive operation. It is recommended to save your project file before baking.

---

<a name="troubleshooting"></a>
## 11. Troubleshooting

### Issue: No agents appear after clicking "Populate".
**Possible Causes and Solutions:**
1.  **Missing Navigation Mesh:** Assign a ground object in the **Control** > **Scatter** settings.
2.  **Empty Agent Groups:** Ensure at least one agent is included in an active group via the **Agents** tab.
3.  **Zero Probability:** Verify the selected agent group has a probability greater than 0.
4.  **Incorrect Distribution:** Try using the "Distribute On Terrain" method as a test.

### Issue: Agents are present but not animating.
**Verification Steps:**
1.  Ensure the timeline is playing.
2.  Check that the character's armature has NLA tracks (Idle, Walk, Run).
3.  Confirm the Geometry Nodes modifier is outputting a valid `Speed` attribute.

### Issue: Physics ragdoll does not activate.
**Verification Steps:**
1.  Confirm a **Rigid Body World** exists in your scene (`Scene Properties > Rigid Body World`).
2.  Verify a **Ragdoll Trigger** object or collection is correctly assigned.
3.  Check the **Trigger Margin** value; increase it if the trigger is not being hit.
4.  Try manually baking the rigid body world simulation first (`Scene Properties > Rigid Body World > Bake`).

### Issue: Character mesh deforms incorrectly.
**Likely Causes and Fixes:**
1.  **Vertex Group Mismatch:** Ensure vertex group names exactly match their corresponding bone names.
2.  **Modifier Order:** Verify the `Anim_Arm` Armature modifier is placed *above* the `RBD_Arm` modifier in the stack.
3.  **Object Scale:** Apply scale to the original character mesh (`Object > Apply > Scale`).

### Issue: Simulation performance is slow.
**Optimization Strategies:**
1.  Reduce the total agent count.
2.  Lower the **Relax Iterations** value to 1.
3.  Enable **LOD** versions for characters where available.
4.  Use simple Capsule collision shapes instead of Mesh shapes in the RBD bone settings.

---

*Developed by Parametra.*