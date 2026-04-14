===============================================================================
Q: What are "Local" and "Workshop" mods?

Workshop Mods
 - Managed by Steam Client. No external changes allowed.
 - Storage location varies on user Steam settings
 - Auto updated by Steam (only if no local changes were made to them)
 - Auto removed by Steam (only if no local changes were made to them)
 
Local Mods
 - Manual Management.
 - Stored under GameFolder/mods folder
 - Folder name must match expression ([a-zA-Z_]+)
 - Manual update
 - Manual removal

===============================================================================
Q: How to set up a mod?

* Open .pat files with 7zip or other archive tools.
* Open mod.info with text editor or other text editing tools.
* Set "name" property equal to mod folder name. Mod name must contain latin letters, digits, characters '_' or '-', whitespace only and not exceed 120 symbols length. Case insensitive.
* Set mod description in "desc" property.
* Set the oldest game version your mod is still compatible with as "minGameVersion" property value.
* Set the latest game version your mod supports as "maxGameVersion" property value. Must be greater or equal to minGameVersion.
* Set "maxGameVersion" ahead by only few version # from current game version, for example no more than 10.
* Both maxGameVersion and minGameVersion properties must be not empty and use valid "X.YYY" version pattern, otherwise mod will be marked as incompatible.
* Create patches in subsequent order to reduce download sizes "1.pat, 2.pat, 3.pat" (not required for Steam Workshop items).

===============================================================================
Q: After update my game is crasing on mods activation. What to do?
Q: After clicking "Apply" in mod options game crashed and won't start again. What to do?

* Run once game in "Safe mode (No mods)" (or use -no_mods command argument). It will disable mods initialization and you can disable mod in options.
OR
* Run once game in "Safe mode" (or use -safe command argument). It will reset all settings to safe profile.

===============================================================================
Q: How to maintain mod version?

It is advised to keep minGameVersion equal to current game version and maxGameVersion slightly ahead.

For simple mods - can extend support for up to 4 next versions:
Game Version: 0.500   Min Mod Version: 0.500   Max Mod Version: 0.504

For complex mods that are sensitive to internal changes - keep them equal:
Game Version: 0.500   Min Mod Version: 0.500   Max Mod Version: 0.500

===============================================================================
Q: Where is old "localization" folder? 

Old localization files moved to /localizations/default/interface/set/ folder. 
It must contain only "POT" - PO Template files, or old ".lng" SDL files.

===============================================================================
Q: I want to add localization to my mod.

You can add localization by creating a folder with language code in /localizations/ folder. 
Resources from it will be automatically merged into engine VFS if user has that language specified.

