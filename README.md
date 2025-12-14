# Mefy's Extended-Gametypes

Server-Side Extended-Gametypes MOD Version 1.2.2 For Medal of Honor (05-14-05)
by Mark Follett (Mefy)
mef123@geocities.com
www.planetmedalofhonor.com/mefy

## Description

This mod allows you to host seven new gametypes for the stock Medal of Honor
maps: Capture-The-Flag, Freeze-Tag, Freeze-Tag-Objective, Freeze-Tag-CTF,
Freeze-Tag-TOW, Demolition, and Freeze-Tag-Demolition. A brief description
of each gametype:

- Capture-The-Flag* (for all stock maps)
    To score a point your team must capture and bring the enemy team's
    flag to your own team's base and hold it there for 15 seconds. The
    first team to score 4 points, or the team with the most points at
    the end of the round, wins the round. The default round time is 12
    minutes.

- Freeze-Tag* (for all stock maps)
    Each team must freeze all the players from the opposing team to win
    the round. To freeze a player, simply kill them. Once frozen, a
    player can't respawn until one of their teammates melts their
    frozen body by either standing next to it for a couple seconds, or
    firing their 'melting laser' at it. This gametype was inspired by
    Darrell Bircsak's Quake 3 Freeze-Tag MOD.
    (http://www.planetquake.com/freeze/)

- Freeze-Tag-Objective* (for all Allied Assault Objective maps)
    This is a combination of Freeze-Tag and a standard Objective-Match
    game. The attacking team must either freeze the entire defending
    team or complete their objectives. The defending team must either
    freeze the entire attacking team or successfully defend their
    objectives for the entire duration of the round.

- Freeze-Tag-CTF* (for all stock maps)
    This is a Capture-The-Flag game with Freeze-Tag type respawning.
    Each team must capture the flag the most times to win the round.
    While both flags are at their own bases, Freeze Tag respawning will
    be active. Once a flag is removed from its base by the opposing
    team, then full respawning will be enabled until it is returned
    back. If a team is killed while in Freeze-Tag respawning mode, then
    the other team will have several free seconds to advance before the
    killed team will respawn.

- Freeze-Tag-TOW* (for all Spearhead and Breakthrough TOW maps)
    This is a Tug-of-War game with Freeze-Tag type respawning. Each
    team must complete its objectives to win the match like a regular
    Tug-of-War game. When an objective is captured, both teams will be
    automatically melted. If a team is killed, then the other team
    will have several free seconds to advance towards their objectives
    before the killed team respawns. Once a team's base has been
    destroyed they will lose the game if all their players are killed. 

- Demolition* (for all stock maps)
    This is similar to an objective game except both teams have a base
    to defend. The team that finds and destroys the opponent's base while
    also successfully defending their own base wins the round.

- Freeze-Tag-Demolition* (for all stock maps)
    This is Demolition mode with Freeze-Tag-Respawning. Kill the enemy
    team or destroy their base to win the round.

The rules of each gametype can be customized by setting cvars- see below for
instructions. The mod is also designed to allow modders to easily set up the
gametypes for custom maps.

This mod is a server-side mod, meaning clients do not have to download anything
to play it on your server!

## Installation

You must put the pk3 file in the correct location.

For Allied Assault, place the pk3 file in your MOHAA/main directory.
For Spearhead, place the pk3 in your MOHAA/mainta directory.
For Breakthrough, place the pk3 in your MOHAA/maintt directory.


## Hosting a Game

If the map is one of the stock dm maps (mohdm#) or Spearhead tow maps, then run
that map in Round-Based-Match mode in order to enable the new gametypes. If the
map is one of the stock objective maps (obj_team#), then run the map in
Objective mode. Running a stock dm map in Free-For-All or Team-Match modes will
make the map function as normal. For Freeze-Tag-TOW, run the map in
Tug-of-War mode.

The default gametype that will be played is Freeze-Tag for the dm maps,
Freeze-Tag-Objective for the obj maps, and Freeze-Tag-TOW for the tow maps. If
you want to activate the other gametypes for a map, you must set the cvar
"g_extgametype" to the gametype that you want to play:

  set g_extgametype ctf   // Capture-The-Flag
  set g_extgametype ft    // Freeze-Tag
  set g_extgametype ftobj // Freeze-Tag-Objective
  set g_extgametype ftctf // Freeze-Tag-CTF
  set g_extgametype fttow // Freeze-Tag-TOW
  set g_extgametype dem   // Demolition
  set g_extgametype ftdem // Freeze-Tag-Demolition

If you want to play Round-Based-Match instead of one of the new gametypes:

  set g_extgametype rbm   // Round-Based-Match

Or if you want to play Objective-Match:

  set g_extgametype obj   // Objective-Match

You can also set "g_extgametype" to the other standard gametypes:

  set g_extgametype ffa   // Free-For-All
  set g_extgametype tdm   // Team-Match
  set g_extgametype tow   // Tug-of-War
  set g_extgametype lib   // Liberation

When "g_extgametype" is set, it will override whatever you set "g_gametype" as.
For example, if "g_extgametype" is set to "ctf" and "g_gametype" is "1", it will
run Capture-The-Flag, not Free-For-All. You can unset "g_extgametype" by setting
it to "".

You can also set a map-specific cvar (g_extgametype_<mapname>) for setting the
gametype for a particular map. The mapname must not include the dm/, obj/, or
/lib prefix. For example,

  set g_extgametype_mohdm1 ctf

will activate Capture-The-Flag for Southern France. This is typically used
in a mixed gametype rotation.

## Sample Server Config Files

See the included sample server config files for examples on how to set up a
server for hosting each of the gametypes. Each gametype has an example config
associated with it:

  ctf.cfg    - Capture-The-Flag config
  ft.cfg     - Freeze-Tag config
  ftobj.cfg  - Freeze-Tag-Objective config
  ftctf.cfg  - Freeze-Tag-CTF config
  fttow.cfg  - Freeze-Tag-TOW config
  dem.cfg    - Demolition config
  ftdem.cfg  - Freeze-Tag-Demolition config

You can set up a mixed-gametype rotation by using the cvar "sv_extmaplist".
This is similar to "sv_maplist" but allows you to specify the gametype for
each map in your rotation. Read through the following examples in order to
learn how to use "sv_extmaplist".

  mixed-types-extmaplist-1.cfg - Basic example of using "sv_extmaplist"
  mixed-types-extmaplist-2.cfg - Example showing how to do an extremely long
                                 map rotation
  mixed-types-extmaplist-3.cfg - Advanced example showing different gametype
                                 settings for each entry in the rotation

Also included are example configs of the older methods for doing a mixed-
gametype rotation. It is recommended that you use "sv_extmaplist" for your
rotation instead of these since it's more powerful and simpler to use.

  mixed-types-basic.cfg - Basic Mixed Gametypes config
  mixed-types-vstr.cfg  - VSTR Mixed Gametypes config for Spearhead and
                          Breakthrough only


## Special Notes

Conflicts with MAM (Mohaa Admin Mod) and the Buzzgoodies addon for MAM:
  If you are using either of these then you must turn off the round warmup
  feature of these mods. It will automatically turn off respawning and end
  the round prematurely. If you look in the configuration files for these
  mods make sure the following cvars are set to 0:

	set map_start 0  // make sure its 0
	set g_dowarmup 0 // make sure its 0

Freeze-Tag-TOW and sv_team_spawn_interval:
  For Freeze-Tag-TOW, this mod will automatically turn off the built-in respawning
  delay feature of Spearhead and Breakthrough (sv_team_spawn_interval will be set
  to 0), since this interferes with Freeze-Tag respawning. Do not turn it back on
  while in the middle of a Freeze-Tag-TOW round or players may be able to hold up
  the round if they don't spawn into the game. If you are hosting a mixed gametype
  rotation where you want respawn delay on other maps in the rotation, you will
  need to set "sv_team_spawn_interval" back to the desired value for the specific
  map.


## Troubleshooting

If you are having trouble getting the mod to run, please read the Hosting FAQ
(www.planetmedalofhonor.com/mefy/hosting-faq.html) which addresses the common
problems. If you are running other mods (like map fix mods), they may be
conflicting with this mod. If you're still having trouble try posting a question
in the mod forums which you can find at www.planetmedalofhonor.com/mefy.


## Uninstall

Just remove the user-mefy-extgametypes... pk3 file from your server's directory.


## Gametype Customization

The rules for each gametype can be customized by using a settings cvar. The
complete list of settings cvars are as follows:

  g_ctf_settings   -- Capture-The-Flag settings
  g_ftctf_settings -- Freeze-Tag-CTF settings
  g_ft_settings    -- Freeze-Tag settings
  g_ftobj_settings -- Freeze-Tag-Objective settings
  g_fttow_settings -- Freeze-Tag-TOW settings (Spearhead and Breakthrough only)
  g_dem_settings   -- Demolition settings
  g_ftdem_settings -- Freeze-Tag-Demolition settings

There are also settings cvars for each of the builtin gametypes:

  g_ffa_settings -- Free-For-All settings
  g_tdm_settings -- Team-Match settings
  g_rbm_settings -- Round-Based-Match settings
  g_obj_settings -- Objective-Match settings
  g_tow_settings -- Tug-of-War settings (Spearhead and Breakthrough only)
  g_lib_settings -- Liberation settings (Breakthrough only)

Finally, there is a general settings cvar that you can use to control
common settings that may apply to more than one gametype, such as
timelimit or fraglimit.

  g_mef_settings -- general gametype settings

If you have the same setting in this cvar as well as a specific gametype
cvar, then the setting's value from the gametype cvar will be used.

A settings cvar must contain a list of setting names and values. Here
are some examples of how to use the settings cvars for various gametypes:

  set g_mef_settings "timelimit: 30 fraglimit: 5 mef_team_spawn_interval: 6"
  set g_ctf_settings "pointlimit: 5 returnpress: -1 returnboth: 1"
  set g_ft_settings  "meltgun: off melttime: 30 suddendeath: 0"
  set g_dem_settings "settime: 15 ticktime: 20 attacker: swap"
  set g_ffa_settings "timelimit: 15 fraglimit: 50"
  set g_tow_settings "timelimit: 40 sv_team_spawn_interval: 15"

Each setting name in the list must end in a colon (:) and be followed by
its value. The following sections describe the settings available for each
gametype.

## General settings for all gametypes

- "timelimit" (no default)
    This is a special setting that will set the "timelimit" cvar when a new map
    is loaded. Use this to have a different timelimit for each gametype. The
    timelimit cvar controls how long a map is played in minutes. If it is blank
    then the map will play until the fraglimit is hit.

- "fraglimit" (no default)
    This is a special setting that will set the "fraglimit" cvar when a new map
    is loaded. The fraglimit determines the score that a player (in FFA mode)
    or team (in all other gametypes) must reach before the next map is loaded.
    If the fraglimit cvar is blank then the map will play until the timelimit is
    hit.

    You would normally use this in a mixed gametype rotation if you are running
    FFA or TDM on some maps and CTF or FT on others. You would want fraglimit
    to be a low number (like 4) for the CTF and FT maps and a high number for
    the FFA and TDM maps (like 100).

- "roundlimit" (no default)
    This is a special setting that will set the "roundlimit" cvar when a new map
    is loaded. Use this to have a different roundlimit for each gametype. This
    controls the length of each round in any of the round-based gametypes. For
    example, in Objective-Match mode, the roundlimit is normally 5 minutes.

- "sv_team_spawn_interval" (no default)
    This is a special setting that will set the "sv_team_spawn_interval" cvar
    when a new map is loaded. Use this to control the Spearhead/Breakthrough
    wave respawning feature in TDM and TOW gametypes.

- "cvar" (no default)
    Use this setting if you want to set any other cvar when a new map is loaded.
    You should set this to the name of the cvar followed by its value. For example:

       set g_ctf_settings "cvar: sv_runspeed 900"

    would turn on ultra-high runspeed for CTF.

- "mef_team_spawn_interval" Default: 0
    This controls the respawning delay for any extended gametype that has full
    respawning (normally a Capture-The-Flag game) and works similar to the
    Spearhead and Breakthrough wave respawning feature. Set this to the
    number of seconds a player must wait after they are killed before they
    can respawn again. Set this to 0 to disable wave respawning.

- "observe" Default: "bodies"
    This setting controls how players are allowed to spectate the game while
    they are dead. The format is a list of options separated by spaces or
    commas:
      "freefloat" -- Allows players to freefloat in the map while they are
                     dead.
      "bodies"    -- Allows players to spectate their own team's frozen
                     bodies while they are dead (for Freeze-Tag gametypes).
      "builtin"   -- Enables the "built-in" spectating mode. In this mode
                     you will be able to see dead player names as red on the
                     scoreboard and gun turrets will be available in the map.
                     However, you will no longer be able to free-float while
                     spectating or be able to spectate from frozen bodies.
      "none"      -- Setting this to "none" will disable both freefloating
                     and spectating of frozen bodies.

- "mapfix" Default: 1
    This setting controls the built-in mapfix feature of this mod. Players
    will be automatically killed if they go under the map. Set it to 0 to turn
    off the map fix.

- "logevents" Default: 0
    This enables logging of gametype related events to the console. When set
    to 1 it will log any Freeze-Tag melts, CTF flag events, or bomb planting
    and defusing. This is used in conjunction with an external program to
    collect player stats.

## Freeze-Tag and Freeze-Tag-Objective Settings

These settings apply to both Freeze-Tag and Freeze-Tag-Objective.

- "suddendeath" Default: 1
    Set this to the number of minutes you want for the sudden death round.
    Once sudden death begins, players will no longer be able to respawn.
    In a Freeze-Tag game, if players are still alive after the sudden death
    round completes, the team with more players alive will win the round.
    The sudden death time is included in the round time. For example, if
    roundlimit is set to 10 and sudden death is set to 2, then there will
    be 8 minutes of normal Freeze-Tag, then 2 minutes of sudden death. Set
    this to 0 to disable sudden death.

## Generic Settings for all Freeze-Tag gametypes

These settings apply to all gametypes with Freeze-Tag respawning: Freeze-Tag,
Freeze-Tag-Objective, Freeze-Tag-CTF, Freeze-Tag-Demolition, and
Freeze-Tag-TOW.

- "melttime" Default: 20
    This setting controls the amount of time it takes to melt a player (in
    tenths of a second). This is how much time it would take to melt
    if a player was standing right next to a frozen body. If you are
    using the melting laser to melt a body, then the time will increase
    with the distance you are from the body.

- "meltradius" Default: 100
    This controls how close you must be standing to a frozen body in order
    to melt it (in map units). 

- "meltgun" Default: "on meltvis scanvis"
    This controls the behavior of the melting laser. Set it to a list of
    options as follows:
      "on"      -- Include this option to enable the melting laser.
      "meltvis" -- Makes the laser visible while melting a player.
      "scanvis" -- Makes the laser visible while scanning (not melting).
      "off"     -- Set this to "off" to disable the melting laser. Players
                   would then have to stand next to a frozen body to melt it.

- "frozenmsg" Default: "loc name bodycodes"
    This setting controls the announcements when a player is frozen. It
    accepts the following options:
      "loc"       -- Announce the location of the body when a player is
                     frozen.
      "name"      -- Announce the name of the player who was frozen.
      "force"     -- Announce when a player is frozen even if no location
                     or name is available.
      "bodycodes" -- Display all of the frozen body locations in abbreviated
                     format on the HUD in the lower left corner of the screen.
      "none"      -- Set this to "none" to disable all frozen announcements.

- "meltmsg" Default: "loc name"
    This setting controls the announcements when a player is melted. It
    accepts the following options:
      "loc"       -- Announce the location of the body when a player is
                     melted.
      "name"      -- Announce the name of the player who was melted and the
                     names of the melters.
      "force"     -- Announce when a player is melted even if no location
                     or name is available.
      "privmsg"   -- Send a private message to the player who was melted
                     showing who melted them. Also send a private message to
                     each melter showing who they melted.
      "none"      -- Set this to "none" to disable all melted announcements.

    Note that body locations will only be announced for maps that have a map
    description set up (currently all Allied Assault dm maps, obj_team1, and
    obj_team4). Also player names are only available in Breakthrough or if you
    are running Foresight v1.4.

## Capture-The-Flag and Freeze-Tag-CTF Settings

These settings apply to both Capture-The-Flag and Freeze-Tag-CTF.

- "respawn" Default: 1
    Set this to 0 in order to enable a non-respawning Capture-The-Flag
    game. While both flags are at their home bases, respawning will be
    disabled. Once a flag is captured from it's home base, then respawning
    will be enabled in order to allow that flag's team to re-capture it
    before the enemy team runs it back to score. If a team is killed while
    in non-respawning mode, the other team will have several free seconds
    in order to advance before the killed team will respawn. This setting
    has no effect on a Freeze-Tag-CTF game.

- "pointlimit" Default: 4
    This sets the number of points a team must score in order to win a
    round. If time runs out before the point limit is reached, then the
    team with the most points will be the winner. Setting this to 0 will
    allow the round to continue until time runs out, then determine a
    winner. Use the standard 'roundlimit' cvar to control the length of
    the round. The default round time is 12 minutes.

- "suddendeath" Default: 5
    If time runs out and the score is tied, a sudden death round will
    begin. The next team to score will win the round. Set this option to
    the number of minutes the sudden death round should last. If the sudden
    death round ends with the score still tied, then a 'final' sudden death
    round will occur (see below). Setting this to 0 will start a final
    sudden death round immediately.

- "fsuddendeath" Default: 2
    If time runs out in sudden death, then a final sudden death round will
    begin. This is the same as sudden death except that respawning will be
    disabled. The next team to score or kill all of the enemy team will win
    the round. Set this option to the number of minutes the final sudden
    death round should last. If the final sudden death round ends with the
    score still tied and players still alive, then the team with the most
    players alive will win the round. Setting this to 0 will disable the
    final sudden death round and force a draw immediately.

- "returnboth" Default: 0
    Set this to 1 in order to require a team to bring both flags to their
    own base in order to score a point. When set to 0, they only have to
    bring the enemy team's flag to their own base to score.

- "countdown" Default: 15
    This sets the number of seconds a team must hold the flags at their
    base in order to score a point. Setting this to 0 will cause them to
    instantly score when the flags are brought home.

    Setting this to a large value will give the opposing team a chance to
    re-capture their flag and prevent a score. The scoring team will have to
    guard their base well in order to hold off the opposing team. Set this
    to a small value to make scoring easy.

- "capturepress" Default: 20
    This sets the duration of the button press for capturing a flag from
    the enemy's base (in tenths of a second). Setting this to -1 means that
    a button press is not required- you can walk up to the flag and capture
    it immediately.

    Set this to a large value to make it difficult to capture a flag from
    an enemy team's base. A player will have to stand in front of the base
    while pressing the button and be vulnerable to attack. This allows
    snipers to guard a base. Setting to zero is not recommended-- it will
    be too easy for the opposing team to re-capture their flag and prevent
    a score.

- "returnpress" Default: 15
    This sets the duration of the button press for returning a flag to home
    base (in tenths of a second). Setting this to -1 means a button press
    is not required- simply walk up to the spot where the flag should go
    and it will attach to the base immediately.

    Set this to a large value to make it difficult to return a flag to home
    base, and keep the snipers happy.

- "drophold" Default: -1
    This sets how long a player must hold the 'use' key in order to drop a
    flag (in tenths of a second). Setting this to -1 will disable intentional
    flag dropping.

    Setting this to a value of 20 would enable flag dropping, and require a
    player to hold the use key for 2 seconds in order to drop it. This would
    allow players to intentionally hide a flag from the opposing team, or
    allow a player to hand off their flag to a teammate.

- "friendlyreturn" Default: 7
    This determines how much time (in seconds) after a player captures their
    own team's flag that it will return automatically to their own base.
    Setting this to 0 will cause the flag to immediately return home. Setting
    this to -1 means that the flag will not return home.

    Setting this to a large value means that a player needs to stay alive
    for awhile after they pick up their team's flag in order for it to return
    to home base. Disabling flag return by setting to -1 will allow a team
    to hide their own flag by having a teammate carry the flag and hide
    somewhere.

- "groundreturn" Default: 25
    This determines how much time (in seconds) after a flag sits on the ground
    that it will automatically return to its base. Setting this to 0 will
    cause the flag to immediately return home. Setting this to -1 means that
    the flag will not return home.

    Setting this to a large value will give a team the chance to recapture a
    flag and continue their progress if their flag carrier drops the flag by
    being killed. Setting this to 0 would mean that the flag carrier must stay
    alive during the entire journey back to home base. Setting to -1 is not
    recommended-- the flag could potentially be lost somewhere for the
    remainder of the round.

- "enemyreturn" Default: -1
    This determines how much time (in seconds) after a flag is captured by
    the enemy team that it will automatically return to its base. Setting this
    to -1 means that the flag will not return home.

- "dropdelay" Default: 20
    This sets the amount of time (in tenths of a second) after a flag is
    dropped that it cannot be picked up by any player. The flag will be
    semi-transparent while it is disabled.

    Set this to a large value to lengthen the amount of time players will
    fight over a flag once its dropped. Setting to 0 is not recommended
    and may make certain functions not work.

- "announce" Default: "dropped atbase"
    This setting controls the announcing of the flag positions for given
    events. The format is the list of events in which to announce the flag
    position. The possible events are:
      "captured" -- Announce the flag position when a player picks up
                    a flag. When not set, the position will be a generic
                    'Axis/Allied Player'
      "dropped"  -- Announce the flag position when the flag is on the
                    ground. When not set, the position will be 'Ground'
      "atbase"   -- Announce the flag position when the flag is at a
                    team's base. When not set, the position will be
                    'Axis/Allied Base'
      "abbr"     -- Include this option to announce the flag positions in
                    abbreviated format.
      "none"     -- Set this to "none" to disable all flag position
                    announcements.
    Note that flag positions will only be announced for maps that have a
    map description set up (currently all Allied Assault dm maps, obj_team1,
    and obj_team4). If a map doesn't have a description available then you
    will only get the generic announcements.

    Setting these options will keep the game moving forward by showing
    players where the flags are.

- "announcefreq" Default: 8
    If announcing the flag position when "captured" is enabled, this
    setting controls the frequency that the flag position is updated.
    Set to the number of seconds between updates of the flag position.
    If set to 0, then only the position at the spot of capture will be
    announced.

    Setting this to a small value will make it impossible for the flag
    carrier to hide or stay alive. Set this to a large value to give
    them a chance but not allow them to completely hide.

## Demolition and Freeze-Tag-Demolition Settings

These settings apply to both Demolition and Freeze-Tag-Demolition.

- "respawn" Default: 0 (1 for Stalingrad)
    Set this to 1 in order to enable a full respawning Demolition
    game. This setting has no effect on a Freeze-Tag-Demolition game.

- "settime" Default: 50
    Set the amount of time (in tenths of a second) it takes to plant a bomb.

- "defusetime" Default: 35
    Set the amount of time (in tenths of a second) it takes to defuse a bomb.

- "ticktime" Default: 45 (60 for Stalingrad)
    Set the amount of time (in seconds) it takes for a bomb to explode.

- "activatedelay" Default: 20
    Set the amount of time (in seconds) before the bombs become activated at
    the start of the round.

- "attacker" Default: "both"
    This determines which team will be the attacking team and which team
    will be the defending team. The possible options are:
      "both"   -- enables a standard double-objective game where both teams
                  must try to blow up the other team's base
      "allies" -- the allies must blow up the axis team's base
      "axis"   -- the axis must blow up the allied base
      "swap"   -- swaps between the axis team and allied team attacking each
                  round

- "suddendeath" Default: 1
    Set this to the number of minutes you want for the sudden death round.
    Once sudden death begins, players will no longer be able to respawn.
    If players are still alive after the sudden death round completes,
    the team with more players alive will win the round. Set this to 0 to
    disable sudden death.

- "secretbases" Default: 0
    Set this to 1 to keep a base's location hidden until its bomb is set.


## Extended-Gametypes for Custom Maps

Setting up these new gametypes for a custom map is easy. Most of the code
is placed in library files that you simply need to distribute with your
custom map. The library files are as follows:
  /global/libmef/bases.scr
  /global/libmef/bomb.scr
  /global/libmef/ctf.scr
  /global/libmef/dem.scr
  /global/libmef/ft.scr
  /global/libmef/gametypes.scr
  /global/libmef/hud.scr
  /global/libmef/mapdesc.scr
  /global/libmef/respawn.scr
  /global/libmef/spawn.scr
  /global/libmef/spectate.scr
  /global/libmef/tow.scr
  /global/libmef/util.scr

You will then need to modify your map script to initialize the new gametypes.
Use one of the stock map script files included in this map pack as a template
for your own map's script file. Also see the mod forums for a tutorial on how
to set up a map script for the new gametypes.

## Other useful cvars

g_mef_disable -- set this to 1 to disable the mod
g_cinematics_off -- set this to 1 to disable the cinematics at the end of TOW
g_mef_version -- is set to which version of the mod you are running
g_mef_currentsettings -- lists the current settings for the running gametype
g_mef_devmode -- Set this to 1 to enable the mod developer mode. This will
                 start the round immediately so you can see where the base
                 locations are for CTF or DEM. Useful if you want to tweak
                 settings or change base locations by yourself.

## Changelog

### Extended-Gametypes 1.2.2 (05/14/05):
- Freeze-Tag and Demolition: Player names are now announced in Breakthrough and also Allied Assault or Spearhead if you run Foresight v1.4.
- Added "logevents" setting to enable logging of gametype events to the console. This is used in conjunction with external programs to collect player stats.
- Freeze-Tag-CTF and non-respawning CTF: Locked spawn points in mohdm1, mohdm4, mohdm6, and mohdm7.
- Added fix to force dead players to respawn when transitioning from full respawning to Freeze-Tag or non-respawning modes.
- Freeze-Tag: Removed "ftannounce" setting and replaced it with "frozenmsg" and "meltmsg" settings for controlling frozen and melted announcements separately.
- Freeze-Tag: Added "privmsg" option to the "meltmsg" setting to enable private announcements to a player who was melted and their melters.
- Simplified map scripts. Eliminated the supported gametypes array. You can now run any gametype on any map without restriction.
- Added support for addon gametypes.

### Extended-Gametypes 1.2.1 (04/09/05):
- Freeze-Tag: Added fix to prevent players from leaving and rejoining their team to respawn earlier.
- Freeze-Tag: Added options to the "meltgun" setting to make the melting laser invisible while scanning and/or melting.
- All Gametypes: Added a mapfix that will automatically kill players who go under the map.
- Added more spawnpoints to dm/mp_bazaar_dm and dm/mohdm4 to prevent players from spawning on top of each other at the beginning of the round.
- Capture-The-Flag: Added Blackadder's CTF terminology (captured/posted/saved/returned/etc...).
- Capture-The-Flag: Player names are now announced in Breakthrough and also Allied Assault or Spearhead if you run Foresight v1.4.
- Freeze-Tag-Objective: The round continues in multiple-bomb games if the planting team is still alive and at least one bomb is set.
- Demolition: Added "secretbases" setting to make the location of a base hidden until its bomb is set.
- Demolition: Flipped the Axis and Allied base locations on the HUD to match CTF.
- Demolition: If a base has no description set, then it will be a generic "Axis/Allied Base".
- Removed the "g_(gametype)_currentsettings" cvars and replaced them with "g_mef_currentsettings". This will hold the settings for the currently running gametype.
- Capture-The-Flag: Players are no longer nuked at the end of the first sudden death round in Freeze-Tag-CTF or non-respawning CTF if no final sudden death round is present.

### Extended-Gametypes 1.2.0 (03/01/05):
- Players no longer get thrown to spectator at the beginning of the second round on a map.
- Demolition: Set up this gametype for all Spearhead and Breakthrough stock maps.
- Freeze-Tag-CTF: Removed the deeper bases for this gametype.
- Bases: Changed the description of the bases to include their general location on the map.
- Freeze-Tag: Removed the generic "Allied/Axis player frozen/melted" messages if there is no location given. Set the "hudmessages" option in the "ftannounce" setting to turn these back on.
- Changed the abbreviation for "South Gate" in Remagen from "GS" to "SG" (Thanks Sweetrobot)
- Created a new simple and powerful map rotation system using sv_extmaplist which allows you to control the gametype and settings for each map in your rotation.
- Removed all of the individual setting cvars (g_ctf_*, g_ft_*, g_dem_*, etc...) and replaced them with a single cvar for each gametype (g_ctf_settings, g_ft_settings, g_dem_settings, etc...) which holds all settings. This should reduce the possibility of server crashing due to hitting MAX_CVARS.
- Added g_ffa_settings, g_tdm_settings, g_rbm_settings, g_obj_settings, g_tow_settings, and g_lib_settings for controlling settings for the built-in gametypes.
- Added g_mef_settings which allows you to control common settings for multiple gametypes.
- Added special settings "timelimit", "fraglimit", "roundlimit", and "sv_team_spawn_interval". These will set the corresponding cvar when a new map loads for a particular gametype.
- Added special setting "cvar". This allows you to set any other cvar when a new map loads for a particular gametype.

### Extended-Gametypes 1.1.4 (11/15/04):
- Capture-The-Flag: Fixed the bug where vehicle bases would vanish.
- All gametypes: Fixed bug where you could set bombs and press buttons behind walls.
- Demolition: Set up this gametype for all Allied Assault stock maps.
- Capture-The-Flag: Added more base positions for all Allied Assault stock maps.
- Demolition: The game now announces when a team's base is destroyed.
- Freeze-Tag: Added new option to g_ft_ftannounce called "hudmessages". Not including this will disable the "Allied/Axis player frozen/melted" messages.
- Round-Based-Match: Added fix so players on opposite teams no longer spawn next to each other on mohdm1, mohdm4, mohdm6, and mohdm7 at the beginning of a round.
- Misc cvar changes:
    - Removed the g_ctf_alliedbase, g_ftctf_alliedbase, g_ctf_axisbase, and g_ftctf_axisbase cvars.

### Extended-Gametypes 1.1.3 (10/16/04):
- Capture-The-Flag: Fixed the no-bomb-ticking-sound bug.
- Demolition: The game is non-respawning as default now, except for Stalingrad which has full respawning.
- Demolition: Default tick time is 45 seconds, except for Stalingrad which remains at 60 seconds.
- Demolition: Set up this gametype for mohdm2 and mohdm3.
- Capture-The-Flag: Added more base positions for mohdm2 and mohdm3.

### Extended-Gametypes 1.1.2 (09/28/04):
- Renamed Voodoo-Dolls gametype to Demolition. Set g_extgametype to 'dem' to run it.
- Added Freeze-Tag-Demolition gametype for Stalingrad. Set g_extgametype to 'ftdem' to run it.
- Added non-respawning Demolition mode. Set 'g_dem_respawn' to 0 to enable it.
- Capture-The-Flag: Added g_ctf_enemyreturn option to make a flag return to its home base if held by the enemy for too long.
- Demolition: Added non-respawning sudden death to the end of the round. The team with less players alive at the end will be nuked.
- Demolition: After both bombs blow up, sudden death will commence.
- Demolition: Base positions and the player count now appear on the HUD.
- Demolition: Added "swap" option for g_dem_attacker: this will make it swap between axis and allies attacking each round.
- Demolition: Fixed bug that would reset the team scores if a draw occured.
- Misc cvar changes:
    - Removed the g_vd_... suite of cvars and replaced them with g_dem_... for the Demolition gametype.
    - Added g_dem_respawn for controlling respawning in Demolition.
    - Added g_dem_suddendeath for controlling sudden death in Demolition.
    - Added the g_ftdem_... suite of cvars for the Freeze-Tag-Demolition gametype.
    - Added g_ctf_enemyreturn.

### Extended-Gametypes 1.1.1 (08/15/04):
- Added Freeze-Tag-TOW gametype for all Spearhead and Breakthrough tow maps. This is now the default gametype for tow maps.
- Fixed bug in 'built-in' spectating mode where spectators at the end of the round would have to re-select their weapons at the start of the next round.
- In Spearhead and Breakthrough, frozen bodies and flags no longer fall through catwalks. (but they still do in Allied Assault, sorry)
- Wave respawning for the new gametypes is now activated with the "g_mef_team_spawn_interval" cvar instead of "sv_team_spawn_interval".
- When a bomb is set or defused, the team who did it will be announced.
- All gametypes: Extended gametypes now start when g_gametype is 5.
- Misc cvar changes:
    - Added the g_fttow_... suite of cvars for the Freeze-Tag-TOW gametype.
    - Added "g_cinematics_off" for the Spearhead TOW maps. Set this to 1 in order to disable cinematics.

### Extended-Gametypes 1.1.0 (07/22/04):
- Added Freeze-Tag-CTF gametype. Set g_extgametype to "ftctf" to start it.
- Added non-respawning CTF mode, similar to Freeze-Tag-CTF except with no respawning during the 'capture' phase of the game. Set g_ctf_respawn to 0 to enable this mode.
- Added wave respawning for CTF. Set sv_team_spawn_interval to the number of seconds a player has to wait to respawn after being killed.
- Added new 'builtin' spectating mode. In this mode, dead players will be seen as red on the scoreboard, and machine gun turrets will be available in the map. Freefloating and spectating from frozen bodies is not possible in this mode. Set g_mef_observe to "builtin" to enable this new spectating mode.
- Spearhead version now includes CTF on all maps (base selection by Kaotik).
- Capture-The-Flag: Flags now stay attached to a player while they climb ladders.
- Capture-The-Flag: Created new CTF base setup method in map scripts which is much simpler and cleaner. Map scripts using the old base setup method will still work.
- Voodoo-Dolls: Added ability to play a game with one team attacking and the other team defending. Set g_vd_attacker to "allies", "axis", or "both".
- Modern-Warfare: Fixed Freeze-Tag-Objective for obj/mw_nasiriyanight. Respawning now works properly.
- All gametypes: Extended gametypes now start on dm maps when g_gametype is 4.
- All gametypes: The player count display now shows the current respawning mode.
- Misc cvar changes:
    - Removed g_ctf_disable, g_ft_disable, g_ftobj_disable, g_vd_disable.
    - Added g_mef_disable for disabling the mod. Use this instead of the old cvars for each gametype.
    - Renamed g_ft_announce and g_ftobj_announce to g_ft_ftannounce and g_ftobj_ftannounce.
    - Removed g_ft_allowjoin and g_ftobj_allowjoin. Players will now always be able to join a game in the middle of a round.
    - Removed g_ft_observe. Use the new g_mef_observe cvar instead.
    - Added g_mef_observe for handling spectator mode options. Now recognizes the 'builtin' option for enabling the new spectating mode.
    - Added the g_ftctf_... suite of cvars for the Freeze-Tag-CTF gametype.

### Extended-Gametypes 1.0.0 (06/02/04):
- Freeze-Tag: Frozen bodies now change to purple when an enemy player is nearby.
- Added readme file and sample server configs.

### Freeze-Tag 1.1 Alpha #11 (05/12/04):
- Added map description for obj_team1.
- Freeze-Tag: Added object 'broadcasting' code which should reduce lag.
- HUD now clears properly when changing to a standard gametype and restarting.
- Freeze-Tag-Objective: Round end condition now works properly for Allied Assault Demo.
- Voodoo-Dolls: Changed to allow setup of base pairs.

### Freeze-Tag 1.1 Alpha #10 (04/27/04):
- Added map descriptions for mohdm1, mohdm3, mohdm5, and mohdm7.
- Freeze-Tag: Fixed bug in code that's supposed to keep ghosts from being thrown to spec. Players would sometimes not be able to jump the next round.
- Freeze-Tag: Frozen bodies no longer spin. Should reduce lag.
- Freeze-Tag: Tweaked the new HUD animation code to reduce lag.
- Freeze-Tag: Tweaked the laser beam to reduce lag.
- Capture-The-Flag: Added capability to define base descriptions for custom maps without a full blown map description file.
- Voodoo-Dolls: Added a team symbol above the voodoo doll's head.
- Voodoo-Dolls: Changed code to allow easier setup for other maps.

### Freeze-Tag 1.1 Alpha #9 (03/20/04):
- Freeze-Tag: Players can now join the game in the middle of a round. They will start out as frozen. To disable this feature, set g_ft_allowjoin or g_ftobj_allowjoin to 0.
- Freeze-Tag-Objective: Set up this gametype for obj/obj_team3. (Omaha Beach)
- Freeze-Tag: Players who are ghosts will no longer be thrown to spectator mode due to inactivity.
- Freeze-Tag: You can now free-look around a frozen body instead of spinning with it. (no more dizzies!)
- Freeze-Tag: Slight improvement to the HUD. The team icons will pop and the text will temporarily change color when someone is frozen or melted.
- Freeze-Tag: Tweaked laser beam to prevent it from colliding with yourself during certain player animations.

### Freeze-Tag 1.1 Alpha #8 (02/28/04):
- Freeze-Tag: Fixed bug in Spearhead and Breakthrough point awarding code that would screw up the player count and end the round prematurely.

### Freeze-Tag 1.1 Alpha #7 (02/22/04):
- Freeze-Tag: More bugfixes in multi-melt code.

### Freeze-Tag 1.1 Alpha #6 (02/21/04):
- Freeze-Tag: Fixed bug in multi-melt code that prevents a player from being melted.

### Freeze-Tag 1.1 Alpha #5 (02/17/04):
- All gametypes w/bombs: Server no longer crashes (for REAL this time!) if someone is defusing a bomb while it explodes.
- Freeze-Tag-Objective: The last minute of the round is now sudden death (no respawning). Set g_ftobj_suddendeath to change the number of minutes.
- Freeze-Tag: Round time now includes the sudden death round. (Setting roundlimit to 10 and g_ft_suddendeath to 2 will give 8 minutes of freeze tag and 2 minutes of sudden death)
- Freeze-Tag: The game will now announce when sudden death is approaching and when the team with less players will be nuked at the very end of the round.
- Freeze-Tag: Multiple players melting a body will make the melt go faster. On SH and BT versions, the point that is awarded will be divided equally between each melter.
- Freeze-Tag: Unspawned players can't use the melting gun.
- Util: Fixed version detection of Allied Assault Demo.

### Freeze-Tag 1.1 Alpha #4.1 (02/22/04):
- All gametypes w/bombs: Server no longer crashes (for REAL this time!) if someone is defusing a bomb while it explodes.

### Freeze-Tag 1.1 Alpha #4 (02/08/04):
- Added fix so players on opposite teams no longer spawn next to each other on mohdm1, mohdm4, mohdm6, and mohdm7 at the beginning of a round.
- Fixed the bug where unspawned spectators would hold up the game.
- On the first round after a new map loads, players now have a minimum of 30 seconds to join a team, regardless of what g_allowjointime is set to.
- Default round time is now 6 minutes instead of 7.
- Sudden death time is now 1 minute instead of 2.
- Put laser sounds for Spearhead back to Alpha #2 config.
- Freeze-Tag-Objective: Melting gun now doesn't fire after you set a bomb.
- Freeze-Tag-Objective: Fixed the 'mysterious death' bug after a bomb would blow up.
- Freeze-Tag-Objective: Altered the behavior to be similar to standard objective when the planting team is killed and bombs are still set.
- All gametypes w/bombs: Server no longer crashes if someone is defusing a bomb while it explodes.
- Capture-The-Flag: Teams will now spawn on the same side of the map as their bases on mohdm1, mohdm4, and mohdm7 at the beginning of a round.

### Freeze-Tag 1.1 Alpha #3 (01/15/04):
- The mod now contains all gametypes- Freeze-Tag, Capture-The-Flag, and Voodoo-Dolls, selectable with the cvar "g_extgametype".
- Set up Freeze-Tag for the Spearhead maps.
- Added new gametype, Freeze-Tag-Objective, for obj_team1, obj_team2, and obj_team4. This is an objective game with Freeze-Tag respawning.
- Freeze-Tag: Free-floating is now disabled by default.
- Freeze-Tag: Uses new set of laser beam sounds for Spearhead.
- Freeze-Tag: Fixed bug with body beam colors not changing properly.
- Freeze-Tag: Changed spectator viewpoint to make it similar to the built-in spectator mode. Also made the spectator movement smoother.
- Freeze-Tag: HUD now shows the total number of players on each team.
- Freeze-Tag: Players now are awarded a point for melting in Spearhead and Breakthrough.

### Freeze-Tag 1.1 Alpha #2 (01/02/04):
- Major structural changes- most of the gametype code is now in library files.
- Set up the gametype for all of the Allied Assault maps.
- Added the melting laser for melting frozen bodies from long distance.
- Added sudden death round. In this round respawning is disabled. If time runs out with people still alive on both teams, then the team with more players alive will win the round, or it will end in a draw if both teams have the same number of players alive.
- Removed all types of turrets from maps in order to prevent the exploit.
- Reworked the spectating code to fix the 'telefragging' bug.

### Capture-The-Flag 1.2 (11/30/03):
- Fixed bug where the flag would get stuck to a player for the rest of the round if they capture the flag at the same time as they are killed.
- Set the game to run in gametype 4 (objective) for the obj maps. This allows you to cycle through the obj maps easier and should stop players from getting thrown to spec when the round restarts in these maps.
- Added a final sudden death round that follows the standard sudden death round if the score is still tied. During this round respawning is disabled. If this round ends with no winner or players are still alive, then the game will end in a draw. Use the "g_ctf_fsuddendeath" cvar to control the length of the round.
- Added a "g_ctf_version" cvar that returns the version of ctf that is running. Intended for viewing from server browsers like Gamespy and All-Seeing-Eye.
- Added code to hide the center message at the end of the round if it's still up ('Allies/Axis score!')
- Changed Defaults:
    - Roundtime is now 12 minutes instead of 15.
    - Pointlimit is now 4 instead of 5.
    - Capturepress is now 2 seconds instead of 2.5 seconds.
    - Dropdelay is now 2 seconds instead of 3 seconds.
    - Base Locations:
        - mohdm2: moved east bldg ruins spot from the upper level to the ground in front, moved east sector spot away from the spawn point
        - mohdm4: moved the spots to the same as obj_team4: under the bridge and next to the 'chartreux' sign
        - obj_team1: moved the axis bases farther back near their spawn

### Freeze-Tag 1.1 Alpha #1 (11/17/03):
- Observers can't melt bodies.
- Removed free-floating mode to keep people from firing a mg42 or using other stuff.

### Capture-The-Flag 1.1 (11/15/03):
- Major structural changes- most of the gametype code is now in library files.
- Set up the gametype for all Allied Assault stock maps.
- You now have to press a button on the flag base to release a flag.

### Capture-The-Flag 1.0 (10/18/03):
- Initial release, for Stalingrad only

### Freeze-Tag 1.0 (10/05/03):
- Initial release, for Stalingrad only

### Voodoo-Dolls 1.1 (09/08/03):
- New rule: If, after the first bomb blows, the other bomb is still set, then the match continues until that bomb explodes or is defused. If it is defused, then the defusing team will win the round. If it explodes, then the round will end with a draw. The team that blew the first bomb will also have 7 seconds added to their own bomb's time.
- The round will continue when time runs out if any bombs are still set.
- At the start of a round, the bombs will not be settable for 20 seconds.
- When a team's bomb explodes, all players on that team explode with it, no matter where they are on the map.
- Added bomb meters on the player's hud to show how much time is left for each team's bomb.

### Voodoo-Dolls 1.0 (08/16/03):
- Initial release, for Stalingrad only