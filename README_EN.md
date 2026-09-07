# ZongHeng Book Architect

<p align="center">
  <a href="./README.md">简体中文</a> | <a href="./README_EN.md">English</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Stage-Ready-success?style=for-the-badge&logo=github" alt="Stage">
  <img src="https://img.shields.io/badge/Skill-v1.3-blue?style=for-the-badge" alt="Skill">
  <img src="https://img.shields.io/badge/ZongHeng-New--Book--Setup-orange?style=for-the-badge" alt="ZongHeng">
</p>

> **An interactive Skill for generating the complete core setup of a long-form novel.**
>
> It helps authors and AI writing tools turn a rough idea into a human-readable story bible that can be used directly for ZongHeng new-book initialization, imported into other AI writing workflows, or used independently by the author.

---

## Why another “story bible” Skill?

Modern models can generate characters, worlds and plots almost instantly. The difficult part is making sure they all belong to the **same book** and continue to serve the author's original intent.

Common failures include:

| Failure | Result |
|---|---|
| Genre-tag stacking | “Apocalypse + rebirth + system + AI” exists as labels but not as a causal story design |
| Lost author intent | The AI fills gaps too aggressively and gradually designs a different novel |
| Encyclopedic worldbuilding | Lots of lore, little pressure on actual character choices |
| Character-card thinking | Personality and backstory exist, but not the drives and constraints that explain action |
| Author-view leakage | Characters know facts that only the model or author should know |
| Weak conflict | Problems can be solved by one conversation because no real interests or costs are at stake |
| Context decay | Confirmed facts are forgotten or rewritten during final summarization |
| Form-driven creation | The author ends up filling fields rather than making creative decisions |

ZongHeng Book Architect focuses on one job:

> **Turn creative intent into a set of confirmed, causally connected initial conditions that can actually drive a long novel.**

---

## The architecture

```text
What the author truly wants to write
            ↓
What the book promises the reader
            ↓
How the world creates continuous pressure
            ↓
Why characters must make costly choices
            ↓
Which interests / values cannot all be satisfied
            ↓
What irreversible opening event proves the engine works
```

The conversation moves through five stages:

```text
Creative Origin
      ↓
World
      ↓
Characters
      ↓
Conflict Seeds
      ↓
Final Health Gate
```

A later stage does not reinvent earlier decisions. It validates and realizes them.

---

## Embedded Socratic questions

Instead of asking only abstract questions such as:

> What is your theme?  
> What is your protagonist's arc?  
> What is the core world rule?

the Skill uses:

> **confirmed book facts + the real abstract decision + 3–5 concrete options derived from this book**

For a confirmed “apocalypse + rebirth” setup, it may ask:

> What common version of this premise do you most want to avoid?
>
> A. Repeated deaths remove the cost of failure  
> B. Time resets erase consequences  
> C. Rebirth restores power or items for free  
> D. The protagonist keeps making mistakes already known from the previous life
>
> Choose the one you most want to forbid.

The examples are part of the question from the start, not a fallback for a confused author.

As the project develops, examples are generated primarily from:

```text
confirmed facts
→ the author's own latest wording
→ confirmed world / character / relationship / conflict bindings
→ genre-combination knowledge
→ generic model candidates only when necessary
```

The conversation therefore becomes increasingly specific to **this novel**.

---

## What this Skill adds beyond a normal story bible

### Creative origin before content generation

It establishes:

- why the author wants to write the book;
- the intended emotional payoff;
- the core innovation;
- repeatable selling points;
- explicit red lines;
- common versions of the premise the author does not want.

World, character and conflict generation then serves those commitments.

### Genre combinations become narrative functions

Tags are treated as functional promises rather than decorations.

For example:

```text
rebirth → information advantage
apocalypse → continuous resource and order pressure
system → controlled growth feedback
science fiction → technological / energy constraints
changing history → decreasing reliability of future knowledge
```

This lets genre choice directly shape world rules, character advantages, costs and reader payoff.

### Worldbuilding becomes a pressure system

Important world facts should answer:

```text
Who does this constrain?
Who benefits?
What does it cost?
What choice or conflict does it create?
```

The Skill covers rules, geography, resources, factions, professions/powers, disasters and key historical events without turning setup into an encyclopedia.

### Characters become decision engines

Beyond biography, core characters need:

- values and bottom lines;
- desires and fears;
- current motivation;
- abilities and resource limits;
- world bindings;
- relationships that alter choices;
- knowledge boundaries: known / unknown / falsely believed / reasonably suspected;
- an arc direction.

Knowledge boundaries are particularly important for downstream AI generation because characters must not inherit the model's omniscient perspective.

### Conflict must be structurally hard to resolve

Conflict seeds identify:

- who is in conflict;
- which interests or values cannot coexist;
- what is contested;
- what failure costs;
- why a single conversation cannot solve the problem;
- which world and character facts sustain it.

The setup then creates **one opening core plot segment** to prove that the story engine actually works, without prematurely outlining dozens of future chapters.

### Negative constraints are first-class setup data

The final setup records not only what the novel is, but also what it must **not** become.

Examples:

```text
Do not let a reborn protagonist repeat known low-level mistakes without cause.
Do not let a system make the protagonist's core moral choices.
Do not create infinite scarce resources without a source.
Do not let characters know information outside their knowledge boundaries.
Do not change world rules ad hoc to solve plot problems.
```

These constraints are useful in ZongHeng and in any other long-form AI writing environment.

### Stage facts reduce context decay

Each stage ends with a compact fact card containing:

- confirmed facts;
- core causal logic;
- cross-stage bindings;
- negative constraints;
- intentionally deferred questions.

In file-capable environments, a compact `NEW_BOOK_CANON.md` can be maintained as the current working canon.

The final story bible is rebuilt from confirmed facts instead of being re-invented from conversational memory.

### A health gate runs before finalization

The Skill checks:

- setup completeness;
- commercial promise and selling points;
- character health;
- world health;
- character–world–plot consistency;
- negative constraints.

Results are only:

```text
Pass / Improve / Blocker
```

Blockers are repaired before the final setup is generated.

---

## Final output

The output is a portable, human-readable core setup:

```text
Book Core Setup
├─ Basic information
├─ Creative origin
├─ World setup
│  ├─ Rules
│  ├─ Geography
│  ├─ Resources
│  ├─ Factions
│  ├─ Professions / powers / progression
│  ├─ Monsters / disasters / non-personified threats
│  └─ Key historical events
├─ Core characters
├─ Important relationships
├─ Conflict seed pool
├─ Opening core plot segment
├─ Global causal chain
├─ Negative list
└─ Optional optimization suggestions
```

It is deliberately **not** a private database format or JSON contract.

That makes the document portable:

- ZongHeng can use it as new-book initialization material;
- other AI writing tools can use it as a story bible or project knowledge source;
- authors can use it manually as a canonical novel setup.

---

## Role inside ZongHeng Narrative Engine

ZongHeng Narrative Engine is designed around the idea:

> **An AI narrative engine for keeping million-character novels on track.**

ZongHeng Book Architect solves the upstream new-book problem:

> **Before long-form production begins, establish what this book actually is.**

```text
rough idea / character / payoff
              ↓
      ZongHeng Book Architect
intent → genre/payoff → world
→ characters → conflict → health gate
              ↓
       Book Core Setup
          ┌───┴───┐
          ↓       ↓
   ZongHeng     other AI /
   new-book      author
   setup
```

The Skill does not replace ZongHeng's later narrative runtime. Its job is to ensure that the starting material entering that runtime is already author-confirmed, causally connected and useful for story generation.

See [docs/在纵横新书创建中的作用.md](docs/在纵横新书创建中的作用.md).

---

## Quick start

Load the repository's `SKILL.md` into a Skill-capable Agent or as project/system instructions in a strong model.

Then start with as little as:

```text
I want to write an apocalypse rebirth novel.
The protagonist built a huge survivor base in the previous life,
but eventually learned that monsters were not the real cause of civilization's collapse.
I do not want a pure stockpiling power fantasy.
```

The Skill should continue from facts already provided rather than restarting with a form.

A fuller interaction example is available in [docs/交互示例.md](docs/交互示例.md).

---

## Recommended repository layout

```text
.
├─ SKILL.md
├─ README.md
├─ README_EN.md
└─ docs/
   ├─ 在纵横新书创建中的作用.md
   └─ 交互示例.md
```

---

## Summary

> **ZongHeng Book Architect does not mass-generate settings. It turns the author's real creative intent into initial facts that the world, characters and conflicts are required to obey.**
>
> Get the book right once; give every downstream AI a better chance to keep it right.
