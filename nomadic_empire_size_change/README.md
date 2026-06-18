# Nomadic Empire Size Change

## Description
This mod removes the empire size penalties that nomadic empires suffer from colonies and districts.

## Changes
In vanilla Stellaris, nomadic empires have the following modifier applied:
- `empire_size_colonies_mult = +100%` (doubles empire size from colonies)
- `empire_size_districts_mult = +100%` (doubles empire size from districts)

This mod sets both of these multipliers to 0, removing the penalty entirely so nomadic empires calculate empire size the same way as regular empires.

## Compatibility
- **Game Version**: Stellaris v4.x
- **Conflicts**: May conflict with other mods that modify the `nomadic_empire` static modifier
- **DLC Required**: The Nomads DLC (to play as nomadic empires)

## Installation
1. Place this mod folder in your Stellaris mod directory
2. Enable the mod in the Stellaris launcher
3. Start a new game or load an existing save

## Files Modified
- `common/static_modifiers/00_nomadic_empire_fix.txt` - Overrides the `nomadic_empire` modifier

## Notes
- This is a balance change that removes the vanilla double penalty for nomadic empires
- May make nomadic empires more powerful than intended by the base game
- This affects all nomadic origins including:
  - Voidfarers (default_nomads)
  - Sacred Path
  - Heirs of the Khan
  - Forever Cruise

## Technical Details
The mod overrides these values in the `nomadic_empire` static modifier:
- `empire_size_colonies_mult` → 0 (was +1 = +100%)
- `empire_size_districts_mult` → 0 (was +1 = +100%)
