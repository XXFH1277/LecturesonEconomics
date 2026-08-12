# 第八十五课：ETF 决策日志、反证指标与复查节奏入门：把复盘写成可执行的研究流程

## 基本信息

- 日期：2026-08-12
- 数据截至：2026-08-12（Asia/Shanghai）。ETF 官方字段采用发行方页面截至 2026-08-11 或最近可读取日期；股东报告、N-PORT、绩效披露和公平呈现规则采用 SEC、Investor.gov 与 CFA Institute 当前可访问页面。
- 主题：复盘之后，怎样把下一步写成可核验、可交接、可反证的决策日志。
- 学习目标：理解 thesis、base case、bull case、bear case、disconfirming evidence、review trigger、source log、no-action decision、process vs outcome 和 handoff note。
- 相关资产：AIQ、BOTZ、SOXX、XLK、SPY、SGOV。
- 核心来源：
  - CFA Institute, Standard III(D) Performance Presentation, updated 2024-04: https://www.cfainstitute.org/standards/professionals/code-ethics-standards/standards-of-practice-iii-d
  - CFA Institute, Portfolio Performance Evaluation, 2026 Curriculum: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
  - Investor.gov, Updated Investor Bulletin: How to Read a Mutual Fund or ETF Shareholder Report, 2024-01-19: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
  - SEC, Form N-PORT Data Sets: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
  - Global X, Artificial Intelligence & Technology ETF (AIQ): https://www.globalxetfs.com/funds/AIQ
  - Global X, Robotics & Artificial Intelligence ETF (BOTZ): https://www.globalxetfs.com/funds/BOTZ
  - iShares, iShares Semiconductor ETF (SOXX): https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
  - State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - State Street, Technology Select Sector SPDR Fund (XLK): https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
  - iShares, iShares 0-3 Month Treasury Bond ETF (SGOV): https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经把收益拆成来源。今天继续问：

```text
我已经知道这次组合回报主要来自哪里，
那下一步到底是买、卖、等、替换，还是继续观察？
```

零基础阶段最容易犯的错，是把复盘写成情绪：

```text
涨了：我看对了。
跌了：市场错了。
没涨：再等等。
```

更好的做法，是把复盘写成决策日志：

```text
当时我知道什么事实？
我的假设是什么？
什么证据会支持它？
什么证据会推翻它？
我准备多久复查一次？
不行动是不是也是一个明确决定？
下一次打开记录的人要先看什么来源？
```

### 参考的教材式概念顺序

1. Thesis：投资假设，一句话说明为什么这个对象值得观察或持有。
2. Base case：基准情景，最普通、最中性的预期路径。
3. Bull case：乐观情景，哪些条件成立时结果可能更好。
4. Bear case：悲观情景，哪些条件出现时结果可能变差。
5. Disconfirming evidence：反证证据，什么事实会推翻原假设。
6. Review trigger：复查触发器，价格、持仓、政策、费用或报告变化到什么程度要复查。
7. Source log：来源日志，记录每个关键事实的来源、日期和链接。
8. No-action decision：不行动决定，明确记录为什么现在不买、不卖、不换。
9. Process vs outcome：过程和结果分离，结果好坏不自动证明过程好坏。
10. Handoff note：学习交接，方便下次或另一个电脑继续。

### 核心概念

一个适合 ETF 研究的决策日志可以写成：

```text
日期：
数据截至：
观察对象：
一句话 thesis：
已确认事实：
我当前的推理：
反证指标：
复查触发器：
下一次核验入口：
本次决定：买入 / 卖出 / 替换 / 再平衡 / 不行动 / 继续观察
为什么这不是投资建议：
```

其中最重要的是“反证指标”。如果没有反证指标，所谓 thesis 很容易变成口号。例如：

```text
弱 thesis：AI 很重要，所以 AI ETF 会好。
强一点的 thesis：如果 AI 基础设施资本开支继续扩张，且 AIQ 的持仓仍主要暴露在平台、软件、芯片和数据链条，那么 AIQ 可能继续更像信息技术主题工具；如果持仓、指数规则、估值、费用、流动性或主题相关性发生明显变化，就要重新评估。
```

强 thesis 不保证结论正确，但它能让你知道什么时候该认错或重写。

### 用自己的话解释

可以把决策日志想成航海日志。航海日志不负责保证天气好，它负责记录：

```text
当时在哪里？
天气怎样？
为什么选择这条航线？
如果风向改变，什么时候改道？
下一个接班的人应该先看哪张地图？
```

ETF 投资研究也是这样。你不能保证 AI、半导体或机器人主题未来表现，但你可以保证自己的学习过程可复查：

```text
不是“AI 很火”，而是“这只 ETF 现在到底持有什么”。
不是“表现强”，而是“强在哪里、和什么基准比、能否解释”。
不是“下次再看”，而是“到什么日期、看什么文件、用什么指标复查”。
```

### 常见误区

- 误区一：只有买卖才算决定。不行动也是决定，也要记录理由。
- 误区二：把主题叙事当成 thesis。主题只是线索，持仓、规则和价格才是可核验对象。
- 误区三：只记录支持自己的事实。反证指标必须提前写，不要等亏损后再改口。
- 误区四：复查只看价格。复查还要看持仓、费用、指数方法论、分配、税务、流动性和报告。
- 误区五：把一次好结果当成能力。CFA Institute 的绩效评估材料提醒，绩效分析有方法和数据限制，不能超出数据能力推断。
- 误区六：表现披露只挑好看的数字。CFA Institute Standard III(D) 要求绩效信息公平、准确、完整，教学复盘也要用同样的纪律要求自己。

## 第二大板块：实时背景与市场传导

### 发生了什么

CFA Institute Standard III(D) Performance Presentation 要求在沟通投资表现时，应合理努力确保信息公平、准确、完整，并避免误导性呈现。这对个人学习同样有用：不能只把表现好的区间、最有利的基准或单一成功案例放进复盘。

CFA Institute 的绩效评估材料提醒，performance attribution 应理解数据输入、方法和局限；returns-based、holdings-based 和 transactions-based attribution 能回答的问题不同。对个人学习者来说，如果没有完整交易记录，就不能假装自己做了 transactions-based attribution。

Investor.gov 的股东报告公告说明，基金和 ETF 股东报告可以帮助投资者持续评估基金投资，并包含费用、绩效、统计信息、持仓图表和重大变化。SEC Form N-PORT 页面说明，N-PORT 是月度组合持仓报告的正式监管入口，但公开数据集不能替代完整申报文件。

Global X AIQ 官方页面显示，截至 2026-08-11，AIQ NAV 为 63.17 美元，市场价格为 63.20 美元，总费用率为 0.68%，净资产为 101.8 亿美元，持仓数量 88，30-day median bid/ask spread 为 0.02%，30-day SEC yield 为 -0.18%。截至 2026-07-31，AIQ 行业暴露中 Information Technology 为 71.5%、Communication Services 为 12.4%、Consumer Discretionary 为 9.7%。截至 2026-08-11，AIQ 前十大持仓包括 Palantir、Microsoft、Oracle、Amazon、SpaceX、Netflix、Alphabet、Cisco、Broadcom 和 Tencent。

Global X BOTZ 官方页面显示，截至 2026-08-11，BOTZ NAV 为 37.42 美元，总费用率为 0.68%，净资产为 35.6 亿美元，持仓数量 61，30-day median bid/ask spread 为 0.03%，30-day SEC yield 为 -0.04%。截至 2026-07-31，BOTZ 行业暴露中 Industrials 为 45.2%、Information Technology 为 37.1%、Health Care 为 8.1%。截至 2026-08-11，BOTZ 前十大持仓包括 Keyence 10.56%、ABB 9.21%、NVIDIA 9.13%、FANUC 7.93%、Intuitive Surgical 6.22%。

iShares SOXX 官方页面显示，截至 2026-08-11，SOXX NAV total return YTD 为 77.70%，费用率为 0.33%，净资产为 426.2595 亿美元，30-day median bid/ask spread 为 0.04%；截至 2026-08-10，行业暴露中 Semiconductors 为 78.92%、Semiconductor Equipment 为 20.94%。State Street XLK 页面显示，截至 2026-08-11，XLK 半导体与半导体设备行业权重为 44.63%，前十大持仓中 NVIDIA、Apple 和 Microsoft 分别为 14.19%、12.06% 和 10.08%。

iShares SGOV 官方页面显示，截至 2026-08-11，SGOV NAV total return YTD 为 2.21%；截至 2026-08-10，30-day SEC yield 为 3.59%，effective duration 为 0.10 年，weighted average maturity 为 0.11 年。它适合在课堂中作为现金仓位和短端利率传导样本，但不是银行存款，也不是收益保证。

### 为什么重要

AIQ 和 BOTZ 名字里都有 AI，但它们不是同一个风险：

```text
AIQ 更像信息技术、平台、软件、芯片和数据主题的组合。
BOTZ 更像机器人、自动化、工业设备、部分医疗设备和 AI 硬件应用的组合。
SOXX 更集中在半导体和半导体设备。
XLK 是科技板块，但也有很高半导体权重。
SPY 是宽基，但大型科技权重已经很高。
SGOV 是短端国债现金工具，收益主要随短端利率环境变化。
```

如果学习者只写“我看好 AI”，就会把不同风险混成一个故事。决策日志要把故事拆成可核验字段：

```text
持仓是否仍符合主题？
主题是否和宽基或行业 ETF 重叠？
费用和价差是否合理？
净资产和流动性是否稳定？
指数方法论是否改变？
回报差异来自持仓，还是来自估值、汇率、行业周期、现金利率和税务？
```

### 本节采用的数据和来源

- 表现披露纪律：CFA Institute Standard III(D)。
- 绩效归因方法边界：CFA Institute Portfolio Performance Evaluation。
- 股东报告和持续评估：Investor.gov shareholder report bulletin。
- 监管持仓入口：SEC Form N-PORT data sets。
- ETF 实时字段：Global X AIQ/BOTZ、iShares SOXX/SGOV、State Street SPY/XLK 官方页面。

### 这些现实事件如何连接理论

ETF 决策日志的传导链可以写成：

```text
主题叙事
-> 官方投资目标和指数方法论
-> 当前持仓和行业暴露
-> 基准与回报口径
-> 费用、价差、溢价折价、净资产
-> 与组合里其他 ETF 的重叠
-> thesis、base case、bull case、bear case
-> 反证指标和复查触发器
-> 行动或不行动
-> 下次复查
```

一个可交接的日志不是越长越好，而是要让下次打开的人立刻知道：

```text
我当时依据哪些事实？
哪些事实需要刷新？
哪些情况会推翻旧判断？
我有没有混用不同日期或不同回报口径？
```

### 至少一个实时新闻、往期事件或真实市场机制案例

本课案例是“AIQ 与 BOTZ 的同名主题差异”。截至本次核验，AIQ 的行业暴露明显偏 Information Technology，前十大持仓包含多家平台、软件、云、半导体和互联网公司；BOTZ 的行业暴露中 Industrials 更高，前十大持仓包含 Keyence、ABB、FANUC、SMC、Daifuku、Cognex 等自动化和工业链公司，同时也有 NVIDIA。

同样是 AI 主题，决策日志不能只写：

```text
AI 机会很大，所以继续观察。
```

更好的写法是：

```text
AIQ 和 BOTZ 都使用 AI 主题线索，但当前持仓和行业暴露不同。
AIQ 更偏软件、平台、数据和大型科技；
BOTZ 更偏工业自动化、机器人和全球制造链；
因此它们在利率、估值、资本开支、产业政策、汇率和制造业周期上的敏感度可能不同。
```

这是教学推理，不是买卖结论。

## 政治、制度和规则视角

### 涉及的政策、监管、制度或国际关系

- SEC 和 Investor.gov 披露框架：股东报告、N-PORT、EDGAR 和基金官网让复查有正式来源。
- CFA Institute 表现披露标准：公平、准确、完整的表现沟通，反对挑选有利数字误导自己或别人。
- 指数方法论和授权：AIQ、BOTZ、SOXX、XLK、SPY 的基准和目标不同，决策日志必须写清对应指数。
- AI、半导体和机器人产业政策：出口管制、芯片供应链、制造业补贴、资本开支和国际竞争都可能改变主题 ETF 的风险。
- 税务和账户制度：同样的 ETF，在应税账户、退休账户和不同国家税制下，税后结果可能不同。

### 已确认事实

- CFA Institute Standard III(D) 要求投资表现信息公平、准确、完整。
- Investor.gov 说明基金和 ETF 股东报告包含费用、绩效、统计信息、持仓图表和重大变化，可帮助投资者持续评估基金。
- SEC Form N-PORT 是正式监管持仓报告入口，但 SEC 提醒公开数据集不能替代完整申报文件。
- AIQ 和 BOTZ 官方页面显示，两者都是 AI 相关 ETF，但持仓、行业暴露、净资产、价差和收益字段不同。
- SOXX、XLK 和 SPY 的官方页面显示，半导体和大型科技可以通过多层 ETF 同时进入一个组合。
- SGOV 官方页面显示，短端国债 ETF 有 duration、weighted average maturity、SEC yield、费用和价差字段。

### 市场可能如何传导

如果 AI 平台公司继续受益于资本开支和盈利预期，AIQ 这类更偏信息技术的 ETF 可能表现不同于 BOTZ；如果全球制造业、自动化资本开支或日元/瑞郎等汇率因素变化，BOTZ 的表现可能和 AIQ 拉开。若半导体周期回落，SOXX 和 XLK 中的半导体权重可能同时影响组合。若短端利率变化，SGOV 的 30-day SEC yield 会随之变化。

### 仍需核验或观察

- AIQ 和 BOTZ 的指数方法论是否改变。
- AIQ 和 BOTZ 的前十大持仓、行业和国家暴露是否继续分化。
- SOXX、XLK、SPY 的半导体与大型科技穿透权重是否继续上升。
- 费用率、净资产、成交量、买卖价差和溢价折价是否恶化。
- 股东报告是否披露重大基金变化。
- N-PORT 或完整持仓文件是否显示衍生品、现金或其他不易从页面摘要看出的暴露。
- SGOV 的 SEC yield、duration 和短端利率环境是否变化。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Thesis | 投资假设 | 为什么观察或持有某对象的一句话逻辑 | 防止只靠情绪 |
| Base Case | 基准情景 | 最中性的预期路径 | 让预期不极端化 |
| Bull Case | 乐观情景 | 哪些条件会让结果更好 | 帮助识别上行因素 |
| Bear Case | 悲观情景 | 哪些条件会让结果变差 | 帮助提前识别风险 |
| Disconfirming Evidence | 反证证据 | 什么事实会推翻原假设 | 防止死守旧观点 |
| Review Trigger | 复查触发器 | 到什么条件必须重新看 | 让复查可执行 |
| Source Log | 来源日志 | 记录来源、日期和链接 | 防止事实漂移 |
| No-Action Decision | 不行动决定 | 明确选择暂不交易 | 防止把拖延当纪律 |
| Process vs Outcome | 过程与结果分离 | 结果好坏不等于过程好坏 | 训练长期复盘能力 |
| Handoff Note | 交接记录 | 告诉下次先看什么 | 让学习不断档 |
| Fair Presentation | 公平呈现 | 不挑选有利数字误导 | 让复盘可信 |
| Review Cadence | 复查节奏 | 固定频率或事件触发复查 | 防止天天看也防止忘记 |

## 回顾提示

- 学到本课前建议回顾：可回顾第 46 课投资备忘录、第 50 课基金表现归因、第 80 课主题 ETF 集中度、第 82 课组合重叠、第 84 课 ETF 绩效归因。
- 本课哪些内容会在后续课程继续使用：thesis、反证指标、复查触发器、source log、no-action decision 和 handoff note。
- 如果看不懂本课，可以先回到：第 1 课市场地图、第 4 课基金和 ETF 入门、第 48 课 ETF 持仓穿透。

## 案例拆解

### 案例对象

AIQ、BOTZ、SOXX、XLK、SPY 和 SGOV 的 ETF 决策日志样例。

### 已确认事实

- AIQ 截至 2026-08-11 的净资产为 101.8 亿美元，费用率 0.68%，持仓数量 88；截至 2026-07-31，Information Technology 权重为 71.5%。
- BOTZ 截至 2026-08-11 的净资产为 35.6 亿美元，费用率 0.68%，持仓数量 61；截至 2026-07-31，Industrials 权重为 45.2%，Information Technology 权重为 37.1%。
- SOXX 截至 2026-08-11 的 NAV total return YTD 为 77.70%；截至 2026-08-10，行业暴露几乎全部在半导体和半导体设备。
- XLK 截至 2026-08-11 的半导体与半导体设备行业权重为 44.63%。
- SPY 截至 2026-08-11 的 Information Technology 权重为 37.51%。
- SGOV 截至 2026-08-10 的 30-day SEC yield 为 3.59%，effective duration 为 0.10 年。

### 来源日期和链接

- CFA Institute Standard III(D), updated 2024-04: https://www.cfainstitute.org/standards/professionals/code-ethics-standards/standards-of-practice-iii-d
- CFA Institute Portfolio Performance Evaluation, 2026: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
- Investor.gov shareholder report bulletin, 2024-01-19: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
- SEC Form N-PORT Data Sets: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
- Global X AIQ official page: https://www.globalxetfs.com/funds/AIQ
- Global X BOTZ official page: https://www.globalxetfs.com/funds/BOTZ
- iShares SOXX official page: https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- State Street XLK official page: https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- State Street SPY official page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- iShares SGOV official page: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf

### 分析推理

一个合格日志可以这样写：

```text
日期：2026-08-12
对象：AIQ 与 BOTZ
Thesis：二者都与 AI 主题相关，但 AIQ 更偏信息技术和平台公司，BOTZ 更偏工业自动化和机器人产业链，不能互相替代。
Base case：继续按各自指数规则持有不同产业链暴露，回报差异由持仓、行业周期、估值和汇率共同决定。
Bull case：AI 资本开支和自动化需求同时扩张，且主要持仓盈利兑现，主题 ETF 的基本面叙事得到支持。
Bear case：估值压缩、资本开支放缓、出口管制、制造业周期下行或主要持仓盈利不达预期，导致主题回撤。
反证指标：持仓和行业暴露明显漂移；费用或价差恶化；AUM 快速下降；股东报告出现重大策略变化；主题 ETF 与已有 SPY/XLK/SOXX 暴露过度重叠。
本次决定：继续观察，不因主题名称相似而直接替代，也不因单期表现强弱得出买卖结论。
```

这个日志的目标不是预测，而是把下一次复查要看的事实提前写清楚。

### 后续验证指标

- AIQ/BOTZ 的指数方法论、持仓、行业、国家和前十大权重。
- SOXX、XLK、SPY 的半导体和大型科技穿透权重。
- SGOV 的 SEC yield、duration、weighted average maturity 和费用。
- 发行方官网、股东报告、N-PORT、完整持仓 CSV 和 EDGAR 文件。
- 费用率、AUM、成交量、30-day median bid/ask spread、premium/discount。
- 每次行动或不行动的理由是否和原 thesis 一致。

## 个人情境连接

- 对关注清单的启发：给每个 ETF 增加 `thesis`、`反证指标`、`复查日期` 和 `来源链接` 字段。
- 对持仓或基金选择的启发：不要因为两个基金名字相似就替换，也不要因为短期回报不同就直接判断优劣。
- 对工作、收入、消费或风险管理的启发：重大决定都可以先写反证指标，避免事后只挑支持自己的理由。

## 结论边界

- 可以确定：决策日志能把事实、推理、行动和反证指标分开，降低事后归因和情绪化复盘。
- 不能确定：日志不能预测市场，也不能告诉某个具体投资者是否应该买卖某只 ETF。
- 需要继续观察：ETF 持仓、指数方法论、费用、价差、AUM、税务、分配、政策和宏观环境。
- 不构成投资建议的原因：本课只训练研究记录和复查流程，不提供投资、税务或法律建议。

## 练习题

1. 写一句合格的 ETF thesis，并写出一条能推翻它的反证指标。
2. 为什么“不行动”也要写进决策日志？
3. 比较 AIQ 和 BOTZ：从持仓和行业暴露看，它们为什么不能简单互相替代？
4. 给 SOXX 写三个复查触发器：一个关于持仓，一个关于流动性，一个关于风险预算。
5. 如果某只 ETF 过去一年表现很好，怎样用公平、准确、完整的方式写复盘？

## 学习交接

- 本课已经完成：把 ETF 绩效复盘推进到决策日志、反证指标、复查触发器、来源日志、不行动决定、过程与结果分离和学习交接。
- 本课最重要的一句话：好复盘不是证明自己对，而是提前写清楚什么事实会让自己重写判断。
- 需要复习的关键词：Thesis、Base Case、Bull Case、Bear Case、Disconfirming Evidence、Review Trigger、Source Log、No-Action Decision、Process vs Outcome、Handoff Note。
- 还不稳定、下次要回看的地方：主题 ETF 的叙事很容易压过持仓事实，后续必须继续用官方持仓和股东报告核验。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`、`lessons/INDEX.md` 和 `templates/investment-memo.md`

## 下节课安排

- 建议主题：第八十六课：从 ETF 持仓穿透到行业研究入门：产业链、周期位置、利润池、政策风险和公司样本。
- 学习目标：理解 industry value chain、profit pool、cycle position、supply-demand balance、policy risk、capex cycle、customer concentration 和 company sample。
- 建议案例：用半导体、AI 基础设施和机器人自动化产业链作为入口，从 SOXX、XLK、AIQ、BOTZ 的持仓穿透到公司和行业研究。
- 必须解释的关键词：Industry Value Chain、Profit Pool、Cycle Position、Supply-Demand Balance、Capex Cycle、Policy Risk、Customer Concentration、Company Sample。
- 下节课开始前需要联网核验的数据：SOXX、XLK、AIQ、BOTZ 最新持仓；NVIDIA、Broadcom、Microsoft、Keyence、ABB、FANUC 等公司最新 IR/年报或季报入口；半导体设备、数据中心资本开支和出口管制相关官方或公司来源。

## 来源

- CFA Institute, Standard III(D) Performance Presentation: https://www.cfainstitute.org/standards/professionals/code-ethics-standards/standards-of-practice-iii-d
- CFA Institute, Portfolio Performance Evaluation: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
- Investor.gov, How to Read a Mutual Fund or ETF Shareholder Report: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
- SEC, Form N-PORT Data Sets: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
- Global X, AIQ: https://www.globalxetfs.com/funds/AIQ
- Global X, BOTZ: https://www.globalxetfs.com/funds/BOTZ
- iShares, SOXX: https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- State Street, SPY: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- State Street, XLK: https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- iShares, SGOV: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
