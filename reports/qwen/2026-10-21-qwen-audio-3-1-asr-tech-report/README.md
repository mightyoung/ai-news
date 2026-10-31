# Qwen · Qwen-Audio-3.1-ASR Technical Report

| 项目 | 内容 |
|---|---|
| 厂商 | Qwen |
| 文档类型 | 技术报告（tech-report） |
| 模型名与版本 | Qwen-Audio-3.1-ASR 家族（Flash / Flash-Streaming / Flash-Filetrans / Flash-Message / Next 等） |
| 发布日期 | 2026-10-21（北京时间） |
| 官方链接 | https://arxiv.org/abs/2610.28711 |
| PDF 链接 | https://arxiv.org/pdf/2610.28711v1 |
| arXiv id | 2610.28711 |
| SHA-256 | 31bbfe494e2fd74504a36ad3c2b0b012e92ab88f43bc63c34d6170c665c44ce5 |
| 页数 | 31 |

> 日期说明：arXiv 提交时间 2026-10-20 17:08 UTC，即北京时间 2026-10-21 01:08。署名 Alibaba Token Foundry, Alibaba Group；项目页 https://qwenaudio.github.io/qwen-audio-3.1-asr/ 。arXiv 许可：nonexclusive-distrib 1.0。

## 摘要

技术报告介绍 Qwen-Audio-3.1-ASR 音频语言模型家族，它在 Qwen-Audio-3.0-ASR 基础上改进语音识别，并扩展了分说话人转写和通用音频理解能力，支持 30 种语言和 16 种中文方言。家族按部署需求分为异步文件转写、低延迟流式、语音输入和非流式识别等变体，分说话人转写与音频理解只在部分变体中提供。报告首页图中，Qwen-Audio-3.1-ASR 在 GigaSpeechBench 7 种语言上宏平均错误率 15.09%（Flash 变体；3.0 版的 22.50% 取自其技术报告），分说话人 cpWER 宏平均 14.12%，Next 变体为 12.93%（4 个测试集均切成约 4 分钟片段；均为厂商自报）。API 为阿里云百炼 qwen-audio-3.1-asr-flash，北京地域输入 0.8 元 / 输出 2.7 元每百万 token；未开放权重。

## 原文

[report.pdf](report.pdf)（arXiv 版）

## 核验

[✅ 能核实](核验.md)：arXiv 元数据、表格数字与百炼价格对得上，评测全为厂商自报。

## 深度解析

[深度解析](深度解析.md)：Qwen MoE 解码器做的指令式 ASR 家族，靠多奖励 RL 和多老师在线蒸馏强化方言、热词、分说话人，但中英文基础识别略逊 3.0；只有百炼 API，无权重。

## 相关文档

- 暂无同一模型的其他文件夹
