# Workflow Overview / 工作流总览

The core workflow is staged and user-gated.

核心设计是：分阶段写，每一阶段都让用户 review，不让 AI 默认一口气写完。

```text
source retrieval
-> case bite extraction
-> opening only
-> user review
-> body only after locked opening
-> user review
-> ending only after locked opening/body
-> user review
-> full draft assembly
-> final user decision
```

Full-script generation is not the default.

默认不生成完整稿。原因很简单：AI 最容易在“一口气写完”时变成顺滑但机械的分析文。

如果用户确实要求 unattended generation / 无人值守生成，也要保留 section boundaries，并把 review gates 标记为 pending。

Recommended usage / 推荐用法：

- first run `opening_only` / 先只写开头
- review and micro-edit / 审稿并给小修改
- lock the approved part / 锁定确认过的部分
- continue to body and ending / 再继续写正文和结尾
