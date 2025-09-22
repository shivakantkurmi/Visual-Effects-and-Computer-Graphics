# Semi-Rigid and Rigid Debris Simulation in Blender

This Blender Python script simulates a combination of **rigid debris** and **semi-rigid debris connected with springs**. It demonstrates rigid body physics and spring constraints in a single cohesive simulation.

## Features

* Creates a **ground plane** for debris to fall onto.
* Spawns **rigid cubes** (red) that fall freely under gravity.
* Spawns **semi-rigid cubes** (blue) connected by spring constraints to form a chain.
* Configures physics properties like **mass, friction, restitution, spring stiffness, and damping**.
* Adds a **camera** for viewing the simulation.
* Automatically sets up the **Rigid Body World** and scene parameters.

## Requirements

* Blender 3.x (tested with 3.6+)
* Python 3.x (Blender’s built-in Python interpreter is used)

## Usage

1. Open Blender.
2. Open a new **Text Editor** window and paste the Python script.
3. Press **Run Script** to set up the scene.
4. Press **Spacebar** in the 3D Viewport to play the physics simulation.
5. Optionally, **bake the rigid body cache** for consistent playback:

   * Go to **Scene Properties → Rigid Body World → Cache**
   * Click **Bake**

## Script Parameters

All parameters for rigid cubes, semi-rigid cubes, and springs are configured at the top of the script:

```python
NUM_RIGID = 5          # Number of rigid cubes
NUM_SEMI_RIGID = 5     # Number of semi-rigid cubes
DROP_HEIGHT = 8.0      # Initial height of cubes
SIM_FRAMES = 250       # Total frames of the simulation
GRAVITY = -9.81        # Gravity strength

# Spring settings inside connect_spring()
stiffness = 50         # Spring stiffness
damping = 5            # Spring damping
```

* **Rigid cubes**: mass = 3, color = red
* **Semi-rigid cubes**: mass = 1.5, color = blue, connected with spring constraints

These settings control the physics behavior of both types of debris and the spring stiffness/damping of the semi-rigid chain. You can also uncomment the last line to form a **closed ring** of semi-rigid cubes.

## Notes

* The blue "thread-like" lines in the 3D viewport indicate **spring constraints**.
* The script automatically ensures a **Rigid Body World** is present.

## Author

**Shivakant Kurmi**

## License

This project is licensed under the MIT License.
