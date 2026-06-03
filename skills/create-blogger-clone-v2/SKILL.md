---
name: create-blogger-clone-v2
description: Build anonymized, creator-specific writing workflow Skills from user-owned or licensed examples. Use staged intake, source registration, micro-edit learning, safety checks, and user review gates. Do not include private corpus text in the public Skill.
---

# create-blogger-clone-v2 Public Workflow Skill

This Skill is a reusable workflow for building creator-style writing assistants from examples the user owns, controls, or has permission to use. The public package contains process, templates, and review criteria only. It does not contain any third-party creator corpus.

## Scope

Use this Skill when the user wants to:

- create a creator-specific writing Skill from provided examples
- register and clean source material
- extract transferable writing methods
- build staged generation packets
- learn from user micro-edits
- export a reviewable Skill package

Do not use this Skill to impersonate a creator, publish private transcripts, copy long samples, bypass user review, run benchmarks by default, or automatically promote output into a golden set.

## Source Governance

Keep source handling explicit:

- Put user-provided raw material in a private source area.
- Register every source before analysis.
- Separate evaluation examples before training.
- Keep cleaned working copies separate from raw material.
- Never include raw source text in a public package.
- Export only method summaries, schemas, templates, and short anonymized examples.

## Distillation Targets

Extract transferable methods rather than identity markers:

- structure and section order
- opening pressure patterns
- evidence handling
- joke or analogy mechanics
- pacing and rhythm rules
- negative patterns and rewrite criteria
- review packet format
- user decision gates

Avoid creator names, channel names, exact catchphrases, private samples, and long recognizable passages.

## Workflow

```text
project initialization
-> source registration
-> source cleaning and segmentation
-> holdout evaluation split
-> method extraction
-> draft Skill generation
-> staged candidate generation
-> user micro-edit ingestion
-> negative-rule update
-> safety scan
-> reviewable package export
```

## Staged Generation Contract

Full-script generation is not the default. Prefer:

```text
source retrieval
-> case bite extraction
-> opening only
-> user decision
-> body only after locked opening
-> user decision
-> ending only after locked opening/body
-> user decision
-> mechanical assembly
-> final user decision
```

A locked section must remain byte-identical unless the user explicitly edits it.

## Review Packet

Every candidate should include:

```yaml
scope: opening_only | body_after_locked_opening | ending_only | full_assembly
source_status: registered | missing | insufficient
locked_inputs_used: []
candidate_text: ""
self_check:
  source_grounding: pass | fail
  long_source_overlap: pass | fail
  human_read_risk: low | medium | high
  private_identifier_risk: low | medium | high
user_decision_needed:
  - approve
  - request_micro_edit
  - reject
```

## Micro-Edit Learning

Treat user edits as small, reviewable rules:

- capture the original candidate line
- capture the user replacement
- infer the transferable lesson
- add a negative rule only when the failure repeats
- do not copy the user's long passage into public docs

## Release Rules

Before exporting a public Skill package:

- remove creator names and channel names
- remove raw transcripts and long examples
- replace concrete IP names with generic labels
- remove local paths and private IDs
- scan for API keys and tokens
- keep MIT license notices separate from third-party source material

