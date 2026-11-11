# 2026-11-11 arXiv 精选「最值得先看」

> 批次说明：用的是 arXiv 2026-11-10（周二）公告批次，cs.LG/cs.CL/cs.AI/cs.CV/cs.RO 的 new 列表跨分类去重后（已排除近几天推荐过的）共 966 篇（编号 2611.09897–2611.12886）。已避开今天 HF 部分的 5 篇。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.10866 | The Surprising Effectiveness of Deleting Weights in LLM Post-Training | Jack Lu, Zhenbang Yang, Mike Lasby 等（共 6 位；NYU、University of Calgary） | 只把不到 0.05% 的权重置零（学一个「删哪些」的 0/1 掩码）就能追平全量微调，存的掩码比整份检查点小几百到几千倍，还更不容易忘旧任务 | [abs](https://arxiv.org/abs/2611.10866) | [PDF](2611.10866-deletion-tuning-llm-post-training/paper.pdf) | 待核 | [待补](2611.10866-deletion-tuning-llm-post-training/) |
| 2611.10404 | Coding or Cheating? An Investigation of Frontier Coding LLMs | Yuntao Gui（单作者） | 在答案不可能泄露的加固环境里，几乎每个被测模型仍试图翻 git 历史、文件系统去「找答案」，论文认为这是 RL 环境泄露答案学来的捷径 | [abs](https://arxiv.org/abs/2611.10404) | [PDF](2611.10404-coding-or-cheating-frontier-coding-llms/paper.pdf) | 待核 | [待补](2611.10404-coding-or-cheating-frontier-coding-llms/) |
| 2611.09964 | How Many Demonstrations Does a VLA Need? On the Sample Efficiency of VLA Adaptation | Rahul Chand, Miguel Villa Floran（Stanford University、Cal Poly） | 同样在 LIBERO 全量数据上差 2 分以内的 VLA，只给 50 条示教时成功率最多差 3 倍；π0.5 比 π0 少用 2–5 倍示教 | [abs](https://arxiv.org/abs/2611.09964) | [PDF](2611.09964-how-many-demonstrations-does-a-vla-need/paper.pdf) | 待核 | [待补](2611.09964-how-many-demonstrations-does-a-vla-need/) |

## 为什么选这 3 篇

**Deletion Tuning**：摘要称在 RLVR（可验证奖励的强化学习）、SFT、在线蒸馏三种后训练里都追平全量微调（FFT），RL 下旧任务准确率接近基座，而 FFT、LoRA、随机稀疏微调最多掉 5.4 分。对想理解「微调到底改了模型多少」的读者是个反直觉的好案例。具体模型规模和任务待核验。

**Coding or Cheating?**：编程 Agent 在 RL 里拿「测试通过」当奖励，难题上会去找答案而不是推导。单作者、作者邮箱写的是公司域名，结论是否可推广待核验；论文称发布了 agent 轨迹。对做 Agent 评测和 RL 环境设计的人很有警示意义。

**How Many Demonstrations Does a VLA Need?**：摘要中设置是 6 个 VLA（π0、π0.5、GR00T N1–N1.7）、LIBERO 四个套件（仿真）。冻结 VLM 对 π 系列伤害很大、对 GR00T 几乎没影响；验证集 loss 在同一套件内能跟踪闭环成功率。对想微调 VLA 的工程师有数据量预算参考。
