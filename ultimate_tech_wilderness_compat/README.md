# Ultimate Technologies - Wilderness Compatibility

This mod fixes compatibility issues between Ultimate Technologies and Wilderness origin Hive Mind empires, plus critical bugs affecting ALL hive minds and gestalts.

## The Issues

### 1. Neural Uplink Datacore (building_ult_datacore) - **BROKEN FOR ALL HIVE MINDS**
- Original uses `job_synapse_drone_add` which references a placeholder job with `possible = { always = no }`
- **These synapse_drone jobs can NEVER be worked by ANY hive mind!**
- Machine empires worked because they use the actual `coordinator` job

### 2. Gestalt Terminal (building_ult_gestalt_terminal) - **BROKEN FOR ALL HIVE MINDS**
- Same issue: uses broken `job_synapse_drone_add` placeholder
- Only worked for Machine empires

### 3. Intelligent Laboratory (building_ult_intelligent_lab) - **BROKEN FOR ALL HIVE MINDS**
- Uses `job_brain_drone_physicist` which has `possible = { always = no }`
- **These jobs can NEVER be worked by ANY hive mind!**
- This building is completely broken for all hive mind empires in the original mod

### 4. Industrial Atomic Assembler (building_ult_industrial_atomic_assembler) - **MISSING FOR ALL GESTALTS**
- Ultimate Technologies provides a massive alloy production building (200 jobs, +10% alloy output)
- Only available to regular empires (`is_regular_empire = yes`)
- **No equivalent exists for gestalt empires** (hive minds, wilderness, machines)
- Gestalts are completely locked out of this major production building

### 5. Commercial Center (building_ult_commercial_center) - **MISSING FOR ALL GESTALTS**
- Ultimate Technologies provides a massive trade generation building (600 trader jobs, 100 entertainer jobs, 200 product designer jobs)
- Only available to regular empires (`is_regular_empire = yes`)
- **No equivalent exists for gestalt empires**
- Regular empires get 4,800+ trade value/month, gestalts get nothing
- Major imbalance for market purchases and planetary deficit coverage

### 6. Technology Prerequisites - **COMPLETELY BLOCKS WILDERNESS EMPIRES**
- Vanilla Stellaris blocks Wilderness from Tier 3 technologies:
  - **tech_society_3** (Biostructural Synthesis) - `is_wilderness_empire = no`
  - **tech_engineering_3** (Nanomechanics) - `is_wilderness_empire = no`
  - **tech_physics_3** (Quantum Field Manipulation) - `is_wilderness_empire = no`
- Ultimate Technologies requires these for THREE critical tech chains:
  - **tech_ult_nano_drone_colony** requires tech_society_3
    - Blocks tech_ult_nano_drone_enhance (unlocks trait_ult_immortal)
    - Blocks tech_ult_paradise_homeplanet (needed for Gestalt Commercial Center!)
  - **tech_ult_molecular_manipulation** requires tech_engineering_3
    - Blocks building_ult_gestalt_atomic_assembler (our gestalt alloy building!)
    - Blocks tech_ult_paradise_homeplanet
  - **tech_ult_beyond_dimension** requires tech_physics_3
    - Blocks +50% shields, +10 evasion bonuses
- **Wilderness empires are locked out of the entire late-game tech tree**
- **The gestalt buildings we created are UNREACHABLE without this fix**

## The Fixes

This mod overrides broken buildings and creates gestalt equivalents:

### Neural Uplink Datacore & Gestalt Terminal
**Fix:** Use the actual `coordinator` job for ALL gestalt empires. The game automatically swaps display names:
- **Machine Empires:** Shows as "Coordinator"
- **Standard Hive Minds:** Shows as "Synapse Drone"  
- **Wilderness Hive Minds:** Shows as "Choirsymbiont"

### Intelligent Laboratory
**Fix:** Use `calculator_physicist/biologist/engineer` jobs for ALL gestalt empires. The game automatically swaps display names:
- **Machine Empires:** Shows as "Calculator"
- **Standard Hive Minds:** Shows as "Brain Drone"
- **Wilderness Hive Minds:** Shows as "Evosymbiont"

### Industrial Atomic Assembler - NEW BUILDING
**Solution:** Created `building_ult_gestalt_atomic_assembler` for gestalt empires:
- Uses `job_fabricator_add = 200` (standard gestalt alloy job)
- Provides same +10% alloy production bonus
- Requires `tech_ult_molecular_manipulation` (same as regular version)
- Available to ALL gestalt empires (hive minds, wilderness, machines)
- Same costs: 1000 minerals + 200 volatile motes, 10 energy upkeep
- Limited to 3 per planet (base_cap_amount = 3)

### Commercial Center - NEW BUILDING
**Solution:** Created `building_ult_gestalt_commercial_center` for gestalt empires:
- Uses `job_logistics_drone_add = 600` (produces 6 trade each = 3,600 trade/month)
  - Wilderness shows as "Spindlesymbiont"
  - Standard hive shows as "Logistics Drone"
  - Machine shows as "Logistics Drone"
- Uses `job_maintenance_drone_add = 100` (amenities + 1 trade each = 100 trade/month)
- Total: **3,700 trade value/month** (vs regular empire's 4,800+ trade/month)
- Requires `tech_ult_paradise_homeplanet` (same as regular version)
- Same costs: 1000 minerals, 5 energy upkeep

### Technology Prerequisites - CRITICAL FIX FOR WILDERNESS
**Solution:** Override THREE Ultimate Technologies techs to remove blocked Tier 3 requirements:

**tech_ult_nano_drone_colony:**
- Original: Requires tech_ult_ultimate_technology + **tech_society_3** (blocked for Wilderness)
- **Fixed:** Requires tech_ult_ultimate_technology only
- Unlocks: tech_ult_nano_drone_enhance → **trait_ult_immortal** (immortal leaders!)
- Unlocks: tech_ult_paradise_homeplanet (needed for Gestalt Commercial Center)
- Benefits: -20% ship upkeep, +25% megastructure build speed, +20% food production

**tech_ult_molecular_manipulation:**
- Original: Requires tech_ult_ultimate_technology + **tech_engineering_3** (blocked for Wilderness)
- **Fixed:** Requires tech_ult_ultimate_technology only
- Unlocks: building_ult_gestalt_atomic_assembler (our new gestalt alloy building!)
- Unlocks: tech_ult_paradise_homeplanet
- Benefits: -20% job upkeep, -20% megastructure cost, +20% alloy production

**tech_ult_beyond_dimension:**
- Original: Requires tech_ult_ultimate_technology + **tech_physics_3** (blocked for Wilderness)
- **Fixed:** Requires tech_ult_ultimate_technology only
- Benefits: +50% shields, +10 evasion

**Impact:** Without this fix, Wilderness empires cannot access:
- Immortal trait (trait_ult_immortal)
- Gestalt Atomic Assembler building
- Gestalt Commercial Center building
- Paradise Homeplanet tech and all its benefits
- Multiple late-game tech chains in Ultimate Technologies

All buildings maintain equivalent bonuses and costs.

## Installation
1. Subscribe to Ultimate Technologies on Steam Workshop (ID: 924990631)
2. The mod files are already in: `Documents\code\Stellaris_mod\ultimate_tech_wilderness_compat\`
3. The .mod file has been copied to: `Documents\Paradox Interactive\Stellaris\mod\`
4. Enable this mod in your Stellaris launcher
5. **Make sure it loads AFTER Ultimate Technologies** in your playset

## Testing
1. Load your Wilderness Hive Mind save (or any Hive Mind/Gestalt empire)
2. Research required technologies
3. Build any of the fixed/new buildings
4. Your pops should now be able to work all jobs created by these buildings

## Notes
- All fixes benefit **ALL gestalt empires**, not just Wilderness
- Gestalts now have equivalent production and trade generation capabilities
- Trade value is essential for market purchases and planetary deficit coverage
- If the origin key is incorrect, you may need to check your game files for the exact Wilderness origin identifier
- Currently using `origin_progenitor_hive` as the Wilderness origin key

## Compatibility
- Requires: Ultimate Technologies (Workshop ID: 924990631)
- Compatible with: Stellaris 4.3.x
- Designed for: Wilderness Origin (Hive Minds) and all Gestalt empires