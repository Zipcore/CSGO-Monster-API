# CSGO Monster API
An API to create monsters, edit from [this plugin](https://forums.alliedmods.net/showpost.php?p=2416226&postcount=43).  
ONLY TESTED IN CSGO.

# Changes
- Removed all commands.
- Added some natives and forwards.
- Added attack target "ct" and "tr".

# Install
- Put `monster.smx` to your server folder.
- Upload all files in `models` and `materials` folder to both your game server and fastDL server.

# Natives
```sourcepawn
#if defined _Monster_included
 #endinput
#endif
#define _Monster_included

/**
 * Spawn a monster.
 * 
 * @param name		Name of the monster.
 * @param model		Model of the monster.
 * @param origin	Position to spawn.
 * @return monster entity index, -1 if failed to spawn a monster.
 */
native int Monster_Spawn(char [] name, char [] model, float origin[3]);

/**
 * Set attribute of a monster.
 *
 * @param name		Name of the monster.
 * @param attr		Attribute to set.
 * @param value		Value of attribute.
 * @return true on success, otherwise false.
 */
native bool Monster_Set(char [] name, char [] attr, char [] value);

/**
 * Remove a monster.
 * 
 * @param name		Name of the monster.
 * @return true on success, otherwise false.
 */
native bool Monster_Remove(char [] name);

/**
 * Clear all monster.
 * 
 * @return true on success, otherwise false.
 */
native bool Monster_Clear();

/**
 * Clear all monster.
 * 
 * @param name		Name of the monster.
 * @param origin	Position to teleport.
 * @return true on success, otherwise false.
 */
native bool Monster_Tele(char [] name, float origin[3]);

/**
 * Called when a monster break.
 *
 * @param monster     Monster entity index.
 * @param client     Client index.
 * @param weapon     Weapon.
 * @return          No return
 */
forward Action Monster_OnBreak(int monster, int client, const char [] weapon);
```
