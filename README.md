# Woodland Walk

A small Godot 4.7 3D movement prototype: a mouse in a woodland courtyard, with a following orthographic camera, obstacles, a raised terrace and three exploration banners. All artwork is made from simple meshes in the project; no external assets are required.

For agent-assisted development, start with [AGENTS.md](AGENTS.md), then read
[project state](docs/agent/PROJECT_STATE.md), [tasks](docs/agent/TASKS.md), and
[decisions](docs/agent/DECISIONS.md). [Testing](docs/agent/TESTING.md) contains
reproducible checks and their limits; [architecture](docs/agent/SPEC_ARCHITECTURE.md)
describes the current code ownership.

Open `project.godot` in Godot and press **F6** in `main.tscn`, or **F5** to run the project.

```sh
godot --path /home/meatpigeon/Documents/Codex/2026-09-28/yeah-switch/outputs/woodland-walk
```

| Control | Action |
| --- | --- |
| WASD / arrow keys | Move relative to the camera |
| Shift | Run |
| Space | Jump |
| Q / E | Rotate camera |
| Mouse wheel | Zoom |
| R | Return to the starting position |

Walk close to each banner to mark it green. The ramp leads to the raised terrace. The courtyard edges are open; falling returns you to the start.

`scripts/player.gd` controls movement and the simple walking animation. `scripts/world.gd` builds the scene, camera and interface. This is a movement playground; combat and faction systems are future work.

Validation: imported and rendered with Godot 4.7.2. Ten automated checks cover grounding, walking, running, jumping and landing, wall collision, ramp traversal, camera-relative movement, fall recovery, and banner collection. A rendered screenshot was visually inspected; this does not substitute for a human playthrough.

```sh
godot --headless --path /home/meatpigeon/Documents/Codex/2026-09-28/yeah-switch/outputs/woodland-walk --script res://tests/movement.gd
```

# woodland-walk
