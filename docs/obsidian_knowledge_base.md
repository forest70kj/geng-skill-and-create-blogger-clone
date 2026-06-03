# Obsidian Knowledge Base Setup

This guide explains the recommended companion setup for using these Skills with an Obsidian vault.

The goal is to reduce generic AI writing by giving the Skill a local bank of reusable joke mechanics, meme structures, analogy patterns, case-bite templates, and negative rules.

## Why Use Obsidian

AI drafts often feel mechanical when the model has to invent everything at once:

- topic understanding
- structure
- jokes
- analogy
- rhythm
- anti-AI cleanup

An Obsidian vault lets you separate taste from generation. You collect the patterns you actually like, then ask the Skill to reference a small relevant subset while writing.

The Skill should not copy your notes as final prose. It should use them as reusable mechanics.

## Suggested Vault Structure

```text
ObsidianVault/
  00-index/
    meme-bank-index.md
    joke-pattern-index.md
    negative-rule-index.md

  jokes/
    reversal-jokes.md
    audience-complaint-jokes.md
    object-pressure-jokes.md
    escalation-jokes.md

  memes/
    waiting-room-pressure.md
    relationship-meter.md
    task-overload.md
    fake-choice.md

  analogies/
    game-ui-analogies.md
    workplace-analogies.md
    shopping-analogies.md
    classroom-analogies.md

  case-bites/
    case-template.md
    opening-pressure-template.md
    body-pressure-template.md

  negative-rules/
    ai-analysis-smell.md
    banned-clean-thesis-endings.md
    generic-review-language.md
    over-polished-transitions.md
```

## Note Template

Use one note per reusable pattern.

```markdown
---
type: joke_pattern
tags: [commentary, opening, audience-pressure]
status: reusable
risk: low
---

# Pattern Name

## What It Does

Explain the mechanism in plain language.

## When To Use

Describe the kind of topic, scene, or audience pressure where it fits.

## Example Shape

Use a short anonymized structure.

## Do Not Use When

List failure cases.

## Related Notes

- [[another-pattern]]
```

## Good Knowledge Base Entries

Good entries are reusable and mechanical:

```markdown
# Waiting Room Pressure

## What It Does

Turns a delayed payoff into the feeling that the viewer is stuck waiting for the story to start.

## When To Use

Use when the episode promises movement but spends most of its time on setup, repetition, or prerequisite explanation.

## Example Shape

"The opening makes you think the story is about to move, but the episode keeps handing you another queue number."

## Do Not Use When

Do not use when the actual complaint is emotional payoff, not delay.
```

Bad entries are copied catchphrases, long private paragraphs, or source text pasted without permission.

## How To Prompt Codex

Give the Skill a small set of relevant notes:

```text
Use geng.skill.

Reference these Obsidian notes before drafting:
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/jokes/audience-complaint-jokes.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use the notes as reusable mechanics, not as text to copy.

Generate opening_only for this case:
[paste source notes or give source file paths]

After drafting, explain which note influenced which choice.
```

If the assistant cannot access your local vault path, paste the relevant notes into the chat or export them into a small working folder.

## Recommended Workflow

```text
choose topic
-> collect source notes
-> select 3 to 8 Obsidian pattern notes
-> run case bite extraction
-> generate opening_only
-> review and micro-edit
-> lock opening
-> generate body_after_locked_opening
-> review and micro-edit
-> lock body
-> generate ending_only
-> assemble final draft
```

## Review Questions

After the Skill writes, check:

- Which note influenced this line?
- Did the Skill copy text, or use the mechanism?
- Is the joke tied to a concrete scene?
- Is the paragraph still understandable without the note?
- Does the output sound like a person reacting, or like a plan?

## Maintenance Tips

- Add notes after real writing sessions, not only before them.
- Keep short "do not use when" sections.
- Tag notes by pressure type, not only topic.
- Keep private examples private.
- Move weak patterns into `negative-rules/`.
- Prefer 100 small reusable notes over 5 huge essays.

## Safety Boundary

The Obsidian vault can contain your private working material, but public Skill packages should not.

Before publishing anything derived from your vault, remove:

- private transcripts
- copied creator passages
- creator names or channel names without permission
- local file paths
- account names
- API keys
- tokens
- long examples that can identify the source
