# 2026-11-04 arXiv 精选「最值得先看」

来自 arXiv「Tuesday, 3 November 2026」公告批次（cs.LG/CL/AI/CV/RO 新提交与交叉列表，去重后 1410 篇，新编号约 2611.00003–2611.03648，抓取于 2026-11-04 09:07 北京时间）的精选，选出最值得先看的 3 篇归档。三篇均不在当日 Hugging Face Daily Papers 榜上。每篇论文一个文件夹，内含 `paper.pdf`，`深度解析.md` 补齐前显示「待补」。下表数字已于 9:40 对照正文核验（页码为 PDF 物理页），结论见「核验」列。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.02404 | When Rewards Depend on the Group, GRPO Plays a Tournament | Junyi Gao, Yu Shi, Pingzhao Hu, Ewen M Harrison | 当奖励依赖同组其他回答（比如「多样性奖励」），GRPO 的组内基线会悄悄改变优化目标：每个回答被训练成在组内「零和比赛」中打败同伴，组大小 K=2 时完全看不到两两多样性奖励。作者给出修正版 Team-GRPO。摘要称理论能把 9B 策略的不动点预测到 ℓ1 误差 0.02 以内（单字母四选项沙盒，12 次运行最大 0.018，p5），在 GlobalOpinionQA 上 GRPO 塌到多数答案，Team-GRPO 把与人类意见分布的平方误差从未训练模型的 0.20 降到 0.08（同设置下 GRPO 升到 0.49；K=2、200 步、510 道未见过的题，表 2 p6）。首页单位 University of Edinburgh、University of Toronto、Health Data Research UK、Western University。 | [arXiv](https://arxiv.org/abs/2611.02404) | [PDF](2611.02404-grpo-plays-a-tournament/paper.pdf) | ✅ 能核实（0.20 是未训练模型的误差，GRPO 同设置升到 0.49，表 2 p6） | [待补](2611.02404-grpo-plays-a-tournament/) |
| 2611.01565 | Beyond Validation Loss: Coverage and Reliability Dynamics in Robot Policy Pretraining | Zhanyi Sun, Max Simchowitz, Shuran Song | 机器人策略「预训练再后训练」时，验证损失和平均成功率选不出好底座。作者用闭环 pass@k（同一初始条件跑 k 次至少成功一次）衡量「成功还够不够得着」，发现 pass@1 相近、大 k pass@k 不同的检查点后训练效果不同，且 pass@k 在预训练中途就会见顶；据此提出离线选检查点准则和生成式数据增强。摘要未给具体数字。首页单位 Stanford University、Carnegie Mellon University。 | [arXiv](https://arxiv.org/abs/2611.01565) | [PDF](2611.01565-beyond-validation-loss-robot-pretraining/paper.pdf) | ✅ 能核实（主要结论来自仿真；真机只有 Push-T 一个任务、20 个初始状态×5 次，p10） | [待补](2611.01565-beyond-validation-loss-robot-pretraining/) |
| 2611.02104 | Consolidating Reasoning with Test-Time Training | Haotian Wu, Zeming Chen, Hao Zhao, Antoine Bosselut | 多个模型各自推理后，常见做法是投票或把所有推理过程塞进上下文。TTT-Consolidate 改为在测试时把这些推理轨迹「训练进」一个小 LoRA 适配器，再让模型据此写最终答案，并用元学习学怎么压缩。作者构建了 12,810 道数学题、六个模型轨迹的 OpenParallelThinking 语料。摘要称比最好的聚合基线高最多 20 个百分点，但引言写的是「平均最多 20%」（p2）；最大增益出现在 8 条轨迹全错、投票只能得 0 分的设置（十个基准平均 +22.6/+10.6，表 1 p6），基座只用 Qwen3-1.7B/4B（p8）；算力对齐比较见 p7。NeurIPS 2026（arXiv 备注自述）。首页单位 EPFL。 | [arXiv](https://arxiv.org/abs/2611.02104) | [PDF](2611.02104-consolidating-reasoning-test-time-training/paper.pdf) | ⚠️ 部分核实：「最多 20 个百分点」摘要与引言（p2 写 20%）口径不一，最大增益出自 8 条轨迹全错的设置（p6）；代码与数据尚未发布 | [待补](2611.02104-consolidating-reasoning-test-time-training/) |

## 为什么选这 3 篇

**GRPO Plays a Tournament（2611.02404）**：GRPO 是现在大模型 RL 后训练最常用的算法之一，很多人会顺手往奖励里加「多样性」「覆盖率」。这篇用一个很短的推导说明，这类奖励下 GRPO 的组内基线会把目标扭成组内零和比赛，K=2 时多样性奖励完全被抵消；修法只是把一个系数从 −1/(K−1) 改成 +1。对正在用 GRPO 做多样性或分布对齐的人，属于「改一行就可能换一个结果」的提醒。

**Beyond Validation Loss（2611.01565）**：机器人模仿学习里大家习惯看验证损失或平均成功率来挑检查点，这篇说明这样会挑错后训练的底座。它把大模型推理里流行的 pass@k 视角搬到机器人闭环评测，给出「覆盖度与可靠性此消彼长」的观察和一个不用上真机就能用的离线挑选准则，对做具身后训练的人很实用。

**Consolidating Reasoning with Test-Time Training（2611.02104）**：多智能体或多次采样推理的「结果怎么合并」是很实际的问题。这篇不投票、不拼长上下文，而是在测试时用 LoRA 把轨迹压进参数，算力对齐下最多 +20 个百分点，并会公开数据集；适合想了解测试时训练（TTT）和推理聚合的读者。
