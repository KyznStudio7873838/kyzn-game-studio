# Kyzn Game Studio

**Android-First Game Engine Studio** — Inspired by Roblox Studio, built for creating mobile games with **C#** as the primary language.

> Status: Concept + Core Systems (MVP scripts ready)  
> Target Platform: Android (APK / AAB)  
> Main Language: C#

---

## What is Kyzn Game Studio?

Kyzn Game Studio is a conceptual game development environment focused on making **Android games** easily. It features:

- Scene / Map Editor (2D & 3D)
- Full C# Scripting + Visual Scripting
- Built-in systems: Inventory, Quest, Economy, NPC, Save/Load
- One-click Build to APK/AAB
- Mobile-first design (portrait 1080×1920 default)

This repository contains the **core C# systems**, project structure, technical design document, and build instructions so you can start building sample games right away using Unity.

---

## Features (Current)

| System              | Status     | Description                                      |
|---------------------|------------|--------------------------------------------------|
| Player Controller   | Ready      | Movement, jump, camera-relative, mobile input    |
| Inventory System    | Ready      | Stackable items, weight limit, events, JSON save |
| Quest Manager       | Ready      | Main/Side quests, objectives, rewards            |
| Economy System      | Ready      | Currency (Gold), buy/sell helpers                |
| Save / Load         | Ready      | Multi-slot, auto-save, JSON based                |
| NPC Controller      | Ready      | Patrol, NavMesh, interaction, quest giver        |
| Visual Scripting    | Designed   | Node system design (see docs)                    |
| Android Build       | Documented | Full pipeline + recommended settings             |

---

## Project Structure

```
KyznGameStudio/
├── Scripts/
│   └── PlayerController.cs
├── Systems/
│   ├── InventorySystem.cs
│   ├── QuestManager.cs
│   ├── EconomySystem.cs
│   ├── SaveLoadSystem.cs
│   └── NPCController.cs
├── PROJECT_STRUCTURE.md
├── README_BUILD_APK.md      ← How to build APK
└── README.md                ← This file
```

---

## Quick Start

### 1. Requirements
- Unity 2022.3 LTS or Unity 6
- Android Build Support module (SDK + NDK + OpenJDK)

### 2. Setup
1. Create a new **3D** Unity project
2. Copy the `Scripts/` and `Systems/` folders into `Assets/`
3. Follow the detailed guide in [`README_BUILD_APK.md`](README_BUILD_APK.md)

### 3. Build APK
- File → Build Settings → Android → Switch Platform
- Set Scripting Backend = **IL2CPP**, Architecture = **ARM64**
- Click **Build**

---

## Documentation

- **Technical Design Document** (PowerPoint): included in the release / parent folder
- [Build APK Guide](README_BUILD_APK.md)
- [Full Project Structure](PROJECT_STRUCTURE.md)

---

## Roadmap

**Phase 1 – MVP** (Current foundation)
- [x] Core C# systems
- [x] Project structure & docs
- [ ] Sample scene + prefabs
- [ ] Virtual Joystick + Mobile UI

**Phase 2 – Core Systems**
- [ ] Visual Scripting runtime
- [ ] Combat system
- [ ] Animation & Audio helpers
- [ ] Material / Shader examples

**Phase 3 – Polish**
- [ ] Terrain tools
- [ ] Advanced lighting
- [ ] Multiplayer foundation
- [ ] Cloud save

---

## Contributing

This is currently a personal/concept project. Feel free to fork, experiment, and open issues or pull requests if you want to improve the systems.

---

## License

MIT License — feel free to use the scripts in your own games (commercial or non-commercial).

---

## Author

**Kyzn Studio**  
Concept & Core Systems designed for Android game creators who love C#.

---

⭐ If you find this useful, give the repo a star!
