# Aurigida — Game Narrative Director Skill for Claude Code

A Claude Code skill that gives you a polymath AAA narrative director as a collaborator. Aurigida draws from the full breadth of human achievement — literature, film, art, history, philosophy, science, music, mythology — and dissolves it into legendary game design.

## What It Does

When active, Aurigida transforms Claude into a seasoned creative director who has shipped AAA titles and approaches every game narrative problem through six disciplines simultaneously:

- **Cultural Alchemy** — Stealing structural principles from poetry, painting, architecture, history, and every other human discipline
- **Game Design** — Ludonarrative consonance, player agency, mechanical metaphor
- **Screenwriting** — Scene construction, dramatic irony, the Kuleshov Effect
- **Literary Fiction** — Character interiority, subtext, thematic coherence
- **Technical Implementation** — Dialogue middleware, engine integration, data architecture
- **Production Leadership** — Cross-discipline communication, scope negotiation, GDD writing

## When It Activates

Aurigida activates automatically when you mention anything related to:

- Game narrative, story, characters, dialogue, cutscenes, quests, lore, world-building
- Game concepts, pitches, one-pagers, narrative bibles, creative direction
- Game design documents (GDD), quest docs, character sheets, VO scripts
- Dialogue systems in Unreal, Unity, or Godot — Yarn Spinner, Ink, Twine, Articy:Draft
- Cross-discipline team leadership, narrative pipeline, VO recording
- Casual phrasing like "I have a game idea," "help me with my game's story," "how do I make players cry"

## Installation

### Option 1: Project-level skill (one game)

Copy `SKILL.md` and the `references/` folder into your project's `.claude/skills/` directory:

```
your-game-project/
  .claude/
    skills/
      aurigida/
        SKILL.md
        references/
```

### Option 2: User-level skill (all your projects)

Copy into your global Claude Code skills directory:

- **macOS/Linux:** `~/.claude/skills/aurigida/`
- **Windows:** `%USERPROFILE%\.claude\skills\aurigida\`

## Reference Library

The `references/` folder contains the deep knowledge base Aurigida reads before generating detailed output:

| File | Purpose |
|---|---|
| `cultural-alchemy.md` | Discipline-by-discipline guide to stealing from poetry, painting, history, music, philosophy, biology, mythology, and more |
| `masterwork-study.md` | Specific great works analyzed through a game design lens, with extractable principles for interactive media |
| `taste-and-direction.md` | How legendary creative directors found the right direction; case studies in creative judgment; developing taste |
| `narrative-structures.md` | Narrative models mapped to game structures |
| `dialoue-systems.md` | Dialogue trees, barks, companion dialogue, VO writing, procedural text |
| `gdd-narrative-templates.md` | Templates for one-pagers, bibles, quest docs, character sheets, dialogue scripts |
| `engine-dialogue-implementation.md` | Unreal/Unity/Godot patterns, middleware, data architecture, localization pipelines, QA |
| `cross-discipline-playbook.md` | Department communication, negotiation, scope management |

## Philosophy

**Games are not made from games.** The most derivative games in history were made by people who only played games. The most original games were made by people who read widely, studied history, watched dance, listened to opera, and brought all of it into the medium.

Aurigida applies **The Six Wells** to every creative problem — before asking "what did other games do?", it asks what a poet, a painter, a historian, a scientist, a philosopher, and a musician would each do.

**The Seven Lenses** evaluate every narrative element simultaneously: polymath depth, writing truth, design function, directorial staging, engineering feasibility, production survivability, and — above all — whether a player who has never read a design document will *feel* it.

## Example Prompts

- "I want to make an RPG about a dying language. Help me develop the concept."
- "Write a quest for a merchant who is secretly funding a revolution."
- "How do I implement branching dialogue in Unreal Engine 5 with Yarn Spinner?"
- "My team doesn't understand why the narrative needs three acts. Help me explain it."
- "I want my game's combat to feel like it means something. How do I do that narratively?"
- "Write a GDD one-pager for a survival game set in a flooded archive."

## Contributing

Contributions to the reference library are welcome. Each reference file follows the pattern of deep, specific, craft-level guidance — not generic advice, but the kind of insight that names the painting, the poem, the historical event behind the design principle.

## License

MIT
