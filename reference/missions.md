# Missions Reference

This guide provides detailed information about all missions available in Antistasi, including objectives, rewards, and strategic considerations. All values are extracted directly from the game code.

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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: 30 minute delay (via addTimeForIdle on marker)
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 600 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: 60 minute delay (via addTimeForIdle on marker)
- **Enemy Aggression**: -
- **Player Score**: 20 points
- **Commander Score**: 20 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 30/60 minutes sooner (normal/difficult, via addTimeForIdle)
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points

---

### Kill The Traitor

**Description:** A civilian informant has been discovered working for the enemy. You must eliminate them before they can report on rebel activities. This mission is time-sensitive and failure can trigger enemy retaliation.

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +15 for 120 minutes (Occupants)
- **Player Score**: 10 points
- **Commander Score**: 5 points

**Success (Difficult):**
- **Money**: 600 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +30 for 120 minutes (Occupants)
- **Player Score**: 20 points
- **Commander Score**: 10 points

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

**Success (Normal Difficulty):**
- **Money**: 200 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 60 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 300 € (200 * 1.5 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 60 minutes
- **Player Score**: 15 points (10 * 1.5 bonus)
- **Commander Score**: 15 points (10 * 1.5 bonus)

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

**Success (Normal Difficulty):**
- **Money**: 200 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 400 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 20 points
- **Commander Score**: 20 points

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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 450 € (300 * 1.5 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 15 points (10 * 1.5 bonus)
- **Commander Score**: 15 points (10 * 1.5 bonus)

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

**Success (Normal Difficulty):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 15 points (10 * 1.5 bonus)
- **Commander Score**: 15 points (10 * 1.5 bonus)

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

**Success - Full Completion (Reached HQ):**
- **Money**: 5000 € (normal) / 7500 € (difficult, 5000 * 1.5 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points (normal) / 15 points (difficult, 10 * 1.5 bonus)
- **Commander Score**: 10 points (normal) / 15 points (difficult, 10 * 1.5 bonus)

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

**Success:**
- **Money**: 300 € per prisoner (normal) / 450 € per prisoner (difficult, 300 * 1.5 bonus)
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

**Success (Normal Difficulty):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 15 points (10 * 1.5 bonus)
- **Commander Score**: 15 points (10 * 1.5 bonus)

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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +5 for 60 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 600 € (300 * 2 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +5 for 60 minutes
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 20 points (10 * 2 bonus)

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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 600 € (300 * 2 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 20 points (10 * 2 bonus)

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

**Success (Normal Difficulty):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: -
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 120 minutes
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 20 points (10 * 2 bonus)

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

**Success:**
- **Money**: 5000 € (normal) / 10000 € (difficult, 5000 * 2 bonus)
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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: 5 points

**Success (Difficult):**
- **Money**: 600 € (300 * 2 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 10 points (5 * 2 bonus)

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

**Success (Normal Difficulty):**
- **Money**: 300 €
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: 10 points

**Success (Difficult):**
- **Money**: 600 € (300 * 2 bonus)
- **HR**: 0
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 20 points (10 * 2 bonus)

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

**Success (Normal Difficulty - Occupants):**
- **Money**: 100 € per refugee
- **HR**: 1 per refugee
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 1 point per refugee
- **Commander Score**: 0.5 points per refugee (rounded)

**Success (Difficult - Occupants):**
- **Money**: 200 € per refugee (100 * 2 bonus)
- **HR**: 1 per refugee
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 2 points per refugee (1 * 2 bonus)
- **Commander Score**: 1 point per refugee (0.5 * 2 bonus, rounded)

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

**Success (Normal Difficulty):**
- **Money**: -
- **HR**: 0
- **Town Support**: +15 in objective town (scaled by city size and antenna status)
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 10 points
- **Commander Score**: 5 points

**Success (Difficult):**
- **Money**: -
- **HR**: 0
- **Town Support**: +30 in objective town (scaled by city size and antenna status)
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes (Occupants)
- **Player Score**: 20 points (10 * 2 bonus)
- **Commander Score**: 10 points (5 * 2 bonus)

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -
- **Commander Score**: -10 points (normal) / -20 points (difficult)

---

## Mission Scoring Notes

- **Player Score** and **Commander Score** values represent points awarded for mission completion
- Values shown as ranges (e.g., "10/20") indicate normal/difficult difficulty tiers
- **Enemy Aggression** values show changes to enemy threat levels with duration (e.g., "+10 for 120 minutes" means aggression increases by 10 points for 120 minutes, then decays)
- **Next Enemy Attack** values indicate how mission outcomes affect timing of enemy counterattacks on specific markers
- **Town Support** changes apply to the nearest town or the mission's objective town, depending on the mission type. Values are scaled based on city population size and antenna status
- **Difficulty** is determined by war tier: missions have a chance to be "difficult" based on `random 10 < tierWar`
- **Bonus multipliers** for difficult missions: Most missions use a 2x multiplier, but convoy missions and Spec Ops use 1.5x
- **Money rewards** from missions are added directly to faction resources (resourcesFIA)
- **HR rewards** from missions are added directly to faction HR pool
