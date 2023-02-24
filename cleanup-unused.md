---
layout: default
title: Cleanup Process
nav_order: 5
---

# What is the Cleanup Operation

The `Cleanup operation` (also known as `Cleanup unused`) is the process by which the plugin collects the [**unused**](index#what-is-consider-unused) from the input assets and creates a [Cleanup report](#what-is-the-cleanup-report).

## What is the Fast Cleanup

The `Fast Cleanup` is the fast version of the clenaup operation, it uses the same logic as the [Complex Cleanup](#what-is-a-complex-cleanup) but **relys on cached information to determine references between assets**.

## What is the Complex Cleanup

The `Complex Cleanup` is a more robust version of the cleanup operation, **it loads all assets into memory to ensure all asset references are up to date** but takes signafiacntly longer (especially on larger projects).

{: .note }
This version is currently disable due to engine crashes.

# What is the Cleanup report

![image](https://user-images.githubusercontent.com/21221169/221194454-c1da8523-f420-4707-aa9e-ffe104d2ba75.png)

## List actions

### Delete

Starts to **forcefully delete** all assets inside the report.

### Mark as Core

[Marks as Core](core-assets#what-are-core-assets) all assets inside the report.

### Exclude from package

[Marks as Excluded](excluded-assets#what-are-excluded-assets) all assets inside the report.

## Context actions

### Remove

Removes the selected assets from the report list, leaving it untouched.

### References

Opens the selected assets in the [Reference Viewer](https://docs.unrealengine.com/4.26/en-US/Basics/ContentBrowser/ReferenceViewer/)).

### Audit

Opens the selected assets in the [Asset Audit UI](https://docs.unrealengine.com/5.1/en-US/cooking-content-and-creating-chunks-in-unreal-engine/#assetauditwindow).

### Soft revert

Removes the selected assets from the `Mark for add` state within the current [source control](https://docs.unrealengine.com/5.0/en-US/using-source-control-in-the-unreal-editor/) by performing a soft revert (equivalent of `p4 revert -k`).

### Mark as Core

[Marks as Core](core-assets#what-are-core-assets) the selected assets.

### Exclude from package

[Marks as Excluded](excluded-assets#what-are-excluded-assets) the selected assets.

### Delete

Starts to **forcefully delete** the selected assets.