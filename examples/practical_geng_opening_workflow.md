# Practical Example: `geng.skill` Opening Workflow

This example shows how to use `geng.skill` without asking it to write a full draft too early.

The case is fictional and anonymized.

## User Prompt

```text
Use geng.skill.

I want an opening_only pass.

Topic:
- A transformation-hero episode where the story promises a major rivalry, but most of the episode is spent explaining rules and showing setup objects.

Source notes:
- The episode starts with the rival entering dramatically.
- The opening scene suggests a direct clash.
- Instead of a clash, the episode introduces three rule cards, a training device, and a scoreboard.
- The protagonist reacts like the rivalry matters, but the viewer has not seen enough action yet.
- The ending teases the same clash again.

Main complaint:
- The episode keeps promising motion but turns the viewer into someone waiting for the real story to start.

Audience position:
- A returning viewer who expected the rivalry to finally move.

Optional reference mechanics:
- waiting-room pressure
- scoreboard joke
- object-pressure joke

Before writing, create a case bite brief.
Then generate only opening candidates.
Stop before writing the body.
```

## Expected Case Bite Brief Shape

```yaml
case_bite_brief:
  main_complaint: "The episode promises a rivalry but delays the actual clash."
  specific_objects:
    - rule cards
    - training device
    - scoreboard
  viewer_position: "returning viewer waiting for the rivalry to move"
  mechanism_candidates:
    - trigger_scene: "dramatic rival entrance"
      mechanism: "waiting-room pressure"
      boundary: "use only if the episode delays action after promising action"
    - trigger_scene: "scoreboard and rule cards"
      mechanism: "object-pressure joke"
      boundary: "use objects to explain delay, not as a random noun list"
  forbidden_shortcuts:
    - generic pacing critique
    - clean thesis ending
    - full body generation before approval
```

## Expected Output Shape

The Skill should produce a review packet, not a finished article:

```markdown
## Review Packet

- scope: opening_only
- source_retrieval_status: source_notes_provided
- user_decision_needed: approve / micro-edit / reject

### Candidate Text

Candidate A:
[short opening]

Candidate B:
[short opening]

Candidate C:
[short opening]

### Self Check

- hard_ban_hits: none
- human_read_risk: low | medium | high
- case_specificity: pass | fail
- mechanism_grounding: pass | fail
```

## Good User Review Responses

Approve one:

```text
opening_good: Candidate B
```

Give a micro-edit:

```text
usable_but_needs_micro_edit:
Candidate A still sounds like pacing analysis.
Push it toward this pressure:
"The rival walks in like the episode is finally starting, but then the story hands the viewer rule cards and a scoreboard."
```

Reject with a pressure point:

```text
reject:
The opening is too abstract. Regenerate from the scoreboard and waiting-room pressure.
```

## Why This Works

The Skill is forced to:

- ground itself in source notes
- name concrete objects
- generate only the opening
- wait for user judgment
- learn from micro-edits before continuing
