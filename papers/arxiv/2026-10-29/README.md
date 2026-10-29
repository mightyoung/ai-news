# 2026-10-29 arXiv 精选「最值得先看」

来自 arXiv 2026-10-28（周三）公告批次（编号约 2610.35869–2610.37668）的精选，选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.37648 | Scaling Laws for Tool-Use Agents via Controllable Environment Synthesis | Andrew Szot, Samira Abnar, Omar Attia, Abbas Kazerouni, Michael Kirchhof, Cheng-Yu Hsieh, Raviteja Vemulapalli, Alexander Toshev | 用可控的合成工具环境（SynthAPI，458,752 个任务、4 种规模共 849 个模型）拟合工具调用 Agent 的数据缩放律：数据预算变大时，扩工具和数据库的多样性比堆任务数量更有效，提高数据复杂度收益更大；按此配方训练的模型在四个基准上超过用以往合成数据训练的模型（摘要层面结论，细节待读正文）。 | [arXiv](https://arxiv.org/abs/2610.37648) | [PDF](2610.37648-tool-use-agent-scaling-laws/paper.pdf) | 待补 |
| 2610.37219 | Vision-Language-Action or World-Action? Just Action Models | Yonghao Yu, Lang Huang, Runyi Li, Toshihiko Yamasaki | 把 VLA 与世界动作模型（WAM）之争拆成「骨干初始化、未来目标、推理时是否保留未来机制」三个选择，提出只加一个训练期「预见」损失（预测冻结编码的未来特征、不生成视频）的 JAM：相对 FastWAM，LIBERO / LIBERO-Plus / RoboTwin 成功率 97.0%/55.3%/91.2% → 98.2%/64.5%/91.4%（RoboTwin 基本持平），估计在线训练 FLOPs 降 73%（使用缓存的预见目标）；均为仿真基准。 | [arXiv](https://arxiv.org/abs/2610.37219) | [PDF](2610.37219-just-action-models/paper.pdf) | 待补 |
| 2610.36849 | When All Rollouts Fail: Policy-Compatible Joint Decoding for Hard-Problem Reasoning | Zehao Wang, Hanzhu Chen, Runquan Gui, Zhe Wang, Lin Yang | 针对 RLVR 在「所有 rollout 都失败、GRPO 优势全为零」的难题上学不到东西：用专家解在 token 级引导解码、同时保留学生的相对概率，并用动态 top-k 限制偏离，得到既正确又与当前策略相容的轨迹，再与在线 rollout 混合（重要性采样）训练；摘要称在推理和 Agent 基准上稳定优于标准 RLVR 和以往离策略基线，具体数字待读正文。 | [arXiv](https://arxiv.org/abs/2610.36849) | [PDF](2610.36849-pico-when-all-rollouts-fail/paper.pdf) | 待补 |
