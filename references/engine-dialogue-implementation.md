# Engine Dialogue Implementation

## Table of Contents
1. Dialogue Middleware Comparison
2. Data Architecture for Narrative
3. Unreal Engine Patterns
4. Unity Patterns
5. Godot Patterns
6. Localization Pipeline
7. Cinematic Implementation
8. Narrative QA and Testing
9. Version Control for Narrative Files
10. Performance Considerations

---

## 1. Dialogue Middleware Comparison

Choose middleware based on team size, narrative complexity, and engine.

### Yarn Spinner
- **Engine**: Unity (native), Godot (community port)
- **Best for**: Teams where writers author directly. Clean markup language that non-programmers learn in hours.
- **Strengths**: Open-source, excellent documentation, built-in localization support, visual node editor (Yarn Editor), strong community. Writers write in `.yarn` files that look like simplified screenplay format.
- **Limitations**: Less suited for extremely complex systemic narratives with hundreds of interdependent variables. Unity-centric ecosystem.
- **Architecture**: Writers author `.yarn` files → Yarn Spinner runtime parses and executes → game code handles display, audio, and state changes via C# callbacks.
- **When to recommend**: Indie to mid-size teams on Unity where writers need autonomy.

### Ink (Inkle)
- **Engine**: Unity (native), Unreal (community integration), web (JavaScript runtime)
- **Best for**: Dense branching prose, choice-driven narratives, text-heavy games.
- **Strengths**: Extremely powerful branching logic. Writers can author complex state-dependent narratives in a clean scripting language. Excellent for prototyping in Inky (desktop editor). Mature and battle-tested (80 Days, Heaven's Vault, Slay the Princess).
- **Limitations**: Less visual than node-based tools — the "shape" of the story lives in the writer's head, not on screen. Steeper learning curve for non-technical writers.
- **Architecture**: Writers author `.ink` files → Ink runtime (C# or JavaScript) handles state, branching, variable tracking → game code reads choices and text output.
- **When to recommend**: Story-driven games with heavy branching, especially if the team has a technical writer or writer-designer hybrid.

### Articy:Draft
- **Engine**: Unity, Unreal (official plugins)
- **Best for**: Large teams with complex world-building and many contributors.
- **Strengths**: Visual node editor with entity management (characters, items, locations all linked). Database-like structure. Flow fragments allow non-linear authoring. Export to JSON/XML. Built-in collaboration features.
- **Limitations**: Expensive commercial license. Learning curve is significant. Can feel heavyweight for small projects. The tool's complexity can become its own management challenge.
- **Architecture**: Authors work in Articy GUI → export to JSON/XML → game-side importer loads data → custom dialogue manager handles runtime.
- **When to recommend**: Studios with 3+ narrative designers, complex world state, or where non-writers (quest designers, level designers) also author narrative content.

### Twine
- **Engine**: Web (native), any engine via export
- **Best for**: Rapid prototyping, proof-of-concept, interactive fiction.
- **Strengths**: Free, zero setup, visual passage map, runs in browser instantly. Multiple story formats (Harlowe, SugarCube, Chapbook) with different complexity levels.
- **Limitations**: Not a production tool for non-web games. Export formats require custom parsing. No built-in engine integration.
- **When to recommend**: Prototyping narrative structure before committing to a production tool. Testing whether a branching story "works" before building it in-engine.

### Custom Solutions
- **When**: Studio has specific needs no middleware covers — deeply systemic narrative, proprietary tools, or performance requirements that off-the-shelf tools can't meet.
- **Cost**: 2-6 months of engineering time for a basic system, 6-18 months for a robust one with authoring tools.
- **Risk**: Engineering team maintains the tool forever. Writers dependent on engineers for tool improvements.
- **Recommendation**: Only for studios with dedicated tools engineers. Start with middleware, migrate to custom only when middleware provably can't handle the design.

---

## 2. Data Architecture for Narrative

### The Narrative Data Stack

```
[Writer Authoring Layer]
    ↓ (export/compile)
[Data Storage Layer] — JSON, XML, SQLite, or custom binary
    ↓ (load at runtime)
[Dialogue Manager] — Core runtime that tracks state, selects nodes, evaluates conditions
    ↓ (outputs)
[Presentation Layer] — UI text display, audio playback, animation triggers, camera control
    ↓ (feedback)
[Game State Layer] — Flags, variables, quest states, relationship values
    ↑ (conditions read from)
[Dialogue Manager] — Loops back, checking state for next node selection
```

### Dialogue Node Schema (Generic)

This is the data structure a narrative designer should be able to describe to an engineer:

```json
{
  "node_id": "DLG_NPC042_QUEST12_003",
  "speaker": "CHR_ELENA",
  "text": "I never said I trusted you. I said I needed you.",
  "audio_id": "VO_ELENA_Q12_003",
  "animation": "ANIM_ELENA_ARMS_CROSSED",
  "emotion_tag": "guarded",
  "conditions": [
    {"flag": "quest_12_betrayal_revealed", "value": true},
    {"variable": "elena_trust", "operator": ">=", "value": 3}
  ],
  "effects": [
    {"set_flag": "elena_acknowledged_distrust", "value": true},
    {"modify_variable": "elena_trust", "delta": -1}
  ],
  "children": ["DLG_NPC042_QUEST12_004A", "DLG_NPC042_QUEST12_004B"],
  "child_conditions": [
    {"child": "004A", "requires": {"flag": "player_apologized", "value": true}},
    {"child": "004B", "requires": "default"}
  ],
  "metadata": {
    "quest": "QST_012",
    "act": 2,
    "priority": "critical",
    "loc_notes": "Emphasis on 'needed' — she's making a distinction between trust and necessity"
  }
}
```

### Flag Management

Narrative flags multiply fast. A mid-size RPG might have 500-2,000 narrative flags. Manage them:

- **Naming convention**: `[system]_[context]_[specific]` — e.g., `quest_blacksmith_sword_repaired`, `companion_elena_trust_broken`, `world_bridge_destroyed`
- **Flag registry**: Maintain a central spreadsheet or database of all flags, their purpose, which quests set them, and which quests read them. This prevents orphaned flags and conflicting states.
- **Flag budgets**: Consult with engineers early about save system limitations. If saves can only track N flags, design within that budget.
- **State machines over booleans**: For complex quest states, use enums (NOT_STARTED, IN_PROGRESS, COMPLETED, FAILED) rather than multiple booleans. Reduces flag count and prevents impossible states.

---

## 3. Unreal Engine Patterns

### Dialogue in Unreal

**Blueprint approach** (most common for narrative designers):
- Dialogue UI driven by UMG widgets
- Dialogue data stored in Data Tables or Data Assets
- Flow control via Blueprint functions that read conditions and advance nodes
- Sequencer for cinematic dialogue sequences (camera, animation, audio synced on a timeline)

**Key Unreal systems narrative designers should understand:**
- **Data Tables**: Spreadsheet-like structures for storing dialogue lines, bark lists, and quest data. Importable from CSV — writers can author in spreadsheets and import.
- **Gameplay Tags**: Hierarchical tag system perfect for narrative flags. `Narrative.Quest.Blacksmith.SwordRepaired` is self-documenting and query-able.
- **Sequencer**: Timeline editor for cinematics. Camera cuts, animation blending, audio cues, particle effects — all on a visual timeline. The narrative designer specs the sequence; the cinematic artist builds it in Sequencer.
- **Dialogue Voice plugin** (if applicable): Unreal's built-in dialogue system with per-context voice selection (same line, different VO based on speaker gender, locale, etc.).
- **Blueprint Interfaces**: Allow dialogue systems to communicate with any actor in the level without hard dependencies. Useful for triggering environmental changes during dialogue.

**Common pitfall**: Over-engineering dialogue in Blueprints. If the Blueprint graph for a single conversation exceeds ~50 nodes, the system needs a data-driven approach (external dialogue files) rather than visual scripting.

### Lip Sync in Unreal
- **MetaHuman + Audio2Face**: Procedural lip sync from audio files
- **FaceFX / OVR Lip Sync**: Middleware options for phoneme-based lip sync
- **Manual curves**: Most precise but most expensive — hand-authored animation curves per line

---

## 4. Unity Patterns

### Dialogue in Unity

**Typical architecture:**
- Dialogue data in ScriptableObjects or JSON files
- Yarn Spinner or Ink as the runtime engine
- Custom DialogueManager MonoBehaviour that orchestrates display, audio, and state
- TextMeshPro for dialogue UI with rich text formatting
- Timeline for cinematic sequences

**Key Unity systems:**
- **ScriptableObjects**: Ideal for narrative data — character profiles, quest definitions, dialogue databases. They're assets, not scene objects, so they persist across scenes and are easy to reference.
- **Addressables**: For managing VO audio clips without loading everything into memory. Stream audio on demand during dialogue playback.
- **Timeline**: Unity's equivalent to Sequencer. Playable tracks for animation, audio, activation — use for in-engine cinematics.
- **Cinemachine**: Procedural camera system. Define virtual cameras with behaviors (follow, look-at, dolly) and blend between them during dialogue.
- **Localization Package**: Unity's official localization system. String tables, locale selection, asset localization (different VO per language). Integrates with Yarn Spinner.

**Common pitfall**: Storing dialogue in MonoBehaviours attached to scene objects. This makes dialogue scene-dependent and hard to maintain. Always externalize dialogue data.

---

## 5. Godot Patterns

### Dialogue in Godot

**Typical architecture:**
- Dialogue data in JSON or custom Resource files
- Dialogic 2 plugin (most popular dialogue system for Godot)
- Custom DialogueManager autoload (singleton) for global narrative state
- RichTextLabel for dialogue display with BBCode formatting
- AnimationPlayer or cutscene system for cinematic sequences

**Key Godot systems:**
- **Custom Resources**: Godot's equivalent to ScriptableObjects. Define `DialogueLine`, `QuestData`, `CharacterProfile` as Resource types.
- **Signals**: Godot's event system. Dialogue events (line_displayed, choice_made, dialogue_ended) communicated via signals.
- **Autoloads**: Singleton scripts that persist across scenes. Perfect for narrative state managers, flag registries, and dialogue managers.
- **Dialogic 2**: Visual dialogue editor with timeline-based authoring. Supports branching, variables, conditions, character expressions, and custom events.

**Common pitfall**: GDScript's dynamic typing can hide narrative bugs (wrong flag name as string, typo in character ID). Use constants or enums for all narrative identifiers.

---

## 6. Localization Pipeline

### The Narrative Designer's Localization Responsibilities

**Before writing:**
- Know the target languages and their UI implications (German text is ~30% longer than English, Japanese needs different font handling, Arabic/Hebrew require RTL support)
- Establish character limits for UI text elements (dialogue boxes, item names, menu strings)
- Decide on formality levels per language (French/German/Japanese have formal/informal registers that affect every line)

**While writing:**
- Write loc-friendly dialogue: avoid idioms, puns, and cultural references in critical paths. Save wordplay for optional flavor text that can be adapted rather than translated.
- Mark gendered text (languages with grammatical gender need variants)
- Use string IDs consistently — never hardcode text
- Include context notes in the string table: translators need to know WHO is saying this, TO WHOM, and in WHAT SITUATION

**String table structure:**
```
ID                          | EN_TEXT                        | CONTEXT                           | CHAR_LIMIT
DLG_ELENA_Q12_003          | I never said I trusted you.    | Elena to player, confrontational  | 80
DLG_ELENA_Q12_003_ALT      | I said I needed you.           | Continuation of above, bitter     | 60
UI_QUEST_COMPLETE           | Quest Complete                 | Screen popup, large font          | 20
BARK_ELENA_COMBAT_LOW_HP_01| I can't keep this up—          | Mid-combat, wounded               | 40
```

**VO localization:**
- Each language needs its own recording sessions — budget accordingly (major cost multiplier)
- Some studios use "wild lines" — actors record the emotional intent in the original language, translators adapt, then local actors match the performance
- Lip sync must be re-driven for each language (or use procedural lip sync that adapts)

---

## 7. Cinematic Implementation

### Speccing Cinematics for Production

When the narrative designer writes a cinematic spec, the cinematic team builds it. The spec must be precise enough to build from but flexible enough to allow cinematic artists to apply their craft.

**Cinematic Spec Format:**
```
CINEMATIC: [ID] — [Title]
Duration: [Estimated seconds]
Trigger: [What causes this to play]
Player control: [Full takeover / Partial / Interactive]
Characters: [List all on-screen characters]
Location: [Level/area]

SHOT LIST:
  SHOT 1: [Duration — e.g., 3 sec]
    Camera: [Wide / Medium / Close-up / Over-shoulder / POV]
    Movement: [Static / Pan / Dolly / Crane / Handheld]
    Subject: [What the camera is focused on]
    Action: [What happens in frame]
    Audio: [Dialogue line ID / Music cue / SFX]
    Emotional beat: [What the player should feel]
    Notes: [Technical requirements — lighting change, particle effect, etc.]

  SHOT 2: ...

TRANSITION OUT:
  [How does control return to the player? Hard cut? Camera pull-back?
  Fade? What's the first thing the player sees/does after the cinematic?]
```

### Interactive Cinematics
For moments where the player retains some control during a cinematic:
- Mark exactly when control is taken and returned
- Specify what inputs the player has (look only? Move? Quick-time event?)
- Define failure states for QTE-style moments (does failure change the outcome or just replay?)
- Camera must accommodate player input — if the player can look around, the composition must work from multiple angles

---

## 8. Narrative QA and Testing

### Test Case Categories

**Branch coverage**: Every path through every dialogue tree is reachable and leads somewhere. No dead ends, no orphaned nodes.

**Flag integrity**: Every flag that is read is also set somewhere. No flag is set to conflicting values by different quests unless intentional. The flag registry matches the actual game state.

**Sequence break testing**: What happens if the player reaches content out of intended order? Does dialogue reference events that haven't happened? Do NPCs acknowledge the player's actual path?

**State consistency**: After completing Quest A and failing Quest B, is the world in a consistent state? Are NPCs aware of both outcomes? Are environmental changes correct?

**Edge cases**: What happens at 0? At max? If the player has max reputation, does the "gain reputation" quest still make sense narratively? If a companion is dead, does quest dialogue that assumes they're alive have fallback lines?

### Narrative Bug Report Template
```
BUG ID: [NAR_XXX]
Type: [Continuity / Missing VO / Incorrect flag / Dead end / Tone break / Loc issue]
Severity: [Blocker / Major / Minor / Polish]
Location: [Quest ID, dialogue node ID, or level]
Repro steps: [Exact steps to reproduce, including save state if relevant]
Expected: [What should happen narratively]
Actual: [What actually happens]
Flags at time of bug: [List relevant flag states]
Screenshot/video: [Attached]
```

---

## 9. Version Control for Narrative Files

### Best Practices

- **One file per conversation or quest** (not one giant dialogue file). This minimizes merge conflicts.
- **JSON with pretty-printing** — human-readable diffs. Never use binary formats for narrative data.
- **Branch naming**: `narrative/quest-12-rewrite`, `narrative/elena-bark-update` — prefix with `narrative/` so engineers can filter.
- **Commit messages**: Reference the quest or character ID. "Updated DLG_ELENA_Q12 — added betrayal variant" > "dialogue changes."
- **Never commit during milestone crunch** without coordinating with the team. Narrative file conflicts during integration can block the entire build.
- **Lock files when editing** if your VCS supports it (Perforce file locking, Git LFS locks). Two writers editing the same dialogue file simultaneously is a recipe for lost work.

---

## 10. Performance Considerations

Narrative systems can become performance bottlenecks if poorly architected:

- **String loading**: Don't load all dialogue into memory at startup. Load per-level or per-quest. Stream VO audio on demand.
- **Condition evaluation**: If every NPC checks 50 flags every frame to determine their bark, you have a performance problem. Evaluate conditions on trigger events, not per-frame.
- **Save file size**: Narrative flags and quest states contribute to save file bloat. Use bitfields for boolean flags, enums for quest states, and prune data that's no longer relevant.
- **UI text rendering**: Rich text with inline images, color changes, and font variations is more expensive to render than plain text. Keep dialogue UI rendering budget-conscious, especially on console.