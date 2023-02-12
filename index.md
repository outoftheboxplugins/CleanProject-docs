---
layout: default
title: Getting started
nav_order: 0
---

# What is consider unused?

{: .important }
Before you run this tool in your project, please make sure you have a backup of your project.

The basic idea behind our algorithm is to build a list of `Core Assets` (the essential assets to your project) and determine all their refereneces recursively. The result are the assets we consider **in-use**.

Finally we loop thorugh all the assets in the project. If they are not part of the **in-use** list, we consider it **unused**.

# Preparing your project

We will automatically determine what assets are important to yor project using (TODO:Insert link). If there are other assets we should be aware of you can manually mark them as (TODO: Insert link).

# Glance over the current state

If you want to get an overview of what the state of your project is, use the (TODO: Insert link). This will display what `Core Assets` the algorithm is using and what assets are currently considered **unused**.

# Project wide cleanup

Once you are happy with the evaluation you can run the Cleanup operation project wide (TODO: Insert link) or targeting a specific folder (TODO: Insert link) or asset selection (TODO: insert link).