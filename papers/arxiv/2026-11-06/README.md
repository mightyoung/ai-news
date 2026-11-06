# 2026-11-06 arXiv 精选「最值得先看」

来自 arXiv「Thursday, 5 November 2026」公告批次（cs.LG/CL/AI/CV/RO 新提交，去重后 447 篇，新编号约 2611.05380–2611.06918，抓取于 2026-11-06 09:07 北京时间）的精选，选出最值得先看的 3 篇归档。三篇均不在当日 Hugging Face Daily Papers 精选归档名单中。每篇论文一个文件夹，内含 `paper.pdf`，`深度解析.md` 补齐前显示「待补」。核验列先写「待核」。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.05942 | Reward Budgeting Reduces Premature Convergence in Reinforcement Learning for LLM Reasoning | Mengni Jia, Mengyu Zhou, Xiaoxi Jiang, Guanjun Jiang | RL 做大模型推理时常常很早平台化；只加熵正则未必能改最终平台。作者从隐式目标策略推出锐度因子 κ / κ_eff，并给出可插拔的「奖励预算」优势构造：每个 prompt 分配固定总奖励。摘要称在 Qwen3-8B 与 Llama3.2-3B-Instruct 上可提升多种 RL 基线，AMC23 最高 +12.50、AIME24/AIME25 最高 +10.00（NeurIPS 2026）。首页单位 Qwen Business Unit, Alibaba、University of Cambridge。 | [arXiv](https://arxiv.org/abs/2611.05942) | [PDF](2611.05942-reward-budgeting-llm-reasoning-rl/paper.pdf) | 待核 | [待补](2611.05942-reward-budgeting-llm-reasoning-rl/) |
| 2611.05591 | C-GRPO: Conformal Group Relative Policy Optimization | Arya Fayyazi, Seyedarmin Azizi, Mehdi Kamal, Massoud Pedram | 标准 GRPO 对每条题用固定组大小采样，简单题浪费、难题欠探索。C-GRPO 用共形阈值（conformal prediction，一种给出有限样本覆盖保证的阈值集合方法）把停止规则做成可校准阈值，替换固定 rollout 预算。摘要称在数学、研究生级科学与代码共六个基准上，相对固定预算 GRPO，在准确率相当（pass@1 持平或略高、差异在二项噪声内）时把平均训练 rollout 降 49–70%，跨模型家族最高可省 82% rollout（NeurIPS 2026 会刊自述）。首页单位 University of Southern California。 | [arXiv](https://arxiv.org/abs/2611.05591) | [PDF](2611.05591-c-grpo-conformal-group-relative/paper.pdf) | 待核 | [待补](2611.05591-c-grpo-conformal-group-relative/) |
| 2611.05838 | RACE: Calibrated Cumulative Scoring for Rollout-Free Robot Policy Checkpoint Selection | Changyeon Kim, Yekyung Nah, Kimin Lee | 挑机器人策略检查点若靠真机/仿真 rollout 很贵；验证损失排序又常与部署成功率不一致。RACE 用一组成功参考轨迹做状态条件校准，对动作偏差打分并用连乘累计，实现「不上机也能排序」。仿真 DexMimicGen 上（每源 10 条成功轨迹、每 run 12 个检查点、10 个训练种子均值）RACE 的 Spearman ρ 约 0.78–0.83，明显好于 Validation Loss / MSE；真机三任务（每检查点 30 次部署，共 900 次）也与成功率正相关。首页单位 KAIST、Config。 | [arXiv](https://arxiv.org/abs/2611.05838) | [PDF](2611.05838-race-robot-policy-checkpoint-selection/paper.pdf) | 待核 | [待补](2611.05838-race-robot-policy-checkpoint-selection/) |

## 为什么选这 3 篇

**Reward Budgeting（2611.05942）**：很多人用 GRPO/DAPO 做推理 RL，早期平台化几乎人人会撞上。这篇不把「加熵」当万能药，而是改优势怎么从奖励里构造，AMC/AIME 上有明确百分点增益，且宣称可插到多种基线上——对正在调 LLM RL 的人很实用。

**C-GRPO（2611.05591）**：GRPO 训练成本一大块在固定 G 的重复采样。用共形阈值把「这道题还要不要继续采样」做成有覆盖保证的规则，省一半以上 rollout 还不掉点，是算法与算力效率并重的一条线。

**RACE（2611.05838）**：和 11-04 归档的「Beyond Validation Loss」同一痛点——机器人预训练/微调怎么挑检查点。这篇给出可复现的离线排序指标，仿真与真机都有数字，适合做具身策略训练的人对照。
