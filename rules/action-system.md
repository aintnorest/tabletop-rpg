# Action System

## Core Mechanics

The action system uses **action tokens** to regulate what characters can do during their turn.

### Action Types

- **Universal Actions**: Actions that anyone can take (e.g., Move, Run, Help). These are shared between all characters at the table.
- **Character-Specific Actions**: Unique actions tied to individual characters. Several are tied to their archetypes while the majority are created through character creation and character progression.

## Action Token Progression

Characters gain action tokens as they increase in tier:

- **Tier 1**: 3 action tokens
- **Tier 3**: 4 action tokens
- **Tier 5**: 5 action tokens
- **Tier 6**: 6 action tokens

## Using Action Tokens

- Characters can spend their action tokens on either universal actions or their character-specific actions.
- Some actions have scaling effects based on the number of action tokens invested in them.
- Action tokens represent committed resources and remain allocated until recovered.

## Token Recovery

At the start of a character's turn, they may pull back **one action token** from any action where they currently have tokens allocated.

## Universal Tier 1 Actions

> **Attack (1 Token) [Active]**
> * **Range**: 0
> * **Target**: An enemy
> * **Effect**: Atk +0 Res. Max Dmg 2.

> **Defend (1 Token) [Reaction]**
> * **Range**: Self
> * **Target**: Self
> * **Effect**: Def + Draw 1 vs one Atk.
> * **Special**: Only when targeted by an Atk.

> **Move (1 Token) [Active]**
> * **Range**: Self
> * **Target**: Self
> * **Effect**: Move up to 3".

> **Run (2 Tokens) [Active]**
> * **Range**: Self
> * **Target**: Self
> * **Effect**: Move up to 7".

> **Reposition (1 Token) [Active]**
> * **Range**: 0
> * **Target**: A character or terrain
> * **Effect**: Reposition the target up to 2".
> * **Special**: Allows Assistance.

> **Expose (1 Token) [Active]**
> * **Range**: 6"
> * **Target**: An enemy
> * **Effect**: +1 Exposed.

> **Impair (1 Token) [Active]**
> * **Range**: 6"
> * **Target**: An enemy
> * **Effect**: +1 Impaired.

> **Hinder (1 Token) [Active]**
> * **Range**: 6"
> * **Target**: An enemy
> * **Effect**: +1 Hindered.

> **Catch Breath (1 Token) [Active]**
> * **Range**: Self
> * **Target**: Self
> * **Effect**: -1 of any condition.

> **Center (1 Token) [Active]**
> * **Range**: Self
> * **Target**: Self
> * **Effect**: Gain 1 Essence.
> * **Special**: Once per turn.

> **Interact (1 Token) [Active]**
> * **Range**: 1"
> * **Target**: An object or terrain
> * **Effect**: Use an item or interact with the environment. Make a Draw if uncertain.

> **Help (1 Token) [Reaction]**
> * **Range**: Varies
> * **Target**: An ally
> * **Effect**: Provide Assistance to the target's action.
> * **Special**: Range determined by GM based on the action being assisted.

---

# Reading Actions

All actions use this format:

```
ACTION NAME (X Tokens, Y Essence) [Timing]
Range: [Distance/Template]
Target: [What can be targeted]
Effect: [What happens, in order]
Special: [Conditional effects or restrictions]
```

**Timing**: `[Active]` — used on your turn. `[Reaction]` — used in response to a trigger. `[Sustained]` — ongoing effect requiring upkeep.

**Target**: Describes what the action can affect (e.g., An enemy, An ally, A character, Self). Effect text uses "the target" to refer to the selected character or object.

**Assistance**: Actions that allow Assistance can benefit from ally help. See *Resolution Mechanic* for Assistance rules.

## Game Terms Reference

- **Movement** (Move, Advance, Retreat, Place, Push, Pull, Reposition, Size & Tier Resistance): See *Positioning*
- **Attacks** (Atk, +X Res, Max Dmg, Hit, Miss): See *Resolution Mechanic*
- **Conditions** (+X Exposed, -X Impaired, etc.): See *Conditions*

