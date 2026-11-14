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

Jack Cook 与 Thinking Machines Lab 同事在 Connectionism 博客写的端到端 4-bit 训练说明，是 11-05 Inkling 2 Small 发布后预告的 NVFP4 配方补完，不是新模型。文中给出 GB300 上三种格式的每值位数和峰值算力（厂商自报）：NVFP4 4.5 bit / 15 PFLOPS，MXFP8 8.25 bit / 5 PFLOPS，BF16 16 bit / 2.5 PFLOPS。其中 4.5 / 8.25 bit 含块缩放因子，公式为 `(4×16+8)÷16`、`(8×32+8)÷32`。文中称 NVFP4 比 BF16 少约 3.6 倍比特，在 GB300 上最高可快约 6 倍。实际做法是专家层前向用 NVFP4（配专用 kernel），反向用 MXFP8，再加重新量化和随机舍入。在最大规模任务上，相对全程 MXFP8，预训练墙钟时间加快 8%，强化学习加快 20%；预训练大约付出 2% 的计算效率代价（达到若用 MXFP8、大约少 2% FLOPs 就能到的损失）。文中再次提到 Inkling 2 Small 在 GB300 NVL72 机架上预训练只用了 68 小时（与 11-05 介绍文 H1 预训练为同一口径）。截至 2026-11-14，权重已在 Hugging Face `thinkingmachines/Inkling-2-Small` 按 Apache 2.0 公开（模型卡声明；仓库无独立 LICENSE 文件；上传时间为 2026-11-12 19:53 UTC，即北京时间 11-13 03:53）。OpenRouter 已上架，输入 $0.30 / 输出 $1.00 / 百万 token，上下文 1,048,576；Artificial Analysis Intelligence Index 仍为 31、每任务 $1.18（与 11-06 核验一致）。暂无独立 PDF 技术报告。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-14 T2 标准版）。数值表与 8%/20%/2%/68 小时均可在原文定位，全部厂商自报；68 小时与 11-05 H1 预训练同一口径。暂无独立 PDF 技术报告。

## 深度解析

待补

## 相关文档

- [Introducing Inkling 2 Small](../2026-11-05-inkling-2-small/README.md)
