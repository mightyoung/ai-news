# NeurIPS 2026 — 顶会周报归档

录用信息来自官方 virtual 站数据 `https://neurips.cc/static/virtual/data/neurips-2026-orals-posters.json`。

## 2026-11-02 周报

| 录用类型 | 标题 | 第一单位 | 主线 | 为什么值得看 | 链接 | 全文 | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|---|
| Oral | Quantized Reasoning Models Think They Need to Think Longer, but They Do Not（量化后的推理模型以为要想更久，其实不用） | FAIR at Meta | 大模型与微调 | 摘要称：激进的训练后量化让推理模型准确率下降、思维链变长；最多 52% 的失败是中间已算出正确答案却没输出；对「wait / but」等词加免训练的 logit 惩罚，思维链缩短 12–23%（5 个 1.5B–32B 模型、3 种量化方法、5 个基准） | [OpenReview](https://openreview.net/forum?id=YulzlhXlgy) · [arXiv 2606.00206](https://arxiv.org/abs/2606.00206) | [PDF（arXiv）](2606.00206-quantized-reasoning-models-think-longer/paper.pdf) | ⚠️ 部分核实：52%/58% 为 Qwen-1.5B×AWQ3bit×MATH-500；12–23% 见 Fig.5（1.5B），Table1 跨模型 4.1–28%；无代码仓 | [深度解析](2606.00206-quantized-reasoning-models-think-longer/深度解析.md) |
| Oral | Fisher-R1: Training LLM Agents for Reliable Hypothesis Testing（训练会做可靠假设检验的 LLM Agent） | Stanford University（论文首页；virtual 站列 University of Wisconsin–Madison） | AI Agent | 提出 425 题的 P-Bench 和用强化学习训练的 Fisher-R1-14B；摘要称单次成功率比 DeepSeek-V4-Pro 平均相对提升 21%，最难任务最高 26% | [OpenReview](https://openreview.net/forum?id=ShMNgympCf) · [arXiv 2608.07437](https://arxiv.org/abs/2608.07437) | [PDF（arXiv）](2608.07437-fisher-r1-llm-agents-hypothesis-testing/paper.pdf) | ⚠️ 部分核实：21%/26% 为 Strict pass@1 相对 DeepSeek-V4-Pro（自建 P-Bench）；对 GPT-5.4 为 3/4 Strict 更高 | [深度解析](2608.07437-fisher-r1-llm-agents-hypothesis-testing/深度解析.md) |
