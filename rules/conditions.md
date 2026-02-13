# Conditions

Conditions are negative effects that reduce combat effectiveness. Each condition has stacks (the number) that reduce by 1 after being used once.

## Condition Stack Limits

The maximum number of condition stacks a character can have is based on **their Tier**.

| Character Tier | Max Stacks Per Condition Type |
|----------------|-------------------------------|
| 1              | 5                             |
| 2              | 7                             |
| 3              | 10                            |
| 4              | 12                            |
| 5              | 15                            |
| 6              | 17                            |

**Stack Limit Rules:**
- Each condition type (Exposed, Impaired, Hindered, Afflicted) has its own separate limit
- When a character would gain a condition stack that exceeds their limit for that condition type, they suffer 1 dmg instead and do not gain the stack
- Higher Tier characters can withstand more condition stacks before taking overflow damage

**Example:** A Tier 2 character has Exposed 7 (at their limit). An enemy action would apply Exposed 2. The character suffers 2 dmg instead and remains at Exposed 7.

**Example - Multiple Conditions:** A Tier 1 character has Exposed 5, Hindered 3, and Impaired 2. They are at their limit for Exposed only. An action applies Exposed 1 & Hindered 2. The character suffers 1 dmg from the Exposed overflow, gains Hindered 2 (now at Hindered 5), and remains at Exposed 5.

## Condition Types

| Condition       | Effect                  | Reduces By 1 After |
|-----------------|-------------------------|--------------------|
| **Exposed X**   | -X to defense           | Being attacked     |
| **Impaired X**  | -X to resolve draw      | Making an attack   |
| **Hindered X**  | -X" to movement         | Attempting to move |
| **Afflicted X** | 1 damage at end of turn | Taking the damage  |
