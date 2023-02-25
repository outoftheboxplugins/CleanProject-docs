---
layout: default
title: Getting started
nav_order: 0
---

# What is consider unused?

{: .important }
Before you run this tool in your project, please make sure you have a backup of your project.

The basic idea behind our algorithm is to build a list of [Core Assets](core-assets#what-are-core-assets) (the essential assets to your project) and including all their refereneces recursively. The result are the assets we consider **in-use**.

Finally we loop thorugh all the assets in the project. If they are not part of the **in-use** list, we consider it **unused**.

# Preparing your project

We will automatically determine what assets are important to yor project using ([see more](core-assets#automatically-picked-up)). If there are other assets we should be aware of you can manually mark them ([see more](core-assets#manually-marking)).

# Starting out

If you want to quickly get an overview of the state of your project before, open up the [Dashboard](how-to-run-commands#dashboard-tab).

If you want to start cleaning up directly, use the [Toolbar Menu](how-to-run-commands#toolbar-menu) to initiate a project wide [Cleanup Operation](cleanup-unused).