# 2026-10-28 arXiv 精选「最值得先看」

来自 arXiv 2026-10-27（周二）公告批次（编号约 2610.32997–2610.35868）的精选，选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.33420 | An Empirical Study of Reinforcement Learning Scaling Laws | Zeyu Zheng, Clare Lyle, Khimya Khetarpal, Will Dabney | Google DeepMind 在 Starpilot、Craftax 两个程序生成环境里给一个 actor-critic 算法拟合 RL 缩放律，能把最优资源分配和超参外推到约 100 倍算力；发现用 Elo 式分数比平均回报更好预测，并据此在 Craftax 上刷新 SOTA。注意只研究了一种算法、两个游戏环境，不是 LLM RL。 | [arXiv](https://arxiv.org/abs/2610.33420) | [PDF](2610.33420-rl-scaling-laws-elo/paper.pdf) | 待补 |
| 2610.34894 | What Outcome RL Buys: Finishing, Reliability, Rarely Reach | Shan Yang | 把 20 个已发布 RL 推理模型（1.5B–32B）相对其出发的思考模型的 pass@1 提升拆成「在预算内答完」「答完后更可靠」「解出基座 8 次都错的题」三部分：token 预算紧时（4k/8k）约 82% 的变化来自答完；「新能力」在四个数理数据集上至多 +2.1 个点。单作者，限物理和数学题。 | [arXiv](https://arxiv.org/abs/2610.34894) | [PDF](2610.34894-what-outcome-rl-buys/paper.pdf) | 待补 |
| 2610.34593 | What Does World Modeling Actually Improve in Robot Action Learning? | Hanwen Cui, Yuanyuan Li, Qing Guo, Zhida Zhang, Chao Chen, Xi Chen, Jie Cao | 在 FastWAM、OpenWAM 里固定架构、数据和步数，只开关未来视频预测损失：已见任务、干净条件下成功率分别 +24.38 和 +72.91 个点，但在未见任务上提升不稳定、在环境随机化下两者都很低且无一致优势；给 π0.5 加一个只在训练时用的轻量预测头，成功率 82.94%→89.19%。 | [arXiv](https://arxiv.org/abs/2610.34593) | [PDF](2610.34593-world-modeling-robot-action-learning/paper.pdf) | 待补 |
