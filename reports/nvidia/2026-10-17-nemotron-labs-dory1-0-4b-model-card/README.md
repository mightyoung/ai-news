# NVIDIA · NVIDIA-Nemotron-Labs-Dory1.0-4B 模型卡

| 项目 | 内容 |
|---|---|
| 厂商 | NVIDIA |
| 文档类型 | 模型卡（model-card） |
| 模型名与版本 | NVIDIA-Nemotron-Labs-Dory1.0-4B（BF16） |
| 发布日期 | 2026-10-17（北京时间） |
| 官方链接 | https://huggingface.co/nvidia/NVIDIA-Nemotron-Labs-Dory1.0-4B-BF16 |
| PDF 链接 | 无（HF 模型卡页面） |
| arXiv id | — |
| SHA-256 | — |
| 页数 | — |

> 日期说明：模型卡写 Release Date：October 16, 2026（未注时区）；HF 仓库创建于 2026-10-16 18:25 UTC，即北京时间 2026-10-17 02:25，按北京时间记为 10-17。

## 摘要

Dory1.0-4B 是 NVIDIA 训练的 4B 参数循环（latent-recurrent）normalized-GPT 模型，SWA 与全注意力层交替，通过重复调用共享层块在推理时调节每 token 计算量，支持最长 256K 上下文。模型卡说明预训练 6T token，其中前约 4.5T 用 NVFP4、其余用 BF16，之后再做 300B token 的上下文扩展，随后经 SFT 和多环境 GRPO 强化学习。许可证为 OpenMDW-1.1。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- 暂无同一模型的其他文件夹
