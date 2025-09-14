# Brief Summary

This mod overhauls the durability system using coherent, RPG-inspired formulas.
The formulas have two components:

    - Basis: A constant value that never changes and represents the minimum durability loss that every weapon or armor will receive.
    - Skill: A modifier where weapon durability scales with skill stats and armor durability scales with SPECIAL stats.

Higher stats result in more resilient items, but they will not last forever (unless the basis is 0 and, in-game, the skill is at its maximum).
Note that 'basis' and 'skill' components can be modified in the INI file.


# Explanation

## Weapons

Weapons degrade per shot based on the following formula:

	fWeaponBaseHealth + (((100 - Skill) / 100) × fWeaponSkillMult)

Default values:

    - Skill = Big Guns, Small Guns, Energy Weapons, Unarmed, or Melee Weapons
    - fWeaponBaseHealth = 0.3
    - fWeaponSkillMult = 0.5

Both fWeaponBaseHealth and fWeaponSkillMult can be modified in the INI file.

## Armor

Armor degrades per hit using this formula:

	fArmorBaseHealth + (((10 - SPECIAL) / 10) × fArmorSkillMult)

Default values:

    - SPECIAL used in each case:
        • Strength → Power Armor & Armors with weight ≥ 25
        • Endurance → Armors with weight ≥ 15 and < 25
        • Agility → Armors with weight < 15
    - fArmorBaseHealth = 0.5
    - fArmorSkillMult = 0.5

Both fArmorBaseHealth and fArmorSkillMult can be modified in the INI file.


# Vanilla Mechanics

## Weapons (Default System)

Weapons degrade based on the formula:

	fDamageToWeapon*Mult × WeaponBaseDamage

Problems with this system:

    • Stronger weapons degrade faster (example of two weapons with the same health points):
        - Chinese Pistol: lasts ~1,250 shots.
        - 10mm Pistol: lasts only ~556 shots.
    • Lacks RPG depth and customization.

Note that 'fDamageToWeapon*Mult' refers to a set of GameSettings, where * can be replaced with 'Gun', 'Energy', 'Melee' and 'Launcher'.

## Armor (Default System)

Vanilla armor degradation is largely unknown, but based on observation:

    - A variable called fDamageToArmorPercentage exists.
    - Damage Resistance (DR) affects it.

This lack of knowledge may result in inconsistent behavior.


# Compatibility

This mod should be compatible with all other mods.
However, any modifications to durability from other mods will be likely overridden by this mod.


# Important Notes

    - You can install this mod mid-game without issues.
    - Safe to uninstall mid-game.
    - You can enable durability, disable it, and enable it again.


# Future Development

This mod is currently in its basic form, but future updates may include:

    • Perks affecting durability.
    • Luck influencing formulas.
    • Integrated UI enhancements.
    • Lots of bug-(never-disappear)-fixes.


# Source Code

GitHub Repository: https://github.com/ByMarcuus/newDurability