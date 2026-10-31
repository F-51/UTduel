# Changelog

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
