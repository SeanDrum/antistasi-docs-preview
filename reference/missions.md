# Missions Reference

This guide provides detailed information about all missions available in Antistasi, including objectives, rewards, and strategic considerations. All values are extracted directly from the game code.

## Understanding Mission Rewards

### Player Score

**Player Score** is a personal progression system that tracks your individual performance. Each point of score you earn:

- **Converts to personal money**: In multiplayer, each score point gives you **10 €** in personal money (points × 10)
- **Tracks mission completion**: Earning 10 or more points from a mission counts as a completed mission for your statistics
- **Is saved between sessions**: Your total score persists when you leave and rejoin the campaign

Player Score rewards are awarded to all players within 500 meters of the mission objective when it's completed, while Commander Score is awarded separately to the commander role.

### Commander Score

**Commander Score** is awarded only to the player with the commander role. It functions identically to Player Score (10 € per point, tracks mission completion, is saved) but is tracked separately and represents the commander's leadership contribution to mission success.

### Difficulty Levels

Missions have a chance to be **"difficult"** based on your war tier, with higher war tiers increasing the likelihood. Difficult missions are not just more rewarding—they are actually harder to complete:

- **Shorter time limits**: Difficult missions typically have **30 minute** time limits instead of 60-120 minutes, giving you less time to complete objectives
- **More enemy defenders**: Difficult missions spawn additional enemy units (e.g., Kill The Officer gets 4 extra bodyguards on difficult)
- **Stronger enemy units**: Difficult missions use more elite unit types (e.g., gunboats instead of transport boats, squad groups instead of police patrols, sentry groups instead of police groups)
- **Faster enemy response**: Enemy reinforcements and patrols arrive more quickly on difficult missions (e.g., Refugees Evac enemy patrols spawn after 5 minutes instead of 5-35 minutes)
- **Tighter spawn conditions**: Some missions have stricter requirements on difficult (e.g., Destroy Heli spawns closer to the objective at 2000m instead of 3000m, making it more dangerous)
- **Longer hold requirements**: Missions requiring you to hold positions need longer hold times on difficult (e.g., City Supplies requires 4 minutes instead of 2 minutes)
- **More aggressive enemy behavior**: Difficult missions trigger more immediate enemy actions (e.g., Destroy Vehicle enemies immediately add the vehicle to their group instead of waiting to detect players first)

In exchange for this increased difficulty, difficult missions provide **higher rewards**—typically 1.5x to 2x the normal reward values for money, player scores, and commander scores.

### Mission Scoring Notes

- **Money rewards** from missions are added directly to faction resources (shared money)
- **HR rewards** from missions are added directly to faction HR pool
- **Enemy Aggression** values show changes to enemy threat levels with duration (e.g., "+10 for 120 minutes" means aggression increases by 10 points for 120 minutes, then decays)
- **Next Enemy Attack** values indicate how mission outcomes affect timing of enemy counterattacks on specific markers
- **Town Support** changes apply to the nearest town or the mission's objective town, depending on the mission type
- **Difficulty** is determined by war tier: missions have an increasing chance to be "difficult" as war tier increases

## Table of Contents

- [Assassination Missions](#assassination-missions)
- [Spec Ops](#spec-ops)
- [Conquest Missions](#conquest-missions)
- [Convoy Missions](#convoy-missions)
- [Destroy Missions](#destroy-missions)
- [Logistics Missions](#logistics-missions)
- [Rescue Missions](#rescue-missions)
- [Dynamically Spawned Missions](#dynamically-spawned-missions)
- [Support Missions](#support-missions)

---

## Assassination Missions

### Kill The Officer

**Description:** Eliminate a high-ranking enemy officer who is patrolling a hostile area. Officers are typically protected by bodyguards, and the mission difficulty increases with war tier. Successfully eliminating the officer disrupts enemy command structure and delays their operations.

**How to Complete:** An enemy officer spawns at the mission location with bodyguards (1 bodyguard on normal difficulty, 5 total on difficult). The officer leads a patrol group that moves around the area. You must locate and kill the officer before the time limit expires.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: 30 minute delay (normal) / 60 minute delay (difficult)
- **Enemy Aggression**: -
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 30/60 minutes sooner (normal/difficult)
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Kill The Traitor

**Description:** A civilian informant has been discovered working for the enemy. You must eliminate them before they can report on rebel activities. This mission is time-sensitive and failure can trigger enemy retaliation.

**How to Complete:** A traitor spawns inside a building in the target location with 2 bodyguards. After 15 seconds, a vehicle spawns nearby. The traitor will attempt to escape in the vehicle if detected. You must kill the traitor before they escape or before the time limit expires. If the traitor escapes in the vehicle, the mission fails and enemy knowledge of your HQ location increases.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +15 for 120 minutes (normal) / +30 for 120 minutes (difficult) (Occupants)
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 5 points (normal) / 10 points (difficult)

**Failed: Mission Expired:**
- **Money**: -30% of current resources
- **HR**: -30% of current HR
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

**Failed: Traitor Escaped:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Outcome**: Increases enemy knowledge of HQ location (may trigger Defend Petros mission)
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

## Spec Ops

**Description:** Special operations missions involve infiltrating enemy-held territory and capturing a strategic location (airport, city, or outpost). These missions require you to flip the location to rebel control within the time limit.

**How to Complete:** Capture the target location marker (airport, city, or outpost) by flipping it to rebel control. This typically requires eliminating all enemy forces in the area and capturing the location's flag/control point. You must complete this before the time limit expires.

**Success:**
- **Money**: 200 € (normal) / 300 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 60 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult)
- **Commander Score**: 10 points (normal) / 15 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

## Conquest Missions

### Resource Acquisition / Take The Outpost

**Description:** Capture and secure an enemy-held outpost or resource site. These missions are essential for expanding your territorial control and securing additional income sources. You'll need to eliminate the enemy garrison and hold the location long enough to capture the flag.

**How to Complete:** Capture the target marker (outpost, resource site, or control point) by flipping it to rebel control. You must capture the location before the time limit expires.

**Success:**
- **Money**: 200 € (normal) / 400 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

## Convoy Missions

### Ammo Convoy

**Description:** Intercept an enemy ammunition supply convoy traveling between bases. Successfully ambushing the convoy provides you with valuable ammunition supplies and disrupts enemy logistics.

**How to Complete:** An enemy convoy spawns at the origin location after a delay. The convoy consists of an ammo truck escorted by military vehicles and travels along roads to the destination. You must intercept and destroy or capture the ammo truck before it reaches the destination.

**Success:**
- **Money**: 300 € (normal) / 450 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult)
- **Commander Score**: 10 points (normal) / 15 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Armored Convoy

**Description:** Attack a heavily guarded enemy convoy transporting armored vehicles or military equipment. These convoys are well-protected but offer significant rewards if successfully intercepted.

**How to Complete:** An enemy convoy spawns at the origin location after a delay. The convoy consists of an anti-air vehicle (AA) being transported, escorted by military vehicles. The convoy travels along roads to the destination. You must intercept and destroy or capture the AA vehicle before it reaches the destination.

**Success:**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult)
- **Commander Score**: 10 points (normal) / 15 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Money Convoy

**Description:** Ambush a convoy transporting enemy funds. These missions provide substantial monetary rewards but are heavily guarded. The financial gain can significantly boost your campaign resources.

**How to Complete:** An enemy convoy spawns at the origin location after a delay. The convoy consists of a civilian supply truck (carrying money) escorted by military vehicles. The convoy travels along roads to the destination. You must intercept the money truck and drive it to your HQ (within 50 meters) before the time limit expires. If you destroy the truck instead of delivering it, you get a partial success reward.

**Success - Full Completion (Reached HQ):**
- **Money**: 5000 € (normal) / 7500 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult)
- **Commander Score**: 10 points (normal) / 15 points (difficult)

**Success - Partial (Destroyed but not delivered):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +5 for 60 minutes
- **Player Score**: 5 points (normal) / 7.5 points (difficult, rounded)
- **Commander Score**: 5 points (normal) / 7.5 points (difficult, rounded)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Prisoner Convoy

**Description:** Intercept a convoy transporting prisoners of war. Successfully rescuing these prisoners provides you with additional HR and money rewards per prisoner rescued.

**How to Complete:** An enemy convoy spawns at the origin location after a delay. The convoy consists of a truck carrying prisoners escorted by military vehicles. The convoy travels along roads to the destination. You must intercept the truck and capture it (by having a player in the driver seat). Once captured, prisoners will exit and you must escort them to your HQ (within 50 meters). Each prisoner that reaches HQ alive provides rewards. If all prisoners die or the convoy reaches its destination, the mission fails.

**Success:**
- **Money**: 300 € per prisoner (normal) / 450 € per prisoner (difficult)
- **HR**: 1 per prisoner rescued
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 0.5 points per prisoner (normal) / 0.75 points per prisoner (difficult, rounded)
- **Commander Score**: 0.5 points per prisoner (normal) / 0.75 points per prisoner (difficult, rounded)

**Failure - Prisoners Killed:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +20 for 120 minutes
- **Player Score**: -
- **Commander Score**: -10 points

**Failure - Convoy Arrived:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Reinforcements Convoy

**Description:** Attack an enemy convoy bringing reinforcements to a contested area. Preventing these reinforcements from reaching their destination weakens enemy positions and delays their offensive capabilities.

**How to Complete:** An enemy convoy spawns at the origin location after a delay. The convoy consists of a truck carrying reinforcements escorted by military vehicles. The convoy travels along roads to the destination. You must intercept and destroy the convoy before it reaches the destination.

**Success:**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult)
- **Commander Score**: 10 points (normal) / 15 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

## Destroy Missions

### Steal Or Destroy Armor

**Description:** Infiltrate an enemy airbase and either steal or destroy a heavily armored vehicle (anti-air vehicle). Successfully completing this mission denies the enemy valuable assets and can provide you with advanced equipment if you choose to steal rather than destroy.

**How to Complete:** An anti-air vehicle spawns at the target airbase once you get close enough (when the marker spawns). On normal difficulty, the vehicle crew will only enter and operate the vehicle if they detect players nearby. On difficult difficulty, the crew immediately enters the vehicle. You must either destroy the vehicle or steal it by having a player enter it before the time limit expires.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +5 for 60 minutes
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Steal Or Destroy Heli

**Description:** Attack an enemy airbase to steal or destroy an enemy helicopter. Helicopters provide significant tactical advantages, so denying them to the enemy is strategically valuable.

**How to Complete:** A crashed helicopter spawns at a location near the target airbase (damaged at 80% health). The crash site is surrounded by sandbags and may have an ammo box nearby (for non-attack helicopters). Enemy forces guard the crash site. You must either destroy the crashed helicopter or repair and steal it before the time limit expires. If it's an attack helicopter and you fail, there are additional timing penalties.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)
- **Note**: If it was an attack helicopter, additional timing penalty applies

---

### Destroy Antenna

**Description:** Destroy an enemy radio tower (antenna) to disrupt their communications network. Destroyed radio towers increase the effectiveness of your hearts-and-minds operations in nearby towns.

**How to Complete:** An enemy radio tower (antenna) exists at the target location. You must destroy the antenna before the time limit expires. The antenna is destroyed when it's no longer alive or when the marker is captured by rebels.

**Success:**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

## Logistics Missions

### Bank Mission

**Description:** Rob an enemy-controlled bank to secure a large cash payout. This mission provides substantial financial resources but comes with significant risk. A truck must be driven near the bank to start a countdown timer.

**How to Complete:** A civilian supply truck spawns at your HQ. Drive the truck to the bank building (within the bank's bounding box distance). Once close enough, a 120 second (normal) or 240 second (difficult) countdown begins. The truck must remain within range of the bank during the entire countdown. After the countdown completes, drive the truck back to your HQ (within 50 meters) to complete the mission and receive the money.

**Success:**
- **Money**: 5000 € (normal) / 10000 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes (Occupants)
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Salvage Supplies

**Description:** Retrieve supplies from a wrecked ship near a seaport. These missions provide resources without the heavy combat of other logistics operations.

**How to Complete:** Three salvage locations are marked in the water near the seaport. When you get close enough, a wrecked ship spawns at one of the three locations with a supply crate (equipment box) in the water. An enemy patrol boat guards the area. You must retrieve the crate (use the rope action to lift it, then transport it to your HQ). The crate can contain weapons, ammunition, or medical supplies.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 5 points (normal) / 10 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

### Steal Or Destroy Ammo Truck

**Description:** Infiltrate an enemy outpost to steal or destroy an ammunition supply truck. Successfully capturing the truck provides you with valuable ammunition resources.

**How to Complete:** An ammo truck spawns at the target outpost once you get close enough. The truck is guarded by enemy patrols. You must either destroy the truck or steal it by entering it and driving it back to your HQ (within 100 meters). The truck is pre-filled with ammunition supplies.

**Success:**
- **Money**: 300 € (normal) / 600 € (difficult)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 10 points (normal) / 20 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

## Rescue Missions

### POW Rescue

**Description:** Infiltrate an enemy-held location (typically an outpost or airbase) to rescue prisoners of war. Each rescued prisoner joins your cause, providing HR and boosting morale. Successfully rescuing POWs increases support in the nearest city.

**How to Complete:** Prisoners spawn at building positions within the target location. Interact with each prisoner using the flag action to free them. Once freed, prisoners will follow you. Escort all prisoners to your HQ (within 50 meters). Each prisoner that reaches HQ alive provides rewards. If all prisoners die, the mission fails.

**Success:**
- **Money**: 100 € per prisoner (normal) / 200 € per prisoner (difficult)
- **HR**: 2 per prisoner rescued
- **Town Support**: +2 per prisoner in nearest city (normal) / +4 per prisoner (difficult)
- **Next Enemy Attack**: -
- **Enemy Aggression**: -1.5 per prisoner for 90 minutes (Occupants)
- **Player Score**: 1 point per prisoner
- **Commander Score**: 0.5 points per prisoner (normal) / 1 point per prisoner (difficult, rounded)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

### Refugees Evac

**Description:** Evacuate civilian refugees from a dangerous area, typically a city under threat. Successfully evacuating refugees provides HR and humanitarian benefits.

**How to Complete:** Refugees spawn at building positions within the target city. Interact with each refugee using the flag action to free them. Once freed, refugees will follow you. Escort all refugees to your HQ (within 50 meters). Each refugee that reaches HQ alive provides rewards. Enemy patrols may guard the area, and for Invader-controlled cities, additional QRF reinforcements may arrive after a delay.

**Success:**
- **Money**: 100 € per refugee (normal) / 200 € per refugee (difficult)
- **HR**: 1 per refugee
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 1 point per refugee (normal) / 2 points per refugee (difficult)
- **Commander Score**: 0.5 points per refugee (normal, rounded) / 1 point per refugee (difficult, rounded)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

## Dynamically Spawned Missions

These missions are spawned automatically by the game based on campaign events and cannot be requested directly from Petros.

### Defend Petros

**Description:** Your headquarters (HQ) is under attack by enemy forces. You must defend Petros and the HQ location from the assault. This mission spawns automatically when HQ comes under threat. Success is critical—failing this mission results in severe penalties, including the potential loss of Petros.

**How to Complete:** Enemy forces attack your HQ marker. You must defend the location and prevent Petros from being killed. The mission ends when either Petros dies (failure) or the attack is repelled (success). Player score is only awarded if combat occurs within 500 meters of the HQ. If you fail, you lose 90% of your money and HR, and Petros is killed.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 60 minutes (attacking side)
- **Player Score**: 10 points (if fought within 500m of HQ)
- **Commander Score**: -

**Failure:**
- **Money**: -90% of current resources
- **HR**: -90% of current HR
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -
- **Additional Penalties**: Petros is killed, HQ may need to be relocated

---

### Tower Rebuild Disrupt

**Description:** The enemy is attempting to rebuild a destroyed radio tower. You must disrupt the reconstruction effort before they can restore their communications network. These missions appear automatically when the enemy begins reconstruction work.

**How to Complete:** A repair truck with crew spawns near a destroyed radio tower. The truck attempts to reach the tower to repair it. You must destroy the repair truck or capture the tower location (flip it to rebel control) before the time limit expires. If you fail, the tower is successfully rebuilt by the enemy.

**Success:**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +15 for 90 minutes (Occupants), +5 for 60 minutes (Invaders)
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points
- **Additional Penalties**: The radio tower is successfully rebuilt

---

## Support Missions

### City Supplies

**Description:** Deliver supplies to a friendly or neutral city to increase the population's support for your rebellion. This is a hearts-and-minds operation that helps build support in towns where you're trying to gain influence. The mission targets cities with low rebel support (below 80%).

**How to Complete:** A supply crate spawns at your HQ. Load the crate into a truck (using the logistics system), then drive the truck to within 40 meters of the target city marker. Once there, the crate must be unloaded (not attached/roped to the truck). Then defend the crate with at least one friendly player within 80 meters, ensuring no enemy units are within 50 meters, for 120 seconds (normal) or 240 seconds (difficult). If enemies get too close or you move too far away, the timer resets.

**Success:**
- **Money**: -
- **HR**: 0
- **Town Support**: +15 (normal) / +30 (difficult) in objective town
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 10 points (normal) / 20 points (difficult)
- **Commander Score**: 5 points (normal) / 10 points (difficult)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

## Mission Rewards Summary Table

The following table summarizes all mission rewards and penalties. Values are shown as "normal / difficult" where applicable. A dash (-) indicates no change.

| Mission | Success: Money | Success: HR | Success: Town Support | Success: Enemy Aggression | Success: Player Score | Success: Commander Score | Failure: Commander Score | Notes |
|---------|----------------|-------------|----------------------|---------------------------|----------------------|-------------------------|--------------------------|-------|
| **Kill The Officer** | 300 / 600 € | 0 | - | - | 10 / 20 | 10 / 20 | -10 | Next Enemy Attack: +30 / +60 min delay on success; -30 / -60 min sooner on failure |
| **Kill The Traitor** | 300 / 600 € | 0 | - | +15 / +30 for 120 min (Occupants) | 10 / 20 | 5 / 10 | -10 | Mission Expired failure: -30% money and HR. Traitor Escaped: May trigger Defend Petros |
| **Spec Ops** | 200 / 300 € | 0 | - | +10 for 60 min | 10 / 15 | 10 / 15 | -10 | Uses 1.5x bonus multiplier |
| **Resource Acquisition / Take The Outpost** | 200 / 400 € | 0 | - | - | 10 / 20 | 10 / 20 | -10 | - |
| **Ammo Convoy** | 300 / 450 € | 0 | - | +10 for 120 min | 10 / 15 | 10 / 15 | -10 | Uses 1.5x bonus multiplier |
| **Armored Convoy** | - | 0 | - | +10 for 120 min | 10 / 15 | 10 / 15 | -10 | Uses 1.5x bonus multiplier |
| **Money Convoy** | 5000 / 7500 € | 0 | - | +10 for 120 min | 10 / 15 | 10 / 15 | -10 | Uses 1.5x bonus multiplier. Partial success (destroyed): +5 agg for 60 min, 5 / 7.5 scores |
| **Prisoner Convoy** | 300 / 450 € per POW | 1 per POW | - | +10 for 120 min | 0.5 / 0.75 per POW | 0.5 / 0.75 per POW | -10 | Uses 1.5x bonus multiplier. Prisoners killed failure: +20 agg for 120 min |
| **Reinforcements Convoy** | - | 0 | - | +10 for 120 min | 10 / 15 | 10 / 15 | -10 | Uses 1.5x bonus multiplier |
| **Steal Or Destroy Armor** | 300 / 600 € | 0 | - | +5 for 60 min | 10 / 20 | 10 / 20 | -10 | - |
| **Steal Or Destroy Heli** | 300 / 600 € | 0 | - | - | 10 / 20 | 10 / 20 | -10 / -20 | Attack helicopter failure has additional timing penalty |
| **Destroy Antenna** | - | 0 | - | +10 for 120 min | 10 / 20 | 10 / 20 | -10 / -20 | - |
| **Bank Mission** | 5000 / 10000 € | 0 | - | +10 for 120 min (Occupants) | 10 / 20 | 10 / 20 | -10 | - |
| **Salvage Supplies** | 300 / 600 € | 0 | - | - | 10 / 20 | 5 / 10 | -10 / -20 | - |
| **Steal Or Destroy Ammo Truck** | 300 / 600 € | 0 | - | - | 10 / 20 | 10 / 20 | -10 | - |
| **POW Rescue** | 100 / 200 € per POW | 2 per POW | +2 / +4 per POW | -1.5 per POW for 90 min (Occupants) | 1 per POW | 0.5 / 1 per POW | -10 / -20 | Reduces enemy aggression |
| **Refugees Evac** | 100 / 200 € per refugee | 1 per refugee | - | -10 for 60 min (Occupants) | 1 / 2 per refugee | 0.5 / 1 per refugee | -10 / -20 | Reduces enemy aggression |
| **Defend Petros** | - | - | - | +10 for 60 min | 10* | - | - | Success: Only if fought within 500m of HQ. Failure: -90% money and HR, Petros killed |
| **Tower Rebuild Disrupt** | - | 0 | - | +15 for 90 min (Occupants), +5 for 60 min (Invaders) | 10 | 10 | -10 | Failure: Tower is rebuilt |
| **City Supplies** | - | 0 | +15 / +30 | -10 for 60 min (Occupants) | 10 / 20 | 5 / 10 | -10 / -20 | - |

\* Player Score only awarded if mission was fought within 500 meters of HQ
