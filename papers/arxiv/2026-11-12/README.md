# 2026-11-12 arXiv 精选「最值得先看」

> 批次说明：用的是 arXiv 2026-11-11（周三）公告批次，cs.LG/cs.CL/cs.AI/cs.CV/cs.RO 的 new 列表跨分类去重后共 476 篇（编号 2611.12900–2611.14519）。已避开今天 HF 部分的 5 篇。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.13560 | Are Dense Rewards Worth Their Tokens in GRPO? | Vikash Singh, Weicong Chen, Debargha Ganguly 等（共 19 位；Case Western Reserve University） | 按相同生成 token 数和训练 GPU 小时来比，Qwen2.5-1.5B 上蒙特卡洛过程奖励比标准 GRPO 低 14.3 个百分点（等 token）和 7.8 点（等训练时间）；共 1,668 次运行、6 个模型（14.3 为 5 个种子、7.8 为 12 个种子；200 道 MATH 留出题 pass@1，p5） | [abs](https://arxiv.org/abs/2611.13560) | [PDF](2611.13560-dense-rewards-grpo-matched-compute/paper.pdf) | ✅ 能核实 | [待补](2611.13560-dense-rewards-grpo-matched-compute/) |
| 2611.13160 | How Much of Your VLA Is kNN | Denis Grachev, Damien LaRocque, Omar Moured（Sereact GmbH；Karlsruher Institut für Technologie） | 不训练策略，只检索相近示教并复用其动作片段，在 LIBERO 仿真上就有 91.7% 成功率（多模态变体，2000 回合，Table 1 p6；代码仓库暂 404）；提出 LAC 离线指标，提醒大家 LIBERO 高分不等于泛化 | [abs](https://arxiv.org/abs/2611.13160) | [PDF](2611.13160-how-much-of-your-vla-is-knn/paper.pdf) | ✅ 能核实 | [待补](2611.13160-how-much-of-your-vla-is-knn/) |
| 2611.13607 | One Byte, One Token: Byteifying a 27B Hybrid-Attention LLM with Self-Generated Data | Liwei Zhang, ZhiMing Tong（Landi Lab，按首页署名） | 把已训练好的 27B 模型词表从 248,320 缩到 384（逐字节输入），用 8×H200 训练 178.6 小时；字符级任务更强（CUTE 75.2→84.0，不开思考模式，单种子（Table 3 p13）），代价是每步产出少 3–5 倍 | [abs](https://arxiv.org/abs/2611.13607) | [PDF](2611.13607-byteifying-27b-llm-one-byte-one-token/paper.pdf) | ✅ 能核实 | [待补](2611.13607-byteifying-27b-llm-one-byte-one-token/) |

## 为什么选这 3 篇

**Are Dense Rewards Worth Their Tokens in GRPO?**：过程奖励（给解题每一步打分）听起来比只看最终答案更细，但摘要指出蒙特卡洛奖励的采样续写占了 91% 的生成 token。把预算对齐后排名反转；另外「训练在预测成功率接近 1/2 的题上」在 Qwen3-0.6B 提升 1.7 点、Qwen2.5-1.5B 提升 0.8 点，且标准 GRPO 把初始学习率翻倍就能追到半个点以内。结论主要在 1.5B 以下小模型上（摘要），大模型是否成立未读到。

**How Much of Your VLA Is kNN**：摘要设置是 LIBERO 仿真，检索基线 91.7%；在 LIBERO-Plus 扰动下检索掉得最少；覆盖 9 个公开 VLA。对想判断「VLA 榜单分数到底说明什么」的工程师是很好的清醒剂。仅仿真，没有真机结论（摘要范围）。

**One Byte, One Token**：作者团队很小（首页署名 Landi Lab 与个人邮箱），结论按论文自报，未经他人复现。亮点是诚实写出代价：逐字节后生成速度约为原来的 1/4（汉字每秒），64K 字节预填充慢 6.5 倍，中文字音字形的查表类知识下降。
