# Dialogue Systems for Games

## Table of Contents
1. Dialogue Tree Design
2. Hub-and-Spoke Dialogue
3. Bark Systems
4. Companion and Party Dialogue
5. Writing for Voice Acting
6. Procedural and Dynamic Text
7. Dialogue as Gameplay
8. Common Pitfalls and Solutions

---

## 1. Dialogue Tree Design

### Structural Principles

A dialogue tree is not a menu — it's a conversation. Each node should feel like a natural continuation of what came before, and every branch should lead somewhere the player *wants* to go (even if that place is uncomfortable).

**The Rule of Meaningful Difference:** If two dialogue options lead to the same response from the NPC, collapse them into one option. Players learn quickly when choice is illusory, and it erodes trust in the entire system.

**The Rule of Visible Consequence:** The player should see or feel the impact of their dialogue choice within the same conversation, within the same quest, or — for major choices — within the same act. Consequences that only appear 40 hours later feel disconnected from the choice that caused them.

**The Rule of Honest Options:** The dialogue option text must accurately represent what the character will actually say. Nothing destroys player trust faster than selecting "I'll help you" and having the character say something sarcastic or threatening. If you want to keep the player's exact words a surprise, at minimum convey the *intent* accurately.

### Node Architecture

Each dialogue node should contain:
- **Speaker tag**: Who is talking
- **Line**: The actual dialogue text
- **Direction**: Performance notes for voice actors (parenthetical emotions, physicality, subtext)
- **Camera/staging notes**: Where the camera should be, what the characters are physically doing
- **Condition gates**: What flags, stats, or states determine whether this node is available
- **Consequence flags**: What state changes when this node is reached

### Branching Depth

Keep dialogue trees no deeper than 3-4 levels for standard conversations. Beyond that, the combinatorial explosion becomes unmanageable and the player loses the thread of the conversation. For deep, important conversations, use a hub-and-spoke model instead.

---

## 2. Hub-and-Spoke Dialogue

The player sits in a conversational "hub" and selects topics to explore ("spokes"). After each spoke, they return to the hub. This model works beautifully for information-gathering, relationship-building, and any conversation where the player should control the pacing.

**Design the hub to evolve.** After the player explores a spoke, the hub text or available options should change to reflect what's been discussed. Static hubs feel mechanical; evolving hubs feel like real conversations.

**Order-dependent reveals.** Some spokes should only appear after others have been explored. This creates a sense of conversational discovery — asking about Topic A reveals that Topic C is even available.

**The exit option.** Always give the player a clear, non-punitive way to leave the conversation. Don't trap them.

---

## 3. Bark Systems

Barks are short, context-triggered voice lines that characters say during gameplay. They are the most-heard dialogue in any game and the easiest to get wrong.

### Bark Categories

- **Combat barks**: Attack calls, hit reactions, kill confirmations, low health warnings, ability usage callouts
- **Exploration barks**: Environmental observations, navigation hints, lore tidbits, reactions to discoveries
- **Idle barks**: Ambient chatter, relationship banter, world-state commentary
- **Systemic barks**: Reactions to player actions (stealing, killing non-combatants, using specific abilities)

### Writing Rules for Barks

**Brevity is survival.** Barks must be short enough that the player processes them while doing something else. 3-8 words for combat barks. 10-15 words for exploration. If a bark needs to be longer, it must justify its length by being genuinely revealing or entertaining.

**Repetition resilience.** The player will hear each bark dozens or hundreds of times. Avoid specificity that becomes absurd on repetition. "Look out!" works 200 times. "Watch out for that Draugr behind the pillar!" becomes nonsensical after the first time.

**Character voice over information.** A bark that sounds like the character is worth more than a bark that conveys tactical data. "Reloading!" is functional. "I'm gonna need a minute!" is both functional AND characterizing.

**State-aware barks.** Barks should evolve as the game state changes. The companion who cheerfully comments on the scenery in Act 1 should have different barks after the traumatic event in Act 2. This is expensive but transformative.

**Bark cooldowns and priorities.** Implement systems to prevent bark spam: minimum time between barks, priority levels (combat > exploration > idle), and never interrupt a higher-priority bark with a lower-priority one.

---

## 4. Companion and Party Dialogue

Companion dialogue is the backbone of character-driven games. The companion is the player's window into the world and the emotional anchor of the experience.

### Designing Companion Conversations

**Reactive, not robotic.** Companions should respond to what the player does, not just what the story does. Killed an innocent? The companion should react — not with a scripted cutscene, but with a bark or a conversation option that appears organically.

**Relationship as progression.** Companion trust/affection should function like a progression system: the player invests (through choices, time, gifts, dialogue) and receives (deeper conversations, personal quests, unique abilities, story-critical information).

**The Three Layers of companion dialogue:**
1. **Surface**: What they say during gameplay (barks, ambient dialogue)
2. **Campfire**: Deeper conversations initiated by the player or triggered by events
3. **Crucible**: Pivotal moments where the relationship is tested (loyalty missions, betrayal opportunities, sacrifice decisions)

### Party Banter Systems

For games with multiple companions, inter-party dialogue adds enormous life to the experience.

**Pairing chemistry.** Not every companion pair needs to be friends. Conflict, rivalry, reluctant respect, and bewildered tolerance are all valid relationship dynamics. Map the web of relationships and design banter for each pairing.

**Topic-driven banter.** Banter should respond to recent events, current locations, and party composition. A conversation about a destroyed village hits differently if a companion is *from* that village.

**The interruption rule.** Party banter should never interrupt critical narrative moments, combat callouts, or environmental audio cues. Implement a robust priority system.

---

## 5. Writing for Voice Acting

Game dialogue is performed. Write for the ear, not the page.

### Performance-Oriented Writing

**Speakability test.** Read every line aloud. If you stumble, the actor will too. Simplify.

**Breath points.** Long lines need natural pause points. Actors need to breathe. Lines without breath points sound rushed and robotic.

**Emotional direction without dictation.** In parentheticals, describe the *situation* and *intent*, not the emotion. Instead of "(angrily)," write "(she's been lied to and she knows it)." This gives the actor room to bring their own interpretation while staying aligned with the scene.

**Mouth feel.** Certain consonant clusters are difficult to voice-act expressively. Hard K sounds, sibilant S chains, and rapid alternation between front-of-mouth and back-of-mouth sounds all create friction. Be conscious of this for key emotional lines.

### Production Considerations

**Line count budgets.** Voice acting is expensive. Plan your line counts early and build your dialogue systems around realistic budgets. A companion with 2,000 lines is a major investment. Make every line count.

**Alt lines.** For any line the player will hear repeatedly (barks, shopkeeper greetings, combat callouts), write 3-5 variants. Variety prevents the "I used to be an adventurer" problem.

**Localization-friendly writing.** Avoid idioms, wordplay, and culture-specific references in critical dialogue. These are expensive or impossible to localize. Save your cleverest language for optional or flavor text.

---

## 6. Procedural and Dynamic Text

For games that generate text dynamically: item descriptions, quest logs, in-game media, AI-driven dialogue.

### Authored Templates with Variable Slots

The simplest form of procedural text. Write complete sentences with specific slots for variable content.

**Do:** "The [adjective] blade of [proper_noun] hums with [element] energy."
**Don't:** "[Adj] [noun] of [noun] — [effect]." (This produces word salad.)

Templates should be varied enough that the player doesn't notice the pattern. Write at least 5-10 templates per category and randomize selection.

### Grammar-Based Generation

For more complex systems, define a narrative grammar: rules for how narrative atoms (characters, actions, objects, locations) can combine into meaningful sentences and paragraphs. Each rule should produce grammatically correct, contextually appropriate text.

### Tone Consistency

Procedural text must match the authored text's tone. If your hand-written descriptions are lyrical and evocative, your procedural descriptions can't be dry and mechanical. Define a style guide for procedural text and test extensively.

---

## 7. Dialogue as Gameplay

In some games, dialogue *is* the core mechanic. Designing dialogue-as-gameplay requires different thinking.

### Conversation Mechanics

**Information as resource.** What the player knows determines which dialogue options are available. Gathering information from other sources (exploration, eavesdropping, documents) unlocks new conversational paths. This creates a feedback loop between dialogue and world interaction.

**Persuasion systems.** Avoid simple "speech check" pass/fail. Instead, design persuasion as a multi-step process: read the NPC's personality, choose an approach (logical, emotional, threatening, flattering), build your argument across multiple exchanges. Failure should open alternative paths, not close doors.

**Debate and confrontation mechanics.** For games where verbal combat is as important as physical combat, design dialogue with the same depth: timing matters, positioning matters (what you've established earlier in the conversation), resources matter (evidence, reputation, emotional leverage).

---

## 8. Common Pitfalls and Solutions

**Exposition dumps.** If a character monologues for more than 30 seconds, you've lost the player. Break exposition into discoveries: let the player *find* the information through exploration, dialogue choices, and environmental clues.

**"As you know, Bob."** Characters should never explain things to each other that they both already know for the player's benefit. Find organic reasons for information to surface — a new arrival, a crisis that demands recap, a disagreement about what happened.

**Protagonist amnesia.** Resist the urge to make the player character a newcomer who needs everything explained. If the protagonist is an experienced member of the world, let the player learn through *doing* rather than through *asking basic questions*.

**Uniform voice.** Every NPC sounds like the same writer. Solution: create a voice sheet for each major character defining their vocabulary level, sentence length preference, verbal tics, topics they gravitate toward, and topics they avoid. Read each character's lines in isolation — they should be identifiable without speaker tags.

**Dead-end responses.** A dialogue option that leads to a generic "I see" or "Interesting" teaches the player not to bother exploring dialogue. Every option the player selects should yield something: information, character, humor, consequence, or atmosphere.