# 2026-10-21 arXiv 精选「最值得先看」

来自 arXiv 2026-10-20（周二）公告批次（编号 2610.23857–2610.26863）的工作日精选，四个方向各挑 3–4 篇后选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.24663 | What RL Brings to Reasoning: A Few Decisions the Base Model Would Not Make | Siyu Zhang, Yuquan Lu, Yoshua Y. Li 等 | 在 Qwen3-4B-Base 与其 RL 版本上做解码干预：只在两者贪心选择不同的约 4% 位置借用 RL 模型的 token，就能找回 AIME 上 90.5% 的 pass@1 提升，说明 RLVR 带来的是少量关键决策。 | [arXiv](https://arxiv.org/abs/2610.24663) | [PDF](2610.24663-what-rl-brings-to-reasoning/paper.pdf) | [深度解析](2610.24663-what-rl-brings-to-reasoning/深度解析.md) |
| 2610.23946 | How Data Scales in Agentic Reinforcement Learning: Laws and Synthesis Strategies | Bowei He, Yankai Chen, Xiaokun Zhang 等 | 把智能体 RL 数据拆成任务、环境、轨迹三个轴分别拟合缩放规律，测到的扩展指数排序是环境 > 任务 > 轨迹，按此分配预算在一个留出点上比只堆轨迹的配方算力效率高 1.7 倍（比 Chinchilla 式配方高 1.4 倍）。 | [arXiv](https://arxiv.org/abs/2610.23946) | [PDF](2610.23946-data-scaling-agentic-rl/paper.pdf) | [深度解析](2610.23946-data-scaling-agentic-rl/深度解析.md) |
| 2610.26863 | Text-to-Image Generative Modeling Without Language Pretraining | Keshigeyan Chandrasegaran, Yue Zhao, Armin W. Thomas 等 | 用 1 亿图文对从零预训练（文本 tokenizer 另用 OpenWebText 训练）早融合自回归模型 Halcyon，0.52B 版 gFD 优于 LlamaGen-XL/8，含语言预训练的总预训练算力少 18.2 倍（其中 93.6% 是基线 FLAN-T5-XL 的语言预训练；只比视觉侧约少 27%），GenEval 44.9 vs 30.5，受控实验显示纯文本预训练对文生图没有帮助。 | [arXiv](https://arxiv.org/abs/2610.26863) | [PDF](2610.26863-t2i-without-language-pretraining/paper.pdf) | [深度解析](2610.26863-t2i-without-language-pretraining/深度解析.md) |
