# Astro Bot Recompiled

An unofficial research project aiming to run **Astro Bot** on PC through static
recompilation and a compatible runtime.

The project is in an early stage of development and does not currently provide
a complete or playable version of the game.

## Current Status

- The current development base is **SharpEmu 0.0.2-beta.4**.
- The project uses parts of the
  [SharpEmu](https://github.com/par274/sharpemu) source code.
- **Dreaming Sarah has been successfully launched on PC through a locally
  modified SharpEmu build.** This result validates the emulator-side changes
  and is being preserved as a reference trace.
- The separate static recompiler implementation has now started at roadmap
  step 2: inventorying Astro Bot modules, imports, and game resources.
- Earlier Vulkan, graphics, and import-execution progress was made in the
  modified SharpEmu path and should not be presented as standalone recompiler
  progress.

No game has been launched by the standalone recompiler yet. The successful
Dreaming Sarah run is an emulator reference result, not a completed
recompiler test.

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

1. Preserve the modified SharpEmu Dreaming Sarah run as a reference trace.
2. **Inventory Astro Bot modules, imports, and game resources (in progress).**
3. Generate the first minimal native recompiler output.
4. Reach the guest entry point and the first HLE call from generated code.
5. Reach stable graphics subsystem initialization.
6. Render the first real frame produced by game code.
7. Implement menu, input, and audio functionality.
8. Load the first playable level.
9. Add user settings, save data, and mod support.

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
