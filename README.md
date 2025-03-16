# Mango: A Connection Game (Godot Engine)

## Overview

Mango is a connection-based puzzle game, implemented in the Godot Engine using GDScript. Connect ripe mangoes while avoiding raw ones to achieve a target score.

## Installation

1.  **Godot Engine:**
    * Download and install the Godot Engine (version 3.x or 4.x).
2.  **Download/Clone:**
    * Download the project as a ZIP file or clone the repository using Git:
        ```bash
        git clone [repository URL]
        ```
3.  **Open in Godot:**
    * Open the Godot Engine.
    * Click "Import" and select the project's `project.godot` file.

## Usage

### Gameplay

* The game board consists of a grid of mangoes (ripe and raw).
* **Ripe Mangoes:** These are the targets. Connect them to score points.
* **Raw Mangoes:** Avoid connecting these! Connecting a raw mango will end the current attempt.
* **Connections:** Click on a ripe mango, then click on another ripe mango to connect them. Connections follow Tango mechanics: adjacent or through existing connections.
* **Scoring:** Each successful ripe mango connection adds to your score.
* **Target Score:** Reach the target score to clear the level.
* **Level Progression:** Each level increases the target score and may add more raw mangoes.

### Controls

* **Mouse Click:** Select and connect mangoes.

## Game Mechanics (Tango Style)

### Mango Types

* **Ripe Mango:** Represented by a yellow/orange `Sprite` or `TextureRect`. Connect these to score.
* **Raw Mango:** Represented by a green `Sprite` or `TextureRect`. Avoid these.

### Connection Rules (Tango Mechanics)

* Connections can only be made between ripe mangoes.
* Connections must be to an adjacent ripe mango, or to a ripe mango that is connected to the currently selected mango. This is the core of the Tango mechanic.
* Connections are stored as a list of connected nodes.
* A visual connection line is shown between connected mangoes.

### Scoring

* Each successful ripe mango connection awards 1 point.
* Each level has a target score.

### Level Design

* Levels are defined by a grid of mangoes (ripe and raw), created using Godot's GridContainer or similar node.
* Level data can be loaded from a JSON or CSV file, or defined directly within a Godot scene.

### Example Level Data (JSON)

```json
{
  "target_score": 5,
  "grid": [
    ["ripe", "raw", "ripe"],
    ["ripe", "ripe", "raw"],
    ["raw", "ripe", "ripe"]
  ]
}
