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
