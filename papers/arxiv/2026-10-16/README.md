# 2026-10-16 arXiv 精选「最值得先看」

来自 arXiv 2026-10-15（周四）公告批次的工作日精选，四个方向各挑 3–4 篇后选出最值得先看的 3 篇归档。每篇论文一个文件夹，内含 `paper.pdf` 与 `深度解析.md`（解析补齐前显示「待补」）。

| arXiv | 标题 | 作者 | 为什么值得看 | 链接 | PDF | 深度解析 |
|---|---|---|---|---|---|---|
| 2610.20064 | FoveaVLA: Foveation Actions Replace the Wrist Camera in VLAs | Bingao Chen, Lihan Zha, C. Karen Liu, Guy Tevet | 让 VLA 自己预测下一步该"凑近看"哪块区域，从高分辨率外部图像里裁剪细节，直接省掉腕部相机，基于 π0.5 实现，硬件和数据采集都更简单。 | [arXiv](https://arxiv.org/abs/2610.20064) | [PDF](2610.20064-foveavla-foveation-actions-vla/paper.pdf) | [深度解析](2610.20064-foveavla-foveation-actions-vla/深度解析.md) |
| 2610.19145 | Demystifying On-Policy Distillation: Where Does the Teacher's Advantage Live? | Yiping Li, Fan Zhao, Zhibo Hou 等 | 用"在师生分歧处翻转 token"的受控实验拆解在线蒸馏的收益来源，多次翻转能把准确率从 28.4% 拉到 74.5%（接近老师的 76.9%），做 OPD 替代 RL 的人很值得看。 | [arXiv](https://arxiv.org/abs/2610.19145) | [PDF](2610.19145-demystifying-on-policy-distillation/paper.pdf) | [深度解析](2610.19145-demystifying-on-policy-distillation/深度解析.md) |
| 2610.20256 | Long-Horizon RL Needs Muon | Kai Ruan, Jinghao Lin, Tao Chen 等 | 在仓库级 issue 修复这种长程 agent RL 上，给出 Muon + 单 rollout 异步训练 + 截断重要性采样的实用配方，并对比优化器选择，短小可直接落地。 | [arXiv](https://arxiv.org/abs/2610.20256) | [PDF](2610.20256-long-horizon-rl-needs-muon/paper.pdf) | [深度解析](2610.20256-long-horizon-rl-needs-muon/深度解析.md) |
