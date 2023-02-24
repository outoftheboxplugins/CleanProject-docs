---
layout: default
title: Excluded Assets
nav_order: 3
---

# What are Excluded Assets?

`ExcludedAssets` are assets which are excluded from your final packaged game. They have **no influence** on the Cleanup process.

This process is very helpful if you have a certain development-only assets, e.g.: `BP_PressEnterShiftWin` which you want to keep in your project/level to simplify development experience but you want them automatically remove from the final package.

![image](https://user-images.githubusercontent.com/21221169/221141252-68bebeb8-247b-4b0e-97c4-4ca016dbd3ad.png)

# Excluding

## Marking an Asset as Excluded

Select the assets you want to mark and use the [asset context menu](how-to-run-commands#asset-context-menu) to `Mark as Excluded`.

## Marking a Folder as Excluded

Select the folders you want to mark and use the [folder context menu](how-to-run-commands#folder-context-menu) to `Mark as Excluded`.

# View Excluded Assets

During the cooking process, the Clean Project Subsystem will log all the assets excluded from the final package:

```
[2023.02.24-09.18.58:931][531]UATHelper: Packaging (Windows): LogCleanProject: Display: Modifying content to be cooked
[2023.02.24-09.18.58:952][531]UATHelper: Packaging (Windows): LogCleanProject: Display: /Game/StarterContent/Props/SM_Chair.SM_Chair is excluded from packaging and will not be included in the final build
```

![image](https://user-images.githubusercontent.com/21221169/221143121-1ee7cf26-79a0-4a46-9d06-2ebd2e1aeb27.png)

# Removing Excluded Assets

You can view entries from `Excluded Assets` in the Settings page. Navigate to `Project Settings → Out-of-the-Box Plugins → Clean Project` and remove unwanted assets from `Assets Excluded From Package` and `Folders Excluded From Package`.

![image](https://user-images.githubusercontent.com/21221169/221143291-3d9270e5-7b35-49f9-b156-887f54a4cedb.png)