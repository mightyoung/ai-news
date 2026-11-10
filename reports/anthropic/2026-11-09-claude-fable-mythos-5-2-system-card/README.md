# Anthropic · Claude Fable 5.2 & Claude Mythos 5.2 System Card

| 项目 | 内容 |
|---|---|
| 厂商 | Anthropic |
| 文档类型 | 系统卡（system-card） |
| 模型名与版本 | Claude Fable 5.2、Claude Mythos 5.2（同一底层模型的两种配置） |
| 发布日期 | 2026-11-09（文档封面日期） |
| 官方链接 | https://www.anthropic.com/document/claude-fable-5-2-mythos-5-2-system-card |
| PDF 链接 | https://assets.claude.com/27d60918d218125e7504bc7354c4b4626ec56b11.pdf |
| arXiv id | — |
| SHA-256 | bb548a5db76349a67a0e65b84f36ddd15c19c3d5819eb3028460955682bfc259 |
| 页数 | 264 |

## 摘要

文档称 Fable 5.2 面向通用使用，在生物和网络安全等高风险双用途领域加有额外防护；Mythos 5.2 防护更宽松，仅通过受信任访问项目向审核过的个人和机构开放。系统卡报告了七个方面的发布前评测，包括 RSP 评测（化学生物、AI 研发自动化、网络安全）、安全防护、智能体安全、对齐评估、模型福利和能力评测。能力表中 Fable 5.2 在 SWE-bench Pro 为 93.0%（厂商自报，adaptive thinking max effort、5 次平均，未注明子集；对比 Fable 5.1 81.2%、Opus 5.5 89.9%，Table 8.1.A，第 207 页）。Remote Labor Index 41.3%（240 个项目中 99 个）已被 Scale Labs RLI 榜独立收录，同为 41.30。训练部分只写了数据来源类别和后训练，没有披露架构、规模或 RL 配方。

## 状态

- 核验：[✅ 能核实](核验.md)（能力数字多为厂商自报；RLI 有第三方独立收录）
- 深度解析：待补

## 相关文档

- [Claude Fable 5.2 与 Mythos 5.2 发布博客](../2026-11-09-claude-fable-mythos-5-2-announcement/README.md)
