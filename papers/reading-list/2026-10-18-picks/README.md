# 2026-10-18 阅读精选（4 篇 arXiv 预印本）

仅含已核对 arXiv 元数据、PDF 取自 arxiv.org 并校验过的论文；解析为自然中文七段式，面向本科工程师。「读到的深度」如实标注，未读部分在各解析文内写明。

| arXiv | 标题 | 作者/单位 | 读到的深度 | 一句话结论 | 深度解析 | PDF |
|---|---|---|---|---|---|---|
| [2610.20563](https://arxiv.org/abs/2610.20563) | Scaling Discovery Requires Forgetting | Shangyin Tan、Ben Zhou 等 11 人（UC Berkeley 为主，Stanford、Bespoke Labs） | 全文 + 附录 A、B；参考文献未逐篇打开 | 让研究型 LLM agent 定期清空历史、只保留当前最佳候选再重启，同预算下在 4 个任务上优于单 agent 与并行 4 agent。 | [解析](2610.20563-scaling-discovery-requires-forgetting/深度解析.md) | [PDF](2610.20563-scaling-discovery-requires-forgetting/paper.pdf) |
| [2610.22322](https://arxiv.org/abs/2610.22322) | Learning Self-Orchestration in Decentralized Agent Swarms | Guowei Xu、Zhenting Qi 等 5 人（Harvard） | 全文 + 附录 A、B、D；附录 C 个案轨迹未逐条读 | 用"拍卖出价 + 反事实出价学习 + 沿行动顺序回传奖励"训练多个独立小模型自组织协作，同训练算力下优于单体 RL；自报结果，需留意任务范围。 | [解析](2610.22322-learning-self-orchestration-agent-swarms/深度解析.md) | [PDF](2610.22322-learning-self-orchestration-agent-swarms/paper.pdf) |
| [2610.15542](https://arxiv.org/abs/2610.15542) | Apertus 1.5: From Open Text Models to Open Multimodal Reasoners | Project Apertus（约 130 人；ETH、EPFL、CSCS 等瑞士机构） | 部分阅读：正文主体与主要评测表；附录大部分、7.3、机器翻译细节未读（134 页） | 完全开放（权重/数据/代码/配方）的 8B/70B 模型加入图像、音频理解与 262K 上下文，开放度领先但整体能力落后于同级开放权重模型。 | [解析](2610.15542-apertus-1.5-open-multimodal-reasoners/深度解析.md) | [PDF](2610.15542-apertus-1.5-open-multimodal-reasoners/paper.pdf) |
| [2608.03893](https://arxiv.org/abs/2608.03893) | Cross-Model KV Cache Transfer in LLM Families: A Closed-Form Linear Mapping for Prefill Reuse | Taekyung Heo、Rasoul Shafipour 等 9 人（NVIDIA） | 全文 + 附录 A–H；图只读图注 | 同家族模型的 KV cache 可用逐头岭回归线性映射以跳过 prefill（6 对中 4 对保留 73–98%，2 对失败），分类类基准好、多步生成衰减重，延迟为理想化测量。 | [解析](2608.03893-cross-model-kv-cache-transfer/深度解析.md) | [PDF](2608.03893-cross-model-kv-cache-transfer/paper.pdf) |

## 许可证（以各篇 arXiv abs 页 "view license" 为准，2026-10-18 核对）

- 2610.20563：CC BY 4.0
- 2610.22322：arXiv 非独占分发许可（见该目录来源.md）
- 2610.15542：CC BY 4.0
- 2608.03893：CC BY 4.0

说明：2610.22322 的许可不是 CC，已按此前归档 arXiv 预印本的做法保留 PDF，并在该目录加 `来源.md` 说明；其余三篇为 CC BY 4.0，可再分发（须署名）。解析中的判断标为"我的判断"，论文未说明处写"论文未说明"。
