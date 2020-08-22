# Port Forwarding

The ports you need to have open are:

* UDP 27016 - Steam server query
* UDP/TCP 7777 - Dead Matter 1
* UDP/TCP 7778 - Dead Matter 2

# Common Issues

* Currently due to a bug, you must log into a Steam client that owns a copy of Dead Matter at least once in order to start the dedicated server. You can log out after logging into the client once. It is not confirmed if you can restart the machine after logging out and reboot the server without having to log back into a client.

# Server Config

The server configuration can be changed via editing the config `.ini` files located in `[ServerInstallDirectory]/deadmatter/Saved/Config/WindowsServer`. The file, section, and variable to change depends on the variable being modified.

If not otherwise specified, the file to modify is `Game.ini`.

## Example

If we are modifying `Game.ini`,

```
[/Script/DeadMatter.SurvivalBaseGameState]
ServerName=My Server
```

The above snippet will cause the server name to be displayed as "My Server".

## Config Reference

### `[URL]` (Engine.ini)

`Port=7777`
Change the server's port.

### `[/Script/Engine.GameSession]`

`MaxPlayers=36`
Maximum player count for the server.

### `[/Script/DeadMatter.SurvivalBaseGameState]`

```
+Admins=Abc
+Admins=Def
+Admins=Ghi
```
List of SteamIDs to mark with admin abilities. Suggested to be used for normal server moderators who do not need access to operational server functionality.

```
+SuperAdmins=Abc
+SuperAdmins=Def
+SuperAdmins=Ghi
```
List of SteamIDs to mark with admin abilities. Suggested to be used for server owners and advanced moderators who will need access to operation server functionality such as server restarts.

`ServerName=My Server`
Server name. Has a soft limit of 255 characters due to Steam server limitations.

`Password=`
Server password. Has a soft limit of 255 characters due to Steam server limitations.

```
+ServerTags="Abc:1"
+ServerTags="Def:Test"
+ServerTags="Ghi:Whatever"
```
List of server tags for Steam - eg. 'Roleplay,' 'Hardcore,' 'PvP,' etc.

`MOTD=Welcome to the server.`
Server's MOTD, displayed in character creation.

`MaxPlayerClaims=3`
Maximum claims per group or player.

`Seed=0`
Server random seed. Not used much.

`bFirstPersonOnly=false`
If the server forces first person only. For gameplay reasons, this has no effect.

`bVACSecure=false`
Whether or not to turn on VAC and EAC.

`bIsHardcore=false`
Whether or not to turn on hardcore mode.

`MaxZombieCount=2048`
The absolute hard-cap for zombie NPCs. If this many zombies are on the server, no more will be allowed to spawn.

`MaxAnimalCount=100`
Above, for animal NPCs.

`MaxBanditCount=256`
Above, for non-safezone human NPCs.

`PVP=true`
Toggles whether or not PVP is enabled. If this is false, no damage can be inflicted by one player on another.

`FallDamageMultiplier=1.0`
Change how much damage falling does here. 1.0 is full damage, 0 is no damage at all.

### `[/Script/DeadMatter.SurvivalBaseGamemode]`

`WhitelistActive=false`
If the server whitelist is enabled.

```
+Whitelist=Abc
+Whitelist=Def
+Whitelist=Ghi
```
List of SteamIDs to be allowed on the server if `WhitelistActive` is true.

### `[/Script/DeadMatter.FlockSpawner]`

`AnimalSpawnMultiplier=1.0`
How many more animals to spawn than usual.

### `[/Script/DeadMatter.GlobalAISpawner]`

`ZombieSpawnMultiplier=1.0`
How many more zombies to spawn than usual.

### `[/Script/DeadMatter.Agenda]`

`Timescale=5.5`
The timescale, relative to real time. The default value of 5.5 indicates that one real-life second is 5.5 seconds ingame.

### `[/Script/DeadMatter.ZombiePawn]`

`AttackMultiplier=1.0`
How strongly the zombies do damage. Set to zero to disable.
`DefenseMultiplier=1.0`
How much the zombies soak up hits. Set to zero to make them made of paper.
