# BlockGen - Unity3d

A lightweight voxel game engine built in Unity, featuring custom block mesh generation, chunk loading and unloading, block interaction, and first-person player movement.

> **Note:** The latest source code is currently available on the `dev` branch. The `main` branch does not contain the latest implementation yet.

## Demo

**Play the demo:** [[Your Demo Link](https://blooplanet.itch.io/blockgen-test)]

## Quick Start

### Requirements

* Unity **2022.3 LTS**
* Git

### Importing BlockGen into Unity

1. Clone or download this repository.
2. If you cloned the repository, switch to the `dev` branch:

   ```bash
   git checkout dev
   ```
3. Open **Unity Hub**.
4. Click **Add** → **Add project from disk**.
5. Select the folder containing the BlockGen project.
6. Open the project with **Unity 2022.3 LTS**.
7. Open the main scene from the `Assets` folder.
8. Press **Play** to run BlockGen.

> Make sure you are using Unity 2022.3 LTS. Opening the project with a different Unity version may cause compatibility issues.

## Features

* **Voxel blocks** — A block-based world built from voxel data.
* **Custom mesh generation** — Generates chunk meshes from the voxel data.
* **Chunk system** — The world is divided into manageable chunks.
* **Chunk loading and unloading** — Chunks are dynamically loaded and unloaded as the player moves.
* **Block placement** — Place blocks directly into the world.
* **Block breaking** — Remove blocks from the world.
* **Player movement** — First-person movement with jumping.
* **Fly Mode** — Double jump to toggle Fly Mode and move freely through the world.

## Controls

| Action          | Control            |
| --------------- | ------------------ |
| Move            | WASD               |
| Look            | Mouse              |
| Jump            | Space              |
| Place Block     | Left Mouse Button  |
| Break Block     | Right Mouse Button |
| Toggle Fly Mode | Double Jump        |

## How It Works

BlockGen represents the world as a collection of voxel blocks organized into chunks.

Instead of creating a separate Unity GameObject for every block, BlockGen generates a mesh for each chunk from its voxel data. This keeps the number of objects in the scene low and allows the engine to handle larger block-based worlds.

### Chunk Management

The world is divided into chunks. As the player moves, BlockGen loads chunks around the player and unloads chunks that are no longer needed.

This allows the engine to stream the world dynamically instead of keeping every chunk loaded at once.

### Block Interaction

When the player targets a block, BlockGen determines which voxel is being interacted with.

* Breaking a block removes it from the voxel data.
* Placing a block adds a new voxel next to the targeted block.
* The affected chunk can then regenerate its mesh to reflect the change.

### Mesh Generation

BlockGen converts voxel data into Unity meshes at runtime. The mesh represents the visible geometry of the voxel world rather than creating individual GameObjects for each block.

## Technical Focus

BlockGen was built to explore the fundamental systems behind voxel-based games:

* Voxel data
* Chunk-based world management
* Runtime mesh generation
* Dynamic chunk streaming
* Block placement and breaking
* First-person player movement
* Fly Mode

The engine is built from the ground up in Unity rather than using an existing voxel-engine framework.

## Project Status

BlockGen is currently in development.

The current version focuses on the core voxel-engine functionality: block mesh generation, chunk management, block interaction, and player movement.

## Roadmap

* [ ] Procedural terrain generation
* [ ] More block types
* [ ] Block textures and materials
* [ ] Improved mesh optimization
* [ ] Lighting system
* [ ] World saving and loading
* [ ] More advanced terrain generation
* [ ] Further performance improvements

## Built With

* **Unity 2022.3 LTS**
* **C#**

## Credits

BlockGen was developed as an exploration of voxel-engine development and real-time procedural mesh generation.

Thanks to the open-source community and learning resources that helped make the project possible.
