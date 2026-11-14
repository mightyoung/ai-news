# InclusionAI · Duo v1 模型卡（Hugging Face）

| 项目 | 内容 |
|---|---|
| 厂商 | InclusionAI（inclusionai） |
| 文档类型 | 模型卡（Hugging Face） |
| 模型名与版本 | Duo 1.0 causal-base / 1.0 distill / 1.2 causal-base（另有 1.0 distill-quant） |
| 发布日期 | 2026-11-12（HF `createdAt`：Duo-1.2-causal-base 06:30Z、Duo-1.0-distill 06:32Z、Duo-1.0-causal-base 06:32Z，北京时间 14:30–14:32；量化包 11-13 08:09Z） |
| 官方链接 | https://huggingface.co/inclusionAI/Duo-1.0-causal-base |
| PDF 链接 | —（技术报告见 arXiv） |
| arXiv id | 2611.15131（模型卡徽章指向该文） |
| SHA-256 | — |
| 页数 | — |

## 摘要

InclusionAI 在 Hugging Face 上发布 Duo 权重集合。主卡 `Duo-1.0-causal-base` 写明这是面向实时音视频交互的全双工多模态世界模型，包里包含 Realization 权重与骨干、Intent 模型与 adapter、视频/音频 codec、语音识别和强制对齐；默认采样 Euler、50 步、flow shift 1.0；实现格式为 PyTorch Distributed Checkpoint。`Duo-1.0-distill` 是四步蒸馏的 Realization 叠加包（默认 Euler、4 步、flow shift 5.0），需先下载 causal-base 再覆盖。`Duo-1.2-causal-base` 卡片写「improved generation quality」，结构与 1.0 causal-base 相同。许可字段为 MiniMax H3 Community License；卡片写权重初始化自 MiniMax H3，再由 Duo 团队训练。技术细节以配套技术报告为准，模型卡本身几乎没有训练数据规模或评测数字。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- [Duo v1 技术报告](../2026-11-11-duo-v1-tech-report/README.md)
