Car RPG
=======

Car RPG is a "tabletop" role playing game system for impromptu sessions when one has no tabletop. It is inspired by [Risus](http://www222.pair.com/sjohn/risus.htm) by S. John Ross.

Participants
------------
* 1 Game master (GM)
* 1 &le; Player characters (PCs)

If the game is being played while traveling, I recommend **not** allowing the driver to be the GM, as it is distracting.
The PCs are fully responsible for keeping track of their character statistics and status (usually in their heads) and being honest about them, as the GM won't be able to keep track.

Character Creation
------------------
Put 5 points into 2 clich&eacute;s. You can make them up.

### Example Clich&eacute;s:
* Cowboy
* Mobster
* Chef
* Yeti
* Kung-fu master

### Example Characters:
* 2 Olympic runner, 3 Biker
* 4 Busboy, 1 Secret agent

Conflict Resolution
-------------------
When a PC says his or her character does something non-trivial where success or failure will affect the narrative significantly (e.g. jump a gorge, hack a computer, cook an important meal), he or she must "roll" for it.

1. The PC chooses a clich&eacute; that still has points left.
+ The GM chooses a difficulty number (_DC_), usually 1 &le; _DC_ &le; 4.
+ The GM calculates the number of "rolls" the player will make: |_DC_ - _clich&eacute; points_| + 1.
+ If _DC_ > _clich&eacute; points_, the PC must "roll" *all* successes.
+ If _DC_ < _clich&eacute; points_, the PC need only "roll" *1* success.
+ For each "roll":
  1. The GM secretly chooses a number, 1 or 2.
  + The player guesses either 1 or 2.
  + If guessed correctly, add one success.
+ If the PC got the required number of successes (as referenced in steps 4 and 5), he or she explains his or her action.
+ If the PC did not get the required number of successes, the GM explains how he or she failed.

Put another way:

```python
from random import randint
def doesPCSucceed(DC, clichePoints):
    rollCount = abs(DC - clichePoints) + 1
    successes = [input('Choose 1 or 2: ') == randint(1,2) for r in range(rollCount)]
    return (DC >= clichePoints and all(successes)) or (DC < clichePoints and any(successes))
```

### Example
<!-- TODO -->

Combat
------
<!-- TODO: clarify this section -->
When successful conflict resolution would bring harm to another character (PC or GM controlled), the defending character chooses a clich&eacute; to defend with. The _DC_ is equal to that clich&eacute;'s remaining points.

If a GM controlled character is attacking a PC, instead the DC is the attacker's remaining chosen clich&eacute; points and the PC "rolls". Why? The GM can't "roll" against him or herself.

The loser loses 1 point in their chosen clich&eacute;. When any clich&eacute; hits 0, the winner chooses what happens.

Ending the game
---------------
Since Car RPG is designed to be played while everyone is bored and waiting like on a car trip, the GM should start wrapping up in the final few minutes, even if it seems rather abrupt.
