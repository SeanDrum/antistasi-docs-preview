# Intel & Intelligence Gathering

Intel is a crucial information-gathering system that provides valuable intelligence about enemy activities, resources, and upcoming threats. Understanding how to find and use intel effectively can give you significant strategic advantages.

## Intel Types

There are four types of intel in Antistasi, each with different sources and rewards:

### Small Intel
**Sources:**
- Found on dead enemy squad leaders (search their bodies)
- Squad leaders must have the `hasIntel` variable set to true

**Rewards:**
- **Decryption Key** (60% chance): Grants a radio decryption key for the enemy faction, allowing you to intercept their communications
- **Time Until Next Attack** (20% chance): Reveals when the enemy will launch their next major attack on your territory
- **Defense Resources** (20% chance): Shows the enemy's current defense resource pool status (Very High, Medium, Low, Very Low, or Empty)
- **Convoy Routes** (currently disabled): Would reveal enemy convoy locations on the map

**How to obtain:**
1. Kill an enemy squad leader
2. Approach the body and use the "Search for Intel" action
3. Wait 10-15 seconds while searching (you can cancel if needed)
4. If the squad leader had intel, you'll receive Small intel automatically

### Medium Intel
**Sources:**
- Found as physical documents on desks in enemy outposts and airbases
- Obtained by interrogating surrendered enemy squad leaders

**Rewards:**
- **Key Pack** (100% chance): Grants 3-6 radio decryption keys for the enemy faction
- **Convoy Routes** (currently disabled): Would reveal all active enemy convoy markers on the map
- **Garrison Composition** (currently disabled): Would show what vehicles and equipment the enemy has access to

**How to obtain:**
1. **From documents**: Search desks in enemy-controlled outposts and airbases. Look for document items on tables in command buildings.
2. **From interrogation**: 
   - Make an enemy squad leader surrender (they must be alive and incapacitated)
   - Use the "Interrogate" action on them
   - Success chance is based on aggression: `120 - aggression` (higher aggression = lower success chance)
   - Only squad leaders can provide Medium intel through interrogation
   - Each unit can only be interrogated once

### Large Intel
**Sources:**
- Found as laptops on desks in enemy outposts and airbases
- Always appears as a computer/laptop object

**Rewards:**
- **Random Weapon Unlock** (40% chance, or 30% if traitor mission is active): Permanently unlocks a random weapon from the enemy faction's arsenal
- **Money** (60% chance, or 40% if traitor mission is active): Grants money based on war tier: `(random 50 + 10 × tierWar) × 100` (typically 1000-1500 in early game, scaling up with tier)
- **Traitor Location** (30% chance, only if "Kill the Traitor" mission is active): Reveals the location of the traitor you need to eliminate

**How to obtain:**
1. Search desks in enemy-controlled outposts and airbases
2. Look for laptop/computer objects on tables
3. Use the "Download Intel" action
4. The intel is immediately processed and rewards are granted

**Special features:**
- Large intel laptops may be trapped with explosives (20% + 4% per war tier chance)
- Engineers can disarm the trap before downloading
- The trap bomb is hidden under the laptop and can be disarmed with a hold action

### Encrypted Intel
**Sources:**
- Found as laptops on desks in enemy outposts and airbases (non-computer large intel items)
- Appears as a laptop that requires decryption

**Rewards:**
- Same as Large Intel (weapon unlock, money, or traitor location)
- However, decryption takes time and may trigger enemy counterattacks

**How to obtain:**
1. Find an encrypted laptop in an enemy location
2. Use the "Decipher Intel" action
3. Complete the decryption minigame:
   - You need to accumulate 500-1000 points
   - Points accumulate at 25 per second (reduced by war tier: 25 - tierWar at tier 2+, 25 - tierWar × 2 at tier 4+)
   - Random "action needed" events will pause progress until you interact
   - Progress is shown as a percentage to nearby players

**Risks:**
- Decryption may trigger enemy counterattacks:
  - **No attack** (20% chance, reduced at higher war tiers, 0% at airbases)
  - **Small attack** (60% chance)
  - **Large attack** (20% chance, increases with war tier, 40% at airbases)
- If decryption fails or is interrupted, the laptop becomes regular Large Intel and can be downloaded normally

## Intel Locations

Intel spawns at:
- **Outposts**: Can spawn Medium or Large/Encrypted intel
- **Airbases**: Can spawn Medium or Large/Encrypted intel
- Intel is placed on desks in specific building types:
  - Command buildings (HQ structures)
  - Control towers
  - Barracks
  - Radar installations

Intel does NOT spawn at:
- Resource sites
- Factories
- Seaports
- Towns/cities

## Radio Towers and Intel

Radio towers significantly enhance your intel capabilities:

- **Increased frequency**: Controlling radio towers increases how often intel spawns at enemy locations
- **Improved effectiveness**: Radio towers boost the quality and usefulness of intel you receive
- **Communication interception**: Radio towers help you intercept enemy support calls and warnings
- **Strategic advantage**: Each radio tower you control makes it harder for enemies to coordinate and easier for you to gather intelligence

**Tip**: Destroying or capturing enemy radio towers early in the campaign is highly recommended, as they provide ongoing intelligence benefits throughout the war.

## Intel Strategy Tips

1. **Prioritize squad leaders**: When attacking enemy positions, focus on eliminating squad leaders first—they may carry Small intel
2. **Search systematically**: When clearing outposts or airbases, check all command buildings for intel documents and laptops
3. **Interrogate when possible**: If you can make a squad leader surrender, interrogate them for Medium intel—it's faster than searching documents
4. **Watch for traps**: Always check Large intel laptops for explosive traps, especially at higher war tiers
5. **Time your decryption**: Only decrypt encrypted intel when you're prepared to handle potential counterattacks
6. **Control radio towers**: Capture or destroy enemy radio towers to boost your intel gathering capabilities
7. **Use decryption keys**: Radio decryption keys from Small and Medium intel let you intercept enemy communications, giving you advance warning of support calls and attacks

## Technical Details

**Code references:**
- `fn_selectIntel.sqf` - Handles intel reward selection and execution
- `fn_searchIntelOnLeader.sqf` - Small intel search mechanics
- `fn_searchIntelOnDocument.sqf` - Medium intel document search
- `fn_searchIntelOnLaptop.sqf` - Large intel laptop download
- `fn_searchEncryptedIntel.sqf` - Encrypted intel decryption minigame
- `fn_interrogate.sqf` - Interrogation mechanics for Medium intel
- `fn_placeIntel.sqf` - Intel spawning system

