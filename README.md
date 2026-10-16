# ai-news

AI 论文原文（PDF）与中文深度解析归档。先按来源分，再按日期，再按论文一个文件夹。

## 目录结构

```
papers/
  huggingface/                       # 来源：Hugging Face 每日热门论文
    YYYY-MM-DD/
      README.md                      # 当日清单（标题、👍、机构、链接、PDF 与深度解析入口）
      <arxiv-id>-<short-english-title>/
        paper.pdf                    # 论文原文
        深度解析.md                  # 中文深度解析
  arxiv/                             # 来源：arXiv 每日精选「最值得先看」（补充归档）
    YYYY-MM-DD/
      README.md
      <arxiv-id>-<short-english-title>/
        paper.pdf
        深度解析.md
x-posts/                             # 来源：X 每日热帖里「建议深挖」的帖子
  README.md                          # 总索引（按日期倒序）
  YYYY-MM-DD/
    README.md                        # 当日清单
    原帖.md                          # 原帖原文
    深度分析.md                      # 中文深度分析
```

## 索引（按来源 → 日期倒序）

### Hugging Face 热门

- [2026-10-15](papers/huggingface/2026-10-15/README.md) — Jeva、Agent-Reflex、Urbex、GreenWAM、Last Secure Code Benchmark

### arXiv 精选

- [2026-10-16](papers/arxiv/2026-10-16/README.md) — FoveaVLA、Demystifying OPD、Long-Horizon RL Needs Muon
- [2026-10-15](papers/arxiv/2026-10-15/README.md) — ChunkAct、SkillScaffold

## X 技术帖子（x-posts/）

X 每日热帖里标了「建议深挖」的帖子：原帖原文 + 中文深度分析，按日期归档。

```
x-posts/
  README.md                          # 总索引（按日期倒序）
  YYYY-MM-DD/
    README.md                        # 当日清单
    原帖.md                          # 原帖原文
    深度分析.md                      # 中文深度分析
```

入口：[x-posts/README.md](x-posts/README.md)
