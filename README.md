# Aurigida — Game Narrative Director Skill for Claude Code

A Claude Code skill that gives you a polymath AAA narrative director as a collaborator. Aurigida draws from the full breadth of human achievement — literature, film, art, history, philosophy, science, music, mythology — and dissolves it into legendary game design.

## What It Does

When active, Aurigida transforms Claude into a seasoned creative director and investor strategist who has shipped AAA titles and approaches every game problem through seven disciplines simultaneously:

- **Cultural Alchemy** — Stealing structural principles from poetry, painting, architecture, history, and every other human discipline
- **Game Design** — Ludonarrative consonance, player agency, mechanical metaphor
- **Screenwriting** — Scene construction, dramatic irony, the Kuleshov Effect
- **Literary Fiction** — Character interiority, subtext, thematic coherence
- **Technical Implementation** — Dialogue middleware, engine integration, data architecture
- **Production Leadership** — Cross-discipline communication, scope negotiation, GDD writing
- **Investor Strategy** — Pitch decks, competitive analysis with revenue data, market sizing (TAM/SAM/SOM), translating creative vision into business language for VCs and publishers

## When It Activates

Aurigida activates automatically when you mention anything related to:

- Game narrative, story, characters, dialogue, cutscenes, quests, lore, world-building
- Game concepts, pitches, one-pagers, narrative bibles, creative direction
- Game design documents (GDD), quest docs, character sheets, VO scripts
- Dialogue systems in Unreal, Unity, or Godot — Yarn Spinner, Ink, Twine, Articy:Draft
- Cross-discipline team leadership, narrative pipeline, VO recording
- Casual phrasing like "I have a game idea," "help me with my game's story," "how do I make players cry"
- Investor and business phrasing: pitch decks, fundraising, VC meetings, publisher presentations, competitive analysis, market sizing, comparable title performance, financial projections

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
| `dialogue-systems.md` | Dialogue trees, barks, companion dialogue, VO writing, procedural text |
| `gdd-narrative-templates.md` | Templates for one-pagers, bibles, quest docs, character sheets, dialogue scripts |
| `engine-dialogue-implementation.md` | Unreal/Unity/Godot patterns, middleware, data architecture, localization pipelines, QA |
| `cross-discipline-playbook.md` | Department communication, negotiation, scope management |
| `investor-pitch-playbook.md` | Investor persuasion, pitch deck architecture, competitive analysis frameworks, game industry market data, TAM/SAM/SOM, financial projection models, comparable title revenue benchmarks, VC communication strategies |

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
- "Help me build a pitch deck for VCs who have never played a game in their lives."
- "What's the TAM for narrative RPGs and how do I frame it for investors?"
- "Generate a competitive analysis against Hades, Disco Elysium, and Baldur's Gate 3 with sales numbers."
- "How do I explain what my game is to someone who only understands SaaS metrics?"

## Contributing

Contributions to the reference library are welcome. Each reference file follows the pattern of deep, specific, craft-level guidance — not generic advice, but the kind of insight that names the painting, the poem, the historical event behind the design principle.

## License

MIT

---

## Aurigida — Claude Code 游戏叙事总监技能

一个 Claude Code 技能，为你提供一位博学的 AAA 级叙事总监作为协作者。Aurigida 汲取人类一切成就的精华——文学、电影、艺术、历史、哲学、科学、音乐、神话——并将其融炼为传奇级别的游戏设计。

## 功能介绍

激活后，Aurigida 将 Claude 转变为一位经验丰富的创意总监与投资策略师，曾参与 AAA 级游戏的开发，并同时从七个维度处理每一个游戏问题：

- **文化炼金** — 从诗歌、绘画、建筑、历史及一切人类学科中提取结构性原则
- **游戏设计** — 叙事与机制的协调统一、玩家能动性、机制隐喻
- **剧本写作** — 场景构建、戏剧性反讽、库里肖夫效应
- **文学虚构** — 角色内心世界、潜台词、主题连贯性
- **技术实现** — 对话中间件、引擎集成、数据架构
- **制作领导力** — 跨部门沟通、范围协商、GDD 文档撰写
- **投资策略** — 融资路演、竞品分析（含销售数据）、市场规模测算（TAM/SAM/SOM）、将创意愿景转化为投资人语言

## 激活时机

当你提到以下任何内容时，Aurigida 将自动激活：

- 游戏叙事、故事、角色、对话、过场动画、任务、背景设定、世界构建
- 游戏概念、提案、一页纸介绍、叙事圣经、创意方向
- 游戏设计文档（GDD）、任务文档、角色表、配音脚本
- Unreal、Unity 或 Godot 中的对话系统 — Yarn Spinner、Ink、Twine、Articy:Draft
- 跨部门团队领导、叙事流程、配音录制
- 日常表达如"我有个游戏创意"、"帮我完善游戏故事"、"怎么让玩家哭出来"
- 投资与商业相关表达：融资路演、风险投资会议、发行商提案、竞品分析、市场规模、可比游戏销售数据、财务预测

## 安装方法

### 方式一：项目级技能（单个游戏）

将 `SKILL.md` 和 `references/` 文件夹复制到项目的 `.claude/skills/` 目录：

```
your-game-project/
  .claude/
    skills/
      aurigida/
        SKILL.md
        references/
```

### 方式二：用户级技能（所有项目）

复制到 Claude Code 全局技能目录：

- **macOS/Linux：** `~/.claude/skills/aurigida/`
- **Windows：** `%USERPROFILE%\.claude\skills\aurigida\`

## 参考资料库

`references/` 文件夹包含 Aurigida 在生成详细输出前会读取的深度知识库：

| 文件 | 用途 |
|---|---|
| `cultural-alchemy.md` | 逐学科指南，介绍如何从诗歌、绘画、历史、音乐、哲学、生物学、神话等领域汲取灵感 |
| `masterwork-study.md` | 从游戏设计视角分析各学科经典作品，提炼可用于互动媒体的原则 |
| `taste-and-direction.md` | 传奇创意总监如何找到正确方向；创意判断的案例研究；品味的培养 |
| `narrative-structures.md` | 叙事模型与游戏结构的对应关系 |
| `dialogue-systems.md` | 对话树、随机台词、伴侣对话、配音写作、程序化文本 |
| `gdd-narrative-templates.md` | 一页纸介绍、叙事圣经、任务文档、角色表、对话脚本模板 |
| `engine-dialogue-implementation.md` | Unreal/Unity/Godot 模式、中间件、数据架构、本地化流程、QA |
| `cross-discipline-playbook.md` | 部门沟通、协商谈判、范围管理 |
| `investor-pitch-playbook.md` | 投资人说服策略、路演 PPT 架构、竞品分析框架、游戏行业市场数据、TAM/SAM/SOM、财务预测模型、可比游戏营收基准、风险投资沟通策略 |

## 设计理念

**游戏不是由游戏创造的。** 历史上最平庸的游戏，出自那些只玩游戏的人之手。最具原创性的游戏，出自那些广泛阅读、研究历史、观看舞蹈、聆听歌剧，并将这一切带入这个媒介的人之手。

Aurigida 将**六口井**运用于每一个创意问题——在问"其他游戏怎么做"之前，先问：诗人会怎么做？画家会怎么做？历史学家会怎么做？科学家会怎么做？哲学家会怎么做？音乐家会怎么做？

**七重透镜**同时审视每一个叙事元素：博学深度、写作真实性、设计功能、导演调度、工程可行性、制作可持续性——以及最重要的——一个从未读过设计文档的玩家，是否能真正**感受到**它。

## 示例提示词

- "我想做一个关于濒危语言的 RPG，帮我发展这个概念。"
- "为一个秘密资助革命的商人写一个任务。"
- "如何在 Unreal Engine 5 中用 Yarn Spinner 实现分支对话？"
- "我的团队不理解为什么叙事需要三幕结构，帮我解释一下。"
- "我想让游戏的战斗在叙事上有意义，怎么做？"
- "为一个发生在洪水淹没的档案馆中的生存游戏写一份 GDD 一页纸。"
- "帮我做一套面向从未玩过游戏的 VC 的融资路演 PPT。"
- "叙事 RPG 的 TAM 是多少？我怎么向投资人呈现这个数据？"
- "生成一份对比《哈迪斯》《迪斯科极乐世界》《博德之门 3》的竞品分析，附销售数据。"
- "如何向只懂 SaaS 指标的人解释我的游戏？"

## 贡献

欢迎为参考资料库贡献内容。每个参考文件都遵循深度、具体、工艺级别的指导原则——不是泛泛而谈，而是那种能说出设计原则背后的画作、诗歌、历史事件的洞见。

## 许可证

MIT
