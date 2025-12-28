# Builder/Fortification System

The builder system allows Team Leaders and Engineers to construct defensive fortifications using faction resources. This system is essential for fortifying captured locations, creating defensive positions, and preparing for enemy counterattacks.

## Access & Eligibility

**Who can use the builder:**
- **Team Leaders**: Can access the builder system if enabled in server parameters
- **Engineers**: Can access the builder system if enabled in server parameters  
- **Commander**: Always has access to the builder system regardless of role

The builder system can be accessed via the "Build" action at your HQ or from builder boxes placed on the map. Server parameters control whether Team Leaders, Engineers, or both roles can use the builder.

**Requirements:**
- You must not have enemies nearby (within detection range)
- The builder box or HQ must have available funds
- You must be at a location where building is permitted (cannot build directly on roads)

## Building Process

When you activate the builder system, you enter a placement camera mode similar to an RTS game. You can move the camera within a set radius around your starting point and preview where structures will be placed before building them.

**Placement controls:**
- Use mouse movement to position structures
- Rotate structures using E (counter-clockwise) and R (clockwise) keys
- Press Space to place the selected structure
- Press C to cancel a placed structure (before it's built)
- Press Escape or Y to exit the builder mode

Structures cannot be placed directly on roads. The builder shows collision previews and will hide objects that cannot be placed in the current location.

## Construction System

When you place a structure, it doesn't immediately appear. Instead, construction materials (planks, pallets, or cinder blocks depending on the structure's cost) appear at the location. You must then hold an interaction action at these materials to construct the building.

**Build time calculation:**
Construction time scales with the structure's cost using a square root formula. The base build time is approximately 1.2 times the square root of the structure's price in seconds. For example, a structure costing 100 resources takes about 12 seconds to build, while one costing 1000 resources takes about 38 seconds.

**HQ bonus:**
Structures built within 100 meters of your HQ construct 25% faster due to easier access to command resources and better logistics support.

**Construction timeout:**
Construction materials remain on the ground for 20 minutes. If you don't complete the construction within this time, the materials disappear and the faction's money is refunded. You can manually cancel construction by interacting with the materials and choosing the cancel option, which also refunds the money.

## Available Structures

The builder system allows you to construct various defensive structures. The exact structures available may vary slightly by map climate (arid, tropical, or temperate), but the following are standard across all maps:

**Large Bunkers & Fortifications:**
- Large Bag Bunker (arid maps): 300 resources
- Large Bag Bunker Green (tropical/temperate maps): 300 resources
- Bag Bunker Tower (arid maps): 300 resources
- H-Barrier Tower (tropical/temperate maps): 300 resources
- Pillbox Bunker (hexagonal): 200 resources
- Small Bag Bunker (arid maps): 60 resources
- Small Bag Bunker Green (tropical/temperate maps): 60 resources

**Structures & Sheds:**
- Shed (9): 120 resources
- Shed (10): 140 resources
- Guard Box (brown): 80 resources
- Helipad: 1500 resources

**Barriers & Fences:**
- Sandbag Barricade (half): 20 resources
- Barricade (4m): 30 resources
- Slum Wall (2m): 5 resources
- Tyres (vehicle obstacle): 10 resources

**Sandbag Fences (Arid Maps):**
- Long Sandbag Fence: 10 resources
- Round Sandbag Fence: 10 resources
- Short Sandbag Fence: 10 resources

**Sandbag Fences (Tropical/Temperate Maps):**
- Long Sandbag Fence Green: 10 resources
- Round Sandbag Fence Green: 10 resources
- Short Sandbag Fence Green: 10 resources

**Repairable Structures:**
You can also repair destroyed buildings by interacting with their ruins in builder mode. The repair cost is calculated based on the building's size (bounding box volume), using a formula of 6 times the square root of the volume, rounded to the nearest 10.

## Cost & Resource Management

All structures cost faction resources (money) to place. The commander's shared faction funds are used for builder purchases, not individual player money. The cost varies significantly by structure type—simple sandbag walls are relatively cheap, while heavy bunkers and HMG emplacements are expensive.

When you place a structure in the builder interface, the cost is immediately deducted from available funds. If you cancel the construction or it times out, the money is refunded. If you successfully build the structure, the cost is permanent.

Constructed structures become part of the location's garrison data if built within a controlled strategic marker, allowing them to persist across saves and be used by AI defenders.

