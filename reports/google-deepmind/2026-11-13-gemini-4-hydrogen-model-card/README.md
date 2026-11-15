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

> 日期说明：模型卡页写 Published 12 November 2026；PDF 封面只写 Published: November 2026。对应博客的 `datePublished` 为 2026-11-12T18:00:00+00:00（北京时间 2026-11-13 02:00），文件夹按上线公告的北京时间归到 2026-11-13。本条是 11-13 已发布、此前 T1 未入库的补档。

> 架构、训练数据、硬件、软件、可接受用途均指向 Gemini 4 Carbon 模型卡；基准结果表在物理第 5 页（页脚 4），为图片。文中称完整 Safety & Security Report「coming soon」，本次未收到。暂无独立技术报告。

## 摘要

模型卡写明 Gemini 4 Hydrogen 由 Gemini 4 Carbon 适配而来，面向日常编程和多样化智能体工作流的快速执行；输入为文本、图像、音频、视频，输入加输出合计上下文最长 1M token（官方文档为 1,048,576），默认同步输出最长 64K（官方文档 65,536）、可通过 background long decode 输出最长 1M。知识截止为 2026 年 3 月。官方默认思考档为 high，另有 low / medium / xhigh。分发渠道包括 Gemini app、Gemini API、Google Sheets、AI Studio、Gemini for business、Antigravity 和 Google Search。这是模型卡，不是技术报告；架构与训练细节指向 Carbon 模型卡。官方 Gemini API / AI Studio 标准付费档为每百万 token 输入 $1.50、输出 $7.50，整个 1M 窗口一口价（另有 Batch/Flex、Priority、Cloud 非全球区域价）。参数量官方未披露；权重不公开。

能力评测表（截至 2026 年 11 月，物理第 5 页图片，已与官方 HTML 表及评测方法 PDF 第 4 页核对；除另注外为 pass@1、最高思考档，对照 Claude Sonnet 5.5 与 GPT-6.1 Terra）完整 10 行如下：

| 类别 | 基准 | 备注 | Gemini 4 Hydrogen | Claude Sonnet 5.5 | GPT-6.1 Terra |
|---|---|---|---|---|---|
| Agentic coding | SWE-sweep | | 13.5% | 3.1% | 5.8% |
| | Terminal-Bench 4.1 | Cheating adjusted | 57.0% | 63.9% | — |
| Knowledge work | Agents' Last Exam v1.1 | Score | 71.6% | 60.4% | 69.8% |
| | AutomationBench-AA | | 76.1% | 71.8% | 60.2% |
| | Vending-Bench 2 | Bank balance ($) | $14,549 | $11,165 | $9,107 |
| Computer use | OSWorld-2.1 | Offline subset | 77.6% | 83.9% | 74.2% |
| Multimodal understanding | MKA | Climb WSR accuracy | 53.4% | 52.0% | 43.8% |
| | Chartography | | 66.6% | 61.6% | 63.2% |
| Science and math | Terminal-Bench-Science 0.1 | | 51.4% | 59.9% | 58.3% |
| Reasoning | HLE-Diamond | | 58.8% | 53.3% | 47.3% |

限定：Terminal-Bench 4.1 的 57.0% 是厂商用 mini-swe-agent vision、high 档、Cheating adjusted 自测；官方 Terminal-Bench 4.1 榜同模型为 Antigravity CLI / high 的 56.4% ± 3.0%（186/330，2026-11-15 查询），不能写成同一个数。Sonnet 5.5 的 63.9% 与官方榜 Claude Code / max 的 63.9% ± 3.0% 一致。官方榜另有 Terra 53.3% ± 3.1%，模型卡该格为「—」。AutomationBench-AA 76.1% 与 HLE-Diamond 58.8% 来自 Artificial Analysis 的 **xhigh** 档（2026-11-15 查询，high 档为 74.4% / 54.9%）。SWE-sweep 不是 SWE-bench，官方 SWE-bench 榜未收录 Hydrogen。

内部自动化安全评测相对 Gemini 3.8 Flash（厂商自报，第 7 页，与旧卡口径不可比）：文本到文本安全 +0.80pp、多语言安全 +1.10pp、图像到文本安全 +7.00pp，拒答语气 −0.65pp，不合理拒答 +5.57pp（越低越好，此项为退步）。前沿安全方面，文中称对 Argon 的 MCC 评估未显示能力的实质性提升，因此未做全套临界能力评测；在针对性测试后认为未达到 CBRN（生物）与网络 CCL，但达到这两个域的 CCL 预警阈值。完整 Safety & Security Report 在 2026-11-15 仍为 coming soon（同构 PDF 404）；英国 AISI、美国 NIST/CAISSI、METR、Apollo Research 暂未见针对 Hydrogen 的公开报告。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-15 T2 标准版）。PDF 10 页哈希与归档一致。能力表 10 行已从截图转读；Terminal-Bench 4.1 的 57.0% 是厂商 high 档自测，官方榜同模型为 56.4% ± 3.0%。AutomationBench-AA 与 HLE-Diamond 的表内分数来自 AA 的 xhigh 档。完整安全报告今日仍未发布。

## 深度解析

[深度解析.md](深度解析.md)。Gemini 4 Hydrogen 是由 Carbon 适配的更快、更便宜日常执行档：1M 上下文一口价，官方标准价 $1.50 / $7.50；适合编程与智能体工作流，但训练细节几乎未披露，完整安全报告尚未发布。

## 相关文档

- [Introducing Gemini 4 Hydrogen（官方博客）](../2026-11-13-gemini-4-hydrogen/README.md)
- [Gemini 4 Carbon 模型卡](../2026-11-11-gemini-4-carbon-model-card/README.md)（本卡多次指向其架构与训练细节）
- [Gemini 4 Carbon Safety & Security Report](../2026-11-11-gemini-4-carbon-safety-report/README.md)
