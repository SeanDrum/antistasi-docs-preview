# Airstrikes

Airstrikes are powerful Commander-only fire support capabilities that allow you to call in precision bombing runs against enemy positions. They use accumulated bomb runs (earned from controlled airbases) to deploy different types of ordnance depending on your tactical needs.

## Requirements

**Commander Only:**
- Only the Commander can call airstrikes

**Prerequisites:**
- Must control at least one airbase
- Must have radio equipment
- Must have sufficient bomb runs available
- The strike line must not be within 100 meters of HQ (if friendly fire punishment is enabled)

## Bomb Run Requirements

Each airstrike type has a different cost in bomb runs:

- **HE (High Explosive)**: 1 bomb run
- **Cluster**: 1 bomb run  
- **Napalm**: 3 bomb runs

## How to Call an Airstrike

1. Access the Commander menu and select "Ask for Air Support" (uses Airstrike points)
2. Choose your bomb type (HE, Cluster, or Napalm)
3. Select the start position on the map where the bombing run should begin
4. Select the end position on the map where the bombing run should finish
5. The aircraft will fly along the line between these two points and drop ordnance

The airstrike uses aircraft from your faction's available CAS (Close Air Support) planes. The aircraft will approach from behind the start position, execute the bombing run, and depart after the end position.

## Airstrike Types

### High Explosive (HE) Bombs

**Cost:** 1 bomb run

**Effect:**
- Drops a series of high-explosive bombs in a straight line along the selected path
- Bombs are dropped at twice the density compared to other bomb types (double the number of bombs for the same run length)
- Creates a line of explosions that deal significant damage to all targets in the impact area
- Effective against infantry, light vehicles, and structures
- Bomb run length is approximately 200 meters

**Best Use:**
- General-purpose area denial
- Destroying enemy positions and static weapons
- Clearing concentrated enemy forces
- Destroying structures and buildings

### Cluster Bombs

**Cost:** 1 bomb run

**Effect:**
- Drops bomblets that spread out over a wider area than HE bombs
- The bomblets disperse shrapnel in a wider pattern than single-point explosions
- Extremely deadly against soft targets (infantry)
- The wider spread makes it more effective against dispersed enemy forces

**Best Use:**
- Eliminating large groups of infantry
- Area denial against unarmored targets
- Clearing enemy positions with spread-out defenders

### Napalm Bombs

**Cost:** 3 bomb runs

**Effect:**
- Drops incendiary bombs that create a line of blazing napalm fire
- The napalm fire burns for 90 seconds in a 30-meter radius area
- Creates a persistent area denial zone that deals damage over time

**Napalm Effects on Different Targets:**

- **Infantry**: Napalm deals damage over time, eventually killing all personnel caught in the fire. Units will take continuous damage for the duration of the burn.

- **Vehicles**: Napalm damages vehicles but does not destroy them completely. A vehicle caught in napalm will:
  - Have all inventory and cargo completely deleted (weapons, ammo, items, backpacks)
  - Have all vehicle components damaged to critical levels (hull damage limited to 80%, other components can reach 100%)
  - Have all crew members killed
  - Remain intact enough to be repaired, refueled, and recaptured (making napalm useful for clearing enemy crews from vehicles)

- **Ground Weapon Holders**: All ground weapon holders (dropped vests, backpacks, weapons, equipment) are completely destroyed and deleted.

- **Ammo Boxes**: All ammo boxes, including loot crates at outposts and other supply containers, are completely destroyed. This makes napalm particularly effective for denying enemy resources.

- **Buildings**: Buildings take damage (up to 50% damage) but are not completely destroyed.

**Best Use:**
- Denying enemy resources (destroying ammo boxes and loot crates)
- Clearing enemy crews from vehicles without destroying the vehicles themselves (allowing capture)
- Area denial for extended periods (90 seconds of burning)
- Destroying enemy equipment and supplies
- Clearing static positions where enemies are entrenched

**Strategic Note:** Because napalm costs 3 bomb runs compared to 1 for other types, it should be used selectively when its unique effects (destroying supplies, clearing vehicles without destroying them) are strategically important.

## Bomb Run Accumulation

Bomb runs are the currency used to call airstrikes. They accumulate automatically over time:

- Each controlled airbase provides 0.25 bomb runs per income tick (approximately every 10 minutes)
- Maximum bomb runs: 4 + (War Tier × 2)
  - At War Tier 3 (when airstrikes unlock): Maximum of 10 bomb runs
  - At War Tier 10: Maximum of 24 bomb runs
- Bomb runs can also be gained by converting captured enemy aircraft at airbases

## Tactical Considerations

**When to Use Airstrikes:**
- Softening enemy positions before an assault
- Clearing heavily defended outposts or airbases
- Area denial during defensive operations
- Destroying enemy resources and supplies (napalm)
- Eliminating concentrated enemy forces

**Timing:**
- Airstrikes have a brief setup time before the aircraft arrives
- The aircraft will follow the exact line you draw on the map
- Plan your strike path to maximize effectiveness against enemy positions

**Accuracy and Targeting:**
- For accurate airstrikes, call in bomb runs along terrain corridors with relatively flat terrain
- Position the start point approximately 100 meters from the center of your target area
- This ensures the bombing run begins before reaching the target and maximizes precision

**Coordination:**
- Coordinate with team members to avoid friendly fire
- Use airstrikes to support ground operations rather than replace them
- Save bomb runs for critical moments rather than using them frivolously

**Restrictions:**
- Airstrikes cannot target air targets (aircraft)
- The strike line must be at least 100 meters from HQ (if friendly fire punishment is enabled)
- Requires an available aircraft from your faction's CAS plane roster

## Differences from Enemy Airstrikes

Enemy airstrikes (from Occupants or Invaders) use the same bomb types but are automatically called by the AI. Enemy strikes:
- Use similar HE, Cluster, and Napalm bombs
- Are balanced against other support types based on war tier
- Have setup delays that decrease with higher war tier and aggression
- Napalm availability for enemies depends on whether the napalm parameter is enabled

Player-controlled airstrikes give you direct tactical control over when and where these powerful weapons are deployed, making them a critical strategic tool for the Commander.

