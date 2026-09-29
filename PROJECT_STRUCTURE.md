# Kyzn Game Studio — Project Folder Structure

```
KyznGameStudio/
├── Assets/
│   ├── Scenes/
│   │   ├── MainMenu.unity
│   │   ├── GameWorld.unity
│   │   └── TestArena.unity
│   ├── Scripts/
│   │   ├── Player/
│   │   │   └── PlayerController.cs
│   │   ├── Systems/
│   │   │   ├── InventorySystem.cs
│   │   │   ├── QuestManager.cs
│   │   │   ├── EconomySystem.cs
│   │   │   ├── SaveLoadSystem.cs
│   │   │   ├── NPCController.cs
│   │   │   └── InteractionSystem.cs
│   │   ├── UI/
│   │   │   ├── InventoryUI.cs
│   │   │   ├── QuestUI.cs
│   │   │   ├── HUDController.cs
│   │   │   └── MobileControls.cs
│   │   ├── Combat/
│   │   │   ├── HealthSystem.cs
│   │   │   └── DamageDealer.cs
│   │   └── Core/
│   │       ├── GameManager.cs
│   │       └── EventBus.cs
│   ├── Prefabs/
│   │   ├── Player/
│   │   ├── NPCs/
│   │   ├── Items/
│   │   ├── UI/
│   │   └── Environment/
│   ├── Models/
│   ├── Materials/
│   ├── Textures/
│   ├── Audio/
│   │   ├── SFX/
│   │   └── Music/
│   ├── Animations/
│   ├── Shaders/          # HLSL / Shader Graph
│   ├── Resources/        # Runtime loadable assets
│   └── StreamingAssets/  # For Android raw files
├── Packages/
├── ProjectSettings/
├── Builds/
│   └── Android/
└── Docs/
    └── TechnicalSpec.md
```

## Key Conventions

- **C# only** for gameplay logic.
- All systems are event-driven where possible (OnInventoryChanged, OnQuestCompleted, etc.).
- Save data uses JSON for human-readable debugging.
- Mobile-first: virtual joystick + touch-friendly UI.
- Android build targets: IL2CPP + ARM64 recommended.
```
