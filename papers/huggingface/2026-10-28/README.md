# Hugging Face 热门论文 — 2026-10-28

> 批次说明：Shanghai 当日（2026-10-28，周三）的 Daily Papers 尚未发布；本目录对应 **2026-10-27** HF Daily Papers API 批次（`?date=2026-10-27`，62 篇），按 upvotes 与研究价值筛选，并避开近几日晨报已荐条目。序号为挑选顺序，不是 HF 榜单名次。

| # | 论文 | 👍 | 机构 | 链接 | 本地 |
|---|---|---|---|---|---|
| 1 | **Trajectory2Gym: Decision-Grounded Compositional Interaction Synthesis for Tool-Use Agents**<br>Trajectory2Gym：工具调用智能体的「决策可依据」组合式交互合成 | 336 | 西湖大学（第一单位）、Ant International ✅ 能核实 | [HF](https://huggingface.co/papers/2610.33568) · [arXiv](https://arxiv.org/abs/2610.33568) | [PDF](2610.33568-trajectory2gym/paper.pdf) · [深度解析](2610.33568-trajectory2gym/深度解析.md) |
| 2 | **Trial by Trace: Benchmarking AI Agent Harnesses for Reliability and Failure Attribution**<br>Trial by Trace：智能体 Harness 可靠性与失败归因基准 | 249 | TraceLite AI（团队名；第一单位中科院自动化所，另署中关村学院、中科院信工所、清华、北理工）✅ 能核实 | [HF](https://huggingface.co/papers/2610.32285) · [arXiv](https://arxiv.org/abs/2610.32285) | [PDF](2610.32285-trial-by-trace/paper.pdf) · [深度解析](2610.32285-trial-by-trace/深度解析.md) |
| 3 | **StreamVibe: Proactive Video Agents for Evolving User Intent**<br>StreamVibe：跟随用户意图变化的主动式视频智能体 | 245 | Google（第一单位；一作为 Google 学生研究员，高校为 UCSB）；另署 UCSC、Stanford、Oxford、Emory、Columbia ⚠️ 存疑 | [HF](https://huggingface.co/papers/2610.34662) · [arXiv](https://arxiv.org/abs/2610.34662) | [PDF](2610.34662-streamvibe/paper.pdf) · [深度解析](2610.34662-streamvibe/深度解析.md) |
| 4 | **DynaFlow: Learning Free-Form Multi-Agent Orchestration**<br>DynaFlow：学习自由形式的多智能体编排 | 189 | National University of Singapore（唯一单位）⚠️ 存疑 | [HF](https://huggingface.co/papers/2610.34467) · [arXiv](https://arxiv.org/abs/2610.34467) | [PDF](2610.34467-dynaflow/paper.pdf) · [深度解析](2610.34467-dynaflow/深度解析.md) |
| 5 | **Continual Learning Exam: Benchmarking Long-Horizon RSI and Experiential Learning in LLM Agents**<br>持续学习考试：评测 LLM 智能体的长程 RSI 与经验学习 | 49 | UCL（第一单位，一作与通讯作者均在 UCL；署名 CLE Team）✅ 能核实 | [HF](https://huggingface.co/papers/2610.33956) · [arXiv](https://arxiv.org/abs/2610.33956) | [PDF](2610.33956-continual-learning-exam/paper.pdf) · [深度解析](2610.33956-continual-learning-exam/深度解析.md) |

点赞数抓取于 2026-10-28 09:05（北京时间）。

## 核验状态（2026-10-28）

论文真实性核验助手标准版核验：归档 PDF 与 arXiv v1 的 SHA-256 一致（5/5）。页码为 PDF 物理页。

- **Trajectory2Gym**：✅ 能核实。代码 Apache-2.0。每个任务、每组消融都只跑一次（p5、p7）；Tau1 Airline 是见过的任务（p16 A.2）；「4B 胜 30B」比的是未经 agent 训练的公开 30B-A3B，本文 30B 的训练语料也更大（p16）。
- **Trial by Trace**：✅ 能核实。代码 MIT。59.8–72.0 是 Harness 层宏平均通过率，不是总分（p16）；每格是挑出的一次执行，部分替换重跑（p14）；1,339 条标准中 430 条由 deepseek-v4-flash 评判，无人工一致性估计（p13、p28）；Verification 维度只有 1 个任务。
- **StreamVibe**：⚠️ 存疑。+10.7% / +12.3% 只在摘要出现、论文未给算法；表 2 Dynamic 列 SFT→RL 误报率 49.13→62.93 升高，与 p10 正文「substantially reduces FPR」矛盾；Gemini-3.8-Flash 赢下 18 个逐点列中的 14 个，且它同时生成标注（p5）；评判为 Claude Sonnet 4.6，未报 κ；未找到代码或权重。
- **DynaFlow**：⚠️ 存疑。+10.90（对 Self-Refine）中净多答对的 75 题有 71 题来自 HotpotQA，该基准上单 agent 基线不能检索，而 DynaFlow 训练数据含 449 条 HotpotQA 示范（p12）；去掉 HotpotQA 只领先 +0.82，GPQA-D 上 84.85 低于 Self-Refine 的 88.38；训练样本数 2,031 / 2,257 / 2,254 三处不一致；附录 E 未报告人工一致性数值；单次运行，种子 42。
- **Continual Learning Exam**：✅ 能核实。47.67% 与 23.3% 是 Trial 2（一次反馈并修改）结果，Trial 1 为 42.17%；+5.33 混合了反馈与额外提交，没有重置记忆的对照（p17）；评判为 DeepSeek V4 Flash，按细则项与人工一致率 96.86%（60 份提交，p32–33），未按关卡报告；只公开 20 个任务（CLE Lite）。
