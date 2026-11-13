# Hugging Face 热门论文 — 2026-11-13

> 批次说明：HF 接口不接受 2026-11-13，用的是 2026-11-12 批次（抓取时共 21 篇）。按 `paper.upvotes` 排序，结合研究价值挑 5 篇，并避开近几天已推荐的。序号只是挑选顺序，不是 HF 榜单名次。机构按论文首页署名。

| # | 论文 | 👍 | 机构 | 链接 | 核验 | 本地 |
|---|---|---|---|---|---|---|
| 1 | **Scaling Mathematical Proof Supervision from Structured Textbooks**<br>TOME-Math：用结构化教材扩大数学证明监督数据 | 39 | 中国科学技术大学；复旦大学；上海人工智能实验室；上海交通大学（按论文首页编号顺序） | [HF](https://huggingface.co/papers/2610.40394) · [arXiv](https://arxiv.org/abs/2610.40394) | ✅ 能核实 | [PDF](2610.40394-tome-math-textbook-proof-supervision/paper.pdf) · [深度解析](2610.40394-tome-math-textbook-proof-supervision/深度解析.md) |
| 2 | **SteerDistill: Quantizing LLM Agents via Closed-Loop Teacher Steering**<br>SteerDistill：用闭环教师引导量化 LLM 智能体 | 31 | 清华大学智能产业研究院（AIR）；中国科学技术大学 | [HF](https://huggingface.co/papers/2611.13410) · [arXiv](https://arxiv.org/abs/2611.13410) | ✅ 能核实 | [PDF](2611.13410-steerdistill-quantized-llm-agents/paper.pdf) · [深度解析](2611.13410-steerdistill-quantized-llm-agents/深度解析.md) |
| 3 | **Incentivizing Self-Learning in Large Language Models via Reinforcement Learning**<br>通过强化学习激励大模型“自学” | 27 | 上海人工智能实验室；上海交通大学；香港中文大学；中国科学技术大学；复旦大学 | [HF](https://huggingface.co/papers/2610.39671) · [arXiv](https://arxiv.org/abs/2610.39671) | ✅ 能核实 | [PDF](2610.39671-self-learning-llm-reinforcement-learning/paper.pdf) · [深度解析](2610.39671-self-learning-llm-reinforcement-learning/深度解析.md) |
| 4 | **Read Less, Solve More: Token-Efficient Sparse Reading of External Content for AI Agents**<br>少读多解：面向 AI 智能体的稀疏读取 | 18 | 中国科学院大学；中国科学院计算技术研究所；松山湖材料实验室 | [HF](https://huggingface.co/papers/2608.22237) · [arXiv](https://arxiv.org/abs/2608.22237) | ✅ 能核实 | [PDF](2608.22237-sparseread-token-efficient-agent-reading/paper.pdf) · [深度解析](2608.22237-sparseread-token-efficient-agent-reading/深度解析.md) |
| 5 | **GTAGym: Real AAA Game Tasks Environment for Evaluation and Reinforcement Learning**<br>GTAGym：真实 3A 游戏任务的评测与强化学习环境 | 12 | 上海创智学院；复旦大学（OpenMOSS） | [HF](https://huggingface.co/papers/2611.13028) · [arXiv](https://arxiv.org/abs/2611.13028) | ✅ 能核实 | [PDF](2611.13028-gtagym-aaa-game-rl-environment/paper.pdf) · [深度解析](2611.13028-gtagym-aaa-game-rl-environment/深度解析.md) |

> 核验（2026-11-13，标准版）：5 篇均能核实。关键限定：TOME-Math 的 6 个评测含 2 个自建、AIME 排第二、语料未发布（p5–p6）；SteerDistill 的 1.84 点来自训练曲线检查点（p7）；Self-Learning 用 LLM 判分、626 题（p5–p6）；SparseRead 的 97% 是 30 个设置中的 29 个、中位数省 61.4% token（p7）；GTAGym 的 103 个 3D 任务是 Babylon.js 重建环境，15%→23% 基于 100 个原生 GTA V 任务（p4、p8）。页码为 PDF 物理页。
