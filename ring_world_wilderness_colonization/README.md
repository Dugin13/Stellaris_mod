# Ring World Wilderness Colonization

This mod allows Wilderness origin empires to colonize ring worlds and relic worlds.

## The Problem
Wilderness origin empires face FOUR hardcoded obstacles when trying to colonize AND construct ring worlds and relic worlds:

1. **Cannot research Ring World technology** - Vanilla Stellaris blocks Wilderness from `tech_ring_world` with `potential = { is_wilderness_empire = no }`. This means Wilderness empires can NEVER build new ring world megastructures, even if they find instructions or have Mega-Engineering.

2. **Must terraform before colonizing** - Wilderness empires cannot directly colonize any planet; they must terraform it first. Ring worlds and relic worlds cannot be terraformed through normal means, showing "no valid world to terraform to".

3. **0% Habitability on artificial worlds** - Wilderness empires have the restriction "the wilderness can not survive on un-natural worlds", giving them 0% habitability on all artificial planets including ring worlds and relic worlds.

4. **Hardcoded pop death** - The game has a hardcoded rule (`is_habitable_for_wilderness` trigger) that causes wilderness pops to decline and die on any artificial planet (`is_artificial = yes`), regardless of habitability modifiers. This is what causes "WILDERNESS_NATURAL_WORLDS_DECLINE".

## The Solution
This mod provides FOUR comprehensive fixes via the Ring World Pioneers ascension perk:

**1. Technology Override**
Overrides `tech_ring_world` to remove the `is_wilderness_empire = no` restriction. Wilderness empires can now:
- Research the Ring World technology after unlocking Mega-Engineering
- Construct new ring world megastructures
- Build ring world segments like any other empire

**2. Self-Terraform Links**
Adds terraform links that allow ring worlds and relic worlds to "terraform to themselves":
- Ring World → Ring World (instant, free)
- Relic World → Relic World (instant, free)

This satisfies the wilderness terraform requirement without actually changing the planet type.

**3. Habitability Boost**
The ascension perk grants **+100% habitability** on ring worlds and relic worlds, overcoming the "unnatural worlds" restriction. This brings wilderness pops from 0% to 100% habitability on these planets.

**4. Override Hardcoded Pop Death Mechanic**
Overrides the `is_habitable_for_wilderness` scripted trigger to add an exception: wilderness pops with the Ring World Pioneers ascension perk can now survive on ring worlds and relic worlds. This prevents the "WILDERNESS_NATURAL_WORLDS_DECLINE" pop death that would otherwise occur on artificial planets.

## Requirements
- Must have the **Ring World Pioneers** ascension perk (provided by this mod)
- Must be a **Wilderness empire**

## How to Use

### To Construct Ring Worlds:
1. Research Mega-Engineering technology
2. Research Ring World technology (now available to Wilderness!)
3. Build ring world megastructures like any empire

### To Colonize Existing Ring Worlds/Relic Worlds:
1. Discover a ring world or relic world
2. Get the **Ring World Pioneers** ascension perk
3. Click the planet and select "Terraform"
4. Choose the terraform option (planet → same planet)
5. After the instant "terraform" completes, you can colonize normally

## Features
- **Technology Override:** Wilderness empires can now research Ring World technology and construct ring worlds
- New ascension perk: "Ring World Pioneers"
  - Requires Mega-Engineering technology
  - Grants **+100% habitability** on ring worlds and relic worlds (makes them fully habitable for wilderness pops)
  - Unlocks self-terraform for wilderness empires
- Free and instant "terraform" process for colonization
- Works with all ring world types and relic worlds
- Fully compatible with wilderness empire mechanics
- Wilderness empires have full parity with other empires for ring world content

## Compatibility
- Requires: Stellaris 4.3.x
- Designed for: Wilderness Origin (Hive Minds)
- Compatible with: All DLC and most other mods
- **Important:** The mod uses file naming (99_ prefix) to ensure it loads AFTER base game wilderness mechanics
- **You must restart Stellaris after enabling the mod** for the scripted trigger override to take effect
