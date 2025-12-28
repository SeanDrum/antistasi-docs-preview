# Roadblocks & Checkpoints

Roadblocks and checkpoints are enemy-controlled positions that dynamically spawn on roads between enemy-controlled territory. They serve as obstacles and security checkpoints that can detect and challenge players moving through enemy territory.

## Spawning & Placement

Enemy factions automatically generate roadblocks on roads connecting their controlled territory. The system selects roads between strategic markers (outposts, airports, cities, etc.) that belong to enemy factions and places roadblocks along these routes. Roadblocks are typically positioned on road segments with suitable spacing from friendly bases and other existing roadblocks.

The number of roadblocks increases with enemy aggression levels—as aggression rises, the enemy creates more roadblocks to secure their territory and restrict player movement. The system aims to maintain roughly one roadblock per enemy-controlled strategic marker, scaling with the current player count and balance parameters.

## Detection & Undercover Status

Roadblocks can detect undercover players. When you're undercover and attempt to pass through an enemy roadblock, there's a chance of being detected based on the enemy faction's current aggression level combined with the war tier. Higher aggression and war tier increase the detection probability. If detected at a roadblock, your undercover status breaks immediately.

Roadblocks check vehicles passing through, so even if you're in a civilian vehicle and properly disguised, there's always a risk when approaching or passing through these checkpoints. Airports have guaranteed detection, but roadblocks use probability checks based on aggression.

## Destruction & Rewards

When all enemy troops at a roadblock are eliminated, the roadblock is automatically removed from the map. Players within 700 meters receive a notification when a roadblock is destroyed. Destroying roadblocks provides a local reputation boost in nearby cities, improving civilian support for your cause in the surrounding area.

Destroyed roadblocks do not respawn immediately. The system will generate new roadblocks over time based on enemy aggression levels and the number of strategic markers they control, but destroyed roadblocks are permanently gone once cleared.

## Camps

Camps are similar to roadblocks but are larger defensive positions located off-road. They're typically placed in strategic locations between enemy bases, away from main road networks. Camps have slightly larger garrisons (typically 8 soldiers compared to 6 for roadblocks) and cover a larger area (300-meter radius versus 30 meters for roadblocks). They serve similar functions to roadblocks—providing security and detection capabilities—but are positioned in less predictable locations and are harder to simply drive past.

Camps spawn at approximately one-third the rate of roadblocks, so you'll encounter them less frequently but they'll be more challenging when you do find them.


