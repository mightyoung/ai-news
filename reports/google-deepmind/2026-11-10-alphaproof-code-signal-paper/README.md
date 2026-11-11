# Google DeepMind · AlphaProof Code: Verifying Signal’s Security at the Machine-Code Level

| 项目 | 内容 |
|---|---|
| 厂商 | Google DeepMind |
| 文档类型 | 技术报告（论文）（tech-report） |
| 模型名与版本 | AlphaProof Code（多智能体形式化验证框架；Gemini Carbon 驱动证明智能体） |
| 发布日期 | 2026-11-10（北京时间） |
| 官方链接 | https://deepmind.google/blog/introducing-alphaproof-code/ |
| PDF 链接 | https://deepmind.google/documents/36/Formal_Verification_of_Signal_4.pdf |
| arXiv id | — |
| SHA-256 | cf813b7192ed247d33003e09cfa612fcda695502eb03768cd96c849afe1cb0a4 |
| 页数 | 57 |

> 论文封面日期 2026-11-10；论文只在 deepmind.google 提供，本次没有查到 arXiv 版。

## 摘要

论文提出 AlphaProof Code：一个由人类指导的 Lean 规约编写智能体、一套 AArch64 机器码形式语义和一组自主证明智能体组成的框架，证明只有通过 Lean 内核检查并且与保留的规约一致才会被接受。应用于 libsignal，摘要称生成约 650 万行机器检查的 Lean 证明代码，依托约 2.6 万行可信规约与 AArch64 语义（约 1.8 万行规约定义 + 约 8 千行 AArch64 语义，第 25 页）；证明覆盖 PQXDH 握手与 Triple Ratchet，建立前向保密、认证、泄露后安全和握手保密。作者署名为 Google DeepMind 与 Google（厂商自报）。Lean 代码在 google-deepmind.github.io/code-verification。证明完全由 Gemini 4 Carbon 驱动的智能体团队生成，规约由人类与 Gemini 4 Carbon、Claude Opus 5.5 驱动的智能体共同起草（第 25–26 页）；代码仓库 README 声明 Apache-2.0，LICENSE 文件只列第三方条款，libsignal 部分为 AGPL-3.0。

## 原文

[来源.md](来源.md)

## 核验

✅ 能核实（作者自报；可信基约 1.8 万行规约 + 8 千行 AArch64 语义） · [核验.md](核验.md)

## 深度解析

待补

## 相关文档

- [Introducing AlphaProof Code（官方博客）](../2026-11-10-alphaproof-code-blog/README.md)
