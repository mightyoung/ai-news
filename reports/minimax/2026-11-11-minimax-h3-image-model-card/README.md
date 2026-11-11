# MiniMax · MiniMax-H3-Image 模型卡（Hugging Face）

| 项目 | 内容 |
|---|---|
| 厂商 | MiniMax |
| 文档类型 | 模型卡（model-card） |
| 模型名与版本 | MiniMax-H3-Image（另有可选提示扩写模型 H3-Image-PE） |
| 发布日期 | 2026-11-11（北京时间） |
| 官方链接 | https://huggingface.co/MiniMaxAI/MiniMax-H3-Image |
| PDF 链接 | 暂无技术报告 |
| arXiv id | — |
| SHA-256 | — |
| 页数 | —（网页） |

> 日期说明：HF API 显示仓库创建于 2026-11-03，PE 模型创建于 2026-11-08；公开发布以官方博客日期 2026-11-11 记。

## 摘要

模型卡写明 H3-Image 把文生图和图像编辑统一在一个检查点；输出约 16 百万像素（4096×4096 至 6272×2688），不用放大器；检查点蒸馏到 6 个采样步（6 NFE），不使用无分类器引导。扩散 Transformer（DiT）为 H3 架构去掉音频层，33.1B 参数、50 层、单流稠密；文本编码器沿用 MiniMax-H3 的 Qwen3-VL 文本编码器，取第 50 层隐藏状态；VAE 为 16 倍下采样、24 个潜在通道。BF16 DiT 约 68.65 GB；PE 模型 NVFP4 约 17.9 GB。许可为 MiniMax-H3-Image Community License（license: other）。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- [MiniMax H3-Image 官方博客](../2026-11-11-minimax-h3-image-blog/README.md)
