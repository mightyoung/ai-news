# Ai2 · XYBench: Helping with the problem behind the question

| 项目 | 内容 |
|---|---|
| 厂商 | Ai2（allenai） |
| 文档类型 | 官方博客（新评测基准发布） |
| 模型名与版本 | —（评测基准 XYBench，不是新模型） |
| 发布日期 | 2026-11-13（页面日期） |
| 官方链接 | https://allenai.org/blog/xybench |
| PDF 链接 | 配套论文 https://arxiv.org/abs/2609.06842（2026-09 已发布，不是本次新发技术报告） |
| arXiv id | 2609.06842（旧文，仅作配套链接） |
| SHA-256 | 网页 HTML：6298f5b419fac9df6dc56dad44304d928db29b6fdbc33bd6dda88f6a59911ae0 |
| 页数 | — |

## 摘要

Ai2 发布 XYBench 官方介绍：这是一个超过 8,115 道题的基准，用来测模型在用户提问建立在错误前提（XY 问题）时，能否认出真正的目标并在回答里把解决方案放在中心。文中称该资源获得 EMNLP 2026 Best Resource Paper Award，合作方包括卡内基梅隆、NVIDIA 和约翰霍普金斯。主评测五个模型（Claude Sonnet 4.6、GPT-5、Gemini 3.1 Pro、Qwen3.5-9B、DeepSeek-V4 Pro）。在 Stack Overflow 子集上（厂商自报）：「提到对潜在目标的修法」五个模型为 59–71%（GPT-5 71%，人类参考答案 67%）；「回答重点放在潜在目标」模型为 35–41%（人类参考答案 55%）；「把用户从错误路径转到真正目标」模型为 47–60%（人类参考答案 79%）。另有 oracle 实验：把真正目标明确告诉模型后，Sonnet 4.6 在「包含潜在目标解法」上从 59% 升到 67%，但「识别错误前提」从 47% 降到 34%。代码与数据见 GitHub `allenai/XYBench`。本次没有新的技术报告，配套论文是 2026-09 的 arXiv:2609.06842。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- 配套论文（2026-09，非本次新发）：https://arxiv.org/abs/2609.06842
- 代码：https://github.com/allenai/XYBench
