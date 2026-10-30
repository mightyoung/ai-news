# Hugging Face 热门论文 — 2026-10-30

> 批次说明：Shanghai 当日（2026-10-30，周五）的 Daily Papers 尚未发布（API 只接受到 2026-10-29）；本目录对应 **2026-10-29** HF Daily Papers API 批次（`?date=2026-10-29`，抓取时 14 篇），按 upvotes 与研究价值筛选，未与近几日晨报重复。序号为挑选顺序，不是 HF 榜单名次。机构按论文首页署名填写。

| # | 论文 | 👍 | 机构 | 链接 | 本地 |
|---|---|---|---|---|---|
| 1 | **Efficient Streaming Audio-Visual Target Speaker Extraction for Real-World Acoustic Scenes**<br>Falcon：面向真实声学场景的高效流式音视频目标说话人提取 | 149 | 青海大学（第一作者单位）、清华大学、北京脑科学与类脑研究所；HF 标 Tsinghua Machine Learning Group ✅ 能核实（带限定） | [HF](https://huggingface.co/papers/2610.32749) · [arXiv](https://arxiv.org/abs/2610.32749) | [PDF](2610.32749-falcon-streaming-avtse/paper.pdf) · [深度解析](2610.32749-falcon-streaming-avtse/深度解析.md) |
| 2 | **OmniShowcase: Omnidirectional Subject-Consistent Video Generation from Multi-View Images**<br>OmniShowcase：基于多视角图像的全方位主体一致视频生成 | 44 | KAIST AI、Inha University、FLIPTION ✅ 能核实 | [HF](https://huggingface.co/papers/2610.35684) · [arXiv](https://arxiv.org/abs/2610.35684) | [PDF](2610.35684-omnishowcase/paper.pdf) · [深度解析](2610.35684-omnishowcase/深度解析.md) |
| 3 | **Sensorimotor Alignment: A Platonic Proxy for Embodied Policy Success**<br>感知–运动对齐：机器人策略成功率的离线代理指标 | 20 | Rice University、NVIDIA ⚠️ 部分核实 | [HF](https://huggingface.co/papers/2610.31670) · [arXiv](https://arxiv.org/abs/2610.31670) | [PDF](2610.31670-sensorimotor-alignment/paper.pdf) · [深度解析](2610.31670-sensorimotor-alignment/深度解析.md) |
| 4 | **TAO: Tool-Aware Joint Scheduling for LLM-Based Agentic Serving**<br>TAO：面向 LLM 智能体服务的工具感知联合调度 | 16 | 上海交通大学、Stanford University；HF 标 AIOR ⚠️ 部分核实 | [HF](https://huggingface.co/papers/2610.37230) · [arXiv](https://arxiv.org/abs/2610.37230) | [PDF](2610.37230-tao-agentic-serving/paper.pdf) · [深度解析](2610.37230-tao-agentic-serving/深度解析.md) |
| 5 | **RealCLI: Toward a Unified Evaluation of Human-Agent Collaboration for CLI Agents**<br>RealCLI：统一评测 CLI 智能体的人机协作能力 | 15 | 北京航空航天大学（1 号单位，通讯作者所在）、中国人民大学、IQuest Research（第一作者所在）⚠️ 部分核实 | [HF](https://huggingface.co/papers/2610.22507) · [arXiv](https://arxiv.org/abs/2610.22507) | [PDF](2610.22507-realcli/paper.pdf) · [深度解析](2610.22507-realcli/深度解析.md) |

点赞数抓取于 2026-10-30 09:00（北京时间）。

## 核验状态（2026-10-30）

论文真实性核验助手标准版核验：归档 PDF 与 arXiv 当前版本的 SHA-256 一致（5/5），其中 S²（2610.31670）归档的是 v2。页码为 PDF 物理页。

- **Falcon**：✅ 能核实（带限定）。第一单位青海大学（p1）；NeurIPS 2026 只出现在 p1 页脚。效率数字与表 5（p9）一致，但 0.5M 只算可训练参数，另有冻结的 11.2M 唇部编码器，总量 11.72M。RealSSA-Sim 7.7 对 7.6 dB（表 3 p8）是单次运行（seed 42）、没有方差，16 个分场景里有 3 个落后（表 17 p23），应视为持平。代码和权重 Apache-2.0；RealSSA-Sim 是 CC BY-NC-ND 4.0（需申请），RealSSA-Real 没有许可标签。
- **OmniShowcase**：✅ 能核实。DINO 0.799 对 0.707、GT-CD 0.1717→0.0824 与表 2（p8）一致。测试集是自建的 50 个主体，和训练用同一渲染流程（p7）；美学分两个基准上都最低（0.574；NAVI 0.551）；单次运行（seed 42，p17）；另有 44 人的偏好研究。GitHub 只有 README，没有 LICENSE。
- **S²**：⚠️ 部分核实。12 个 VLA 的 r=+0.717（CI [+0.436, +0.912]）中，h=7 是 10 个视野里的峰值（表 2 p23）；去掉 5 个 StarVLA 变体后 r=+0.526、p=0.113（附录表 1 p20）。真机 r=+0.831 用的是探索性视野 h=110，预先指定的 h=7 下 r=+0.429、p=0.236，不显著（附录 B.5 p21）。p 值都是单尾、未校正；WAM 的 p=0.054，不显著。代码 MIT，真机复现包未放出。
- **TAO**：⚠️ 部分核实。−26.8% / −36.3% / +29.5% 三个「最多」来自表 1（p6）同一格（DeepSeek、SWE-Lite、64 workers）；36 格里有 5 格不如最佳基线（−8.8、−6.2、−5.1、−0.2、−2.5）。正文和表格不一致：p7 说 96 workers 解码吞吐最高，但表里 1996.8 低于 ThunderAgent 的 2104.9；正文写 500 个 SWE-verified 任务，表 2 图注写 300 个（p7）。单次运行，没有代码。
- **RealCLI**：⚠️ 部分核实。1 号单位北航，通讯作者也在北航，第一作者在 IQuest。引言写 52.7%（p3），摘要和表 3 写 49.2%（p1、p7），49.2 是混合 Rexec、Rcollab、Jcollab 的 9 格平均。37.6% 只是 Claude Opus 5 在 Terminus-2 上的 Jcollab，三种脚手架平均 32.1。GPT-5.6 Sol 的 58.5% 和 8.5% 是不同指标（Rexec 对 Jcollab）。TC 7% / SR 0% 是按场景平均的 ≥75% 通过率（p5），其他模型也有。评审是 Claude Code 跑的 Claude-Opus-4.8（p24），用户模拟器是 GLM-5.3（p22）。HF 数据集公开但没有许可证，GitHub 也没有。
