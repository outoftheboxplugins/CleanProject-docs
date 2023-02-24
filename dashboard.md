---
layout: default
title: Dashboard
nav_order: 4
---

# What is the Dashboard?

The Clean Project Dashboard is a convient editor tab which highlights the cleanup state of your project.

![image](https://user-images.githubusercontent.com/21221169/221167041-b9b93d5a-0e6a-4000-b379-15a8a9e76abf.png)

# Core Assets list

This list contains all the root `Core Assets`. This include automatically added and manually marked assets and folders. ([What are Core Assets](core-assets#what-are-core-assets)).

# Unused Assets list

A list of all the assets currently considered **unused** across the whole project. ([What is considered unused](index#what-is-consider-unused)).

# Operations

Action buttons to quick launch a Cleanup operation project wide.

# Status

Whether the dashboard needs a refresh or not. If the dashboard is up to date, it will display  `Index is up to date` or `Index is NOT up to date` if a **Refresh** is needed.

For convience a refresh is automatically execute when an asset is modified on disk or when the plugin settings are changed. However, to avoid slowing down operations, refresh will be skipped if they happen too often. These can be changed inside the [settings](#settings).

![image](https://user-images.githubusercontent.com/21221169/221169509-023f225b-09a6-43e5-9ea2-a3d974ccdba2.png)

** Auto Refresh Dashboard ** - Enable or disable automatic updates. If your project is very big and changes are frequent it might be worth disabling it and manually refreshing the index.

** Auto Refresh Interval ** - Change the frequency of allowed updates. By default updates will be a skipped if a previous update was executed less than 30 seconds ago. You can increase the number to decrease updates frequency or enter a negative number to allow every change to trigger an update.

# Settings

Shortcut to quickly launch the Plugin's Project Settings section.

# Documentation

Shortcut to quickly launch the Documentation in your browser.