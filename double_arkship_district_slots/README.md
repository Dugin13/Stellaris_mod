# Double Arkship District Slots

## Description
This mod doubles the district slot capacity for all arkship tiers in the Nomads DLC.

## Changes
Arkships now have the following total district slots:

| Arkship Tier | Vanilla Districts | Modded Districts |
|--------------|---------------|--------------|
| Tier 1       | 9             | 18           |
| Tier 2       | 18            | 36           |
| Tier 3       | 27            | 54           |

This applies to all three arkship types:
- **Civilian Arkships** - General purpose colony arkships
- **Science Arkships** - Research-focused arkships with sensor bonuses
- **Military Arkships** - Combat-oriented arkships

## Compatibility
- **Game Version**: Stellaris v4.x
- **DLC Required**: The Nomads DLC
- **Conflicts**: May conflict with other mods that modify arkship district capacity
- **Compatibility**: Should be compatible with most other mods

## Installation
1. Subscribe to this mod or place it in your Stellaris mod directory
2. Enable the mod in the Stellaris launcher
3. Works with existing saves - arkships will immediately gain the extra district slots

## Files Modified
- `common/scripted_variables/arkship_building_slots_doubled.txt` - Overrides the arkship district capacity variables

## Notes
- This mod affects district capacity, not starbase building or module slots
- Vanilla tier totals are 9/18/27; this mod doubles them to 18/36/54
- Works well with the Nomadic Empire Size Change mod if you want to reduce nomad empire size penalties too

## Technical Details
The mod overrides these scripted variables:
- `@arkship_max_districts_add_0` → 9 (was 0)
- `@arkship_max_districts_add_9` → 27 (was 9)
- `@arkship_max_districts_add_18` → 45 (was 18)
