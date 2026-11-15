# Meituan LongCat · LongCat-Video-Avatar 1.6 模型卡（Hugging Face）

| 项目 | 内容 |
|---|---|
| 厂商 | 美团 LongCat（Meituan LongCat Team） |
| 文档类型 | 模型卡（model-card） |
| 模型名与版本 | LongCat-Video-Avatar 1.6 |
| 发布日期 | 2026-11-13（北京时间） |
| 官方链接 | https://huggingface.co/meituan-longcat/LongCat-Video-Avatar-1.6 |
| PDF 链接 | 技术报告见另一文件夹 |
| arXiv id | —（卡片引用块同样留空） |
| SHA-256 | —（网页 / README，无单一 PDF） |
| 页数 | — |

> 日期说明：HF API `createdAt` 为 2026-11-13T02:45:33.000Z（北京时间 10:45），`lastModified` 为 2026-11-13T11:27:11.000Z（北京时间 19:27，与技术报告 PDF 元数据时间接近）。本条是 11-13 已发布、此前 T1 未入库的补档。

## 摘要

Hugging Face 模型卡宣布开源音频驱动数字人框架 LongCat-Video-Avatar 1.6，在 1.5 基础上改进表情自然度、唇音同步、面部与肢体配合，以及长视频生成时的视觉一致性，并称做了端到端推理优化。卡片列出的要点包括：减轻夸张或紧绷的口型、嘴唇过红和时间不稳定；缓解自回归续拍中的误差累积，使视频可以超过 10 分钟并保持身份与时间连贯；以及更快的端到端推理（厂商自报，模型卡 Key Features / Model Introduction）。Human Evaluation 节写与 1.5 及 OmniHuman-2.0 等比较，33,051 次有效两两投票，Bradley–Terry Elo 1068.1、排第 2、落后 OmniHuman-2.0，与技术报告 Fig. 1 / §4 一致（厂商自报）；与 1.5 的 Fig. 8 绝对分仍只在技术报告里。权重确已公开、无门禁（`usedStorage=77623900551` 字节，约 72.29 GiB；`base_model` 约 29.53 GiB、`base_model_int8` 约 14.79 GiB、`loraA` / `loraB` 各约 2.35 GiB）。卡片 Quick Start 将 `loraA` 标为 DMD LoRA、`loraB` 标为 OPSD LoRA，与技术报告「推理合并 GRPO + OPSD LoRA」的表述不一致，原文未解释对应关系。许可以 GitHub `LICENSE`（MIT，Copyright (c) 2025 Meituan）与 `cardData.license=mit` 为准；HF 仓无独立 LICENSE 文件（徽章与「See the LICENSE file」会 404）。卡片另写「不授予美团商标或专利许可」，此句不在 GitHub LICENSE 原文中。仓内捆绑的 `whisper-large-v3/` 子目录 README 自述 Apache-2.0，卡片未说明 MIT 是否覆盖该部分。1.6 的参数量、激活参数、上下文和 API 价格官方未披露；OpenRouter 与 Artificial Analysis LLM 榜暂未收录本模型。更完整的训练与评测细节指向 GitHub 上的技术报告，已另建文件夹。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-15 T2 标准版）。仓公开无门禁，权重文件可 HEAD 到真实字节数。HF 仓无独立 LICENSE 文件，以 GitHub MIT 原文与 cardData 为准。

## 深度解析

待补（模型卡本身不精读；技术报告已列入今日精读）

## 相关文档

- [LongCat-Video-Avatar 1.6 Technical Report](../2026-11-13-longcat-video-avatar-1-6-tech-report/README.md)
