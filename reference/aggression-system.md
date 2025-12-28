# Aggression System

The Aggression System is a core mechanic in Antistasi that tracks how much the enemy factions (Occupants and Invaders) are targeting your rebellion. Understanding how aggression works is crucial for managing enemy threat levels and planning your operations.

## Overview

Aggression is tracked separately for both **Occupants** and **Invaders** on a scale from **0 to 100**. Higher aggression means the enemy will respond more aggressively to your actions, launch more frequent attacks, and have faster response times.

## Aggression Levels

Aggression is displayed in two ways:

1. **Aggression Value** (0-100): The raw numerical value showing current enemy hostility
2. **Aggression Level** (1-5): A tiered level system calculated from the value:
   - Level 1: 0-20 aggression
   - Level 2: 21-40 aggression
   - Level 3: 41-60 aggression
   - Level 4: 61-80 aggression
   - Level 5: 81-100 aggression

When aggression crosses level boundaries, you'll receive a notification message indicating the level change for the affected faction.

## How Aggression Increases

Aggression increases when you perform hostile actions against the enemy:

### Killing Enemy Units

- **Normal enemy kills**: +0.5 aggression for 45 minutes
- **Killing surrendered units**: +20 aggression for 30 minutes (significant penalty)
  - Surrendered units are identified by having no weapons
  - This is considered a war crime and heavily penalized
  - Also reduces city support by 2 points

### Capturing Locations

Capturing strategic locations adds aggression based on the location type:

- **Airbases**: +20 aggression for 120 minutes
- **Seaports**: +20 aggression for 120 minutes
- **Outposts**: +20 aggression for 120 minutes
- **Resources**: +20 aggression for 120 minutes
- **Factories**: +20 aggression for 120 minutes
- **Cities**: +10 aggression for 120 minutes

### Completing Missions

Different mission types add varying amounts of aggression:

- **Traitor missions**: +15 aggression (normal) or +30 aggression (difficult) for 120 minutes
- **Bank heist missions**: +10 aggression for 120 minutes
- **Destroy missions** (antennas): +10 aggression for 120 minutes
- **Other mission types**: Varies by mission

### Other Actions

- **Killing civilians**: +10 aggression for 60 minutes (or +30 if it's a journalist)
- **Vehicle captures/destruction**: Varies based on vehicle type and value

## Aggression Decay

Aggression doesn't stay at maximum forever. The system uses a **decay mechanism**:

- Each aggression boost has a **duration** (measured in minutes)
- Over time, the aggression value gradually decreases back toward zero
- The decay rate is calculated automatically based on the initial boost amount and duration
- Multiple aggression sources stack together, and each decays independently

The decay happens every minute as part of the game's update loop. Temporary boosts from actions will fade over time, allowing aggression to naturally decrease if you avoid further hostile actions.

## Effects of High Aggression

Higher aggression levels have significant gameplay impacts:

### Enemy Resource Generation

- **Defense resources**: Higher aggression increases the rate at which enemies generate defense resources (used to reinforce garrisons)
- **Attack resources**: Higher aggression increases the rate at which enemies generate attack resources (used to launch attacks against you)
- The multiplier formula: `1.0 + (aggression / 200)` for single-enemy modes, or `0.5 + (aggression / 200)` for multi-enemy modes

### Enemy Support Availability

Aggression affects what support types enemies can call:

- **Artillery support**: Available at aggression level 5+ (tier 5 = 81-100 aggression)
- **Airstrikes**: Available at aggression level 10+ (requires war tier 3+ and aggression level 10)
- Higher aggression also affects the **response time** for enemy support calls—they arrive faster when aggression is high

### Attack Frequency

- Higher aggression means enemies generate attack resources faster
- This leads to more frequent enemy attacks on your positions
- Enemy attacks become more likely and happen more often as aggression increases

### Response Times

- Enemy units respond faster to your actions when aggression is high
- Reinforcement convoys arrive more quickly
- Enemy patrols become more alert and aggressive

## Player Count Scaling

Aggression values are automatically adjusted based on the number of active players:

- Aggression gains are divided by the player scale factor
- This prevents small groups from being overwhelmed by aggression designed for larger teams
- The scaling ensures balanced gameplay regardless of player count

## Managing Aggression

**Strategies for keeping aggression low:**

- Avoid killing surrendered enemies (major penalty)
- Space out your attacks to allow aggression to decay
- Complete missions that reduce aggression (like POW rescues or refugee evacuations)
- Focus on stealth and undercover operations when possible

**When high aggression is acceptable:**

- You're ready to defend against counterattacks
- You have strong defensive positions
- You're in late game with sufficient resources
- You're intentionally drawing enemy attention to create opportunities elsewhere

## Technical Details

- Aggression is calculated server-side and synchronized to all clients
- The system uses a "stack" approach where each aggression source is tracked separately
- Aggression updates occur every minute as part of the game's main loop
- The system prevents simultaneous aggression changes to avoid conflicts

