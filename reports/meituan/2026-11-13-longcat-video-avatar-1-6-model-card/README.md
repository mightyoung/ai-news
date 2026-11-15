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

Hugging Face 模型卡宣布开源音频驱动数字人框架 LongCat-Video-Avatar 1.6，在 1.5 基础上改进表情自然度、唇音同步、面部与肢体配合，以及长视频生成时的视觉一致性，并称做了端到端推理优化。卡片列出的要点包括：减轻夸张或紧绷的口型、嘴唇过红和时间不稳定；缓解自回归续拍中的误差累积，使视频可以超过 10 分钟并保持身份与时间连贯；以及更快的端到端推理（厂商自报，模型卡 Key Features / Model Introduction）。权重声明为 MIT License，仓库含 `base_model`、`base_model_int8` 以及 `loraA` / `loraB`。更完整的训练与评测细节指向 GitHub 上的技术报告，已另建文件夹。卡片未给出独立的基准数字表。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补（模型卡本身不精读；技术报告已列入今日精读）

## 相关文档

- [LongCat-Video-Avatar 1.6 Technical Report](../2026-11-13-longcat-video-avatar-1-6-tech-report/README.md)
