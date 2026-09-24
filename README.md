# 🐂 牛马报告技能 (Niuma Report Skills)

> *打工人写给打工人的结构化写作救命指南 · 把苦差事做成手艺活*

[![GitHub stars](https://img.shields.io/badge/⭐-点个Star救救牛马-yellow)](https://github.com/gz927cool/niuma-report-skills)
[![PRs Welcome](https://img.shields.io/badge/PRs-欢迎投喂-important)](https://github.com/gz927cool/niuma-report-skills/pulls)

---

![牛马报告技能 Hero · 打字 → 技能匹配 → 技能库展开 → 三次聚焦 → 牛马显形](assets/hero/hero.gif)


---

## 📢 来自牛马的独白

> *“牛马者，打工之畜也。日写日报，夜改周报，临晨三点还在对齐技术方案的颗粒度。”*

你是否也曾面临以下人间真实？

- 日报不知道写什么，憋了半小时只憋出“今日工作：处理需求”；
- 周报像流水账，老板看了只想问“所以你的价值在哪？”；
- 技术方案写了删删了写，总觉得自己在“屎上雕花”；
- 数据分析报告全是图表，但根本讲不出业务故事。

别慌。**我也是牛马，但我把这套活整明白了。**

本仓库是我在无数个加班夜里，用头发换来的 **报告写作方法论 & Claude Code 技能库**。不求升职加薪，只求每天少掉几根头发。

---

## 🗂️ 仓库目录

目前收录 **7 个 Claude Code 技能**——6 个报告类，外加 1 个开发辅助类（git 提交信息）——覆盖打工人从"记录今天"到"立项拿资源"，再到"把提交写明白"的全部写作场景：

| 技能目录 | 一句话定位 | 什么时候用它 |
|---|---|---|
| [`gz-daily-work-log/`](gz-daily-work-log/) | 📅 当日工作日志（日报） | 填 OA、给领导交今天的差——把当日 git 提交转成"问题驱动"的日报，而不是操作流水账 |
| [`gz-daily-thought-log/`](gz-daily-thought-log/) | 💭 工作思路日志 | 给自己/技术同事看的非正式复盘——还原"怎么想的"（问题链），而不是"做了什么"（任务清单） |
| [`gz-leadership-work-report/`](gz-leadership-work-report/) | 📊 周报 / 阶段报 / 专题汇报 | 把一段时期的技术工作浓缩成给决策层看的材料，价值密度全在"难点"上（结果 → 行动 → 问题 → 规划） |
| [`gz-proposal-report/`](gz-proposal-report/) | 📑 技术提案 / 立项报告 | 向决策层要资源、求立项——讲清"为什么做、值不值、要什么支持"，和给实施团队看的设计文档是两回事 |
| [`gz-analysis-report/`](gz-analysis-report/) | 📈 数据分析结果报告 | 从数据/模型产出原生写成、独立可读的结果文书，给业务/技术领导/第三方混合读者看 |
| [`gz-plain-report/`](gz-plain-report/) | 🗣️ 通俗版报告 | 把技术报告"翻译成人话"——给不懂统计和代码的业务方独立读懂的版本 |
| [`gz-git-message/`](gz-git-message/) | 📝 git 提交信息 | 写 commit 时——动机行+改动行一句一行，不罗列字段/代码名，数月后重读还能想起"为什么改" |

**场景速查**：今天干了啥 → `gz-daily-work-log`；今天想了啥 → `gz-daily-thought-log`；这周/这阶段干了啥 → `gz-leadership-work-report`；想让领导要资源 → `gz-proposal-report`；数据跑完了要交报告 → `gz-analysis-report`；领导说"看不懂" → `gz-plain-report`；提交代码要写提交信息 → `gz-git-message`。

报告类技能目录下的 `SKILL.md` 是完整写作方法论，配声明式 `manifest.yaml`（声明 always_load 共享纪律与按需 references，按需读入）；部分技能附 `references/` 与 `static/fragments/` 条件模块（提案模板/插图纪律/对话补全等，见各技能目录）；[`gz-shared/`](gz-shared/) 是内部共享依赖包（格式基线 / 数字纪律 / 交付语境），供其他 gz-* 技能按需引用——安装时 `cp -r gz-*` 已整体带上，不要只拷贝单个技能目录。`gz-git-message/` 是单文件技能，一个 `SKILL.md` 就是全部，拷走即用。

---

## 🧠 核心方法论（牛马三大铁律）

无论写哪种报告，底层逻辑逃不出这三条：

1. **目标导向**：动笔之前先问自己——“老板/读者到底想看到什么？”（而不是“我今天干了什么”）。
2. **数据说话**：能用数字不用形容词（“优化了性能” ❌ → “接口响应耗时从 200ms 降至 50ms” ✅）。
3. **结论先行**：金字塔原理——把最重要的结论/结果写在最前面，细节和过程放后面。不要让别人猜你的重点。

> 💡 每个技能的 `SKILL.md` 都是基于这三点展开的具体“作弊技巧”。

---

## 🚀 如何使用（通过 Claude Code）

这套技能不是让你"抄模板"的静态文档，而是 **Claude Code 技能（Skills）**——装好之后，你用大白话说需求，Claude 自动调用对应技能，基于你的真实工作痕迹把报告写出来。

### 第 1 步：安装到技能目录

需要本地已安装 [Claude Code](https://claude.com/claude-code)。然后把技能目录放进 Claude Code 的技能路径：

```bash
git clone https://github.com/gz927cool/niuma-report-skills.git

# 方式一：个人全局可用（所有项目都能触发）
mkdir -p ~/.claude/skills
cp -r niuma-report-skills/gz-* ~/.claude/skills/

# 方式二：单项目使用 / 团队随仓库共享
cp -r niuma-report-skills/gz-* your-project/.claude/skills/
```

> 注：[`gz-shared/`](gz-shared/) 是内部共享依赖包，上面的 `gz-*` 通配已整体带上；不要只拷贝单个技能目录而漏掉它。

重启 Claude Code（或新开会话），技能即生效。

### 第 2 步：用人话触发

不需要背任何命令。直接说需求，Claude 会根据你的话自动选择技能：

| 你说 | Claude 调用 |
|---|---|
| "帮我写今天的日报，要填 OA" | `gz-daily-work-log` |
| "总结一下今天的工作思路" | `gz-daily-thought-log` |
| "写个周报给领导" | `gz-leadership-work-report` |
| "把这个方案写成立项材料" | `gz-proposal-report` |
| "把这批数据的结果写份报告" | `gz-analysis-report` |
| "写个不懂技术的人也能看懂的版本" | `gz-plain-report` |
| "帮我把这些改动提交了，信息写好点" | `gz-git-message` |

也可以显式点名：在对话里输入 `/gz-daily-work-log`，或直接说"用 gz-plain-report 改写这份报告"。

### 第 3 步：补上下文，审稿收尾

技能触发后，Claude 会主动去读你的 git 提交记录、会话历史来还原事实。你只需要：

- **确认受众**：给谁看（领导 / 自己复盘 / 客户），决定口吻和详略；
- **补上"为什么"**：git 只记 what，哪些是临时插活、哪些是领导拍板的，一句话说明即可；
- **指定产出路径**（可选）：不指定则默认写入项目内的报告目录（如 `docs/work-log/`）。

## ✅ 关键前提（用前必读）

这套技能的核心能力是"从你的工作痕迹中还原事实、再组织成报告"，所以效果直接取决于你的工作习惯。以下前提满足得越好，报告写得越像你本人写的：

1. **工作集中在一个目录（仓库）下**。Claude 靠 `git log` 还原你做了什么——如果工作散落在十个目录、一半还没进版本管理，日报就只能靠你口述回忆了。强烈建议把每天的活儿都落在同一个 git 仓库里。
2. **每日工作用 git 提交留痕**。commit message 不必华丽，但要**当天提交、见名知义**（"修复订单导出超时"远好于 "fix bug"）。技能会自动从提交记录提取事实，再结合上下文补全动机——提交即存证，写日报时不用翻记忆。
3. **（加分项）保留会话记录**。日报/思路日志技能还能读取 `.specstory/history/` 下的 Claude Code 会话记录（由 [SpecStory](https://marketplace.visualstudio.com/items?itemName=SpecStory.vscode-specstory-ai) 等工具自动保存），用来还原"为什么这么做"——commit 只有 what，会话记录里才有 why。没有它技能也能用（自动退化到只基于 git log），但思路日志的效果会打折。
4. **报告产物落点固定并纳入版本管理**。技能默认把报告写入项目内的报告目录（如 `docs/work-log/`、`docs/report/`），建议将该目录纳入 git——报告本身也是工作痕迹的一部分，第二天写日报时又能被引用。

## 🤝 一起做快乐的牛马

这套技能是我个人的经验总结，但**一个人的力量是有限的，一群牛马的力量是无限的**。

如果你也有压箱底的“报告~~糊弄学~~方法论”，欢迎通过以下方式投喂：

- 🍴 Fork 本仓库
- ✍️ 提交 Pull Request
- 📦 新增你的分类（比如“会议纪要”、“面试述职”等）

只要对打工人有帮助，来者不拒！

------

## ⚠️ 免责声明

- 本仓库所有技巧均来自个人实战经验，**不保证升职加薪**，但保证能显著减少你写报告时的精神内耗。
- 使用本仓库技能导致 **“周报过早写完导致被安排额外任务”** 等后果，本人概不负责（建议写完先别急着发）。
- 如果觉得有用，请务必点个 ⭐Star，这是对我这头老牛马最大的精神安慰。

------

**愿天下牛马，都能准点下班。** 🍻