# 2026-10-19 arXiv 精选「最值得先看」

来自 arXiv 2026-10-16（周五）公告批次（主要为 10-15 提交）的工作日精选，四个方向各挑 3–4 篇后选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（三篇深度解析均已完成，见下表「深度解析」列链接）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.22019 | Priming Base Models for Agentic Post-Training: An Open Midtraining Recipe | Soumye Singhal, Joseph Jennings, Ka Shun Shum 等 | 少见地公开了"中训练"阶段怎么做：256K 上下文、几千亿 token 的真实软件工程数据，同样 SFT 后 Nemotron 3.5 Lightning 的 SWE-bench Verified 从 60.7 提到 64.5，还附了消融和评测协议。 | [arXiv](https://arxiv.org/abs/2610.22019) | [PDF](2610.22019-priming-base-models-agentic-midtraining/paper.pdf) | [深度解析](2610.22019-priming-base-models-agentic-midtraining/深度解析.md) |
| 2610.20898 | Wrong Votes, Right Gradients: Why Majority-Vote Rewards Track Verifiable RL | Dylan P. Wilson, Chengsong Huang, Jiaxin Huang | 解释了为什么"多数投票当奖励"的自训练 RL 能接近可验证奖励：关键不是标签错多少，而是错误在不同题目之间是否同向，随机翻转 30% 标签更新方向几乎不变（前提：这只是 Qwen3-1.7B-Base 初始化点上的期望更新方向，即与金标准更新的余弦，不是训练结果；30% 一档没有置信区间，有区间支撑的最高是 20%）。 | [arXiv](https://arxiv.org/abs/2610.20898) | [PDF](2610.20898-wrong-votes-right-gradients/paper.pdf) | [深度解析](2610.20898-wrong-votes-right-gradients/深度解析.md) |
| 2610.22342 | Spark-0: Scaling Spatially Aligned Tactile Pretraining for Robot Dexterous Manipulation | Tianxing Chen, Wenwei Lin, Chuqiao Lyu 等 | 用 1000 小时全手触觉人类操作数据做预训练监督，即使部署时只用视觉，Ego Humanoid 成功率也从 52.5% 升到 71.7%，说明触觉还能当可扩展的预训练信号。 | [arXiv](https://arxiv.org/abs/2610.22342) | [PDF](2610.22342-spark-0-tactile-pretraining-dexterous/paper.pdf) | [深度解析](2610.22342-spark-0-tactile-pretraining-dexterous/深度解析.md) |
