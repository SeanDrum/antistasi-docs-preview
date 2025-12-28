# Enemy Reactions & Counter-Attacks

The enemy factions in Antistasi are not passive—they actively respond to your actions with various types of military responses. Understanding these systems is crucial for planning attacks, defending territory, and managing enemy aggression.

## Quick Reaction Forces (QRF)

QRFs are rapid reinforcement units that enemies send when you attack their locations. They're designed to recapture or defend strategic points under assault.

### Types of QRF

**Land QRF:**
- Composed of ground vehicles (trucks, APCs, armored vehicles)
- Spawns from the nearest enemy land base (outpost or airbase)
- Travels overland to the target location
- Typically includes 1-3 vehicles with infantry cargo
- May include 0-1 attack vehicles (APCs or light armor) depending on vehicle count

**Air QRF:**
- Composed of transport helicopters
- Spawns from the nearest enemy airbase
- Flies directly to the target location
- Typically includes 1-3 helicopters with infantry cargo
- May include 0-1 attack helicopters depending on vehicle count
- Faster response time than land QRFs

### QRF Mechanics

**When QRFs are triggered:**
- Automatically when you attack an enemy garrison (outpost, airbase, resource site, etc.)
- Response time depends on:
  - **War tier**: Higher tiers = faster response (delay formula: `(0.5 + random 1) × (300 - 15 × tierWar - 1 × aggression)`)
  - **Aggression level**: Higher aggression = faster response
  - **Distance from enemy bases**: Closer bases respond faster
  - **Air vs Land**: Air QRFs are generally faster but cost more resources

**QRF behavior:**
- QRFs attempt to reach the target location and engage your forces
- They will try to recapture the location if you've taken it
- QRFs have a 30-minute timeout—if they can't find targets or complete their mission, they retreat
- QRFs retreat if 75% of their forces are eliminated
- QRFs check for nearby enemies within 500m of the target; if none found after 10 minutes, they return to base

**Resource cost:**
- Land QRF: `vehicleCount × A3A_balanceVehicleCost`
- Air QRF: `1.5 × vehicleCount × A3A_balanceVehicleCost` (50% more expensive)
- Resources are deducted from the enemy's defense pool when the QRF spawns

**Defeating QRFs:**
- Successfully defeating a QRF gives you breathing room—they won't immediately respawn
- However, if the garrison is still under attack, enemies may send additional QRFs
- QRFs that timeout or retreat don't count as "defeated" but still give you temporary relief

## Enemy Support Calls

Support calls are force multipliers that enemy garrisons can request during combat. Unlike QRFs (which are reinforcements), support calls provide firepower and area denial capabilities.

### Support Types

**Mortars** (Always available):
- Light area bombardment
- Effective radius: 100m
- Strike power: 50 resources
- Called by garrison defenders when under attack
- 20-30 second delay before impact
- Can target static weapons and vehicles at longer ranges

**Artillery** (Available at war tier 5+):
- Heavy area bombardment
- Effective radius: 150m
- Strike power: 85 resources
- Requires enemy faction to have artillery vehicles
- More powerful than mortars but less frequent

**Airstrikes** (Scales with war tier):
- Fast jet strikes on target areas
- Effective radius: 150m
- Requires enemy faction to have CAS (Close Air Support) aircraft
- Balanced against carpet bombs (50/50 weighting at tier 10)
- Fast response time

**CAS (Close Air Support)** (Tier dependent):
- Attack aircraft with loiter time
- Targets specific units or areas
- Can engage multiple targets during its patrol
- Effective radius: 3000m patrol area
- Requires enemy faction to have CAS aircraft
- More persistent than single airstrikes

**Carpet Bombs** (Tier dependent, requires "Unfair Supports" parameter):
- Massive area denial bombardment
- Effective radius: 200m
- Requires "Unfair Supports" parameter to be enabled
- Balanced against airstrikes (50/50 weighting at tier 10)
- Devastating but resource-intensive

**SAMs (Surface to Air Missiles)** (Tier dependent):
- Anti-aircraft defense systems
- Targets player aircraft and helicopters
- Requires enemy faction to have SAM capabilities (some factions don't have SAMs)
- Balanced against ASF (Air Superiority Fighters) if available

**Tank Support** (Tier dependent):
- Armored vehicle reinforcement
- Targets specific threats
- Provides heavy firepower on the ground
- Balanced against CAS support

**Orbital Strikes** (Rare, requires "Futuristic Supports" parameter):
- Massive area destruction
- Effective radius: 300m
- **Destroys cities within 200m** - extremely dangerous
- Requires "Futuristic Supports" parameter to be enabled
- Very rare and resource-intensive

### When Support is Called

**Automatic calls:**
- Garrison defenders automatically call for support when:
  - They detect enemy threats (damage or spotting events)
  - The threat level exceeds a random threshold
  - They have appropriate support types available

**Support availability:**
- Based on war tier (higher tiers unlock more support types)
- Based on faction capabilities (not all factions have all support types)
- Based on resource pools (enemies have limited resources)
- Some supports require specific parameters (Unfair/Futuristic Supports)

**Support call mechanics:**
- Enemy units "call for support" by temporarily reducing their combat effectiveness (simulating radio communication)
- Support calls take 10-15 seconds (scaled by player count)
- Support types are selected based on:
  - Target type (air vs ground)
  - Distance to target
  - Available support types
  - Resource pool limits

**Support reveal:**
- Radio towers and decryption keys can reveal incoming support calls
- Higher reveal values provide more information about support type, timing, and target location
- Intercepted communications give you advance warning

## Major Attacks

Major attacks are large-scale offensive operations that enemies launch against your territory. These are separate from QRFs and support calls.

**Attack resource pool:**
- Enemies accumulate attack resources over time
- Resource generation rate depends on war tier and difficulty settings
- Attacks are launched when resources reach sufficient levels

**Attack types:**
- **Standard attacks**: Target your outposts, resources, factories, or seaports
- **Punishment attacks** (Invaders only): Target your cities—if successful, they **destroy the entire city**, killing all civilians
- **Special operations**: Triggered if enemies know your HQ location

**Attack timing:**
- Attacks are scheduled based on resource accumulation
- Small intel can reveal time until next attack
- Higher aggression levels increase attack frequency

## HQ Knowledge and Special Operations

If enemies discover your HQ location, they may launch special operations:

- **Increased threat**: Enemies will prioritize attacking your HQ
- **Special mission types**: "Defend Petros" missions may spawn
- **Persistent pressure**: Enemies will continue targeting your HQ until you relocate or eliminate the threat

**How enemies discover HQ:**
- If you drag enemies back to HQ
- If enemies spot your HQ during operations
- Through certain mission failures or events

## Key Differences: QRF vs Support Calls

**QRFs (Quick Reaction Forces):**
- **Purpose**: Reinforce and recapture locations
- **Type**: Troop reinforcements (vehicles + infantry)
- **Trigger**: Automatic when attacking enemy locations
- **Behavior**: Travel to location, engage, attempt to recapture
- **Timeout**: 30 minutes
- **Resource pool**: Defense pool

**Support Calls:**
- **Purpose**: Force multiplier for existing defenders
- **Type**: Firepower (artillery, air strikes, etc.)
- **Trigger**: Called by garrison defenders during combat
- **Behavior**: Strike target area/units, then complete
- **Duration**: Varies by type (instant for strikes, minutes for CAS)
- **Resource pool**: Defense pool (for garrison support)

**Both systems:**
- Scale with war tier (more powerful at higher tiers)
- Scale with aggression (more frequent at higher aggression)
- Cost enemy resources
- Can be revealed through radio towers and intel

## Strategy Tips

1. **Expect QRFs**: Always plan for enemy reinforcements when attacking locations—have AT and AA ready
2. **Speed matters**: Finish captures quickly before QRFs arrive
3. **Defeat QRFs**: Eliminating QRFs gives you breathing room—focus fire on transport vehicles first
4. **Watch for support**: Listen for artillery/mortar impacts and watch the skies for aircraft
5. **Control radio towers**: They reveal incoming support calls, giving you advance warning
6. **Use decryption keys**: Intel-provided keys let you intercept enemy communications
7. **Manage aggression**: Higher aggression means faster, more frequent responses—sometimes it's worth letting it decay
8. **Prepare for punishment**: If playing against Invaders, always be ready to defend cities from punishment attacks
9. **Protect your HQ**: Don't let enemies discover your HQ location—it triggers special operations
10. **Time your attacks**: Use intel to time attacks when enemy resources are low

## Technical Details

**Code references:**
- `fn_SUP_QRFAir.sqf` - Air QRF setup and spawning
- `fn_SUP_QRFLand.sqf` - Land QRF setup and spawning
- `fn_SUP_QRFRoutine.sqf` - QRF behavior and timeout logic
- `fn_initSupports.sqf` (lines 34-57) - Support type definitions and availability
- `fn_requestSupport.sqf` - Support call request system
- `fn_garrisonLocal_enemyInfo.sqf` - Garrison support call logic
- `fn_callForSupport.sqf` - Unit-level support call mechanics

