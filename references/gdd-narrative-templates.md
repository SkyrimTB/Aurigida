# GDD Narrative Templates

## Table of Contents
1. Narrative One-Pager
2. Narrative Bible Structure
3. Story Outline Format
4. Quest Design Document
5. Character Sheet (Production)
6. Dialogue Script Format
7. Narrative Scope Estimation
8. Living Document Practices

---

## 1. Narrative One-Pager

This document decides whether the project lives or dies. Every sentence must justify its existence. The audience is stakeholders: studio leads, publishers, investors, or the team lead at an indie studio deciding what to build next.

### Template

```
[GAME TITLE]
Narrative One-Pager | [Date] | [Author]

COCKTAIL PITCH
[One sentence. The fantasy. The hook. What the player IS.]
Example: "You are the last cartographer in a world that keeps redrawing itself."

GENRE & TONE
[Genre] | [Tone keywords, max 3-4]
Example: Open-world exploration | Melancholic, wonder, quiet dread

THE PLAYER FANTASY
[2-3 sentences. What does it FEEL like to play this game moment to moment?
Not what happens — what the player experiences emotionally and mechanically.]

PROTAGONIST
[Name or archetype] — [One-line character summary including their core contradiction]
Example: Kael — A blind navigator who sees the world more clearly than anyone with sight.

CENTRAL CONFLICT
[The external conflict in one sentence]
[The internal conflict in one sentence]
[Why these two conflicts create tension with each other]

NARRATIVE STRUCTURE
[Model: Linear / Branching / Emergent / Hybrid]
[Number of acts or chapters]
[Key structural innovation, if any]

THE HOOK — WHY THIS MUST BE A GAME
[1-2 sentences on why this story can ONLY work as a game. What does interactivity
add that film or a novel cannot? This is the most important section for greenlight.]

COMPARABLE TITLES
[2-3 titles with a brief note on what you're taking from each]
Example: "The exploration loop of Outer Wilds meets the character intimacy of
Firewatch, set in the visual language of Moebius comics."
```

### Writing Guidance
- The cocktail pitch is the most important line. If it doesn't make someone say "tell me more," rewrite it.
- Comparables are not aspirational ("like GTA but..."). They're communicative — they help the reader immediately understand the experience space.
- "Why this must be a game" is where most one-pagers fail. "Because games are interactive" is not an answer. What *specific* interactive affordance makes this story impossible in other media? Player choice? Spatial exploration? Mechanical metaphor? Emergent systems?

---

## 2. Narrative Bible Structure

The bible is the world's source of truth. It is a living document — it grows and changes as the project evolves. It must be searchable, well-organized, and maintained by one person (usually the lead narrative designer) to prevent contradictions.

### Recommended Structure

```
NARRATIVE BIBLE — [Game Title]
Version [X.X] | Last Updated [Date] | Owner: [Name]

SECTION 1: WORLD RULES
  1.1 Physical Laws — What's different from our world? Magic systems, technology
      level, geographical rules, cosmology.
  1.2 Social Structure — How is society organized? Classes, castes, governance.
  1.3 Economics — What's valuable? How do people survive? What drives conflict
      at the material level?
  1.4 Religion & Belief — What do people believe? How do those beliefs create
      tension? Are the gods real?
  1.5 Technology & Magic — How does it work? What are the limits? What's the
      cost of use?
  1.6 The Unknown — What is deliberately mysterious? What questions does the
      game ask but not answer? (Protect these — don't let other docs accidentally
      resolve them.)

SECTION 2: HISTORY TIMELINE
  Presented chronologically. Each entry:
  - Date/era
  - Event
  - Consequences (what changed because of this)
  - Player relevance (when/how the player encounters evidence of this)

SECTION 3: FACTIONS
  Per faction:
  - Name and visual identity keywords
  - Philosophy / governing belief
  - What they want (stated goal)
  - What they actually want (hidden goal, if different)
  - Internal tensions (factions are not monoliths)
  - Relationship to other factions (ally/rival/indifferent + why)
  - Player interaction model (joinable? Questline? Enemy? Neutral?)

SECTION 4: KEY CHARACTERS
  Per character (major characters only — minor NPCs go in quest docs):
  - Name, age, role
  - One-paragraph summary (the "bible page" — anyone on the team reads
    this to understand the character instantly)
  - Core contradiction
  - Arc summary (beginning state → end state)
  - Key relationships (map format if complex)
  - Voice profile: vocabulary level, sentence patterns, verbal tics,
    topics they gravitate toward, topics they avoid
  - Visual identity keywords (for concept art)

SECTION 5: TONE GUIDE
  - Tone keywords with examples (what "melancholic" means in THIS game)
  - Dialogue register (formal? Colloquial? Archaic? Mixed?)
  - Humor policy (type of humor allowed, frequency, what's off-limits)
  - Violence policy (graphic? Implied? Consequences shown?)
  - Profanity policy (none? Light? Realistic? Character-dependent?)
  - Reference examples: "This game's dialogue should feel like [X],
    not like [Y]."

SECTION 6: NAMING CONVENTIONS
  - Character naming rules (linguistic roots, cultural patterns)
  - Place naming rules
  - Item/ability naming rules
  - Glossary of invented terms with pronunciation guides

SECTION 7: NARRATIVE BOUNDARIES
  - What this story is NOT about (anti-themes)
  - Topics handled with care (and how)
  - Sensitivity considerations
  - Content rating targets and their narrative implications
```

### Maintenance Rules
- Single owner with final authority on contradictions
- Version numbered, changes logged
- Reviewed by narrative team weekly during production
- Other departments reference the bible but never edit it directly — they submit change requests

---

## 3. Story Outline Format

The story outline is the structural blueprint. It maps the emotional journey, the key narrative beats, and the branching architecture. Level designers, quest designers, and cinematic teams build from this.

### Template

```
STORY OUTLINE — [Game Title]
Version [X.X] | [Date]

THEMATIC STATEMENT
[One sentence. What is this game ultimately about?]
Example: "Power without accountability always becomes cruelty."

EMOTIONAL CURVE
[Map the intended emotional experience across the game's runtime. Use a simple
notation: each act gets 2-3 emotional keywords and an intensity level 1-5]

Act 1: Wonder (2) → Unease (3)
Act 2: Determination (3) → Betrayal (5) → Grief (4)
Act 3: Resolve (4) → Sacrifice (5) → Quiet Hope (3)

ACT BREAKDOWN

ACT [N]: [Title]
  Estimated playtime: [X hours]
  Emotional arc: [Starting emotion → ending emotion]

  BEAT 1: [Beat Name]
    Type: [Cinematic / Gameplay / Environmental / Dialogue / Mixed]
    Location: [Level/area name]
    Summary: [2-3 sentences — what happens]
    Player action: [What does the player DO during this beat?]
    Narrative function: [Why does this beat exist? What does it set up, pay off,
    or reveal?]
    Key characters: [Who is present?]
    Required assets: [VO lines estimate, cinematics, unique props/environments]
    Dependencies: [What must happen before this beat? What does it unlock?]

  BEAT 2: ...

BRANCHING MAP
  [For branching narratives, include a flowchart — even ASCII/text-based —
  showing decision points, branch paths, and convergence points. Mark which
  branches affect the ending and which are cosmetic.]

ENDINGS
  [List each ending with:]
  - Trigger conditions (what choices lead here)
  - Emotional tone
  - Thematic statement (how this ending answers the thematic question)
  - Final image/moment
  - Estimated % of players who will see this ending on first playthrough
```

---

## 4. Quest Design Document

Quest docs are the most engineer-facing narrative documents. They must be buildable.

### Template

```
QUEST: [Quest Name]
Quest ID: [QST_XXX]
Type: [Main / Side / Companion / World / Radiant]
Act/Chapter: [Where in the story]
Prerequisites: [Quests, flags, or conditions that must be true]
Estimated playtime: [Minutes]
Author: [Name] | Version: [X.X] | Date: [Date]

NARRATIVE SUMMARY
[3-5 sentences. The quest as a story. What's the setup, conflict, resolution?]

DESIGN INTENT
[Why does this quest exist? What does it teach, reveal, or make the player feel?
How does it serve the larger narrative?]

QUEST FLOW
[Step-by-step gameplay flow. Each step:]

  Step 1: [Step Name]
    Trigger: [What starts this step — NPC interaction, entering area, item pickup]
    Player objective: [What the player is told to do]
    Hidden objective: [What the quest is actually about, if different]
    Gameplay: [What the player physically does — combat, exploration, dialogue,
    puzzle, etc.]
    Narrative content: [Dialogue exchanges, VO barks, text popups, environmental
    storytelling moments]
    Branching: [Decision points, if any — include conditions and consequences]
    Completion condition: [What flags as done]

  Step 2: ...

BRANCHING FLOWCHART
[Visual or text-based flowchart of all possible paths through the quest.
Mark: decision points (diamonds), narrative outcomes (rectangles),
convergence points (circles)]

CHARACTERS INVOLVED
  [Name] — Role in quest, new VO lines needed: [count]
  [Name] — Role in quest, new VO lines needed: [count]

ASSET REQUIREMENTS
  VO Lines: [Total count, broken down by character]
  Cinematics: [Count and brief description of each]
  Unique Props: [Items, documents, environmental pieces needed]
  Unique Environments: [Any new spaces or modifications to existing spaces]
  Audio: [Ambient audio, music cues, sound effects needed]
  VFX: [Visual effects needed]
  Animation: [Custom animations needed]

FLAGS AND STATE CHANGES
  Sets: [List of narrative flags this quest sets, with conditions]
  Reads: [List of flags this quest checks]
  World state changes: [How the world is different after this quest]

ESTIMATED IMPLEMENTATION
  Scripting: [Hours]
  VO recording: [Lines × estimated session time]
  Cinematic production: [Hours per cinematic]
  QA: [Test cases count]
  Total: [Person-days]
```

---

## 5. Character Sheet (Production)

Character sheets serve two audiences: the creative team (who needs to *know* this person) and the production team (who needs to *build* this person).

### Template

```
CHARACTER SHEET: [Character Name]
Character ID: [CHR_XXX]
Role: [Protagonist / Antagonist / Companion / Major NPC / Minor NPC]
Author: [Name] | Version: [X.X]

THE BIBLE PAGE
[One paragraph. If someone on the team has 30 seconds to understand this
character, this is what they read. Captures essence, contradiction, and
function in the story.]

IDENTITY
  Full name:
  Age:
  Background:
  Occupation/role in world:
  Core contradiction: [The internal tension that makes them interesting]
  Wants: [Conscious goal]
  Needs: [Unconscious need — often in tension with wants]
  Fatal flaw:
  Greatest strength:

ARC
  State at introduction:
  Key turning points: [List with brief descriptions]
  State at conclusion:
  Arc sentence: "[Name] begins as [X] and becomes [Y] because [Z]."

VOICE PROFILE
  Vocabulary level: [1-10, where 1=simple, 10=erudite]
  Sentence length: [Short/Medium/Long/Varies]
  Verbal tics: [Repeated phrases, filler words, speech patterns]
  Topics drawn to: [What they naturally talk about]
  Topics avoided: [What makes them uncomfortable or silent]
  Humor style: [Dry / Sarcastic / Warm / None / Physical]
  Dialogue sample: [3-5 lines in their voice, across different emotions]

VISUAL IDENTITY (for concept art)
  Body language keywords: [How they carry themselves]
  Clothing/armor philosophy: [What their appearance says about them]
  Signature visual element: [One detail an artist can latch onto]
  Color association:
  Reference images: [Film characters, paintings, photographs — not other games]

RELATIONSHIPS
  [Character Name] — [Relationship type] — [One sentence on dynamics]
  [Repeat for each significant relationship]

GAMEPLAY INTEGRATION
  Companion abilities (if companion):
  Bark categories and line count estimate:
  Number of major dialogue scenes:
  Quest involvement: [List quest IDs]

VOICE CASTING NOTES
  Gender:
  Age range:
  Accent/dialect:
  Reference performances: [Actor in specific role — "like [Actor] in [Film]"]
  Emotional range required: [List key emotions the actor must convey]
  Total estimated VO lines:
```

---

## 6. Dialogue Script Format

Formatted for recording sessions. The voice director and actors see this document.

### Format

```
RECORDING SCRIPT — [Game Title]
Character: [Name] | Actor: [Name]
Session: [Session number] | Date: [Date]
Director: [Name]

---

LINE ID: [DLG_CHRXXX_QST_001]
CONTEXT: [2-3 sentences. What's happening in the game at this moment.
Where are they? Who are they talking to? What just happened?]
DIRECTION: [Emotional/performance note. Situation-based, not emotion-label.
"She's realized the person she trusted has been lying for years"
rather than "(angry)"]
TEXT: "The actual dialogue line goes here."
TECH NOTES: [Radio filter / Echo / Whisper / Shouting distance / etc.]
ALTS: [If alternates are needed: ALT1, ALT2]
PRONUNCIATION: [For invented words: "Kaelthar = KALE-thar"]

---

LINE ID: [DLG_CHRXXX_BARK_COMBAT_001]
CONTEXT: [In combat, taking damage, enemy is close range]
DIRECTION: [Pain but still fighting — not defeated, angry]
TEXT: "Not today—"
TECH NOTES: [Effort sound, short breath before line]
```

### Recording Script Guidelines
- Group lines by context (all combat barks together, all quest dialogue together) for acting continuity
- Provide scene context even for barks — actors perform better when they understand the situation
- Never write "(angrily)" or "(sadly)" — write the situation and let the actor find the emotion
- Include pronunciation for every invented word on first appearance
- Mark critical lines (lines where wrong performance breaks the scene) clearly so the director prioritizes coverage

---

## 7. Narrative Scope Estimation

When producers ask "how big is the narrative?" they need numbers.

### Estimation Formula

```
Total VO lines = Main quest lines + Side quest lines + Companion lines +
                 Bark lines + Ambient NPC lines + System lines (UI, tutorials)

Recording time estimate = Total lines × 0.5 minutes per line (rough average
                          including retakes and direction)

Writing time estimate = Total lines × 3-5 minutes per line (including
                        iteration and review)

Localization cost multiplier = Number of supported languages × 0.7
                               (some savings from batch processing)
```

### Scope Categories (industry rough benchmarks)
- **Small narrative game** (Firewatch-scale): 5,000-15,000 VO lines
- **Mid-size RPG** (Disco Elysium-scale): 50,000-100,000 text lines (no VO) or 15,000-30,000 VO lines
- **Large AAA RPG** (Witcher 3-scale): 80,000-150,000+ VO lines
- **Barks-heavy action game** (God of War-scale): 15,000-40,000 VO lines with heavy bark emphasis

### Scope Ladder Template
For each major narrative feature, define:
- **Gold**: The full creative vision, no compromises
- **Silver** (80%): One significant cut that preserves the core experience
- **Bronze** (50%): Minimum viable — the story still works but texture is reduced
- **Iron** (emergency): What happens if this gets cut entirely? What breaks?

---

## 8. Living Document Practices

Narrative documents are not write-once artifacts. They evolve with the project.

**Versioning**: Major.Minor (2.0 = structural revision, 2.1 = content addition, 2.2 = minor fixes). Log changes with dates.

**Review cadence**: Narrative bible reviewed weekly by narrative team. Quest docs reviewed at milestone gates. Character sheets updated after VO recording (actors always add nuance that should be captured).

**Deprecation**: When a narrative element is cut, don't delete it — move it to an "archived" section. Cut content sometimes returns, and the original thinking is valuable context.

**Cross-department access**: All narrative docs should be readable by everyone on the team. Write clearly enough that an engineer who has never read a screenplay can understand the narrative intent. Include a "TL;DR" at the top of long documents.