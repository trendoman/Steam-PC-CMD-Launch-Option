# Steam [PC]: Launch Option to CMD (Windows)
How-to start anything else beside the game itself via Steam using game's **launch option**.

## Motive

I wanted to have a local backup of a savegame folder for a game - 
- perform a backup when I start to play
- fully automated
- no extra apps


## Plan 
Game's path to exe already stored in Steam's code word `%command%`. I ask Steam to fire a command line then use that command line to start the game and whatever else I wish. The only drawback with current version is a briefly popping cmd window.

## Example
Launch a game and simultaneously start a Task in Windows' Task Scheduler (for example, zip and copy a savegame folder). I put the whole line in Game->Properties->General->Launch Option.
```
cmd /c start /min "" "%command%" & schtasks.exe -Run -TN [TLD]BackupSaves
```
Basically, whatever EXE comes after `&` will be launched as well as the game itself.
