# Polymorph-Damage-Fix
Polymorph-Damage-Fix

These are the values returned by the function: GetPolymorphPower() to calculate the attack value in polymorphism

The problem is that ymir seems to have forgotten how to count elements in the array.

With a 0-point passive skill, you gain +10 power. This might not be surprising, but with 40 points (P), you exceed the array and instead of gaining +100 power, you gain 0 points.

In summary, with a G10 skill, you hit significantly harder than with a P skill.

The bug probably occurs on every private and global server.

Fix:

Just add: 

0,   // 0
At the very top of the array.
