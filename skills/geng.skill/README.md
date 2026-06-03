# geng.skill

`geng.skill` 是一个匿名化的 controlled commentary writing Skill。

它适合用来写 commentary-style script / article opening / body / ending，但默认不是让 AI 一口气写完整稿。

Core workflow / 核心流程：

```text
source retrieval
-> case bite extraction
-> opening_only
-> user review / micro-edit
-> locked opening
-> body_after_locked_opening
-> user review / micro-edit
-> ending_only
-> final assembly
```

主要能力：

- source grounding / 先基于材料，不凭空发挥
- case bite extraction / 写之前先提炼核心冲突点
- staged drafting / 开头、正文、结尾分阶段写
- locked-part integrity / 用户确认过的部分不偷偷改
- micro-edit learning / 用户的小修改会变成下一轮规则
- human-read anti-AI gate / 检查是否有机械 AI 分析腔

It does not impersonate any creator and does not include any private corpus.

它不冒充任何创作者，也不包含私人语料、频道名、转录稿或长篇样本。

Typical prompt / 常用提示词：

```text
Use geng.skill.

I want an opening_only pass.
First create a case bite brief.
Then generate opening candidates.
Stop before writing the body.
```
