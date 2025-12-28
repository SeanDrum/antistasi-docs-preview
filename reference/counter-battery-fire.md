# Counter Battery Fire

Counter battery fire is an enemy response system that detects when you fire artillery or mortars and allows enemy garrisons to retaliate with their own artillery strikes. Understanding this system is crucial for effective artillery usage and avoiding devastating counterattacks.

## How Counter Battery Detection Works

**Detection mechanism:**
- When you fire artillery or mortars, the game calculates the trajectory and landing point of your shells
- Enemy garrisons within **600 meters** of the impact point are automatically alerted
- The system tracks the artillery piece that fired, not just the impact location
- Detection happens regardless of line of sight—enemies can detect artillery fire through trajectory calculation

**What triggers detection:**
- Firing any artillery piece (mortars, howitzers, etc.)
- The detection occurs when shells are approximately **3.5 seconds** from impact
- All artillery types are detected, including static mortars, vehicle-mounted artillery, and towed guns

## Enemy Response Mechanics

**Response conditions:**
- Enemy garrisons must have available mortars that are:
  - Not already busy with other fire missions
  - Within range of your artillery position
  - At least **100 meters** away from your position (to avoid danger close)
- The garrison's "threat" level must exceed a random threshold (random 3)
- Mortar fire events add **3 threat points** (vs 1 point for regular damage events)

**Response behavior:**
- At **long ranges** (beyond marker radius + 200-500m), enemies prefer using mortars for counter battery
- At **close ranges**, enemies may send infantry patrols instead
- Counter battery fire targets your artillery position with a precision offset (random 0-60m based on detection quality)
- Enemy mortars fire **4 HE rounds** in a **40-meter area** around your position

**Response timing:**
- **Static mortars** (your artillery): **5-10 second delay** before counter battery begins
- **Mobile artillery** (your artillery): **20-30 second delay** before counter battery begins
- The faster response to static mortars reflects that stationary positions are easier to target

## Threat System

**Threat accumulation:**
- Each artillery round you fire adds threat to nearby garrisons
- Threat decays over time (1 point per minute)
- Multiple rounds fired quickly stack threat, increasing counter battery probability
- Threat is tracked per garrison marker

**Threat thresholds:**
- Counter battery is triggered when threat exceeds a random value (0-3)
- Higher accumulated threat = higher chance of counter battery response
- Threat resets after a successful counter battery response

## Range and Positioning

**Effective ranges:**
- Enemy mortars can respond if your position is within their artillery range
- Detection range: **600 meters** from impact point
- Counter battery range: Limited by enemy mortar's maximum range
- Minimum distance: Enemy mortars won't fire if you're within **100 meters** (danger close)

**Positioning considerations:**
- **Static positions** (mortars set up in one location) are detected and targeted faster
- **Mobile artillery** (firing from vehicles) gets slower counter battery response
- Moving between shots reduces the chance of accurate counter battery
- The changelog notes that "chances of receiving a counter battery action will depend on how static the battery has been"

## Strategies to Avoid Counter Battery

**1. Shoot and scoot:**
- Fire your artillery and immediately move to a new position
- Don't remain in the same location for multiple volleys
- Mobile artillery (vehicle-mounted) is harder to counter than static mortars

**2. Limit sustained fire:**
- Avoid firing multiple rounds from the same position
- Spread out your artillery strikes over time and location
- Each round adds threat—rapid fire increases counter battery probability

**3. Use range advantage:**
- Position your artillery at maximum range when possible
- Enemy mortars may be out of range to respond
- Check enemy garrison capabilities before engaging

**4. Target selection:**
- Avoid firing at garrisons that are known to have mortars
- Scout enemy positions to identify mortar locations
- Destroy enemy mortars first if possible

**5. Suppress enemy mortars:**
- Use direct fire or airstrikes to eliminate enemy mortar positions
- Destroying enemy mortars removes their counter battery capability
- Focus on garrisons with known artillery assets

**6. Coordinate timing:**
- Fire multiple artillery pieces simultaneously to overwhelm enemy response
- Coordinate with teammates to suppress counter battery positions
- Use smoke or other distractions to mask your position

## Counter Battery Indicators

**Warning signs:**
- Enemy mortars firing in your general direction
- Incoming shells landing near your artillery position
- Multiple rounds targeting your area (enemies fire 4-round volleys)
- Sustained counter battery indicates your position is compromised

**What to do when counter battery starts:**
- **Immediately move** your artillery to a new position
- If using static mortars, pack up and relocate
- If using vehicle artillery, drive to a new firing position
- Don't try to "out-duel" enemy mortars—they have the advantage

## Technical Details

**Detection system:**
- Uses trajectory calculation to predict shell landing points
- Detection occurs ~3.5 seconds before impact
- Alerts garrisons within 600m of impact point
- Works regardless of line of sight or visibility

**Response system:**
- Threat-based probability system (threat > random 3)
- Mortar selection based on availability and range
- Precision offset: random 0-60m (reduced by detection quality)
- 4-round HE volley in 40m area
- Response delay: 5-10s (static) or 20-30s (mobile)

**Threat decay:**
- Threat decreases by 1 point per minute
- Resets after successful counter battery response
- Accumulates with each artillery round fired

## Integration with Other Systems

**Relationship to support calls:**
- Counter battery is separate from enemy support calls (artillery, airstrikes)
- Counter battery uses garrison mortars, not support call resources
- Both can occur simultaneously during combat

**Relationship to aggression:**
- Higher aggression may increase threat accumulation rates
- More aggressive enemies may respond faster or more accurately
- Counter battery is part of the overall enemy response system

**Relationship to war tier:**
- Higher war tiers may provide enemies with better artillery
- Enemy mortar accuracy and response times may improve with tier
- More enemy garrisons may have mortars at higher tiers

## Summary

Counter battery fire is a realistic and dangerous mechanic that punishes static artillery positions and sustained fire. To use artillery effectively:

- **Move after firing** - Don't stay in one place
- **Limit sustained fire** - Spread out your strikes
- **Use mobile artillery** - Vehicles are harder to counter
- **Scout enemy positions** - Know where enemy mortars are
- **Coordinate with team** - Suppress counter battery positions
- **Be ready to relocate** - Have an escape plan ready

Remember: The best counter to counter battery is mobility and unpredictability. Keep your artillery moving, and you'll stay one step ahead of enemy retaliation.

