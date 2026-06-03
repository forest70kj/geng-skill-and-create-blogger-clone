# Practical Example: Obsidian-Assisted Drafting / Obsidian 辅助写作示例

This example shows how to pair `geng.skill` with a small Obsidian knowledge set.

这个例子展示：怎么把 `geng.skill` 和少量 Obsidian 梗库 / 段子库 / 负面规则搭配起来。

Do not give the Skill your entire vault. Select a small number of relevant notes.

不要把整个 vault 一次性塞给 Skill。每次只选少量相关 notes。

## Example Obsidian Notes / 示例 Obsidian 笔记

```text
/path/to/ObsidianVault/memes/waiting-room-pressure.md
/path/to/ObsidianVault/jokes/object-pressure-jokes.md
/path/to/ObsidianVault/negative-rules/ai-analysis-smell.md
```

## User Prompt / 用户提示词

```text
Use geng.skill.

Before writing, reference these Obsidian notes:
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/jokes/object-pressure-jokes.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use the notes as reusable mechanics, not as text to copy.
After drafting, explain which note influenced which choice.

Generate opening_only for this case:

Topic / 选题:
- A fictional hero episode where a dramatic rival entrance gets delayed by rule cards, training equipment, and scoreboard setup.
- 一个虚构英雄剧集：rival 登场很有气势，但剧情被 rule cards、training equipment 和 scoreboard setup 拖住了。

Source notes / 材料摘要:
- Rival entrance appears in the first scene.
- 第一场戏就出现 rival entrance。
- The episode cuts away to explain rule cards.
- 剧集切去解释 rule cards。
- The protagonist trains with a device instead of confronting the rival.
- 主角用 device 训练，而不是直接面对 rival。
- The scoreboard appears twice.
- scoreboard 出现两次。
- The ending teases the confrontation again.
- 结尾又 tease confrontation。

Main complaint / 核心吐槽:
- The story keeps telling the viewer the rivalry matters, but the actual rivalry does not move yet.
- 故事一直说宿敌线很重要，但真正的宿敌线并没有推进。

Audience position / 观众位置:
- returning viewer
- 老观众

Stop after opening candidates.
```

## Expected Skill Behavior / 预期 Skill 行为

The Skill should:

Skill 应该：

- read or use the selected notes / 读取或使用所选 notes
- extract a case bite brief / 提炼 case bite brief
- map each note to a writing mechanic / 把每条 note 映射到写作机制
- generate only opening candidates / 只生成 opening candidates
- explain note influence without copying note text / 说明 note 影响，但不复制 note 原文
- stop for review / 停下来等 review

## Expected Note Influence Summary / 预期 Note Influence Summary

```text
Note influence:
- waiting-room-pressure.md: used to frame the viewer as waiting for the promised clash.
- object-pressure-jokes.md: used rule cards, training device, and scoreboard as concrete delay objects.
- ai-analysis-smell.md: used to avoid abstract lines like "the pacing undermines the narrative stakes."

Note 影响说明:
- waiting-room-pressure.md: 用来把观众位置写成“在等 promised clash”。
- object-pressure-jokes.md: 用 rule cards、training device、scoreboard 这些具体物件解释 delay。
- ai-analysis-smell.md: 用来避开 "the pacing undermines the narrative stakes" 这种抽象分析句。
```

## Review Checklist / 审稿清单

After the Skill responds, ask:

拿到 Skill 输出后，检查：

- Did it copy the Obsidian note, or use the mechanic? / 它是在复制 note，还是在使用机制？
- Is every joke tied to a source object? / 每个梗有没有绑定 source object？
- Does the opening sound like a person reacting? / 开头像不像人在反应？
- Did it avoid generic analysis language? / 有没有避开泛泛分析腔？
- Did it stop before writing the body? / 有没有在写正文前停下来？
