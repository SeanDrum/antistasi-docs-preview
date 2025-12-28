## Params tab reference (behavior-first)

This page is the “what it actually changes in code” reference for the Setup UI **Params** tab.

- **Key names**: we use the internal parameter key in backticks (eg `allowUnfairSupports`) so you can talk about the same thing even if UI text changes.
- **Scope**: most params are effectively **server rules** (published by the server on game start) even if the UI renders them client-side.
- **Mid-campaign changes**: some params are safe-ish, some will produce weirdness if changed after a save is already running. When in doubt, treat all of these as “set at campaign start”.

## Core / starting conditions

- **Game mode** (`gameMode`)
  - **What it does**: changes which “enemy” sides exist and whether Occupants/Invaders are friendly to each other.
  - **Who uses it**: server init applies `setFriend` relationships and hides carrier markers for the missing side in some modes.
  - **Gotchas**: changing mid-campaign can desync assumptions baked into saved state (factions, markers, resources).

- **Auto save** (`autoSave`)
  - **What it does**: gates the autosave loop (the server checks this every interval).
  - **Who uses it**: server-only autosave loop in `initServer` triggers `A3A_fnc_saveLoop`.
  - **Gotchas**: autosave only happens if there have been players online since the last save (prevents empty-server spam).

- **Auto save interval** (`autoSaveInterval`)
  - **What it does**: sets the interval for the autosave scheduler and also pushes out the next autosave when you do a manual save.
  - **Who uses it**: server autosave loop + `A3A_fnc_saveLoop` sets `autoSaveTime = time + autoSaveInterval` so you don’t immediately autosave after a manual save.

- **Initial player money** (`initialPlayerMoney`)
  - **What it does**: seed money for personal saves / first join.
  - **Who uses it**: player save/load logic (personal economy), not the shared pool.

- **Initial faction money** (`initialFactionMoney`)
  - **What it does**: sets the starting rebel shared money pool (`resourcesFIA`).
  - **Who uses it**: server sets `server setVariable ["resourcesFIA", initialFactionMoney, true]` during init.

- **Initial HR** (`initialHr`)
  - **What it does**: sets starting HR (`hr`).
  - **Who uses it**: server sets `server setVariable ["hr", initialHr, true]` during init.

## Map / missions / pacing

- **Player markers enabled** (`playerMarkersEnabled`)
  - **What it does**: enables the player-markers loop.
  - **Who uses it**: clients spawn `A3A_fnc_playerMarkers` during `initClient` when in multiplayer.
  - **Gotchas**: only applies in MP; SP doesn’t run the player marker system.

- **Limited fast travel** (`limitedFT`)
  - **What it does**: blocks fast travel entirely or restricts destinations.
  - **Who uses it**: fast-travel gating checks.
  - **Behavior**:
    - `limitedFT == 2`: disables fast travel (except some HC-related flows).
    - `limitedFT == 1`: allows fast travel only to **HQ** and **captured airports**.
  - **Gotchas**: fast travel can also be blocked by combat/enemy proximity (`enemyNearDistance`), active attacks, towing, FF punishment, and membership leash.

- **Mission distance** (`distanceMission`)
  - **What it does**: hard radius from HQ marker for mission selection/generation.
  - **Who uses it**: mission request system filters candidate markers/objects by `distanceMission`.
  - **Gotchas**: impacts which missions can roll at all (especially on large terrains).

- **Spawn distance** (`distanceSPWN`)
  - **What it does**: base radius used by the spawn/despawn ecosystem and a few other systems.
  - **Who uses it**: server derives `distanceSPWN1` and `distanceSPWN2` from it; HQ placement also uses it for side-flipping nearby road controls after placement.
  - **Gotchas**: very low values can look “poppy” (vehicles spawning on approach); very high values cost performance.

- **Enemy near distance** (`enemyNearDistance`)
  - **What it does**: the radius for “is there combat close enough to block an action?”
  - **Who uses it**: `A3A_fnc_enemyNearCheck` checks Occupants+Invaders units in COMBAT that can fight.
  - **Common blocks**: fast travel, buying/recruiting, builder, some HQ interactions.
  - **Gotchas**: it checks *behavior == COMBAT*, not just “enemy exists”.

## Civilians / world activity

- **Civilian traffic** (`civTraffic`)
  - **What it does**: scales spawned *parked* city vehicles/boats.
  - **Who uses it**: city spawn place stats compute parked vehicles as roughly `sqrt(pop) * civTraffic` (see garrison/city vehicle generation).
  - **Gotchas**: this is about city vehicles (cars/boats) as well as civ “activity” in other systems; higher values means more ambient vehicles to manage/clean up.

- **Global civilian max** (`globalCivilianMax`)
  - **What it does**: global cap used by the civ spawning systems.
  - **Who uses it**: server/client civ spawning logic (plus UI shows it in “game options” hint).
  - **Gotchas**: `0` is effectively “no civs” in many spawners; on busy servers, low values reduce ambience but help perf.

- **Max civilians per town** (`maxCiviliansPerTown`)
  - **What it does**: per-town cap used by civ spawners.
  - **Who uses it**: town/city spawn logic.

## Performance / cleanup

- **Idle timeout** (`A3A_idleTimeout`)
  - **What it does**: marks players as AFK after no movement/rotation for the configured time.
  - **Who uses it**: client idle checker sets `player setVariable ["isAFK", true, ...]` when exceeded.
  - **Gotchas**: this mainly feeds server-side behavior and stats; it does *not* kick players. Commander gets a warning hint.

- **GC max objects** (`A3A_gcMaxObjects`)
  - **What it does**: hard cap for the postmortem cleanup queue; if the queue is too big, objects are deleted immediately even if near players.
  - **Who uses it**: postmortem cleanup loop deletes regardless of expiry once over cap.
  - **Gotchas**: this interacts with loot systems that mark containers as “don’t GC” (`stopPostmortem`).

- **GC threshold** (`A3A_GCThreshold`)
  - **What it does**: server-side timer for forced garbage collection.
  - **Who uses it**: garbage cleaner tracker reminds players and runs GC when time since last GC exceeds threshold.
  - **Special value**: `0` disables the forced GC tracker.

## Revive / medical

- **Revive time** (`A3A_reviveTime`)
  - **What it does**: affects the time required for revive actions.
  - **Who uses it**: revive action logic.

- **Self revive method** (`A3A_selfReviveMethods`)
  - **What it does**: enables the self-revive action while incapacitated.
  - **Who uses it**: unconscious UI/action wiring checks this before allowing `A3A_fnc_selfRevive`.
  - **Gotchas**: this is independent of ACE medical; if ACE medical replaces the revive pipeline, behavior may differ.

- **ACE food** (`aceFood`)
  - **What it does**: adds ACE food items to the initial rebel equipment pool (when ACE is present).
  - **Who uses it**: ACE compatibility init appends `aceFoodItems` into `initialRebelEquipment` when enabled.
  - **Gotchas**: this does not “force-enable ACE hunger”; it only changes what items the campaign starts with.

## Building / quality-of-life

- **Builder permissions** (`A3A_builderPermissions`)
  - **What it does**: gates who can start the building placer.
  - **Who uses it**: builder start checks:
    - **Team leader** eligibility when set to TL/both.
    - **Engineer** eligibility when set to engineer/both.
    - **Commander** (boss) is always eligible.
  - **Gotchas**: also blocked by `enemyNearDistance`.

- **Remove / restore** (`A3A_removeRestore`)
  - **What it does**: disables the “restore units” action on the vehicle box when enabled.
  - **Who uses it**: client-side addAction condition includes `!A3A_removeRestore`.

- **Helmet loss chance** (`helmetLossChance`)
  - **What it does**: when a unit takes lethal head damage (`hithead`), there’s a % chance to remove headgear.
  - **Who uses it**: damage handler for rebels / PvPers.
  - **Gotchas**: this is specifically tied to the hitpoint `"hithead"` and “damage >= 1”, not general knockdowns.

## Garage / access

- **Flag garage block** (`A3A_flagGarageBlock`)
  - **What it does**: locks the flag’s **garage / buy vehicle / recruit** menus for N minutes after a flag flip.
  - **Who uses it**: `manageFlagAccess` checks `serverTime - A3A_flagFlipTime` against `A3A_flagGarageBlock * 60`.
  - **Gotchas**: the lock is per-flag and uses serverTime (so JIP clients see the same remaining time).

## Membership / moderation

- **Membership enabled** (`membershipEnabled`)
  - **What it does**: turns on the member/guest system.
  - **Who uses it**:
    - Guests can be blocked from using some actions (eg fast travel) if they’re outside the leash zone.
    - Guests can be forcibly teleported back to HQ if they roam too far (see `memberDistance`).
  - **Gotchas**: if disabled, membership checks mostly treat everyone as allowed.

- **Guest commander** (`A3A_guestCommander`)
  - **What it does**: controls whether non-members can become commander.
  - **Who uses it**: commander assignment / eligibility logic.

- **TK punish** (`tkPunish`)
  - **What it does**: enables the friendly-fire punishment system and also gates some “danger close” behaviors.
  - **Who uses it**:
    - FF punishment EHs are not installed if `tkPunish == 0`.
    - Some actions (including fast travel) check whether you’re currently jailed/punished.
    - Rebel bomb-run UI blocks “danger close to HQ” when `tkPunish > 0`.
  - **Modes**:
    - `0`: off
    - `1`: on
    - `2`: log/notify-only (still installs parts of the system)

- **Member slots** (`memberSlots`)
  - **What it does**: reserves a % of rebel slots for members.
  - **Who uses it**: server computes `bookedSlots = floor((memberSlots/100) * playableSlotsNumber teamPlayer)`; clients enforce it on join (guests can be kicked/ended when too many non-members).
  - **Gotchas**: this is enforced client-side during init; server owners should also manage via server rules for best results.

- **Member distance** (`memberDistance`)
  - **What it does**: leash distance (meters) that guests must stay within of HQ (or members).
  - **Who uses it**: guest leash loop warns with a countdown then teleports guests back to HQ when exceeded.
  - **Special value**: `-1` (or `<= 0`) means unlimited / disabled.
  - **Gotchas**: there are exemptions (boss, some aircraft states, FF punishment state).

## Balance / difficulty (AI + scaling)

- **Enemy balance multiplier** (`A3A_enemyBalanceMul`)
  - **What it does**: scales core enemy “balance” values used in multiple systems (resources, weights, etc.).
  - **Who uses it**: several balance computations; also displayed in the in-game “game options” hint.

- **Enemy attack multiplier** (`A3A_enemyAttackMul`)
  - **What it does**: scales how quickly enemy attack resources accumulate / how often they can afford attack operations.
  - **Who uses it**: server init seeds attack pools using this multiplier.
  - **Gotchas**: this is “strategy layer” pacing, not per-unit combat skill.

- **Invader balance multiplier** (`A3A_invaderBalanceMul`)
  - **What it does**: separate scaling for invader side (compared to occupants).
  - **Who uses it**: server init resources for invaders use this multiplier.

- **Enemy response time** (`A3A_enemyResponseTime`)
  - **What it does**: changes reaction delays (how quickly AI responds to contacts/events).
  - **Who uses it**: enemy response scheduling logic.

- **Attack HQ proximity multiplier** (`A3A_attackHQProximityMul`)
  - **What it does**: increases attack pressure when fights are close to HQ (strategy layer).
  - **Who uses it**: attack-selection logic weights HQ-proximity.

- **Enemy skill multiplier** (`A3A_enemySkillMul`)
  - **What it does**: scales per-unit AI skill settings for enemy forces.

- **Rebel skill multiplier** (`A3A_rebelSkillMul`)
  - **What it does**: scales per-unit AI skill settings for rebel AI.

## Supports / “spicy stuff”

- **Napalm enabled** (`napalmEnabled`)
  - **What it does**: allows napalm to be selected/used where supported.
  - **Who uses it**:
    - AI airstrike support selection weights `NAPALM` as one of the possible bomb types (otherwise napalm weight is 0).
    - Rebel “bomb run” support tries to use napalm (and falls back if disabled).
  - **Gotchas**: if disabled, you can still see non-napalm variants (HE/cluster) and carpet bombing is separate.

- **Allow unfair supports** (`allowUnfairSupports`)
  - **What it does**: unlocks support types flagged as “unfair” in the AI support system.
  - **Who uses it**: AI support type initialization filters out “unfair” supports unless this is enabled.
  - **Which supports** (current code):
    - **`CARPETBOMBS`**: wide-area carpet bombing (AI-selected; requires an available airbase).
    - **Cruise missile (`MISSILE`)**: gated here too, but currently **hard-disabled** by the availability function (`if(true) exitWith {-1};`) pending fixes; also template-restricted (eg VN disallowed) and requires being in range of the side’s carrier marker.

- **Allow futuristic supports** (`allowFuturisticSupports`)
  - **What it does**: unlocks “futuristic” support types flagged as such in the AI support system.
  - **Who uses it**: AI support type initialization filters out these supports unless enabled.
  - **Which supports** (current code):
    - **`ORBITALSTRIKE`**: orbital strike (AI-selected, very expensive).

## Garrisons

- **Rebel garrison limit** (`A3A_rebelGarrisonLimit`)
  - **What it does**: caps the maximum number of rebel garrison units by location type.
  - **Who uses it**: `getGarrisonLimit` returns:
    - **Cities**: derived from `sqrt(pop)` (not a fixed number).
    - **Airports**: `~1.5x` the base limit.
    - **Factories/resources**: `~0.5x` the base limit.
    - **Others**: base limit.
  - **Special value**: `-1` means no limit.

## Equipment / unlock rules

- **Minimum weapons** (`minWeaps`)
  - **What it does**: enables the “unlock by quantity” system: items become permanently unlocked once you have at least `minWeaps` copies in the arsenal.
  - **Who uses it**: arsenal management loop; also used as a general “no unlocks” switch.
  - **Special value**: `-1` disables unlock progression entirely (many systems treat this as “no unlocks”).

- **Guest item limit** (`A3A_guestItemLimit`)
  - **What it does**: caps how many items guests can take (anti-drain / anti-hoarding).
  - **Who uses it**: arsenal limit enforcement.

- **Unlocked unlimited ammo** (`unlockedUnlimitedAmmo`)
  - **What it does**: when a weapon becomes unlocked, also unlocks its primary magazine (to avoid “unlocked gun but no mags”).
  - **Who uses it**: arsenal management unlock step.

- **Allow unguided launchers** (`allowUnguidedLaunchers`)
  - **What it does**: blocks unlock progression for rocket launchers and their magazines (simulation `shotrocket`) when disabled.
  - **Who uses it**: arsenal management filters both item categories and magazine simulations.

- **Allow guided launchers** (`allowGuidedLaunchers`)
  - **What it does**: blocks unlock progression for missile launchers and their magazines (simulation `shotmissile`) when disabled.
  - **Who uses it**: arsenal management filters both item categories and magazine simulations.

- **Allow unlocked explosives** (`allowUnlockedExplosives`)
  - **What it does**: blocks unlock progression for explosives when disabled.
  - **Who uses it**: arsenal management category filter.

- **Start with long range radio** (`startWithLongRangeRadio`)
  - **What it does**: adds long-range radios to starting rebel equipment for some radio mods.
  - **Who uses it**: ACRE path appends LR radios when enabled.
  - **Gotchas**: TFAR behavior differs (some TFAR settings are hard-set during init).

## Loot-to-crate / LTC

- **Loot to crate radius** (`LootToCrateRadius`)
  - **What it does**: sets the radius used by the “loot to crate” action to vacuum bodies and ground loot into a container.
  - **Who uses it**: LTC scans dead bodies + weapon holders within radius and transfers contents.
  - **Gotchas**:
    - LTC forcibly breaks undercover (`player setCaptive false`).
    - The target container is marked `stopPostmortem = true` to prevent cleanup eating it mid-process.

- **LTC loot unlocked** (`LTCLootUnlocked`)
  - **What it does**: decides whether LTC respects unlock rules.
  - **Who uses it**: when disabled, LTC uses unlocked item sets as a filter (items considered “already unlocked” are treated differently during transfer).

## Loot crate tuning (crate limits)

These params affect `A3A_fnc_fillLootCrate` which fills loot crates and some garrison crates.

- **Bob chaos crates** (`bobChaosCrates`)
  - **What it does**: switches loot generation from “biased toward not-yet-unlocked, gaussian-ish amounts” to “pure random”.
  - **Who uses it**: loot crate picker functions for weapon selection, number-of-types, and quantity.
  - **Behavior**:
    - On: random categories, random items, random quantities.
    - Off: prefers items not yet unlocked; uses distributions to avoid extreme crates.

- **Crate player scaling** (`cratePlayerScaling`)
  - **What it does**: reduces loot amounts as player count increases (to stop loot inflation on big servers).
  - **Who uses it**: loot crate amount picker scales by approximately \(1 / (1 + \text{players}/20)\).
  - **Gotchas**: if `minWeaps < 0` (no unlocks), scaling is disabled and treated as factor 1.

- **Type max** (`crate*TypeMax`)
  - **What it does**: caps the number of *different* types rolled for that category.
  - **Who uses it**: loot crate generator loops up to a random number of distinct types.

- **Number max** (`crate*NumMax`)
  - **What it does**: caps the *quantity* rolled per selected type (then possibly scaled by player count).
  - **Who uses it**: loot crate generator amount picker.

## Development / logging

- **Log level** (`LogLevel`)
  - **What it does**: sets mission logging verbosity (`1..4`).
  - **Who uses it**: server publishes it immediately during init; various systems change logging cadence/detail based on it.

- **Log debug console** (`A3A_logDebugConsole`)
  - **What it does**: controls debug console logging access level.
  - **Who uses it**: server publishes it during init; client/dev tools respect it.
