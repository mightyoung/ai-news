# 2026-11-10 arXiv 精选「最值得先看」

> 批次说明：用的是 arXiv 2026-11-09（周一）公告批次，cs.LG/cs.CL/cs.AI/cs.CV/cs.RO 的 new 列表跨分类去重后共 403 篇（编号 2611.08490–2611.09894）。已排除近 7 天推荐过的论文，也避开了今天 HF 部分的 5 篇（含 Video-Coder）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.08946 | Flex-RSI: Benchmarking Recursive Self-Improvement of Frontier Agents | Jingdong Zhang, Jionghao Wang, Zhengming Yu 等（共 22 位） | 把「Agent 自己改自己的工作流程（harness）」做成带固定预算的基准，覆盖感知、机器人动作、3D 重建等任务 | [abs](https://arxiv.org/abs/2611.08946) | [PDF](2611.08946-flex-rsi-recursive-self-improvement-benchmark/paper.pdf) | ✅ 能核实（描述与摘要 p1、Fig.1b p2 一致：24 个任务、六个领域） | [深度解析](2611.08946-flex-rsi-recursive-self-improvement-benchmark/深度解析.md) |
| 2611.09798 | Test-Time Compute Scales Better with Parallel Agent Teams | Junlin Wang, Haozhe Chen, Ang Li 等（共 5 位） | 同样的算力预算下，「很多个小团队并行、取最好」比「很多单兵」或「一个大团队」更划算 | [abs](https://arxiv.org/abs/2611.09798) | [PDF](2611.09798-test-time-compute-parallel-agent-teams/paper.pdf) | ⚠️ 部分核实（数字与摘要 p1、Fig.2 p2 一致；大团队只在 4 个任务上跑 1–5 次；论文给的代码仓库当前 404） | [深度解析](2611.09798-test-time-compute-parallel-agent-teams/深度解析.md) |
| 2611.09670 | Goodhart in the Planner: Sampling-Based Control Exploits Rewards Learned from Human Preferences | Soovadeep Bakshi, Apurba Bose（共 2 位） | 机器人用「人类偏好学来的奖励模型」去搜索动作时，搜得越狠真实表现越差，并给出理论解释 | [abs](https://arxiv.org/abs/2611.09670) | [PDF](2611.09670-goodhart-in-the-planner/paper.pdf) | ✅ 能核实（76% 与 0/20 vs 10/10 对应 Table 1 p8；仿真，人类标签来自两位作者） | [深度解析](2611.09670-goodhart-in-the-planner/深度解析.md) |

## 为什么选这 3 篇

**Flex-RSI**：RSI（递归自我改进）常被说得很玄，这篇把它拆成可测的流程：执行器改解法、只有验证集分数更高才保留，再由改进器改 harness（提示词、工具、记忆、控制循环）。适合想知道「Agent 自我进化到底有没有用」的读者。

**Parallel Agent Teams**：摘要里的设置是 27B 模型、100 个 agent 预算、12 个长任务（GPU 内核、形式化证明等）：10 人小队并行在 12 个任务中的 10 个上胜过 100 个单兵，并在跑了大团队对照的 4 个任务上全部胜过 100 人大团队。对做 Agent 工程的人，是现成可借鉴的算力分配思路。

**Goodhart in the Planner**：摘要中，在 HalfCheetah、Hopper、Meta-World 上，更强的 MPPI 搜索让真实回报最多下降 76%，人类标签下抽屉任务 0/20 成功，而起点的克隆策略是 10/10。是对「奖励模型 + 搜索」做法的一个提醒。
