---
layout: default
title: Cleanup empty folders
nav_order: 8
---

# What are Empty Folders?

I know this might sound straight forward but that's not the case in Unreal Engine. It's possible after moving an asset a folder will show up empty inside the editor, but on disk it will still contain files. This is happening due to [Redirectors](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/Redirectors/).

{: .note }
Running this operation will trigger a [Fixup redirectors](fix-redirectors) operation beforehand to ensure the folders are empty.

![image](https://user-images.githubusercontent.com/21221169/221152423-66b2b785-42e9-40e3-8731-f01f2a5b1060.png)

# Deleting Empty Folders

## Project Wide

To quickly fix all empty folders in your project, navigate the [Toolbar menu](how-to-run-commands#toolbar-menu) and start the `Cleanup empty folders` operation.

## Specific folders

Select the folders you want to clean up and use the [folder context menu](how-to-run-commands#folder-context-menu) to `Cleanup empty folders`.