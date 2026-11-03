# Anthropic · Progress on provable inference for large language models

| 项目 | 内容 |
|---|---|
| 厂商 | Anthropic（Frontier Red Team） |
| 文档类型 | 官方博客（blog，安全研究） |
| 模型名与版本 | FlashProve（可证明推理系统原型；实验对象为 Llama 4 Maverick 形状的 4-bit 整数模型） |
| 发布日期 | 2026-11-02（北京时间） |
| 官方链接 | https://www.anthropic.com/research/provable-inference |
| PDF 链接 | 技术报告另建文件夹，见「相关文档」 |
| arXiv id | — |
| SHA-256 | —（网页） |
| 页数 | —（网页） |

> 日期说明：Anthropic Research 页面 Published Nov 2, 2026（仅日期）。

## 摘要

Anthropic 介绍了 FlashProve：用 zkSNARK（零知识简洁证明）让模型提供方先对权重做承诺，再证明每次回复确实来自这个模型，同时不泄露权重。博客称在单张 H100 上，对 400B 参数 MoE（Llama 4 Maverick 形状的整数模型，权重多为 4-bit）每秒约 110 个 prefill token 生成证明（24 条一批），每个证明约 19 MB、只检查 1 个输出 token（技术报告第 5 页），GPU 时间约为 vLLM 跑同样长度提示的 70–95 倍（厂商自报）。博客说这些改进由 Claude 完成，安全性的顶层陈述用 Lean 形式化；代码、Lean 证明和文档以 Apache 2.0 发布。

## 原文

[来源.md](来源.md)

## 核验

✅ 能核实，详见 [核验.md](核验.md)

## 深度解析

待补（博客不单独精读，精读见技术报告文件夹）

## 相关文档

- 技术报告：[FlashProve: Hash-Based Proofs of LLM Inference at 400 Billion Parameters](../2026-11-02-flashprove-tech-report/README.md)
