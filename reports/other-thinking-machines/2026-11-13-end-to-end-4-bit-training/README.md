# Thinking Machines Lab · End-to-End 4-Bit Training

| 项目 | 内容 |
|---|---|
| 厂商 | Thinking Machines Lab（other-thinking-machines） |
| 文档类型 | 官方博客（Connectionism；训练配方，不是新模型） |
| 模型名与版本 | Inkling 2 Small（既有模型；本文补 NVFP4 训练细节） |
| 发布日期 | 2026-11-13（页面日期） |
| 官方链接 | https://thinkingmachines.ai/blog/end-to-end-4-bit-training/ |
| PDF 链接 | — |
| arXiv id | — |
| SHA-256 | 网页 HTML：d6067a8288846b7dac93c9caf2688a18e93f914d90b04c48afc52c9a041b5999 |
| 页数 | — |

## 摘要

Jack Cook 与 Thinking Machines Lab 同事在 Connectionism 博客写的端到端 4-bit 训练说明，是 11-05 Inkling 2 Small 发布后预告的 NVFP4 配方补完，不是新模型。文中给出 GB300 上三种格式的每值位数和峰值算力（厂商自报）：NVFP4 4.5 bit / 15 PFLOPS，MXFP8 8.25 bit / 5 PFLOPS，BF16 16 bit / 2.5 PFLOPS；并称 NVFP4 比 BF16 少约 3.6 倍比特，在 GB300 上最高可快约 6 倍。实际做法是专家层前向用 NVFP4（配专用 kernel），反向用 MXFP8，再加重新量化和随机舍入。在最大规模任务上，相对全程 MXFP8，预训练墙钟时间加快 8%，强化学习加快 20%；预训练大约付出 2% 的计算效率代价（达到若用 MXFP8、大约少 2% FLOPs 就能到的损失）。文中再次提到 Inkling 2 Small 在 GB300 NVL72 机架上预训练只用了 68 小时（这一数字在 11-05 介绍文里已经出现过）。暂无独立 PDF 技术报告。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- [Introducing Inkling 2 Small](../2026-11-05-inkling-2-small/README.md)
