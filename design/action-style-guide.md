# Action Style Guide

This document defines how to format and write actions. It supports consistency for anyone creating character-specific actions or reviewing action text. See `rules/action-system.md` for core mechanics and universal actions.

## Action Template

All actions follow this standardized format:

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

**Target**: What the action can affect. Be specific: An enemy, An ally, A character, Self, Up to X characters, All characters within X", A terrain, A character or terrain, An enemy & a terrain. Include size/tier restrictions if applicable. Effect text uses "the target" to refer to the selected character or object.

**Effect**: The mechanical outcome, written in order of resolution.
- Use numbered steps for complex sequences
- Each sentence describes one discrete game effect
- Use implicit subject for self-actions (no pronoun needed)
- Use explicit labels for other characters: "the target", "an ally", "an enemy", etc.

**Special**: Conditional triggers, restrictions, or additional rules.
- Use "If/Then" structure for clarity
- State limitations explicitly

## Writing Rules for Action Effects

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

**Specific Numbers**: Always use exact values, never ranges in the effect text.

**Order of Operations**: Write effects in the order they resolve
- Movement happens first
- Then attacks/draws
- Then apply conditions
- Then secondary effects

**One Effect Per Sentence**: Don't combine multiple game effects in a single sentence unless using "&" to link effects on the same target(s).

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
- Good: "-1 Impaired" (means remove 1 stack)
- Good: "+1 Condition" / "-1 Condition" (active character chooses type)
- Bad: "pushed 3"" (passive, not keyword)
- Bad: "Apply 2 Exposed" (too long)

**Omit Unnecessary Verbs**: When context is clear from colon notation, omit verbs like "suffer", "take", "are"
- Good: "1 dmg" (in context: "the target: 1 dmg")
- Acceptable: "suffer 1 dmg" (when not using colon notation)
- Bad: "take 1 dmg" (non-standard verb)

**Implicit Choice**: When options are presented with "OR", the word "Choose" is redundant and should be omitted.
- Good: "Hit: Push 1" OR +1 Condition"
- Bad: "Hit: Choose Push 1" OR +1 of any Condition"
- Good: "Cannot use if Engaged"
- Bad: "Use when not in melee"
- Special line: Drop "Can only be used" → just state the condition
  - Good: "Only when targeted by an Atk"
  - Bad: "Can only be used when targeted by an Atk"

**Capitalize Game Terms**: All keywords and conditions are capitalized for recognition. Capitalize "Condition" when referring to the mechanic itself.
- Good: "+1 Condition"
- Good: "Choose a Condition type"

## Action Construction Guidelines

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
Always specify the exact trigger condition.

**Clear Triggers**:
- "When an ally within Range 6" is targeted by an Atk"
- "When an enemy moves within Range 3""
- "When suffering dmg"
- "At start of turn"

**Avoid Vague Triggers**:
- "When needed"
- "In response to danger"
- "If appropriate"
