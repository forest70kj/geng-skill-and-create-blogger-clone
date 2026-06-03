# Practical Example: Obsidian-Assisted Drafting

This example shows how to pair `geng.skill` with a small Obsidian knowledge set.

Do not give the Skill your entire vault. Select a small number of relevant notes.

## Example Obsidian Notes

```text
/path/to/ObsidianVault/memes/waiting-room-pressure.md
/path/to/ObsidianVault/jokes/object-pressure-jokes.md
/path/to/ObsidianVault/negative-rules/ai-analysis-smell.md
```

## User Prompt

```text
Use geng.skill.

Before writing, reference these Obsidian notes:
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/jokes/object-pressure-jokes.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use the notes as reusable mechanics, not as text to copy.
After drafting, explain which note influenced which choice.

Generate opening_only for this case:

Topic:
- A fictional hero episode where a dramatic rival entrance gets delayed by rule cards, training equipment, and scoreboard setup.

Source notes:
- Rival entrance appears in the first scene.
- The episode cuts away to explain rule cards.
- The protagonist trains with a device instead of confronting the rival.
- The scoreboard appears twice.
- The ending teases the confrontation again.

Main complaint:
- The story keeps telling the viewer the rivalry matters, but the actual rivalry does not move yet.

Audience position:
- returning viewer

Stop after opening candidates.
```

## Expected Skill Behavior

The Skill should:

- read or use the selected notes
- extract a case bite brief
- map each note to a writing mechanic
- generate only opening candidates
- explain note influence without copying note text
- stop for review

## Expected Note Influence Summary

```text
Note influence:
- waiting-room-pressure.md: used to frame the viewer as waiting for the promised clash.
- object-pressure-jokes.md: used rule cards, training device, and scoreboard as concrete delay objects.
- ai-analysis-smell.md: used to avoid abstract lines like "the pacing undermines the narrative stakes."
```

## Review Checklist

After the Skill responds, ask:

- Did it copy the Obsidian note, or use the mechanic?
- Is every joke tied to a source object?
- Does the opening sound like a person reacting?
- Did it avoid generic analysis language?
- Did it stop before writing the body?
