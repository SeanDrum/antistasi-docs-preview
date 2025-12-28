# AI Squad Management (Basic)

AI squad management allows players to recruit, command, and directly control AI squadmates to enhance their combat effectiveness and tactical options during missions.

## Recruiting AI Squadmates

**Location**: HQ flagpole

**Requirements**:
- You must have a radio (or radioman in certain mod sets)
- You must be the leader of your group
- You must have sufficient HR (Human Resources) - each unit costs 1 HR
- You must have enough money - unit costs vary by type (riflemen are cheapest, specialists like medics, engineers, and AT operators cost more)
- You must not be near enemies
- You must have unlocked the required weapons for that unit type
- Your group must not be full (maximum 9 total units including yourself)

**How it works**:
When you interact with the HQ flag and select "Recruit Squad", you'll see a menu with different unit types you can recruit. Each unit automatically joins your group when recruited - you don't need to do anything additional. The recruited AI will spawn near you at HQ and immediately become part of your squad.

**Unit types available**:
- Rifleman (basic infantry)
- Autorifleman (light machine gunner)
- Grenadier (rifle with grenade launcher)
- Anti-tank (rocket launcher operator)
- Medic (medical specialist)
- Marksman/Sniper (precision rifle)
- Engineer (explosives and repairs)
- Bomb Specialist (explosives expert)
- AT Missile Operator (guided anti-tank)
- AA Missile Operator (anti-aircraft)

## Basic Squad Control

Once AI are in your group, you can use standard Arma 3 command controls:

**Numbered keys (1-0)**: Select AI units by their position in your squad. The first AI is key 1, second is key 2, etc.

**Command menu**: Use the default Arma 3 interaction menu to give orders like move, hold position, engage targets, and more.

**Vehicle management**: You can order your AI squadmates into vehicles or tell them to get out. Select the unit and use the command menu, or assign them vehicle roles when you get in yourself.

**Equipment management**: AI can be equipped with gear from the arsenal just like players. Access the arsenal at HQ, select the AI unit, and give them weapons, armor, and equipment. This is useful for customizing your squad's loadouts for specific missions.

## Dismissing AI Squadmates

**How to dismiss**:
- Open the AI Management dialog from the Player menu
- Select the AI units you want to dismiss from the squad list
- Click the "Dismiss" button
- You must be the group leader to dismiss units

**Requirements**:
- You must be the group leader
- Units must be conscious and able to fight (you cannot dismiss unconscious units)
- You cannot dismiss Petros (the HQ contact)
- You cannot dismiss other players

**What happens when dismissed**:
When you dismiss AI, they leave your group and begin traveling back to HQ. Once they reach HQ (or after two minutes pass), they return to the recruitment pool and you get a partial refund:
- You get the full HR cost back (1 HR per unit)
- You get 50% of the unit's money cost refunded
- Any equipment the unit was carrying (weapons, magazines, items, gear) is automatically placed in the arsenal box at HQ
- There is a 60-second cooldown before you can recruit new units after dismissing

## Direct Control (AI Control Action)

Direct control allows you to take direct control of an AI unit, essentially "playing as" that unit for tactical positioning and precision tasks.

**How to use**:
1. Select a single AI unit from your squad bar (using the numbered keys 1-0)
2. Open the AI Management dialog from the Player menu
3. Click the "AI Control" button
4. You will immediately switch to controlling that AI unit

**Requirements**:
- You must be the group leader
- You must not be undercover (the action is blocked while in undercover mode)
- The AI unit must be alive and conscious
- You cannot control Petros
- You cannot control other players
- You cannot already be controlling another unit

**What happens during control**:
- You directly control the AI unit like you were playing as them - you can move, shoot, and interact exactly as if you selected that unit as your character
- Your original character is temporarily disabled but remains at your location
- You have 60 seconds of control time before automatically returning to your character
- The AI unit retains all of its equipment and capabilities

**Returning to your character**:
- **Automatic return**: You automatically return to your character after 60 seconds
- **Manual return**: Use the "Return" action available while controlling the AI
- **Damage return**: If either your original character OR the controlled AI takes any damage, you immediately return to your character
- **Fast travel**: While controlling an AI unit, you can use a special fast travel action to move your original character to the AI's location (only works when neither unit is near enemies)

**Tactical uses**:
Direct control is particularly useful for:
- Precise positioning of specific units (like placing an engineer exactly where you need them)
- Breaching and entry tactics where you need direct control
- Technical tasks requiring exact placement (like setting explosives)
- Scouting ahead while keeping your main character safe
- Any situation where standard AI behavior isn't precise enough

**Limitations**:
- You cannot go undercover while controlling an AI unit
- Your original character is vulnerable and disabled - make sure they're in a safe location
- You cannot control units that are already being controlled by another player
- The time limit means you need to work quickly

## Squad Size and Limitations

**Maximum squad size**: Your group can have up to 9 total units, including yourself. This means you can have up to 8 AI squadmates at once.

**Recruitment cooldown**: After dismissing units, you must wait 60 seconds before recruiting new ones. The cooldown stacks if you dismiss multiple times.

**Equipment availability**: Some unit types require that you have unlocked certain weapons. If you try to recruit a unit type whose weapons aren't available, the recruitment option will be disabled.

## Tips for Effective Squad Management

- **Specialize your squad**: Mix different unit types to cover all roles - medics for healing, engineers for repairs and explosives, AT for vehicles, etc.
- **Customize loadouts**: Use the arsenal to give your AI specialized equipment for specific missions
- **Manage resources**: Dismiss unused AI to get HR back for recruiting different specialists when needed
- **Position safely**: When using direct control, make sure your original character is in cover before taking control
- **Coordinate with team**: In multiplayer, communicate with other players about who has which specialists to avoid redundancy
- **Use vehicle transport**: Large squads benefit from transport vehicles - order AI into vehicles to keep them together and protected during travel


