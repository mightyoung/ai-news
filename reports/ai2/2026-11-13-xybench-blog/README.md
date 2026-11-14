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

Ai2 发布 XYBench 官方介绍：这是一个 8,115 道题的基准（博客与配套论文 Table 1 一致，原文是 8,115 及「8K+」，不是「超过 8,115」），用来测模型在用户提问建立在错误前提（XY 问题）时，能否认出真正的目标并在回答里把解决方案放在中心。官方 GitHub README 与 HF 数据集卡片将 WikiHow 写成 6,268（加总 8,111），与博客/论文的 WikiHow 6,272、总计 8,115 差 4 道；数据集 gated，原始文件未能计行。文中称该资源获得 EMNLP 2026 Best Resource Paper Award，已在会议官方获奖名单（https://2026.emnlp.org/program/awards/）与 ACL Anthology（https://aclanthology.org/2026.emnlp-main.2646/）交叉；合作方包括卡内基梅隆、NVIDIA 和约翰霍普金斯。主评测五个模型（Claude Sonnet 4.6、GPT-5、Gemini 3.1 Pro、Qwen3.5-9B、DeepSeek-V4 Pro）。在 Stack Overflow 子集上（厂商自报）：「提到对潜在目标的修法」五个模型为 59–71%（GPT-5 71%，人类参考答案 67%）；「回答重点放在潜在目标」模型为 35–41%（人类参考答案 55%）；「把用户从错误路径转到真正目标」模型为 47–60%（人类参考答案 79%）。另有 oracle 实验：把真正目标明确告诉模型后，Sonnet 4.6 在「包含潜在目标解法」上从 59% 升到 67%，但「识别错误前提」从 47% 降到 34%。代码见 GitHub `allenai/XYBench`（Apache-2.0）；数据集卡片为 `allenai/XYBench-dataset`（CC-BY-NC-SA-3.0，自动门控）。本次没有新的技术报告，配套论文是 2026-09 的 arXiv:2609.06842。

## 原文

[来源.md](来源.md)

## 核验

[⚠️ 部分核实（存疑）](核验.md)（2026-11-14 T2 标准版）。评测数字与奖项可在原文定位，并与论文 Table 2 / Table 11 及 EMNLP 官方名单一致；但官方 GitHub / HF 卡片的 WikiHow 题量与博客/论文差 4 道，原始数据因门控读不到。本次没有新的技术报告。

## 深度解析

待补

## 相关文档

- 配套论文（2026-09，非本次新发）：https://arxiv.org/abs/2609.06842
- 代码：https://github.com/allenai/XYBench
