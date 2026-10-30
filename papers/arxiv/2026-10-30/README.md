# 2026-10-30 arXiv 精选「最值得先看」

来自 arXiv 2026-10-29（周四）公告批次（编号约 2610.37669–2610.38256）的精选，选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.37741 | Agentic Backdoors via Pretraining Poisoning | Xinyan Hu, Pingbang Hu, Chloe Loughridge, Xuanli He, Nicholas Carlini, Matthew Jagielski, Javier Rando, Yiming Zhang | 首次端到端展示：只在预训练语料里投毒，就能让之后用干净流程后训练出的 CLI Agent 在触发词出现时执行攻击者指定的命令（远程代码执行），干净输入上表现正常；作者从头预训练 0.6B/1.7B/4B 的 Qwen3 架构模型，4B 在 0.1% 投毒率下攻击成功率约 92%，投毒率降到 0.0005% 仍为正，且成功率随规模上升（只到 4B，非已发布的大模型）。代码已开源。 | [arXiv](https://arxiv.org/abs/2610.37741) | [PDF](2610.37741-agentic-backdoors-pretraining-poisoning/paper.pdf) | 待补 |
| 2610.37719 | What a Weight Update Buys: Leverage Across Training Stages | Shikhar Shiromani | 提出「杠杆（leverage）」：一次权重更新的 Fisher 二次型除以同尺寸随机方向的值，用来衡量各训练阶段「每单位权重变化买到多少行为变化」；在 Olmo-3、Tülu-3、Zephyr、OLMo-2 已发布检查点上，预训练窗口在散文文本上与随机方向相当，SFT 约 5 倍，RL-Zero/RLVR 400–1,500，DPO 400–23,000；还发现 bf16 训练不留 fp32 主副本会冻结 36–99% 坐标、杠杆最多降 7 倍，并给出 DARE 随机丢弃损伤的预测式（在 DARE 有效处与实测相差两倍以内）。单作者，结论基于这几条开源模型谱系。 | [arXiv](https://arxiv.org/abs/2610.37719) | [PDF](2610.37719-weight-update-leverage/paper.pdf) | 待补 |
| 2610.38027 | METATRON: A Promptable Whole-Body Execution Layer for Humanoids | Chen Tessler, Yifeng Jiang, Alec Otto, Yi Shi, Umar Iqbal, Gal Chechik, Xue Bin Peng | NVIDIA 等提出可「提示」的人形机器人全身执行层：冻结的生成式基础策略接收部分目标（定时身体部位目标、速度指令、风格），上层「技能」就是普通代码，可由编程 Agent 分析动作数据后编写，不再为每个任务训练策略；在真机 Unitree G1 上一个冻结检查点支持行走、摔倒恢复、遥操作拾物和坐到家具上，伸手成功率与抗推鲁棒性高于所测的参考轨迹跟踪方案（摘要未给具体数字）；攀爬与杂技只在仿真角色上展示。 | [arXiv](https://arxiv.org/abs/2610.38027) | [PDF](2610.38027-metatron-promptable-humanoid/paper.pdf) | 待补 |

## 为什么选这 3 篇

- **37741（Agent 安全）**：Agent 正在普遍获得执行 shell 命令的权限，这篇把「预训练数据投毒」直接连到「Agent 在用户机器上执行恶意命令」，且后训练流程是干净的，说明仅靠后训练对齐不足以兜底；作者阵容（Anthropic Fellows / Anthropic，含 Carlini）和开源代码让结果更可复查。
- **37719（训练动力学 / 后训练）**：给 SFT、DPO、RLVR 的「小改动大效果」一个可计算的统一量尺，并顺带给出 bf16 主副本、DARE 合并等工程上能直接用的结论，和 10/27 归档的「VLA 微调缺 fp32 主副本」一文可对照阅读。
- **38027（具身智能 + 编程 Agent）**：把人形机器人控制拆成「冻结的通用运动底座 + 用代码写的技能」，让编程 Agent 无需再训练策略就能组合出新技能，并有 G1 真机验证，是 VLA/具身与 Agent 两条主线的交汇点。
