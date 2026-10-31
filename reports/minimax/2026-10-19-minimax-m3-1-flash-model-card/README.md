# MiniMax · MiniMax-M3.1-Flash 模型卡（Hugging Face）

| 项目 | 内容 |
|---|---|
| 厂商 | MiniMax |
| 文档类型 | 模型卡（model-card） |
| 模型名与版本 | MiniMax-M3.1-Flash |
| 发布日期 | 2026-10-19（北京时间） |
| 官方链接 | https://huggingface.co/MiniMaxAI/MiniMax-M3.1-Flash |
| PDF 链接 | 无（HF 模型卡页面） |
| arXiv id | — |
| SHA-256 | — |
| 页数 | — |

> 日期说明：HF 仓库创建于 2026-10-17 06:37 UTC（北京时间 14:37），最后修改 2026-10-30；公开发布以官方博客日期 2026-10-19 记。HF 仓库已放出完整权重（48 个 safetensors 分片约 250 GB，路由专家 NVFP4 量化，另附 DSpark 草稿头），2026-10-31 经 HF API 核实。

## 摘要

模型卡描述 MiniMax-M3.1-Flash 为总参数约 428B、激活 23B 的 MoE 模型，支持 1M 上下文，使用 MiniMax Sparse Attention（引用 6 月的 arXiv 2606.13392）与 DSpark 投机解码。卡内 CyberGym 为 82.2，许可证为 minimax-community。权重已在 HF 公开（MiniMax Community License：非商业免费，商用需署名并通知，年收入超过 2000 万美元的需授权）；API 价格每百万 token 输入 $0.15 / 输出 $0.60；第三方 AA 智能指数 29。

## 原文

[来源.md](来源.md)

## 核验

[⚠️ 部分核实（评测全为厂商自报、无技术报告；第三方 AA 实测速度低于官方说法）](核验.md)

## 深度解析

待补

## 相关文档

- [MiniMax · MiniMax M3.1 Flash: Redefining Agent Performance and Cost](../2026-10-19-minimax-m3-1-flash-blog/README.md)（官方博客）
