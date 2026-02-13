# Action System

## Core Mechanics

The action system uses **action tokens** to regulate what characters can do during their turn.

### Action Types

- **Universal Actions**: Actions that anyone can take (e.g., Move, Dash, Help). These are shared between all characters at the table.
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

---

# Action Template & Language Guide

## Action Template

All actions follow this standardized format for maximum clarity:

```
ACTION NAME (X Tokens, Y Essence) [Timing]
Range: [Distance/Template]
Target: [What can be targeted]
Effect: [What happens, in order]
Special: [Conditional effects or restrictions]
```

### Template Components

**ACTION NAME**: Use active verbs. Be specific and evocative.

**Token Cost**: Always displayed in parentheses immediately after the name. If the action costs Essence, include it after the Token cost separated by a comma.
- Examples: `(1 Token)`, `(2 Tokens, 3 Essence)`, `(1 Token, 8 Essence)`
- Tier 1-2 actions typically cost only Tokens unless supernatural
- Tier 3+ actions cost both Tokens and Essence

**Timing**: Displayed in brackets. Options:
- `[Active]` - Used on the character's turn
- `[Reaction]` - Used outside the character's turn in response to a trigger
- `[Sustained]` - Ongoing effect requiring upkeep

**Range**: The distance or area the action affects.
- Use specific measurements: `Range 0`, `Range 6"`, `Range 12"`
- Templates: `8" Cone`, `10" Line`, `3" Circle` (diameter implied)
- `Self` for actions affecting only the acting character

**Target**: What the action can affect.
- Be specific about what can be targeted:
  - `An enemy`
  - `An ally`
  - `A character` (any character, friend or foe)
  - `Up to X characters` (choose up to the specified number)
  - `All characters within X"`
  - `A terrain`
  - `A character or terrain`
  - `An enemy & a terrain`
- Include size/tier restrictions if applicable

**Effect**: The mechanical outcome, written in order of resolution.
- Use numbered steps for complex sequences
- Each sentence describes one discrete game effect
- Use implicit subject for self-actions (no pronoun needed)
- Use explicit labels for other characters: "the target", "an ally", "an enemy", etc.

**Special**: Conditional triggers, restrictions, or additional rules.
- Use "If/Then" structure for clarity
- State limitations explicitly

---

## Consistent Language Guide

### Keywords & Definitions

Use these exact terms consistently throughout all action descriptions:

#### Movement Terms
- **Move**: Change position up to the specified distance
- **Advance**: Move in a straight line toward the target. The line must be drawn so that if you continued the full distance, you would end B2B with the target. You may stop at any point along this line before reaching B2B.
- **Retreat**: Move in a straight line directly away from the target.
- **Place**: Position the character or object at a specific location (ignores intervening terrain)

**Forced Movement** (Push, Pull, Reposition):
All forced movement is subject to **Size & Tier Resistance**. The distance is reduced by 1" for each size category the target is larger than the acting character. The distance is also reduced by 1" for each Tier the target is higher than the acting character. Size and Tier reductions are cumulative. If the final distance is 0" or less, the forced movement fails and the target does not move.

When forced movement affects multiple targets, the acting character chooses the order targets are moved. Forced movement stops if the target contacts another character or terrain.

- **Push**: Force a character or terrain to move directly away in a straight line. Subject to Size & Tier Resistance.
- **Pull**: Force a character or terrain to move directly toward in a straight line. Subject to Size & Tier Resistance.
- **Reposition**: Force a character or terrain to move in any direction. Subject to Size & Tier Resistance.

**Advance Example:** You are 4" away from an enemy. You Advance 3" toward them. You draw a straight line from the center of your base in any direction. If continuing along that line would eventually result in B2B contact with the target, the Advance is valid. You move 3" along this line. This means you could move directly at the target's center, or at an angle that would clip their base if you continued far enough.

**Retreat Example:** You are B2B with an enemy. You Retreat 3" away from them. You draw a straight line from the center of your base away from the nearest point of the enemy's base, and move 3" along that line.

**Reposition Example:** A Tier 2, Size 1 character uses Reposition (2" base distance) on a Tier 3, Size 2 enemy. The target is 1 size larger (-1") and 1 Tier higher (-1"), reducing the distance to 0". The Reposition fails and the target does not move.

#### Attack Terms
- **Atk**: Perform a Draw vs a target's Def
- **+X Res**: Add this value to the Draw
- **Max Dmg**: Cap on dmg this atk can deal. Damage is calculated as (Atk Result - Def), then capped at Max Dmg.
- **Hit**: Atk result exceeds target's Def
- **Miss**: Atk result does not exceed target's Def

**Example:** An Atk with +2 Res and Max Dmg 3 is made against a target with Def 8. The attacker Draws 2 cards totaling 9, adds +2 Res for a result of 11. Damage would be (11 - 8) = 3, which does not exceed Max Dmg 3, so the target suffers 3 dmg.

#### Targeting Terms

**Target Types** (used in Target line to describe what can be selected):
- **Character**: A player character or enemy combatant
- **Terrain**: An environmental object or structure
- **Self**: The character using the action
- **An ally** / **allies**: Friendly character(s)
- **An enemy** / **enemies**: Hostile character(s)
- **A character** / **characters**: Any character, friend or foe

**Target Quantities** (used in Target line to specify how many):
- **An [target type]**: A single valid target
- **Up to X [target type]**: Choose between 1 and the specified number of valid targets
- **All [target type]**: Every valid target in range
- **[Target type] or [target type]**: Choose one of the listed types
- **[Target type] and [target type]**: Must target both types

**Target References** (used in Effect text after selection):
- **The target**: The character or object selected in the Target line (singular)
- **Each [target type]**: Refers to all selected targets individually (plural)

**Measurement**:
- **Range X**: Measure from base to target's base (or nearest point for terrain)
- **Range 0**: Target must be B2B
- **Within X"**: Any point within the specified distance
- **LoS**: Unobstructed straight line from base to target

#### Condition Terms
- **+X [Condition]**: Add the specified number of condition stacks to the target. (e.g., "+2 Impaired"). Unless otherwise specified, conditions are always applied to the target of the action.
- **-X [Condition]**: Reduce condition stacks by the specified amount. (e.g., "-2 Impaired"). Unless otherwise specified, conditions are removed from the target of the action.

#### Timing Terms
- **Start of turn**: Before any actions are taken
- **End of turn**: After all actions are resolved
- **When [trigger]**: Immediately upon the specified event
- **Before [event]**: Prior to the specified event resolving
- **After [event]**: Once the specified event is complete
- **Sustain**: Effect persists until the start of your next turn

#### Resource Terms
- **Spend**: Pay the cost (Tokens, Essence, etc.)
- **Gain**: Add to the current total or return spent resources to the available pool
- **Allocate**: Assign Tokens to an action (remains committed)

#### Assistance Terms
- **Assistance**: Allies can help with certain actions. See Resolution Mechanic for Assistance rules.
- **Allows Assistance**: This action can benefit from Assistance

#### Measurement Terms
- **Inches (")**: Standard distance measurement
- **Range 0**: Target must be B2B (base-to-base, models touching). Use Range 0 in action templates for actions that can be improved to have greater range during character growth.
- **B2B**: Base-to-base, models are touching. Use B2B in effect descriptions and for actions that must always remain at base contact (cannot be improved to have greater range).
- **Engaged**: B2B with an enemy
- **vs**: Against or versus (used in comparisons & opposed checks)

### Writing Rules for Action Effects

**Core Principle**: Clarity first, conciseness second. Write as briefly as possible while maintaining perfect understanding. Eliminate unnecessary words.

**Use Present Tense**: "The target suffers 3 dmg" not "will suffer"

**Active Voice**: "Gain 1 Essence" not "1 Essence is gained"

**Pronoun Convention**:
- **Self-actions**: Use implicit subject (no pronoun)
  - Good: "Move up to 6""
  - Good: "Gain 1 Essence"
  - Bad: "You move up to 6""
  - Bad: "The acting character moves up to 6""
- **Other characters**: Always use explicit labels
  - "The target" for the character being affected
  - "An ally" / "allies" for friendlies
  - "An enemy" / "enemies" for hostiles
  - "A character" / "characters" for any character

**Use Abbreviations**: Use standard abbreviations for frequently used terms
- "Atk" for Attack, "Def" for Defense, "Dmg" for Damage
- "Draw X" instead of "Draw X cards"
- "&" instead of "and"
- "vs" instead of "against"
- "B2B" instead of "base-to-base"

**Specific Numbers**: Always use exact values, never ranges in the effect text

**Order of Operations**: Write effects in the order they resolve
- Movement happens first
- Then attacks/draws
- Then apply conditions
- Then secondary effects

**One Effect Per Sentence**: Don't combine multiple game effects in a single sentence unless using "&" to link effects on the same target(s)

**Explicit Conditionals**: Use "If X, then Y" structure or shorthand "If X > Y"
- Good: "If the target moved this turn, apply 2 Exposed"
- Good: "If Advance > 3", characters B2B: 1 dmg & Push 3""
- Bad: "Apply Exposed to targets that moved"

**Colon for Multiple Effects**: When applying multiple effects to a group, use colon notation
- Good: "characters B2B: 1 dmg & Push 3""
- Good: "the target: 2 dmg & Apply 1 Exposed"
- Bad: "characters B2B suffer 1 dmg and are pushed 3""

**Use Keywords in Effect Text**: Use capitalized keywords (Push, Pull, Reposition) not passive forms. For conditions, use +/- notation.
- Good: "Push 3"" (uses keyword)
- Good: "+2 Exposed" (uses notation)
- Bad: "pushed 3"" (passive, not keyword)
- Bad: "Apply 2 Exposed" (too long)

**Omit Unnecessary Verbs**: When context is clear from colon notation, omit verbs like "suffer", "take", "are"
- Good: "1 dmg" (in context: "the target: 1 dmg")
- Acceptable: "suffer 1 dmg" (when not using colon notation)
- Bad: "take 1 dmg" (non-standard verb)

**State Restrictions Clearly**: 
- Good: "Cannot use if Engaged"
- Bad: "Use when not in melee"
- Special line: Drop "Can only be used" → just state the condition
  - Good: "Only when targeted by an Atk"
  - Bad: "Can only be used when targeted by an Atk"

**Capitalize Game Terms**: All keywords & conditions are capitalized for recognition

---

## Universal Tier 1 Actions

**Attack (1 Token) [Active]**
Range: 0
Target: An enemy
Effect: Atk +0 Res. Max Dmg 2.

---

**Defend (1 Token) [Reaction]**
Range: Self
Target: Self
Effect: Def + Draw 1 vs one Atk.
Special: Only when targeted by an Atk.

---

**Move (1 Token) [Active]**
Range: Self
Target: Self
Effect: Move up to 3".

---

**Run (2 Tokens) [Active]**
Range: Self
Target: Self
Effect: Move up to 7".

---

**Reposition (1 Token) [Active]**
Range: 0
Target: A character or terrain
Effect: Reposition the target up to 2".
Special: Allows Assistance.

---

**Expose (1 Token) [Active]**
Range: 6"
Target: An enemy
Effect: +1 Exposed.

---

**Impair (1 Token) [Active]**
Range: 6"
Target: An enemy
Effect: +1 Impaired.

---

**Hinder (1 Token) [Active]**
Range: 6"
Target: An enemy
Effect: +1 Hindered.

---

**Catch Breath (1 Token) [Active]**
Range: Self
Target: Self
Effect: -1 of any condition.

---

**Center (1 Token) [Active]**
Range: Self
Target: Self
Effect: Gain 1 Essence.
Special: Once per turn.

---

**Interact (1 Token) [Active]**
Range: 1"
Target: An object or terrain
Effect: Use an item or interact with the environment. Make a Draw if uncertain.

---

**Help (1 Token) [Reaction]**
Range: Varies
Target: An ally
Effect: Provide Assistance to the target's action.
Special: Range determined by GM based on the action being assisted.

---

## Action Construction Guidelines

When creating new character-specific actions, follow these principles:

### Complexity Budget
- **Tier 1-2**: 1-2 distinct effects per action
- **Tier 3-4**: 2-3 distinct effects per action
- **Tier 5-6**: 3-4 distinct effects per action

### Scaling Actions
When an action has multiple power levels based on Token investment, create separate actions with distinct names rather than variable costs.

**Good:**
```
Move (1 Token) [Active]
Effect: Move up to 3".

Run (2 Tokens) [Active]
Effect: Move up to 7".
```

**Avoid:**
```
Move (1 or 2 Tokens) [Active]
Effect: Move up to 3" if spending 1 Token, or up to 7" if spending 2 Tokens.
```

For truly variable scaling (spend any number of tokens), use this format:
```
ACTION NAME (1+ Tokens, X Essence) [Active]
Range: X
Target: Y
Effect: [Base effect]. For each additional Token spent beyond the first, [scaling effect].
Special: Max X Tokens can be spent on this action.
```

### Sustained Actions
For actions with ongoing effects:

```
ACTION NAME (X Tokens, Y Essence) [Sustained]
Range: Z
Target: W
Effect: [Initial effect]. This effect persists until next turn.
Upkeep: Choose one:
- Allocate: The Token used for this action does not Recover. Pay half the Essence cost (rounded down) at start of turn.
- Drain: Pay the full Essence cost at start of turn.
Special: May end this effect at any time.
```

### Reaction Triggers
Always specify the exact trigger condition:

**Clear Triggers**:
- "When an ally within Range 6" is targeted by an Atk"
- "When an enemy moves within Range 3""
- "When suffering dmg"
- "At start of turn"

**Avoid Vague Triggers**:
- "When needed"
- "In response to danger"
- "If appropriate"

