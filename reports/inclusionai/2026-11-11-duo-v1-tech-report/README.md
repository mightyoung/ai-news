# InclusionAI · Duo: A Reciprocal World Model for Full-Duplex Interaction

| 项目 | 内容 |
|---|---|
| 厂商 | InclusionAI（inclusionai） |
| 文档类型 | 技术报告（arXiv 预印本，标题页标注 Technical Report） |
| 模型名与版本 | Duo v1（HF 另有 Duo 1.0 / 1.2 causal-base 与 1.0 distill 权重） |
| 发布日期 | 2026-11-11（arXiv published 2026-11-11T07:17:02Z，北京时间 15:17） |
| 官方链接 | https://arxiv.org/abs/2611.15131 |
| PDF 链接 | https://arxiv.org/pdf/2611.15131 （v1，27 页） |
| arXiv id | 2611.15131 |
| SHA-256 | 4400fb3fe36d3f9941075ac8249cba4978b14c3222a5c75fe28fd9069334a8df |
| 页数 | 27（pdfinfo 物理页） |

## 摘要

这篇由 InclusionAI 署名的技术报告提出 Reciprocal World Model（RWM），并发布全双工世界模型 Duo v1：一边持续接收用户的音视频，一边实时生成助手的音视频回应。系统分成 Intent（交互推理与是否开口）和 Realization（生成对齐的音视频行为）两块。训练分三阶段（均为厂商自报）：Stage 1 用因果监督微调 Intent（对预训练多模态语言骨干做 LoRA）；Stage 2 在冻结的 Intent 上训练 Realization 的因果联合音视频生成；Stage 3 用 distribution matching 做四步蒸馏，并用双重 rollout 对齐推理时的条件。Realization 的预训练骨干初始化自 MiniMax H3（报告 Related Work / 架构处写明）。流式推理以 17 帧、24 fps 为一块（约 0.708 秒），报告描述了在 8 张 GPU 上的调度（Intent TP4 在 GPU 0–3，Realization 用全部 8 卡做 4 步去噪）。录制数据时长图中可见 duplex-audio 83.3 hours、live-stream 100 hours、open datasets 3.14 hours，另有若干类别标注 1000 hours（厂商自报，排版需对照原图核对）。人工评测写了 30 个实时双工案例，结论称语言、语音和身份检查已通过，但意图理解（尤其是语音与画面合起来才清楚的情况）仍是下一代重点；作者自述 Duo v1「仍是初步的，目前支持基本的音视频对话」。代码与权重见 GitHub `inclusionAI/Duo` 和 HF collection `inclusionAI/duo-v1`。首页：https://duo-v1.github.io/

## 原文

[report.pdf](report.pdf)（arXiv v1）

## 核验

待核

## 深度解析

待补

## 相关文档

- [Duo v1 模型卡（Hugging Face）](../2026-11-12-duo-v1-model-card/README.md)
