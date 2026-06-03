# Practical Example: `geng.skill` Opening Workflow / 开头工作流示例

This example shows how to use `geng.skill` without asking it to write a full draft too early.

这个例子展示：如何让 `geng.skill` 先写 opening_only，而不是太早写完整稿。

The case is fictional and anonymized.

下面的 case 是虚构且匿名化的。

## User Prompt / 用户提示词

```text
Use geng.skill.

I want an opening_only pass.

Topic / 选题:
- A transformation-hero episode where the story promises a major rivalry, but most of the episode is spent explaining rules and showing setup objects.
- 一个变身英雄类剧集：故事承诺要展开重要宿敌线，但大部分篇幅都在解释规则和展示设定物件。

Source notes / 材料摘要:
- The episode starts with the rival entering dramatically.
- 开头让 rival 很戏剧性地登场。
- The opening scene suggests a direct clash.
- 第一场戏暗示马上要正面对抗。
- Instead of a clash, the episode introduces three rule cards, a training device, and a scoreboard.
- 但没有直接打起来，反而开始介绍三张 rule cards、一个 training device 和一个 scoreboard。
- The protagonist reacts like the rivalry matters, but the viewer has not seen enough action yet.
- 主角表现得像这条宿敌线很重要，但观众还没看到足够动作。
- The ending teases the same clash again.
- 结尾又 tease 了一次同样的对抗。

Main complaint / 核心吐槽:
- The episode keeps promising motion but turns the viewer into someone waiting for the real story to start.
- 它一直承诺要动起来，但观众像是在等真正的故事开始。

Audience position / 观众位置:
- A returning viewer who expected the rivalry to finally move.
- 一个以为宿敌线终于要推进的老观众。

Optional reference mechanics / 可参考机制:
- waiting-room pressure
- scoreboard joke
- object-pressure joke

Before writing, create a case bite brief.
Then generate only opening candidates.
Stop before writing the body.
```

## Expected Case Bite Brief Shape / 预期 Case Bite

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

## Expected Output Shape / 预期输出结构

The Skill should produce a review packet, not a finished article.

Skill 应该输出 review packet，而不是完整文章。

```markdown
## Review Packet

- scope: opening_only
- source_retrieval_status: source_notes_provided
- user_decision_needed: approve / micro-edit / reject

### Candidate Text

Candidate A:
[short opening / 短开头]

Candidate B:
[short opening / 短开头]

Candidate C:
[short opening / 短开头]

### Self Check

- hard_ban_hits: none
- human_read_risk: low | medium | high
- case_specificity: pass | fail
- mechanism_grounding: pass | fail
```

## Good User Review Responses / 好的用户反馈

Approve one / 认可其中一个：

```text
opening_good: Candidate B
```

Give a micro-edit / 给一个小修改：

```text
usable_but_needs_micro_edit:
Candidate A still sounds like pacing analysis.
Push it toward this pressure:
"The rival walks in like the episode is finally starting, but then the story hands the viewer rule cards and a scoreboard."

Candidate A 还是太像节奏分析。
往这个压力改：
"宿敌一登场像是这集终于要开始了，结果故事转头给观众发 rule cards 和 scoreboard。"
```

Reject with a pressure point / 带着压力点拒绝：

```text
reject:
The opening is too abstract. Regenerate from the scoreboard and waiting-room pressure.

这个开头太抽象。请从 scoreboard 和 waiting-room pressure 重新生成。
```

## Why This Works / 为什么这样有效

The Skill is forced to:

这样会强制 Skill：

- ground itself in source notes / 基于材料，而不是凭空写
- name concrete objects / 说出具体物件
- generate only the opening / 只生成开头
- wait for user judgment / 等用户判断
- learn from micro-edits before continuing / 先从小修改里学习，再继续写
