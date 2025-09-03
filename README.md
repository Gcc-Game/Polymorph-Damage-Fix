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
At the very top of the array. Like this:

const int aiPolymorphPowerByLevel[SKILL_MAX_LEVEL + 1] =
{
	0,    // 0
	10,   // 1
	11,   // 2
	11,   // 3
	12,   // 4
	13,   // 5
	13,   // 6
	14,   // 7
	15,   // 8
	16,   // 9
	17,   // 10
	18,   // 11
	19,   // 12
	20,   // 13
	22,   // 14
	23,   // 15
	24,   // 16
	26,   // 17
	27,   // 18
	29,   // 19
	31,   // 20
	33,   // 21
	35,   // 22
	37,   // 23
	39,   // 24
	41,   // 25
	44,   // 26
	46,   // 27
	49,   // 28
	52,   // 29
	55,   // 30
	59,   // 31
	62,   // 32
	66,   // 33
	70,   // 34
	74,   // 35
	79,   // 36
	84,   // 37
	89,   // 38
	94,   // 39
	100,  // 40
};

