# Astro Bot PC

An unofficial research project aiming to run **Astro Bot** on PC through static
recompilation and a compatible runtime.

The project is in an early stage of development and does not currently provide
a complete or playable version of the game.

## Current Status

- The current development base is **SharpEmu 0.0.2-beta.4**.
- The project uses parts of the
  [SharpEmu](https://github.com/par274/sharpemu) source code.
- **Dreaming Sarah has been successfully launched on PC** and is being kept as
  a test for the recompiler.
- Astro Bot development is currently focused on loading and processing
  graphics, textures, and other game resources.

The successful Dreaming Sarah test validates part of the chosen approach. It
does not mean that Astro Bot is currently bootable or playable.

## Project Goal

The intended execution pipeline is:

```text
eboot.bin and game modules
        |
        v
SharpEmu loader and executable analysis
        |
        v
static recompilation and native x86-64 relinking
        |
        v
PC compatibility runtime, Vulkan, and system implementations
        |
        v
locally generated AstroBot.exe
```

The project aims to preserve compatible x86-64 game code for native execution
while providing only the required PS5 API implementations, import handling,
memory management, threading, file system, graphics, audio, and input support.

## Development Areas

- Loading `eboot.bin` and related modules
- Import, NID, relocation, and TLS handling
- Native Windows executable generation
- A compatibility runtime for the PS5 APIs used by the game
- Graphics command and shader translation to Vulkan
- Texture and game resource loading
- Audio, input, save data, and file system support
- In-game graphics and control settings
- Differential tracing against SharpEmu
- Mod support without DRM

## Roadmap

1. Preserve Dreaming Sarah as a permanent regression test.
2. Complete the Astro Bot module, import, and resource inventory.
3. Reach stable graphics subsystem initialization.
4. Render the first real frame produced by game code.
5. Implement menu, input, and audio functionality.
6. Load the first playable level.
7. Add user settings, save data, and mod support.
8. Consider an Android ARM64 backend after the Windows version is stable.

## Repository State

This repository currently contains project information only. Source code,
build instructions, and technical documentation will be added when they are
ready for public development.

## Licensing

This project uses SharpEmu source code. Any derived recompiler and runtime code
must be published in compliance with SharpEmu's **GPL-2.0** license, including
the corresponding source code.

An exact `LICENSE` file, copyright notices, and a list of reused components
will be added when the source code is published.

## Legal Notice

This project is not affiliated with Sony Interactive Entertainment or the
developers of Astro Bot.

This repository will not distribute:

- Astro Bot or other game files
- Game assets, modules, or decompiled game code
- PS5 firmware dumps
- Encryption keys
- Executables containing game-derived code or data
- Links or instructions for obtaining illegal copies

Users must provide files from their own legally obtained copy of the game. All
game-specific processing is intended to happen locally on the user's computer.

Astro Bot, PlayStation, and all related trademarks and copyrighted materials
belong to their respective owners.
