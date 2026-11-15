# Google DeepMind · Gemini 4 Hydrogen Model Card

| 项目 | 内容 |
|---|---|
| 厂商 | Google DeepMind |
| 文档类型 | 模型卡（model-card） |
| 模型名与版本 | Gemini 4 Hydrogen（adapted from Gemini 4 Carbon） |
| 发布日期 | 2026-11-13（北京时间） |
| 官方链接 | https://deepmind.google/models/model-cards/gemini-4-hydrogen/ |
| PDF 链接 | https://storage.googleapis.com/deepmind-media/Model-Cards/Gemini-4-Hydrogen-Model-Card.pdf |
| arXiv id | — |
| SHA-256 | 5b985d4e06c8881317bdadcbee5656c96b84a9d3278f043b20b396707b9f3c20 |
| 页数 | 10 |

> 日期说明：模型卡页写 Updated 12 November 2026；PDF 封面只写 Published: November 2026。对应博客的 `datePublished` 为 2026-11-12T18:00:00+00:00（北京时间 2026-11-13 02:00），文件夹按上线公告的北京时间归到 2026-11-13。本条是 11-13 已发布、此前 T1 未入库的补档。

> 架构、训练数据、硬件、软件、可接受用途均指向 Gemini 4 Carbon 模型卡；基准结果表在物理第 5 页（页脚 4），为图片。文中称完整 Safety & Security Report「coming soon」，本次未收到。暂无独立技术报告。

## 摘要

模型卡写明 Gemini 4 Hydrogen 由 Gemini 4 Carbon 适配而来，面向日常编程和多样化智能体工作流的快速执行；输入为文本、图像、音频、视频，输入加输出合计上下文最长 1M token，默认同步输出最长 64K、可通过 background long decode 输出最长 1M。知识截止为 2026 年 3 月。分发渠道包括 Gemini app、Gemini API、Google Sheets、AI Studio、Gemini for business、Antigravity 和 Google Search。能力评测表（厂商自报，截至 2026 年 11 月，物理第 5 页图片，对照 Claude Sonnet 5.5 与 GPT-6.1 Terra）例如：SWE-sweep 13.5%（Sonnet 5.5 为 3.1%，Terra 为 5.8%）；Terminal-Bench 4.1（Cheating adjusted）57.0%（Sonnet 5.5 为 63.9%，Terra 为「—」）；Agents' Last Exam v1.1 71.6%；AutomationBench-AA 76.1%；MKA（Climb WSR accuracy）53.4%；HLE-Diamond 58.8%。内部自动化安全评测相对 Gemini 3.8 Flash（厂商自报，第 7 页，与旧卡口径不可比）：文本到文本安全 +0.80pp、多语言安全 +1.10pp、图像到文本安全 +7.00pp，拒答语气 −0.65pp，不合理拒答 +5.57pp（越低越好，此项为退步）。前沿安全方面，文中称对 Argon 的 MCC 评估未显示能力的实质性提升，因此未做全套临界能力评测；在针对性测试后认为未达到 CBRN（生物）与网络 CCL，但达到这两个域的 CCL 预警阈值。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补（已列入今日精读）

## 相关文档

- [Introducing Gemini 4 Hydrogen（官方博客）](../2026-11-13-gemini-4-hydrogen/README.md)
- [Gemini 4 Carbon 模型卡](../2026-11-11-gemini-4-carbon-model-card/README.md)（本卡多次指向其架构与训练细节）
- [Gemini 4 Carbon Safety & Security Report](../2026-11-11-gemini-4-carbon-safety-report/README.md)
