---
layout: default
title: Core Assets
nav_order: 1
---

# What are Core Assets?

`Core Assets` are assets considered essential to your project. They and their references will be protected from the cleanup process. We will automatically determine the assets required by your packaged game (TODO: Insert link) but you can manually mark a folder (TODO: Insert link) or asset (TODO: Insert link) as such.

# Automatically picked up

Right now, the algorithm marks the following assets as `Core Assets`:
- all assets which are inside a `DirectoriesToAlwaysCook` (recursively)
- all maps inside the `MapsToCook` section
- all default objects:
    - `GameDefaultMap` - map loaded on startup by the client
    - `ServerDefaultMap` - map loaded on startup by the server
    - `GlobalDefaultGameMode` - GameMode used by the client if none was explicity set on the world
    - `GlobalDefaultServerGameMode` - GameMode used by the server if none was explicity set on the world
    - `GameInstance` - Manager spawned on both client & server to manage the running game

# Marking an Asset as Core

To mark one or more assets as `CoreAssets` select the objects then right click -> Mark as Core.

TODO: Insert video of selecting one or more assets and right-clicking

# Marking a Folder as Core

To mark all the assets inside one or more folders as `CoreAssets` select the objects then right-click -> Mark as Core.

TODO: Insert video of selecting one or more folders and right-clicking