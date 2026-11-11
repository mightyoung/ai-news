# Amazon · Mitra-v2 Technical Report

| 项目 | 内容 |
|---|---|
| 厂商 | Amazon |
| 文档类型 | 技术报告（arXiv）（tech-report） |
| 模型名与版本 | Mitra-v2（表格基础模型，77M 参数，合成数据预训练） |
| 发布日期 | 2026-11-10（北京时间） |
| 官方链接 | https://arxiv.org/abs/2609.04540 |
| PDF 链接 | https://arxiv.org/pdf/2609.04540 |
| arXiv id | 2609.04540 |
| SHA-256 | 903adb02c60a4774b14c7368d81c9ced9a2e4814e756853f70d1b97bed87ef5b |
| 页数 | 38 |

> 日期说明：arXiv v1 提交日期 2026-09-03；亚马逊官方博客 2026-11-10 才公开宣布并链接此报告，按官方发布日期归档。

## 摘要

摘要称 Mitra-v2 是只用合成数据预训练的表格基础模型，预训练分布比 Mitra-v1 更大更多样，骨干是小型二维 Transformer（行与列两个方向做注意力）。在 TabArena 和 TALENT（合计超过 300 个真实数据集）上评测，摘要称与工业级 TabFM、EXAONE Tabular 同水平，并以 77M 参数（分类 75.7M、回归 76.7M）匹配 16 亿参数的 TabFM（作者自报：TabArena 合并榜 1,774.6 vs 1,773.5 Elo，统计持平，一小时预算、默认微调 + 8 份 bagging，表 3，第 12 页）。TabArena 官方现榜（2026-11-09）上 Mitra-v2 为 1802、TabFM 为 1826，前面还有多个更新的模型。模型权重、推理与微调代码和评测结果以 Apache-2.0 许可发布。作者单位为 Amazon。

## 原文

[report.pdf](report.pdf)（arXiv 版）；另见 [来源.md](来源.md)

## 核验

✅ 能核实（「持平 TabFM」基于 9 月冻结池；TabArena 现榜 Mitra-v2 1802、TabFM 1826） · [核验.md](核验.md)

精读一句话：77M 参数、只用合成数据预训练的表格基础模型，在 9 月冻结榜上与 1.6B 的 TabFM 统计持平，但默认要每表微调 + 8 份 bagging，不是零样本。

## 深度解析

[深度解析.md](深度解析.md)

## 相关文档

- [Mitra-v2: Scaling synthetic pretraining for tabular foundation models（官方博客）](../2026-11-10-mitra-v2-blog/README.md)
