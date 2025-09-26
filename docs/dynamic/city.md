

# City iCrowd Simulation System - User Documentation

## 1.0 System Overview

The **City Crowd Simulation System** is a crowd generation tool for Blender that integrates seamlessly with the **iCity addon**. It allows users to populate urban environments with agents that navigate roads, sidewalks, and custom areas while avoiding obstacles.

Key features include:

* Automatic integration with **iCity road and sidewalk geometry**
* Optional **custom ground and colliders**
* Support for **default agents** (idle, walk, run) or **custom character collections**
* Configurable **population density, movement, and activity behaviors**

---

## 2.0 Inputs

### 2.1 iCity Integration

The system can automatically use iCity’s road and sidewalk geometry. It also auto-detects colliders from the sidewalk.

**Inputs:**

* **Road:** Main road geometry (required)
* **SideWalk:** Sidewalk geometry (required)
* **Colliders:** Automatically collected from sidewalks when using iCity

### 2.2 Custom Geometry

Users can provide their own ground geometry and colliders:

* **Ground:** Mesh representing walkable surfaces
* **Colliders:** Collection of objects to avoid (buildings, obstacles, etc.)

---

## 3.0 Agents

### 3.1 Agent Types

You can choose between:

1. **Default agents:** Idle, walk, run animations included
2. **Custom agents:** User-provided collection of characters

### 3.2 Agent Settings

* **Agents Speed Scaler:** Adjust the speed of agents (0.1–3.0, default 1.0)

---

## 4.0 Population Control

### 4.1 Density Settings

* **Distance Min:** Minimum spacing between agents (meters)
* **Density Max:** Maximum crowd density (0–1)
* **Density Factor:** Population multiplier (e.g., 0.5 = half, 2 = double)
* **Seed:** Randomize distribution for unique crowd arrangements

### 4.2 Mask

* **Vertex Group:** Limit agent spawning to specific areas

---

## 5.0 Movement and Simulation

### 5.1 Pathfinding

* **Path Finding Details:** Adjust precision vs performance
* **Time Scale:** Control simulation speed (1.0 = real-time)

### 5.2 Debug Tools

* **Debug Movement:** Visualize agent trajectories
* **Debug Activity:** Color-coded display of agent behaviors

---

## 6.0 Activity System

Agents can perform **four types of activities**:

| Activity   | Purpose       | Inputs                                                         |
| ---------- | ------------- | -------------------------------------------------------------- |
| ADM_fun    | Entertainment | Connect a collection of target objects (e.g., parks, theaters) |
| ADM_sleep  | Rest          | Collection of seating objects or benches                       |
| ADM_hunger | Nutrition     | Collection of restaurant or food location objects              |
| ADM_balder | Shelter       | Collection of covered or safe areas                            |

**Usage:**

1. Create target objects or empties at relevant locations
2. Group them into a collection
3. Connect the collection to the corresponding activity socket
4. Agents automatically navigate to the nearest target of that type

---

## 7.0 Recommended Workflow

1. Choose either **iCity integration** or **custom geometry**.
2. Set up **agents** (default or custom characters).
3. Configure **density and distribution** settings.
4. Set **pathfinding and simulation speed**.
5. Define **activities** for agents if required.
6. Use **debug tools** to verify agent movement and behaviors.

---

## 8.0 Optimization Tips

* Start with **Density Max ≤ 0.5** for better performance
* Simplify colliders and ground geometry
* Use **vertex group masks** to limit agent count
* For large-scale crowds, prefer **default agents** or simplified proxies

---

## 9.0 Notes

* Agents automatically avoid obstacles detected from sidewalks in iCity mode.
* Custom colliders override automatic detection if provided.
* Custom agents must include at least idle, walk, and run animations for proper integration.
* Random seed ensures varied crowd patterns on each simulation run.

---
