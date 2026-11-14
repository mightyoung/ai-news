# InclusionAI · Duo v1 模型卡（Hugging Face）

| 项目 | 内容 |
|---|---|
| 厂商 | InclusionAI（inclusionai）。技术报告标题页为 Ant Group 标志，项目页页脚为 Ant Research；原文未说明其间关系。 |
| 文档类型 | 模型卡（Hugging Face） |
| 模型名与版本 | Duo 1.0 causal-base / 1.0 distill / 1.2 causal-base（另有 1.0 distill-quant） |
| 发布日期 | 2026-11-12（HF `createdAt`：Duo-1.2-causal-base 06:30Z、Duo-1.0-distill 06:32Z、Duo-1.0-causal-base 06:32Z，北京时间 14:30–14:32；量化包 11-13 08:09Z） |
| 官方链接 | https://huggingface.co/inclusionAI/Duo-1.0-causal-base |
| PDF 链接 | —（技术报告见 arXiv） |
| arXiv id | 2611.15131（模型卡徽章指向该文） |
| SHA-256 | — |
| 页数 | — |

## 摘要

InclusionAI 在 Hugging Face 上发布 Duo 权重集合。主卡 `Duo-1.0-causal-base` 写明这是面向实时音视频交互的全双工多模态世界模型，包里包含 Realization 权重与骨干、Intent 模型与 adapter、视频/音频 codec、语音识别和强制对齐；默认采样 Euler、50 步、flow shift 1.0；实现格式为 PyTorch Distributed Checkpoint。`Duo-1.0-distill` 是四步蒸馏的 Realization 叠加包（默认 Euler、4 步、flow shift 5.0），需先下载 causal-base 再覆盖。`Duo-1.2-causal-base` 卡片写「improved generation quality」（厂商自报，未见定量对比），结构与 1.0 causal-base 相同。许可字段为 MiniMax H3 Community License；卡片写权重初始化自 MiniMax H3，再由 Duo 团队训练。技术细节以配套技术报告为准，模型卡本身几乎没有训练数据规模或评测数字。

本轮 HF API（2026-11-14）确认：四仓均公开、无门禁，且含真实权重。1.0 / 1.2 causal-base 均为完整包，`usedStorage` 约 142.89 GB；1.0 distill 为约 2.59 GB 的 Realization DCP 叠加包；1.0 distill-quant 为 FP8 量化的四步 Realization 叠加包（约 43.80 GB，默认同样 4 步 / flow shift 5.0），`createdAt` 为 2026-11-13 16:09 CST。GitHub `inclusionAI/Duo` 非空，提供离线推理代码，仓内声明 Apache-2.0；**权重**许可是 MiniMax H3 Community License（LICENSE 日期 2026-08-02，许可方写 Nanonoble Pte. Ltd.），关键限制包括：排除欧盟、英国、韩国与美国；年收入超过 2000 万美元的商业使用须事先书面授权；商业产品界面须显著标明 “MiniMax H3”；不得用该作品或其输出去改进 MiniMax H3 及其衍生模型以外的其他 AI 模型。官方未披露参数量、激活参数、上下文长度或 API 价格；OpenRouter 与 Artificial Analysis 的 LLM 榜均暂未收录 Duo。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-14 T2 标准版）。四份 HF 仓库均公开、无门禁，且含 safetensors / DCP 等真实权重；头条采样设置与许可名称可在模型卡原文定位。参数量、上下文和 API 价格官方未披露。须把代码的 Apache-2.0 与权重的 MiniMax H3 Community License 分开写。

## 深度解析

待补

## 相关文档

- [Duo v1 技术报告](../2026-11-11-duo-v1-tech-report/README.md)
