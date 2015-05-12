# Instructions for Windows
- (create c:/steamcmd)
- (extract  https://steamcdn-a.akamaihd.net/client/installer/steamcmd.zip)

- `cd c:/steamcmd`
- `./steamcmd.exe +login anonymous +force_install_dir cssdm_server +app_update 232330 validate +quit`


## Server plugins
(extract all to c:\steamcmd\cssdm_server\cstrike\)
- http://www.sourcemm.net/snapshots (1.10.5-git931.zip	)
- http://www.sourcemod.net/snapshots.php (1.7.2-git5195.zip	)
- http://www.bailopan.net/cssdm/snapshots/2.1/?C=M;O=D (cssdm-2.1.6-git214-windows.zip)
- http://forums.eventscripts.com/viewtopic.php?f=128&t=40765 (EventScripts Public Beta v2.1.1.379)
- http://addons.eventscripts.com/addons/view/dmendround (DM EndRound - Version 2.5) 

## Server cfg:
- copy server.cfg to c:\steamcmd\cssdm_server\cstrike\cfg
- copy cssdm.cfg to c:\steamcmd\cssdm_server\cstrike\cfg\cssdm

## map DM spawnpoints (server):
- copy de_eVision_Office_v1.txt to C:\steamcmd\cssdm_server\cstrike\cfg\cssdm\spawns\cstrike

## client cfg:
- copy autoexec.cfg to C:\Program Files (x86)\Steam\SteamApps\common\Counter-Strike Source\cstrike\cfg

## Add map to server
- copy de_eVision_Office_v1.bsp to C:\steamcmd\cssdm_server\cstrike\maps

## Starting the server: 
- `cd ./cssdm_server/`
- `./srcds.exe -console -game "cstrike" -secure +map de_eVision_Office_v1 +log on +maxplayers 16 -port 27015 +exec server.cfg`
you can now join the server by browing LAN servers

## Updating the map
If you'd like to update the map you need to
- Copy the map to the server (C:\steamcmd\cssdm_server\cstrike\maps)
- Copy the map to the client (C:\Program Files (x86)\Steam\SteamApps\common\Counter-Strike Source\cstrike\maps)
- Update mapcycle.txt with the new mapname
- Rename de_eVision_Office_v1.txt to new mapname (layout must be identical) (C:\steamcmd\cssdm_server\cstrike\cfg\cssdm\spawns\cstrike)
- Update the server launch command

## Restarting the map (shouldn't be necessary)
- Go to console (ingame) and type `rcon changelevel_next`

## Notes:
- When the player is ready, hit F6 to start a 3second countdown timer
- Scores will need to be kept track of manually 
- Each round lasts 3 minutes but is configurable in server.cfg under `dm_roundtime`
- For best performance (at least on the laptop I set up on) you should set all GFX options to the lowest possible setting
