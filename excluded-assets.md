---
layout: default
title: Excluded Assets
nav_order: 3
---

# What are Excluded Assets?

`ExcludedAssets` are assets which are excluded from your final packaged game. They have **no influence** on the Cleanup process.

This process is very helpful if you have a certain development-only assets, e.g.: `BP_PressEnterShiftWin` which you want to keep in your project/level to simplify development experience but you want them automatically remove from the final package.

# Availability

Origin                | Available | Explanation                                                    |
--------------------- | --------- | -------------------------------------------------------------- |
Clean Project Menu    | ❌        | Selected assets are required for this operation               |
Project Context Menu  | ❌        | Selected assets are required for this operation               |
Asset Context Menu    | ✅        | Blacklist **all the selected** assets                         |
Folder Context Menu   | ✅        | Blacklist **all** assets **from the selected folders**        |
Report Dialog         | ✅        | Blacklist **all the selected** assets                         |

# Marking an Asset as Excluded

To mark one or more assets as `ExcludedAssets` select the objects then right click -> Mark as Excluded.

TODO: Insert video of selecting one or more assets and right-clicking

# Marking a Folder as Excluded

To mark all the assets inside one or more folders as `ExcludedAssets` select the objects then right-click -> Mark as Excluded.

TODO: Insert video of selecting one or more folders and right-clicking