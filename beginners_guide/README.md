# Beginners Guide

This is the casual “how do I actually play this?” guide.


---

# Setup UI

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

### Set HQ position

See **[Set HQ position (HQ placement)](../reference/set-hq-position.md)**.

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

### Map markers

This section is intentionally short. For Antistasi, the question is always: **“What does this marker mean for the campaign?”**

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

This is more advanced and **not covered in this beginners guide**. Placeholder:

- **[Commander and member functionality](../reference/commander-and-member-functionality.md)**

---

### Undercover and how to use it

Undercover is great for scouting and getting into position before you start shooting. Assume it will eventually break; plan your exit.

---

### Victory / loss condition

Winning is usually about **controlling key strategic locations** and **having enough population support**—not just painting the whole map your color.

---

## Missions

Mission types commonly include:

- Conquest
- Destroy
- Assassination
- Convoy ambush
- Rescue
- Logistics
- Support

Pick missions that match your group size and patience.

---

## Vehicles

Vehicles are campaign progress. Treat them like valuable assets, not disposable taxis.

---

## Walkthrough (very short)

- **Early**: get gear and intel, stay alive, don’t start base sieges.
- **Mid**: take a strategic point, defend it, build momentum.
- **Late**: airbases and big pushes—expect heavy resistance.


