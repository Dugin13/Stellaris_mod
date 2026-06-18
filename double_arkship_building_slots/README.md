# Double Arkship Building Slots

## Description
This mod doubles the building slot capacity for all arkship tiers in the Nomads DLC.

## Changes
Arkships now have the following building slots:

| Arkship Tier | Vanilla Slots | Modded Slots |
|--------------|---------------|--------------|
| Tier 1       | 4             | 8            |
| Tier 2       | 8             | 16           |
| Tier 3       | 12            | 24           |

This applies to all three arkship types:
- **Civilian Arkships** - General purpose colony arkships
- **Science Arkships** - Research-focused arkships with sensor bonuses
- **Military Arkships** - Combat-oriented arkships

## Compatibility
- **Game Version**: Stellaris v4.x
- **DLC Required**: The Nomads DLC
- **Conflicts**: May conflict with other mods that modify arkship building capacity
- **Compatibility**: Should be compatible with most other mods

## Installation
1. Subscribe to this mod or place it in your Stellaris mod directory
2. Enable the mod in the Stellaris launcher
3. Works with existing saves - arkships will immediately gain the extra building slots

## Files Modified
- `common/scripted_variables/arkship_building_slots_doubled.txt` - Overrides the arkship building capacity variables

## Notes
- This mod affects starbase building slot capacity on arkships, not district or module slots
- Vanilla tier values are 4/8/12; this mod doubles them to 8/16/24
- Works well with the Nomadic Empire Size Change mod if you want to reduce nomad empire size penalties too

## Technical Details
The mod overrides these scripted variables:
- `@arkship_starbase_building_capacity_add_4` → 8 (was 4)
- `@arkship_starbase_building_capacity_add_8` → 16 (was 8)
- `@arkship_starbase_building_capacity_add_12` → 24 (was 12)
