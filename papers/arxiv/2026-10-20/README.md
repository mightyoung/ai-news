# 2026-10-20 arXiv 精选「最值得先看」

来自 arXiv 2026-10-19（周一）公告批次（编号 2610.22373–2610.23856）的工作日精选，四个方向各挑 3–4 篇后选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.22471 | Has GPT-6-Astra Achieved Embodied Intelligence? | SenseNova 联合研究团队（Zhongang Cai, Ziang Cao, Tailai Chen 等） | 用 12 个操作/导航基准和 8 种真机配置系统检验通用大模型直接控机器人：仿真里靠上下文示范已跨过"能做"的门槛，真机上仍卡在示范成本和物理约束，还给出下一代具身评测的原型。 | [arXiv](https://arxiv.org/abs/2610.22471) | [PDF](2610.22471-has-gpt-6-astra-achieved-embodied-intelligence/paper.pdf) | [深度解析](2610.22471-has-gpt-6-astra-achieved-embodied-intelligence/深度解析.md) |
| 2610.23036 | Towards Looped Models Done Right, Part I: Topology, Input Injection, Recurrent-State Design | Benhao Huang, Chufan Shi, Junlin Chen 等 | 把循环（层复用）Transformer 的三个设计轴拆开做受控对比，结论是 Huginn 式"前段-循环块-尾段"更好，在 MoE 上常驻参数少 75%（8.0B vs 32.0B），训练与推理 FLOPs 对齐，但对比 112 层前馈 MoE 的 10 项基准里只有 3 项不落后（DROP、GSM8K 领先，MATH500 持平），且只有一个规模、一次训练。 | [arXiv](https://arxiv.org/abs/2610.23036) | [PDF](2610.23036-towards-looped-models-done-right/paper.pdf) | [深度解析](2610.23036-towards-looped-models-done-right/深度解析.md) |
| 2610.23148 | Grounded Credit Assignment in Reinforcement Learning for Multi-Turn Search Agents | Qirui Liu, Hao Chen, Yi Wen 等 | 指出 GRPO 训搜索智能体会让"答对但没用证据"越来越多，用可验证的子结果分开给搜索和作答记功，不加模型不加采样，EM 提升约 6 分、有据作答占比从 76.9% 升到 93.4%。 | [arXiv](https://arxiv.org/abs/2610.23148) | [PDF](2610.23148-grounded-credit-assignment-search-agents/paper.pdf) | [深度解析](2610.23148-grounded-credit-assignment-search-agents/深度解析.md) |
