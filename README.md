<base target="_blank">

# Roblox-BallparkDefender

## Summary

This repo serves as the backup location for my [Roblox game Ballpark Defender](https://roblox.com/games/12117545162/Ballpark-Defender) - a Tower Defense game with a baseball theme. Mobs invade a local ballpark and you have to strategically place 10 defenders to keep the ballpark from being destroyed. 

## Technical Details

[Roblox-BallparkDefender on Github](https://github.com/prilldev/Roblox-BallparkDefender).

### Credits

Credit to Youtuber [GnomeCode](https://www.youtube.com/@GnomeCode) for his excellent [22 Video Tutorial](https://www.youtube.com/watch?v=DanjB0cTfw0&list=PLtMUa6NlF10fEF1WOeDtuGcIn0RdUNL7c) on how to build a complete Tower Defense game on Roblox. I learned almost everything in this codebase from that tutorial, and tailored it to fit my needs for this game.

### Project Structure 

The relevant items of how I have Ballpark Defender setup in Roblox Studio are listed below. I've included links where source code exists in this repo.

```
**Key:** -- = Folder | ... = Other misc items not shown
```

* **Workspace**
    * **-- GUIData**
        * #Inning (NumberValue)
        * #Message (StringValue)
    * **[-- Maps](/Workspace/Maps)**
        * [-- GrassLand](/Workspace/Maps/GrassLand)
            * -- BaseballField
            * -- DefPositions
            * -- MobPath
                * -- Waypoints (includes objects named as "1, 2, 3, etc" to "steer" the Mob around the map)
            * Ballpark
                * Head (HealthGui attached to this in code)
                * Humanoid
                * ...
            * ...
    * **-- Mobs** (empty folder that Mobs are spawned into during Gameplay)
    * **-- Squad** (empty folder that Defenders are spawned into during Gameplay)
    * ...
    * Baseplate 
    
* **[ReplicatedStorage](/ReplicatedStorage/Modules)**
    * **[-- Events](/ReplicatedStorage/Events)**
        * AnimateDefender
        * EquipDefender
        * SpawnDefender
    * **[-- Functions](/ReplicatedStorage/Events)**
        * RequestDefender
    * **[-- GUIs](/ReplicatedStorage/GUIs)**
        * HealthGui
    * **[-- Modules](/ReplicatedStorage/Modules)**
        * **[Health.lua](/ReplicatedStorage/Modules/Health.lua)** (dynamic re-usable Health bars)
    * **-- Squad** (stores all the Defender characters used by the game)
    * **-- Weapons** 
    (Each Group represents an "Upgrade Path" of Weapons. Defenders are assigned a Group)
        * **-- Group1** 
            * Slingshot (EquipOrder = 1)
            * Crossbow (EquipOrder = 2)
        * **-- Group2**
            * Black Baseball Bat (EquipOrder = 1)
            * Large Wood Bat (EquipOrder = 2)
        * **-- Group3**
            * Baseball (EquipOrder = 1)
    
* **[ServerScriptService](/ServerScriptService)**
    * **[-- Game](/ServerScriptService/Game]** (includes scripts that run immediately as game loads)
        * [Main.lua](/ServerScriptService/Game/Main.lua)
        * [PlayerAdded.lua](/ServerScriptService/Game/PlayerAdded.lua)
    * **[-- Modules](/ServerScriptService/Modules]** (module scripts referenced throughout game)
        * [Defender.lua](/ServerScriptService/Modules/Defender.lua)
        * [Mob.lua](/ServerScriptService/Modules/Mob.lua)
* **ServerStorage**
    * -- Various Backup Folders for Characters and Other items that might be needed
* **[StarterGui](/StarterGui)**
    * -- Billboards (stores all HealthGui billboards created on Mobs/Ballpark during the game)
    * **[GameController.lua](/StarterGui/GameController.lua)** (the main script that handles user interaction/input)
    * **GameGui** (all the visual frames, etc. on the screen)
        * DefendersList (Scrollable Frame: menu of Defenders on the Left)
            * TemplateButton (used to dynamically generate Defender buttons)
                * Price (Textlabel)
        * Info (Top of screen info area)
            * Health (Frame)
                * CurrentHealth (Frame)
                * MaxHealth (Frame)
                * Title
            * Stats (frame)
                * Inning (TextLabel)
                * Gold (TextLabel)
            * Message (TextLabel - display messages to user)
        
* **[StarterPlayer](/StarterPlayer)**
    * **[-- StarterPlayerScripts](/StarterPlayer/StarterPlayerScripts)**
        * [Animations.lua](/StarterPlayer/StarterPlayerScripts/Animations.lua)

---

## License

TO DO...
