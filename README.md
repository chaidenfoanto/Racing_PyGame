# Racing Game

A 2D top-down racing game built with Python and Pygame for a Computer Graphics course assignment. The player races against an AI opponent across 10 progressive levels, where both cars grow in size and the AI speeds up each level.

---

## Features

- Player-controlled car using keyboard input (WASD)
- AI opponent that follows a predefined path using angle-based navigation
- Collision detection with track borders using pixel-perfect masking
- 10 levels with increasing difficulty — AI speed and car size scale each level
- Pause and resume functionality
- Full game reset with a single key press
- HUD displaying current level, elapsed time, and player velocity

---

## Controls

| Key | Action |
|-----|--------|
| W | Accelerate forward |
| S | Reverse |
| A | Rotate left |
| D | Rotate right |
| P | Pause / Resume |
| R | Reset game to level 1 |

---

## Tech Stack

- Language: Python 3
- Library: Pygame
- Font: Poppins (bundled in fonts/)
- Assets: Custom track, car, and grass images (bundled in imgs/)

---

## Project Structure

```
racing-game/
├── main.py           # Main game loop, car classes, collision handling
├── utils.py          # Helper functions for image scaling and rendering
├── fonts/
│   └── Poppins-Regular.ttf
└── imgs/
    ├── grass.jpg
    ├── track.png
    ├── track-border.png
    ├── finish.png
    ├── red-car.png
    └── green-car.png
```

---

## How to Run

Make sure Python 3 and Pygame are installed.

Install Pygame if you haven't already:

```
pip install pygame
```

Then run the game:

```
python main.py
```

---

## How It Works

**Player Car**
The player car accelerates and decelerates smoothly using a constant acceleration value. Hitting the track border triggers a bounce that reverses velocity. Crossing the finish line from the correct direction advances the level.

**AI Car**
The AI follows a hardcoded list of waypoints using angle-based steering. Each frame it calculates the angle toward the next waypoint and rotates toward it incrementally. On each new level, the AI resets to the start and increases its base velocity by 0.2 units.

**Difficulty Scaling**
Every level, both cars are rescaled by 5% using the update_scale method. The AI also gets faster, making it progressively harder to beat as levels advance.

**Pause System**
The pause system preserves elapsed time accurately. When the game is paused, the elapsed time before the pause is stored. When resumed, the level start time is adjusted by the duration of the pause so the timer continues from where it left off.

---

## What I Learned

Building this taught me how pixel-perfect collision detection works using surface masks in Pygame, and how angle-based pathfinding can produce surprisingly smooth AI movement from just a list of coordinates. Managing game state cleanly across multiple classes also gave me a clearer sense of how to structure a game loop that stays readable as features are added.
