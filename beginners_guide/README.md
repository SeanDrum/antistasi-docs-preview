# Beginners Guide

This is the casual “how do I actually play this?” guide.


---

# Setting up the scenario

This is the **first screen you see after loading into the scenario**.

Before the campaign actually starts, you (or your host/admin) need to set up:

- what save to load (or whether you’re starting fresh)
- which factions are in the war
- the campaign parameters (difficulty/limits/tuning)

It has three main tabs:

- **Load game**
- **Factions**
- **Params**

## Load game tab (starting, copying, loading)

You’ll see a list of existing saves (if any), plus controls for starting something new.

Things you can do here:

- **Load an existing save** (select it, then start).
- **Create a new game** (check “new game”, set a name, start).
- **Copy a game** (new game + copy option) if you want a “branch” of an older campaign.
- **Load old params** (when starting a new game): reuse parameter settings from a selected save.
- **Use new namespace** (new game): used for save/import compatibility and cross-platform differences.
- **Set HQ position** (new game): choose where HQ starts — see **[Set HQ position (HQ placement)](../reference/set-hq-position.md)**.
- **Export / import** (only available for compatible saves).
- **Delete / rename** saves.


## Factions tab (who’s fighting)

Before you pick factions, you should understand the campaign **game mode**, because it changes what “Occupants” and “Invaders” mean.

Antistasi supports:



- **Reb vs Gov**: simplest mode. One main enemy (“the government/occupants”). Good for learning, smaller groups, or “one clear front line”.
- **Reb vs Gov + Inv**: two enemy factions exist. You’ll still mostly feel pressure from the government, but the invaders add extra chaos and extra threats depending on where they are on the map.
- **Reb vs Gov vs Inv**: full three-way war. Expect the most unpredictability and “stuff happening without you”. Great for emergent fights, but it’s the least beginner-friendly.

You should probably determine the mode you want on the param tab before picking factions. Once you've done that you can determine which faction(s) you face against and who you play as.

- **Rebels** (you)
- **Civilians**
- **Occupants** (main government force)
- **Invaders** (secondary enemy faction depending on mode)

Helpful options in this tab:

- **Switch enemy sides**: swap occupants/invaders around.
- **Override side limits**: loosen restrictions on which factions can be picked for each enemy slot.
- **Override camo limits**: ignore climate/camo constraints.
- **Show missing mods**: show factions even if required addons aren’t loaded (usually greyed out).
- **DLC / Addons toggle**: switch between DLC and “addon vehicles” lists.
- **Info panel**: shows faction lore + dependencies so you know what you’re selecting.

## Params tab (campaign rules)

This tab is a big list of “server rules” / tuning options. This allows for fine grained control over difficulty, realism, convenience, and many other things. Leaving them as default will be a "middle of the road" experience for all the aforementioned factors.

Full reference:

- **[Params tab reference](../reference/params-tab.md)**

---

## Game Mechanics

Before walking through a basic strategy on how to win in Antistasi, there are some basic elements of the game that must be first understood.

### Map markers

These are capturable (and losable) points around the map. Each carries different benefits and different challenges to capture them.

- **Towns / cities**: Towns are the “hearts and minds” layer, and they’re also **passive income**: every ~10 minutes the campaign adds **money (“resources”) and HR** based on that town’s population and rebel support. If you *control* the town you get the full value; if the enemy controls it you still get some, but reduced. High rebel support can flip the town to your side, and keeping support high makes the war easier over time.
- **Outposts**: Outposts are military footholds and common frontline objectives. Capturing them removes an enemy garrison anchor in that area and gives you another defensible point you can garrison. Some outposts are also tied to nearby **radio towers**, which makes them extra valuable to hold.
- **Airbases**: Airbases are “big win” strategic targets and are among the highest-value markers for victory/defeat pacing. Owning more airbases increases your available **bomb runs** over time, and denying them to the enemy reduces where they can stage attacks from. Expect tough fights and serious counterattacks, but the payoff is large.
- **Seaports**: Seaports are strategic on coastal/island maps, and they can have a very direct economic payoff: on maps with multiple seaports, each friendly seaport can reduce **vehicle purchase prices** (up to a cap). They also shape where sea movement and sea-side attacks naturally happen, making them good staging points.
- **Resources**: Resource sites are one of the most straightforward income markers: each one you own adds a **large flat amount of money (“resources”) every ~10 minutes** as long as the site isn’t destroyed. They’re high-priority targets because the swing is immediate and continuous (you gain it, the enemy loses it).
- **Factories**: Factories are an **income multiplier** rather than a big payout on their own. Each factory you own increases how much money your controlled **resource sites** produce (stacking per factory), so factories scale better the more of the economy you already control. Prioritize factories once you’re ready to turn “some income” into “steady funding”.
- **Radio towers**: Radio towers (antennas) drive the “information war”: holding them increases how often you get **intel** like enemy vehicle reveals and warnings about enemy support/strikes. They also make “hearts and minds” actions in nearby towns more effective when the tower is alive and on your side. Because the benefit applies across many fights, radio towers are often worth hitting early.


---

### Info bar

The info bar is a persistent display at the top of your screen showing key campaign metrics. It displays: **HR** (Human Resources for recruiting), your **personal money**, **aggression levels** for Occupants and Invaders (how much they're targeting you), **war tier** (campaign progression), faction names, and your **undercover status**. If you're the commander, it also shows faction **resources** (shared money) and available **bomb runs**. You can toggle it on/off with a keybind (default Ctrl+F12) or via the player menu. Check it regularly to track your progress and enemy threat levels.

---

### Player Roles & Abilities

When you join the campaign, you select a **player role** that grants you specialized abilities and stat modifiers. Each role fills a different tactical niche, so coordinate with your team to cover all the bases.

**Available roles:**

- **Rifleman**: The balanced choice. Can **hack enemy UAVs** to turn them to your side.
- **Team Leader**: Stealthy scout and logistics expert. **0.8x visibility/audibility** (harder to detect), **1.4x load capacity** (carries more), and can use the **builder system** to construct fortifications.
- **Grenadier**: Heavy firepower specialist. **1.2x visibility** (easier to spot), but **0.8x fatigue from weight** (better stamina under load).
- **Autorifleman**: Sustained fire support. **1.2x audibility** (louder), but **0.8x fatigue from weight** (better stamina under load).
- **Medic**: Medical specialist. Can perform **advanced medical actions** like surgeries and PAK usage (if Advanced Medical is enabled in params).
- **Engineer**: Technical expert and builder. Can **build fortifications**, **defuse mines**, **repair vehicles**, and is an **explosives specialist**. Also benefits from **0.9x visibility** (stealthier) and **1.4x load capacity** (better stamina).
- **Commander**: Gets **all role benefits automatically** (except hacking UAVs, which requires Rifleman).

**Tips:**
- You can change roles at HQ via the **Player menu**
- Teams benefit from having at least one Medic and one Engineer
- Commanders have powerful strategic abilities—see the **[Commander functionality](../reference/commander-and-member-functionality.md)** guide for details

---

### Your Headquarters (HQ)

HQ is your "home base" for a lot of campaign actions. Don't turn it into a permanent battlefield by dragging enemies back to it.

At HQ, you can:
- **Recruit units** (at the flag): Spend HR to add AI squadmates to your team. These units will follow you and can be equipped with gear from the arsenal.
- **Access arsenal** (at the vehicle box): Customize your loadout with unlocked gear and weapons. The arsenal contains everything you've unlocked through campaign progress and captures.
- **Access garage** (at the vehicle box): Retrieve stored vehicles or manage your vehicle fleet. You can store vehicles here to keep them safe and access them later from any friendly garage location.
- **Buy vehicles** (at the flag or vehicle box): Purchase new vehicles with your personal money. This is how you expand your motor pool when you need specific vehicles for missions.
- **Restore units** (at the vehicle box): Bring back unconscious AI squadmates who were downed in combat. This lets you recover your team without having to recruit replacements.
- **Request missions** (from Petros): If you're a member, ask for new mission assignments. Petros will offer various mission types based on current campaign needs and your war tier.

---

### Arsenal

The **Arsenal** is your primary equipment management system, accessed at the vehicle box at HQ. It's where you customize your loadout with weapons, gear, and equipment collected during the campaign.

**How it works:**
- **Access**: Interact with the vehicle box at HQ to open the arsenal interface
- **Item collection**: Equipment looted from enemies and placed in the vehicle box is automatically added to the arsenal inventory
- **Unlocking system**: When you collect enough copies of an item (default 25), it becomes **permanently unlocked** with unlimited availability for all players
- **Limited items**: Items below the unlock threshold have finite quantities—take them and they're gone until you loot more
- **Member privileges**: Commanders and members can take any item regardless of quantity; regular players may be restricted until sufficient copies are available

**What gets unlocked:**
- Weapons (rifles, pistols, launchers), attachments (optics, grips, suppressors), uniforms, vests, backpacks, headgear, NVGs, magazines, explosives, and utility items
- Intel missions can also unlock weapons directly
- Starting equipment from your faction is available immediately
- Ammo for unlocked weapons can be automatically unlocked if enabled in parameters

The arsenal is central to progression: collect enemy equipment, build up your inventory, and unlock better gear as your stockpiles grow. Loot everything you can and bring it back to HQ to expand your available equipment.

---

### Commander and member functionality (advanced)

This is more advanced and **not covered in this beginners guide**.

- **[Commander and member functionality](../reference/commander-and-member-functionality.md)**

---

### Undercover

Undercover lets you move through enemy territory disguised as a civilian. Access it via the **Player menu** (click "Go Undercover"). It's great for scouting and positioning, but plan your exit—it will break.

**To go undercover, you need:**
- **Civilian uniform** (no military gear)
- **No weapons, vests, helmets, or NVGs**
- **Civilian vehicle only** (cars, bikes, civilian trucks—stay on roads when enemies are nearby)
- Not near enemies who can see you
- Not compromised (wait 30 minutes after being reported)

**What breaks undercover:**
- **Shooting or combat actions**
- **Equipping military gear** (weapons, vests, helmets, NVGs)
- **Entering enemy bases** (airbases are instant detection; outposts check based on aggression)
- **Driving off-road** near enemies or in non-civilian vehicles
- **Being spotted** by enemies

When undercover breaks, you're marked as compromised for **30 minutes** and can't go undercover again during that time. Your AI squadmates automatically disguise themselves when you go undercover if you're the group leader. Treat undercover as temporary—always have an escape plan ready.

---

### Victory / loss conditions

The campaign has clear win and lose conditions based on population support and strategic control. The system automatically checks these conditions after key events (like capturing airbases or losing cities) and during regular resource check cycles.

**Victory condition:**

You win the campaign when **both** of these are true:

1. **Control all airbases** on the map. Airbases (airports) are the highest-value strategic targets, and you must capture every single one from the enemy factions.
2. **Achieve majority population support**: More than 50% of the total civilian population must support your rebellion. This is calculated as:
   - For each city you **control**: Count the full city population multiplied by that city's rebel support percentage.
   - For each city you **don't control**: Count only 50% of the city population multiplied by that city's rebel support percentage.
   - If the total "rebel-supported population" exceeds 50% of the map's total population, this condition is met.

**What this means in practice:**
- You can't win just by taking all airbases—you also need hearts-and-minds work.
- You can't win just by building support—you must control every airbase too.
- Controlling cities doubles their contribution to your support total, making city captures valuable for both income and victory progress.
- The victory check runs immediately after you capture an airbase, so you'll know right away if you've won.

**Loss condition:**

You lose the campaign if **more than one-third (33.33%) of the total civilian population is killed** by cities being destroyed.

**How cities get destroyed:**
- **Invader punishment attacks**: If the Invaders launch a punishment attack against one of your cities and you fail to defend it, they will destroy the city completely. This involves killing all civilians, mining the area, and marking the location as destroyed. The civilians are permanently counted towards the loss condition and the city cannot be rebuilt. Any benefits like HR or income will no longer occur from that location. You will be given a "Punishment" mission to warn you that this act is occuring, it is obviously really important you show up and defend towns targeted by punishment missions.
- **Orbital strikes**: If an enemy orbital strike hits within 200 meters of a city, that city is immediately destroyed.

---

## Campaign Walkthrough

This section provides a strategic roadmap for progressing through an Antistasi campaign from start to finish. The campaign naturally divides into three phases based on your capabilities and objectives.

### Early Game: Building Your Arsenal

**Primary goal**: Acquire basic combat gear (rifle, body armor, helmet) and unlock essential equipment. This phase typically takes 10-20 hours of gameplay.

**What to focus on:**

- **Kill patrols**: Hunt down enemy patrols scattered around towns. They're relatively weak and provide easy gear.
- **Complete easy missions**: Prioritize "City Supplies" and "Kill the Traitor" missions. These have lower risk and good rewards.
- **Tackle checkpoints**: Once you have basic weapons, attack small checkpoints. They often have useful 50cal mounted vehicles you can capture.
- **Use all available resources**: Be creative with what you have. Improvise, adapt, overcome. Civilian vehicles, stolen enemy gear, and guerrilla tactics are your friends.
- **Destroy radio towers**: Once you obtain placeable explosives (C4, satchel charges), prioritize destroying nearby enemy radio towers. **This is crucial**: When a radio tower is destroyed or rebel-controlled, your positive influence on nearby populations is **DOUBLED**. This makes it much easier to win hearts and minds and gain passive income from towns.

**What NOT to do:**

- Don't try to capture and hold strategic zones yet. You lack the gear, manpower, and resources to defend them.
- Don't take on heavily defended positions or high-tier missions. Build up your capabilities first.
- Don't ignore the radio towers. They significantly slow down your population support growth if left in enemy hands.

### Mid Game: Taking Territory

**Primary goal**: Capture your first strategic zones, establish defenses, and build toward taking an airbase.

**What to focus on:**

- **Capture your first outpost or resource site**: Choose one with a radio tower if possible. You'll need to garrison it with AI soldiers—the exact number depends on the site's size and whether it's on the frontline, but expect to need a significant force (the game calculates garrison requirements dynamically based on marker size and strategic importance).
- **Defend against counterattacks**: Expect frequent enemy attacks depending on aggression levels. Successfully defending these attacks provides excellent gear-looting opportunities.
- **Fortify captured zones**: Use the builder system (Engineer or Team Leader roles) to place static weapons, cover, and defensive positions. This lets you stay on offense later.
- **Expand methodically**: Only attack new zones when you have the vehicles, HR (soldiers), and money to spare. Overextending will leave you vulnerable.
- **Use roadblocks and outposts strategically**: These help solidify your control over an area. Note that fast travel works between airbases, outposts, and seaports (as long as there are no enemies within 500 meters).
- **Capture enemy armor**: As you gain advanced AT (anti-tank) options, try to disable and capture enemy vehicles rather than destroying them. Turn their assets against them.
- **Train your soldiers**: Spend excess money on garrison training. This makes your AI troops more comparable to the enemy's hardened infantry.
- **Build your arsenal**: Continue collecting and unlocking weapons, vehicles, and equipment through missions and looting.

**Preparing for an airbase assault:**

You should only attempt to capture an airbase when you meet these conditions:

- **War Tier 3 or higher**: You cannot capture airbases below War Tier 3 (the flag capture action won't work).
- **Surplus of soldiers**: You need enough AI troops to both assault the base and garrison it afterward.
- **AA (Anti-Air) assets**: Enemy air support can devastate your assault force.
- **AT (Anti-Tank) assets**: Airbases have armored vehicle support.
- **Armored vehicles** (if possible): Having your own armor helps, but isn't strictly required.

**Important note**: Your first airbase assault doesn't have to succeed on the first try. It's often a war of attrition—launch multiple attacks, whittle down their defenses, and eventually break through.

### Late Game: Total Victory

**Primary goal**: Capture all airbases and achieve majority population support to win the campaign.

**What to focus on:**

- **Leverage your airbase**: Owning an airbase gives you passive income of airstrike points over time, plus access to air assets. You're now transitioning from a guerrilla resistance to a proper army.
- **Use airstrikes liberally**: You have bomb runs available—use them to soften up targets before assaults.
- **Deploy armor carefully**: Enemy AT weapons remain accurate and deadly. Always eliminate AT threats first, then focus on enemy armor.
- **Take advantage of the "collapse"**: As you capture more territory from the Occupants, the Invaders will also expand, creating a power vacuum. The Occupants may run out of vehicles and become unable to effectively counterattack. This is your chance to rapidly capture their remaining territory—it's essentially free real estate.
- **Defend every punishment mission**: Once the Occupants collapse, it's you versus the Invaders. The Invaders are ruthless with the civilian population. If they succeed in punishment attacks, they will **destroy entire cities**, killing all civilians in them. If more than one-third (33.33%) of the map's total population is killed, **you lose the game**. Punishment missions are your highest priority.
- **Expect massive attacks**: The Invaders have access to their full arsenal, including multiple jets, heavy armor, and advanced support calls. Prepare accordingly.
- **Continue hearts-and-minds efforts**: You need over 50% of the population supporting you (in addition to all airbases) to win. Keep working on city support through missions, killing enemies in cities, and controlling radio towers.
- **Stay persistent**: Late game is often a slog. You will die. You will fail attacks. The path to victory in Antistasi is persistence—keep trying, whittle down the enemy, and maintain pressure.

**Final victory requirements (both must be met):**

1. **Control ALL airbases** on the map
2. **More than 50% population support**:
   - Cities you **control**: Full population × support percentage counts toward your total
   - Cities you **don't control**: Only 50% of population × support percentage counts toward your total
   - Your "rebel-supported population" total must exceed 50% of the map's total population

**Remember**: This is a marathon, not a sprint. Antistasi is designed to be a long-term campaign. Stay focused, adapt to setbacks, and keep pushing forward. Good luck, Commander!