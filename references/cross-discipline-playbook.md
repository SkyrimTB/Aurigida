# Cross-Discipline Playbook

## Table of Contents
1. The Narrative Designer's Position in the Studio
2. Speaking Each Department's Language
3. Negotiation Frameworks
4. Scope Management
5. Conflict Resolution
6. Pitching Narrative Ideas Internally
7. Managing Up (Working with Directors and Leads)
8. Working with External Partners (VO Actors, Outsource Writers, Licensors)
9. The Narrative Designer's Meeting Toolkit
10. Career Advocacy and Visibility

---

## 1. The Narrative Designer's Position in the Studio

The narrative designer is unique: you have no department that's "yours" in the way that art has the art department, code has engineering, and levels have level design. Your work lives *inside* everyone else's work. This is both your greatest vulnerability and your greatest superpower.

**Vulnerability**: Without a dedicated department, your work is the first to be cut when scope tightens. No one else on the team fully understands the narrative pipeline, so estimates are often wrong (underscoped), and your needs are often deprioritized because they cross department boundaries.

**Superpower**: You have a legitimate reason to be in every meeting, review every asset, and influence every system. No other role touches art, code, audio, level design, QA, localization, and marketing. Use this access deliberately. Build relationships across the entire team.

**The fundamental rule**: Your authority comes from the quality of your ideas and the clarity of your communication — not from your title. A narrative designer who makes everyone else's work better is indispensable. A narrative designer who creates work for other departments without understanding their constraints is a liability.

---

## 2. Speaking Each Department's Language

### Engineering

**They value**: Precision, predictability, technical feasibility, clean data, well-defined scope.

**How to communicate**:
- Describe narrative features as *systems* with inputs, outputs, and state. "The companion trust system takes player choices as input, maintains a per-companion integer score, and outputs available dialogue nodes based on threshold values." This is a system description an engineer can estimate.
- Use their vocabulary: "node graph," "state machine," "event-driven," "callback," "condition evaluation." You don't need to code — you need to describe your design in a way that maps to code.
- Provide edge cases. When you propose a feature, anticipate the "what if" questions: What if the player does X? What happens at boundary conditions? What's the failure state? Engineers respect thoroughness.
- Never say "it should just..." or "can't you just..." The word "just" implies something is simple, which is dismissive of engineering complexity.

**In meetings with engineers**: Lead with the data structure, then explain the creative intent. They'll engage with the creative once they understand the technical shape.

### Art and Animation

**They value**: Visual clarity, creative freedom, reference material, mood over specifics.

**How to communicate**:
- Lead with *feeling*, not with *specs*. "This character moves like they're carrying something heavy that isn't physical — slow, deliberate, always slightly bowed" gives an animator creative direction. "Walk speed 2.3, head tilt 15 degrees" does not.
- Provide reference images, film clips, and photography — not just written descriptions. A 30-second film clip communicates more about a scene's visual tone than a page of text.
- When reviewing concept art, respond to the emotional intent before critiquing details. "This captures the isolation perfectly — the scale of the environment against the character is exactly right. Can we push the color temperature colder to reinforce the loneliness?" This validates the artist's interpretation before redirecting.
- Respect their craft knowledge. If an animator says a character animation will take 3 days, they know better than you. Ask "is there a simpler version that captures the same feeling?" rather than "can you do it in 1 day?"

**In meetings with artists**: Lead with mood boards and references, then explain the narrative context. Artists think spatially and visually — translate your narrative into images before you translate it into words.

### Audio and Music

**They value**: Emotional clarity, scene context, creative latitude, early involvement.

**How to communicate**:
- Describe the emotional arc of a scene, not the technical audio output. "This scene starts warm and familiar, then something slightly wrong enters — a note that doesn't belong, a rhythm that's off. By the end, the warmth is gone and the wrongness is all that's left." A sound designer or composer can build from this.
- Provide the "sound of the world" early. What does this world sound like when nothing is happening? The ambient soundscape is the foundation — music and dialogue sit on top of it.
- Involve audio in storyboarding. The moment when music drops out is as powerful as any line of dialogue. Design those silences together.
- Share bark lists and VO schedules early. Audio needs lead time for recording sessions, and last-minute VO additions are the most expensive kind of scope creep.

**In meetings with audio**: Lead with the scene's emotional journey, then discuss specific cues and triggers. Audio professionals think in time and emotion — your narrative timeline is their workflow.

### Level Design

**They value**: Player flow, spatial clarity, pacing control, metrics-driven decisions.

**How to communicate**:
- Collaborate during greybox, not after polish. If you walk into a finished level and say "we need a room for this conversation," you're creating rework. If you walk into a greybox and say "what if this corridor has a locked door that creates a reason to backtrack after the revelation in Act 2?" you're adding value.
- Think spatially. "This revelation should happen on a vista — the player crests a hill and sees the destination for the first time, and the scale of it makes them understand what they're up against." This gives the level designer both a narrative beat and a spatial design constraint.
- Provide player intent for each area. "In this area, the player is searching for clues. The pacing should feel investigative — small rooms, lots of readable objects, quiet ambient audio." vs "In this area, the player is fleeing. The pacing should feel urgent — long sightlines, few stops, escalating audio."

**In meetings with level designers**: Walk the level together (even in greybox). Point at spaces and tell stories about them. Level designers think by moving through space — meet them there.

### Producers

**They value**: Predictability, measurability, risk management, milestone deliverables, person-hours.

**How to communicate**:
- Translate everything to numbers. "This companion questline requires 340 VO lines, 2 in-engine cinematics (est. 3 person-days each), 12 bark variants (existing recording session), and 1 custom environment prop. Writing and scripting: 5 person-days. Total: 11 person-days."
- Present scope ladders (Gold/Silver/Bronze/Iron) for every major feature. Don't wait for cuts — offer your own triage. This demonstrates maturity and builds trust.
- Flag risks early. "The branching quest in Act 2 has 4 convergence points that each need unique dialogue. If VO recording slips by 2 weeks, we'll need to cut 2 branches." This is a risk assessment, not a complaint.
- Treat milestone deliverables as contracts. If you promised a narrative bible by milestone 2, deliver it — or flag the slip early with a revised date.

**In meetings with producers**: Lead with status, risks, and numbers. Then discuss creative intent — they care about the creative, but they need the production data first.

### QA

**They value**: Clear test plans, context for edge cases, accessibility, quick response to "is this a bug?" questions.

**How to communicate**:
- Write narrative test plans. Don't assume QA knows which dialogue paths exist or which flags affect the story. Provide a map.
- Be available for questions. Narrative bugs often require judgment calls: "Is it intentional that this NPC says 'I heard you helped the rebels' when the player sided with the empire?" Only you can answer that.
- Respect their findings. When QA flags a narrative issue, it usually reflects a real player experience problem — even if the content is technically "correct."

---

## 3. Negotiation Frameworks

### The Interest-Based Negotiation

When narrative and another department are in conflict (e.g., you need a custom animation for a critical scene, animation says they're at capacity):

1. **Separate positions from interests.** Your position: "I need this custom animation." Their position: "We can't add more animation work." The real interests: you need the scene to emotionally land; they need to hit their milestone deadline.

2. **Find the overlap.** Is there a way to achieve the emotional beat without custom animation? Could an existing animation be repurposed with different camera framing? Could the scene use environmental storytelling instead of character animation?

3. **Trade, don't demand.** "If animation can give me one custom moment for Elena's betrayal scene — even just 5 seconds — I'll cut the two ambient animations I requested for the tavern sequence. Net zero on your schedule, but it concentrates the custom work where it matters most."

4. **Escalate with data, not emotion.** If you can't resolve it: "I'd like to flag this for the director. The betrayal scene is the emotional climax of Act 2, and our playtest data shows players are disengaging during the current version. I believe a custom animation would solve this, and I've already offered scope trades to animation to make it feasible."

### The Scope Trade

Never ask for something without offering something in return. This is the single most effective negotiation habit in game development.

**The formula**: "If I could get [thing I need] from [department], I would cut [thing of equal or greater cost] from my own deliverables. Net impact: [zero/positive for them]."

**Example**: "If engineering can give me 2 more narrative flags in the save system, I'll simplify the faction reputation from a 0-100 scale to a 3-tier system (hostile/neutral/friendly). That actually reduces the total data we're saving while giving me the specific flags I need for the ending branches."

### The "Help Me Understand" Move

When someone rejects your request and you don't understand why:

Don't say: "Why not?" (sounds confrontational)
Say: "Help me understand the constraint — I want to make sure I'm designing around the real limitation, not a misunderstanding on my part."

This is disarming, respectful, and often reveals that the constraint is more flexible than the initial "no" suggested.

---

## 4. Scope Management

### The Scope Mindset

Scope is not the enemy of quality — it's the shape of quality. A beautifully scoped game is better than an ambitious game that shipped half-finished. Your job is not to fight for everything you've written — it's to fight for the right things and gracefully release the rest.

### Triage Categories

When cuts are needed, categorize every narrative element:

**Load-bearing** — Cannot be cut without breaking the story. Main quest critical path, key character introductions, act transitions, endings. If this is cut, the game's narrative doesn't function.

**Structural** — Reinforces the main narrative significantly but isn't strictly necessary. Major side quests that introduce key themes, companion arcs that deepen the protagonist's journey, world-building that establishes the rules of the setting. Cutting these hurts but doesn't break.

**Texture** — Adds richness and immersion but can be removed cleanly. Ambient NPC dialogue, environmental storytelling vignettes, optional lore entries, side quests that are self-contained. The game is less rich without these, but the core experience stands.

**Polish** — The extra layer that delights. Bark variants, idle animations with narrative content, Easter eggs, callback dialogue. These are the first to cut and the last to add back.

### The Pre-Mortem

Before cuts happen, do a "pre-mortem" on your own content:
- If this game ships at 70% of current scope, what must survive?
- Which quests are secretly load-bearing? (Side quests that introduce information the main quest depends on)
- Which characters can be merged?
- Which branches can be collapsed into a single path without losing the *feeling* of choice?

Having these answers ready before the producer asks is the difference between being a strategic partner and being a victim of cuts.

---

## 5. Conflict Resolution

### Common Conflicts and Approaches

**"The story is slowing down the game."** (From design or production)
- Don't defend the story abstractly. Ask: "Where specifically is the pacing off?" Then address those specific moments. Often the issue isn't "too much story" — it's "story in the wrong place" (a cutscene interrupting a high-energy gameplay sequence, an exposition dump in the middle of an action level).
- Offer to restructure: "What if we move this conversation from a forced cutscene to an optional campfire scene? Same content, player-initiated pacing."

**"We can't implement this branching."** (From engineering)
- Understand their constraint fully before proposing alternatives. Is it a technical limitation (save system can't track that many states)? A time limitation (too many paths to script by milestone)? A testing limitation (QA can't verify all branches)?
- Design within the constraint: "If we're limited to 10 narrative flags for this quest, I can redesign the branching to use a 3-tier outcome (help/neutral/hinder) instead of 5 specific permutations. We lose some granularity but keep the feeling of meaningful choice."

**"This character design won't work visually."** (From art)
- Listen to the visual concern. Artists understand what reads on screen. If they say a design element is too subtle to read at game camera distance, they're probably right.
- Collaborate on a solution: "The scar was meant to signal their violent past. If it's too subtle, what if their body language tells that story instead? A flinch when someone moves too fast, a refusal to sit with their back to the door."

**"This VO budget is too high."** (From production)
- Present the scope ladder. Show what the experience looks like at each tier.
- Identify lines that can be systemic rather than unique: "Instead of 20 unique shopkeeper greetings (one per shop), we use 5 greeting templates that adapt to player reputation. Same variety feeling, 75% fewer lines."

### The Non-Negotiables

Know your non-negotiables before entering any negotiation. These are the 2-3 elements that define the game's narrative identity. Everything else is negotiable.

**How to identify non-negotiables**: "If we cut this, would the game still feel like *this game*?" If removing a character, scene, or system changes the fundamental identity of the experience, it's non-negotiable.

**How to defend non-negotiables**: With data, not passion. "This character's arc is the emotional spine of the game. Our playtest showed 85% of testers named this character as their reason for wanting to continue playing. Cutting them doesn't save scope — it removes the thing that makes players care about the scope we have."

---

## 6. Pitching Narrative Ideas Internally

### The 3-Layer Pitch

When proposing a new narrative feature or direction to the team:

**Layer 1: The Player Experience (30 seconds)**
What does the player feel? What do they do? What makes them care?
"Imagine the player walks into a town they've been hearing about for 10 hours. Every NPC has mentioned this place with fear. When they arrive — it's beautiful. Peaceful. Children playing. And that's when the horror begins, because the player realizes what's wrong before any NPC tells them."

**Layer 2: The Implementation Shape (2 minutes)**
How does it work? What systems does it use? What does it cost?
"This requires 3 environmental storytelling setups in the level (art team has capacity), a trigger-based bark system that shifts NPC dialogue from pleasant to disturbing over 15 minutes of real-time play (engineering estimates 2 days), and 60 VO lines (within our current recording budget for Act 2)."

**Layer 3: The Scope Flexibility (1 minute)**
What's the fallback? How does this survive cuts?
"At minimum, this works as a single static revelation — player enters town, finds evidence, quest updates. The gradual shift version is the ideal, but the minimum viable version still delivers the key narrative beat."

### Timing Your Pitch

- **Pre-production**: Pitch big ideas. This is when the creative vision is being set.
- **Production**: Pitch refinements and optimizations. Big new ideas are disruptive.
- **Post-production**: Pitch DLC and post-launch narrative direction.

Don't pitch a major new system during crunch. Read the room.

---

## 7. Managing Up (Working with Directors and Leads)

### The Creative Director Relationship

The creative director is your most important ally and your most important check. They set the vision; you translate it into narrative.

- **Align early and often.** Schedule regular 1:1s specifically to discuss narrative direction. Don't wait for review meetings to discover misalignment.
- **Present options, not decisions.** "I see two directions for the ending: A costs X and delivers Y feeling, B costs Z and delivers W feeling. I lean toward A because [reason], but I wanted your input before I commit the team."
- **Push back respectfully when needed.** If the creative director's request contradicts established narrative logic, you have a duty to flag it: "I love the idea, and I want to find a way to make it work. Right now it contradicts [established element]. Here's how I'd reconcile them — does this work?"

### When Your Idea Gets Killed

It happens. Regularly. How you handle it defines your reputation:
- Ask why (genuinely, not defensively). The reason might reveal a constraint you can design around.
- Let it go publicly. Don't relitigate in other meetings or in side conversations.
- Save the idea. Cut content often returns in sequels, DLC, or future projects. Archive it.
- Redirect your energy. The next idea is always more important than the last one.

---

## 8. Working with External Partners

### Voice Actors

- **Casting**: Provide character sheets with voice profile, emotional range, and reference performances. Sit in on auditions when possible.
- **Direction**: Brief the voice director thoroughly. They're your proxy in the booth. Give them the narrative bible page for each character, key relationship dynamics, and the emotional arc of the recording session.
- **In the booth**: If you're present, direct by situation and intent, never by line reading. Don't say "say it angrier." Say "she just found out her brother lied to protect her. She's angry, but underneath it, she's hurt because the lie means he didn't trust her to handle the truth."
- **Pickups**: There will always be pickups (re-records for changed lines or missed performances). Budget for them. Maintain a running pickup list throughout production.

### Outsource Writers

- Provide the narrative bible, tone guide, and dialogue samples *before* they write a word.
- Define scope precisely: quest ID, word count, character voices involved, narrative constraints.
- Review early and often. Catching a tone mismatch at outline stage saves weeks of rewriting.
- Credit them appropriately in the final game.

---

## 9. The Narrative Designer's Meeting Toolkit

### Before Any Meeting
- Know your ask: What do you need from this meeting?
- Know your offer: What can you give?
- Know your fallback: If you don't get what you need, what's plan B?
- Prepare visuals: Flowcharts, mood boards, or reference clips > walls of text in slides

### In Review Meetings
- Lead with the player experience, not the document structure
- When receiving feedback, write it down visibly — people feel heard when they see you recording their input
- Don't defend on the spot — say "That's interesting, let me think about how to integrate that" and follow up later

### When Presenting to Stakeholders
- Start with the fantasy: "In this game, you are..."
- Show, don't tell: If you can, demo. If you can't, show concept art with narrative annotations.
- Anticipate the budget question. Have your scope estimate ready before they ask.
- End with the "water cooler moment": "This is the scene players will talk about. This is the moment that goes viral. This is why people will buy the sequel."

---

## 10. Career Advocacy and Visibility

### Making Narrative Visible

Narrative work is often invisible. The best compliment to a narrative designer — "I didn't even notice the writing, it just felt natural" — is also the worst for career visibility. Combat this:

- **Document your impact with data.** "Player retention through Act 2 increased 15% after the companion dialogue rewrite." "Playtest scores for quest engagement rose from 3.2 to 4.1 after the quest restructure."
- **Present at team reviews.** When the level designer shows the level, ask to co-present the narrative layer. When the cinematic is reviewed, be there to explain the narrative function.
- **Write post-mortems.** After the game ships, document what worked, what didn't, and what you'd do differently. This is valuable for the studio and positions you as someone who thinks systematically about craft.
- **Contribute to the discipline.** Write articles, give GDC talks (or internal talks), share tools and methods. The narrative design discipline is still maturing — your contributions shape the industry.

### Building Your Influence

Influence in a studio is earned, not assigned. The narrative designers who have the most creative influence are the ones who:
- Solve other people's problems (not just their own)
- Speak every department's language (not just writer-speak)
- Deliver on time (not just beautifully)
- Are in the room (not just in their office writing)
- Listen more than they talk (and when they talk, it matters)