# Magic System

## The Soul's Law: Path & Fragments

Characters are defined not by static classes, but by a **Path**—a personal law imposed upon the universe—and **Fragments**, the fundamental building blocks of that law.

### Fragments

Fragments are individual units of insight (e.g., *Fire's Heat*, *Axe Blade Sharpness*, *Velocity*, *Gravity*).

*   **Tier Limit**: A Fragment's Tier cannot exceed the Character's Tier.
*   **Upgrading**: Merge two Fragments of the same Tier to create one Fragment of the next Tier.
    *   *Example: Fragment of Sharpness [T1] + Fragment of Strength [T1] = Fragment of the Axe [T2].*
*   **Usage**: Fragments must be used in actions to gain the familiarity required for Integration.

### Integration

Fragments exist as "loose" insights until they are **Integrated** into the Path.

*   **Requirement**: The Fragment must be upgraded to the Character's current Tier.
*   **Process**: Once eligible, the Fragment merges into the Path, becoming a permanent part of the soul.
*   **Benefit**: Integration improves efficiency.
    *   **Standard Bonus**: Using the Path in an action reduces the Essence cost by **1**.
    *   **Pure Path Bonus**: If an action *only* utilizes the Path (no loose Fragments), reduce the Essence cost by **2** (Minimum cost: 1).

**Example:** Kira is Tier 2 with Fragment of Fire [T1] and Fragment of Wind [T1]. She merges them to create Fragment of Scorching Gale [T2]. Since this Fragment is now equal to her Character Tier, she can Integrate it into her Path. Once Integrated, any action using her Path reduces Essence cost by 1. If an action uses ONLY her Path (no loose Fragments), the cost is reduced by 2 (minimum 1).

### The Path Statement

At each Tier, the character must define a **Path Statement**—the narrative "Dao" of their existence.

*   **Tier 1**: Unformed.
*   **Tier 2**: The Statement is born. It is usually broad (e.g., *"The unseen wind that cuts"*), reflecting the initial Fragments (e.g., Shadow, Wind, Sharpness).
*   **Tier 3+**: The Statement evolves to be more specific and potent (e.g., *"The Hidden Gale that Shreds"* → *"The Unforeseen Diamond Maelstrom"* → *"Sunder"*).
*   **Consistency**: While wording changes, the Statement must remain thematically consistent with the Fragments that comprise it.

**Tier Advancement**: When you advance to a new Tier, you must revise your Path Statement. This is mandatory—your soul is changing to incorporate the Fragments and your Identity. As your Path Statement evolves and more Fragments are Integrated, you gain greater Essence cost reductions on actions that use your Path.

---

## Action Construction (Essence Cost)

Actions are constructed by summing the **Essence Cost** of their components. This calculation is typically done between sessions.

### Component Costs

**Targeting Components**
*   **Melee**: 0 Essence.
*   **Range**: +1 Essence per inch.
*   **Cone/Line Template**: Cost based on length (Max length: 10).
*   **Circle Template**: Cost based on range to epicenter + diameter.

**Magnitude Components**
*   **Power**: Determines damage potential.
*   **Resolution**: Attack resolution is `Bonus vs. Defense`. Excess is damage, capped by Tier.

**Effect Components**
*   **Condition Stacks**: Cost varies by condition type. Max total stacks you can apply to a target is limited by your Tier (see Conditions.md).
    *   *Note: You may use multiple lower-tier Fragments to build up to your current Tier limit, allowing you to train those Fragments for future Integration.*
*   **Forced Movement**: Cost reduced by target size.

### Calculating Final Cost

1.  **Base Cost**: Sum all components.
2.  **Tier Cap**: Total complexity (effects/magnitude) cannot exceed the Character's Tier limit.
3.  **Integration Discount**: Apply -1 Essence (or -2 for Pure Path).

---

## Essence & Action Economy

### The Essence Threshold

*   **Tier 1–2 (Physical)**: Actions cost **Action Tokens**. Supernatural actions require **Essence**.
*   **Tier 3+ (Magical)**: Body and soul merge. All actions cost **Action Tokens + Essence**.

### Sustaining Effects (Upkeep)

Active actions (Auras, Shrouds, Zones) require upkeep. Choose one method per action:

*   **Option A: Focus & Drain**
    *   **Token Lock**: The Action Token used to activate the effect does not refresh.
    *   **Half Drain**: Pay **half** the original Essence cost (rounded down) at the start of each turn.

*   **Option B: Pure Drain**
    *   **Full Drain**: Pay the **full** original Essence cost at the start of each turn.

---

## Corruption

For Corruption rules and effects, see `stats.md`.

---

## Resolution & The Path Suit

Upon reaching **Tier 2**, choose a Path Suit (♠, ♥, ♦, ♣).

When you draw your Path Suit during a resolution, gain 1 Essence (see `stats.md` for details).

---

## Open Questions

- **Cone/Line Template Max Length** (referenced in Action Construction, Targeting Components): Should max length be Tier-based rather than fixed at 10"?

- **Power Component Costs** (referenced in Action Construction, Magnitude Components): Need to determine Essence costs for Power component that determines damage potential.
