# Obsidian Knowledge Base Setup / Obsidian 知识库搭建

This guide explains the recommended companion setup for using these Skills with an Obsidian vault.

这份指南讲的是：怎么把这些 Skills 和 Obsidian vault 搭配起来，减少 AI 写作的机械感。

## Why Use Obsidian / 为什么要用 Obsidian

AI drafts often feel mechanical when the model has to invent everything at once:

AI 一次性同时处理这些事时，很容易写得机械：

- topic understanding / 理解选题
- structure / 组织结构
- jokes / 写段子
- analogy / 做类比
- rhythm / 控节奏
- anti-AI cleanup / 去 AI 味

An Obsidian vault lets you separate taste from generation.

Obsidian 的作用是把“审美”和“生成”分开。你把自己喜欢的 jokes、memes、analogies、negative rules 长期沉淀下来；写作时只给 Skill 相关的一小组笔记，让它参考机制，而不是临场硬编。

The Skill should not copy your notes as final prose. It should use them as reusable mechanics.

重点：Skill 不应该复制你的笔记原文。它应该使用其中的 mechanism / pattern / boundary。

## Suggested Vault Structure / 推荐目录结构

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

你不需要一开始就建完整。可以先从三个文件夹开始：

```text
jokes/
memes/
negative-rules/
```

## Note Template / 笔记模板

Use one note per reusable pattern.

一个可复用 pattern 单独写一条 note：

```markdown
---
type: joke_pattern
tags: [commentary, opening, audience-pressure]
status: reusable
risk: low
---

# Pattern Name / 模式名

## What It Does / 它在做什么

Explain the mechanism in plain language.
用普通话解释机制。

## When To Use / 什么时候用

Describe the topic, scene, or audience pressure where it fits.
说明它适合什么选题、场景或观众压力。

## Example Shape / 示例骨架

Use a short anonymized structure.
写一个短的匿名化结构。

## Do Not Use When / 不适合什么时候用

List failure cases.
写清楚边界和失败场景。

## Related Notes / 相关笔记

- [[another-pattern]]
```

## Good Knowledge Base Entries / 好笔记长什么样

Good entries are reusable and mechanical.

好的条目不是“漂亮句子库”，而是“机制库”。

```markdown
# Waiting Room Pressure / 等候室压力

## What It Does / 它在做什么

Turns a delayed payoff into the feeling that the viewer is stuck waiting for the story to start.
把“迟迟不给兑现”的观感，转成“观众像在等故事真正开始”的压力。

## When To Use / 什么时候用

Use when the episode promises movement but spends most of its time on setup, repetition, or prerequisite explanation.
适合那种开头承诺要动起来，但正片大部分时间都在解释规则、铺设定、重复等待的情况。

## Example Shape / 示例骨架

"The opening makes you think the story is about to move, but the episode keeps handing you another queue number."

## Do Not Use When / 不适合什么时候用

Do not use when the actual complaint is emotional payoff, not delay.
如果真正问题是情感兑现太快，而不是拖延，就不要用。
```

Bad entries are copied catchphrases, long private paragraphs, or source text pasted without permission.

坏条目通常是：复制来的口头禅、长篇私人原文、未经授权的 source text。公开发布时尤其要避免。

## How To Prompt Codex / 怎么提示 Codex

Give the Skill a small set of relevant notes:

每次只给少量相关 notes：

```text
Use geng.skill.

Reference these Obsidian notes before drafting:
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/jokes/audience-complaint-jokes.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use the notes as reusable mechanics, not as text to copy.

Generate opening_only for this case:
[paste source notes or give source file paths / 粘贴材料摘要或给文件路径]

After drafting, explain which note influenced which choice.
```

If the assistant cannot access your local vault path, paste the relevant notes into the chat or export them into a small working folder.

如果 Codex 访问不了你的本地路径，就把相关 notes 粘贴进对话，或者导出到一个小的 working folder。

## Recommended Workflow / 推荐流程

```text
choose topic / 选题
-> collect source notes / 收集材料
-> select 3 to 8 Obsidian pattern notes / 选 3 到 8 条 Obsidian pattern notes
-> run case bite extraction / 提炼 case bite
-> generate opening_only / 只生成开头
-> review and micro-edit / 审稿和小改
-> lock opening / 锁定开头
-> generate body_after_locked_opening / 基于锁定开头写正文
-> review and micro-edit / 审稿和小改
-> lock body / 锁定正文
-> generate ending_only / 只写结尾
-> assemble final draft / 机械组装完整稿
```

## Review Questions / 审稿问题

After the Skill writes, check:

拿到草稿后检查：

- Which note influenced this line? / 这句话受哪条 note 影响？
- Did the Skill copy text, or use the mechanism? / 它是在复制文字，还是在用机制？
- Is the joke tied to a concrete scene? / 这个梗有没有绑定具体场景？
- Is the paragraph still understandable without the note? / 不看笔记还能看懂吗？
- Does the output sound like a person reacting, or like a plan? / 像人在反应，还是像计划书？

## Maintenance Tips / 维护建议

- Add notes after real writing sessions, not only before them. / 写完真实稿子后补充 notes，不要只在写之前建库。
- Keep short "do not use when" sections. / 每条 note 都写清楚什么时候不能用。
- Tag notes by pressure type, not only topic. / 标签按压力类型打，不只按题材打。
- Keep private examples private. / 私人样本不要公开。
- Move weak patterns into `negative-rules/`. / 弱 pattern 移到负面规则里。
- Prefer 100 small reusable notes over 5 huge essays. / 100 条小笔记通常比 5 篇大长文更好用。

## Safety Boundary / 安全边界

The Obsidian vault can contain your private working material, but public Skill packages should not.

你的 Obsidian vault 可以有私人工作材料，但公开 Skill package 不应该有。

Before publishing anything derived from your vault, remove:

公开发布前，删除：

- private transcripts / 私人转录稿
- copied creator passages / 复制来的创作者段落
- creator names or channel names without permission / 未授权的创作者名和频道名
- local file paths / 本地路径
- account names / 账号名
- API keys / API key
- tokens / token
- long examples that can identify the source / 能识别来源的长示例
