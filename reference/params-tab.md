## Params tab reference (behavior-first)

This page describes what each parameter in the Setup UI **Params** tab does and when you might want to change it.

- **Key names**: we use the internal parameter key in backticks (eg `allowUnfairSupports`) so you can reference the same setting even if UI text changes.
- **Scope**: most params are effectively **server rules** that are set when the game starts, even if the UI allows you to view them client-side.
- **Mid-campaign changes**: some params are safe to change mid-campaign, but many will produce unexpected behavior if changed after a save is already running. When in doubt, treat all of these as "set at campaign start".

## Core / starting conditions

- **Game mode** (`gameMode`)
  - **What it does**: changes which "enemy" sides exist and whether Occupants/Invaders are friendly to each other.
  - **When to change**: set at campaign start; determines fundamental enemy structure.
  - **Gotchas**: changing mid-campaign can desync assumptions baked into saved state (factions, markers, resources).

- **Auto save** (`autoSave`)
  - **What it does**: enables or disables automatic periodic saves of campaign progress.
  - **When to change**: set at campaign start; can be toggled if you prefer manual-only saves.
  - **Gotchas**: autosave only happens if there have been players online since the last save (prevents empty-server spam).

- **Auto save interval** (`autoSaveInterval`)
  - **What it does**: sets how frequently automatic saves occur (in minutes). Manual saves reset the timer to prevent immediate duplicate autosaves.
  - **When to change**: adjust based on how often you want automatic backups; longer intervals reduce save operations but increase risk of losing progress.

- **Initial player money** (`initialPlayerMoney`)
  - **What it does**: starting personal money for each player when they first join the campaign.
  - **When to change**: increase for easier starts where players can immediately buy equipment; decrease for more challenging early-game economy.

- **Initial faction money** (`initialFactionMoney`)
  - **What it does**: starting shared money pool for the rebel faction (used by commander for purchases, recruiting, etc.).
  - **When to change**: higher values give commanders more starting options; lower values create tighter early-game resource management.

- **Initial HR** (`initialHr`)
  - **What it does**: starting Human Resources (HR) value, which determines how many AI units can be recruited.
  - **When to change**: higher values allow immediate recruitment of larger forces; lower values require building HR through missions before significant recruitment.

## Map / missions / pacing

- **Player markers enabled** (`playerMarkersEnabled`)
  - **What it does**: shows player position markers on the map for all friendly players.
  - **When to change**: disable for more realism/hardcore play; enable for easier coordination in multiplayer.
  - **Gotchas**: only applies in multiplayer; single-player doesn't use the player marker system.

- **Limited fast travel** (`limitedFT`)
  - **What it does**: controls fast travel availability.
  - **Behavior**:
    - `2`: disables fast travel entirely (except some special cases like HC movements).
    - `1`: allows fast travel only to **HQ** and **captured airports**.
    - `0`: allows fast travel to any valid destination.
  - **When to change**: increase restrictions for more realistic movement and strategic positioning; decrease for quality-of-life convenience.
  - **Gotchas**: fast travel can also be blocked by combat/enemy proximity, active attacks, towing vehicles, friendly-fire punishment, and membership leash restrictions.

- **Mission distance** (`distanceMission`)
  - **What it does**: maximum distance from HQ where missions can spawn or be selected.
  - **When to change**: increase on large maps to allow missions further from HQ; decrease to keep action focused near your base.
  - **Gotchas**: missions beyond this radius won't be available at all, which can significantly limit options on very large terrains.

- **Spawn distance** (`distanceSPWN`)
  - **What it does**: base radius that determines when units and vehicles spawn/despawn around players, and affects initial HQ placement behavior.
  - **When to change**: increase for better visual continuity (things spawn further away); decrease to improve performance on slower servers.
  - **Gotchas**: very low values can look "poppy" (vehicles spawning right in front of you); very high values cost performance and may cause issues on lower-end hardware.

- **Enemy near distance** (`enemyNearDistance`)
  - **What it does**: radius that determines if nearby enemies are close enough to block certain actions (like fast travel, recruiting, building, HQ interactions).
  - **When to change**: increase to prevent actions during combat more easily; decrease to allow more actions even when enemies are somewhat nearby.
  - **Gotchas**: only checks for enemies in active combat state, not just any enemy presence, so you might see enemies but still be able to use actions if they haven't engaged.

## Civilians / world activity

- **Civilian traffic** (`civTraffic`)
  - **What it does**: controls how many parked civilian vehicles spawn in cities (scaled by city population).
  - **When to change**: increase for more immersive world activity; decrease to reduce clutter and potential performance impact.
  - **Gotchas**: affects parked vehicles in cities, not moving traffic; higher values mean more vehicles scattered around that may need cleanup.

- **Global civilian max** (`globalCivilianMax`)
  - **What it does**: maximum total number of civilians that can exist in the world at once.
  - **When to change**: increase for more populated, immersive worlds; decrease to improve performance on busy servers or lower-end machines.
  - **Gotchas**: setting to `0` effectively disables civilian spawning; low values reduce world ambience but help with server performance.

- **Max civilians per town** (`maxCiviliansPerTown`)
  - **What it does**: maximum number of civilians that can spawn in any single town or city.
  - **When to change**: increase for more populated settlements; decrease to limit civilian presence and improve performance in urban areas.

## Performance / cleanup

- **Idle timeout** (`A3A_idleTimeout`)
  - **What it does**: time (in seconds) before a player is marked as AFK when they haven't moved or rotated their view.
  - **When to change**: adjust based on how quickly you want to identify inactive players; shorter times catch AFK faster, longer times are more forgiving.
  - **Gotchas**: this marks players but doesn't automatically kick them; the commander will receive a warning notification about AFK players.

- **GC max objects** (`A3A_gcMaxObjects`)
  - **What it does**: maximum number of objects allowed in the cleanup queue before forced deletion (even if near players).
  - **When to change**: increase if you notice important items being cleaned up too aggressively; decrease if you're experiencing performance issues from too many objects piling up.
  - **Gotchas**: some loot containers are protected from cleanup, but when the queue exceeds this limit, protections may be bypassed to prevent performance degradation.

- **GC threshold** (`A3A_GCThreshold`)
  - **What it does**: time interval (in seconds) before the server forces a garbage collection cycle to clean up memory.
  - **When to change**: increase if GC warnings are too frequent; decrease if you want more aggressive memory management. Set to `0` to disable automatic GC entirely.
  - **Special value**: `0` disables the forced GC tracker and automatic cleanup reminders.

## Revive / medical

- **Revive time** (`A3A_reviveTime`)
  - **What it does**: time (in seconds) required to revive a downed teammate.
  - **When to change**: increase for more punishing/tactical gameplay where revives are risky; decrease for faster-paced action.

- **Self revive method** (`A3A_selfReviveMethods`)
  - **What it does**: enables players to revive themselves when incapacitated.
  - **When to change**: enable for quality-of-life when playing alone or with uncoordinated teams; disable for more realistic cooperative gameplay requiring teammate assistance.
  - **Gotchas**: this is independent of ACE medical; if ACE medical is enabled, it may override or interact differently with this setting.

- **ACE food** (`aceFood`)
  - **What it does**: includes ACE food items in the starting rebel equipment pool when ACE mod is loaded.
  - **When to change**: enable if you're using ACE and want food items available from the start; disable if you prefer to acquire them through gameplay.
  - **Gotchas**: this only adds items to starting equipment; it doesn't enable ACE's hunger/thirst systems (those are controlled by ACE mod settings).

## Building / quality-of-life

- **Builder permissions** (`A3A_builderPermissions`)
  - **What it does**: controls which roles can access the building placement system.
  - **Options**: team leaders, engineers, both, or commander-only (commander always has access regardless of setting).
  - **When to change**: restrict to specific roles for organized building; open to more roles for flexibility.
  - **Gotchas**: building is also blocked when enemies are nearby (controlled by enemy near distance).

- **Remove / restore** (`A3A_removeRestore`)
  - **What it does**: disables the "restore units" action on the vehicle box (which allows recovering stored vehicles/equipment).
  - **When to change**: disable if you want permanent vehicle/equipment loss when items are removed; enable for quality-of-life recovery options.

- **Helmet loss chance** (`helmetLossChance`)
  - **What it does**: percentage chance that headgear is removed when a unit takes lethal head damage.
  - **When to change**: increase for more realistic combat where headshots often remove helmets; decrease or set to 0 to prevent helmet loss.
  - **Gotchas**: only triggers on actual lethal head damage, not just any knockdown or head injury.

## Garage / access

- **Flag garage block** (`A3A_flagGarageBlock`)
  - **What it does**: locks the flag's garage, vehicle purchase, and recruitment menus for a set number of minutes after capturing a flag.
  - **When to change**: increase to prevent immediate exploitation after captures (realism/balance); decrease for faster access to resources.
  - **Gotchas**: the lock timer is per-flag and synchronized across all clients, so players joining mid-game will see the correct remaining time.

## Membership / moderation

- **Membership enabled** (`membershipEnabled`)
  - **What it does**: enables the member/guest system, which allows server admins to distinguish between trusted members and temporary guests.
  - **When to change**: enable for servers that want to restrict certain actions to trusted players; disable for open servers where everyone has equal privileges.
  - **Effects**: when enabled, guests may be restricted from fast travel outside the leash zone and can be teleported back to HQ if they roam too far (controlled by member distance).
  - **Gotchas**: if disabled, all players are treated as having full member privileges.

- **Guest commander** (`A3A_guestCommander`)
  - **What it does**: allows or prevents guests (non-members) from becoming commander.
  - **When to change**: disable to restrict commander role to trusted members only; enable to allow any player to become commander.

- **TK punish** (`tkPunish`)
  - **What it does**: enables friendly-fire punishment system and affects certain safety restrictions.
  - **Modes**:
    - `0`: disabled (no punishment)
    - `1`: enabled (full punishment system active)
    - `2`: logging/notification only (tracks TKs but doesn't punish)
  - **When to change**: enable to discourage accidental or intentional friendly fire; disable for relaxed gameplay or when using external admin tools.
  - **Effects**: when enabled, players who teamkill are temporarily jailed and blocked from certain actions (like fast travel); bomb runs near HQ are also restricted for safety.

- **Member slots** (`memberSlots`)
  - **What it does**: reserves a percentage of rebel team slots for members, preventing guests from filling all available slots.
  - **When to change**: increase to guarantee slots for trusted members on busy servers; decrease to allow more guests to play.
  - **Gotchas**: guests may be kicked when member slots are filled and more members try to join; server admins should coordinate with server rules for best enforcement.

- **Member distance** (`memberDistance`)
  - **What it does**: maximum distance (in meters) that guests can travel from HQ or nearby members before being teleported back.
  - **When to change**: decrease to keep guests close to HQ for supervision; increase to give guests more freedom; set to `-1` or `0` to disable the leash entirely.
  - **Special value**: `-1` or `0` disables the distance restriction completely.
  - **Gotchas**: commander, certain aircraft states, and players under friendly-fire punishment are exempt from the leash restriction.

## Balance / difficulty (AI + scaling)

- **Enemy balance multiplier** (`A3A_enemyBalanceMul`)
  - **What it does**: scales overall enemy strength across multiple systems (resources, attack frequency, unit quality, etc.).
  - **When to change**: increase for harder campaigns with more aggressive and resourceful enemies; decrease for easier gameplay.

- **Enemy attack multiplier** (`A3A_enemyAttackMul`)
  - **What it does**: controls how quickly enemies accumulate resources for attack operations and how frequently they launch attacks against player positions.
  - **When to change**: increase for more frequent and intense enemy attacks; decrease for slower-paced campaigns with less pressure.
  - **Gotchas**: this affects strategic-level attack frequency, not individual unit combat effectiveness.

- **Invader balance multiplier** (`A3A_invaderBalanceMul`)
  - **What it does**: separate difficulty scaling specifically for the Invader faction, independent of Occupants.
  - **When to change**: adjust if you want Invaders to be stronger or weaker than Occupants; useful for asymmetric difficulty or specific campaign narratives.

- **Enemy response time** (`A3A_enemyResponseTime`)
  - **What it does**: controls how quickly enemy forces react to player actions and contacts.
  - **When to change**: decrease for more aggressive, fast-reacting enemies; increase for slower, more methodical enemy responses.

- **Attack HQ proximity multiplier** (`A3A_attackHQProximityMul`)
  - **What it does**: increases enemy attack frequency and intensity when combat occurs near your HQ.
  - **When to change**: increase for more pressure when fighting near base (defensive focus); decrease to prevent HQ from being constantly under siege.

- **Enemy skill multiplier** (`A3A_enemySkillMul`)
  - **What it does**: directly scales AI combat skill (accuracy, reaction time, tactics) for all enemy units.
  - **When to change**: increase for deadlier, more accurate enemy AI; decrease for easier combat encounters.

- **Rebel skill multiplier** (`A3A_rebelSkillMul`)
  - **What it does**: directly scales AI combat skill (accuracy, reaction time, tactics) for all rebel AI units you recruit.
  - **When to change**: increase to make your recruited forces more effective; decrease for more challenging gameplay where you rely more on player skill.

## Supports / “spicy stuff”

- **Napalm enabled** (`napalmEnabled`)
  - **What it does**: allows napalm weapons to be used in airstrikes and bomb runs.
  - **When to change**: enable for more devastating area-denial weapons; disable for less intense support options or performance reasons.
  - **Gotchas**: disabling napalm doesn't remove other bomb types (HE, cluster) or carpet bombing, which are controlled separately.

- **Allow unfair supports** (`allowUnfairSupports`)
  - **What it does**: enables extremely powerful support types that may be considered unbalanced.
  - **When to change**: enable for maximum firepower and cinematic moments; disable for more balanced, tactical gameplay.
  - **Includes**: carpet bombing (wide-area devastation, requires airbase) and cruise missiles (currently disabled pending fixes; also requires carrier access and specific map templates).

- **Allow futuristic supports** (`allowFuturisticSupports`)
  - **What it does**: enables science-fiction style support weapons that may not fit realistic campaigns.
  - **When to change**: enable for high-tech/modern campaigns; disable for realistic or period-accurate gameplay.
  - **Includes**: orbital strikes (extremely powerful but very expensive; AI can select these if available).

## Garrisons

- **Rebel garrison limit** (`A3A_rebelGarrisonLimit`)
  - **What it does**: sets the base limit for how many rebel garrison units can be placed at each location type.
  - **Scaling by location**:
    - **Cities**: scaled by city population (larger cities can have more garrisons).
    - **Airports**: approximately 1.5x the base limit.
    - **Factories/resources**: approximately 0.5x the base limit.
    - **Other locations**: base limit applies.
  - **When to change**: increase to allow larger defensive forces; decrease to limit garrison sizes and reduce resource costs. Set to `-1` to remove limits entirely.
  - **Special value**: `-1` means no garrison limit.

## Equipment / unlock rules

- **Minimum weapons** (`minWeaps`)
  - **What it does**: enables the unlock system - items become permanently unlocked once you have this many copies in the arsenal.
  - **When to change**: increase to make unlocks slower (more items needed); decrease for faster unlocks; set to `-1` to disable unlocks entirely (all items available from start).
  - **Special value**: `-1` disables unlock progression entirely and makes all items immediately available.

- **Guest item limit** (`A3A_guestItemLimit`)
  - **What it does**: maximum number of items guests can take from the arsenal at once.
  - **When to change**: decrease to prevent guests from taking too many items (anti-hoarding); increase to give guests more freedom; set to `-1` or `0` to remove limits.

- **Unlocked unlimited ammo** (`unlockedUnlimitedAmmo`)
  - **What it does**: automatically unlocks the primary magazine type when a weapon is unlocked, preventing the situation where you have an unlocked gun but no ammo for it.
  - **When to change**: enable for convenience (recommended); disable if you want magazines to be unlocked separately from weapons.

- **Allow unguided launchers** (`allowUnguidedLaunchers`)
  - **What it does**: allows or prevents unguided rocket launchers (like RPGs) from being unlocked.
  - **When to change**: disable to restrict access to rocket launchers (balance or realism); enable for full weapon variety.

- **Allow guided launchers** (`allowGuidedLaunchers`)
  - **What it does**: allows or prevents guided missile launchers (like Javelins) from being unlocked.
  - **When to change**: disable to restrict access to guided missiles (balance or realism); enable for full weapon variety.

- **Allow unlocked explosives** (`allowUnlockedExplosives`)
  - **What it does**: allows or prevents explosives (grenades, mines, etc.) from being unlocked.
  - **When to change**: disable to restrict access to explosives (balance or safety concerns); enable for full equipment variety.

- **Start with long range radio** (`startWithLongRangeRadio`)
  - **What it does**: includes long-range radios in starting rebel equipment when using radio mods like ACRE or TFAR.
  - **When to change**: enable for immediate long-range communication; disable to require acquiring radios through gameplay.
  - **Gotchas**: TFAR may have different behavior compared to ACRE due to how TFAR initializes settings.

## Loot-to-crate / LTC

- **Loot to crate radius** (`LootToCrateRadius`)
  - **What it does**: radius (in meters) for the "loot to crate" action that automatically collects items from dead bodies and ground loot into a container.
  - **When to change**: increase for easier loot collection over larger areas; decrease to require closer proximity or manual looting.
  - **Gotchas**: using this action will break undercover status, and the container is protected from automatic cleanup during the transfer process.

- **LTC loot unlocked** (`LTCLootUnlocked`)
  - **What it does**: controls whether the loot-to-crate system respects unlock restrictions when transferring items.
  - **When to change**: enable to maintain unlock progression (only unlocked items transfer easily); disable to allow all items regardless of unlock status.

## Loot crate tuning (crate limits)

These parameters control how loot crates and garrison crates are filled with equipment.

- **Bob chaos crates** (`bobChaosCrates`)
  - **What it does**: switches loot generation between organized (unlock-focused) and completely random.
  - **Behavior**:
    - **On**: completely random categories, items, and quantities (chaotic).
    - **Off**: biased toward items not yet unlocked, with balanced quantities (organized progression).
  - **When to change**: enable for unpredictable, varied loot; disable for progression-focused gameplay where crates help unlock new items.

- **Crate player scaling** (`cratePlayerScaling`)
  - **What it does**: automatically reduces loot amounts in crates as more players join the server (prevents loot inflation on large servers).
  - **When to change**: enable to maintain balance on busy servers where many players would otherwise receive full loot; disable for consistent loot regardless of player count.
  - **Gotchas**: scaling is automatically disabled if unlocks are turned off (minWeaps < 0).

- **Type max** (`crate*TypeMax`)
  - **What it does**: maximum number of different item types that can appear in a crate for each category (weapons, magazines, items, etc.).
  - **When to change**: increase for more variety per crate; decrease to keep crates focused on fewer item types.

- **Number max** (`crate*NumMax`)
  - **What it does**: maximum quantity of each item type that can appear in a crate (before player scaling is applied).
  - **When to change**: increase for more generous loot; decrease to limit how many of each item can be found per crate.

## Development / logging

- **Log level** (`LogLevel`)
  - **What it does**: controls how much detail is written to server logs (1 = minimal, 4 = verbose debugging).
  - **When to change**: increase for troubleshooting issues; decrease for cleaner logs on production servers. Higher levels may impact performance.

- **Log debug console** (`A3A_logDebugConsole`)
  - **What it does**: controls who can access debug console logging features.
  - **When to change**: restrict to admins/developers for security; open up for public debugging or testing servers.
