# Anthropic · Building strong safety evaluations

| 项目 | 内容 |
|---|---|
| 厂商 | Anthropic |
| 文档类型 | 官方博客（Engineering / 安全评测方法） |
| 模型名与版本 | —（文中举例取自既有系统卡，不是新模型发布） |
| 发布日期 | 2026-11-13（页面 Published Nov 13, 2026；`article:published_time` 为 2026-11-13T00:00:00.000Z） |
| 官方链接 | https://www.anthropic.com/research/building-strong-safety-evaluations |
| PDF 链接 | —（正文是网页；文中引用的 PDF 是既有 Claude Sonnet 5 系统卡，不是本文附件） |
| arXiv id | — |
| SHA-256 | 网页 HTML：3347eedaf655fe6005fe728a581409a7972602124e920c00fb60207bf6e61136（2026-11-14 再抓可见正文未变，仅脚本哈希不同） |
| 页数 | — |

## 摘要

Anthropic Engineering 博客给出一套设计、运行和报告 AI 安全评测的建议，作者为 Ruth Appel、Evan Frondorf、Jeremy Hadfield、Rebecca Hiscott、Kamya Jagadish、Shayne Longpre、Madeleine Tucker、Brett Wittmershaus。文中把安全评测定义为：在特定输入下，模型是否做了「该做的事」，以及它造成或加重伤害的倾向，而不是测能力是否够用。作者把心理学可重复性改革（预注册、更好的测量和统计）作为参照，并结合自己写系统卡的经验。文中没有发布新模型或新系统卡；如果只做三件事，文中建议：在收集数据前先写清要测的构念、在相信评分器数字前先用人类判断校准、报告不确定性。暂无独立技术报告。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-14 T2 标准版）。官方方法博客存在，不是新模型或新系统卡；暂无技术报告。

## 深度解析

待补

## 相关文档

- [Claude Fable 5.2 / Mythos 5.2 系统卡](../2026-11-09-claude-fable-mythos-5-2-system-card/README.md)
- [The components of agent memory](../2026-11-07-components-of-agent-memory/README.md)
