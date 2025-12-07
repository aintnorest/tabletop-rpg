# Resolution Mechanic

The game uses a card-based resolution mechanic instead of dice to provide a unique probability curve and allow for more strategic, less luck-based play.

## Custom Card Deck Composition

The game uses a custom 18-card deck:

- **4 Aces** - One of each suit (value: 1)
- **4 Twos** - One of each suit (value: 2)
- **4 Threes** - One of each suit (value: 3)
- **4 Jacks** - One of each suit (value: 0)
- **1 Red Joker** - (value: 0, Wild Suit)
- **1 Black Joker** - (value: 3, No Suit)

**Total**: 18 cards

## Card Values

| Card | Value | Suit | Notes |
|------|-------|------|-------|
| Ace | 1 | ♠ ♥ ♦ ♣ | Standard suit |
| Two | 2 | ♠ ♥ ♦ ♣ | Standard suit |
| Three | 3 | ♠ ♥ ♦ ♣ | Standard suit |
| Jack | 0 | ♠ ♥ ♦ ♣ | Standard suit |
| Red Joker | 0 | Wild | Can count as any suit for ability trigger purposes (Wild Suit) |
| Black Joker | 3 | None | Does not count as any suit and cannot trigger suit-based abilities (No Suit) |

## Deck Management

### Discard Pile Rules

- After resolution, drawn cards are placed face down in the discard pile
- Discard pile contents are **not public knowledge**
- Players cannot look at the discard pile
- The discard pile order is maintained (cards are not shuffled when discarded)

### Reshuffling

- When the deck has **one card left**, immediately shuffle the discard pile to form a new deck
- The remaining card is shuffled into the newly shuffled deck
- This ensures the deck is never completely empty

### Deck State

- The deck starts shuffled
- The current deck size is public knowledge (players can count remaining cards)

## Probability Distribution

With 18 cards total:

| Value | Count | Probability |
|-------|-------|-------------|
| 0 | 5 | 27.8% (4 Jacks + 1 Red Joker) |
| 1 | 4 | 22.2% (4 Aces) |
| 2 | 4 | 22.2% (4 Twos) |
| 3 | 5 | 27.8% (4 Threes + 1 Black Joker) |

**Average value**: ~1.44

**Note**: This creates a different probability curve than traditional dice, with more weight toward the extremes (0 and 3) and less in the middle.

## Drawing Cards

- **No hand system**: Cards are drawn fresh from the top of the deck for each check
- **On Turn**: Characters draw **2 cards** when performing actions on their turn
- **Off Turn**: Characters draw **1 card** when performing actions outside their turn (reactions, opportunity attacks, etc.)

## Suit-Based Ability Triggers

Certain abilities can trigger extra effects based on the suits of cards drawn:

- **Single Spade**: A single spade (♠) is drawn out of the one or two cards
- **Single Spade or Heart**: A single spade (♠) or heart (♥) is drawn out of the one or two cards
- **Both Spades**: Both cards drawn are spades (♠)
- **Spade and Heart**: One card is a spade (♠) and one card is a heart (♥)

*Note: See Card Values table for suit matching rules (Red Joker = Wild Suit, Black Joker = No Suit)*

## Modifiers and Deck Manipulation

### Character Attributes/Skills

- Character attributes/skills (or merged system) will add to card values
- These modifiers are applied after drawing cards

### Deck Manipulation

- Abilities may allow manipulation of the deck and/or discard pile
- Specific mechanics for deck manipulation will be defined in ability descriptions

## Version History

- **v0.2** - Added drawing rules, suit-based triggers, clarified suit mechanics, and modifier system
- **v0.1** - Initial resolution mechanic documented

