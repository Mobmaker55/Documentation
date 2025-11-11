# Running a Game with WinDurango


WinDurango works by being added to existing Xbox One game dumps. WinDurango is not an independently running piece of software.  

The process of adding WinDurango to an existing Xbox One game will add the game to your system as a
"Universal Windows Platform" (UWP) application, much like anything else you'd find on the Windows Store.


## Prerequisites


1. Windows Developer Mode is enabled in settings, see [Enable Developer Mode](/build-contrib.md#enabling-developer-mode)
2. Windows 10 (or later)
3. Install the [Windows App SDK](https://learn.microsoft.com/en-us/windows/apps/windows-app-sdk/downloads)
4. Visual Studio 2022 OR WinDbg (for debugging if needed)
  a. If using Visual Studio, make sure you select the "Desktop development with C++" workload.
6. Install [Visual C++ Redistributables](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist) (install the "Latest supported" (2017-2026), 2015, 2013, and 2012 for best results)
7. Enable the Graphics Tools optional feature in Windows (from `Settings > Apps > Optional Features` (Windows 10) or `Settings > System > Optional Features` (Windows 11))
8. The latest [release](https://github.com/WinDurango/WinDurango/releases), or [artifact](https://github.com/WinDurango/WinDurango/actions/workflows/msbuild.yml)

> **Note**: If you run into errors on the latest release, try the latest artifact. 


## Setting up a Game


You need to have an existing dump of an Xbox One game. A proper dump will have at least a "Mount" folder, and will likely have other folders.  

Inside that "Mount" folder should be the game's main exe file.
If that is not where the exe file is, find the exe file, and use that as the "Mount" folder for the rest of these instructions.

![Example Mount Folder](assets/example-mount.png)

1. Open the "Mount" folder, and the WinDurango build you downloaded above.
2. Copy the contents of the WinDurango build into the "Mount" folder.
3. Open PowerShell to this folder (Shift + Right Click, "Open PowerShell window here")
4. Run `Add-AppXPackage -Register .\\AppxManifest.xml`


Once the registration completes, look up the name of the game in Window's search bar, and you should see it. Try running the game now. 


## Troubleshooting


If the game does not work on the latest release, try the latest artifact. Same goes if you tried the artifact first to try the release instead.
If it still does not work, but it is listed to work on the [Playable Games](/playable-games.md) page, open an issue in
[GitHub](https://github.com/WinDurango/WinDurango/issues), or ask in the [Discord](https://discord.gg/mHN2BgH7MR).
