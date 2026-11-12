# Changelog

## v1.2.4 (2026-11-13)

- The package is now UTDuel_v124: update ServerPackages and the game type; the HUD settings have moved to [UTDuel_v124.HudDuel], and the server settings to [UTDuel_v124.DuelGame]
- Connection loss: the game is paused after 10 seconds of silence (previously 5)
- Reconnecting after a connection loss: the match no longer resumes automatically upon reconnection. The returning player can resume the match with the Pause key ("Press Pause to continue" under the timer), and can reconnect again if their connection is still unstable. If the returning player does not resume the match manually, it resumes automatically when the remaining pause time expires. The opponent cannot resume the match. If both players lose their connection during the same pause, the player who disconnected first can resume the match once both players have returned
- Fixed the overtime timer: it now counts up instead of staying at 0:00; UTComp's timed overtime retains its original display
- Challenger Picks the Map (a server setting, off by default): each player in the queue picks the map for their next duel (ESC - Pick Map, at any time) from the server's map voting list; the winner who stays has no say. Added a favourite maps tab (star icon). On the score screen, if the next challenger has picked a different map, any UTComp map or game type vote is cancelled. UTComp's Restart vote remains available
- ESC - Duel Settings (admin): Challenger Picks the Map, Restart Map After Match, End Match When a Player Leaves; server settings are now arranged in two columns
- ESC: the Players and Queue sections now share the available space equally (both players fit on screen at low resolutions such as 1024x768); added a "<--- you" indicator next to your entry in the queue
- Spectator: added a new Below (Meters) layout (presets plain-meters, portraits-meters): health and shield are displayed as meters divided into 25-point segments, using stock HUD icons; with portraits, the values are shown next to the meters (DuelMeters)
- DuelHP without an argument now cycles through the layouts available in the Duel HUD window (old unused presets have been removed)
- Fixed nickname sizes at 1440p and 4K resolutions
- Fixed a bug that prevented spectators from switching between players' POVs
- ESC: button rows are now centred
- Localisation: menus, HUD text and server messages are now stored in UTDuel_v124.int; each player sees them in their own game language (the server sends the message, and the client displays the localised text). Russian included (UTDuel_v124.rut). Information for translators can be found in the "LOCALISATION" section above
- The release archive now includes UTDuel_v124.u.uz2 for redirect servers (in the Redirect folder)
- With UTComp: fixed a bug where, with "Restart Map After Match" enabled, duelists spawned without their full warm-up weapon loadout on their first respawn

## v1.2.3 (2026-11-05)

- The package is now UTDuel_v123: update ServerPackages and the game type; the HUD settings moved to [UTDuel_v123.HudDuel], the server settings to [UTDuel_v123.DuelGame]
- Grenades with UTComp: UTComp decides them (its NumGrenadesOnSpawn setting, ?GrenadesOnSpawn, its voting); its warm-up keeps its full grenade ammo instead of 1. Without UTComp: 1 grenade, or ?GrenadesOnSpawn=N

## v1.2.2 (2026-11-02)

- The package is now UTDuel_v122: update ServerPackages and the game type; the HUD settings moved to [UTDuel_v122.HudDuel], the server settings to [UTDuel_v122.DuelGame]
- Offline: going to spectate or joining from the ESC menu no longer pauses the game
- Top panel with UTComp coloured nicks on (DuelColoredNames 1): the nicks are drawn with the mod's own copy of the Eurostile font, so they look the same in a localized game; black letters get a shadow in the colour of the player's side and stay readable on the dark plate, with a transparent HUD too

## v1.2.1 (2026-11-01)

- The package is now UTDuel_v121: update ServerPackages and the game type; the HUD settings moved to [UTDuel_v121.HudDuel], the server settings to [UTDuel_v121.DuelGame]
- The game type is listed as just "Duel" (no version in the name, so stats sites keep it as one mode)
- A player who closes the game in a pause (Disconnect, the menu) keeps his slot like after a connection loss, no forfeit
- A dropped player gets back his health, shield, weapons and ammo more reliably, and his speed too; he is put in his old place during the countdown; his body is removed; leaving no longer costs a point or a death
- Both players left in the same pause: both keep their slots, one countdown for both ("Both players are back"); whoever comes back first is put in his old place at once
- Whoever leaves in a pause gets the full connection-loss time; if nobody comes back the match ends with no winner and the queue plays next
- One who was dead when the pause began comes back as after a death
- Pause sounds: a connection loss and a player's pause each have their own
- A player's pause cannot be ended in its first 3 seconds (an accidental double press no longer wastes it)
- Pause System: a switch for all the pauses (rules, WebAdmin, admin window); off - no player pauses and no pause on connection loss
- Offline (with bots) the Pause key is the plain pause: no limits, no countdown
- The queue part of the ESC menu is updated at once, in a pause too
- Score screen: a message when a player leaves the server or goes to spectate
- Duel HUD window: "Hide Spectators' Chat on Screen" and "Hide Players' Chat on Screen" (your own lines stay; the hidden ones are still in the chat window F2 and the console)
- By default the player's top panel has no portraits, the spectator's has them

## v1.2 (2026-10-31)

- The package is now UTDuel_v12: update ServerPackages and the game type; the HUD settings moved to [UTDuel_v12.HudDuel]
- The Duel HUD window (ESC - Duel HUD, or DuelMenu): the stock panel while playing, portraits for playing and for spectating, nick colours (default / UTComp coloured nicks / UTComp model colours), the spectator's health layout; playing and spectating keep their own settings. For an admin it is "Duel Settings" with the server settings
- Spectator: the panel behind the watched player is lit in his colour (DuelGlow); a new spectator starts on a duelist in first person, and again at every match start
- Portraits: cropped to the face per character; a thin line over the head at some resolutions is gone
- Duel queue (Queue System, on by default), the next match on the same map without reloading (Restart Map After Match), a forfeit for leaving or spectating in the match (End Match When a Player Leaves), List as Deathmatch; "Spectate" on the score screen takes effect at the next match; a bot gives its slot to a human at once
- Score screen: the result and "Next Duel: A vs B" take turns; a player who joins on the score screen plays the next match (he used to become a spectator); one who comes back on it gets his line of the match back
- Announcer: "New round in" and a 10..1 countdown before the next match on the same map; "Flawless victory" / "Humiliating defeat" for a win with 10+ frags and no deaths (not after a forfeit); the result and the overtime sound were silent after a restart without reloading
- Pauses: a player's pause (Pause key / DuelPause / !pause), the admin's pause, "PAUSED by <name>" with its timer
- Connection loss: the technical pause, the slot kept, everything given back on the return, a forfeit if not back in time
- The match clock of every client is kept in step with the server (it drifted, in the overtime too)
- The queue button cannot be used to flood the chat; Join Queue / Leave Queue keep the ESC menu open
- The settings are written to the server's ini at its first start; admin command mutate duelrestart [on | off]

## v1.1 (2026-10-24)

- New spectator layouts: health / shield in a row above the score line (preset portraits-above; DuelHP above) and in a row under the score line with portraits (portraits-below; DuelHP below); DuelHP without an argument now cycles through the layouts
- With UTComp on the server the crosshair follows the Crosshair Factory settings of UTComp; its changes are picked up within a tenth of a second
- The bottom HUD takes the side colour: a spectator sees the colour of the watched player (left blue, right red), a player sees blue (DuelTint 0 - the player keeps his own HUD colour). A spectator's tint cannot be switched off: the custom HUD colour of the game settings does not apply while watching a duel
- Shorter command names: DuelPortraits, DuelHP, DuelDefault, DuelTint (the 'Hud' is dropped); the old names DuelHudPortraits, DuelHudHP, DuelHudDefault still work
- DuelHP list shows the layouts of the health / shield rows and the current one
- New spectator layout without portraits: health / shield in one row after the nicks, outside, both rows read left to right (preset plain-line; DuelHP line)
- The look without portraits has its own settings (Plain*): bigger score digits, the nicks centred on the panel height; the two looks no longer share any setting
- Double Damage is off by default in the mode (a small built-in mutator removes its pickups); the 'Double Damage' checkbox in the game rules (also in WebAdmin) or ?DoubleDamage=true turns it on, with UTComp running and no such option the choice is left to UTComp
- New command DuelColoredNames: the top panel shows the UTComp coloured nicks (the HUD player's own setting; off by default); an all-white or unpainted nick keeps the usual blue / red; the 'now viewing' line is not painted
- Fix: the style name (DuelStyle) now follows the layout changed with DuelHP
- The package is now UTDuel_v11: update ServerPackages and the game type name; the saved panel settings moved to the section [UTDuel_v11.HudDuel], set the look again (DuelStyle / DuelReset)

## v1.0 (2026-10-23)

- First release
