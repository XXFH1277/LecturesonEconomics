# 第八十八课：半导体公司财报读表入门：收入分部、毛利率、库存、应收账款、客户集中和出口限制

## 基本信息

- 日期：2026-08-14
- 数据截至：2026-08-14（Asia/Shanghai）。NVIDIA 官方最新已发布业绩为 FY2027 Q1，季度截至 2026-04-26；NVIDIA 官方事件页显示 FY2027 Q2 业绩安排在 2026-08-26 发布，本课不使用未发布的 Q2 数字。Broadcom 官方最新可读取财务结果为 FY2026 Q2，季度截至 2026-05-03，10-Q 提交于 2026-06-09。SOXX 使用 iShares 页面可读取的 2026-07-29/2026-07-30 数据。出口管制使用 BIS 当前可访问页面和 2026-01-13 公告。
- 主题：怎样第一次读半导体公司的财报，不从股价和故事开始，而从收入分部、毛利率、库存、应收账款、客户集中和政策限制开始。
- 学习目标：理解 segment revenue、gross margin、inventory、accounts receivable、purchase obligations、customer concentration、export control risk 和 guidance。
- 相关资产：NVIDIA、Broadcom、SOXX。
- 核心来源：
  - NVIDIA FY2027 Q1 earnings release: https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-Financial-Results-for-First-Quarter-Fiscal-2027/default.aspx
  - NVIDIA FY2027 Q1 Form 10-Q, quarter ended 2026-04-26: https://www.sec.gov/Archives/edgar/data/1045810/000104581026000052/nvda-20260426.htm
  - NVIDIA FY2027 Q2 event page: https://investor.nvidia.com/events-and-presentations/events-and-presentations/event-details/2026/NVIDIA-2nd-Quarter-FY27-Financial-Results/default.aspx
  - Broadcom FY2026 Q2 earnings release: https://www.broadcom.com/company/news/financial-releases/64371
  - Broadcom FY2026 Q2 Form 10-Q, quarter ended 2026-05-03: https://www.sec.gov/Archives/edgar/data/1730168/000173016826000054/avgo-20260503.htm
  - iShares SOXX official page: https://www.ishares.com/us/products/239705/SOXX
  - BIS semiconductor export license policy, 2026-01-13: https://www.bis.gov/press-release/department-commerce-revises-license-review-policy-semiconductors-exported-china

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经把 NVIDIA、Broadcom、Microsoft、Keyence、ABB 和 FANUC 放进同一张价值链地图。今天开始进入单家公司财报：

```text
我打开一家公司财报时，第一眼应该看哪里？
```

零基础学习者容易先看新闻标题、股价涨跌或某个宏大主题。财报读表的起点更朴素：

```text
公司卖什么？
卖给谁？
收入在哪个分部？
毛利率为什么高或低？
库存和应收账款有没有异常变化？
客户是否集中？
管理层给了什么指引？
哪些政策或出口限制会改变收入？
```

这些问题比“公司好不好”更基础，因为它们决定后面能不能做估值、比较和风险判断。

### 参考的教材式概念顺序

1. Revenue：收入，公司已经确认的销售额。
2. Segment revenue：分部收入，把总收入按业务线、市场平台或地区拆开。
3. Gross margin：毛利率，收入扣掉直接成本之后剩下的比例。
4. Inventory：库存，已经生产、正在生产或准备生产的产品和材料。
5. Accounts receivable：应收账款，已经确认收入但还没收回现金的客户欠款。
6. Purchase obligations：采购义务，公司已经承诺向供应商采购的金额。
7. Customer concentration：客户集中，少数客户贡献大量收入。
8. Guidance / outlook：指引，管理层对下一阶段收入、毛利率或成本的预期。
9. Risk factor：风险因素，公司正式披露的可能伤害业务的风险。

### 核心概念

读半导体公司财报，可以先用这条顺序：

```text
收入表
-> 分部收入
-> 毛利率
-> 资产负债表里的应收账款和库存
-> 现金流量表里的经营现金流和资本开支
-> 附注里的客户集中、采购义务和地区收入
-> MD&A 里的原因解释
-> Risk Factors 里的反证风险
-> 下一季 guidance 和复查日期
```

这个顺序的好处是，它把故事拆成可核验的会计项目。比如“AI 需求强”不能单独作为结论，要继续看收入是否增长、毛利率是否稳定、库存是否跟着扩大、应收账款是否过快上升、客户是否高度集中、出口限制是否改变可销售市场。

### 用自己的话解释

如果把半导体公司当成一家“接单、生产、交付、收钱”的企业，最小读表框架是：

```text
收入分部：哪块业务在增长？
毛利率：增长是不是带来足够利润空间？
库存：公司是不是为未来交付提前备货？
应收账款：确认收入后钱是否及时回来？
采购义务：公司为了满足需求已经向供应链承诺多少？
客户集中：增长是不是依赖少数客户？
出口限制：某些产品是不是不能卖给特定地区或客户？
指引：管理层认为下一季会怎样？
```

半导体公司的特殊之处在于，强需求通常会同时拉动库存、采购义务、供应链承诺和客户集中风险。新手不能只看收入增速。

### 常见误区

- 误区一：收入增长就等于风险下降。高速增长可能伴随客户集中、供应约束和库存风险。
- 误区二：毛利率高就永远安全。毛利率会受产品组合、供应成本、库存减值、出口限制和价格竞争影响。
- 误区三：库存增加一定是坏事。扩产期库存可能是为未来交付准备；但如果需求突然放缓，也可能变成减值风险。
- 误区四：应收账款增加一定是收入质量差。它可能来自收入增长和开票时点，也可能提示回款压力，要结合客户、账龄和现金流看。
- 误区五：指引是承诺。Guidance 是管理层基于当前信息的预期，不是保证。
- 误区六：出口管制只是政治新闻。对先进芯片公司来说，它可能直接改变可销售产品、客户、收入地区、库存和毛利率。

## 第二大板块：实时背景与市场传导

### 发生了什么

NVIDIA 2026-05-20 发布 FY2027 Q1 业绩：季度收入 816.15 亿美元，同比增长 85%；GAAP 毛利率 74.9%；Data Center 收入 752.46 亿美元，同比增长 92%。在新的 market platform 口径下，Data Center 又拆成 Hyperscale 378.69 亿美元和 AI Clouds, Industrial & Enterprise 373.77 亿美元；Edge Computing 收入为 63.69 亿美元。公司给出的 FY2027 Q2 outlook 为收入 910 亿美元上下 2%，且没有假设来自中国的 Data Center compute revenue。NVIDIA 官方事件页显示，FY2027 Q2 financial results 安排在 2026-08-26 14:00 PT。

NVIDIA FY2027 Q1 10-Q 显示，截至 2026-04-26，应收账款净额为 407.10 亿美元，库存为 257.97 亿美元；制造、供应和产能承诺为 1190 亿美元，其中 950 亿美元将在 FY2027 剩余期间支付。公司还披露，FY2027 Q1 三个直接客户分别占总收入 21%、17% 和 16%，且都主要归属于 Compute & Networking segment。

Broadcom 2026-06-03 发布 FY2026 Q2 业绩：季度收入 221.87 亿美元，同比增长 48%；其中 semiconductor solutions segment 收入 150.09 亿美元，同比增长 79%；infrastructure software segment 收入 71.78 亿美元，同比增长 9%。公司称 Q2 AI semiconductor revenue 为 108 亿美元，同比增长 143%，主要由 custom AI accelerators 和 AI networking 需求推动，并给出 FY2026 Q3 收入约 294 亿美元的指引。

Broadcom FY2026 Q2 10-Q 显示，截至 2026-05-03，贸易应收账款净额为 108.30 亿美元，库存为 43.28 亿美元；公司解释库存增加主要是为了支持 custom AI accelerators 的更高预期出货。Broadcom 还披露，一个半导体解决方案分销客户占季度和上半年净收入的 42%，前五大终端客户合计约占净收入 45%。

iShares SOXX 官方页面显示，截至可读取的 2026-07-29/2026-07-30 数据，SOXX 持仓数量为 30，行业暴露主要为 Semiconductors 和 Semiconductor Equipment；前十大样本包括 NVIDIA、AMD、Broadcom、Micron、Intel、Applied Materials、TSMC、Texas Instruments、KLA 和 Analog Devices。它说明半导体 ETF 不是一家公司，而是一组不同商业模式和周期位置的公司。

BIS 2026-01-13 公告称，对 NVIDIA H200、AMD MI325X 和类似芯片输往中国的出口许可申请，在满足特定安全要求时采用逐案审查。这说明半导体财报里的收入、库存、采购义务和客户集中，必须和出口许可一起读。

### 为什么重要

NVIDIA 和 Broadcom 都受 AI 基础设施需求推动，但读表重点不同：

```text
NVIDIA：数据中心平台、毛利率、客户集中、库存、巨额供应承诺、出口限制。
Broadcom：AI 半导体收入、custom accelerator、AI networking、分销客户、库存、软件分部。
SOXX：把多家公司放进同一个 ETF 外壳，投资者需要继续穿透到每家公司的财报。
```

如果只说“AI 芯片需求强”，研究还停留在主题层。财报读表要继续追问：

```text
收入增长来自哪个分部？
毛利率有没有被库存或产品组合影响？
库存增加是为交付准备，还是需求放缓的先兆？
应收账款增长是否和收入同步？
少数客户是否能改变一整季收入？
管理层 guidance 是否排除了某些市场？
政策限制是否已经进入财报数字？
```

### 本节采用的数据和来源

- NVIDIA FY2027 Q1 earnings release、FY2027 Q1 Form 10-Q 和 FY2027 Q2 event page。
- Broadcom FY2026 Q2 earnings release 和 FY2026 Q2 Form 10-Q。
- iShares SOXX 官方页面。
- BIS 2026-01-13 半导体出口许可政策公告。

### 这些现实事件如何连接理论

同样是“半导体公司”，NVIDIA 和 Broadcom 的读表路径可以这样分：

| 项目 | NVIDIA 读法 | Broadcom 读法 |
| --- | --- | --- |
| 分部收入 | Data Center、Hyperscale、AI Clouds/Industrial/Enterprise、Edge Computing | Semiconductor Solutions、Infrastructure Software |
| 毛利率 | 看 Blackwell 产品组合、库存准备和出口限制影响 | 看 AI 半导体增长与软件业务组合 |
| 库存 | 是否支持下一代产品交付，是否有减值风险 | 是否支持 custom AI accelerators 出货 |
| 应收账款 | 是否随大客户交付和开票扩大 | 是否受半导体收入、开票时点和保理安排影响 |
| 采购义务 | 供应链承诺非常关键 | 更多看资本开支、库存和客户付款风险 |
| 客户集中 | 三个直接客户合计占比较高 | 一个分销客户和前五大终端客户占比较高 |
| 出口限制 | 中国 Data Center compute revenue 和 H200/H20 许可是重点 | 贸易限制、关税、供应链和客户资本开支是重点 |

### 至少一个实时新闻、往期事件或真实市场机制案例

本课案例是“高增长同时带来供应链承诺和客户集中”。

NVIDIA FY2027 Q1 的收入和 Data Center 收入继续大幅增长，但同一份 10-Q 还显示库存、应收账款、制造供应承诺和客户集中都很大。Broadcom Q2 的 AI semiconductor revenue 大幅增长，但 10-Q 也显示库存上升、分销客户占比高、前五大终端客户占比高。

这说明财报读表不能停在第一层好消息：

```text
收入增长
-> 需要看毛利率和现金流
-> 需要看库存和应收账款
-> 需要看客户集中和订单节奏
-> 需要看供应链承诺
-> 需要看出口管制和客户资本开支
-> 最后才进入估值和市场预期
```

## 政治、制度和规则视角

### 涉及的政策、监管、制度或国际关系

- SEC 披露制度：10-Q、8-K、业绩新闻稿、MD&A 和 Risk Factors 是公司正式披露入口。
- 出口管制：先进计算芯片、AI 加速器和相关技术可能受 BIS、EAR、许可审查、最终用户和地区限制影响。
- 供应链制度：半导体公司常通过代工、封装、测试、设备、材料和长期供应承诺组织生产。
- 国际关系：美国、中国、中国台湾、中东、欧洲和其他地区的政策变化会影响客户、供应链、关税和许可。
- ETF 披露：SOXX 让投资者获得半导体行业暴露，但 ETF 外壳不能替代公司财报阅读。

### 已确认事实

- NVIDIA FY2027 Q1 收入 816.15 亿美元，Data Center 收入 752.46 亿美元，GAAP 毛利率 74.9%。
- NVIDIA FY2027 Q2 earnings event 安排在 2026-08-26，本课没有使用未发布的 Q2 实际数据。
- NVIDIA FY2027 Q1 10-Q 披露应收账款、库存、制造供应承诺和客户集中。
- Broadcom FY2026 Q2 收入 221.87 亿美元，semiconductor solutions 收入 150.09 亿美元，AI semiconductor revenue 为 108 亿美元。
- Broadcom FY2026 Q2 10-Q 披露库存增加主要为了支持 custom AI accelerators 的更高预期出货，并披露客户集中。
- BIS 2026-01-13 公告确认对部分先进芯片输往中国采用逐案许可审查。

### 市场可能如何传导

如果 AI 数据中心建设继续强劲，NVIDIA 和 Broadcom 的上游需求可能继续体现为收入、库存、采购承诺和供应链投资。但如果客户资本开支放缓、产品交付延迟、出口许可收紧或大客户改变采购节奏，收入和毛利率可能快速波动。SOXX 这类 ETF 会把这些公司风险组合在一起，投资者看到的是基金净值变化，但底层原因仍来自公司财报、行业周期和政策限制。

### 仍需核验或观察

- 2026-08-26 NVIDIA FY2027 Q2 实际收入、Data Center 细分、毛利率、库存、客户集中和中国收入说明。
- Broadcom FY2026 Q3 是否兑现约 294 亿美元收入指引，以及 AI semiconductor revenue 是否继续增长。
- BIS、Federal Register 和公司风险因素是否改变出口许可、产品规格或客户范围。
- SOXX 后续持仓权重是否继续集中在 NVIDIA、AMD、Broadcom、Micron 等公司。
- 应收账款和库存增长是否与收入增长匹配，还是出现收款、出货或需求风险。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Segment Revenue | 分部收入 | 把总收入按业务或市场拆开 | 找到真正增长的业务 |
| Gross Margin | 毛利率 | 收入扣直接成本后剩下的比例 | 判断产品组合和定价权 |
| Inventory | 库存 | 原材料、在制品和成品 | 判断交付准备和减值风险 |
| Accounts Receivable | 应收账款 | 已确认收入但尚未收到的钱 | 判断回款节奏和收入质量 |
| Purchase Obligations | 采购义务 | 已经承诺未来采购或支付的金额 | 高需求期会锁定供应，也会增加风险 |
| Customer Concentration | 客户集中度 | 少数客户贡献大量收入 | 大客户变化会放大业绩波动 |
| Guidance / Outlook | 管理层指引 | 管理层对下一阶段的预期 | 市场会拿实际结果和指引比较 |
| Export Control Risk | 出口管制风险 | 产品出口受到许可和国家安全规则限制 | 可能改变收入地区、库存和产品组合 |
| Factoring | 应收账款保理 | 把应收账款卖给金融机构提前回款 | 会影响现金流和应收账款读法 |
| SOXX | iShares Semiconductor ETF | 半导体行业 ETF | 是行业暴露入口，不是单家公司分析 |

## 回顾提示

- 学到本课前建议回顾：可回顾第 10 课三张报表、第 18 课 RPO 和 backlog、第 20 课应收账款、第 22 课毛利率、第 86 课行业价值链、第 87 课公司样本地图。
- 本课哪些内容会在后续课程继续使用：分部收入、毛利率、库存、应收账款、客户集中、采购义务、指引和风险因素。
- 如果看不懂本课，可以先回到：第 7 课股票入门、第 11 课财报披露链。

## 案例拆解

### 案例对象

NVIDIA 和 Broadcom 的半导体公司财报读表入门。

### 已确认事实

- NVIDIA FY2027 Q1 收入 816.15 亿美元，Data Center 收入 752.46 亿美元，GAAP 毛利率 74.9%。
- NVIDIA FY2027 Q1 10-Q 显示，应收账款净额 407.10 亿美元，库存 257.97 亿美元，制造、供应和产能承诺 1190 亿美元。
- NVIDIA FY2027 Q1 三个直接客户分别占总收入 21%、17% 和 16%。
- Broadcom FY2026 Q2 收入 221.87 亿美元，semiconductor solutions 收入 150.09 亿美元，AI semiconductor revenue 108 亿美元。
- Broadcom FY2026 Q2 10-Q 显示，贸易应收账款净额 108.30 亿美元，库存 43.28 亿美元；一个半导体解决方案分销客户占季度和上半年净收入 42%。

### 来源日期和链接

- NVIDIA FY2027 Q1 earnings release, 2026-05-20: https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-Financial-Results-for-First-Quarter-Fiscal-2027/default.aspx
- NVIDIA FY2027 Q1 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1045810/000104581026000052/nvda-20260426.htm
- Broadcom FY2026 Q2 earnings release, 2026-06-03: https://www.broadcom.com/company/news/financial-releases/64371
- Broadcom FY2026 Q2 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1730168/000173016826000054/avgo-20260503.htm
- BIS semiconductor export license policy, 2026-01-13: https://www.bis.gov/press-release/department-commerce-revises-license-review-policy-semiconductors-exported-china

### 分析推理

NVIDIA 的核心读表问题是：Data Center 高增长能否在供应、客户、毛利率和出口限制下继续转化为收入和现金流。Broadcom 的核心读表问题是：AI semiconductor revenue 的增长是否能在 custom accelerator、AI networking、客户集中、库存扩张和软件分部组合中持续。

这不是买卖判断，而是研究入口。真正的结论要等下一期实际结果、10-Q、电话会和风险因素继续核验。

### 后续验证指标

- NVIDIA FY2027 Q2 actual revenue、Data Center、Hyperscale、ACIE、gross margin、inventory、accounts receivable、customer concentration、China data center compute revenue。
- Broadcom FY2026 Q3 revenue、AI semiconductor revenue、semiconductor solutions margin、inventory、accounts receivable、customer concentration。
- SOXX 最新完整持仓 CSV 和行业暴露。
- BIS/Federal Register 的先进计算和半导体出口管制更新。

## 个人情境连接

- 对关注清单的启发：给半导体公司新增 `分部收入`、`毛利率`、`库存`、`应收账款`、`客户集中`、`出口限制` 和 `下一次财报日期` 字段。
- 对持仓或基金选择的启发：持有半导体 ETF 时，也要知道底层公司风险不是平均分散的。
- 对工作、收入、消费或风险管理的启发：AI 基础设施投资会影响云、芯片、制造、数据中心、电力和工业自动化岗位，但个人决策不能只跟着主题热度走。

## 结论边界

- 可以确定：半导体公司财报读表要从收入分部、毛利率、库存、应收账款、客户集中、采购义务、指引和风险因素开始。
- 不能确定：NVIDIA 或 Broadcom 后续季度一定继续增长，也不能用本课数字直接推导股价。
- 需要继续观察：下一期财报、出口许可、客户资本开支、供应链承诺、库存变化和 ETF 持仓变化。
- 不构成投资建议的原因：本课只训练财报阅读方法，不提供任何买入、卖出、持有、税务或法律建议。

## 练习题

1. 为什么读半导体公司不能只看总收入？
2. 用自己的话解释库存增加的两种可能含义：交付准备和需求风险。
3. NVIDIA 的客户集中和 Broadcom 的客户集中分别应该怎样复查？
4. 如果下一季收入增长但应收账款增长更快，你会增加哪三个问题？
5. 为什么出口管制可能影响毛利率和库存，而不只是影响地区收入？

## 学习交接

- 本课已经完成：把第 87 课的公司样本地图推进到 NVIDIA 和 Broadcom 的财报读表，覆盖收入分部、毛利率、库存、应收账款、采购义务、客户集中和出口限制。
- 本课最重要的一句话：财报读表不是验证故事，而是把故事拆成收入、成本、资产、客户、政策和下一次指引。
- 需要复习的关键词：Segment Revenue、Gross Margin、Inventory、Accounts Receivable、Purchase Obligations、Customer Concentration、Guidance、Export Control Risk。
- 还不稳定、下次要回看的地方：NVIDIA FY2027 Q2 尚未发布，Broadcom FY2026 Q3 尚未发布；出口许可和客户资本开支都可能改变结论。
- 适合下次打开仓库先读的文件：`lessons/2026-08-14-lesson-89-semiconductor-risk-factors-review-triggers.md`

## 下节课安排

- 建议主题：第八十九课：半导体公司风险因素与复查触发器入门：出口管制、客户集中、供应约束、库存风险和指引更新。
- 学习目标：学会把财报里的风险因素转成可执行的反证指标和复查节奏。
- 建议案例：NVIDIA FY2027 Q1 10-Q、Broadcom FY2026 Q2 10-Q、BIS 出口管制公告、SOXX 持仓。
- 必须解释的关键词：Risk Factor、Forward-looking Statement、Review Trigger、Disconfirming Evidence、Supply Constraint、Customer Concentration、Inventory Risk、Regulatory Risk。
- 下节课开始前需要联网核验的数据：NVIDIA FY2027 Q2 是否仍未发布或是否出现新公告；Broadcom 是否发布 FY2026 Q3 事件安排；BIS 是否有新的先进计算或半导体出口管制更新；SOXX 最新持仓日期。

## 来源

- NVIDIA FY2027 Q1 earnings release: https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Announces-Financial-Results-for-First-Quarter-Fiscal-2027/default.aspx
- NVIDIA FY2027 Q1 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1045810/000104581026000052/nvda-20260426.htm
- NVIDIA FY2027 Q2 event page: https://investor.nvidia.com/events-and-presentations/events-and-presentations/event-details/2026/NVIDIA-2nd-Quarter-FY27-Financial-Results/default.aspx
- Broadcom FY2026 Q2 earnings release: https://www.broadcom.com/company/news/financial-releases/64371
- Broadcom FY2026 Q2 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1730168/000173016826000054/avgo-20260503.htm
- iShares SOXX official page: https://www.ishares.com/us/products/239705/SOXX
- BIS semiconductor export license policy: https://www.bis.gov/press-release/department-commerce-revises-license-review-policy-semiconductors-exported-china
