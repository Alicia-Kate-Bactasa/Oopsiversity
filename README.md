# OOPsiversity

> **Sneak onto campus, exploit entry loopholes, dodge patrolling guards, and beat the clock.**

An 8-bit, quest-centered campus stealth web game built with **Godot (.NET)** and **C#**[cite: 4, 5]. Players begin outside campus with a difficulty-based violation, read scattered hints to find entry loopholes, evade stationary and roving guards, complete campus tasks, cure their violations, and extract through a portal before the timer runs out.

---

## Team Members

- **Alicia Kate Bactasa**
- **Josh Kenzho Suarez**
- **Margarette Christel Balbuena**
- **June Jayson Culanag**

---

## Tech Stack & Environment

| Layer | Configuration & Notes |
| :--- | :--- |
| **Game Engine** | Godot Engine (.NET / Mono build, `4.7.2.stable.mono` in current workspace)[cite: 4, 5] |
| **Language & Runtime** | C# with .NET SDK (`Oopsiversity.csproj`, `Oopsiversity.sln`) |
| **Code Editor** | Visual Studio Code (set in **Editor Settings > Dotnet > Editor > External Editor**)[cite: 3, 5] |
| **Viewport & Scaling** | `320x180` base viewport, `viewport` stretch mode, `keep` aspect ratio, `Resizable` enabled[cite: 1, 2] |
| **8-Bit Rendering** | `Default Texture Filter` set to `Nearest` for crisp pixel art |
| **Assets & Deployment** | Sprites/audio from Kenney & OpenGameArt; planned web deployment on Itch.io / DCISM |

---

## Project Structure

```text
Oopsiversity/
├── scenes/        # Scene files (.tscn), starting with test_world.tscn (TestWorld root)[cite: 4, 5]
├── scripts/       # C# scripts (.cs), starting with TestWorld.cs[cite: 4, 5]
├── assets/        # 8-bit sprites, tilesets, fonts, and sound effects
└── resources/     # Custom data resources (.tres) and ConfigFile save data
```

---

## Getting Started

1. **Install prerequisites:** Install a **Godot .NET** build and the **.NET SDK** (verify in terminal with `dotnet --version`).
2. **Clone and open:** Clone the repository, open Godot, and select the project folder containing `project.godot`.
3. **Configure VS Code:** In Godot, open **Editor Settings**, search `dotnet`, go to **Dotnet > Editor**, and set **External Editor** to **Visual Studio Code**[cite: 3, 5].
4. **Build and run:** Click the **Build (hammer)** icon in the top-right corner of Godot so C# compiles with `0 Error(s)`, then run a scene (`test_world.tscn`)[cite: 4, 5].

---

## Core OOP Architecture

- **`CampusEntity` (Abstract Base Class):** Defines shared spatial behaviors such as movement and position queries across map entities.
- **`Player` & `Guard` (Subclasses):** Inherit from `CampusEntity` to implement player movement/stealth and guard patrol/detection states.
- **`IViolation` (Interface):** Declares loophole/violation checks overridden by concrete violation types (e.g., uniform or vehicle violations).
- **`GameManager` & `ViolationManager`:** Coordinate game state, scoring, difficulty, and violation assignment.
- **`Item`, `Task`, & `ExitGate`:** Handle collectible items, campus objectives, and score/extraction checks.
