# Official Antistasi Community Edition Wiki

Hello and welcome to the Antistasi Guide!

Antistasi is a persistent “capture the island” style campaign for Arma 3. You start out outgunned and under-resourced, and you grow your rebellion over time by looting, completing missions, and taking (and holding) key locations.

This repo is intentionally simple: **Markdown files you can browse directly in GitHub**.

## Guides

We aim to keep the documentation in three “levels”:

- **Beginners Guide** — how to play, what the systems mean, and what to do next.
- **Detailed Reference Guide** — deeper mechanics and numbers (optional).
- **Dev Guide** — developer/admin focused notes (optional).

Right now we’re starting with just one guide:

- **[Beginners Guide](beginners_guide/README.md)**

## Game Mechanics

### Arsenal

The **Arsenal** is your primary equipment management system, accessed at the vehicle box at HQ. It's where you customize your loadout with weapons, gear, and equipment collected during the campaign.

**How it works:**
- **Access**: Interact with the vehicle box at HQ to open the arsenal interface
- **Item collection**: Equipment looted from enemies and placed in the vehicle box is automatically added to the arsenal inventory
- **Unlocking system**: When you collect enough copies of an item (controlled by the `minWeaps` parameter, default 25), it becomes **permanently unlocked** with unlimited availability for all players
- **Limited items**: Items below the unlock threshold have finite quantities—take them and they're gone until you loot more
- **Member privileges**: Commanders and members can take any item regardless of quantity; regular players may be restricted until sufficient copies are available

**What gets unlocked:**
- Weapons (rifles, pistols, launchers), attachments (optics, grips, suppressors), uniforms, vests, backpacks, headgear, NVGs, magazines, explosives, and utility items
- Intel missions can also unlock weapons directly
- Starting equipment from your faction is available immediately
- Ammo for unlocked weapons can be automatically unlocked if enabled in parameters

The arsenal is central to progression: collect enemy equipment, build up your inventory, and unlock better gear as your stockpiles grow. Loot everything you can and bring it back to HQ to expand your available equipment.

## Notes

- This guide is a "living" rewrite inspired by the older docs site:
  - [Antistasi Docs index](https://official-antistasi-community.github.io/A3-Antistasi-Docs/index.html)
  - [Beginners Guide (raw)](https://official-antistasi-community.github.io/A3-Antistasi-Docs/beginners_guide/raw_beginners_guide.html#beginners-guide)



