# Kyzn Game Studio — Cara Build ke APK Android

Karena Kyzn Game Studio adalah **engine editor** (mirip Roblox Studio / Unity Editor), versi APK yang dimaksud biasanya adalah:

1. **Sample Game** yang dibuat dengan sistem Kyzn (paling masuk akal untuk demo)
2. Atau **runtime player** yang menjalankan game hasil export dari studio

Di bawah ini adalah panduan lengkap untuk menghasilkan **APK yang bisa diinstall di HP Android**.

---

## Opsi 1: Build Sample Game dengan Unity (Recommended)

### Prasyarat
- Unity 2022.3 LTS atau 6000.x (Unity 6) — download di https://unity.com/download
- Android Build Support module (saat install Unity, centang **Android Build Support** + **Android SDK & NDK Tools** + **OpenJDK**)
- Minimal Android API Level 24 (Android 7.0)

### Langkah-langkah

1. **Buat Project Baru**
   - Buka Unity Hub → New Project → 3D (URP) atau 3D Core
   - Nama project: `KyznSampleGame`

2. **Import Script Kyzn**
   - Copy semua folder `Scripts/` dan `Systems/` dari package ini ke dalam folder `Assets/Scripts/` di project Unity kamu
   - Struktur yang disarankan:
     ```
     Assets/
     ├── Scripts/
     │   ├── Player/
     │   │   └── PlayerController.cs
     │   └── Systems/
     │       ├── InventorySystem.cs
     │       ├── QuestManager.cs
     │       ├── EconomySystem.cs
     │       ├── SaveLoadSystem.cs
     │       └── NPCController.cs
     ├── Prefabs/
     ├── Scenes/
     └── Materials/
     ```

3. **Setup Scene Dasar**
   - Buat scene baru: `Assets/Scenes/GameWorld.unity`
   - Tambah Plane sebagai ground
   - Buat empty GameObject → rename `Player`
     - Add Component: `Character Controller` atau `Rigidbody` + Capsule Collider
     - Add Component: `PlayerController`
     - Buat child empty `GroundCheck` di kaki player, assign ke field Ground Check
   - Buat empty `GameSystems`
     - Add: `InventorySystem`, `QuestManager`, `EconomySystem`, `SaveLoadSystem`

4. **Setup Input (Mobile Friendly)**
   - Edit → Project Settings → Input Manager (atau pakai Input System package)
   - Untuk mobile: gunakan Virtual Joystick (bisa pakai asset gratis di Asset Store: "Joystick Pack" atau buat sendiri dengan UI Image + EventTrigger)

5. **Build Settings untuk Android**
   - File → Build Settings
   - Platform: **Android** → Switch Platform
   - Player Settings (tombol di bawah):
     - Company Name: `KyznStudio`
     - Product Name: `Kyzn Sample Game`
     - Package Name: `com.kyzn.samplegame`
     - Minimum API Level: **Android 7.0 (API 24)**
     - Target API Level: Automatic
     - Scripting Backend: **IL2CPP**
     - Target Architectures: centang **ARM64** (penting!)
     - Graphics APIs: Vulkan + OpenGLES3
   - Di Build Settings:
     - Texture Compression: ASTC (recommended) atau ETC2
     - Build App Bundle (Google Play) → centang jika mau AAB

6. **Build APK**
   - Klik **Build** (atau Build And Run jika HP terhubung via USB + USB Debugging aktif)
   - Pilih folder output, misalnya `Builds/Android/`
   - Tunggu proses compile (pertama kali bisa 5–15 menit)

7. **Install ke HP**
   - Copy file `.apk` ke HP
   - Aktifkan “Install from unknown sources”
   - Atau pakai `adb install path/to/your.apk`

---

## Opsi 2: Build Langsung dari Command Line (Advanced)

Jika sudah punya Unity project:

```bash
# Contoh (ganti path sesuai instalasi Unity kamu)
"/Applications/Unity/Hub/Editor/2022.3.XX/Unity.app/Contents/MacOS/Unity" \
  -quit -batchmode -projectPath "/path/to/KyznSampleGame" \
  -executeMethod BuildScript.BuildAndroid \
  -logFile build.log
```

Buat script C# `Assets/Editor/BuildScript.cs` untuk otomatisasi.

---

## Catatan Penting

| Item                    | Rekomendasi                          |
|-------------------------|--------------------------------------|
| Scripting Backend       | IL2CPP                               |
| Architecture            | ARM64 only (lebih kecil & cepat)     |
| Min API                 | 24+                                  |
| Keystore (Release)      | Wajib buat sendiri untuk Play Store  |
| App Bundle (AAB)        | Ya, untuk upload ke Google Play      |
| Development Build       | Centang saat testing                 |

---

## File yang Sudah Disiapkan di Package Ini

- `PlayerController.cs` — movement + jump + interaction
- `InventorySystem.cs` — inventory lengkap + weight + events
- `QuestManager.cs` — quest system + objectives + rewards
- `EconomySystem.cs` — currency / gold system
- `SaveLoadSystem.cs` — multi-slot save/load JSON
- `NPCController.cs` — basic NPC patrol + interact
- `PROJECT_STRUCTURE.md` — struktur folder resmi
- PowerPoint Technical Design Document

---

## Next Steps yang Bisa Kamu Minta

- Saya buatkan **BuildScript.cs** otomatis
- Saya buatkan **Virtual Joystick** sederhana (UI script)
- Saya buatkan **sample scene** lengkap (prefab player, NPC, item)
- Saya buatkan **AndroidManifest** custom + permission list
- Atau fokusat tutorial video step-by-step (deskripsi)

Langsung bilang mau yang mana! 

— Kyzn Studio
