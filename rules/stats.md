# Core Stats

There are four stats that track a character's physical and spiritual state. These values are primarily determined by **Tier**, but there are rare methods to permanently increase them beyond these baselines.

## Vitality

Vitality represents physical health and the will to survive. Combat is dangerous; at Tier 1, characters are vulnerable, and fighting an enemy of a higher Tier is a deadly challenge.

### Calculation

**Base Vitality**: 10  
**Tier Bonus**: +4 per Tier (including Tier 1)

### Damage & Recovery

**Taking Damage**: Damage is calculated as `Attack Result - Defense`. This value is subtracted from Vitality.

**Healing**: Vitality is hard to raise above the cap, but there are many ways to recover lost Vitality. However, many of the fastest methods (potent alchemical pills, dark rituals) cause Corruption.

**0 Vitality**: The character is **Downed**. They cannot take actions and must roll on the **Death & Consequences Table** (TODO: Create Table).

*Design Intent: This table will include outcomes ranging from Death to permanent penalties, deck augmentation (scars/trauma cards), and Corruption damage. Recovery from these states varies in difficulty.*

## Defense

Defense represents a character's ability to avoid attacks (dodge/parry) and their resilience (soak). It serves as the **Target Number (TN)** for enemy attacks. Because damage is based on how much an attack exceeds Defense, a higher Defense directly reduces damage taken.

### Calculation

Defense follows the standard Difficulty Curve (TN) for each Tier, plus bonuses from **Equipment** and other sources.

**Base Defense**: 5  
**Tier 2**: +2  
**Tier 3**: +4  
**Tier 4**: +6  
**Tier 5**: +4  
**Tier 6**: +5

**Total Defense**: Sum all sources (Base + Tier + Equipment + Buffs). Round down to the nearest whole number.

## Essence

Essence is the spiritual fuel for supernatural abilities.

### Calculation

**Base Essence**: 5  
**Tier 2**: +5  
**Tier 3**: +15  
**Tier 4**: +20  
**Tier 5**: +25  
**Tier 6**: +30

*Note: This may not be enough but we'll check again once we have other numbers.*

### Recovery

**Path Suit**: Gain 1 Essence when you draw a card matching your Path Suit during resolution. This only applies once you have chosen a Path Suit (Tier 2+, see *Magic System*).

**Environment**: Slow recovery dependent on the environment (e.g., resting in a place rich with compatible essence).

**Shortcuts**: Pills, potions, and other rapid healing methods can restore Essence immediately but generate Corruption.

*Note: Essence is not fully recovered automatically between sessions.*

## Corruption

Corruption (0–100) measures the stain of foreign laws and the fracturing of the self. It is a persistent threat that is easy to gain but extremely difficult to remove.

### Gaining Corruption

- Using forbidden magic or artifacts
- Exposure to strong concepts and laws that don't agree with your own
- Specific enemy attacks
- **Shortcuts**: Pills, potions, and shortcuts to healing or pushing up in tiers quickly can add corruption

### Effects of Corruption

As Corruption rises, it interferes with the character's connection to their Path.

**Path Rejection**: Increase Essence cost of all actions by `floor(Corruption / 10)`.

**Identity Inversion**: If `Corruption > (Tier × 10)`, one Identity (chosen by GM/Table) is **Inverted**. The Identity is reworded to reflect a corrupted, darker version (e.g., *Disgraced Constable* → *The Lawless Executioner*). Inverted Identities lose "Automatic Success" capabilities (see *Resolution Mechanic*). All tasks using this Identity require a Resolution draw.

**Core Damage**: If `Corruption > (Tier × 10)`, take damage equal to the overflow whenever you spend an Action Token.

### Reducing Corruption

Corruption cannot be healed by normal means (rest, medicine, or standard magic). It requires:
- Rare, high-tier rituals
- Significant narrative sacrifices (giving up a Fragment, losing memories, etc.)

## Size

### Base Stats Table

| Size | Min Base | Max Base | Examples                   |
|------|----------|----------|----------------------------|
| 0.5  | 12       | 24       | Dog, mailbox, crate        |
| 1    | 25       | 39       | Human, humanoid            |
| 2    | 40       | 59       | Large humanoid, motorcycle |
| 3    | 60       | 89       | Car, large dumpster        |
| 4    | 90       | 129      | Dump truck, small building |
| 5    | 130      | 170      | Medium building            |
| 6    | 171      | 250      | Large building             |

---

## Open Questions

- **Size** I believe somewhere i say that players can only be up to size 3 but that its up to the GM. Should consolidate anything i have about size to here.
I also want to make size matter but not sure how I should go about that in this game.

- **Death & Consequences Table** (referenced in Vitality section, line 22): Need to create table with outcomes ranging from Death to permanent penalties, deck augmentation (scars/trauma cards), and Corruption damage.

- **Corruption as Viable Path**: In cultivation fiction, "demonic cultivation" or "forbidden techniques" are often viable (if risky) paths to power. The current Corruption system makes shortcuts feel like traps rather than meaningful choices. Should Corruption provide mechanical benefits to balance the penalties (e.g., Corrupted actions deal bonus damage, or access to forbidden techniques)? Should there be clearer thresholds where Corruption becomes dangerous vs. manageable?
