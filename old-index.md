---
layout: default
title: Leagcy docs
nav_order: 999
---

# Terms and Methodology

## Project Context

Through this first section we are going to define some core **keywords** regarding how the Clean Project works, to visualize everything better, we prepared a sample project so you can get a better grasp on what is happening. 
Let's say for example we have the following assets with the following dependencies in a project:

![7-ProjectShowcase.gif](https://bitbucket.org/repo/MrEeja9/images/6873176-7-ProjectShowcase.gif)

Asset Name            | Type                 | References                            |
--------------------- | -------------------- | ------------------------------------- |
MyLevel               | Level                | BP_MyCoolBlueprint; MyLevel_BuiltData |
MyLevel_BuiltData     | MapBuildDataRegistry | N/A                                   |
BP_MyCoolBlueprint    | Blueprint            | MySphere                              |
BP_MyNotCoolBlueprint | Blueprint            | MySphere                              |
MySphere              | Static Mesh          | MyMaterial                            |
MyMaterial            | Material             | N/A                                   |
BP_MyDebugBlueprint   | Blueprint            | MyCube                                |
MyCube                | Static Mesh          | N/A                                   |

## Cleanup Check

The Cleanup Check refers to the process performed by the clean Project where a set of assets are checked if they are a **Dependency Asset** and create a [Report Dialog](#markdown-header-report-dialog) containing all the assets considered **UNUSED**. This can be triggered by the [Cleanup unused](#markdown-header-cleanup-unused) operation.

![11-CleanupCheck.gif](https://bitbucket.org/repo/MrEeja9/images/3567333808-11-CleanupCheck.gif)

# Clean Project Dialogs

## Report Dialog

Represent the dialog window opened after a [Cleanup Check](#markdown-header-cleanup-check) is performed. It contains a list of all the assets which were found **UNUSED** and a small bit of information about the analysis.

![13-ReportDialog.gif](https://bitbucket.org/repo/MrEeja9/images/1903843838-13-ReportDialog.gif)

By selecting one or more assets and *right-clicking* or *using the buttons at the button*, we can trigger the following actions:

* **Remove** - excludes the entries from the dialog so you can operate with the rest
* **More Info** - opens the entries in Unreal's Asset Audit to gather more information
* **Whitelist** - adds the entries to the [Whitelist Assets Paths](#markdown-header-whitelist-assets-paths)
* **Blacklist** - opens the [Blacklist Dialog](#markdown-header-blacklist-dialog) with the selected entries
* **Delete** - starts the deleting process of the selected entries' assets

## Blacklist Dialog

When we perform Blacklist operation the following dialog will show up on our screen:

![15-BlacklistDialog.gif](https://bitbucket.org/repo/MrEeja9/images/3992905913-15-BlacklistDialog.gif)!

This contains the following configurable options, which can be configured further inside [Blacklist Settings](#markdown-header-blacklist-settings).

* **Platforms** - Folder where the Blacklist information will be saved
* **Configurations** - File where the Blacklist information will be saved
* **Append** - How the information should be added to the existing file 
	* Checked - Information will override the content of the existing file
	* Unchecked - Information will appended at the end of the existing file 
* **Skip next time** - The dialog will be skipped and accepted with the default values

## Clean Project Menu

The Clean Project Menu is an awesome editor window that let's you see how our Plugin has improved your project so far and how it can improve it further. This window can also be docked to your layout.

The Clean Project Menu can be opened from Window -> Clean Project Menu

![18-MenuDock.gif](https://bitbucket.org/repo/MrEeja9/images/75734050-18-MenuDock.gif)

### Menu Overview

The top part of the menu (known as the Overview) contains information regarding Spaced gained by using the tool and how many unused assets are now in your project. The menu updates automatically whenever you add, delete, rename or modify assets inside your Content folder or when you change the settings related to the Clean Project.

![16-MenuOverview.gif](https://bitbucket.org/repo/MrEeja9/images/4112662855-16-MenuOverview.gif)

### Menu Assets

The next part of the menu shows the enabled Dependency Assets. Right now we have 2 different type (Map Assets & Whitelist Assets). Each category reflects the current status from the [Whitelist Settings](#markdown-header-whitelist-settings) as well as contains a list of Package paths of the containing assets.

![19-MenuAssets.gif](https://bitbucket.org/repo/MrEeja9/images/2342354690-19-MenuAssets.gif)

### Menu Dependencies

Right below we have a Tree View which shows each entry from the above lists combined with a foldable Tree view which contains all direct dependencies.

![20-MenuDependency.gif](https://bitbucket.org/repo/MrEeja9/images/1069947682-20-MenuDependency.gif)

### Menu Buttons

Finally we have the buttons which should sever as a quick shortcut for most [Operation Types](#markdown-header-operation-types). 

![image_2021-06-13_140601.png](https://bitbucket.org/repo/MrEeja9/images/1149723909-image_2021-06-13_140601.png)

# Configuration

To take advantage of the full capabilities we highly recommend tweaking the settings of the Clean Project to the needs of your project. Now we're going to discuss each of them and how they affect the cleanup process.

![image_2021-06-12_053718.png](https://bitbucket.org/repo/MrEeja9/images/3913924816-image_2021-06-12_053718.png)

## Blacklist Settings

The goal of the Blacklist settings have is to modify the behaviour of either the Blacklist Dialog or the Blacklist Process.

![1-Blacklist-Dialog.gif](https://bitbucket.org/repo/MrEeja9/images/24651327-1-Blacklist-Dialog.gif)

### Save To Temp File

If this option is enabled it will create a temporary file *(ProjectRoot)/Saved/Blacklist.txt* where the output of the blacklist operation will be added. This will also open the newly created/updated file with your default text editor.

If this option is disabled it will create/update the actual final Blacklist files inside *(ProjectRoot)/Build/(Platform)/PakBlacklist-(Configuration).txt*. The blacklist information will override or append to the file content based on other settings or options selected inside the dialog.

### Platform Paths

This is the list of platforms we're going to create Blacklists for. If you are developing for other platforms such as: **tvOS**. The platform needs to be added inside the list. Feel free to delete any platforms you are **NOT** developing for. 

### Blacklist Files

These are the names of the actual blacklist files that will be created on disk. As presented in this [Forum Answer](https://answers.unrealengine.com/questions/479126/apkblacklist-shippingtxt-not-working.html) at the moment of writing this documentation the names of the files need to respect the format: *PakBlacklist-(Configuration).txt* (e.g.: *PakBlacklist-**Shipping**.txt*).

I recommend minimal interaction with this part of the settings, it's not expected that these settings will change anytime soon, so keeping the default is the way to go. Unless you have a configuration you are certain you won't develop/blacklist for.

### Should Append Default

This will change the default value of the **Append?** checkbox inside the blacklist dialog. In case you are rarely deleting previously blacklisted assets or want to cleanup the files, I recommend keep this **check** by default, to always append new lines to your existing files.

### Should Skip Blacklist Dialog

Takes the pain away from dealing with blacklist dialog, it's a quick way of saying: "I trust the default values of the system for everything". Enabling this will automatically run the Blacklist process with the default values ( **All Platforms**, **All Configurations**, **[Append?](#markdown-header-should-append-default)** ) instead of creating the an additional dialog.

**Note**: This has the same effect as ticking *Skip next time* inside the dialog.

## Whitelist Settings

The goal of the **Whitelist Settings** is to provide a transparent way for you to edit how the assets should be checked if they are unused.

![image_2021-06-12_060457.png](https://bitbucket.org/repo/MrEeja9/images/2128375945-image_2021-06-12_060457.png)

### Whitelist Assets Paths

This is the list with the paths of all the assets that were whitelisted by the plugin. In case you move an asset it needs to be whitelisted again. Unless you want to delete the whole list, you should not manually modify this list. New items should be added via the Whitelist dialogs([Whitelist assets](#markdown-header-whitelist-assets)).

![2-Whitelist-Delete.gif](https://bitbucket.org/repo/MrEeja9/images/674808760-2-Whitelist-Delete.gif)

### Check Whitelist References

If this option is enabled, the Cleanup process will use all each asset that is **whitelisted** as a [Dependency Asset](#markdown-header-dependency-asset). I highly recommend keeping this option **enabled**, unless you whitelisted a bunch of debug assets which you have not blacklist and you don't want them in the final packed game.

![3-Whitelist-AssetsReference.gif](https://bitbucket.org/repo/MrEeja9/images/1190761851-3-Whitelist-AssetsReference.gif)

### Check All Maps References

If this option is enabled, the Cleanup process will use all each asset that is **Level(Map)** as a [Dependency Asset](#markdown-header-dependency-asset).I highly recommend keeping this option **enabled**, unless you have a bunch of maps why you don't want to see in the final packed game.

![4-Whitelist-MapsReference.gif](https://bitbucket.org/repo/MrEeja9/images/154473340-4-Whitelist-MapsReference.gif)

## Report Settings

The goal of the Report Settings is to ease your experience in viewing reports generated by the Clean Project.

### Report Hidden Columns

By default the Clean Project 	* [Report Settings](#markdown-header-report-dialog) will report as much info as it can about the assets opened, similar to Asset Audit from Unreal's default Engine.

This means if you open only Textures inside the Analyzer, you will get a lot information related to textures (image dimensions, mipmap and many others). However if you also include a Blueprint which doesn't contain such information, the editor will all the columns that do not apply to all the asset selected. In our case, it will hide the image size and mipmap, since the newly introduced blueprint does not have them.

The purpose of the **Report Hidden Columns** is to provide a way for you to hide columns even if they are applicable. This means you can open only textures and hide the unwanted columns (image size, mipmap) if you are not interested in them. By default we added the most common columns, however if you wish to see all the information possible, you can clear all entries. We can see the difference below between default report hidden columns (left) and no report hidden columns (right).

![image_2021-06-12_120815.png](https://bitbucket.org/repo/MrEeja9/images/3642652369-image_2021-06-12_120815.png)
![image_2021-06-12_120906.png](https://bitbucket.org/repo/MrEeja9/images/2910743903-image_2021-06-12_120906.png)

Our recommendation is keep the columns hidden and even add more of them if we missed any and if you require more information about a certain object to use the **More Info** button.
