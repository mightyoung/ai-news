# InclusionAI · Duo: A Reciprocal World Model for Full-Duplex Interaction

| 项目 | 内容 |
|---|---|
| 厂商 | 标题页为 Ant Group 标志 + Duo 标志（作者行无单位）；项目页页脚 Copyright © 2026 Ant Research；代码与权重组在 inclusionAI 名下。原文未说明上述名称之间的组织关系。 |
| 文档类型 | 技术报告（arXiv 预印本，标题页标注 Technical Report） |
| 模型名与版本 | Duo v1（HF 另有 Duo 1.0 / 1.2 causal-base 与 1.0 distill 权重） |
| 发布日期 | 2026-11-11（arXiv published 2026-11-11T07:17:02Z，北京时间 15:17） |
| 官方链接 | https://arxiv.org/abs/2611.15131 |
| PDF 链接 | https://arxiv.org/pdf/2611.15131 （v1，27 页） |
| arXiv id | 2611.15131 |
| SHA-256 | 4400fb3fe36d3f9941075ac8249cba4978b14c3222a5c75fe28fd9069334a8df |
| 页数 | 27（pdfinfo 物理页） |

## 摘要

这篇技术报告提出 Reciprocal World Model（RWM），并发布全双工世界模型 Duo v1：一边持续接收用户的音视频，一边实时生成助手的音视频回应。系统分成 Intent（交互推理与是否开口）和 Realization（生成对齐的音视频行为）两块。训练分三阶段（均为厂商自报）：Stage 1 对预训练多模态语言骨干做因果监督微调，并写明使用 low-rank adaptation（原文未出现 “LoRA” 字样）训练 Intent；Stage 2 在冻结的 Intent 上训练 Realization 的因果联合音视频生成；Stage 3 用 distribution matching 做四步蒸馏，并以双重 rollout 对齐推理时条件。Realization 模块写明以 (MiniMax, 2026) 的预训练权重初始化，参考文献指向 MiniMax H3 模型卡。流式推理以 17 帧、24 fps 为一块（17/24 ≈ 0.708 秒；Fig. 11 亦标 708 ms）。报告描述单机 8 张 GPU 的调度（Intent 的 VLM 以 TP4 跑在 GPU 0–3，Realization 用全部 8 卡做 4 步去噪再加一次 clean forward；见 PDF 物理第 19 页 Fig. 11）。

录制数据见 Fig. 10(a)（PDF 物理第 17 页，厂商自报）：Synchronous dual-stream 1000 hours、Asynchronous dual-stream 1000 hours、Single-stream 1000 hours、live-stream 100 hours、Duplex-audio 83.3 hours、Open datasets 3.14 hours。正文 §5.2 列出这六类但不再给小时数。「1000 hours」是三个大类的图内标注，不是坐标轴上限；色块面积与标注大致成比例，未见与分项时长对不上的证据。

人工评测为厂商自建：30 个实时双工案例、六项二元标准，180 项中 168 项通过（93.3%，物理第 20 页 §7.1）。语言遵守、语音可懂度、视觉身份稳定性共 90 项全部通过；音视频情感一致 96.7%，唇形与语音对齐 90.0%；内容回应性 73.3%（22/30），是主要失分项（尤其是需要把语音和画面合起来理解的意图）。作者自述 Duo v1「仍是初步的，目前支持基本的音视频对话」。代码与权重见 GitHub `inclusionAI/Duo` 和 HF collection `inclusionAI/duo-v1`。首页：https://duo-v1.github.io/ 。参数量、上下文和 API 价格官方未披露；原文未报告系统卡式安全评测。

## 原文

[report.pdf](report.pdf)（arXiv v1）

## 核验

[✅ 能核实](核验.md)（2026-11-14 T2 标准版）。文档为 arXiv 2611.15131v1，27 页，SHA-256 与归档一致。头条数字均可在原文定位，评测与数据规模均为厂商自报。论文雷达近 7 日未收录本 id。

## 深度解析

[深度解析.md](深度解析.md)。Duo v1 把「是否开口」和「实时出声出画」拆成 Intent 与 Realization，在约 0.71 秒一块的因果时间线上做全双工音视频交互；训练配方较清楚，评测只有 30 例厂商自报，内容回应性 73.3% 是短板。

## 相关文档

- [Duo v1 模型卡（Hugging Face）](../2026-11-12-duo-v1-model-card/README.md)
