# Hugging Face 热门论文 — 2026-10-29

> 批次说明：Shanghai 当日（2026-10-29，周四）的 Daily Papers 尚未发布（API 只接受到 2026-10-28）；本目录对应 **2026-10-28** HF Daily Papers API 批次（`?date=2026-10-28`，51 篇），按 upvotes 与研究价值筛选，并避开近几日晨报已荐条目（如 DynaFlow）。序号为挑选顺序，不是 HF 榜单名次。

| # | 论文 | 👍 | 机构 | 链接 | 本地 |
|---|---|---|---|---|---|
| 1 | **Multiscale Policy Optimization for Long-Horizon LLM Agents**<br>多尺度策略优化：面向长程 LLM 智能体的强化学习 | 373 | 北京大学（第一单位；HF 标的 IQuest 不是第一单位）；另署 IQuest Research、清华、人大、港大 ✅ 能核实 | [HF](https://huggingface.co/papers/2610.35013) · [arXiv](https://arxiv.org/abs/2610.35013) | [PDF](2610.35013-multiscale-policy-optimization/paper.pdf) · [深度解析](2610.35013-multiscale-policy-optimization/深度解析.md) |
| 2 | **ChronoReplay: One Answer Interface Is Not Enough for Streaming Spatial Intelligence**<br>ChronoReplay：流式空间智能不能只靠一种答题接口 | 345 | 西湖大学（第一单位；HF 标 LINs lab）✅ 能核实 | [HF](https://huggingface.co/papers/2610.34283) · [arXiv](https://arxiv.org/abs/2610.34283) | [PDF](2610.34283-chronoreplay/paper.pdf) · [深度解析](2610.34283-chronoreplay/深度解析.md) |
| 3 | **The Trinity: Capability-Driven Recursive Self-Improvement for Multimodal Agents**<br>The Trinity：以能力为导向的多模态智能体递归自我改进 | 312 | Inf Rec（第一单位，按 p15 作者表；首页署 The Trinity Research Team；HF 标的 NUS 不是第一单位）⚠️ 部分核实 | [HF](https://huggingface.co/papers/2610.36077) · [arXiv](https://arxiv.org/abs/2610.36077) | [PDF](2610.36077-the-trinity/paper.pdf) · [深度解析](2610.36077-the-trinity/深度解析.md) |
| 4 | **PDRVLA: A Vision-Language-Action Model with Physical Dynamics Representations**<br>PDRVLA：带物理动态表征的视觉-语言-动作模型 | 139 | 京东（第一单位）、北京大学（第二单位）⚠️ 部分核实 | [HF](https://huggingface.co/papers/2610.37381) · [arXiv](https://arxiv.org/abs/2610.37381) | [PDF](2610.37381-pdrvla/paper.pdf) · [深度解析](2610.37381-pdrvla/深度解析.md) |
| 5 | **Memory Tax: Dissecting the Net Value of Agent Memory**<br>记忆税：拆解智能体记忆的净价值 | 125 | UIUC（第一单位）；另署清华、人大、Verdent.ai、滑铁卢 ✅ 能核实 | [HF](https://huggingface.co/papers/2610.34073) · [arXiv](https://arxiv.org/abs/2610.34073) | [PDF](2610.34073-memory-tax/paper.pdf) · [深度解析](2610.34073-memory-tax/深度解析.md) |

点赞数抓取于 2026-10-29 09:00（北京时间）；PDRVLA（136→139）与 Memory Tax（123→125）按核验时数字更新。

## 核验状态（2026-10-29）

论文真实性核验助手标准版核验：归档 PDF 与 arXiv v1 的 SHA-256 一致（5/5）。页码为 PDF 物理页。

- **MPO**：✅ 能核实。第一单位北京大学（p1）。没有代码。89.5% 来自一次 search-agent 运行的 2,048 条轨迹（p2、p34）；表 1（p10）18 格全部最高，+4.33 / +3.85 无误。每个设置只训一次（p12、p13、p34）；HLE 上只领先 0.66（4B）和 0.12（30B）；论文没写选 checkpoint 用的是哪个集合。
- **ChronoReplay**：✅ 能核实。西湖大学。GitHub 仓库没有 LICENSE，README 写明未授予许可。OST 50.52→63.93（+13.41）、UCS +7.44、OVO-S +4.91 无误（表 1–3，p6–7）；时间顺序贡献 2.41 在两个配对种子下为 +2.42 / +2.41（表 12，p24）。头条分数只有单种子（p21）；OST 是作者自建的场景不重叠切分，剔除了 243 个 ScanNet 场景，不能和已发表的 OST 分数横比（p7、p21）。
- **The Trinity**：⚠️ 部分核实。第一单位 Inf Rec（p15 作者表），不是 NUS。代码 Coming Soon，没有 LICENSE。主干冻结的 Claude Opus 5（p9、p33）。39.06→73.16 和 42.13→64.06 是 **Oracle 上界**（每个实例事后挑最好的 Harness，p12、p33）；每个基准（包括未见基准）评测前都先在本基准上做 5 次准备。可部署路由器 **71.27 / 60.96**（表 4 p12）；只加准备技能已有 58.86 / 48.67（表 2 p9）。没有用 LLM 评判；对比的 Codex 和 DeepSeek 用同一主干，论文没说它们是否也做了准备。
- **PDRVLA**：⚠️ 部分核实。第一单位京东，第二单位北京大学（p1）。没有代码。99.3 / 89.9 / 93.6 / 81.5 无误（表 5 p13），全部是仿真。基线取自各家论文和官方仓库，协议不一（p13）；领先 0.2–0.9 分，没有种子或方差；没有「去掉物理动态模块」的成功率消融，预测误差改善的置信区间含 0（p15）。
- **Memory Tax**：✅ 能核实。第一单位 UIUC。代码 MIT，结果数据 CC BY 4.0。11 个系统、三个基准、三个底座无误（p2–3）；LongMemEval-s 上 33 格全部低于两轮 RAG（表 1 p3）。GPT-5.6 Luna 只评了 20% 的题（p9）；评判模型 Qwen3.6-27B 本身也是被测底座，与人工一致率 95.1%–100%（表 6 p16）；PersonaMem-v2 只用 20% 的题，MINT-Eval 只用 10%。
