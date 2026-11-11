# Amazon · Mitra-v2: Scaling synthetic pretraining for tabular foundation models

| 项目 | 内容 |
|---|---|
| 厂商 | Amazon |
| 文档类型 | 官方博客（blog） |
| 模型名与版本 | Mitra-v2 |
| 发布日期 | 2026-11-10（北京时间） |
| 官方链接 | https://www.amazon.science/blog/mitra-v2-scaling-synthetic-pretraining-for-tabular-foundation-models |
| PDF 链接 | 见 mitra-v2-technical-report 文件夹 |
| arXiv id | 2609.04540 |
| SHA-256 | — |
| 页数 | —（网页） |

## 摘要

亚马逊科学博客（2026-11-10，作者 Chris Kong）介绍 Mitra-v2：预训练表格行数是 v1 的 10 倍、列数约 3 倍，新增混合 SCM 先验和混合优化器；部署时用 SVD 处理宽表、用层级树处理超过 10 类的任务，默认对每张新表短暂微调并做 8 份平均（bagging），因此不是严格零样本。博客称在 TabArena（51 个数据集）上领先单模型，在两个版本都能原生运行的 33 个数据集中有 32 个优于 v1，并在一小时预算内完成全部 51 个（均为厂商自报）。权重在 Hugging Face 以 Apache-2.0 发布。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- [Mitra-v2 Technical Report](../2026-11-10-mitra-v2-technical-report/README.md)
