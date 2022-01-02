# Rock Paper Scissor
A Quake 2 deathmatch mod

## Gameplay
At least 3 players are required (1 on each team). One player on each team is given an energy cube. This player can be identified by the trail of sparkles surrounding them. Fragging this player will make them drop their cube for other players to pick up. If you (or your team) can gain possession of all 3 cubes, your team scores a point. When a point is scored, the cubes are immediately redistributed to their respective teams and the gameplay repeats.

The RPS logic comes into play with the teams fighting each other. The *Rock* team does normal damage to the *Scissor* team, which does normal damage to the *Paper* team. The *Paper* team however does 25% damage to the *Scissor* team which also does 25% damage to the *Rock* team. 

## Compiling
Just run `make` on Linux to build the mod.

## Server Config
The only RPS specific CVARs are:

|CVAR|default|function|
|---------------------|---------|-------------|
|`autoteams`|1|Automatically put players on a team when they join|
|`sv_maplist`||A space-separated list of maps to rotate|
|`stdlogfile`|0|How to log. 0=logging off, |
|`stdlogname`|"rps/StdLog.log"|The filename to use for logging|

Example `server.cfg`:
```
// Use nearly all default values
set hostname       "RPS Biatch!"
set maxclients     "20"
set rcon_password  "bonergarage"
set sv_maplist     "q2dm1 tltf q2rdm2 q2dm3 q2dm8 backup campcity children"
set fraglimit      "30"  // frags, not score points
set timelimit      "15"  // minutes

// weapon stay, instant items, same level, spawn farthest, quad drop
set dmflags        "16948" 
```
