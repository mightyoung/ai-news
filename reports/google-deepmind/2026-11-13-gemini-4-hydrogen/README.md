# Google DeepMind · Introducing Gemini 4 Hydrogen

| 项目 | 内容 |
|---|---|
| 厂商 | Google DeepMind |
| 文档类型 | 官方博客（blog） |
| 模型名与版本 | Gemini 4 Hydrogen（由 Gemini 4 Carbon 适配而来，见模型卡） |
| 发布日期 | 2026-11-13（北京时间） |
| 官方链接 | https://deepmind.google/blog/introducing-gemini-4-hydrogen/ |
| PDF 链接 | 见模型卡文件夹；文中称 Safety & Security Report「即将发布」，本次未见到独立技术报告 |
| arXiv id | — |
| SHA-256 | 网页 HTML：94da1d732aadfe1d8a5c7960b3e74c9e51cdc67c455489b2d8f3310825eb0355 |
| 页数 | —（网页） |

> 日期说明：页面写 Nov 12, 2026，Last updated November 13, 2026；`article:published_time` / `datePublished` 为 2026-11-12T18:00:00+00:00，即北京时间 2026-11-13 02:00。DeepMind 博客地址会跳转到 blog.google 同一篇文章。本条是 11-13 已发布、此前 T1 未入库的补档。

> 博客发布新模型，但没有单独的技术报告；模型卡已另建文件夹。安全报告模型卡写明「coming soon」，本次未收到。

## 摘要

博客宣布推出 Gemini 4 Hydrogen，面向日常编程和智能体工作流，并称 Carbon / Argon 仍承担更深、更长程的推理。文中自报：默认 high 思考档在 Artificial Analysis Intelligence Index 上为 51、高于 Argon 的 50，最高 xhigh 档为 54——与 2026-11-15 查询的 Artificial Analysis Intelligence Index v5.0.1 一致。输入/输出定价为每百万 token 1.50 / 7.50 美元，且在整个 100 万 token 上下文窗口内一口价，与官方 Gemini API / AI Studio 标准付费档及 OpenRouter 标准条目一致（官方另有 Batch/Flex、Priority、Cloud 非全球区域价，博客未列）。相对 Gemini 3.8 Flash，文中称默认 high 档完成任务快 2.5 倍（厂商自报），Terminal-Bench 4.1 为 57% 对 18.2%（18.2% 与官方 4.1 榜 Flash + mini-SWE-agent + high 的 18.2% ± 3.4% 一致；57% 与模型卡 57.0% 的 high 档、Cheating adjusted、mini-swe-agent vision 自测一致。官方榜 Hydrogen 条目是 Antigravity CLI / high 的 56.4% ± 3.0%。模型卡对照对象改为 Claude Sonnet 5.5 的 63.9%，属于对照不同，不是 57 自相矛盾）。博客同时介绍 Antigravity 的 Orchestrator，称在 Terminal-Bench 4.0 上接近 Carbon 的任务成功率，平均少用 24% 配额、快 19%（厂商自报；官方 4.1 榜未见 Orchestrator 条目，本次也未能打开 4.0 成绩表复核）。正文另称 Vals Tax Agent Bench 52.3% 第 1，与 2026-11-11 更新的 Vals 榜 52.30% 第 1 一致；但把 Vals Legal Research Bench 写成「并列第 1、55.8%」，同日榜实际为 Carbon 55.77% 第 1、Hydrogen 53.85% 第 6，与博客不符。暂无技术报告。完整 Safety & Security Report 在 2026-11-15 仍未发布。

## 原文

[来源.md](来源.md)

## 核验

[✅ 能核实](核验.md)（2026-11-15 T2 标准版）。T1 头条均可在原文定位；AA 51/54/50 与官方标准价 $1.50 / $7.50 能与第三方或官方页对上。博客正文把 Vals Legal Research Bench 写成并列第 1、55.8%，与 2026-11-11 榜不符。暂无技术报告。

## 深度解析

待补（本条为官方博客，默认不精读；模型卡已列入今日精读）

## 相关文档

- [Gemini 4 Hydrogen 模型卡](../2026-11-13-gemini-4-hydrogen-model-card/README.md)
- [Gemini 4 Carbon 模型卡](../2026-11-11-gemini-4-carbon-model-card/README.md)（Hydrogen 模型卡称架构与训练数据指向此卡）
- [Gemini 4 Carbon is now available](../2026-11-11-gemini-4-carbon-now-available/README.md)
