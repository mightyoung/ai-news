# Meituan LongCat · LongCat-Video-Avatar 1.6 Technical Report

| 项目 | 内容 |
|---|---|
| 厂商 | 美团 LongCat（Meituan LongCat Team） |
| 文档类型 | 技术报告（tech-report） |
| 模型名与版本 | LongCat-Video-Avatar 1.6（基于 1.5 的后训练升级） |
| 发布日期 | 2026-11-13（北京时间） |
| 官方链接 | https://github.com/meituan-longcat/LongCat-Video/blob/main/assets/LongCat-Video-Avatar-1.6-Tech-Report.pdf |
| PDF 链接 | https://raw.githubusercontent.com/meituan-longcat/LongCat-Video/main/assets/LongCat-Video-Avatar-1.6-Tech-Report.pdf |
| arXiv id | —（文末引用块留空，写了 `archivePrefix={arXiv}` 但没有 eprint；1.5 报告为 arXiv:2605.26486） |
| SHA-256 | 3eb115c18f1147683977d2a0664442794e4137ac1ea2810b57f8f68bfd061c44 |
| 页数 | 15 |

> 日期说明：PDF 元数据 `CreationDate` / `ModDate` 为 Fri Nov 13 19:28:47 2026 CST；HF 仓库 `createdAt` 为 2026-11-13T02:45:33.000Z（北京时间 10:45）。本条是 11-13 已发布、此前 T1 未入库的补档。

## 摘要

美团 LongCat 团队的技术报告介绍开源音频驱动数字人视频模型 LongCat-Video-Avatar 1.6，在冻结的基座上做两路后训练、再用各自的 LoRA 在同一条推理管线里合并：一路用 GRPO 强化学习优化感知运动（重点是口型与面部动作），另一路先用 DMD2 把采样从 50 步蒸到 8 步，再做长视频 rollout 与 on-policy self-distillation（OPSD，EMA teacher，改编自 OPSD-V 的 context-replacement），并改了 text–audio classifier-free guidance，以减轻面部过饱和和嘴唇发红（厂商自报，第 2 节）。作者称可生成超过 10 分钟、仍保持观感和时间一致性的视频。自家 Avatar Arena（33,051 次有效两两人类偏好投票，Bradley–Terry Elo）上，1.6 为 1068.1，排第 2，落后闭源 OmniHuman-2.0 的 1236.7，高于 1.5 的 1051.8（厂商自报，摘要图 / 第 1 节）。与 1.5 的对比基于 EvalTalker 风格基准、508 组图像–音频对、270 名参与者的 1–5 分人类像真评分：总体 3.006→3.322，写实子集 3.083→3.441，动画子集 2.246→2.114（作者认为动画长视频在 OPSD 训练集中较少，可能造成动画泛化略降）；专家标注的一致性问题率 19.9%→11.6%，音频–表情不匹配 13.0%→6.7%，唇色/分辨率改变 3.1%→0.0%，唇同步不匹配 83.7%→82.5%（文中说明唇同步是 0.5 倍速严查，因此基数偏高）；Fig. 8 另有不自然表情过渡 8.9%→6.5%、角色属性变化 1.4%→0.4%，正文还写说话人数不匹配 18.5%→11.2%（厂商自报，第 5 节 / Fig. 8）。以上评测均为厂商自报。Avatar Arena 为 15 种模型配对，标注员须先通过准确率至少 80% 的资格测验，因偶发 API 失败各对比的有效样本数不等。报告写推理时合并 GRPO LoRA 与 OPSD LoRA，但模型卡与 GitHub README 将已发布的 `loraA` / `loraB` 标为 DMD LoRA 与 OPSD LoRA，原文未解释对应关系。1.6 的总参数量、激活参数、上下文窗口和 API 价格官方未披露（不要把 GitHub README 里基础模型 LongCat-Video 的 13.6B 直接当成 1.6 的规模）。许可以 GitHub `LICENSE`（MIT，Copyright (c) 2025 Meituan）与 Hugging Face `cardData.license=mit` 为准；HF 模型仓无独立 LICENSE 文件。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-15 T2 标准版）。官方 raw PDF 15 页，SHA-256 与归档一致。头条数字均可在原文定位；Avatar Arena 与 Fig. 8 均为厂商自报。报告写推理合并 GRPO + OPSD LoRA，模型卡将已发布的 loraA / loraB 标为 DMD 与 OPSD LoRA。

## 深度解析

待补（已列入今日精读）

## 相关文档

- [LongCat-Video-Avatar 1.6 模型卡（Hugging Face）](../2026-11-13-longcat-video-avatar-1-6-model-card/README.md)
- [Introducing LongCat-2.5](../2026-11-01-longcat-2-5-blog/README.md)（同厂商另一条产品线，不是本模型）
