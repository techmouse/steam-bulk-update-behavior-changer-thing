# steam-bulk-update-behavior-changer

## What is this?
This is a simple BASH script that changes the update behavior for all games installed in a single steamapps directory.

Easily switch the auto-update behavior of all games in a steamapps directory to `Always keep this game updated` (Steam's default), `Only update this game when I launch it`, or `High Priority - Always auto-update this game before others` in one go. Takes only seconds, makes backups before changing anything, and double checks its own results.

NOTE: It's safe to run this script on the same steamapps directory multiple times.

## How to install:
1. Save the file [steam-bulk-update-behavior-changer](https://raw.githubusercontent.com/techmouse/steam-bulk-update-behavior-changer-thing/main/steam-bulk-update-behavior-changer) to whatever directory you keep your personal scripts. (Example: $HOME/bin or ~/Scripts)
2. Give the file execution permissions. (Example: `chmod +x ~/bin/steam-bulk-update-behavior-changer`)
3. Done.

## Usage:
1. Open a terminal.
2. Type `/path/to/the/script /path/to/your/steamapps/`
3. Read the instructions on screen.

## Example:
Input:

`$ ../path/to/steam-bulk-update-behavior-changer /media/hard_drive_1/steamapps/`

Output:

```
What behavior?
0 for 'Always keep this game updated'. (Steam's default)
1 for 'Only update this game when I launch it'.
2 for 'High Priority - Always auto-update this game before others'.
```
Type `1` and press enter:
```
Processing Terraria (105600)
Processing Red Faction: Guerrilla Steam Edition (20500)
Processing Saints Row IV (206420)
Processing The Incredible Adventures of Van Helsing (215530)
Processing POSTAL 2 (223470)
Processing Fallout: New Vegas (22380)
Processing Sacred 2 Gold (225640)
Processing Cities: Skylines (255710)
Processing Wasteland 2: Director's Cut (404730)
Processing Surviving Mars (464920)
Processing Spacewar (480)
Processing Aven Colony (484900)
Processing ATOM RPG (552620)
Processing Graveyard Keeper (599140)
Processing Wasteland 3 (719040)
Processing Destroy All Humans! (803330)
Done!
16 out of 16 entries successfully changed.
Steam must be restarted before any changes will be applied.
```
Then simply restart Steam.

## To do multiple steamapps directories at once:
If you love one line commands, you can also pass the `behavior` argument to this script, to more easily change multiple steamapps directories:

`$ ../path/to/steam-bulk-update-behavior-changer /media/hard_drive_1/steamapps/ 1 && ../path/to/steam-bulk-update-behavior-changer /media/hard_drive_2/steamapps/ 0 && ../path/to/steam-bulk-update-behavior-changer /media/hard_drive_3/steamapps/ 1`

## Filtering:
You can add your own filters for any games you want ignored to the variable `filter` at the top of the script.

The proper syntax is:
`filter=("game 1 name here" "game 2 name here" "gameid here" "99999" "etc")`

There are no commas, names should be in double quotes, and they are separated by only a space. And ensure they are _exactly_ the name of the game you want ignored.

Example 1: The filter "Fallout" will not filter out the game Fallout: New Vegas.

Example 2: The filter "Fallout New Vegas" will not filter out any Fallout. Nor will it filter out the game it was intended to filter either, because the game is named "Fallout: New Vegas" and not "Fallout New Vegas".
