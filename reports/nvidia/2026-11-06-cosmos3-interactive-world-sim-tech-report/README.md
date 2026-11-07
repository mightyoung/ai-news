# NVIDIA · Interactive World Simulation with Cosmos for Physical AI

| 项目 | 内容 |
|---|---|
| 厂商 | NVIDIA |
| 文档类型 | 技术报告（tech-report） |
| 模型名与版本 | Cosmos3-Nano-Sim-Bimanual / Sim-Transfer / Sim-Auto / Transfer-Auto（基于 Cosmos 3 Nano） |
| 发布日期 | 2026-11-06（北京时间，HF 博客公开发布；PDF 封面日期 2026-11-4） |
| 官方链接 | https://research.nvidia.com/labs/cosmos-lab/cosmos-simulation/ |
| PDF 链接 | https://research.nvidia.com/labs/cosmos-lab/cosmos-simulation/technical-report.pdf |
| arXiv id | — |
| SHA-256 | b3d73f530196f65ebc6fb33b13609d78b1f855e6b89cee64dd22635833d2086c |
| 页数 | 119 |

## 摘要

NVIDIA 提出一套把 Cosmos 世界基础模型改造成实时交互式世界模拟器的通用框架：根据动作和场景控制信号流式生成视觉观测，覆盖相机导航与机器人操作、可控视频转换、多视角自动驾驶模拟。Cosmos 3 主干是 Mixture-of-Transformers（推理塔做语言自回归、生成塔做扩散去噪）。后训练分四个阶段：双向适配、Teacher Forcing 因果训练、离散时间一致性蒸馏、Self Forcing + 分布匹配蒸馏（SF-DMD）。代码在 github.com/nvidia/cosmos，四个检查点在 Hugging Face 公开。

## 原文

[来源.md](来源.md)

## 核验

✅ 能核实，详见 [核验.md](核验.md)。一句话：四阶段配方和开放权重都查得到，性能数字全部厂商自报；闭环机器人提升只在 32 个起点的校准集上测过。

## 深度解析

[深度解析.md](深度解析.md)（2026-11-07）

## 相关文档

- [HF 博客：New NVIDIA Cosmos 3 Open Models for Interactive World Simulation](../../nvidia/2026-11-06-cosmos3-interactive-world-sim-blog/README.md)
