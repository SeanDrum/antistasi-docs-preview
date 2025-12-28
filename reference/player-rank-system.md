# Player Rank System

The player rank system tracks long-term contribution to the rebellion through accumulated score points. While ranks are primarily cosmetic, they affect commander election priority and serve as a visible indicator of a player's experience and dedication to the campaign.

## How Ranks Work

Players earn **score points** through various actions during the campaign:
- Completing missions successfully
- Destroying enemy vehicles and equipment
- Capturing strategic locations
- Eliminating enemy units
- Other combat and strategic achievements

Score points accumulate over time and are saved with your player profile. Unlike money or other resources, score points are never lost and persist across sessions.

## Rank Progression

There are seven ranks in the system, from lowest to highest:

1. **Private**: Starting rank for all new players
2. **Corporal**: Requires 50 score points
3. **Sergeant**: Requires 100 additional score points (50 × 2 multiplier)
4. **Lieutenant**: Requires 150 additional score points (50 × 3 multiplier)
5. **Captain**: Requires 200 additional score points (50 × 4 multiplier)
6. **Major**: Requires 250 additional score points (50 × 5 multiplier)
7. **Colonel**: Requires 300 additional score points (50 × 6 multiplier), the highest rank

Each rank requires 50 points multiplied by a sequential multiplier. When you reach the score threshold for the next rank, you're automatically promoted and the points spent on that rank are deducted from your total score. This means:
- Private to Corporal: 50 points required
- Corporal to Sergeant: 100 points required (your score shows 100+, but only 100 are spent)
- Sergeant to Lieutenant: 150 points required
- And so on...

You cannot exceed Colonel rank—once you reach it, additional score points continue to accumulate but no further promotions occur.

## Commander Election Priority

Rank significantly affects who becomes commander when elections occur or when the current commander disconnects or becomes ineligible.

**Election priority calculation:**
1. **Members always have priority over guests**: Server members receive a large priority bonus (+1000) compared to regular players
2. **Rank determines priority within member/guest groups**: Higher rank means higher priority
3. **Only eligible players are considered**: Players who are AFK, marked as ineligible, or (if guest commander is disabled) non-members are excluded

The system calculates a priority score for each eligible player. Members get their numeric rank value plus 1000, while guests only get their numeric rank value. The player with the highest priority score becomes the new commander. If multiple players have the same priority (same rank and membership status), the selection is effectively random among them.

**Rank numeric values:**
- Private = 1
- Corporal = 2  
- Sergeant = 3
- Lieutenant = 4
- Captain = 5
- Major = 6
- Colonel = 7

So a Colonel who is a member would have priority 1007, while a Private who is a member would have priority 1001. A Colonel guest would have priority 7, which is still lower than any member.

## Cosmetic Only

Aside from commander election priority, player ranks are purely cosmetic. They don't affect:
- Available equipment or loadouts
- Combat effectiveness or stats
- Access to game features or abilities
- Resource generation or income

Your rank serves as a long-term indicator of your contribution to the campaign and helps the community recognize experienced players, but it doesn't provide gameplay advantages beyond commander election.

## Promotion Notifications

When players are promoted, all players receive a notification message listing everyone who was promoted during that check. Promotions are checked periodically by the server, and you'll see your new rank reflected immediately upon promotion.


