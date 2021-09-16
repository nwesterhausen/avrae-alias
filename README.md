# avrae-alias

aliases used with the avrae bot

## Chaos Bolt

Accepts 2 arguments (in any order):

- `a` or `d`: cast the spell with **a**dvantage or **d**isadvantage respectively
- `2-10`: cast the spell using a higher level spell slot. Only the last number
  listed will be used for the casting level

Uses the following variables:

- `charname`: the character name, defaults to "You". Will prefer to use the
  name of your current character, then will check for a uvar by "name"
- `spellattackmod`: the ranged spell attack modifier, defaults to 2. Will prefer
  to use the spell attack + proficiency from your character, otherwise it will
  use a uvar "spell" and add it to uvar "proficiencyBonus"

This alias handles all aspects of chaos bolt:

- damage type: when rolling the 2d8, it chooses one die at random and uses it
  to set the type of damage the chaos bolt will cause.
- up casting: if you specify a spell slot level 2-10, it will roll the
  additional d6 for damage
- attack roll: will roll the attack roll with advantage or disadvantage if
  specified in the arguments.

## Fire Bolt

Accepts 1 argument:

- `a` or `d`: cast the spell with **a**dvantage or **d**isadvantage respectively

Uses the following variables:

- `charname`: the character name, defaults to "You". Will prefer to use the
  name of your current character, then will check for a uvar by "name"
- `spellattackmod`: the ranged spell attack modifier, defaults to 2. Will prefer
  to use the spell attack + proficiency from your character, otherwise it will
  use a uvar "spell" and add it to uvar "proficiencyBonus"
- `charlevel`: the character's level, defaults to 1. Will prefer to use the level
  of your current character, then it will check for a uvar "level"

This alias handles scaling the damage of fire bolt with character level as well
as rolling attack (with advantage or disadvantage as needed).

## Wild Magic Surge

This alias accepts 1 argument:

- `1-10`: level of the spell cast. If you don't include the argument, it will assume
  that you cast a level 1 spell. This is used for the optional rule listed in the wiki:
  "Instead of a flat 5% ... roll d20 and subtract the level of the spell" If you supply
  an argument > 19 then you will guarentee a wild magic surge.

Uses the following variables:

- `charname`: the character name, defaults to "You". Will prefer to use the
  name of your current character, then will check for a uvar by "name"

This alias will do both the chance roll for wild magic surge, and then will roll
for a wild magic effect. It uses the homebrew wild magic suge table variant from
[d&d wiki](<https://www.dandwiki.com/wiki/Wild_Magic_Surge_Table,_Variant_(5e_Variant_Rule)>).
The roll tables are stored in the following global variables:

| gvar                                 | description      |
| ------------------------------------ | ---------------- |
| 8997aaef-5010-4048-9604-7f37d4661c01 | nuisance effects |
| 98425f5f-5851-45fb-aef5-dc3ce6a08375 | moderate effects |
| 8997aaef-5010-4048-9604-7f37d4661c01 | extreme effects  |

I have stored the value of these tables in the [gvars](/gvars) directory.
