# Hugging Face 热门论文 — 2026-10-27

> 批次说明：Shanghai 当日（2026-10-27，周二）的 Daily Papers 尚未发布（API 仅接受到 2026-10-26）；本目录对应 **2026-10-26** HF Daily Papers API 批次（`?date=2026-10-26`，42 篇），按 upvotes 与研究价值筛选，并避开近几日晨报已荐条目。序号为挑选顺序，不是 HF 榜单名次。

| # | 论文 | 👍 | 机构 | 链接 | 本地 |
|---|---|---|---|---|---|
| 1 | **Reading, Writing, Sharing, and Interacting with the World through Video**<br>用视频阅读、书写、共享与交互世界（统一视频世界模型综述） | 216 | University of Oxford（第一单位兼项目负责方；另署 NUS、NTU、UC Merced） | [HF](https://huggingface.co/papers/2610.31668) · [arXiv](https://arxiv.org/abs/2610.31668) | [PDF](2610.31668-video-world-model-survey/paper.pdf) · [深度解析](2610.31668-video-world-model-survey/深度解析.md) |
| 2 | **RSIHub: A Composable Framework for Agent-Evolution Methods**<br>RSIHub：智能体自进化方法的可组合框架 | 34 | 第一单位 UC Berkeley；论文第 3 单位为抖音集团（Douyin Group），未署 ByteDance（ByteDance 为 HF 页面标签）；另署上海交大、BIGAI 等 | [HF](https://huggingface.co/papers/2610.32253) · [arXiv](https://arxiv.org/abs/2610.32253) | [PDF](2610.32253-rsihub/paper.pdf) · [深度解析](2610.32253-rsihub/深度解析.md) |
| 3 | **UserArena: Benchmarking Interactive User Simulation for Long-Horizon Shopping Agents**<br>UserArena：长程购物智能体的交互式用户模拟基准 | 47 | 第一单位 Leiden 大学；Alibaba 为第 3 单位（HF 页面标 alibaba） | [HF](https://huggingface.co/papers/2610.30932) · [arXiv](https://arxiv.org/abs/2610.30932) | [PDF](2610.30932-userarena/paper.pdf) · [深度解析](2610.30932-userarena/深度解析.md) |
| 4 | **HiSTEVE 1.0: Harnessing Human-Interface VLA Agents for Open-World Games**<br>HiSTEVE 1.0：开放世界游戏中的人类接口 VLA 智能体 | 38 | 论文未署 Tencent（仅为 HF 页面标签）；署名 HKU（第一单位）、浙大、复旦、LIGHTSPEED 及一位独立研究者 | [HF](https://huggingface.co/papers/2610.31162) · [arXiv](https://arxiv.org/abs/2610.31162) | [PDF](2610.31162-histeve/paper.pdf) · [深度解析](2610.31162-histeve/深度解析.md) |
| 5 | **RynnUnify: Towards Unified Embodied Brain**<br>RynnUnify：迈向统一的具身大脑 | 33 | DAMO Academy（第一单位；阿里达摩院、湖畔实验室） | [HF](https://huggingface.co/papers/2610.32965) · [arXiv](https://arxiv.org/abs/2610.32965) | [PDF](2610.32965-rynnunify/paper.pdf) · [深度解析](2610.32965-rynnunify/深度解析.md) |

点赞数抓取于 2026-10-27 09:05（北京时间）。

## 核验更正（2026-10-27）

经核验，5 篇 PDF 的 SHA-256 均与 arXiv 当前版本一致。以下为对晨报口径的更正与补充限定：

1. **视频世界模型综述**：「约 65 页」只算正文（结论在 p65），PDF 全文 102 页。Oxford 是第一单位兼项目负责方（Oxford、NUS 各 3 位作者）。
2. **RSIHub**：第一单位 UC Berkeley；论文第 3 单位写的是 Douyin Group，未写 ByteDance。+13.5（56.2→69.7，Table 1 p8）是单次运行、16 个配置中最好的一个，且是含 train split 的 overall 分数；sealed split 只有 +5.6。Codex 起点已是 69.7，最多只提升 +2.2。Apache-2.0 属实。
3. **UserArena**：第一单位 Leiden，Alibaba 第 3。0.713× 来自一次线上 A/B、一对排序策略，指标是 ΔPV-CTR，含义是**低估了 28.7%**，不应说成「复现」。仓库为非商用许可，只公开了 535 个会话的 held-out 集。
4. **HiSTEVE 1.0**：论文未出现 Tencent（仅 HF 标签）；署名 HKU（第一单位）、ZJU、Fudan、LIGHTSPEED 和一位独立研究者。VLA 为 Qwen2.5-VL-7B。OpenHA 37.4% 只比 36.8% 的基线高 0.6。「两倍多」指 LongBench 上 10.7→25.0（Table 3 p10），LongBench 是作者自建的 14 任务基准，未报告 episode 数。论文印的 GitHub 项目页截至 2026-10-27 09:30（北京时间）返回 404。
5. **RynnUnify**：DAMO 为第一单位。+9.75 是在自建的 Rynn-VP 上测的，由 GPT-6-sol 打分（p17）。Rynn-GEU 题目经 GPT-5.6-Luna 筛选、只保留生成未来视频有帮助的题，对「先想象」路线有利。RoboCasa「Selected-20」未说明挑选标准、基线由作者自跑，在 Composite-Seen 上只排第 2（52.0 对 Xiaomi 57.1）。真机为作者自选 3 个任务、每个 20 次。「先想象再回答」是从推理器另行 RL 后训练的 8B agent，奖励为格式有效性 + 答案质量（Fig.4 p13），无过程奖励；GEU +6.0（44.0→50.0，10 项中 7 项提升，Pos/Dist/Size 下降）。权重在 [HF collection](https://huggingface.co/collections/Alibaba-DAMO-Academy/rynnunify)（小写路径；论文印的大写链接 404），无 gate；[GitHub](https://github.com/alibaba-damo-academy/RynnUnify) 仅含代码。推理器在 Stage 1 微调、Stage 2 冻结。
