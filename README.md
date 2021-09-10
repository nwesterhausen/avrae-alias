# avrae-alias

aliases used with the avrae bot

## Chaos Bolt

Accepts 2 arguments (in any order):

- `a` or `d`: cast the spell with **a**dvantage or **d**isadvantage respectively
- `2-10`: cast the spell using a higher level spell slot. Only the last number
  listed will be used for the casting level

Uses the following user variables:

- `charname`: the character name, defaults to "You"
- `spellattackmod`: the ranged spell attack modifier, defaults to 2

This alias handles all aspects of chaos bolt:

- damage type: when rolling the 2d8, it chooses one die at random and uses it
  to set the type of damage the chaos bolt will cause.
- up casting: if you specify a spell slot level 2-10, it will roll the
  additional d6 for damage
- attack roll: will roll the attack roll with advantage or disadvantage if
  specified in the arguments.
