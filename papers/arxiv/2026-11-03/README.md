# 2026-11-03 arXiv 精选「最值得先看」

来自 arXiv「Monday, 2 November 2026」公告批次（cs.LG/CL/AI/CV/RO 新提交与交叉列表，编号约 2610.40662–2610.42152，抓取于 2026-11-03 09:05 北京时间）的精选，选出最值得先看的 3 篇归档。三篇均不在当日 Hugging Face Daily Papers 榜上。每篇论文一个文件夹，内含 `paper.pdf`，`深度解析.md` 补齐前显示「待补」。下表数字均出自论文摘要，已于 2026-11-03 对照原文核验，结论见「核验」列。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2610.41073 | bf16 Rounding Silently Discards Most RL Policy Updates: A Hidden Training-Inference Mismatch and an Unbiased One-Line Fix | Andrew Gao, William Gao | 指出大模型 RL 后训练里一个容易被忽略的数值问题：优化器用 fp32 主权重，生成数据用 bf16 副本，按「四舍五入到最近」转换时大部分小更新被直接抹掉。摘要称在 Qwen3-1.7B 上每步只有 0.4–0.5% 的部署权重真正改变，生成数据的策略比优化器落后 50–150 步。修法 Fair Cast 只改导出那一行（随机舍入或误差反馈），1.7B 参数每次导出多花 22–38 ms；Qwen3-0.6B 到 4B、AdamW 与 Muon 的 25 组配对种子里 18 胜 6 平 1 负，平均高 6.1 个百分点（多数配置单种子，主要由 zebra 的 +24 拉高）；zebra 谜题上 4 次运行 0.57±0.16，对照组塌到 0.33±0.10。首页单位 Stanford University。 | [arXiv](https://arxiv.org/abs/2610.41073) | [PDF](2610.41073-bf16-rounding-discards-rl-updates/paper.pdf) | ⚠️ 部分核实（数字与原文一致，但多数对照单种子，+6.1 主要来自 zebra +24，表 2 p7） | [深度解析](2610.41073-bf16-rounding-discards-rl-updates/深度解析.md) |
| 2610.41857 | When the Simulator Fails, Not the Policy: Auditing Contact Artifacts in Simulated Robot Benchmarks | Alex Zhou, Junhao Wu, Xueyang Zhou, Yixiao Huo, Hongcheng Gao, Di Zhu, Zhenghao Zhang, Yongchao Chen | 机器人仿真基准里很多「失败」其实是物理引擎把已放好的物体弹飞了。作者做了审计插件 SimuGuard（支持 LIBERO、RoboTwin、RoboCasa、RoboDojo），在 RoboTwin 上追到碰撞检测里一个面积阈值常数；只改这个常数，每 100 个回合里有异常的从 12 个降到 0，五个容器任务成功率从 89% 升到 98%（LingBot-VA，每任务 20 回合，仿真；作者配对检验 p=0.11）。还建议无法换引擎的基准同时报告区间，例如作者按基准原样跑出的 LingBot-VA 83.1%，在把被标记回合全算失败或全算成功时落在 75.8%–98.5% 之间。首页单位清华大学人工智能学院、中国科学院大学。 | [arXiv](https://arxiv.org/abs/2610.41857) | [PDF](2610.41857-simulator-contact-artifacts-robot-benchmarks/paper.pdf) | ⚠️ 部分核实（89%→98% 仅 LingBot-VA 5 任务×20 回合仿真，配对检验 p=0.11，表 3 p8；代码无 LICENSE） | [深度解析](2610.41857-simulator-contact-artifacts-robot-benchmarks/深度解析.md) |
| 2610.41720 | UpLoop: Training Looped Transformers via Upcycling at No Extra Pretraining Compute | Cheng Liang, Tengfei Zhang, Ya Zhang, Yanfeng Wang, Zhouhan Lin | 「循环 Transformer」让同一组层重复跑多遍来加深推理，但每多一遍训练算力就多一份。UpLoop 先训浅模型、再复制层逐步加深，把前期省下的算力留给后期的循环，最终参数量、训练 token 数和训练 FLOPs 都与普通稠密基线完全对齐。摘要称 1.3B 规模下 22 个下游任务平均分从 22.99 升到 27.52（单种子，主要由变量赋值两项 +33.0/+24.6 带动），SFT 后数学推理也有提升。 | [arXiv](https://arxiv.org/abs/2610.41720) | [PDF](2610.41720-uploop-looped-transformers-upcycling/paper.pdf) | ⚠️ 部分核实（单种子；平均分涨幅主要来自 VarAssign 两项，表 2 p6；未给代码） | [深度解析](2610.41720-uploop-looped-transformers-upcycling/深度解析.md) |

## 为什么选这 3 篇

**bf16 舍入（2610.41073）**：做 GRPO/PPO 一类 RL 微调的人几乎都用 fp32 主权重加 bf16 推理，这篇说的问题很可能在自己的训练里也存在，而且修法只有一行，成本很低，适合当作「先读再试」的工程类论文。要留意的是结果只到 4B 模型，核验结果：指标是贪心解码的留出集准确率，增益集中在长 rollout 逻辑任务（zebra +24），短答案和接近满分的任务两者差不多（表 2，PDF 第 7 页）。

**仿真接触伪影（2610.41857）**：它提醒读者，机器人论文里的仿真成功率不一定可信，失败可能是引擎的锅。对想入门具身智能、准备跑 LIBERO 或 RoboTwin 的人很实用，也给了具体的排查工具。根因只在 RoboTwin（PhysX 5.3.1 及更早版本）上追到，别的基准是否同样严重要看正文。

**UpLoop（2610.41720）**：在算力完全对齐的前提下比较循环模型和稠密模型，比较方式公平，思路（先小后大、复制层）也好懂，适合理解「预训练怎么省算力」。最大规模只有 1.3B，平均分绝对值不高，能否放大到更大模型还不知道。
