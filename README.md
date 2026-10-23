# Aura ESP — Minecraft Java / Fabric 1.21.11

Client-only vanilla-style entity outlines. This project is source code, NOT a compiled mod JAR.

## Features

- **G**: toggle ESP on/off (default OFF).
- **H**: cycle targets: players only ↔ players + mobs.
- **J**: cycle five outline colors (Aqua, Violet, Coral, Lime, Gold).
- Vanilla glowing silhouettes show through walls for *client-loaded, renderable* entities.
- Modern semi-transparent HUD card at upper-left while enabled.
- Settings stored in `<minecraft>/config/auraesp.properties`.
- All keys can be changed in Minecraft's Controls screen.
- Does **not** send packets, reveal entities removed by a server, or change server permissions.

## Build

Requires Java 21, internet access for Gradle dependencies, and **Gradle 9.6.1**.

```
gradle build
```

The installable jar appears at `build/libs/auraesp-1.0.0.jar` (not the `-sources`/`-dev` variant).

If you don't have Gradle installed, upload this folder to your own GitHub repository
and run **Actions → Build Aura ESP → Run workflow**. Download the build artifact
from that workflow when it finishes. The included GitHub Actions workflow installs
Gradle and Java itself.

## Install

1. Install Fabric Loader for Minecraft Java **1.21.11** and Fabric API for **1.21.11**.
2. Copy the built `auraesp-1.0.0.jar` to your Minecraft installation's `mods` folder.
3. Launch 1.21.11 using the Fabric profile.
4. Press **G**. H changes highlighted entity types; J changes the glow color.

## Project layout

- `AuraEspClient.java` — keybinds, HUD and target settings
- `EntityMixin.java` — forces local glowing outline and team-color getter
- `EspSettings.java` — saves config to a properties file

**Testing note:** The source was prepared against documented 1.21.11 Mojang-mapped
APIs. It was not compiled or launched in this environment, which does not
have access to online Gradle/Minecraft dependencies. A local Gradle or GitHub
Actions build is required before installation.

Check rules of any multiplayer server before using client mods.
