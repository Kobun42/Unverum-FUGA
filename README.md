# Unverum-FUGA
Unverum-FUGA is an unofficial branch of the Unverum Mod Manager. It is a tool that allows gamers to download, install, and manage mods for several Unreal Engine 4 anime games. 

## Supported Games
- Dragon Ball FIghterZ
- My Hero One's Justice 2
- Granblue Fantasy: Versus
- Guilty Gear -Strive
- Jump Force
- Kingdom Hearts III
- FUGA: Melodies of Steel (戦場のフーガ)

## Before Starting
If your game already contains mods, it would be best practice to move them into the Mods folder for the specific game, accessed by pressing the Open Mods Folder button.  Separate mods by folder.  The mods list is generated by taking those folder names. Make sure you do this since when you get to the building process, the ~mods folder will be erased.

## Getting Started
### Prerequisites
When you first open the exe, you'll get a message saying to install .NET 5 Runtime if you don't already have it installed. Please do so if that's the case.

### Setup
Next thing you want to do is choose the game that you wish to mod from the dropdown menu, then click the Setup button.  From there you would just have to select the specific game exe that it's asking for.  Once you do that, Unverum will handle the rest and let you know when setup is completed.

### Installing Mods
Before you can manage and load some mods, you have to install some.

There are 3 methods of doing this:
1. Using the built in Mod Browser tab to download mods found on GameBanana
2. Using 1-click install buttons (once they're added in) from browsing mods directly from the GameBanana website
3. Downloading mods from other websites such as Nexus or VideoGameMods and extracting them straight into your mods folder which you can access by pressing the Open Mods Folder button

### Managing Mods
Managing mods is as simple as dragging the order of the rows to prioritize the top and enabling which mods you want in the build. Once you have your desired loadout, make sure to click the Build button. After building is completed, you can finally press Launch.

WARNING: Every time you click build, Unverum deletes everything from the ~mods directory so make sure to backup or move any projects or mods you have in there before setting up Unverum.

### Auto Updates
Unverum also supports auto updates for mods downloaded from GameBanana using the built-in browser or the 1-click install buttons. Click the Check for Updates button for Unverum to check if any are available for the currently selected game.

Self updates for Unverum are also supported so you don't need to keep checking back here to see if you have the latest version. These are checked everytime on launch.

## Game Specific Functionalities
###Dragon Ball FighterZ
Included in the Unverum download is Lean's materials that some DBFZ mods utilize. It would be best to keep that as the highest priority as enabled. Note that the Costume Patcher mod is integrated with Unverum. On setup, the exe is patched and the placeholder costume files are always placed as the lowest priority on build.

### My Hero One's Justice 2
Only implemented with My Hero One's Justice 2 is the option to undo the setup by clicking the Setup button again.  This will rename the pak and sig files so that mods can no longer be used.

## Text Patching
As of v1.2.0, Unverum now supports modularly patching specific parts of REDAsset.uexp/uasset which contains all the text for Dragon Ball FighterZ, Guilty Gear -STRIVE-, and Granblue Fantasy: Versus.  Unverum looks for a text.json in each mod folder. 

An example of how it's setup would be:
```
{
  "Entries": [
    {
      "header": "CHARA_NAME_L_HTN",
      "text": "Pepsiman"
    },
    {
      "header": "CHARA_NAME_S_HTN",
      "text": "Pepsiman"
    },
    {
      "header": "CHARA_NAME_DEMO_HTN",
      "text": "Pepsiman"
    }
  ]
}
```
This example replaces each instance of Hit with Pepsiman in the game DBFZ.

You can put as many entries as you want.  The headers can be found in the hex of REDAsset.uexp which are followed by the text that goes with it.  You would want to put the header of the part you would want to replace.  The text property is what you would want to replace the text that goes with the header specified.

Note that for each game update, Unverum would have to update the base files used to match the current version of the game.  If you're tech savvy enough, you can manually replace the files found under the Resources folder if I take too long.

## FAQ
### Are music/splash/movie mods supported?
Yes. It'll look for .awb, .mp4, .bmp, .uasset, and .usm files to replace within the Content folder.  The files will be replaced only if they have the exact same name.

### Is this safe? My antivirus is getting set off.
Yes this application is safe. Antivirus tends to trigger false alarms, especially due to it needing to be connected to the internet in order to be compatible with 1-click installations. You can check out the source code for yourself if your suspicious of anything as well.

### Why won’t Unverum open?
I made it so only one instance is running at a time so if it’s already running, the app won’t open. Check to see if you can end the process in task manager or even restart your pc if you don’t know how to do that. 

### Why doesn't Unverum have permissions to copy over files?
Try running as administrator or checking to see if any antivirus is preventing the application from operating on files.

### Why aren't my mods showing up after checking them?
Please make sure you pressed build after selecting your loadout and before launching the game.
