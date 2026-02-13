# Rules Editor Reference

This document provides extended examples, deep dives, and additional patterns for complex editing scenarios. Consult when facing unusual situations or needing detailed guidance.

## Rules Folder Structure & Scope

Use this to decide where content belongs. Define each concept once in its primary file; cross-reference elsewhere.

| File                       | Scope                                                                                                                                  | Cross-References To                                                      |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| **action-system.md**       | Action tokens, universal actions, action economy, token recovery, reading action format                                                | Positioning (movement terms), Resolution Mechanic (Atk/Def), Conditions  |
| **archetype.md**           | Archetype definitions, archetype-specific actions, party roles                                                                         | Action system (format), Conditions, Positioning                          |
| **conditions.md**          | Condition types (Exposed, Impaired, Hindered, Afflicted), stack limits, application notation                                           | Stats (tier for limits), Action system                                   |
| **equipment.md**           | Gear, weapons, armor, equipment rules                                                                                                  | Stats (Def, etc.)                                                        |
| **identity.md**            | Character identity system                                                                                                              | Resolution Mechanic (competence)                                         |
| **initiative.md**          | Turn order, round structure                                                                                                            | Action system                                                            |
| **magic-system.md**        | Path, Fragments, Integration, Essence costs, sustaining, Path Suit                                                                     | Stats (Essence, Corruption), Resolution Mechanic (Path Suit), Conditions |
| **positioning.md**         | Movement (Move, Advance, Retreat, Place), terrain, forced movement (Push, Pull, Reposition), Size & Tier resistance, measurement terms | Action system (movement in effects)                                      |
| **resolution-mechanic.md** | When to resolve, competence matrix, deck, combat resolution (Atk/Def), non-combat resolution, assistance                               | Stats, Conditions, Magic System (Path Suit)                              |
| **stats.md**               | Vitality, Defense, Essence, Corruption, Size                                                                                           | Conditions, Resolution Mechanic, Magic System                            |

## Extended Ambiguity Examples

### Example 1: Vague Targeting

**Problematic text**:
> "Choose enemies near you and deal damage to them."

**Problems**:
- "Near" is undefined (Range 3"? 6"? Line of sight?)
- "Enemies" could mean all or some
- "Damage" amount unspecified
- Order of operations unclear

**Fixed version**:
```
Range: 6"
Target: Up to 3 enemies
Effect: Each target: 2 dmg.
```

### Example 2: Unclear Timing

**Problematic text**:
> "When you move and attack, the target is weakened."

**Problems**:
- Must you both move AND attack, or is it either/or?
- Does order matter (move then attack, or attack then move)?
- When is "weakened" applied (before attack resolves, or after)?
- What is "weakened" (is it a condition, temporary effect)?

**Fixed version**:
```
Effect: Move up to 3". Make an Atk vs the target. After resolving the Atk, the target: +1 Exposed.
```

### Example 3: Resource Ambiguity

**Problematic text**:
> "Spend tokens to increase the effect."

**Problems**:
- How many tokens?
- What's the base effect vs enhanced effect?
- Is there a maximum?
- What if you don't have tokens?

**Fixed version**:
```
Cost: 1+ Tokens
Effect: The target: 1 dmg. For each additional Token spent beyond the first, the target: +1 dmg.
Special: Max 3 Tokens can be spent on this action.
```

## Terminology Consistency Deep Dive

### Building a Terminology Map

When editing across multiple files, create a mental or written map of terms:

| Concept | Approved Term | Rejected Synonyms | Files Using |
|---------|---------------|-------------------|-------------|
| Forced movement away | Push | shove, knock back, repel | positioning.md, action-system.md |
| Forced movement toward | Pull | drag, yank, draw in | positioning.md |
| Precise forced movement | Reposition | move, place, relocate | positioning.md |
| Close combat range | Range 0, B2B | melee, adjacent, touching | combat.md, positioning.md |

### Cross-File Terminology Audit

**Process**:
1. Identify a potentially inconsistent term (e.g., "move" vs "travel" vs "relocate")
2. Search all rules/ files for each variant
3. Determine which term is most prevalent or clearest
4. Propose standardization to that term
5. Check if term is defined in a glossary or core file
6. Update all files to use the standard term

**Example audit findings**:
```
Term: Movement-related actions
- "move": 47 instances across 6 files ✓ Standard
- "travel": 3 instances in combat.md → Should change to "move"
- "relocate": 1 instance in positioning.md → Should change to "move"
```

## DRY Violation Patterns & Fixes

### Pattern 1: Scattered Definitions

**Problem**: The same rule defined in multiple places with slight variations

**Example**:
- `rules/combat.md`: "Engaged: When B2B with an enemy"
- `rules/movement.md`: "Characters are Engaged if at Range 0 to an enemy"
- `rules/action-system.md`: "Engaged means touching bases with an enemy"

**Solution**:
1. Choose the most comprehensive, clear definition
2. Create or update `rules/conditions.md` with canonical definition:
   ```markdown
   ## Engaged
   At Range 0 to an enemy. Characters can Disengage to end this condition.
   ```
3. Replace all other instances with cross-references:
   ```markdown
   Characters at Range 0 to an enemy are Engaged (see Conditions).
   ```

### Pattern 2: Copy-Paste Mechanics

**Problem**: The same mechanic copy-pasted into multiple actions or rules

**Example**: 20 actions that each explain how Push works

**Solution**:
1. Define Push once in `rules/positioning.md`:
   ```markdown
   ## Push
   Forced movement directly away from the source. The target moves X" in a straight line away from the character causing the Push.
   ```
2. In actions, simply use the keyword:
   ```markdown
   Effect: Push the target 3".
   ```

### Pattern 3: Partial Repetition

**Problem**: Core rule stated in one place, but pieces of it scattered elsewhere

**Example**:
- `rules/action-system.md`: "Actions cost Tokens shown in parentheses"
- `rules/reactions.md`: "Reactions also cost Tokens"
- `rules/essence.md`: "Some actions cost Essence too"

**Solution**: Consolidate into one complete statement in the most logical file:
```markdown
## Action Costs (in action-system.md)
All actions cost Action Tokens, shown in parentheses after the action name. Some actions also cost Essence, shown after the Token cost separated by a comma.

Example: (2 Tokens, 3 Essence)
```

Then reference from other files:
```markdown
## Reactions (in reactions.md)
Reactions cost Action Tokens like all actions (see Action Costs in action-system.md).
```

## Genre Tone Examples

See `design/core-concepts.md` for primary genre definitions.

### Tone-Appropriate Rule Text

**Good examples**:
> "At Tier 3, breakthrough into the Spirit realm grants +3 Essence capacity."

> "Consuming cultivation resources increases Essence Regeneration."

**Tone violations**:
> "This creates a balanced risk-reward scenario." (meta-commentary)

> "Unlike D&D, our system uses tokens." (comparison to other games)

> "We thought it would be cool if..." (design justification)

## Action Conciseness Workshop

### Maximizing Information Density

**Verbose (42 words)**:
```
Effect: The acting character can move up to 6 inches. After the move is completed, the acting character makes an attack against a target. If the attack is successful, the target suffers 3 damage and is pushed 2 inches away.
```

**Step 1 - Remove acting character references (32 words)**:
```
Effect: Move up to 6 inches. After the move is completed, make an attack against a target. If the attack is successful, the target suffers 3 damage and is pushed 2 inches away.
```

**Step 2 - Use abbreviations & symbols (24 words)**:
```
Effect: Move up to 6". After the move is completed, make an Atk vs a target. If successful, the target suffers 3 dmg & is pushed 2" away.
```

**Step 3 - Use keywords, remove unnecessary words (17 words)**:
```
Effect: Move up to 6". Make an Atk vs a target: 3 dmg & Push 2".
```

**Step 4 - Implicit successful attack (13 words)**:
```
Effect: Move up to 6". Atk vs a target: 3 dmg & Push 2".
```

**Final (13 words)**: 68% reduction from original while maintaining perfect clarity

### Common Verbosity Traps

**Trap 1: Explaining obvious mechanics**
- ❌ "Draw 2 cards from your deck into your hand"
- ✓ "Draw 2"

**Trap 2: Redundant subjects**
- ❌ "The target suffers 3 dmg and the target is pushed"
- ✓ "The target: 3 dmg & Push 3""

**Trap 3: Unnecessary qualifiers**
- ❌ "You can move up to 6" or less"
- ✓ "Move up to 6""

**Trap 4: Passive voice padding**
- ❌ "3 dmg is suffered by the target"
- ✓ "The target: 3 dmg" or "3 dmg" (in context)

**Trap 5: Over-explaining conditionals**
- ❌ "If the target has moved during this turn, then apply 2 Exposed to them"
- ✓ "If the target moved this turn, +2 Exposed"

## Complex Edge Cases

### Simultaneous Effect Resolution

**Scenario**: Two characters both have reactions that trigger "when an enemy moves within Range 3"". The same enemy moves, triggering both.

**Ambiguity**: Which resolves first? Can the first reaction prevent the second from triggering?

**Solution approaches**:
1. **Define priority rules** in a core file (e.g., "Reactions resolve in Initiative order")
2. **State explicitly** if some reactions can interrupt others
3. **Declare simultaneous** if order doesn't matter ("All triggered reactions resolve simultaneously")

### Nested Conditionals

**Problematic text**:
> "If the target is Engaged, and if you have 3+ Tokens, and if the target moved this turn, deal extra damage."

**Problems**:
- Hard to parse
- Unclear what "extra" means
- Three conditions make for confusing gameplay

**Fixed approach 1 - Simplify**:
```
Special: If the target is Engaged & moved this turn: +2 dmg.
```

**Fixed approach 2 - Break into cases**:
```
Special: 
- If the target is Engaged: +1 dmg
- If the target moved this turn: +1 dmg
```

### Replacement Effects

**Scenario**: One ability says "Draw 2", another says "When you would draw, gain 1 Essence instead."

**Ambiguity**: Does the replacement happen? Do you draw 0 and gain 2 Essence, or draw 1 and gain 1 Essence?

**Solution**: Define replacement effect rules clearly:
```markdown
## Replacement Effects
When an effect would occur, but another effect replaces it:
1. The replacement happens instead of the original effect
2. The original effect does not occur at all
3. If multiple replacements apply, the affected player chooses which applies

Example: "Draw 2" with "When you would draw, gain 1 Essence instead" → Gain 2 Essence, draw 0 cards.
```

### Continuous vs Triggered Effects

**Problematic text**:
> "Allies near you have +1 Defense."

**Ambiguity**:
- Is this continuous (always on)?
- Is this a triggered effect (checks at specific timing)?
- Does "near" update as characters move?

**Fixed - Continuous**:
```
Range: 6" Aura
Effect: Allies within range have +1 Def.
Special: This effect updates continuously as allies enter or leave the aura.
```

**Fixed - Triggered**:
```
Trigger: When an ally within Range 6" is targeted by an Atk
Effect: That ally gains +1 Def until the Atk resolves.
```

## File Organization Strategies

### When to Create a New File

**Create a new file when**:
- A topic has 5+ distinct rules or mechanics
- The content is thematically separate from existing files
- Players would reasonably expect this to be its own section
- An existing file is becoming bloated (>300 lines)

**Example**: If `rules/combat.md` contains sections on attacking, defending, damage, cover, terrain, line of sight, and flanking, consider splitting:
- `rules/combat-core.md` - attacking, defending, damage
- `rules/battlefield.md` - terrain, cover, line of sight, flanking

### When to Merge Files

**Merge files when**:
- Two files together are <200 lines
- They cover closely related mechanics
- Rules in one constantly reference the other
- Players would expect them to be together

**Example**: Merge `rules/push.md` and `rules/pull.md` into `rules/positioning.md` if they're both short and conceptually part of forced movement.

### File Naming Conventions

**Good names** (clear, specific):
- `action-system.md`
- `conditions.md`
- `character-creation.md`
- `resolution-mechanic.md`

**Poor names** (vague):
- `misc.md`
- `other-rules.md`
- `stuff.md`
- `additional.md`

### Cross-Reference Syntax

**Standard format**:
```markdown
See [Topic] in filename.md

Example: See Push in positioning.md
Example: See Action Costs in action-system.md
```

**With section**:
```markdown
See [Topic] in filename.md#section

Example: See Forced Movement in positioning.md#push-pull-reposition
```

**In the same file**:
```markdown
See [Section] below
See [Section] above

Example: See Reactions below
```

## WIP Content Management

### Bottom Section Best Practices

**Good structure**:
```markdown
---

## Open Questions

### How do multiple Pushes interact?
**Context**: If two abilities both Push the same target simultaneously.
**Current ruling**: None.
**Proposed**: Add vectors, or resolve in Initiative order.
**Test priority**: High - likely to occur in play.

### What's minimum Push distance?
**Context**: Some abilities say "Push 1"" but that seems insignificant.
**Current ruling**: As written (1").
**Proposed**: Change minimum to 2"?
**Test priority**: Low - playtest first.

---

## Design Notes

- Considered making all Pushes cost Action Tokens, but decided against for balance
- Originally had Push/Pull/Reposition as separate keywords, keeping this

---

## TODO

- [ ] Add example for Push into terrain/obstacles
- [ ] Cross-reference Engaged condition from positioning.md
- [ ] Playtest Push distance scaling with Tier
- [ ] Create diagram showing Push direction relative to source
```

### What Belongs in Bottom Sections

**Open Questions**: Unresolved rules interactions, edge cases, ambiguities discovered during editing

**Design Notes**: Rationale, alternatives considered, intentional design choices (for future reference)

**TODO**: Concrete tasks with clear completion criteria

### What Doesn't Belong

❌ Complete rules text that should be in the main body
❌ Vague "maybe we should..." without context
❌ Outdated notes from months ago (clean up regularly)
❌ Design justifications that should move to design/ folder

## Quality Assurance Checklist

### Before Declaring Edit Complete

Run through this comprehensive checklist:

#### Clarity
- [ ] Every rule has one interpretation only
- [ ] All terms are defined before first use
- [ ] Edge cases are addressed or marked as open questions
- [ ] Examples (if present) are correct and helpful
- [ ] No assumptions left unstated

#### Language
- [ ] Active voice throughout
- [ ] Present tense throughout
- [ ] Imperative sentences for player actions
- [ ] Declarative sentences for game states
- [ ] Short, simple sentences
- [ ] No unnecessary words

#### Consistency
- [ ] Terminology matches other files
- [ ] Game terms capitalized correctly
- [ ] Abbreviations used correctly (in actions only)
- [ ] Cross-references are accurate
- [ ] Formatting matches other files

#### Organization
- [ ] Content is in the logical file
- [ ] No DRY violations
- [ ] Main text contains only finished/test-ready rules
- [ ] WIP content in bottom sections with context
- [ ] File serves one coherent purpose

#### Genre & Tone
- [ ] Fits cultivation/progression fantasy genre
- [ ] No meta-commentary in rules text
- [ ] No design justifications in rules text
- [ ] Clinical tone for rules, not conversational
- [ ] Actions are maximally concise

#### Actions (if applicable)
- [ ] Template format followed exactly
- [ ] Costs in parentheses
- [ ] Timing in brackets
- [ ] Implicit subject for self-actions
- [ ] Explicit labels for other characters
- [ ] Abbreviations used (Atk, Def, Dmg, B2B, &, vs)
- [ ] Keywords capitalized (Push, Pull, Reposition)
- [ ] Colon notation for multiple effects
- [ ] Triggers are specific (for reactions)

#### Technical
- [ ] Numerals for game quantities
- [ ] Ranges use " for inches
- [ ] Conditions use +/- notation
- [ ] Order of operations is clear
- [ ] Timing is explicit
- [ ] Resource costs are specific

## Common Pushback & Responses

### "This is too clinical and dry"
**Response**: Rules text must be clinical for clarity. Save engaging writing for fluff, lore, and flavor text. Players need to understand mechanics first, be entertained second. A confused player isn't having fun.

### "But players will understand from context"
**Response**: Never assume context fills gaps. Different play groups have different assumptions. What's "obvious" to the designer is often ambiguous to players. Write for the player who's reading this section in isolation.

### "This makes the file longer with examples/edge cases"
**Response**: Better a longer, complete file than a short, ambiguous one. Alternatively, move extensive examples to an appendix or separate examples file, but don't eliminate them entirely.

### "We can clarify in FAQ later"
**Response**: FAQ sections are failure points. Rules should be clear on first reading. FAQs indicate something in the main text is confusing and should be fixed at the source. Don't hide rules in FAQs.

### "This rule works fine in playtesting"
**Response**: Your playtest group has implicit shared context from discussions, questions, and designer intent. A new group reading the rules cold will not have that context. Write for strangers, not your playtest group.

### "That's a really rare edge case"
**Response**: If it can happen in play, it needs a ruling. "Rare" doesn't mean "ignorable." Address it explicitly or mark it as an open question. Don't leave rules gaps.

## Success Metrics

You've succeeded when:

1. **A stranger can play**: Someone who's never played can read the file and understand exactly what to do, without asking questions
2. **No rules arguments**: Two players can't interpret a rule differently and both claim to be correct
3. **Quick reference**: A player mid-game can find the rule they need quickly
4. **No surprises**: Edge cases that arise during play were addressed in the rules
5. **Consistent terms**: A term means the same thing every time it appears across all files
6. **Proper homes**: Every rule is in the file where players would expect to find it
7. **Actions fit**: Character sheet has space for action text
8. **Genre resonance**: Rules feel like cultivation/progression fantasy
9. **Clean main text**: WIP content isn't cluttering the rules
10. **DRY maintained**: Changing a rule requires editing exactly one place (plus cross-references)
