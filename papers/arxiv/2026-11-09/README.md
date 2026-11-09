# 2026-11-09 arXiv 精选「最值得先看」

来自 arXiv「Friday, 6 November 2026」公告批次（cs.LG/CL/AI/CV/RO 的 new 条目，去重后 538 篇，编号约 2611.06255–2611.08487，另含个别更早编号的跨类条目；抓取于 2026-11-09 09:06–09:10 北京时间）的精选，选出最值得先看的 3 篇归档。三篇均不在当日 Hugging Face 精选归档名单中，也未在 11-04、11-06 两期出现过。每篇论文一个文件夹，内含 `paper.pdf`，`深度解析.md` 由 10:40 例程补。核验列先写「待核」。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 核验 | 深度解析 |
|---|---|---|---|---|---|---|---|
| 2611.07639 | Measuring the Marginal Value of Verifier-Based RL Beyond Supervised Fine-Tuning | Amit Sagtani, Saloni Garg | 把「RLVR 到底在 SFT 之上还能加多少」直接测出来。自建确定性基准 gpu-train-debug（1,877 道 GPU/LLM 训练故障诊断题、30 类，程序化验证器给部分分）。基座 Qwen2.5-3B-Instruct：先导实验 1,200 条金标演示做 SFT，hard split 0.785，而从基座起 15 步 GRPO 为 0.314（基座 0.311）；预注册规模（SFT 之后再 60 步 GRPO，lr 1e-6）在分布内仅 +0.22 点（95% CI [-0.06, +0.51]），分布外 +0.33 点（CI [+0.02, +0.68]）。单一 3B 模型、单一合成任务族，结论别外推。论文脚注自述研究设计与写作有 LLM 协助。首页只写 Santa Clara, California，无机构署名。 | [arXiv](https://arxiv.org/abs/2611.07639) | [PDF](2611.07639-verifier-rl-marginal-value-beyond-sft/paper.pdf) | ⚠️ 部分核实（数字与 Table 1 p3、Table 2 p4 一致；论文给的代码仓库当前 404，RL 只有一个训练种子） | [深度解析](2611.07639-verifier-rl-marginal-value-beyond-sft/深度解析.md) |
| 2611.07367 | Test-Time Self-Play: Scaling without a Verifier | Akira Yoshiyama, Akmal Ashirmatov, Jonas Hübotter 等 | 没有可靠验证器时怎么做测试时扩展：TTSP 在同一冻结 Qwen3-8B 骨干上挂两个 LoRA，用非对称自博弈（出题方生成合成课程、解题方求解）在目标题上现场训练，不依赖验证器。在 LiveCodeBench v6 里按 Qwen3-8B mean@512 筛出的难题子集（HardLCBv6，0<mean@512<0.7）上，七种验证器强度下均为最优，验证器越弱优势越大；无验证器（v0）时 mean@8 绝对提升 35%（图 1 标 +0.35；对比 Qwen3-8B 拒绝采样、功能多数投票 FMV、ACE 提示优化）。基座对正确解覆盖接近 0 时失效。首页单位 ETH Zurich & Tufa Labs。 | [arXiv](https://arxiv.org/abs/2611.07367) | [PDF](2611.07367-test-time-self-play-no-verifier/paper.pdf) | ✅ 能核实（HardLCBv6 仅 28 题，Table 3–4 p16；合成题上仍用执行反馈 p17） | [深度解析](2611.07367-test-time-self-play-no-verifier/深度解析.md) |
| 2611.08485 | Where and Why is Grounded Reasoning Useful? | David Yan, Le Xue, Forrest Huang 等 | 回答「VLM 在思维链里输出坐标（grounded reasoning）到底有没有用」：以 Qwen3-VL-8B 做 SFT/RL 消融，在 6 个空间推理、3 个细粒度感知基准上基本无显著增益，只在计数上有（SFT 后 CountQA +3.6±2.4、FSC-147 +2.6±1.3，Table 3 p6）。合成任务显示：只有目标「难以用语言指代」时才有用（无标签场景走线追踪 69.3 vs 文本 CoT 24.4；计数 95.2 vs 直接微调 34.4；加上文字标签后文本 CoT 反超）。作者据此提出 BrickVision 基准。首页单位 Elorian、Princeton University。 | [arXiv](https://arxiv.org/abs/2611.08485) | [PDF](2611.08485-where-why-grounded-reasoning-useful/paper.pdf) | ✅ 能核实（计数增益在 Table 3 p6；合成探针每变体只训一次 p8） | [深度解析](2611.08485-where-why-grounded-reasoning-useful/深度解析.md) |

## 为什么选这 3 篇

**2611.07639（RL）**：当下大家默认「SFT + RLVR」流水线里 RL 一定带来增益，这篇用预注册、可复现（总计算成本 8.69 美元）的受控实验给出反例：SFT 占了大部分可得提升，RL 在分布外才有微小增益。对想理解 RLVR 边界的学习者，是一份诚实的负结果；局限是单一 3B 模型和合成任务。

**2611.07367（大模型）**：测试时扩展几乎都默认有验证器，这篇直面「没有验证器」的现实场景，思路（自博弈出合成课程、现场训练 LoRA）与代码题上的实测提升都很具体，适合配合测试时训练、自博弈类工作一起读。

**2611.08485（多模态）**：对「grounded reasoning 是不是必需」这类流行做法做了干净的对照与消融，结论（只在难以语言指代时有用，多数现有基准用文字就能解）对设计 VLM 训练配方与基准都有参考价值。
