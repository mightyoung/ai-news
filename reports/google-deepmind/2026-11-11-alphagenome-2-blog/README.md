# Google DeepMind · AlphaGenome 2: Deciphering how cells read DNA to better understand disease

| 项目 | 内容 |
|---|---|
| 厂商 | Google DeepMind |
| 文档类型 | 官方博客 + 官方预印本（尚未正式发表） |
| 模型名与版本 | AlphaGenome 2 |
| 发布日期 | 博客 2026-11-11（页面日期，BJT 按 RSS 为 11-11 23:00）；预印本 PDF CreationDate 2026-11-10 21:54:54（北京时间） |
| 官方链接 | https://deepmind.google/blog/alphagenome-2-deciphering-how-cells-read-dna-to-better-understand-disease/ |
| PDF 链接 | https://storage.googleapis.com/deepmind-media/DeepMind.com/Blog/alphagenome-2-deciphering-how-cells-read-dna-to-better-understand-disease/alphagenome-2.pdf（官方预印本，78 页；文本未见可再分发许可，不上传仓库） |
| arXiv id | — |
| SHA-256 | 预印本：bf9a560ce501f252a397df40d1ebb28879a026ffc4b150aa7478bbafaede10e9；网页 HTML：576664e716381d1242faa9919711064f8d1537cf4663c2c4abffc54836ddd2c0 |
| 页数 | 预印本 78 页（PDF 物理页） |

## 摘要

博客称 AlphaGenome 2 是条件式 DNA 序列模型：输入 100 万碱基（1 Mb）序列加一个目标生物学条件（组织、细胞类型或状态），一次预测一个条件。预印本第 2 页写后训练在从 1.07 亿条人类 scRNA-seq 谱中抽样的单细胞上；第 3 页图 1d 写单细胞表达编码器训练于超过 1 亿条、覆盖 68 个组织的谱。在 TenK10K 上，90% 精确率下因果 sc-eQTL 召回为 30%，对比用单细胞数据微调的 AlphaGenome 1（AG1-sc）为 16%；方向预测在 90% 准确率下召回为 43% vs 23%（预印本第 4 页，仅厂商自报，未经同行评审，无第三方复测）。讨论部分写明高精度下仍只找回少数精细定位 eQTL（第 14 页）。目前通过 AlphaGenome API 面向非商业研究开放（表达量条件化单次最多 256 个细胞，见 FAQs），商业研究为私有预览；权重要等论文正式发表后才提供（第 53 页）。

## 原文

[来源.md](来源.md)

## 核验

✅ 能核实：头条数字与设置已在官方预印本第 4 页对上，但仍是厂商自报，预印本尚未正式发表、未见同行评审，无第三方复测。见 [核验.md](核验.md)（2026-11-12 更正：原版漏掉官方预印本）。

## 深度解析

待补
