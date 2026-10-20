# @skunzu｜「Opus plans, Haiku scans, Sonnet ships」Claude Code ultracode 工作流帖 深度分析

**链接**：https://x.com/skunzu/status/2110808873322123547
**官方文档（帖内唯一外链）**：https://code.claude.com/docs/en/workflows（已读全文）；另读 model-config、changelog、models overview
**抓取时刻**：2026-10-16 14:10 CST（互动数据均为此刻；X API 与 fxtwitter 各取一次，略有出入）
**类型**：**方法论/技巧帖 + 营销**。技术主干（Claude Code 动态工作流 + 分模型分工）有官方文档支撑；但「Anthropic just dropped」「省 Opus token」「JEV 毫秒路由」三处都没有证据或被夸大；附带视频是**示意动画，不是实测**；同时在软推 Jev。

---

## 一句话结论
这是一条把 Claude Code 官方「dynamic workflows / ultracode」功能包装成「金矿技巧」的帖子：**核心机制是真的**（Claude 写一段 JS 编排脚本，运行时在后台并行调度大量子 agent，中间结果留在脚本变量里，主会话上下文只收最终答案），启动命令 `claude --model opus --effort ultracode` 也与文档一致；但它**不是 Anthropic 新发布**（该功能至少自 v2.1.160 起就有），**「Haiku 扫、Sonnet 改」的分模型分工不是默认行为**（文档：没指定模型时 agent 跑在会话模型上，即这里的 Opus），**「省 Opus token」不等于省钱**（文档明说 ultracode 会让每个任务总 token 更多、更快撞上用量上限），视频里的数字（16 agents、598/1,207 forks、18k→116k Opus tokens）是**演示动画**；JEV 那段是作者自己的叠加，与 Claude Code 官方无关，且没有任何数据。可以借鉴的是「计划写成脚本 + 只读扫描用便宜模型 + 改动用隔离副本 + 独立验证 + 两轮无进展就停」这套**设计**，不要当作已被验证的省钱方案。

## 原文事实表（时间已转 CST）
| 项 | 内容 |
|---|---|
| 作者 | @skunzu（Skunzu），简介 "covering ai models, tools, and the money behind them. facts and figures, plain english."；粉丝 386、关注 14、总推文 139、listed 11；账号创建 2026-09-18 22:23 UTC = **2026-09-19 06:23 CST（约 4 周）**；认证状态两个数据源不一致（fxtwitter 显示 individual verified，X API 为 false）【第三方，未核】 |
| 发布时间 | 2026-10-15 19:03:46 UTC = **2026-10-16 03:03:46 CST**；长推（note tweet），无编辑记录 |
| 互动（14:10 CST） | 浏览 23,501（X API）/ 23,523（fxtwitter）；点赞 200；转推 22；引用 0；回复 18；**书签 292**（书签 > 点赞） |
| 引用的帖子 | @0xCodila（codila，粉丝 26,017）2026-10-12 12:33 UTC = **10-12 20:33 CST** 的 X Article「Reverse Engineering: How to Get Anything for FREE With Most Dangerous Repo & Opus 5.5 (Full Course)」，帖文：「REA … lets your AI agent reverse engineer any app, down to the binary … rebuild any feature you pay for, for FREE」，浏览约 176 万、书签 6,171。**与本帖内容毫无关系**（本帖讲 Claude Code 工作流）；文章正文**只读到预览**，未展开 |
| 附带视频 | 1 条，20 秒，终端风格动画（标题「CLAUDE CODE ULTRACODE TIP · OPUS 5.5 PLANS · 16 AGENTS RUN」，页脚「X: @skunzu」）。我抽帧看了 3 帧：显示 workflow.js 4 阶段（scan/edit/verify/report），scan ×8（Haiku 5.5）、edit ×6（Sonnet 5.5）、verify ×2（Sonnet 5.5）；Opus tokens 计数 18k → 63k → 116k；「JEV · fork layer」forks 598 → 1,207；日志「23 findings → 4 rejected → 19 confirmed → 19 fixes ready to merge」。**我没看到任何「示意/模拟」标注**，数字整齐且单调上升【推断：脚本化演示，非真实运行日志】 |
| 正文要点 | ①「Anthropic just dropped one of the best tricks for Claude Code」②启动：`claude --model opus --effort ultracode` ③分工：Opus 5.5 写 workflow 脚本；Haiku 5.5 并行扫每个文件；Sonnet 5.5 在隔离副本里改；verify 阶段 Sonnet 5.5 复核；Opus 只读验证后结果并「签收」④「JEV engineering is the same move one layer down」：「哪个文件/哪个工具/重试还是停」这类分叉交给 JEV「毫秒级」处理⑤一段可粘贴给 Claude Code 的提示词（4 条：Opus 5.5 + ultracode；scan 用 Haiku 5.5、edit 用 Sonnet 5.5 且各自隔离副本；CLAUDE.md 加规则「每个发现必须经独立 verifier；修复循环两轮无进展即停」；把确定性分叉路由到 JEV；要求先展示 diff、我说 go 再改）⑥链接 code.claude.com/docs/en/workflows |
| 作者本人回复（我取到 25 条会话回复，其中作者 8 条） | 全是短句寒暄：「Its been my default for a while now」「Yep thats the one that saved me the most」「This is a big advantage tbh…」等；有人问「how many tokens did the whole swarm burn tho」，作者答「**More than I'd like to admit..**」——**没有给出任何 token/成本数字**；对「省下的 token 会不会又花在给小模型收拾烂摊子」答「Sometimes yeah, but the 2 round stop rule keeps the mess small」（03:54–05:17 CST） |

### 关键声明逐条核对
| 声明 | 核对 |
|---|---|
| Claude 把任务写成脚本、由 agent 群执行、主上下文只拿最终答案 | ✅ 官方文档原话：「A workflow script holds the loop, the branching, and the intermediate results itself, so Claude's context holds only the final answer」【第一方文档】 |
| `claude --model opus --effort ultracode` | ✅ 文档：`claude --effort ultracode` 开启 ultracode 且把 effort 设为 xhigh；该 flag 需 v2.1.203+。`--model opus` 在 Anthropic API 上解析为 Opus 5.5（model-config 页）。需 Opus 5.5 ≥ v2.1.280 |
| 「Anthropic just dropped」 | ❌/⚠️ **不是新发布**：changelog 里 `ultracode` 关键词在 **v2.1.160** 已出现（工作流触发词由 `workflow` 改名 `ultracode`），当前最新 v2.1.301；`--effort ultracode` 自 v2.1.203。具体首发日期 changelog 未写，**未核到**。帖子没有引用 Anthropic 官方账号的任何公告，唯一外链是文档页【推断：「just dropped」是营销措辞】 |
| 三个模型都存在 | ✅ models overview：Opus 5.5 $4/$20、Sonnet 5.5 $2/$10、Haiku 5.5 起价 $0.10/$0.50 每百万 token；Haiku 5.5 需 Claude Code ≥ v2.1.293 |
| Haiku 扫 / Sonnet 改 是工作流自带分工 | ⚠️ **不是默认**。文档（Cost 一节）：「When nothing else assigns one, the agent runs on your session's model」，即 `--model opus` 时 agent 默认也是 Opus；要省钱须**在提示里明确让 Claude 给脚本各阶段指定模型**（文档建议“Ask Claude to use a smaller model for stages that don't need the strongest one”）。帖子的提示词第 2 条恰好做了这件事，所以**提示词比标题更重要** |
| 「Opus 只出现三次：写 workflow、读验证结果、签收」 | ⚠️ 前两点符合设计；「签收」不是内置机制。文档还写明工作流**运行中不能向用户提问**（要分阶段签收须把每阶段拆成独立 workflow）。【推断】这里的「Opus 签收」只是 Opus 读结果，不是人工审批 |
| 每个改动在「isolated copy」里做 | ✅ 文档示例「transform each one in an isolated copy so edits don't conflict」；但需在提示里写明 |
| 「每个发现独立 verifier」「两轮无进展停止」 | ✅ 文档同样有「adversarially verify each finding」「stop when two rounds in a row make no progress」的示例提示；当 verifier 查不了（限流/报错）时，该发现标为**未验证**而非被否决 |
| 「way fewer Opus tokens」「bigger jobs」 | ⚠️ 只对 **Opus 主上下文**成立（因为中间 transcript 不进主会话）。**总花费未必更低**：文档「With ultracode on … each request uses more tokens and takes longer … reaches a session or weekly limit sooner」；且开 ultracode 后 Large workflow 警告和并发子 agent 限制都被关闭。帖子**没有任何前后对比** |
| 并发规模「16 agents」「a hundred agent transcripts」 | ⚠️ 文档：默认最多 16 并发（可调 1–256）；单次最多 1,000 agent；默认 size guideline 为 medium（<10 agents，Pro 为 small <5），只是建议。视频里 16 个 agent 在上限内但超过默认建议 |
| JEV 在毫秒内路由 micro-forks | ❌ **未核到**。Claude Code 工作流**没有** JEV 接入点；工作流脚本本身不能直接访问文件系统/shell/网络，只能让 agent 调工具【文档】，所以把 Jev 接进去要额外写 tool/MCP/脚本调用【推断】。Jev 的价格/接口/风险见旧稿。视频中的 598/1,207 forks、0.93/0.52 置信度是**动画数字** |

## 机制要点（原理拆解）
1. **把「计划」从对话挪进代码**：普通 subagent 是 Claude 一轮轮决定下一步，所有结果回灌上下文；workflow 是 Claude 写一次 JS（`agent()` / `pipeline()` / `parallel()`），运行时执行循环和分支，中间结果存在脚本变量。**省的是主上下文，不是总算力**——子 agent 仍然各自烧 token。
2. **分阶段异构模型（cascade）**：只读、量大、容错高的扫描阶段用最便宜模型；有副作用的改动阶段用中档；规划与最终阅读用最强。价格比（基础价）：Opus:Sonnet = 2:1；Opus:Haiku 输入 40:1（Haiku 提示 >100K 时 $0.50/$2.50，只有 8:1，见 `x_posts_2026-10-08_analysis.md` §2）。**所以「改」阶段换 Sonnet 只省约一半，大头在扫描阶段，而扫描是否真省取决于 Haiku 的漏报/误报**。
3. **对抗式验证与止损**：scan 产出发现 → 独立 verifier 复核（视频里 23 条里剔除 4 条）→ 只有存活者回到 Opus。配合「修复循环两轮无进展即停」，是防止并行 agent 互相覆盖/无限重试的断路器（回复区 @ruth_ozarx、@JyunsuitenshI 也认为这是最值钱的一条）。
4. **隔离副本 + 并行**：每个编辑 agent 在独立副本里改，避免并发写冲突；最终由主会话合并——合并冲突的成本仍在你这边。
5. **JEV 层（作者叠加）**：「确定性分叉（选文件/选工具/是否重试）用小分类器而不是大模型」本身是合理的 cascade 思路（见 beamnxw 稿），但在工作流里这类分叉多半**直接用代码就能判**（路径列表、重试次数、退出码），不需要模型；把它说成「一层之下的同一招」是类比而非实证。

## 工程落地（8 条）
1. **先小范围试跑**：文档建议先在一个目录/窄问题上跑，看 `/workflows` 里每个 agent 的 token 用量，再放大；全仓库 ultracode 前先用 `/workflows` 估算成本。
2. **别全局开 ultracode**：它会让每个「实质性任务」都编排工作流；日常用关键词 `ultracode: …` 或「use a workflow to …」单次触发，用完 `/effort ultracode off`。
3. **显式指定各阶段模型**：在提示里写明「扫描 agent 用 haiku、编辑 agent 用 sonnet、验证 agent 用 sonnet」；或设 `CLAUDE_CODE_SUBAGENT_MODEL=haiku` 作为未指定时的默认（文档：优先级低于 agent 单独指定）。**慎用 `CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL`**（changelog v2.1.296：让所有 workflow agent 用同一个模型）——它与「按阶段分模型」的目标冲突，是否覆盖脚本内指定未核到。
4. **扫描阶段只读**：scan agent 不给写/执行权限；写操作只在 edit 阶段的隔离副本里；先开 manual/accept-edits 模式，让「Yes, run it / View raw script」生效，**先看脚本再放行**（`Ctrl+G`/View raw script）。bypass 模式不会弹确认，不建议跑陌生提示词。
5. **自己量一次账**：同一任务跑「单 Opus 会话」vs「ultracode + 分模型」，记录总 token、美元估算、墙钟时间、被 verifier 剔除比例、合并后的返工量；用「每个被接受的修复的成本」而不是「Opus token 数」做 KPI。
6. **留退出条件**：把「两轮无进展即停」写进 CLAUDE.md 或工作流提示；限制 agent 总数（`workflowSizeGuideline` 设 small/medium）；设置 `--max-budget-usd`（changelog 提到该参数按 Sonnet 5.5 缓存价计价）等硬上限【本条预算参数**未实测**】。
7. **验证者要独立且能失败**：verify 阶段不要与 edit 同一提示/同一上下文；允许「未验证」状态进入报告；对高风险改动（鉴权、支付、迁移）保留人工评审，不要把 Opus「签收」当审批。
8. **对 JEV 段保持怀疑**：不要为了「毫秒路由」给工作流加第三方分类器依赖（外发数据、版本漂移、被注入风险）；确定性分叉先用代码判断，真要用 Jev 先看旧稿 `x_post_beamnxw_…_analysis.md` 的评测集+影子模式+固定版本做法。

## 风险与未核到
- **「Anthropic just dropped」不实**：功能已存在多个版本（≥v2.1.160）；我没找到 Anthropic 官方账号对「这个技巧」的单独发帖，**未核到**。
- **成本幻觉**：文档明说 ultracode 总消耗更高；帖子只展示「Opus 上下文小」，没有总成本、没有基线、没有质量对比。作者被问到 token 总量时没给数字。
- **质量风险**：Haiku 扫描的漏报（该报没报）无法被下游 verifier 发现——verifier 只复核「已发现」的东西，不补漏【推断】；回复区也有人质疑「subagents are less likely to follow instructions」（@1000xdesigner，**个人看法，无数据**）。
- **提示注入（防守面）**：扫描阶段会读仓库里任意文件/依赖/issue 文本，其中可能夹带对 agent 的指令。文档说明 workflow agent 的任务文本「不算用户授权」，且 agent 的工具调用走同样的权限检查/沙箱；仍应：扫描只读、编辑在隔离副本、网络与凭据最小化、对 agent 输出不直接执行。
- **一键粘贴提示词的风险**：该提示会让 Claude「Rebuild my Claude Code setup」，改 CLAUDE.md / 设置，且第 4 条会引入对第三方 Jev 的调用（数据外发、依赖新增）。作者加了「先给 diff、等我说 go」，这一句要保留；**不要去掉也不要在 bypass 模式下执行**。
- **营销属性**：账号约 4 周、386 粉丝，简介「money behind them」；开头「ABSOLUTE F*CKING GOLDMINE」+ 结尾「you'll use this on every big task from now on」是典型流量话术；与 beamnxw 一帖都在推 Jev，并共用「X engineering」命名【推断：同一叙事/可能同源推广；**未核到**与 TypeSafe 的商业关系】。
- **引用帖不匹配**：引用的是 @0xCodila 「逆向工程任意 App、免费重建你付费的功能」的文章，与本帖主题无关，疑似借流量/蹭关联【推断】。该文涉及绕过付费功能，**不建议照做**，本稿不展开，也未读正文。
- **回复区**：18 条回复里多为一两句附和；有带推广性质的账号（@tryatlas_cc 推自家「跨会话追踪」产品、@KowalPrato4o 夹带「账号/多端续跑」措辞、@frogbetbobby 的「VP machines … #VPSession1,847」像垃圾内容），**均不要点其链接/主页**；我没打开任何回复里的外链。互动里**真正有信息量**的是 @ruth_ozarx（并行 agent 互相 patch 导致合并冲突吃掉省下的 token）、@ajs6888（省下的 token 会不会花在收拾小模型烂摊子上，作者答「有时会」）。
- **未核到**：视频全 20 秒逐帧（只看了 3 帧）；`ultracode` 首发的具体日期；`CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL` 与脚本内模型指定的优先级；任何真实运行下的 token/成本数据；JEV 在 Claude Code 工作流里的实际延迟；@0xCodila 文章正文。

## 与已有稿的指针
- Jev（TypeSafe）的价格、Choice/Noul/Score、置信度公式、1.14 版本、对抗性输入风险、评测集与影子模式：见 `x_post_beamnxw_2108101310515925217_analysis.md`（§核对表、§机制要点 1–3、§风险）。本稿不重复。
- Jev「低延迟、够用智力」的路由框架（L0 分类/L1 通用/L2 旗舰）：见 `x_posts_C_D_analysis.md` §D。
- Haiku 5.5 的价格口径（≤100K 与 >100K 的 5 倍差）与 tokenizer 差异：见 `x_posts_2026-10-08_analysis.md` §2。
- Claude 代理的「止损/不可逆动作要在工具层拦」思路：见 `x_posts_2026-10-10_analysis.md`（评测里 Haiku 4.5 误提交表单一节，§「在工具层拦不可逆动作」）。
- 未在 `/workspace/output` 找到其他讨论 Claude Code 动态工作流 / ultracode 的旧稿。

---

## 用户简报版（约 270 字）
skunzu 这条是把 Claude Code 官方的「动态工作流 / ultracode」包装成省钱技巧：让 Opus 5.5 把任务写成脚本，Haiku 并行扫文件、Sonnet 在隔离副本里改、再独立验证，Opus 只读最后结果。机制是真的，官方文档（workflows 页）能对上，启动命令也对。但有四处要降调：一，不是 Anthropic 新发布，ultracode 至少 v2.1.160 就有了；二，分模型不是默认，没指定时子 agent 跑在会话模型（Opus）上，要靠提示词明确指定；三，「省 Opus token」不等于省钱，文档明说 ultracode 总 token 更多、更易撞限额，帖子没有任何实测，作者被问总消耗只答「比我愿意承认的多」；四，视频里的 16 agents、1,207 forks 是动画数字，JEV「毫秒路由」那段与 Claude Code 无关，也没数据，疑似在推 Jev。值得借鉴的是设计：只读扫描用便宜模型、改动放隔离副本、独立验证、两轮无进展就停；先小范围试跑并自己量总成本。别在 bypass 模式粘贴整段提示词，回复区带链接的推广别点。

## 核实清单
**已核实**
- 帖子全文（X API note_tweet + fxtwitter）、作者资料、发布时间（2026-10-16 03:03:46 CST）、互动数（14:10 CST）、引用帖 @0xCodila（文章仅预览）、25 条会话回复
- 官方文档 workflows 页全文：脚本编排、上下文只含最终答案、`--effort ultracode`（xhigh）、ultracode 增耗与限额、默认 16 并发/1,000 agent 上限、默认 agent 用会话模型、`CLAUDE_CODE_SUBAGENT_MODEL`、隔离副本与两轮无进展示例、无中途用户输入
- model-config：`opus`→Opus 5.5 / `sonnet`→Sonnet 5.5 / `haiku`→Haiku 5.5（Anthropic API）；版本要求（Opus 5.5 ≥2.1.280、Sonnet 5.5 ≥2.1.284、Haiku 5.5 ≥2.1.293）
- models overview：三模型价格；changelog：`ultracode` 关键词 v2.1.160、`--effort ultracode` v2.1.203、`CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL` v2.1.296，当前 v2.1.301
- 视频抽 3 帧，确认为动画式终端界面与上述数字

**未公开 / 未核到**
- Anthropic 官方对该「技巧」的发帖；ultracode 具体首发日期
- 任何真实运行的总 token/美元/质量对比；Haiku 扫描漏报率
- JEV 接入 Claude Code 的方式与「毫秒」延迟；作者与 TypeSafe 的商业关系；视频其余帧；@0xCodila 文章正文
- 回复区外链（未打开）；`CLAUDE_CODE_WORKFLOW_SUBAGENT_MODEL` 与脚本内指定模型的优先级；`--max-budget-usd` 对工作流子 agent 的实际约束（未实测）
