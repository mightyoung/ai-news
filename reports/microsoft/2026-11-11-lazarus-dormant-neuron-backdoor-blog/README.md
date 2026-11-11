# Microsoft · Lazare, veni foras: Reprogramming Dormant Neurons to Backdoor AI Agents

| 项目 | 内容 |
|---|---|
| 厂商 | Microsoft |
| 文档类型 | 官方博客（安全研究）（blog） |
| 模型名与版本 | —（研究博客，Lazarus 后门技术） |
| 发布日期 | 2026-11-11（北京时间；页面日期 Nov 10） |
| 官方链接 | https://www.microsoft.com/en-us/research/blog/lazare-veni-foras-reprogramming-dormant-neurons-to-backdoor-ai-agents/ |
| PDF 链接 | 论文：https://github.com/anadim/anadim.github.io/blob/master/papers/Lazarus.pdf（博客内链接，托管在作者个人 GitHub，本次未下载） |
| arXiv id | — |
| SHA-256 | — |
| 页数 | —（网页） |

> 暂无技术报告：论文 PDF 在作者个人 GitHub，不属于官方发布渠道，本次未下载。安全话题只写防御侧。

## 摘要

微软研究院博客（2026-11-10，作者 Dimitris Papailiopoulos）称，对 LLM 中不到 10 个休眠神经元重编程权重就足以给基于它的智能体植入后门，无需再训练，模型能通过标准评测，直到触发条件出现。博客的防御侧结论：这类改动可以被发现（前沿智能体在被要求时能识别异常权重修改），但没有任何扫描能证明模型绝对安全；可靠检测需要与原始权重做差，因此模型来源和权重完整性是关键；微软列出的做法包括 Foundry 的来源校验、AI 权重扫描、红队工具、带防篡改溯源的加密签名。本条只记录防御侧。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- 暂无同一模型的其他文件夹
