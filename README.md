# geng-skill-and-create-blogger-clone

Two public, anonymized Codex writing workflow Skills:

- `geng.skill`
- `create-blogger-clone-v2`

This repository is for people who want a controlled way to write commentary-style drafts with source grounding, staged review, micro-edits, and anti-AI self-checks.

It is not a private corpus dump. It does not include creator transcripts, channel names, proprietary sample scripts, local paths, API keys, tokens, or private generated archives.

## What This Is

This package gives you reusable Skill workflows for:

- turning source material into a short "case bite" before drafting
- generating only one section at a time, such as opening, body, or ending
- keeping user-approved sections locked and byte-identical
- using user micro-edits to improve future drafts
- checking whether the output sounds like human commentary or clean AI analysis
- exporting anonymized, reviewable creator-style workflow packages

The focus is transferable writing method: structure, rhythm, joke mechanics, evidence handling, revision criteria, and review gates.

## What This Is Not

This repository is not for:

- impersonating a creator
- copying long source passages
- publishing private transcripts
- bypassing user review
- automatically generating finished scripts without checkpoints
- treating any sample as golden by default
- replacing human judgment with benchmark scores

## Included Skills

| Skill | Use It For |
| --- | --- |
| `geng.skill` | Controlled commentary writing with source retrieval, case-bite extraction, opening/body/ending staging, locked-part integrity, and human-read anti-AI checks. |
| `create-blogger-clone-v2` | Building anonymized creator-specific writing workflow Skills from user-owned or licensed examples, staged review, micro-edits, and release scans. |

## Repository Layout

```text
geng.skill/
  SKILL.md
  skill.json

create-blogger-clone-v2/
  SKILL.md
  skill.json
  templates/

docs/
  anonymization_policy.md
  obsidian_knowledge_base.md
  safety_and_scope.md
  workflow_overview.md

examples/
  anonymized_case_bite.md
  anonymized_micro_edit_packet.md
  anonymized_review_packet.md
```

## Installation

Clone or download this repository:

```bash
git clone https://github.com/forest70kj/geng-skill-and-create-blogger-clone.git
cd geng-skill-and-create-blogger-clone
```

Copy the Skill folder you want into your Codex skills directory:

```bash
cp -R geng.skill ~/.codex/skills/
cp -R create-blogger-clone-v2 ~/.codex/skills/
```

Then start a new Codex session and call the Skill by name.

If your Codex setup uses a different custom skills folder, copy the Skill folder there instead. The important part is that each folder keeps its own `SKILL.md` and `skill.json`.

## Quick Start: Use `geng.skill`

Use `geng.skill` when you already know the topic or source object and want to generate a controlled commentary draft.

Example prompt:

```text
Use geng.skill.

I want an opening_only pass for this case:
- topic: [your topic]
- source notes: [paste short source notes or give local file paths]
- main complaint: [what feels wrong, funny, confusing, or worth attacking]
- audience position: [new viewer, returning viewer, fan, buyer, comment section, etc.]

Before writing, create a case bite brief.
Then generate only opening candidates.
Stop and wait for my review before writing the body.
```

Expected output:

```text
case bite brief
-> opening candidates
-> self-check
-> user decision gate
```

You should then reply with one of these:

```text
opening_good
usable_but_needs_micro_edit: [your edit]
reject: [why]
```

The Skill should not move to the body until the opening is approved or revised.

## Quick Start: Use `create-blogger-clone-v2`

Use `create-blogger-clone-v2` when you want to build a new writing workflow Skill from examples that you own, control, or have permission to use.

Example prompt:

```text
Use create-blogger-clone-v2.

I want to build a new anonymized writing Skill from my own examples.
First help me register sources, split an eval set, and extract transferable methods.
Do not include private source text in any public package.
```

Expected workflow:

```text
source registration
-> source cleaning
-> evaluation split
-> method extraction
-> staged candidate generation
-> micro-edit learning
-> safety scan
-> reviewable package export
```

## Default Writing Workflow

The default workflow is intentionally staged:

```text
source retrieval
-> case bite extraction
-> opening only
-> user review / micro edit
-> locked opening
-> body only
-> user review / micro edit
-> locked body
-> ending only
-> user review / micro edit
-> locked ending
-> full draft assembly
-> final user decision
```

Full-script generation is not the default. This is deliberate. Staging makes it easier to catch generic AI phrasing before it infects the whole draft.

## Author's View: Pair This With an Obsidian Knowledge Base

My recommended setup is to use these Skills together with an Obsidian vault.

The idea is simple: build a large local knowledge base of jokes, memes, analogies, reusable complaint structures, scene-pressure patterns, and negative examples. When you use the Skill to write an article or script, ask it to reference the relevant Obsidian notes while drafting.

This can greatly reduce the mechanical feeling of AI writing. Instead of asking the model to invent flavor from nothing, you give it a living bank of concrete joke mechanics and reusable patterns. The Skill still has to write a new draft, but it can lean on your own curated taste.

Suggested Obsidian layout:

```text
ObsidianVault/
  00-index/
    meme-bank-index.md
    joke-pattern-index.md
  jokes/
    reversal-jokes.md
    audience-complaint-jokes.md
    object-pressure-jokes.md
  memes/
    waiting-room-pressure.md
    relationship-meter.md
    task-overload.md
  analogies/
    game-ui-analogies.md
    workplace-analogies.md
    shopping-analogies.md
  case-bites/
    case-template.md
  negative-rules/
    ai-analysis-smell.md
    banned-clean-thesis-endings.md
```

Useful note format:

```markdown
---
type: joke_pattern
tags: [commentary, opening, audience-pressure]
status: reusable
risk: low
---

# Pattern Name

## What It Does

Explain the joke or meme mechanism in plain language.

## When To Use

Describe the kind of scene, topic, or audience pressure where this pattern fits.

## Example Shape

Use a short anonymized structure, not a copied private paragraph.

## Do Not Use When

List boundaries and failure cases.
```

Prompt example:

```text
Use geng.skill.

Before writing, reference these Obsidian notes:
- /path/to/ObsidianVault/jokes/audience-complaint-jokes.md
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use them as reusable mechanics, not as text to copy.
Generate opening_only for this case:
[your source notes]
```

Best practice: do not dump your whole vault into one prompt. Give the Skill a small, relevant set of notes, usually 3 to 8 files. Ask it to explain which note influenced which draft choice.

For a deeper setup guide, see [`docs/obsidian_knowledge_base.md`](docs/obsidian_knowledge_base.md).

## How To Review Output

When the Skill gives you a draft, do not only ask whether the facts are correct. Also ask:

- Does it sound like a person reacting, or like an organized essay?
- Is the first paragraph case-specific?
- Does every paragraph add a new pressure?
- Are jokes explaining the complaint, or just decorating it?
- Did the ending summarize too cleanly?
- Could this paragraph work for another topic by swapping names?

If something feels AI-written, give a micro-edit:

```text
This line is too analytical:
"The relationship arc lacks sufficient buildup."

Rewrite toward this pressure:
"The relationship meter is not even full, but the story already throws the special ending image at the viewer."
```

The useful lesson is not the exact sentence. The useful lesson is: concrete mechanism beats abstract critique.

## Public Release Safety

Before publishing a Skill package made with this workflow:

- remove private transcripts
- remove creator names and channel names unless you have permission
- remove long recognizable source passages
- remove local paths, account names, API keys, and tokens
- keep examples short and anonymized
- run a sensitive-content scan
- keep user review gates visible

This repository's public release scan is included in:

```text
PUBLIC_RELEASE_SENSITIVE_SCAN.md
PUBLIC_RELEASE_SENSITIVE_SCAN.json
```

## License

MIT License.
