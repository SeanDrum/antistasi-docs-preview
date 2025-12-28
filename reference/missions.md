# Missions Reference

This guide provides detailed information about all missions available in Antistasi, including objectives, rewards, and strategic considerations.

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

**Success:**
- **Money**: 300/600 € (standard/difficult)
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 30/40 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Kill The Traitor

**Description:** A civilian informant has been discovered working for the enemy. You must eliminate them before they can report on rebel activities. This mission is time-sensitive and failure can trigger enemy retaliation.

**Success:**
- **Money**: 300/600 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failed: Mission Expired:**
- **Money**: -30%
- **HR**: -30%
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10 points

**Failed: Traitor Escaped:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Outcome**: Triggers "Defend Petros" mission (or reveals some of your mines if Defend Petros is already active)
- **Enemy Aggression**: -
- **Player Score**: -

---

## Spec Ops

**Description:** Special operations missions involve infiltrating enemy-held territory to complete high-risk objectives. These missions typically require stealth and precision, targeting strategic enemy positions or assets.

**Success:**
- **Money**: 200/400 €
- **HR**: -
- **Town Support**: +5/+10 support in nearest town
- **Next Enemy Attack**: 10/20 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: 10/20 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: +5/+10 Occupier support in nearest town
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Conquest Missions

### Resource Acquisition / Take The Outpost

**Description:** Capture and secure an enemy-held outpost or resource site. These missions are essential for expanding your territorial control and securing additional income sources. You'll need to eliminate the enemy garrison and hold the location long enough to capture the flag.

**Success:**
- **Money**: 200/400 €
- **HR**: -
- **Town Support**: -5/-10 Occupier support in nearest town
- **Next Enemy Attack**: 10/20 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: +5/+10 Occupier support in nearest town
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Convoy Missions

### Ammo Convoy

**Description:** Intercept an enemy ammunition supply convoy traveling between bases. Successfully ambushing the convoy provides you with valuable ammunition supplies and disrupts enemy logistics.

**Success:**
- **Money**: 300/600 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 30/60 minute delay
- **Enemy Aggression**: +25 for 2 hours
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20/40 minutes sooner
- **Enemy Aggression**: -5 for 60 minutes
- **Player Score**: -10/-20 points

---

### Armored Convoy

**Description:** Attack a heavily guarded enemy convoy transporting armored vehicles or military equipment. These convoys are well-protected but offer significant rewards if successfully intercepted.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: +5/+10 support in nearest town
- **Next Enemy Attack**: 30/60 minute delay
- **Enemy Aggression**: +20 for 90 minutes
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20/40 minutes sooner
- **Enemy Aggression**: -5 for 60 minutes
- **Player Score**: -10/-20 points

---

### Money Convoy

**Description:** Ambush a convoy transporting enemy funds. These missions provide substantial monetary rewards but are heavily guarded. The financial gain can significantly boost your campaign resources.

**Success:**
- **Money**: 5000/10000 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20 minute delay
- **Enemy Aggression**: +25 for 2 hours
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20 minutes sooner
- **Enemy Aggression**: -5 for 60 minutes
- **Player Score**: -10/-20 points

---

### Prisoner Convoy

**Description:** Intercept a convoy transporting prisoners of war. Successfully rescuing these prisoners provides you with additional HR and increases support in nearby towns.

**Success:**
- **Money**: 300/600 € per prisoner
- **HR**: -
- **Town Support**: +10/+20 support in nearest town
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 2 hours
- **Player Score**: 1 point per POW
- **Commander Score**: 1 point per POW

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -10 for 60 minutes
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Reinforcements Convoy

**Description:** Attack an enemy convoy bringing reinforcements to a contested area. Preventing these reinforcements from reaching their destination weakens enemy positions and delays their offensive capabilities.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: +10/+20 support in nearest town
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 90 minutes
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -10 for 60 minutes
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Destroy Missions

### Steal Or Destroy Armor

**Description:** Infiltrate an enemy airbase and either steal or destroy a heavily armored vehicle. Successfully completing this mission denies the enemy valuable assets and can provide you with advanced equipment if you choose to steal rather than destroy.

**Success:**
- **Money**: 300/600 €
- **HR**: -
- **Town Support**: +10 support in nearest town if Occupier was target, or +5 if target was Invader
- **Next Enemy Attack**: 10/20 minute delay
- **Enemy Aggression**: +10 for 60 minutes
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -100/-200 €
- **HR**: -5/-10
- **Town Support**: Occupier gains 5/10 support in nearest town
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Steal Or Destroy Heli

**Description:** Attack an enemy airbase to steal or destroy an enemy helicopter. Helicopters provide significant tactical advantages, so denying them to the enemy is strategically valuable.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 30/60 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Destroy Antenna

**Description:** Destroy an enemy radio tower (antenna) to disrupt their communications network. Destroyed radio towers double the effectiveness of your hearts-and-minds operations in nearby towns, making this mission highly valuable for population support campaigns.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10 points

---

## Logistics Missions

### Bank Mission

**Description:** Rob an enemy-controlled bank to secure a large cash payout. This mission provides substantial financial resources but comes with significant risk. Note that simply approaching the bank with the required truck will trigger support penalties regardless of mission outcome.

**Important:** If you bring the truck for the Bank Mission close enough to the bank to start the countdown, you will lose 20 or 40 support depending on difficulty. The enemy will gain 10 or 20 support. This penalty applies just by starting the countdown—success or failure after that will not change the support further.

**Success:**
- **Money**: 5000/10000 €
- **HR**: -
- **Town Support**: See note above about approach penalty
- **Next Enemy Attack**: 30/60 minute delay
- **Enemy Aggression**: 20/40 for 2 hours
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Salvage Supplies

**Description:** Retrieve supplies from a wrecked or abandoned location, typically near seaports. These missions provide resources without the heavy combat of other logistics operations.

**Success:**
- **Money**: 300/600 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Steal Or Destroy Ammo Truck

**Description:** Infiltrate an enemy outpost to steal or destroy an ammunition supply truck. Successfully capturing the truck provides you with valuable ammunition resources.

**Success:**
- **Money**: 300 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10/20 minute delay
- **Enemy Aggression**: -
- **Player Score**: 10/20 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10/20 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Rescue Missions

### POW Rescue

**Description:** Infiltrate an enemy-held location (typically an outpost or airbase) to rescue prisoners of war. Each rescued prisoner joins your cause, providing HR and boosting morale. Successfully rescuing POWs significantly increases support in the city where they were held.

**Success:**
- **Money**: 100/200 € per POW
- **HR**: 2 per prisoner
- **Town Support**: Some support from city you rescued them from
- **Next Enemy Attack**: -
- **Enemy Aggression**: +1.5 per prisoner for 90 minutes
- **Player Score**: 1 point per POW
- **Commander Score**: 1 point per POW

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

### Refugees Evac

**Description:** Evacuate civilian refugees from a dangerous area, typically a city under threat. Successfully evacuating refugees provides HR and humanitarian benefits.

**Success:**
- **Money**: 100 € per refugee
- **HR**: 1 per refugee
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -10 for 60 minutes
- **Player Score**: 1/2 points per POW
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Dynamically Spawned Missions

These missions are spawned automatically by the game based on campaign events and cannot be requested directly from Petros.

### Defend Petros

**Description:** Your headquarters (HQ) is under attack by enemy forces. You must defend Petros and the HQ location from the assault. This mission spawns automatically when HQ comes under threat. Success is critical—failing this mission results in severe penalties, including the potential loss of Petros.

**Success: Occupier Attacking:**
- **Money**: 300/300 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: Occupier +10 for 60 minutes and Invader +5 for 60 minutes
- **Player Score**: 10 points
- **Commander Score**: -

**Success: Invader Attacking:**
- **Money**: 300/300 €
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: Occupier +5 for 60 minutes and Invader +10 for 60 minutes
- **Player Score**: 10 points
- **Commander Score**: -

**Failure:**
- **Outcome**: See [Losing Petros Penalties](../concepts_info/concepts/losing_petros_penalties.html) for detailed failure consequences
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -

---

### Tower Rebuild Disrupt

**Description:** The enemy is attempting to rebuild a destroyed radio tower. You must disrupt the reconstruction effort before they can restore their communications network. These missions appear automatically when the enemy begins reconstruction work.

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 20 minute delay
- **Enemy Aggression**: +15 for 90 minutes (Occupier) and +5 for 60 minutes (Invader)
- **Player Score**: 10 points
- **Commander Score**: -

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: -
- **Next Enemy Attack**: 10 minutes sooner
- **Enemy Aggression**: -
- **Player Score**: -10 points

---

## Support Missions

### City Supplies

**Description:** Deliver supplies to a friendly or neutral city to increase the population's support for your rebellion. This is a hearts-and-minds operation that helps build support in towns where you're trying to gain influence. The mission targets cities with low rebel support (below 80%).

**Success:**
- **Money**: -
- **HR**: -
- **Town Support**: -15/-30 Occupier support in objective town
- **Next Enemy Attack**: -
- **Enemy Aggression**: +10 for 60 minutes
- **Player Score**: 10/20 points
- **Commander Score**: 5/10 points

**Failure:**
- **Money**: -
- **HR**: -
- **Town Support**: +5 Occupier support in objective town and -5 support in objective town
- **Next Enemy Attack**: -
- **Enemy Aggression**: -
- **Player Score**: -10/-20 points

---

## Mission Scoring Notes

- **Player Score** and **Commander Score** values represent points awarded for mission completion
- Values shown as ranges (e.g., "10/20") indicate standard/difficult difficulty tiers
- **Enemy Aggression** values show changes to enemy threat levels with duration (e.g., "+25 for 2 hours" means aggression increases by 25 points for 2 hours)
- **Next Enemy Attack** values indicate how mission outcomes affect timing of enemy counterattacks
- **Town Support** changes apply to the nearest town or the mission's objective town, depending on the mission type

