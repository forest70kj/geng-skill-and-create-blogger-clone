# geng-skill-and-create-blogger-clone

两个公开、匿名化的 Codex 写作 workflow Skills:

- `geng.skill`
- `create-blogger-clone-v2`

This repo is for people who want controlled commentary-style writing with source grounding, staged review, micro-edits, and anti-AI self-checks.

简单说：它不是让 AI 一口气写完整文章，而是让 AI 先读材料、先提炼 case bite，再一段一段写，用户每一步都可以 review / micro-edit / lock。

## What This Is / 这是什么

这个 package 提供的是可复用的 Skill workflow，核心能力包括：

- source retrieval: 先找材料，不凭感觉写
- case bite extraction: 写之前先提炼这个选题真正的冲突点
- opening/body/ending staging: 开头、正文、结尾分段生成
- locked-part integrity: 用户确认过的部分不偷偷改
- micro-edit learning: 用户的小修改会变成下一轮写作规则
- human-read anti-AI gate: 检查它是不是又写成了干净但机械的 AI 分析
- reviewable export: 可以导出匿名化、可检查的 Skill package

The focus is transferable writing method: structure, rhythm, joke mechanics, evidence handling, revision criteria, and review gates.

重点不是“模仿某个人”，而是抽取可以迁移的写作方法：结构、节奏、梗的机制、证据怎么用、怎么改稿、怎么判断不像 AI。

## What This Is Not / 这不是什么

这个仓库不用于：

- impersonating a creator / 冒充某个创作者
- copying long source passages / 复制长篇原文
- publishing private transcripts / 发布私人转录稿
- bypassing user review / 绕过用户审稿
- one-shot full-script generation / 默认一口气生成完整稿
- treating samples as golden by default / 默认把样本当 golden
- replacing human judgment with benchmark scores / 用分数替代人的判断

It is not a private corpus dump. It does not include creator transcripts, channel names, proprietary sample scripts, local paths, API keys, tokens, or private generated archives.

## Included Skills / 包含的 Skill

| Skill | 用途 / Use It For |
| --- | --- |
| [`geng.skill`](skills/geng.skill) | 用于 controlled commentary writing。它会做 source retrieval、case-bite extraction、opening/body/ending staging、locked-part integrity 和 human-read anti-AI checks。 |
| [`create-blogger-clone-v2`](skills/create-blogger-clone-v2) | 用于从用户自己拥有或有授权的 examples 中，搭建匿名化 creator-style writing workflow Skill。重点是 source registration、eval split、micro-edit learning 和 release scan。 |

## Repository Layout / 仓库结构

```text
skills/
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
  practical_geng_opening_workflow.md
  practical_obsidian_assisted_workflow.md
```

`skills/` 里是真正可以复制进 Codex 的 Skill 文件夹。`docs/` 是说明文档。`examples/` 是可以直接照抄改写的使用示例。

## Installation / 安装

Clone or download this repository:

```bash
git clone https://github.com/forest70kj/geng-skill-and-create-blogger-clone.git
cd geng-skill-and-create-blogger-clone
```

Copy the Skill folder you want into your Codex skills directory:

```bash
cp -R skills/geng.skill ~/.codex/skills/
cp -R skills/create-blogger-clone-v2 ~/.codex/skills/
```

然后开启一个新的 Codex session，直接点名调用 Skill:

```text
Use geng.skill.
```

或者：

```text
Use create-blogger-clone-v2.
```

If your Codex setup uses a different custom skills folder, copy the Skill folder there instead. The important part is that each folder keeps its own `SKILL.md` and `skill.json`.

## Quick Start: `geng.skill` / 快速开始

`geng.skill` 适合你已经有一个 topic / source object，并且想写一篇 commentary-style draft，但不想让 AI 一口气写完整稿的时候。

Example prompt / 示例 prompt:

```text
Use geng.skill.

I want an opening_only pass for this case:
- topic: [your topic / 你的选题]
- source notes: [paste short source notes or give local file paths / 粘贴材料摘要或给本地文件路径]
- main complaint: [what feels wrong, funny, confusing, or worth attacking / 你想吐槽的核心点]
- audience position: [new viewer, returning viewer, fan, buyer, comment section, etc. / 观众位置]

Before writing, create a case bite brief.
Then generate only opening candidates.
Stop and wait for my review before writing the body.
```

Expected output / 预期输出:

```text
case bite brief
-> opening candidates
-> self-check
-> user decision gate
```

你接下来可以这样回复：

```text
opening_good
usable_but_needs_micro_edit: [your edit / 你的小修改]
reject: [why / 为什么不行]
```

The Skill should not move to the body until the opening is approved or revised.

它不应该在开头还没确认前继续写正文。这个分段机制是核心。

Full copy-paste example / 完整可复制示例：

- [`examples/practical_geng_opening_workflow.md`](examples/practical_geng_opening_workflow.md)

## Quick Start: `create-blogger-clone-v2` / 快速开始

`create-blogger-clone-v2` 适合你想从自己拥有、自己写的、或明确有授权的 examples 中，搭建一个新的 writing workflow Skill。

Example prompt / 示例 prompt:

```text
Use create-blogger-clone-v2.

I want to build a new anonymized writing Skill from my own examples.
First help me register sources, split an eval set, and extract transferable methods.
Do not include private source text in any public package.
```

Expected workflow / 预期流程：

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

## Practical Examples / 实用示例

如果你第一次用，建议先看这两个：

- [`examples/practical_geng_opening_workflow.md`](examples/practical_geng_opening_workflow.md): 一个 realistic opening-only workflow，包含 source notes、expected case bite、candidate output shape 和 review responses。
- [`examples/practical_obsidian_assisted_workflow.md`](examples/practical_obsidian_assisted_workflow.md): 展示如何把 `geng.skill` 和少量 Obsidian jokes / memes / negative rules 搭配使用。

## Default Writing Workflow / 默认写作流程

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

Full-script generation is not the default. This is deliberate.

默认不一口气写完整稿，这是有意设计的。因为 AI 最容易在“一口气写完”的时候变成那种很顺、很干净、但是没有人味的分析文。

Staging makes it easier to catch generic AI phrasing before it infects the whole draft.

## Author's View / 作者观点：搭配 Obsidian 知识库

My recommended setup is to use these Skills together with an Obsidian vault.

我的建议是：把这个 Skill 和 Obsidian 知识库一起用。

思路很简单：你可以在 Obsidian 里搭一个很大的本地知识库，专门存放 jokes、memes、analogies、complaint structures、scene-pressure patterns、negative examples。写文章或写视频稿时，让 Skill 边写边参考这些相关笔记。

This can greatly reduce the mechanical feeling of AI writing.

这样能明显减少 AI 写东西的机械感。因为你不是让模型从 0 开始硬编“风味”，而是给它一个你自己长期积累出来的梗库、段子库、类比库和负面规则库。Skill 仍然要写新稿，但它可以借用你自己的审美和素材机制。

Suggested Obsidian layout / 建议 Obsidian 结构:

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

Useful note format / 笔记格式:

```markdown
---
type: joke_pattern
tags: [commentary, opening, audience-pressure]
status: reusable
risk: low
---

# Pattern Name / 模式名

## What It Does / 它解决什么

Explain the joke or meme mechanism in plain language.
用普通话解释这个梗、段子或机制到底在干什么。

## When To Use / 什么时候用

Describe the kind of scene, topic, or audience pressure where this pattern fits.
说明它适合什么场景、选题或观众压力。

## Example Shape / 示例骨架

Use a short anonymized structure, not a copied private paragraph.
写一个短的匿名化结构，不要复制私人原文。

## Do Not Use When / 不适合什么时候用

List boundaries and failure cases.
列出边界和失败场景。
```

Prompt example / 调用示例:

```text
Use geng.skill.

Before writing, reference these Obsidian notes:
- /path/to/ObsidianVault/jokes/audience-complaint-jokes.md
- /path/to/ObsidianVault/memes/waiting-room-pressure.md
- /path/to/ObsidianVault/negative-rules/ai-analysis-smell.md

Use them as reusable mechanics, not as text to copy.
Generate opening_only for this case:
[your source notes / 你的材料摘要]
```

Best practice: do not dump your whole vault into one prompt. Give the Skill a small, relevant set of notes, usually 3 to 8 files.

最佳做法：不要一次把整个 Obsidian vault 塞进去。每次只给 3 到 8 个最相关的 notes，并要求它说明哪条 note 影响了哪个 draft choice。

Deeper setup guide / 更详细指南：

- [`docs/obsidian_knowledge_base.md`](docs/obsidian_knowledge_base.md)

## How To Review Output / 怎么审稿

When the Skill gives you a draft, do not only ask whether the facts are correct. Also ask:

拿到草稿后，不要只检查事实对不对，还要检查：

- Does it sound like a person reacting, or like an organized essay? / 像人在吐槽，还是像整理好的作文？
- Is the first paragraph case-specific? / 第一段是不是足够具体？
- Does every paragraph add a new pressure? / 每一段有没有新增压力？
- Are jokes explaining the complaint, or just decorating it? / 梗是在解释问题，还是只是在装饰？
- Did the ending summarize too cleanly? / 结尾是不是总结得太干净？
- Could this paragraph work for another topic by swapping names? / 换个名字还能用吗？如果能，就太泛了。

If something feels AI-written, give a micro-edit:

如果某句话有 AI 味，直接给 micro-edit：

```text
This line is too analytical:
"The relationship arc lacks sufficient buildup."

Rewrite toward this pressure:
"The relationship meter is not even full, but the story already throws the special ending image at the viewer."
```

The useful lesson is not the exact sentence. The useful lesson is: concrete mechanism beats abstract critique.

真正有价值的不是这句原文，而是这个规则：具体机制比抽象评论更有用。

## Public Release Safety / 公开发布安全边界

Before publishing a Skill package made with this workflow:

发布任何由这个 workflow 生成的 Skill package 前，请确认：

- remove private transcripts / 删除私人转录稿
- remove creator names and channel names unless you have permission / 未授权就删除创作者名和频道名
- remove long recognizable source passages / 删除长篇可识别原文
- remove local paths, account names, API keys, and tokens / 删除本地路径、账号名、API key 和 token
- keep examples short and anonymized / 示例保持短、匿名化
- run a sensitive-content scan / 做敏感内容扫描
- keep user review gates visible / 保留用户审稿 gate

This repository's public release scan is included in:

```text
PUBLIC_RELEASE_SENSITIVE_SCAN.md
PUBLIC_RELEASE_SENSITIVE_SCAN.json
```

## License / 许可证

MIT License.
