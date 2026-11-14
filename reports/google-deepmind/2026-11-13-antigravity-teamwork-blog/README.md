# Google Research · Advancing science & engineering with Antigravity’s /teamwork

| 项目 | 内容 |
|---|---|
| 厂商 | Google Research（归入 google-deepmind） |
| 文档类型 | 官方博客（多智能体工作流上的科学与工程结果） |
| 模型名与版本 | Gemini 4 系列 + Antigravity `/teamwork`（及 `/boost`、Deep Review）；不是新基座模型 |
| 发布日期 | 2026-11-13（页面日期；Research 博客 RSS `pubDate` 同日） |
| 官方链接 | https://research.google/blog/advancing-science-engineering-with-antigravitys-teamwork-feature/ |
| PDF 链接 | — |
| arXiv id | — |
| SHA-256 | 网页 HTML：df90f214b627d1f6ba67df46ce3ffeac9466438f8e137728a93126a27e5aeca0 |
| 页数 | — |

## 摘要

Google Fellow / VP Vahab Mirrokni 署名的 Google Research 博客，汇报用 Antigravity `/teamwork` 多智能体工作流、配合人类专家，在数学形式化、化学、系统软件和 ML 工程上的一批结果（均为厂商自报，未见独立复核）。数学方面：与港中文、南加州大学、卡内基梅隆等合作，用 Long Proof 模式（文中称在 Antigravity 里实现 Stellar Colosseum）证明并在 Lean 4 中形式化 Courtade–Kumar 猜想，完整证明约 5,000 万行 Lean；另称对 Weil 猜想的形式化约 180 万行 Lean、经过约 28,800 次子智能体调用，并形式化了一般整数环上希尔伯特第十问题的一个近期证明（逾 91.9 万行 Lean）等。化学：30 个专用智能体加物理信息光谱模拟器，在「复杂基准分子」上 top-1 精确匹配 95%、top-3 准确率 100%，称接近把单智能体表现翻倍（文中未给出基准名称和分子数量）。系统：FarArray 上无锁连通分量在万亿边图上称有 60x–90x 吞吐、40x–180x 加速，内存比 TCP 键值存储低 6 倍；用约 17 万行 Rust 重写 libgav1，一致性测试 100% bit-exact，在给分析工具并要求提速后，比原来的 C++ 和手写汇编在 x86_64 与 ARM 上快 20–30%；Borg 调度工作流上线 2 项改动，在部分硬件类型上把 TPU 任务抢占降低 24%。Deep Review：STOC 2027 有 578 篇投稿（超过三分之一）选择接受；进行中的作者调查 N=70，90% 认为反馈大体或几乎全部属实，90% 表示还会再用。官方称这些工具已向外开放，并向 10,000 名学术研究者提供六个月最高用量档的免费申请。暂无技术报告。

## 原文

[来源.md](来源.md)

## 核验

待核

## 深度解析

待补

## 相关文档

- 暂无同模型的既有技术报告文件夹
