# 2026-10-22 arXiv 精选「最值得先看」

来自 arXiv 2026-10-22（周四）公告批次（编号 2610.28637–2610.30136）的补发精选（当天定时任务未运行，10/23 凌晨补齐），选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。以下说明已对照正文核过。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.28707 | SimHack: Predicting the onset of detectable reward hacking before RL training | Junwei Deng, Alex Bie, Natalia Ponomareva | 在跑 RL 之前预测代码 RL 中可检测的奖励作弊何时成为主导：从少量小规模参考训练学出作弊动态，模拟未见配方；摘要报告中位起点相对误差 11.3%、跨配方排名相关 0.85，并能筛出多训 96.6% 才出现作弊的课程。 | [arXiv](https://arxiv.org/abs/2610.28707) | [PDF](2610.28707-simhack-reward-hacking-onset/paper.pdf) | [深度解析](2610.28707-simhack-reward-hacking-onset/深度解析.md) |
| 2610.29348 | Data Schedules and Learning Rate Schedules Should Be Designed Together | Haodong Wen, Kairong Luo, Tingkai Yan 等 | 把预训练到中训练的数据切换看成数据混合调度的特例：学习率持续衰减时更早混入中训练数据更好，恒定学习率下结论反转；建议中训练数据进入后再衰减学习率，并给出理论解释。 | [arXiv](https://arxiv.org/abs/2610.29348) | [PDF](2610.29348-data-and-lr-schedules/paper.pdf) | [深度解析](2610.29348-data-and-lr-schedules/深度解析.md) |
| 2610.29264 | Training in Deployment: Human-in-the-loop Online Post-Training for Robot Manipulation | Chun Gu, Xiaofei Wei, Yiming Chen 等 | TIDE 在部署过程中用人工干预和策略自己的 rollout 在线更新机器人基础模型，不需要 critic、奖励模型或动作打分器；4 个真实双臂任务上优于热启动策略和等量离线示范，每个任务的在线后训练不到 1 小时。 | [arXiv](https://arxiv.org/abs/2610.29264) | [PDF](2610.29264-tide-training-in-deployment/paper.pdf) | [深度解析](2610.29264-tide-training-in-deployment/深度解析.md) |
