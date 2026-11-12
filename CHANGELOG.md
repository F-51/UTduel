# Changelog

## v1.2.4 (2026-11-13)

- The package is now UTDuel_v124: update ServerPackages and the game type; the HUD settings moved to [UTDuel_v124.HudDuel], the server settings to [UTDuel_v124.DuelGame]
- Connection loss: the game is paused after 10 seconds of silence (was 5)
- Back after a connection loss: the pause no longer ends by itself. The one who is back resumes it with the Pause key ("Press Pause to continue" under the timer), and can reconnect meanwhile if his connection is still bad; it goes on by itself when the rest of the pause time is over. The opponent cannot resume it. Both left in one pause: the first one who left resumes it, once the second one is back too
- Overtime: the clock counts it up (it stood at 0:00); UTComp's timed overtime is shown the UTComp way
- Challenger Picks the Map (a server setting, off by default): everyone in the queue picks the map of his next duel (ESC - Pick Map, any time) from the server's map vote list; the winner who stays has no say. A tab of favourite maps (the star). On the score screen a UTComp map vote against the challenger's map is cancelled
- ESC - Duel Settings (admin): Challenger Picks the Map, Restart Map After Match, End Match When a Player Leaves; the server settings in two columns
- ESC: the Players and Queue sections half and half (two players fit at 1024x768); "<--- you" at your line of the queue
- Spectator: a new layout Below (Meters) (presets plain-meters, portraits-meters): health and shield as meters in pieces of 25 with the icons of the stock HUD; with portraits the values beside them (DuelMeters)
- DuelHP without an argument goes through the layouts of the Duel HUD window
- Nicks keep growing with the panel on 1440p and 4K screens
- Fix: a spectator who came in at the very start of the match could not switch players (the camera stuck)
- ESC: the rows of buttons centred
- Translation: the menus, the HUD texts and the messages of the server are in UTDuel_v124.int; every player sees them in the language of his own game (the server sends the message, his client writes it). Russian included (UTDuel_v124.rut); how to translate: TRANSLATION
- The release archive has UTDuel_v124.u.uz2 for redirect servers (the Redirect folder)
- With UTComp: after Restart Map After Match the duelists start the warm-up with the warm-up weapons (they had the match loadout, so the warm-up looked like a new match), and nobody is ready at its start

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
