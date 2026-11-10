# YeeSales AI

## Your AI-powered Global Sales Operating System

专为中国企业出海获客、国际商务拓展与全球销售团队打造。

**版本** v2.0 ｜ **日期** 2026-11-10 ｜ **对应原型** `prototype.html`

---

## 0. 这份文档是什么

本文档取代 v1 的《产品愿景》单页，把三条线对齐到同一个口径：

| 层 | 内容 | 对谁有用 |
|---|---|---|
| 产品层 | 定位、信息架构、模块规格、评分模型、审批流 | 产品、业务负责人 |
| 工程层 | 数据模型、状态机、集成边界、Demo 剧本 | 研发、实施 |
| 商务层 | 差异化叙事、成效指标、路线图 | 汇报、对外演示 |

网页原型（`prototype.html`）是这份文档的可交互版本：文档里的每一条规格，都能在原型里点到对应的界面。**所有数据为虚构演示数据，不代表任何真实客户。**

---

## 1. 产品愿景与定位

> 不只是记录销售做过什么，而是 AI 主动帮助销售完成下一步应该做什么。

市面上的 CRM（HubSpot / Zoho / Salesforce）解决的是**记录与流程**：把已经发生的销售动作结构化存档。它们默认销售是在一个成熟市场里、用一套熟悉的语言、和一批查得到底细的客户打交道。

出海销售不是这样。客户在拉各斯、迪拜、圣保罗，公开信息残缺；机会产生在展会展台的三分钟寒暄里，而不是官网表单里；一次出差七天跑五国，回来面对 200 张名片和 40 段录音。**信息在采集环节就漏掉了，后面再好的 CRM 也只是在管理空洞。**

YeeSales AI 把重心前移到**采集与判断**：让 AI 在展台、在车上、在酒店大堂就把对话变成结构化记录，把记录变成评分，把评分变成任务、草稿和时间表——人只负责确认和发出去。

### 一句话差异化

| | 传统 CRM | YeeSales AI |
|---|---|---|
| 起点 | 客户已进入系统 | 客户还不知道我们是谁 |
| 数据来源 | 人工填表 | 九源自动归集（语音／纪要／IM／邮件／名片／照片／PDF／手记／CRM） |
| 核心产出 | 报表 | 下一步动作（任务、草稿、行程、路线图） |
| AI 角色 | 辅助输入 | 承担动作，人类审批 |
| 地域假设 | 单一市场 | 跨境、多时区、多语言、多监管 |

---

## 2. 我们解决的三断点

**断点一：展会上采不进来。**
BD 一天站 8 小时，见 20 个客户。当场记笔记不礼貌、也记不全；回酒店已经晚上十点，第二天记忆就开始衰减。等回到国内再补，只剩"见过、聊得还不错"。

**断点二：采进来的是文本，不是判断。**
40 段录音转成 4 万字逐字稿，等于没整理。销售需要的是：这家值不值得跟、下一句该说什么、卡在谁那里。

**断点三：判断完落不到动作。**
知道该跟进，但邮件没写、任务没建、行程没排、合规材料没催。热度在 72 小时内衰减，超过一周基本凉了。

对应的产品答案：**Capture → Understand → Act**。三条断点分别由 Meeting Assistant、Debrief Agent / 评分模型、Follow-up Agent + Action Center 承接。

---

## 3. 信息架构：六大模块

导航按销售真实工作流排列，而不是按数据库表排列。

| 序号 | 模块 | 回答的问题 | 二级入口 |
|---|---|---|---|
| 01 | AI Sales Cockpit | 今天该干什么 | — |
| 02 | Lead Generation | 客户在哪里 | — |
| 03 | Global Engagement | 怎么见到人、见到了怎么记 | Event Intelligence、Travel Planner |
| 04 | Customer 360 | 这家客户到底是谁 | — |
| 05 | Deal Management | 这单推进到哪了 | Pipeline、Deal Roadmap |
| 06 | AI Workforce & Automation | 谁在替我干活、接了什么系统 | AI Workforce、Integrations |

设计原则：**一级导航最多六个**。超过六个，销售就不点了。所有"看起来重要但不常用"的能力（评分明细、来源记录、审批队列）都收进抽屉和二级 Tab，不占导航。

---

## 4. 模块规格

每个模块按五要素描述：**目标 / 关键界面 / AI 动作 / 数据来源 / 人工审批点**。

### 4.1 AI Sales Cockpit

- **目标**：打开就知道今天做什么，不用自己翻五个系统拼线索。
- **关键界面**：五个 KPI（活跃线索、合格商机、Pipeline 金额、本周会议、逾期跟进）+ AI Recommendations 列表（每条带优先级 P1/P2/P3 和一句话理由）+ Pipeline by stage + Recent interactions + AI Agent activity。
- **AI 动作**：跨模块聚合待办，按"预期影响 ÷ 所需时间"排序；对逾期和沉默客户主动催办。
- **数据来源**：全部下游模块的汇总视图，本身不产生数据。
- **人工审批点**：Recommendations 只是建议，点进去才产生真实动作。

### 4.2 Lead Generation

- **目标**：把"目标市场"变成"有名字、有联系人、有触发事件的线索列表"。
- **关键界面**：ICP 定义、线索池、信号流（牌照变更、走廊上线、招聘中国业务岗位）、批量加 CRM。
- **AI 动作**：Prospecting Agent 按 ICP 扫描公开信息；Account Researcher 做会前情报（牌照、走廊、中国敞口、决策人）。
- **数据来源**：公开注册信息、监管公告、招聘网站、展会名录、既有客户转介绍。
- **人工审批点**：AI 只提议线索与分级，进入 CRM 需人工确认；对"无公开中国业务痕迹"的公司会主动降级并标注原因，而不是凑数。

### 4.3 Global Engagement

出海销售最高频的场景，拆成两个二级入口。

#### Event Intelligence —— 展会五 Tab

展会不是"参加完就结束"，而是**一次集中采集、集中转化**的事件。五个 Tab 对应一条流水线：

| Tab | 解决什么 | 关键内容 |
|---|---|---|
| Overview | 这场展会值不值 | 32 家公司 / 21 次业务互动 / 14 条来源记录 / 9 个合格商机 / 26 条建议任务 / 12 封邮件草稿；线索分层 Tier A 3 家、Tier B 6 家、Tier C 23 家 |
| Account Intelligence | 每家客户到底是谁 | 公司画像、牌照与走廊、中国敞口、决策人、Fit Score 与理由、来源记录链接 |
| Meeting Insights | 那 20 分钟聊了什么 | 逐字稿／纪要摘要、支付业务专项字段（收单币种、结算币种、受益人类型、用途、量级、对华付款需求）、Confirmed / AI-inferred / Missing 三级事实标记 |
| Action Center | 谁来把这些变成动作 | 18 条建议记录（公司／联系人／商机／任务／草稿），支持全选批准、逐条批准、改后批准、驳回、合并重复 |
| Reports & Export | 怎么向上汇报 | 复盘报告、BD insights、按客户分组的总结、导出（模拟） |

**五 Tab 的设计意图**：把"复盘"从一次性写 PPT 的动作，变成一条可审核的数据流水线。人只需要在 Action Center 做判断题，不需要做录入题。

#### Travel Planner

- **目标**：把"七天五国见十二家客户"排成一条不折腾的路线。
- **关键界面**：按地理位置聚类（同城／同区合并）、天气与当地节假日提示、文化注意事项、每天 1–2 次转场、晚间 formal dinner 就近安排。
- **AI 动作**：读日历与客户地址，生成行程草案；冲突时给两个方案而不是报错。
- **数据来源**：飞书日历（最高优先级事实源）、客户地址、公开天气与节假日数据。
- **人工审批点**：行程草案需 BD 确认后才写回日历；**同步日程绝不添加任何参会人**（避免以用户名义向客户发邀约）。

### 4.4 Customer 360

- **目标**：见到客户前 3 分钟能读完，且知道哪些数字可信。
- **关键界面**：公司档案、联系人图谱、历史互动时间线（邮件／IM／会议／展会）、商机与合同、合规材料状态、来源记录。
- **AI 动作**：把九源互动压缩成时间线摘要；标注数字的来源与可信度。
- **数据来源**：CRM + 邮箱 + 飞书 + WhatsApp + 展会记录。
- **人工审批点**：AI 推断的联系人角色、决策链位置必须人工确认后才写库。

### 4.5 Deal Management

#### Pipeline

阶段固定为八段，避免每个销售自定义一套口径：

`Lead → Qualified → Meeting → Proposal → Negotiation → Compliance → Integration → Live`

- 合规（Compliance）单独成段，不是审批动作而是**阶段**：KYC／UBO／牌照材料不齐，不允许进入 Integration。
- 看板支持按负责人、区域、金额、停滞天数筛选。

#### Deal Roadmap

- **目标**：把复盘结论变成一张 45 天执行计划。
- **关键界面**：甘特图（D1–D45，八个阶段：Discovery / Engagement / Solution / Commercial / Compliance / Integration / Pilot / Go Live），每行可改负责人、改日期、加依赖。
- **AI 动作**：根据评分与缺口自动生成任务序列（缺 UBO → 先排合规任务，而不是先报价）。
- **数据来源**：Meeting Insights + 评分明细 + 合规缺口。
- **人工审批点**：`Approve plan` 后任务才写入飞书任务；`Push to Feishu` 为模拟动作，原型中不实际调用。

### 4.6 AI Workforce & Automation

#### 六个 Agent

| Agent | 职责 | 典型动作 | 审批点 |
|---|---|---|---|
| AI Prospecting Agent | 全球获客 | 按 ICP 扫描目标市场，抓牌照变更、走廊上线、招聘信号 | 线索入池需确认 |
| AI Account Researcher | 会前情报 | 查牌照、走廊、中国敞口、决策人，输出 A/B/C 分级 | 分级可被 BD 覆盖 |
| AI Travel Planner | 行程与后勤 | 地理聚类、天气／节假日、每天转场次数控制 | 行程需确认才写日历 |
| AI Meeting Assistant | 采集与抽取 | 录音转写、飞书会议纪要、IM 摘要，抽取支付专项字段 | 抽取结果需核对 |
| AI Event Debrief Agent | 归集与评分 | 把 21 次互动归集成公司／联系人／商机／任务／草稿 | **绝不自行写 CRM** |
| AI Follow-up Agent | 起草，不发送 | 基于逐字稿与历史线程写 12 封草稿 | 人工发送，AI 无发信权限 |

**设计红线**：任何 Agent 都不能"替人做外部动作"。可以起草、可以建议、可以准备，但不能发信、不能改共享日历、不能对外承诺。

#### Integrations

原则：**只读优先、缺失要显形**。

| 来源 | 状态 | 说明 |
|---|---|---|
| Feishu（日历／IM／任务） | Connected | 出差期间日历是最高优先级事实源；现场手记的短事件＝实际会面清单 |
| 企业邮箱 | Connected | IMAP 粗筛 + 本地精筛；`.ics` 为日程权威时间源；草稿箱可写，发信不代执行 |
| WhatsApp Desktop | Needs permission | 本地库只读解析；缺权限时该来源标 `!!`，不阻断其他来源 |
| 展会 App | Connected | 名录、预约、展位互动 |
| CRM | Simulated | 演示用，写入需审批 |

---

## 5. 数据模型：Source Record 与事实分级

每一条原始素材都是一条 **Source Record**，独立编号、独立状态，可回溯到具体某段录音的第几分钟。

**必带字段**

`Source ID` · `Source type` · `Capture time` · `Owner` · `Linked company / contact / meeting` · `Processing status` · `Consent status`

**九类来源**

1. 现场录音
2. 飞书会议纪要 / 逐字稿
3. WhatsApp 对话摘要
4. 邮件线程
5. 名片照片
6. 展台照片
7. PDF 宣传资料
8. BD 手记（语音或文字）
9. 客户提供的牌照包 / CRM 更新

**三级事实标记**——这是整套系统最重要的一个设计：

| 标记 | 含义 | 用法 |
|---|---|---|
| Confirmed | 客户当面确认，或来自官方文件 | 可直接用于报价、合规判断 |
| AI-inferred | AI 从上下文推断 | 必须人工核对后才能写库 |
| Missing | 该字段本应有但没有 | 显式列出缺口，驱动下一轮提问 |

**支付业务专项字段**（跨境场景必备，通用 CRM 没有）

`Origin country` · `Destination country` · `Collection currency` · `Settlement currency` · `Beneficiary type` · `Payment purpose` · `Volume / frequency` · `China payout requirements`

> 口径纪律：客户自报交易量一律视为"未核实"，评分时按中位打折，并在界面上标明来源。**客户填报 ≠ 已核实。**

---

## 6. AI 线索评分模型

Fit Score 满分 100，五维加权，每一项都能点开看依据。

| 维度 | 权重 | 判断依据 |
|---|---|---|
| Strategic Fit | 25% | 是否持牌 PSP／MSO、走廊覆盖、与 B2B 定位的重合度 |
| China Payout Demand | 25% | 对华付款占比、是否主动提出、是否有人民币结算需求 |
| Transaction Potential | 20% | 自报量级（打折后）、交易频次、客单价 |
| Licence & Compliance Readiness | 15% | 牌照有效性、UBO 层数、AML 体系成熟度 |
| Engagement & Buying Intent | 15% | 到场层级、是否主动约二轮、回复速度 |

**示例：AtlasPay Global — 94 / 100 · Tier A**

| 维度 | 得分 | 依据 |
|---|---|---|
| Strategic Fit | 24 / 25 | 持牌 PSP、14 条走廊、定位完全重合 |
| China Payout Demand | 25 / 25 | 62% 的量进入中国，现场主动提对华付款 |
| Transaction Potential | 18 / 20 | 自报 40–60M USD/月，口径未核实，按中位打折 |
| Licence & Compliance | 13 / 15 | CBK 牌照有效，UBO 层数未确认 |
| Engagement & Intent | 14 / 15 | CEO 级未到场，但主动约了二轮 |

**两条规则**

1. **可解释优先于准确**：宁可分数略低，也要让人看懂为什么。销售不信的分数等于没有分数。
2. **BD override 优先**：人可以改分，但必须填理由，改动留痕。AI 不是裁判，是参谋。

---

## 7. Human-in-the-loop 审批流

AI 产出的一切都是**候选记录**，不是事实。

```
AI 抽取  →  Staged（待审）  →  Approved（批准）  →  Written to CRM
                    ↓
              Edited（改后批准）
                    ↓
              Rejected（驳回，保留原因用于调模型）
                    ↓
              Merged（合并重复，保留主记录与来源链）
```

**Action Center 的四种操作**

- `Approve All Validated`：只批准数据完整的，缺字段的自动留在待审
- `Approve Selected`：逐条勾选
- `Edit Before Approval`：先改再批
- `Reject` / `Merge Duplicates`

**边界文案（界面上必须出现）**

> Nothing is written to CRM until you approve.
> Drafts remain drafts until a human sends them. The system has no send permission.

---

## 8. 端到端 Demo 剧本：AtlasPay Global

一场展会 → 一个商机的完整链路，用于对外演示（约 6 分钟）。

1. **Cockpit**：首页提示"SFF 2026 复盘已就绪：32 家公司 · 21 次互动 · 9 个合格商机 · 26 条任务 · 12 封草稿待批"。
2. **Event Intelligence · Overview**：看到本场展会的投入产出与线索分层。
3. **Account Intelligence**：点开 AtlasPay Global，读公司画像与 94 分评分明细。
4. **Meeting Insights**：展开 8 分钟会谈的摘要，指出三条 Confirmed、两条 AI-inferred、一条 Missing（UBO 层数）。
5. **Action Center**：批准 18 条记录中的 12 条，把缺 UBO 的那条留着——演示"AI 不会帮你蒙"。
6. **Deal Roadmap**：系统据此生成 45 天计划，第一步不是报价而是补 UBO 材料。
7. **AI Workforce**：Debrief Agent 状态从 `Needs approval` 变为 `Completed`，Follow-up Agent 产出草稿但状态停在 `Waiting`。
8. **邮件草稿**：打开草稿，明确写着"AI 起草，人工发送"；发送按钮在真实系统里才可用。

**演示纪律**：全程不假装任何外部动作已真实完成。导出、写日历、发邮件、建飞书文档，一律标注 simulated 或 not connected。

---

## 9. 视觉与设计规范

**基调**：企业级 SaaS，克制、密、可扫读。参考 Salesforce / HubSpot / Linear 的信息密度，但不做它们的复杂感。

| 项 | 规范 |
|---|---|
| 主色 | 易宝绿 `#00A870`（hover `#008E5E`，active `#00714A`） |
| 主色浅底 | `#EAF7F1` / `#D5EFE3` |
| 文字 | `#12161A` / `#3B464D` / `#6A767D` / `#96A1A7` 四级 |
| 分隔线 | `#E6EBE8`，浅线 `#F2F5F3` |
| 背景 / 卡片 | `#FAFBFA` / `#FFFFFF` |
| 语义色 | 待审 `#A96500`、风险 `#BE3A2C`、信息 `#2563EB`、AI `#6D5BD0` |
| 字体 | Inter / PingFang SC，正文 13px，行高 1.6 |
| 圆角 | 容器 10px、控件 7px、标签 5px |
| 阴影 | 仅两级，且极浅；靠留白和线分层次，不靠阴影堆叠 |
| 图标 | 全部内联 SVG sprite，线宽 1.65，不用 emoji |

**禁止项**：大面积渐变、彩色卡片墙、装饰性插画、动效炫技。销售工具的可信感来自"信息清楚"，不来自"设计用力"。

**动效**：只做 200–300ms 的位移与透明度过渡，不做视差、不做滚动动画。所有入场动画必须**不依赖 opacity 从 0 开始**，否则截图和低性能设备上会出现整页发白。

---

## 10. 模拟 vs 真实：能力边界声明

原型阶段的能力边界必须显式写在界面上，而不是靠口头解释。

| 能力 | 原型状态 | 真实系统行为 |
|---|---|---|
| 数据 | 全部虚构 | 来自九源接入 |
| 导出报告 | 模拟下载 | 生成 PDF / Excel |
| 写飞书任务 | 模拟 | 调用飞书任务 API，需 OAuth |
| 同步日历 | 模拟 | 写默认日历，**零参会人** |
| 发邮件 | 从不代发 | 存草稿箱，人工发送 |
| 写 CRM | 需审批后模拟写入 | 审批后调用 CRM API |

**为什么这么较真**：演示时把模拟动作说成真实动作，一次就能毁掉可信度；而在真实系统里，AI 直接发信或改客户日历会造成无法撤回的商务事故。

---

## 11. 路线图

### P0（Demo 就绪，已完成于原型）

- 六大模块导航与九视图
- Event Intelligence 五 Tab + SFF 2026 数据集
- Fit Score 可解释抽屉
- Action Center 审批流（批准／改后批准／驳回／合并）
- Deal Roadmap 45 天甘特
- AI Command Center + AI Activity Center
- 全站 simulated 标识与边界文案

### P1（可交付客户试用）

- 真实飞书接入：日历只读、任务写入、IM 拉取
- 企业邮箱 IMAP 接入 + 草稿箱写入
- 录音转写与支付字段抽取（中／英／法）
- CRM 双向同步（先 HubSpot，再 Salesforce）
- 权限模型：BD / 主管 / 管理员三级

### P2（规模化）

- WhatsApp 本地库只读接入
- 多语言界面（英／中／西／法）
- 评分模型按区域校准（非洲／中东／东南亚各自基线不同）
- 团队级 insights 聚合（不只单兵作战）
- 与资金侧系统打通：报价、通道能力、清算时效

---

## 12. 成效衡量

不看"AI 生成多少条"，看销售是否真的省了时间、提了转化。

| 指标 | 定义 | 目标 |
|---|---|---|
| 展会到记录时长 | 从会面结束到进入系统 | 从 3 天降到 2 小时 |
| 记录完整率 | 支付专项八字段齐全比例 | ≥ 70% |
| 建议采纳率 | Action Center 批准数 ÷ 建议数 | ≥ 60%（低于 40% 说明 AI 判断不可信） |
| 首触及时率 | 72 小时内发出首封跟进的比例 | ≥ 90% |
| 商机转化 | Qualified → Proposal | +20% |
| 单兵产能 | 人均同时推进商机数 | +30% |

**反向指标**（用来发现系统在添乱）：待审积压天数、AI 推断被驳回率、字段反复修改率。

---

## 13. 术语表

| 术语 | 含义 |
|---|---|
| ICP | Ideal Customer Profile，理想客户画像 |
| PSP / MSB / MSO | 支付服务商 / 货币服务商 / 货币服务机构 |
| UBO | 最终受益人，合规穿透的核心对象 |
| VA | 虚拟账户 |
| POBO | Payment On Behalf Of，代收代付 |
| Fit Score | 线索匹配度评分，0–100 |
| Source Record | 一条可回溯的原始素材记录 |
| Confirmed / AI-inferred / Missing | 事实三级标记 |
| Action Center | 建议记录审批中心 |
| Deal Roadmap | 商机 45 天执行计划 |

---

## 14. 交付物清单

| 文件 | 内容 |
|---|---|
| `prototype.html` | 可交互原型，单文件、零外部依赖、可直接部署 |
| `prototype.v1-中文版.html` | 第一版中文业务演示（备份） |
| `prototype_orig.html` | 改造前的原始线上版本（备份） |
| `YeeSales-AI-产品与开发说明-v2.md` | 本文档，Markdown 源文件 |
| `YeeSales-AI-产品与开发说明-v2.html` | 本文档的可打印／可转发版本 |

---

*本文档所有客户名称、金额、联系人、牌照信息均为虚构演示数据。*
