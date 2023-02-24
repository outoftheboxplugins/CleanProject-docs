---
layout: default
title: Core Assets
nav_order: 2
---

# What are Core Assets?

`Core Assets` are assets considered essential to your project. They and their references will be protected from the cleanup process. We will automatically determine the assets required by your packaged game but you can manually mark an asset or a folder.

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

# Manually Marking

## Marking an Asset as Core

Select the assets you want to mark and use the [asset context menu](how-to-run-commands#asset-context-menu) to `Mark as Core`.

## Marking a Folder as Core

Select the folders you want to mark and use the [folder context menu](how-to-run-commands#folder-context-menu) to `Mark as Core`.

# View Core Assets

You can view all the root `Core Assets` inside the [Clean Project Dashboard](how-to-run-commands#dashboard-tab).

![image](https://user-images.githubusercontent.com/21221169/221132010-08aebccc-a89c-4cd7-8491-1845028524d8.png)

# Removing Core Assets

You can view entries from `Core Assets` in the Settings page. Navigate to `Project Settings → Out-of-the-Box Plugins → Clean Project` and remove unwanted assets from `Core Assets` and `Core Folders`.

![image](https://user-images.githubusercontent.com/21221169/221131128-94b59466-ae99-41af-884c-b9b3625688ef.png)