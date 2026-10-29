# ai-news

AI 论文原文（PDF）与中文深度解析归档。先按来源分，再按日期，再按论文一个文件夹。

## 目录结构

```
papers/
  huggingface/                       # 来源：Hugging Face 每日热门论文
    YYYY-MM-DD/
      README.md                      # 当日清单（标题、👍、机构、链接、PDF 与深度解析入口）
      <arxiv-id>-<short-english-title>/
        paper.pdf                    # 论文原文
        深度解析.md                  # 中文深度解析
  arxiv/                             # 来源：arXiv 每日精选「最值得先看」（补充归档）
    YYYY-MM-DD/
      README.md
      <arxiv-id>-<short-english-title>/
        paper.pdf
        深度解析.md
  reading-list/                      # 来源：用户指定的阅读清单（按日期/主题一个文件夹）
    YYYY-MM-DD-<topic>/
      README.md                      # 清单总表（含原文是否已上传、来源链接）
      <序号>-<id 或出处>-<short-slug>/
        paper.pdf                    # 仅放可合法再分发的原文
        深度解析.md
        来源.md                      # 不能上传原文时：官方页面与合法获取方式
x-posts/                             # 来源：X 每日热帖里「建议深挖」的帖子
  README.md                          # 总索引（按日期倒序）
  YYYY-MM-DD/
    README.md                        # 当日清单
    原帖.md                          # 原帖原文
    深度分析.md                      # 中文深度分析
```

## 索引（按来源 → 日期倒序）

### Hugging Face 热门

- [2026-10-29](papers/huggingface/2026-10-29/README.md) — Multiscale Policy Optimization（MPO）、ChronoReplay、The Trinity、PDRVLA、Memory Tax
- [2026-10-28](papers/huggingface/2026-10-28/README.md) — Trajectory2Gym、Trial by Trace（TraceTrial-Bench）、StreamVibe、DynaFlow、Continual Learning Exam
- [2026-10-27](papers/huggingface/2026-10-27/README.md) — 统一视频世界模型综述（Reading/Writing/Sharing/Interacting）、RSIHub、UserArena、HiSTEVE 1.0、RynnUnify
- [2026-10-26](papers/huggingface/2026-10-26/README.md) — WeVisOne-VL、OpenDS-World（Deep Search in Real-World Web）、IQuest-Q1、Toward RSI in Physical AI、FAPL（Cinematic Video Generation）
- [2026-10-23](papers/huggingface/2026-10-23/README.md) — StreamEval、SpatialScout、DONIC、Looking Ahead（FCP）、Cache Engineering for Agents（AKV）
- [2026-10-22](papers/huggingface/2026-10-22/README.md) — FocusGUI（Focused Omni-Modal GUI Agents）、Matrix-Game 4.0、Ropedia W0、PAR、S-Agent 2.0
- [2026-10-21](papers/huggingface/2026-10-21/README.md) — Brain-encoding PEFT（BrainLoRA）、OR-License、EgoXperience、MemT-1.0、Learning from Fleet Experience
- [2026-10-20](papers/huggingface/2026-10-20/README.md) — HexaShell、BizBench、ACT3D、Into the Unknown、CarryOn
- [2026-10-19](papers/huggingface/2026-10-19/README.md) — Waypoint-OPD、OmniCompass、MJev-Spatial、OpenGCUA、FDE-Gym
- [2026-10-16](papers/huggingface/2026-10-16/README.md) — ATAS、Player-1、ROAD MOPD、Doc2Harness、Cortex
- [2026-10-15](papers/huggingface/2026-10-15/README.md) — Jeva、Agent-Reflex、Urbex、GreenWAM、Last Secure Code Benchmark

### arXiv 精选

- [2026-10-29](papers/arxiv/2026-10-29/README.md) — 工具调用 Agent 数据缩放律、VLA 与世界动作模型之争的拆解（JAM）、RLVR 全失败难题的策略相容联合解码（PICO）
- [2026-10-28](papers/arxiv/2026-10-28/README.md) — RL 缩放律（Elo 指标）、结果 RL 到底买到了什么、世界建模对机器人动作学习的真实增益
- [2026-10-27](papers/arxiv/2026-10-27/README.md) — VLA 微调缺 fp32 主副本悄悄吞掉更新、合成改写数据缩放律、舍入位置对齐稳定 LLM RL
- [2026-10-26](papers/arxiv/2026-10-26/README.md) — 生成式奖励模型缩放律（评估-奖励落差）、Softmax 与交叉熵数值修复、流匹配 VLA 一步推理
- [2026-10-22](papers/arxiv/2026-10-22/README.md) — SimHack 预测奖励作弊、数据与学习率调度联合设计、TIDE 部署中在线后训练
- [2026-10-21](papers/arxiv/2026-10-21/README.md) — What RL Brings to Reasoning、Agentic RL 数据缩放律、Halcyon 无语言预训练文生图
- [2026-10-20](papers/arxiv/2026-10-20/README.md) — GPT-6-Astra 具身评估、Looped Models Done Right、Grounded Credit Assignment
- [2026-10-19](papers/arxiv/2026-10-19/README.md) — Agentic Midtraining Recipe、Wrong Votes Right Gradients、Spark-0
- [2026-10-16](papers/arxiv/2026-10-16/README.md) — FoveaVLA、Demystifying OPD、Long-Horizon RL Needs Muon
- [2026-10-15](papers/arxiv/2026-10-15/README.md) — ChunkAct、SkillScaffold

### 阅读清单（reading-list）

- [2026-10-18 RL 文献地图](papers/reading-list/2026-10-18-rl-map/README.md) — SAC、InFOM、SkillBlender、Sutton & Barto、平均奖励 Q-learning、DQN、AlphaProof、Lewis 两篇（9 篇；4 篇无原文，见来源.md）
- [2026-10-18 阅读精选（4 篇 arXiv）](papers/reading-list/2026-10-18-picks/README.md) — Scaling Discovery Requires Forgetting、MPT 去中心化 agent 集群、Apertus 1.5、跨模型 KV Cache 迁移

## X 技术帖子（x-posts/）

X 每日热帖里标了「建议深挖」的帖子：原帖原文 + 中文深度分析，按日期归档。

```
x-posts/
  README.md                          # 总索引（按日期倒序）
  YYYY-MM-DD/
    README.md                        # 当日清单
    原帖.md                          # 原帖原文
    深度分析.md                      # 中文深度分析
```

入口：[x-posts/README.md](x-posts/README.md)
