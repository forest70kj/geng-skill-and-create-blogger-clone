---
name: geng.skill
description: Use when the user asks for target-creator-method special-effects media or special-effects commentary, piecewise controlled opening/body/ending generation, anti-AI line repair, or near-miss-to-reviewable revision. This draft enforces source retrieval, case-bite extraction, locked-part integrity, hard-ban scanning, human-read anti-AI gates, and user decision gates. Do not impersonate the creator, install this as production, or treat any full_script_good sample as golden.
---

# Controlled Commentary Skill v1 Public Draft

This is a public, anonymized Skill draft. It distills transferable writing methods from user-reviewed assets: workflow, structure, spoken rhythm, scene-to-mechanism mapping, joke mechanics, evidence handling, revision criteria, and self-check gates.

Do not claim to be the creator. Do not copy long source passages. Do not overwrite any private creator Skill. Do not promote assets to golden or run benchmarks unless the user explicitly asks in a later turn.

## Activation Boundary

Use this Skill when the user asks for any of these:

- Controlled commentary using an anonymized target-creator method.
- A piecewise controlled rewrite or generation pass.
- `opening_only`, `body_after_locked_opening`, `ending_only`, or mechanical full assembly.
- Repair of lines that feel like AI analysis.
- Revision of a `near_miss`, `still_ai_analysis`, or source-grounded-but-planlike draft.

Do not use this Skill to impersonate a creator, reproduce source text, run a benchmark, or mark anything golden.

## Source Retrieval Requirement

Never write from vibe alone. Before drafting, collect source-grounded material:

- Case title and target object.
- Concrete scenes, plot actions, named props, characters, opening/ending-theme moments, or lore objects.
- Audience pressure point: returning viewer, new viewer, comment section, toy buyer, waiting viewer, etc.
- 2-3 source-compatible mechanism candidates.
- Known negative constraints and case-specific banned shortcuts.

If the source is missing or too vague, ask for source material or explicitly label the draft as blocked for source retrieval. Source correctness is necessary but not sufficient: a source-grounded draft can still fail if it reads like organized AI analysis.

## Case Bite Extraction

Before prose, create a short internal brief:

```yaml
case_bite_brief:
  main_complaint: ""
  specific_objects: []
  viewer_position: ""
  mechanism_candidates:
    - trigger_scene: ""
      mechanism: ""
      boundary: ""
  forbidden_shortcuts: []
  user_locked_inputs:
    opening: null
    body: null
    ending: null
```

The brief is not final prose. It is a pressure map for writing one controlled segment at a time.

## Mandatory Piecewise Workflow

Full-script generation is not the default. The default workflow is:

```text
source retrieval
-> case bite extraction
-> opening only
-> opening self-check
-> user confirms opening_good or gives micro-edit
-> body only after locked opening
-> body self-check
-> user confirms body_good or gives micro-edit
-> ending only after locked opening + body
-> ending self-check
-> user confirms ending_good or gives micro-edit
-> mechanical full draft assembly
-> locked-part integrity check
-> user confirms or rejects full_script_good
```

If the user explicitly requests unattended generation, still keep section boundaries visible and mark all user gates as pending. Do not silently promote a finished draft.

## Opening-Only Rules

Goal: land the concrete irritation quickly without solving the entire essay.

Required:

- Start from the actual discomfort in this case, not a general review category.
- Name at least one concrete scene, object, promise, opening-theme moment, relationship pressure, or viewer position within 1-2 sentences.
- Use a stance, question, or annoyed judgment instead of neutral setup.
- Let the opening sound like spoken complaint, not a polished outline.
- Stop after the opening and ask for `opening_good`, micro-edit, or reject, unless the user explicitly asked for unattended generation.

Avoid:

- "今天我们来聊聊", broad setup, thesis framing, or "this is worth analyzing".
- Solving the body in the opening.
- Safe scaffold overuse such as repeated "你以为", "其实", "最抽象的是", "离谱", "难评", or "那完了".

Opening self-check:

- Is the discomfort case-specific?
- Is there a named object or visible action?
- Could this opening still work if no body existed yet?
- Does it sound spoken rather than outlined?

## Body After Locked Opening Rules

Inputs:

- Byte-identical locked opening.
- Case bite brief.
- 2-4 selected body pressure points.

Rules:

- Never rewrite the locked opening unless the user asks.
- Each body paragraph must add a new object, action, or audience reaction.
- Mechanism must come after the scene trigger: `scene/object -> why absurd -> audience reaction -> mechanism`.
- Do not use a mechanism label as a replacement for scene evidence.
- Do not pile source nouns as if listing equals humor.
- Keep some spoken unevenness: short interruptions, viewer questions, direct annoyance, and rough mouth-feel are allowed.

Body self-check:

- Is the opening preserved exactly?
- Does every paragraph add a new pressure?
- Could any paragraph apply to many shows by swapping names? If yes, rewrite.
- Is a joke explaining the case, or merely decorating it?
- Does the paragraph sound like a person reacting into a mic, or like a review outline?

## Ending-Only Rules

Inputs:

- Byte-identical locked opening.
- Byte-identical locked body.
- One ending pressure point.

Rules:

- Never rewrite locked opening/body unless the user asks.
- Do not summarize the whole script.
- Do not teach lore or explain legacy settings like a classroom.
- Do not end with a CTA, moral, clean thesis, or "this is why".
- End on a spoken question, demand, or annoyed judgment that tightens the main conflict.

Ending self-check:

- Does it sharpen the central pressure instead of summarizing?
- Does it avoid parallel explanation and lore lesson framing?
- Does it sound like a short mic landing?
- Is the ending specific enough that it cannot be used for a different case?

## Full Assembly Rules

Assembly is mechanical:

```text
locked opening + locked body + locked ending
```

Rules:

- No stealth rewrite.
- No smoothing transitions unless explicitly approved.
- Preserve line breaks unless formatting is broken.
- Check locked-part integrity against snapshots.
- User alone decides whether the result is `full_script_good`.
- Even after `full_script_good`, do not auto-promote to golden, run a benchmark, or replace production.

## Positive Writing Rules From 001 / 002 / 003

Case 001 / 002 / 003 are method summaries only. Use them as workflow evidence, not as text to copy.

Transferable rules:

- Start from concrete irritation. 001 succeeds by exposing unearned relationship payoff; 002 succeeds by exposing an opening theme promise vs episode delivery gap; 003 succeeds by exposing how a new protagonist story gets crowded by legacy-context baggage.
- Use mechanisms only after scenes anchor them. Relationship payoff can become game-affinity logic only after the missing relationship work is visible. Opening-theme hype can become waiting-room or fast-forward pressure only after the promise gap is visible. Legacy context can become returning-viewer/new-viewer pressure only after named objects enter the scene.
- Let each body paragraph add a new pressure. If two paragraphs can swap positions without loss, the body is too generic.
- Keep the voice spoken, not polished. Use questions, interruptions, short reactions, and some roughness. Do not over-smooth logic.
- Treat the comment section and new-viewer position as pressure sites, not generic audience labels.
- Make jokes do explanatory work. A mechanism must clarify the complaint, not merely add flavor.
- End by tightening the conflict, not by summarizing the argument.

## Negative Hard-Ban And Warning Rules

Core failure: `tool PASS / source grounded / source details present` can still fail because the human reads it as organized AI analysis.

Hard-fail or force thought-level rewrite on these families:

- Engineering or programming leakage: abstract load-bearing, wiring, runtime, or system metaphors that make the line sound like a plan instead of a reaction.
- Abstract review language: category labels that could apply to many works after swapping names.
- Case-specific overfit phrasing: repeated private feedback fragments, source-adjacent jokes, or memorable short phrases from internal drafts.
- Flavor-only phrasing: vague "this has that feeling" language that replaces scene evidence.
- Abstract relationship framing: relationship labels without visible actions, objects, or viewer pressure.
- Classroom / legacy-explanation framing: prerequisite-list explanations that teach background instead of landing a story complaint.
- Generic AI writing: ordered essay transitions, broad setup, clean thesis statements, moral endings, or platform-style CTA language.

Warn and inspect manually:

- Clean contrast skeletons that sound too balanced.
- Consecutive three-part analytical parallelism.
- Multiple paragraphs ending in clean summary sentences.
- Unreviewed slang added to otherwise polished analysis.
- Repeated safe scaffolds that become a formula instead of a reaction.

Rewrite principle:

```text
abstract mechanism -> concrete viewer reaction
abstract metaphor -> spoken judgment
analysis noun -> visible story action
classroom explanation -> confused audience question
source-term pileup -> one memorable scene pressure
summary ending -> annoyed spoken landing
```

Do not synonym-replace banned phrasing. Rewrite the thought.

## Human-Read Anti-AI Gate

Before showing a draft, ask:

- Is this a spoken complaint or organized analysis?
- Are source details wrapped in clean AI sentence structure?
- Are paragraphs too symmetrical?
- Does the ending summarize?
- Could this line appear in a generic review?
- Does the draft feel like "AI learned surface markers"?

If yes, fail and rewrite before user review. Tool pass is not human pass.

## Case Specificity Gate

For every paragraph, identify:

- Concrete story object or action.
- Viewer reaction.
- Mechanism, if present.
- Reason this paragraph must appear in this case and not another.

If any paragraph lacks a concrete object/action or can be reused by swapping names, rewrite.

## Mechanism Grounding Gate

Every meme or mechanism must include:

- Trigger scene.
- Target of the joke.
- Why the mechanism explains the complaint.
- Boundary preventing misuse.

If a mechanism appears before the scene, move or rewrite it. If the mechanism is ungrounded, delete it.

## Locked-Part Integrity Gate

During body, ending, and assembly:

- Opening remains byte-identical once locked.
- Body remains byte-identical once locked.
- Ending is inserted exactly as confirmed.
- Full draft is assembled, not reauthored.

If a locked part changes accidentally, report the integrity failure and restore the locked text before continuing.

## User Decision Gate

Only the user can mark:

- `opening_good`
- `body_good`
- `ending_good`
- `full_script_good`
- any golden status
- benchmark permission
- production replacement permission

Default state for all generated drafts is pending review.

## Output Format For Review Packets

Use this structure when returning a candidate:

```markdown
## Review Packet

- scope: opening_only | body_after_locked_opening | ending_only | full_assembly
- case_id:
- locked_inputs_used:
- source_retrieval_status:
- user_decision_needed:

### Case Bite Brief
[short brief, not final prose]

### Candidate Text
[draft segment only]

### Self Check
- hard_ban_hits:
- warning_patterns:
- human_read_risk: low | medium | high
- case_specificity:
- mechanism_grounding:
- locked_part_integrity:

### User Options
- approve as opening_good/body_good/ending_good/full_script_good
- request micro-edit
- reject and regenerate from a named pressure point
```

Do not hide uncertainty. If the draft is near-miss, label it as near-miss.

