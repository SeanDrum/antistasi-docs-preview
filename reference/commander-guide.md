# Commander Guide

This guide covers features exclusive to the Commander role. Regular players and members do not have access to these functions.

## What is the Commander?

One player is designated as Commander (stored in the `theBoss` variable). The Commander is elected automatically based on rank and member status. Members have priority over guests in elections, and higher rank provides higher election priority. The Commander can resign eligibility to allow re-election.

The Commander automatically receives all role traits (medic, engineer, builder, stealth bonuses, better stamina, explosives specialist, and UAV hacking). These traits override any selected role until the Commander loses their position.

## Commander-Only Actions

### 1. Training FIA/Garrison Units

The Commander can spend faction money to train garrison and recruited units. Training increases the `skillFIA` variable, which starts at 1 and has a maximum of 20.

**Training Cost Formula:**
- Base cost: 1000
- Additional cost: 1.5 × current skillFIA × 750
- Total cost: 1000 + (1.5 × skillFIA × 750)

**Training Limitations:**
- Training cannot exceed twice the current war tier (skillFIA cannot exceed tierWar × 2)
- Each training level increases unit skill by 0.015
- Base unit skill calculation: 0.1 + (0.1 × skillMultiplier) + (0.015 × skillFIA)
- Training also increases recruitment costs proportionally (cost increases by skillFIA/280 per level)

**Benefits:**
- Makes AI defenders more effective in combat
- Improves garrison unit performance
- Applies to all garrison and recruited FIA units

### 2. Move Headquarters (HQ)

The Commander can relocate HQ to any valid location on the map. During the move, Petros joins the Commander's group and follows them.

**Requirements:**
- Commander must be eligible and active
- Petros must not be incapacitated or attached to another object
- New location must be in valid territory (not too close to enemies)

**Effects:**
- HQ movement is tracked by enemies—they remember old locations
- Moving HQ reduces but doesn't eliminate enemy HQ knowledge
- Garrison is cleared and must be re-established at the new location
- All HQ objects (flag, vehicle box, arsenal, etc.) are relocated automatically

### 3. Manage Garrisons

The Commander has access to a garrison management interface at HQ that allows them to:

- **Add AI squads** to captured locations (outposts, resources, factories, seaports, airbases)
- **Remove units** from garrisons
- **Assign static weapons** to garrisons
- **View garrison strength** and composition

**Strategic Importance:**
- Garrison strength directly affects defense success against enemy attacks
- Larger and more strategic locations need stronger garrisons
- Properly garrisoned locations are essential for holding territory
- Garrisons can be built up from High Command squads or recruited units

### 4. Sell Vehicles

The Commander can sell faction vehicles for money, which returns funds to the shared faction resource pool.

**Requirements:**
- Vehicle must be at a friendly location (HQ, outposts, airbases, seaports, factories, resources)
- Vehicle must be empty (no players in crew)
- Vehicle must be owned by the Commander or have no owner

**Value Calculation:**
- Value is proportional to vehicle condition (damage percentage)
- Formula: Base sell price × (1 - damage percentage)
- Vehicles with less than 10% damage return full value
- Different vehicle types have different base values (light vehicles: 100, helicopters: 500, tanks: 3000, etc.)

**Restrictions:**
- Cannot sell player-locked vehicles without override
- Static weapons are deleted rather than sold
- Some vehicle types cannot be sold (blacklisted assets)

### 5. Arsenal Limits Management

The Commander can set custom limits for guest players on specific items in the arsenal. This controls which equipment guests can take from the arsenal.

**Features:**
- Set per-item limits for guests
- Members and Commander ignore these limits (unlimited access)
- Limits persist across sessions
- Can reset limits to defaults
- Organized by item category (weapons, attachments, uniforms, etc.)

**Purpose:**
- Control resource allocation
- Prevent guests from depleting rare equipment
- Manage faction economy
- Balance gameplay for different player types

### 6. Members List Management

The Commander can add or remove players from the members list in multiplayer sessions.

**Member Benefits:**
- Unlimited arsenal access (ignores quantity limits)
- Can request missions from Petros
- Higher priority in Commander elections
- Member status persists across sessions

**Requirements:**
- Commander must have admin privileges or server command access
- Membership system must be enabled in parameters
- Target player must be online and valid

**Effects:**
- Adding a member grants them immediate privileges
- Removing a member revokes their privileges
- Member status is saved with the campaign

### 7. Call Fire Support

The Commander can request artillery strikes using faction bomb runs. Bomb runs accumulate over time from controlled airbases.

**Bomb Run Accumulation:**
- Each controlled airbase provides 0.25 bomb runs per income tick (every ~10 minutes)
- Maximum bomb runs: 4 + (tierWar × 2)
- Bomb runs can also be gained by converting captured enemy aircraft at airbases

**Fire Support Types:**
- **Artillery strikes**: Point, barrage, suppression, or continuous fire missions
- **Airstrikes**: CAS (Close Air Support) runs using accumulated bomb runs
- Requires radio equipment to call
- Uses mortar units or aircraft available to the faction

**Strategic Use:**
- Soften enemy positions before assaults
- Defend against counterattacks
- Destroy enemy infrastructure
- Support major operations

### 8. Persistent Save

The Commander can manually trigger a persistent save of the current campaign state to the server.

**When to Use:**
- Before risky operations
- Before server restarts
- After major campaign milestones
- When significant progress has been made

**What Gets Saved:**
- All player data and positions
- Campaign state (markers, garrisons, resources)
- Faction data and relationships
- Arsenal contents and limits
- Mission states and progress
- All persistent variables

**Note:** The game also has automatic saves at regular intervals, but manual saves ensure critical moments are preserved.

### 9. Garbage Cleaning

The Commander can clean up map-wide garbage (dead bodies, wrecks, abandoned equipment) to improve performance on long-running campaigns.

**Two Cleaning Options:**

1. **Map-Wide Clean:**
   - Removes all dead bodies, destroyed vehicles, weapon holders, and junk items
   - Only cleans objects far from active players and spawners (500+ meters)
   - Has a cooldown period between uses
   - Improves overall server performance

2. **HQ Area Clean:**
   - Faster cleanup focused on HQ area (100 meter radius)
   - Removes dead bodies, wrecks, and junk items near headquarters
   - Useful for keeping HQ area clear during active gameplay
   - Less performance impact than full map clean

**What Gets Cleaned:**
- Dead soldiers and civilians
- Destroyed vehicles and wrecks
- Weapon holders and dropped equipment
- Surrender crates (if far from players)
- Ejection seats and other debris
- Leaflets and propaganda items

### 10. Resign Commander

The Commander can toggle their eligibility for the Commander role, which triggers an election for a new Commander.

**How It Works:**
- Commander can resign eligibility at any time
- Resigning triggers automatic election
- New Commander is chosen by rank and member status
- Cannot resign in singleplayer (no other players to take over)

**Election Priority:**
- Members receive +1000 priority points
- Numeric rank adds to priority
- Highest priority eligible player becomes Commander
- AFK players are excluded from elections

**Effects:**
- Commander loses all Commander-only abilities
- Selected role traits take effect (if a role was previously selected)
- New Commander gains all Commander abilities automatically

## Commander Election System

Elections are automatically triggered when:

- No Commander exists
- Commander goes AFK (away from keyboard)
- Commander toggles eligibility (resigns)
- Commander disconnects from the server
- Member-only mode is enabled and current Commander is a guest

**Election Process:**
1. System checks all eligible players
2. Calculates priority: Member status (+1000) + Numeric rank
3. Excludes AFK and ineligible players
4. Highest priority player becomes Commander automatically
5. Previous Commander's High Command groups are transferred to new Commander

**Priority Calculation:**
- Members: Base rank + 1000 points
- Guests: Base rank only (if guest Commander is allowed)
- AFK players: Excluded
- Ineligible players: Excluded

## Commander Traits & Abilities

The Commander automatically receives all role traits, overriding any selected role:

**Combat Traits:**
- **Medic abilities**: Can perform advanced medical actions
- **Engineer abilities**: Can build, repair vehicles, and defuse mines
- **Builder system access**: Can construct fortifications
- **Explosives specialist**: Enhanced explosive handling

**Stealth & Mobility:**
- **0.8x visibility coefficient**: Harder for enemies to spot
- **0.8x audibility coefficient**: Makes less noise
- **1.4x load capacity**: Can carry more equipment without fatigue

**Special Abilities:**
- **UAV hacking**: Can hack enemy UAVs (rifleman trait)
- **All role benefits**: Combines advantages from multiple roles

**Important Notes:**
- Commander traits override selected role until Commander position is lost
- Selected role takes effect after losing Commander position
- Commander cannot manually change role traits while in command

## Info Bar (Commander View)

The Commander sees additional information in the persistent info bar at the top of the screen:

**Commander-Specific Display:**
- **Faction resources**: Shared money pool (resourcesFIA)
- **Available bomb runs**: Current count of available airstrike points
- **All standard info**: HR, personal money, aggression levels, war tier, undercover status

**Standard Info (All Players):**
- HR (Human Resources for recruiting)
- Personal money
- Aggression levels (Occupants and Invaders)
- War tier
- Faction names
- Undercover status

**Toggle:**
- Press Ctrl+F12 to show/hide the info bar
- Can also be toggled via the Player menu

The info bar provides real-time campaign status and is essential for strategic decision-making.


