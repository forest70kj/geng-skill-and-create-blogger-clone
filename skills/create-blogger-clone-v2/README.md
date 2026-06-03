# create-blogger-clone-v2

`create-blogger-clone-v2` 是一个用来创建 writing workflow Skill 的 reusable Skill。

它适合从你自己拥有、自己写的、或明确获得授权的 examples 中，提炼 transferable writing methods，然后生成一个匿名化、可审查、可发布的 Skill package。

Core workflow / 核心流程：

```text
source registration
-> source cleaning
-> eval split
-> transferable method extraction
-> staged candidate generation
-> micro-edit learning
-> safety scan
-> reviewable package export
```

它关注的是：

- structure / 结构
- rhythm / 节奏
- joke mechanics / 梗和段子的机制
- evidence handling / 材料怎么进入正文
- revision criteria / 怎么判断要改哪里
- release safety / 公开发布前怎么匿名化

This public version contains workflow structure, templates, safety rules, and anonymized examples only.

这个公开版本只包含 workflow、templates、安全规则和匿名化示例，不包含任何私人 creator corpus。

Typical prompt / 常用提示词：

```text
Use create-blogger-clone-v2.

I want to build a new anonymized writing Skill from my own examples.
First help me register sources, split an eval set, and extract transferable methods.
Do not include private source text in any public package.
```
