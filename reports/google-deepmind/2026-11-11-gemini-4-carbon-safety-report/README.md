# Google DeepMind · Gemini 4 Carbon Safety & Security Report

| 项目 | 内容 |
|---|---|
| 厂商 | Google DeepMind |
| 文档类型 | 系统卡类（Safety & Security Report）（system-card） |
| 模型名与版本 | Gemini 4 Carbon |
| 发布日期 | 2026-11-11（北京时间） |
| 官方链接 | https://storage.googleapis.com/deepmind-media/gemini/gemini_4_carbon_safety_report.pdf |
| PDF 链接 | https://storage.googleapis.com/deepmind-media/gemini/gemini_4_carbon_safety_report.pdf |
| arXiv id | — |
| SHA-256 | 78179c76c34e3f6f57cbc36fc672c8fb5d15afb0209bd98a46adacebb43774eb |
| 页数 | 94 |

> 日期说明：页面日期 Nov 10, 2026；RSS 时间 2026-11-10 16:03:47 UTC，即北京时间 2026-11-11 00:03。

> 类型说明：这是安全与安全性报告，起系统卡作用，类型按 system-card 归档。网络安全相关内容后续只写防御侧。

## 摘要

这是谷歌对 Carbon 的安全与安全性报告，范围包括前沿安全框架（FSF）评估、缓解措施、内容安全与智能体滥用、对齐与幻觉、间接提示注入、网络防御能力。报告称 Carbon 相对 Argon 没有实质新增能力或能力的实质提升，因此没有重做完整关键能力评估，沿用 Argon 的结论：不能排除未加外部缓解时达到 Cyber Uplift Level 1 CCL、CBRN Uplift Level 1 CCL 与 Stealth and Situational Awareness TCL（厂商自报）。自报数字：CWE-bench v1（120 个任务，73 种 CWE，六种语言）Pass@1 71.0%，Argon 为 68.0%（已被 Collinear AI 的 CWE-bench v1 榜独立收录，71%）；ExploitGym 成功率 54.8%（10 小时延长超时、单次尝试、关闭基准缓解，自算；Argon 同条件 42.0%，差 12.8 个百分点；默认 6 小时为 53.5% vs 39.5%，第 90 页）；Gray Swan 间接提示注入基准攻击成功率 0%。本次未重做完整 FSF 能力评估，也未做新一轮 ESTP 外部能力评测，外部合作为 Gray Swan、Trajectory Labs 防护红队（第 17 页）。

## 原文

[来源.md](来源.md)

## 核验

✅ 能核实（ExploitGym 54.8% 为 10 小时超时自算；CWE-bench 71.0% 有第三方榜收录） · [核验.md](核验.md)

## 深度解析

待补

## 相关文档

- [Gemini 4 Carbon 模型卡](../2026-11-11-gemini-4-carbon-model-card/README.md)
- [Gemini 4 Carbon is now available（官方博客）](../2026-11-11-gemini-4-carbon-now-available/README.md)
- [Gemini 4 Carbon: our next frontier model（10-29 官方博客）](../2026-10-29-gemini-4-carbon/README.md)
