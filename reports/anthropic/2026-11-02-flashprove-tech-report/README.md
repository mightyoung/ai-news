# Anthropic · FlashProve: Hash-Based Proofs of LLM Inference at 400 Billion Parameters

| 项目 | 内容 |
|---|---|
| 厂商 | Anthropic（合作：EPFL、MIT 等，见博客作者列表） |
| 文档类型 | 技术报告（tech-report） |
| 模型名与版本 | FlashProve（证明对象：Llama 4 Maverick 形状的 400B MoE 整数模型，公开权重） |
| 发布日期 | 2026-11-02（北京时间，随博客发布） |
| 官方链接 | https://github.com/anthropics/FlashProve |
| PDF 链接 | https://github.com/anthropics/FlashProve/blob/main/paper/paper.pdf |
| arXiv id | — |
| SHA-256 | `bcb2a7b32f2f40c1be2737d295c4aa68f98a7771fe553c0dce1d244daf4d9a25` |
| 页数 | 114 |

## 摘要

FlashProve 是一个基于哈希的 commit-and-prove 论证系统：提供方承诺模型权重，再证明其贪心解码输出正确。摘要写明三项性质（知识可靠性、对一次请求的完备性和零知识）在 Lean 中机器检验，但定理针对 Lean 里的协议和证明器，不针对实际的 C++/CUDA 程序。C++ 和 CUDA 程序在一张 H100 上、24 条提示一批、权重掩码开启时，对公开权重的 400B MoE 整数模型稳定约每秒 110 个预填充 token，每个证明 18.74–18.81 MB、检查一个输出 token（厂商自报）。报告「Who wrote and checked this」一节写明：论文、软件和 Lean 代码几乎全部由 AI 系统在人的指导下写成，据作者所知没有人独立审读过这些证明和测试。

## 原文

[来源.md](来源.md)（仓库 Apache-2.0，但按本仓库默认规则不上传厂商 PDF）

## 核验

待核

## 深度解析

待补

## 相关文档

- 官方博客：[Progress on provable inference for large language models](../2026-11-02-provable-inference-flashprove-blog/README.md)
