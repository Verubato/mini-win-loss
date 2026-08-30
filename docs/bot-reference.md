# MiniWinLoss - bot reference

Version 1.1.6. Interface version: 120100 (retail only). No saved
variables.

## What it does

Adds a win-loss line to each bracket button on the Conquest (Rated) tab of
the PvP window, formatted "wins - losses (winrate%)", e.g. "12 - 8 (60.0%)".
Brackets covered: Rated BG Blitz, Rated Solo Shuffle, 2v2 Arena, 3v3 Arena,
and Rated Battlegrounds.

## How it works

- Waits for Blizzard_PVPUI to load (it loads when you open the PvP window),
  then creates a text line on each bracket button of the ConquestFrame.
- Numbers come from GetPersonalRatedInfo: games played and won this season.
  Solo Shuffle uses the round-based season fields instead, so its numbers
  count rounds, not lobbies.
- Losses are computed as played minus wins; win rate is wins / played.
- Refreshes on entering world and on rated stats updates.

## Settings

Open with a slash command or Options -> AddOns -> MiniWinLoss. The panel
describes what the addon does; its subtitle says there is nothing to
configure. No saved variables.

## Slash commands

/miniwinloss, /mwl - both open the settings panel.

## Troubleshooting

- "I don't see any numbers": open the PvP window (default hotkey H) and go to
  the Rated/Conquest tab; the text only exists on that frame. If a bracket
  shows "0 - 0 (0.0%)" you have no recorded games this season in it.
- "Solo Shuffle numbers look too big": intended; shuffle counts individual
  rounds won and lost, not whole matches.
- Stats are for the current season only; there is no history display.
