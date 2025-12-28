# War Tier Explained

War Tier is a fundamental progression system in Antistasi that represents your overall campaign advancement. It's calculated from the territory you control and directly affects enemy equipment, support availability, and mission difficulty.

## Overview

War Tier is a scale from **1 to 10**, calculated automatically based on how much territory you control. As you capture more locations, your war tier increases, which unlocks new capabilities but also makes the enemy stronger and more dangerous.

## How War Tier is Calculated

War Tier is determined by the **total points** you control from captured locations. Each location type has a different point value:

### Location Point Values

- **Airbases**: 8 points each
- **Seaports**: 4 points each
- **Outposts**: 2 points each
- **Resources**: 2 points each
- **Factories**: 2 points each
- **Cities**: 1 point each

### Calculation Formula

The game calculates war tier using this formula:

```
Total Points = (8 × Airbases) + (4 × Seaports) + (2 × Outposts) + (2 × Resources) + (2 × Factories) + (1 × Cities)

War Tier = 1 + floor(9 × sqrt(Rebel Points / (0.7 × Total Points)))
```

War Tier is capped at a maximum of 10.

### War Tier Thresholds

Based on the formula, here are the approximate territory percentages needed for each tier:

- **Tier 1**: 0% of total points (starting tier)
- **Tier 2**: ~1% of total points
- **Tier 3**: ~4% of total points
- **Tier 4**: ~8% of total points
- **Tier 6**: ~22% of total points
- **Tier 8**: ~42% of total points
- **Tier 10**: ~70% of total points (maximum tier)

**Note**: The formula uses a square root function, so early tiers require less territory, while higher tiers require significantly more territory to progress.

## Effects of War Tier

War Tier affects multiple aspects of gameplay:

### Enemy Equipment and Vehicles

As war tier increases, enemies deploy progressively stronger equipment:

#### Vehicle Types by Tier

- **Tier 1**: Primarily militia vehicles (light armed cars)
- **Tier 2**: Introduction of light armed vehicles and some light tanks
- **Tier 3**: More light tanks, introduction of regular tanks
- **Tier 4**: Increased tank presence, introduction of heavy tanks
- **Tier 5+**: Heavy tanks become more common
- **Tier 6+**: Maximum vehicle variety with all types available

#### Vehicle Weight Distribution

The system uses weighted probabilities to determine what vehicles enemies spawn:

- **Militia vehicles**: Most common at tier 1, rapidly decrease at higher tiers
- **Light armed vehicles**: Peak around tiers 3-6
- **Anti-air vehicles**: Start appearing at tier 3, increase steadily
- **Light tanks**: Available from tier 2, stable presence through all tiers
- **Main battle tanks**: Start at tier 3, become dominant at higher tiers
- **Heavy tanks**: Available from tier 4, increase significantly at higher tiers

### Enemy Support Availability

War Tier directly controls what support types enemies can call:

#### Artillery Support

- **Available at**: War Tier 5+
- **Weight**: Increases from ~8.3% at tier 5 to 50% at tier 10
- **Balanced against**: Mortar support (artillery becomes more likely as tier increases)

#### Airstrikes

- **Available at**: War Tier 3+
- **Weight**: 100% at tier 3-5, then decreases as carpet bombs become available
- **Balanced against**: Carpet bombing (airstrikes become less common as tier increases)

#### Carpet Bombing

- **Available at**: War Tier 6+
- **Weight**: Increases from 10% at tier 6 to 50% at tier 10
- **Balanced against**: Regular airstrikes

#### Mortar Support

- **Available at**: War Tier 2+
- **Weight**: 100% at tier 2-4, then decreases as artillery becomes available
- **Balanced against**: Artillery support (mortars become less common as tier increases)

### Mission Difficulty

- Higher war tiers unlock more difficult mission variants
- Enemy forces in missions scale with war tier
- Mission rewards may increase at higher tiers

### Airbase Capture Requirement

- **You cannot capture airbases below War Tier 3**
- The flag capture action is disabled until you reach tier 3
- This prevents early-game airbase captures that would be too easy

### Player Balance Scaling

War Tier affects the player balance scale:

- Higher war tiers increase the overall difficulty multiplier
- This ensures the game remains challenging as you progress
- The formula: `(Player Count^0.8 + 1 + War Tier / 4) / 6`

### Enemy Response Times

- Higher war tiers may affect enemy support call times
- Airstrike setup delays decrease with higher war tier: `(0.5 + random 1) × (300 - 15 × tierWar - 1 × aggression)`
- This means faster enemy air support at higher tiers

## Strategic Implications

### Early Game (Tiers 1-3)

- Focus on building your arsenal and capturing easy targets
- Enemy equipment is relatively weak
- Limited enemy support options (mostly mortars)
- Good time to establish your first outposts and resources

### Mid Game (Tiers 4-6)

- Enemy starts deploying tanks and stronger vehicles
- Artillery support becomes available to enemies
- Airstrikes become more common
- Time to capture your first airbase and expand territory

### Late Game (Tiers 7-10)

- Enemy has access to full arsenal including heavy tanks
- Carpet bombing becomes available
- Maximum enemy support variety
- Focus on capturing remaining airbases and achieving victory

## War Tier Notifications

When your war tier changes, you'll receive a notification message from Petros informing you of the new tier level. This helps you track your campaign progress and understand when enemy capabilities are about to increase.

## Technical Details

- War Tier is recalculated whenever you capture or lose a location
- The calculation happens server-side and is synchronized to all clients
- War Tier affects many systems including vehicle spawning, support availability, and mission generation
- The system uses a square root formula to create a natural progression curve


