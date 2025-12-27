# Params tab reference

This page explains **every parameter** shown in the Setup UI **Params** tab (campaign rules/tuning).

The names below use the internal parameter key in parentheses so hosts can talk about the same setting even if UI wording changes.

## Core / starting conditions

- **Game mode** (`gameMode`): Which sides exist in the campaign. **Do not change mid-campaign**.
- **Auto save** (`autoSave`): Enables/disables automatic campaign saving.
- **Auto save interval** (`autoSaveInterval`): How often autosaves happen (when enabled).
- **Initial player money** (`initialPlayerMoney`): Starting money given to each player.
- **Initial faction money** (`initialFactionMoney`): Starting “shared” money for the rebellion.
- **Initial HR** (`initialHr`): Starting Human Resources (how many AI you can recruit/support early).

## Map / missions / pacing

- **Player markers enabled** (`playerMarkersEnabled`): Whether player markers show on map.
- **Limited fast travel** (`limitedFT`): Limits where fast travel is allowed (any / HQ-only / none).
- **Mission distance** (`distanceMission`): How far from HQ missions can be generated/selected. This affects HQ placement.
- **Spawn distance** (`distanceSPWN`): How far away enemies/markers spawn in (server tuning for performance/immersion).
- **Enemy near distance** (`enemyNearDistance`): How close enemies must be before certain actions are blocked (eg fast travel/other interactions).

## Civilians / world activity

- **Civilian traffic** (`civTraffic`): Amount of civilian traffic (none/low/medium/high).
- **Global civilian max** (`globalCivilianMax`): Overall cap on civilians spawned.
- **Max civilians per town** (`maxCiviliansPerTown`): Per-town cap on civilians spawned.

## Performance / cleanup

- **Idle timeout** (`A3A_idleTimeout`): How long an idle player can sit before the mission treats them as idle (or disables this).
- **GC max objects** (`A3A_gcMaxObjects`): Garbage-collector object cap before cleanup becomes aggressive.
- **GC threshold** (`A3A_GCThreshold`): How long objects stick around before GC deletes them (or disables).

## Revive / medical

- **Revive time** (`A3A_reviveTime`): Time to revive (short/medium/long).
- **Self revive method** (`A3A_selfReviveMethods`): Whether/how self-revive is allowed (eg “withstand”).
- **ACE food** (`aceFood`): Enables/disables ACE food mechanics integration (server-side).

## Building / quality-of-life

- **Builder permissions** (`A3A_builderPermissions`): Who can use building tools (TL / engineer / both).
- **Remove / restore** (`A3A_removeRestore`): Enables/disables remove/restore feature (server rule).
- **Helmet loss chance** (`helmetLossChance`): Chance to lose helmet (never → always).

## Garage / access

- **Flag garage block** (`A3A_flagGarageBlock`): Delay (minutes) before garage access after capturing/flipping a location (or disabled).

## Membership / moderation

These are server/community settings that affect “members vs guests” and team-kill handling.

- **Membership enabled** (`membershipEnabled`): Enables member/guest system.
- **Guest commander** (`A3A_guestCommander`): Whether non-members can become commander.
- **TK punish** (`tkPunish`): Team-kill punishment behavior (off / on / log-only).
- **Member slots** (`memberSlots`): Percentage of player slots reserved for members (or none/all).
- **Member distance** (`memberDistance`): Distance rule for membership effects (4km → unlimited).

## Balance / difficulty (AI + scaling)

- **Enemy balance multiplier** (`A3A_enemyBalanceMul`): General enemy strength scaling (0.4x → 2.8x).
- **Enemy attack multiplier** (`A3A_enemyAttackMul`): How strong/frequent enemy attacks feel (server-side).
- **Invader balance multiplier** (`A3A_invaderBalanceMul`): Scaling specific to the invader faction.
- **Enemy response time** (`A3A_enemyResponseTime`): How quickly enemies react to you (very slow → very fast).
- **Attack HQ proximity multiplier** (`A3A_attackHQProximityMul`): Increases attacks when fighting near HQ (no change → 8x).
- **Enemy skill multiplier** (`A3A_enemySkillMul`): Enemy AI skill (very low → very high).
- **Rebel skill multiplier** (`A3A_rebelSkillMul`): Rebel AI skill (very low → very high).

## Supports / “spicy stuff”

- **Napalm enabled** (`napalmEnabled`): Enables/disables napalm support where applicable.
- **Allow unfair supports** (`allowUnfairSupports`): Enables “unfair” supports (server rule).
- **Allow futuristic supports** (`allowFuturisticSupports`): Enables futuristic supports (server rule).

## Garrisons

- **Rebel garrison limit** (`A3A_rebelGarrisonLimit`): Cap on rebel garrison size (or no limit).

## Equipment / unlock rules

- **Minimum weapons** (`minWeaps`): Minimum weapons required for unlock behavior (or “no unlocks”).
- **Guest item limit** (`A3A_guestItemLimit`): Limits how many items guests can take (or no limit).
- **Unlocked unlimited ammo** (`unlockedUnlimitedAmmo`): If enabled, unlocked items can have unlimited ammo (server rule).
- **Allow unguided launchers** (`allowUnguidedLaunchers`): Whether unguided launchers are allowed (server rule).
- **Allow guided launchers** (`allowGuidedLaunchers`): Whether guided launchers are allowed (server rule).
- **Allow unlocked explosives** (`allowUnlockedExplosives`): Whether unlocked explosives are allowed (server rule).
- **Start with long range radio** (`startWithLongRangeRadio`): Whether players start with LR radios (server rule).

## Loot-to-crate / LTC

- **Loot to crate radius** (`LootToCrateRadius`): Automatically moves loot into a crate within this radius (or disabled).
- **LTC loot unlocked** (`LTCLootUnlocked`): If enabled, LTC interacts with unlock rules (server rule).

## Loot crate tuning (crate limits)

These control “loot crate” generation/contents. Higher numbers usually mean more variety and more items.

- **Bob chaos crates** (`bobChaosCrates`): Enables/disables chaos crate behavior (server rule).
- **Crate player scaling** (`cratePlayerScaling`): Scales crate contents with player count.

Limits are split into:
- **Type max**: how many *different kinds* of that category can appear.
- **Num max**: how many *total items* of that category can appear.

### Weapons

- **Weapon type max** (`crateWepTypeMax`)
- **Weapon number max** (`crateWepNumMax`)

### Items

- **Item type max** (`crateItemTypeMax`)
- **Item number max** (`crateItemNumMax`)

### Ammo

- **Ammo type max** (`crateAmmoTypeMax`)
- **Ammo number max** (`crateAmmoNumMax`)

### Explosives

- **Explosive type max** (`crateExplosiveTypeMax`)
- **Explosive number max** (`crateExplosiveNumMax`)

### Attachments

- **Attachment type max** (`crateAttachmentTypeMax`)
- **Attachment number max** (`crateAttachmentNumMax`)

### Backpacks

- **Backpack type max** (`crateBackpackTypeMax`)
- **Backpack number max** (`crateBackpackNumMax`)

### Vests

- **Vest type max** (`crateVestTypeMax`)
- **Vest number max** (`crateVestNumMax`)

### Helmets

- **Helmet type max** (`crateHelmetTypeMax`)
- **Helmet number max** (`crateHelmetNumMax`)

### Devices

- **Device type max** (`crateDeviceTypeMax`)
- **Device number max** (`crateDeviceNumMax`)

## Development / logging

These are mainly for server owners and debugging.

- **Log level** (`LogLevel`): Controls how much the scenario logs (error → verbose).
- **Log debug console** (`A3A_logDebugConsole`): Controls debug console logging access (none / non-dev / all).


