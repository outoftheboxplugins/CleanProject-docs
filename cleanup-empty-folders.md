---
layout: default
title: Cleanup empty folders
nav_order: 8
---

# What are Empty Folders?

I know this might sound straight forward but that's not the case in Unreal Engine. It's possible after moving an asset a folder will show up empty inside the editor, but on disk it will still contain files. This is happening due to [Redirectors](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/Redirectors/).

{: .note }
Running this operation will trigger a [Fixup redirectors](fix-redirectors) operation beforehand to ensure the folders are empty.

# Deleting Empty Folders

## Project Wide

To quickly fix all directors in your project, navigate the [Toolbar menu](how-to-run-commands#toolbar-menu) and start the `Cleanup redirectors` operation.

## Specific folders

Unreal provides multiple ways to fix redirectors explained [here](https://docs.unrealengine.com/4.26/en-US/ProductionPipelines/Redirectors/).

