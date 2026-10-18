# 强化学习文献地图阅读清单（2026-10-18）

## 来源

用户在「论文分析群」里发的一张**强化学习文献地图截图**（Experts 栏）里的 9 个条目。截图里的标题有些被截断，完整标题、作者、出处均已从 arXiv / 出版社页面核对补全，不是猜的。要求：逐篇研究，原文上传到仓库。

## 总表

原文上传规则：只上传可合法再分发的原文（arXiv 预印本、开放获取）。订阅期刊文章和版权书**不上传**，改放 `来源.md`，写明官方页面和合法获取方式。

| 序号 | 完整标题 | 作者 | 年份 | 出处 | 原文是否已上传 | 深度解析 | 来源/原文链接 |
|---|---|---|---|---|---|---|---|
| 1 | Soft Actor-Critic: Off-Policy Maximum Entropy Deep Reinforcement Learning with a Stochastic Actor | Haarnoja, Zhou, Abbeel, Levine | 2018 | ICML 2018；arXiv:1801.01290 | 是（arXiv 预印本 v2） | [深度解析](01-1801.01290-soft-actor-critic/深度解析.md) | [arXiv](https://arxiv.org/abs/1801.01290) · [paper.pdf](01-1801.01290-soft-actor-critic/paper.pdf) |
| 2 | Intention-Conditioned Flow Occupancy Models | Zheng, Park, Levine, Eysenbach | 2025（v4：2026-05） | ICLR 2026；arXiv:2506.08902 | 是（arXiv 预印本 v4） | [深度解析](02-2506.08902-intention-conditioned-flow-occupancy-models/深度解析.md) | [arXiv](https://arxiv.org/abs/2506.08902) · [paper.pdf](02-2506.08902-intention-conditioned-flow-occupancy-models/paper.pdf) |
| 3 | SkillBlender: Towards Versatile Humanoid Whole-Body Loco-Manipulation via Skill Blending | Kuang, Geng, Elhafsi, Do, Abbeel, Malik, Pavone, Wang | 2025 | arXiv:2506.09366（仅预印本，未查到正式发表） | 是（arXiv 预印本） | [深度解析](03-2506.09366-skillblender/深度解析.md) | [arXiv](https://arxiv.org/abs/2506.09366) · [paper.pdf](03-2506.09366-skillblender/paper.pdf) |
| 4 | Reinforcement Learning: An Introduction（1998 第一版；第二版 2018） | Richard S. Sutton, Andrew G. Barto | 1998 | MIT Press（书） | **否**（版权书） | [深度解析](04-sutton-barto-rl-introduction-1998/深度解析.md)（章节级概述，未读全书） | [来源.md](04-sutton-barto-rl-introduction-1998/来源.md) · [作者主页](http://incompleteideas.net/book/the-book-2nd.html) |
| 5 | On Convergence of Average-Reward Q-Learning in Weakly Communicating Markov Decision Processes | Yi Wan, Huizhen Yu, Richard S. Sutton | 2024 | arXiv:2408.16262（未查到正式发表） | 是（arXiv 预印本，CC BY 4.0） | [深度解析](05-2408.16262-average-reward-q-learning-weakly-communicating/深度解析.md) | [arXiv](https://arxiv.org/abs/2408.16262) · [paper.pdf](05-2408.16262-average-reward-q-learning-weakly-communicating/paper.pdf) |
| 6 | Human-level control through deep reinforcement learning（DQN） | Mnih, Kavukcuoglu, Silver 等 | 2015 | Nature 518:529–533；DOI 10.1038/nature14236 | **否**（订阅文章，无授权开放版） | [深度解析](06-nature-2015-dqn-human-level-control/深度解析.md)（未读全文，依据官方页面摘要图注 + 前身预印本 1312.5602） | [来源.md](06-nature-2015-dqn-human-level-control/来源.md) · [Nature 官方页面](https://www.nature.com/articles/nature14236) |
| 7 | Olympiad-level formal mathematical reasoning with reinforcement learning（AlphaProof） | Hubert 等（Google DeepMind；含 Hassabis, Kohli, Silver） | 2025（在线）/ 2026（卷期） | Nature 651，2026-03-19；DOI 10.1038/s41586-025-09833-y | 是（开放获取，CC BY 4.0） | [深度解析](07-nature-2025-alphaproof-olympiad-formal-math/深度解析.md) | [来源.md](07-nature-2025-alphaproof-olympiad-formal-math/来源.md) · [paper.pdf](07-nature-2025-alphaproof-olympiad-formal-math/paper.pdf) · [DOI](https://doi.org/10.1038/s41586-025-09833-y) |
| 8 | Online actor–critic algorithm to solve the continuous-time infinite horizon optimal control problem | Kyriakos G. Vamvoudakis, Frank L. Lewis | 2010 | Automatica 46(5):878–888；DOI 10.1016/j.automatica.2010.02.018 | **否**（订阅期刊） | [深度解析](08-automatica-2010-online-actor-critic-ct-optimal-control/深度解析.md)（仅依据摘要） | [来源.md](08-automatica-2010-online-actor-critic-ct-optimal-control/来源.md) · [DOI](https://doi.org/10.1016/j.automatica.2010.02.018) |
| 9 | Initially Excited Asynchronous Reinforcement Learning Control With Monotonicity and Stability | Jiacheng Wu, Wenqian Xue, Frank L. Lewis, Bosen Lian | 2026 | IEEE Trans. Syst., Man, Cybern.: Systems 56(2):1138–1150；DOI 10.1109/TSMC.2025.3647521 | **否**（订阅期刊） | [深度解析](09-ieee-tsmc-2026-initially-excited-async-rl-control/深度解析.md)（仅依据摘要的二手概述） | [来源.md](09-ieee-tsmc-2026-initially-excited-async-rl-control/来源.md) · [DOI](https://doi.org/10.1109/TSMC.2025.3647521) |

## 阅读深度说明

- **读了全文**：第 1、2、3、5、7 篇（pdftotext 全文，数字对照表格核对；第 5 篇 §5–7 的证明没有逐行验证；第 7 篇的 Supplementary 不在 PDF 内，未读）。
- **没读全文**：第 4 篇（只读第一版在线目录与三节正文）、第 6 篇（官方页面摘要/图注/参考文献 + 前身预印本）、第 8、9 篇（仅摘要；第 9 篇连摘要原文都没拿到，只有概述）。这些解析里都标明了「未读全文」。

## 为什么有 4 篇没传原文

- 第 4 篇：MIT Press 版权书。
- 第 6、8、9 篇：订阅期刊，没有找到作者/出版社授权的开放版本。第三方镜像站（课程主页、个人站点）不属于明确授权来源，没有使用。
- 合法获取入口见各自的 `来源.md`。
