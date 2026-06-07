# Gameplan

## High Concept

The game is a roguelike autobattler inspired by Doomfields.

The player builds and evolves a team, progresses through stages, and makes route choices through different zones. Some zones may use a branching path structure where the player can choose between encounters, rewards, risks, or events.

## Core Structure

- Genre: Roguelike autobattler
- Run structure: Progress through stages and zones
- Zone structure: Can include branching paths with player choice
- Team structure: Start with 1 team member and cap at 5 team members
- Recruitment: The player has a chance to pick up a new character in each zone
- Combat style: Autobattler combat, with planning and build decisions happening outside direct combat control

## Combat And Positioning

Combat uses three lines:

- Front
- Mid
- Back

Position matters because abilities may target specific lines or adjacent positions.

Current formation concept:

- Grid layout with 3 spaces across the front/mid/back lines
- 6 spaces down
- Both teams share one battlefield grid and face each other
- Player side uses back/mid/front rows facing enemy front/mid/back rows
- Enemy side mirrors the player side across the center of the battlefield
- This layout should make closest-enemy targeting based on grid distance straightforward

Combat is real-time autobattler combat. Attack speed and cast speed should matter as timing stats.

Units do not move during combat after the fight begins. Formation choices matter because starting slots affect distance, targeting, adjacency, lines, and aura coverage.

Normal attacks usually target the closest enemy. Midline and backline characters can be attacked if they are closer than a frontline character. Abilities, class traits, equipment, or combat context may override this. Flyers are an important exception candidate because their rogue identity may let them attack less restricted targets.

For now, defeated team members revive after combat.

## Equipment

Each team member has these equipment slots:

- Main hand
- Offhand
- Armour

## Class And Evolution Structure

Current concept: 3 starter class families, each branching into 3 subclasses, then each subclass branching into 3 final forms.

This structure is provisional and should be workshopped before implementation.

Current broad class identities:

- Dino: Fighter class. Can branch into tank, berserker, or supportive roles.
- Reptile: Mage class.
- Flyer: Rogue class.

Each branch has:

- 4 abilities that can receive ability points
- 1 innate ability for evolved branches

Starter families, such as Dino, Reptile, and Flyer, each have 4 abilities. When a character evolves into a subclass, that subclass adds 4 abilities plus an innate ability. When a character evolves into a final form, that final form also adds 4 abilities plus an innate ability.

Characters keep all abilities and innates from prior evolution stages.

Ability design should become more specialized as a character evolves:

- Starter family abilities are self-affecting only: personal stats, basic attacks, and self-improvement
- Buffs, debuffs, auras, and team-facing effects start at subclass or final evolution tiers
- Subclass abilities are more specialized and begin defining the character's role
- Final evolution abilities are heavily specialized, unique, and build-defining

All levels grant an ability point.

The first point spent on an ability unlocks it. Additional points spent on that ability upgrade it. What each upgrade does depends on the specific ability.

Abilities can be passive or active. Active abilities use cooldown timers. All active abilities fire on cooldown during combat.

Characters evolve through experience levels and a choice made by the player.

```text
DINO
+-- Herbivore
|   +-- Triceratops
|   +-- Ankylosaurus
|   +-- Brachiosaurus
|
+-- Carnivore
|   +-- Tyrannosaurus
|   +-- Velociraptor
|   +-- Carnotaurus
|
+-- Omnivore
    +-- Gallimimus
    +-- Oviraptor
    +-- Troodon

REPTILE
+-- Snake
|   +-- Rattlesnake
|   +-- Constrictor
|   +-- Cobra
|
+-- Lizard
|   +-- Chameleon
|   +-- Monitor
|   +-- Gecko
|
+-- Crocodilian
    +-- Crocodile
    +-- Death Roller
    +-- Gharial

FLYER
+-- Bird of Prey
|   +-- Eagle
|   +-- Falcon
|   +-- Owl
|
+-- Flock Bird
|   +-- Raven
|   +-- Goose
|   +-- Parrot
|
+-- Pterosaur
    +-- Rhamphorhynchus
    +-- Pteranodon
    +-- Quetzalcoatlus
```

## Draft Ability Tree

Abilities use no numbers yet. This section is for names and rough design direction.

Assumptions for this draft:

- Auras affect adjacent allied slots.
- Buffs and debuffs may stack if timing or builds allow it.
- Starter abilities are simple and self-focused, with no buffs, debuffs, auras, or team-facing effects.
- Subclasses specialize, and final evolutions are unique or build-defining.
- Abilities should create stat archetypes, not just generic effects. A player should be able to tell what stats and items a species wants.
- Avoid making all flyers feel like "the unit that attacks backline." Flyers should split into leader, assassin, curse support, flock support, mimicry, control, bleed, and large-threat identities.

### Final Evolution Stat Targets

These are intended build directions, not hard restrictions.

| Species | Primary Stat Fantasy |
| --- | --- |
| Triceratops | Strength |
| Ankylosaurus | Strength |
| Brachiosaurus | Intelligence |
| Tyrannosaurus | Strength |
| Velociraptor | Agility |
| Carnotaurus | Strength/Agility |
| Gallimimus | Agility |
| Oviraptor | Intelligence/Agility |
| Troodon | Intelligence |
| Rattlesnake | Intelligence |
| Constrictor | Strength |
| Cobra | Intelligence |
| Chameleon | Agility |
| Monitor | Strength/Intelligence |
| Gecko | Agility |
| Crocodile | Strength |
| Death Roller | Strength |
| Gharial | Agility/Intelligence |
| Eagle | Agility |
| Falcon | Agility |
| Owl | Intelligence |
| Raven | Intelligence |
| Goose | Strength |
| Parrot | Intelligence |
| Rhamphorhynchus | Agility |
| Pteranodon | Intelligence |
| Quetzalcoatlus | Strength/Intelligence |

### DINO

- **Thick Hide**: Passive that improves survivability.
- **Heavy Bite**: Active attack against the closest enemy that establishes Strength as Dino's basic damage stat.
- **Bulk Up**: Directly increases this unit's Health.
- **Enduring Heart**: Passive that improves health recovery and staying power.

### Herbivore

- **Innate - Herd Guard**: Adjacent allies gain protection while this unit is alive.
- **Rooted Stand**: Passive that improves durability.
- **Stomp**: Active attack that can weaken enemies in a line.
- **Nourishing Presence**: Aura that improves healing received by adjacent allies.
- **Patient Defense**: Passive that rewards surviving long fights.

### Triceratops

- **Innate - Shielded Charge**: Opens combat by pressuring the nearest enemy and drawing attention.
- **Horn Wall**: Aura that protects allies behind or beside this unit.
- **Gore**: Active attack that applies armor reduction.
- **Challenge Roar**: Active debuff that encourages enemies to target this unit.
- **Last Bastion**: Passive that becomes stronger when allies are injured.

### Ankylosaurus

- **Innate - Spiked Shell**: Attackers take return damage.
- **Tail Club**: Active attack that can disrupt the target.
- **Stoneback**: Passive armor scaling.
- **Rattle Ground**: Active debuff that slows nearby enemies.
- **Punishing Guard**: Buff that increases thorns and resistance.

### Brachiosaurus

- **Innate - High Canopy**: Extends supportive effects farther through the formation.
- **Long Reach**: Active attack that can hit past the closest enemy.
- **Shelter Aura**: Aura that protects adjacent allies.
- **Gentle Giant**: Passive that improves healing power and ally recovery.
- **Earthshaker**: Active line attack that disrupts grouped enemies.

### Carnivore

- **Innate - Blood Scent**: Gains offensive pressure against injured enemies.
- **Lunge**: Active attack that pressures a vulnerable target.
- **Rend**: Active attack that applies a damage-over-time debuff.
- **Adrenal Rush**: Buff that improves attack speed after dealing damage.
- **Predator Focus**: Passive that improves critical attacks.

### Tyrannosaurus

- **Innate - Apex Predator**: Becomes more dangerous when facing fewer enemies.
- **Crushing Bite**: Heavy active attack against the closest enemy.
- **Terrifying Roar**: Active debuff that weakens enemy offense.
- **Bonebreaker**: Active attack that reduces armor and healing.
- **King's Momentum**: Passive that rewards kills or near-kills.

### Velociraptor

- **Innate - Pack Hunter**: Gains bonuses when allies attack the same target.
- **Flurry Claws**: Fast active multi-hit attack.
- **Hamstring**: Active attack that slows attack timing or weakens target pressure.
- **Open Wound**: Debuff that makes repeated hits more valuable.
- **Killer Instinct**: Passive that improves crit chains.

### Carnotaurus

- **Innate - Brutal Rush**: Gains power when charging into close targets, leaning into reckless Strength/Agility aggression.
- **Headbutt**: Active attack that can interrupt a cast.
- **Savage Impact**: Active attack that benefits from armor penetration.
- **Reckless Hide**: Buff that trades safety for attack speed, armor penetration, or missing-health damage.
- **Momentum Beast**: Passive that rewards repeated attacks without switching targets, especially in risky low-health fights.

### Omnivore

- **Innate - Opportunist**: Gains flexible bonuses based on the current fight state.
- **Clever Bite**: Active attack with a small debuff.
- **Forage**: Passive that improves sustain or reward value.
- **Distracting Call**: Active debuff that weakens enemy accuracy or focus.
- **Adaptable Stance**: Buff that shifts between offense and defense.

### Gallimimus

- **Innate - Swift Scout**: Improves team tempo at the start of combat.
- **Quick Jab**: Fast active attack.
- **Evasive Pathing**: Passive dodge improvement.
- **Fleet Aura**: Aura that improves adjacent allies' speed.
- **Hit And Run**: Active attack that rewards high agility.

### Oviraptor

- **Innate - Nest Thief**: Gains value from enemy buffs or battlefield advantages.
- **Snatch**: Active debuff that removes or weakens an enemy buff.
- **Guarded Egg**: Support ability that protects an ally briefly.
- **Scrappy Peck**: Active attack that scales with mixed stats.
- **Resourceful**: Passive that improves item or gold reward hooks later.

### Troodon

- **Innate - Bright Mind**: Converts intelligence into broader combat value.
- **Needle Bite**: Active attack that applies a debuff.
- **Tactical Call**: Buff that improves an ally's next ability.
- **Analyze Weakness**: Debuff that makes a target easier to damage.
- **Clever Pack**: Aura that improves adjacent allies' ability use.

### REPTILE

- **Arcane Scales**: Passive that improves magic durability.
- **Spit Bolt**: Simple active spell attack that establishes Intelligence as Reptile's basic damage stat.
- **Focused Mind**: Passive that improves cast speed or ability power.
- **Inner Glare**: Active self-focus that improves this unit's next spell.

### Snake

- **Innate - Venom Glands**: Attacks and spells can apply poison.
- **Venom Spit**: Active poison spell.
- **Coiling Threat**: Debuff that slows or pressures a target.
- **Shed Skin**: Defensive cleanse or resistance buff.
- **Toxic Patience**: Passive that rewards long fights.

### Rattlesnake

- **Innate - Warning Rattle**: Punishes enemies that approach or target this unit.
- **Rattle Hex**: Active debuff that weakens enemy speed.
- **Fang Snap**: Active poison attack against the closest enemy.
- **Nerve Venom**: Debuff that disrupts active abilities.
- **Danger Signal**: Aura that improves adjacent allies against debuffed enemies.

### Constrictor

- **Innate - Crushing Coil**: Focuses control on one target over time.
- **Bind**: Active debuff that locks down a target.
- **Squeeze**: Active damage that improves against controlled enemies.
- **Scaled Grip**: Passive durability while controlling a target.
- **No Escape**: Debuff that punishes enemies trying to retarget.

### Cobra

- **Innate - Royal Venom**: Poison effects become more burst-oriented.
- **Hood Flare**: Active debuff that intimidates nearby enemies.
- **Venom Lance**: Active spell that hits a priority target.
- **Toxic Bloom**: Poison effect that can spread when refreshed.
- **Deadly Dose**: Passive that improves poison against low-health enemies.

### Lizard

- **Innate - Cold Blooded**: Gains defensive value from timing and patience.
- **Sun-Baked Scales**: Passive resistance buff.
- **Elemental Spit**: Active spell attack.
- **Skitter**: Buff that improves dodge or target avoidance.
- **Distracting Colors**: Active debuff that weakens enemy targeting.

### Chameleon

- **Innate - Perfect Camouflage**: Becomes harder to target when not in front.
- **Color Shift**: Buff that changes defensive profile.
- **Tongue Lash**: Active attack that reaches unusual targets.
- **Mislead**: Debuff that interferes with enemy targeting.
- **Hidden Caster**: Passive that rewards casting from mid/back.

### Monitor

- **Innate - Relentless Monitor**: Applies steady pressure as a Strength/Intelligence battle mage.
- **Septic Bite**: Active attack that applies a weakening debuff.
- **Heavy Claws**: Active physical/magic hybrid attack that rewards mixed stat investment.
- **Predatory Stamina**: Passive sustain.
- **Ruinous Spit**: Active spell that reduces armor or resistance.

### Gecko

- **Innate - Wall Climber**: Gains evasive value from non-front positions.
- **Sticky Feet**: Passive dodge/control resistance.
- **Tail Drop**: Defensive active that escapes danger.
- **Bright Chirp**: Buff for adjacent allies.
- **Regrow**: Passive recovery after taking damage.

### Crocodilian

- **Innate - Ambush Predator**: Stronger opening attacks from stable positions.
- **Crushing Jaws**: Active close-range attack.
- **Mud Hex**: Debuff that slows enemies.
- **River Hide**: Passive armor/resistance.
- **Drag Under**: Active control effect on the closest enemy.

### Crocodile

- **Innate - Still Water**: Becomes stronger based on its chosen line.
- **Death Clamp**: Active attack that weakens the target over time.
- **Armored Lurk**: Passive durability.
- **Swamp Aura**: Adjacent enemies suffer a debuff.
- **Drowning Grip**: Control ability that punishes isolated targets.

### Death Roller

- **Innate - Rolling Terror**: Converts control into heavy area pressure.
- **Roll Thrash**: Active attack that damages adjacent enemies.
- **Bone Twist**: Debuff that reduces offense.
- **Blood In Water**: Passive that improves damage against wounded enemies.
- **Violent Spiral**: Big active attack with high disruption identity.

### Gharial

- **Innate - Needle-Snout Hunter**: Excels at precise attacks into mid/back.
- **Piercing Snap**: Active attack with armor penetration flavor.
- **Riverline Shot**: Active spell that targets along a line.
- **Patient Aim**: Passive that rewards cast timing.
- **Thin Profile**: Defensive passive against direct attacks.

### FLYER

- **Light Frame**: Passive dodge improvement.
- **Dive Strike**: Active attack that can ignore normal closest-target rules and establishes Agility as Flyer's basic damage stat.
- **Sharp Eyes**: Passive critical or targeting improvement.
- **Wingbeat**: Active self-technique that improves this unit's evasiveness.

### Bird of Prey

- **Innate - Predator's Angle**: Can pressure priority targets more easily.
- **Talon Rake**: Active attack that applies bleed.
- **Mark Prey**: Debuff that makes one enemy easier to focus.
- **High Perch**: Passive bonus from back or mid positions.
- **Kill Window**: Buff that improves attacks against injured enemies.

### Eagle

- **Innate - Commanding Wings**: Improves nearby allies when attacking marked targets.
- **Royal Dive**: Active strike against a marked or vulnerable enemy.
- **Sky Standard**: Aura that improves adjacent allies' offense.
- **Ripping Talons**: Active bleed-focused attack.
- **Apex Vision**: Passive that improves target selection and crits.

### Falcon

- **Innate - Blinding Speed**: Rewards high attack speed and cooldown cycling.
- **Flash Dive**: Very fast active attack.
- **Feinting Arc**: Buff that improves dodge after attacking.
- **Rapid Mark**: Debuff that supports repeated hits.
- **Terminal Velocity**: Passive that boosts the next strike after waiting.

### Owl

- **Innate - Silent Hunter**: Punishes debuffed or isolated enemies.
- **Night Glare**: Active debuff that weakens accuracy or casting.
- **Silent Talons**: Active attack against backline or vulnerable targets.
- **Dread Hoot**: Aura/debuff that pressures nearby enemies.
- **Moonlit Focus**: Passive ability-power/crit hybrid.

### Flock Bird

- **Innate - Flock Tactics**: Gains value when adjacent to allies.
- **Harass**: Active attack that applies a small debuff.
- **Shared Alarm**: Aura that improves adjacent allies' defense.
- **Pecking Order**: Buff that helps allies focus a target.
- **Wing Cover**: Support ability that protects a nearby ally.

### Raven

- **Innate - Bad Omen**: Debuffs on enemies become more valuable.
- **Caw Curse**: Active debuff spell.
- **Carrion Sense**: Passive bonus against injured enemies.
- **Black Feathers**: Aura that improves adjacent allies against debuffed enemies.
- **Ill Luck**: Debuff that interferes with enemy crits or dodges.

### Goose

- **Innate - Territorial Menace**: Punishes enemies that get close.
- **Honk Barrage**: Active disruption.
- **Wing Slap**: Active attack that can interrupt.
- **Mean Stance**: Defensive buff that draws pressure.
- **Protect The Flock**: Aura that protects adjacent allies.

### Parrot

- **Innate - Mimicry**: Copies or echoes supportive effects in a controlled way.
- **Repeat Call**: Active support that repeats a recent ally buff.
- **Bright Distraction**: Active debuff.
- **Learned Trick**: Passive that improves mixed builds.
- **Echo Chorus**: Aura that improves adjacent allies' ability use.

### Pterosaur

- **Innate - Ancient Wings**: Gains flexible targeting from flight.
- **Swoop**: Active attack that can reach past the closest enemy.
- **Wing Buffet**: Active disruption against a line or cluster.
- **Skyline Reach**: Passive targeting/range improvement.
- **Hollow Bones**: Passive speed and dodge with durability tradeoff.

### Rhamphorhynchus

- **Innate - Needle Swarm**: Repeated small hits become more dangerous.
- **Skewer Peck**: Active bleed attack.
- **Frenzied Flutter**: Buff that improves attack speed.
- **Scavenger's Cut**: Passive bonus against bleeding enemies.
- **Tiny Terror**: Debuff that stacks pressure through repeated attacks.

### Pteranodon

- **Innate - Open Sky Control**: Controls target access and punishes enemy formations.
- **Aerial Hook**: Active attack against mid/back targets.
- **Gale Push**: Active line disruption.
- **Glide Pattern**: Passive dodge/cooldown value.
- **Sky Net**: Debuff that weakens enemy flyers or evasive units.

### Quetzalcoatlus

- **Innate - Giant Shadow**: Threatens a large area and pressures backlines.
- **Spear Beak**: Active long-reach attack.
- **Shadow Pass**: Aura/debuff that affects adjacent allies and nearby enemies.
- **Titan Wings**: Active disruption across multiple slots.
- **High Sovereign**: Passive that rewards careful formation around this unit.

## Stats

When a character levels up, they gain a stat point that can be assigned to one primary stat:

- Strength
- Agility
- Intelligence

### Primary

- Strength: Adds 10 Health and 1 Physical Resistance
- Agility: Adds 1 Dodge Chance and 1 Attack Speed
- Intelligence: Adds 1 Cast Speed and 1 Ability Power

### Offense

- Attack Damage
- Attack Speed
- Critical Chance
- Critical Damage
- Ability Power
- Cast Speed

### Defense

- Health
- Armor
- Debuff Resistance
- Dodge Chance
- Healing Power

### Special

- Armor Penetration
- Lifesteal
- Thorns

## Damage And Effects

Current damage types:

- Physical
- Poison/Bleed

Physical Resistance reduces physical damage. Debuff Resistance reduces how long effects remain on the unit.

### Draft Status Effects

This is a review list before numbers are added.

- **Poison**: Damage-over-time effect, likely associated with Reptiles and Intelligence builds.
- **Bleed**: Damage-over-time effect, likely associated with Flyers, Carnivores, and repeated physical hits.
- **Slow**: Reduces attack timing or cast timing.
- **Weaken**: Reduces outgoing damage or pressure.
- **Armor Reduction**: Lowers physical durability so follow-up physical damage matters more.
- **Healing Reduction**: Lowers healing received.
- **Mark**: Makes a target easier to prioritize or focus.
- **Taunt/Challenge**: Encourages or forces enemies to target a specific unit.
- **Interrupt**: Disrupts an active ability or cast.
- **Control/Bind**: Restricts a target's ability usage, target choice, or combat pressure without moving it.
- **Cleanse**: Removes or shortens negative effects.
- **Shield/Guard**: Adds temporary protection or damage prevention.
- **Thorns**: Returns damage to attackers.
- **Dodge Up**: Improves chance to avoid attacks.
- **Attack Speed Up**: Improves basic attack timing.
- **Cast Speed Up**: Improves ability timing.
- **Ability Power Up**: Improves ability damage or effect strength.

### Draft Attack And Target Function Types

These are conceptual combat functions to define before implementation.

- **Closest Target Attack**: Targets the closest valid enemy by grid distance.
- **Line Attack**: Targets enemies in a front/mid/back line.
- **Piercing Line Attack**: Targets along a straight path and can hit past the closest enemy.
- **Adjacent Attack**: Targets enemies adjacent to the primary target or adjacent to the attacker.
- **Cluster Attack**: Targets a small group around a target slot.
- **Priority Target Attack**: Targets an enemy based on a rule such as lowest Health, marked, injured, backline, or highest threat.
- **Self Effect**: Applies a stat increase, self-technique, or self-only passive result.
- **Ally Aura**: Applies an effect to adjacent allied slots.
- **Enemy Aura**: Applies an effect to adjacent or nearby enemy slots.
- **Damage Over Time Application**: Applies Poison or Bleed.
- **Debuff Application**: Applies a named negative status effect.
- **Buff Application**: Applies a named positive status effect.
- **Cleanse/Remove Effect**: Removes or shortens buffs or debuffs.

## Design Priorities

- Clear dinosaur/stat/ability data structures
- Combat logic that is easy to balance
- Evolution tree logic that is easy to expand
- No "everything happens in Form1.vb" disasters
- Simple save/load structure
- Names that make sense to a non-expert

## Open Workshop Topics

- Whether the 3 x 3 x 3 class structure creates enough interesting choices without becoming hard to balance
- What each starter family should feel like mechanically
- Whether final forms should be strict upgrades, sidegrades, or build-defining transformations
- How equipment should interact with class identity
- How the 3-across and 6-down grid maps to each side's formation slots
- How the real-time timing model should work for Attack Speed, Cast Speed, cooldowns, and effect durations
- What the player chooses between battles
- How branching zones should generate risk and reward
- What resources exist during a run
- How healing, injury, and replacement should work if revival after combat needs more pressure later
- Whether abilities are class-locked, item-granted, learned, or mixed

## Zone Rewards And Recruitment

Later zones can offer pre-made characters, but the player can also choose to take a starter instead.

Possible rewards include:

- Equipment
- Gold
