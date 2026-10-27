# 2026-10-27 arXiv 精选「最值得先看」

来自 arXiv 2026-10-26（周一）公告批次（编号 2610.31673–2610.32982）的精选，选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.31859 | Full-Weight VLA Fine-Tuning Without an fp32 Master Copy Silently Erases Most Updates | Shubham Singh | 指出用 bf16 存可训练权重、又不留 fp32 主副本时，AdamW 会把小于权重 1/512 的更新直接舍掉；作者称 12 个开源 VLA 代码库中有 9 个的默认或文档配方这样训练。在 LIBERO 上加回 fp32 副本后，π0.5 默认学习率下成功率从 89.0% 升到 97.7%；4.3%→49.3%（SmolVLA）和 5.1%→80.9%（π0.5）这两组大幅提升是在十倍低学习率、模型欠训练的设置下，SmolVLA 默认学习率下只提升 4.2–10.2 个点。单作者、仅 LIBERO 仿真。 | [arXiv](https://arxiv.org/abs/2610.31859) | [PDF](2610.31859-vla-fp32-master-copy/paper.pdf) | 待补 |
| 2610.31867 | Rewriting Scaling Laws for Synthetic Data with Compute and Data Constraints | Nicholas Roberts, Ahmed Ahmed, Suhas Kotha, Percy Liang, Yu Wang, Alex Renda, Nitya Mani | 把「用模型改写预训练文档」纳入缩放律并计入改写算力：最优改写占比随算力从 3e18 FLOPs 时不到 10% 升到 1e22 FLOPs 时 32%；外推 33 倍算力训练的 22B 模型最终 loss 与预测相差 1.1% 以内，且在若干网页领域的 BPB 优于改写器（训练算力约为其 1/10）。数据受限设定下，用同尺寸改写器改写自身预训练数据，在 3B 及以下各尺寸都胜过只用自然数据的最好结果。 | [arXiv](https://arxiv.org/abs/2610.31867) | [PDF](2610.31867-rewriting-scaling-laws-synthetic-data/paper.pdf) | 待补 |
| 2610.32951 | Where Rounding Happens Matters: Rounding-Location Alignment Stabilizes LLM Reinforcement Learning | Yijing Ke, Tianle Cai, Ruosong Wang | 推理与训练框架分离时，即便权重相同、都用 BF16，实现差异也会让 on-policy 更新变成 off-policy 并导致崩溃。作者只在 RoPE、SwiGLU、残差 RMSNorm 三处让训练端的舍入位置与推理端对齐（中间量保留 FP32），在四个 Qwen 系模型上避免了默认 BF16 基线的崩溃；在所研究的运行中只对齐 RoPE 也足够。不改推理引擎、矩阵乘/注意力内核和训练目标。 | [arXiv](https://arxiv.org/abs/2610.32951) | [PDF](2610.32951-rounding-location-alignment-rl/paper.pdf) | 待补 |
