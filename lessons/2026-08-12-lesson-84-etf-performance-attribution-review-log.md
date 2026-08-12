# 第八十四课：ETF 绩效复盘和持仓归因入门：收益来源、再平衡贡献、费用拖累、税后结果和研究日志

## 基本信息

- 日期：2026-08-12
- 数据截至：2026-08-12（Asia/Shanghai）。美国 ETF 价格、NAV、持仓、费用、买卖价差和溢价折价采用发行方页面截至 2026-08-11 或最近可读取日期；月末标准化绩效主要采用 2026-06-30 和 2026-07-31 可读取表格；监管和方法框架采用 SEC、Investor.gov 与 CFA Institute 当前可访问页面。
- 主题：怎样把“基金涨跌”拆成收益来源、基准差异、费用、税务、现金仓位和复盘记录。
- 学习目标：理解 performance measurement、performance attribution、performance appraisal、contribution to return、allocation effect、selection effect、tracking difference、fee drag、tax drag、cash drag 和 decision journal。
- 相关资产：SPY、XLK、SOXX、AIQ、BOTZ、SGOV。
- 核心来源：
  - CFA Institute, Portfolio Performance Evaluation, 2026 Curriculum: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
  - Investor.gov, Updated Investor Bulletin: How to Read a Mutual Fund or ETF Shareholder Report, 2024-01-19: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
  - SEC, Form N-PORT Data Sets, last reviewed or updated 2026-06-30: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
  - State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - State Street, Technology Select Sector SPDR Fund (XLK): https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
  - iShares, iShares Semiconductor ETF (SOXX): https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
  - iShares, iShares 0-3 Month Treasury Bond ETF (SGOV): https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
  - Global X, Artificial Intelligence & Technology ETF (AIQ): https://www.globalxetfs.com/funds/AIQ
  - Global X, Robotics & Artificial Intelligence ETF (BOTZ): https://www.globalxetfs.com/funds/BOTZ

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲的是税务敏感再平衡。今天的问题是：

```text
我的 ETF 组合今年涨了，或者某只基金涨得特别多，
我怎么知道这是我真的做对了，还是只是某个行业、某只股票或现金利率在起作用？
```

只看账户总收益，很容易把结果误认为能力。绩效复盘要先问三件事：

```text
1. 赚了多少或亏了多少？这是 performance measurement。
2. 为什么赚或亏？这是 performance attribution。
3. 这个结果能不能说明决策质量？这是 performance appraisal。
```

CFA Institute 的绩效评估框架把 performance measurement、performance attribution 和 performance appraisal 分开。对零基础学习者来说，这个区分很重要：收益数字告诉你“发生了什么”，归因告诉你“来源在哪里”，评价才讨论“决策过程是否值得保留”。

### 参考的教材式概念顺序

1. Total return：总回报，把价格变化和分配再投资放在一起。
2. NAV return：基金净值回报，按基金净资产价值计算。
3. Market price return：市场价格回报，按交易价格计算，可能受溢价折价影响。
4. Benchmark return：基准回报，用来比较基金是否完成跟踪或主动目标。
5. Excess return / active return：超额回报，基金回报减去基准回报。
6. Performance attribution：绩效归因，把回报拆成来源。
7. Contribution to return：收益贡献，某个仓位权重乘以它的回报。
8. Allocation effect：配置效应，资产或行业权重偏离基准带来的影响。
9. Selection effect：选择效应，同一类别里选择具体证券或基金带来的影响。
10. Tracking difference：跟踪差异，基金长期回报和基准回报之间的差。
11. Fee drag：费用拖累，费用率、交易成本、买卖价差和佣金对回报的减少。
12. Tax drag：税务拖累，分配、卖出和账户类型对税后结果的影响。
13. Cash drag：现金拖累，现金或短端工具相对权益资产的机会成本。
14. Decision journal：决策日志，记录当时的事实、假设、行动和反证指标。

### 核心概念

最小绩效复盘表可以这样写：

```text
基金或资产
-> 起始权重
-> 本期回报
-> 收益贡献
-> 对应基准
-> 相对基准差异
-> 费用和税务口径
-> 本期是否有再平衡动作
-> 下一次要核验什么
```

收益贡献的入门公式是：

```text
某资产收益贡献 ≈ 起始权重 × 该资产本期回报
```

这个公式只是入门近似。真实归因还要处理资金流入流出、期间再平衡、分红再投资、税务、交易价格和持仓变化。它的价值在于让学习者先看到一个事实：小仓位如果涨得特别多，也可能贡献很多收益；大仓位如果涨得一般，也可能因为权重大而贡献主要收益。

### 用自己的话解释

可以把组合绩效想成一锅汤。总回报只是告诉你这锅汤好不好喝，归因是问：

```text
味道主要来自底汤，还是来自辣椒？
来自肉，还是来自调味料？
是不是某个配料放得太多，掩盖了其他味道？
```

ETF 组合也一样：

```text
SPY 可能提供宽基权益回报。
XLK 可能提供科技板块倾斜。
SOXX 可能提供半导体集中暴露。
AIQ 和 BOTZ 可能提供主题和产业链暴露。
SGOV 可能提供短端国债现金仓位回报。
```

如果今年组合好看，不一定说明每个判断都好；可能只是半导体大涨、科技权重较高、现金收益稳定，或者某个行业刚好处在强势阶段。

### 常见误区

- 误区一：账户涨了，就说明策略正确。结果好不等于过程好，可能只是运气、集中暴露或市场风格。
- 误区二：只看价格回报，不看总回报。分配再投资会影响长期比较。
- 误区三：把 NAV return 和 market price return 混在一起。ETF 交易价格可能高于或低于 NAV。
- 误区四：把日期不同的数据硬拼。归因必须尽量对齐日期，否则结论会失真。
- 误区五：只看税前，不看税后。应税账户里的分配和卖出会改变实际留下的结果。
- 误区六：把主题基金的强回报当成可重复能力。主题和行业暴露可能周期性很强。

## 第二大板块：实时背景与市场传导

### 发生了什么

CFA Institute 的 2026 年绩效评估材料把绩效评估分成 measurement、attribution 和 appraisal，并强调使用者要理解分析方法、数据输入和局限，避免从结果中推断出超出数据能力的结论。该材料还区分 returns-based、holdings-based 和 transactions-based attribution：只看回报、看期间持仓、以及同时看持仓和交易记录，能回答的问题不一样。

Investor.gov 的 ETF / mutual fund shareholder report 投资者公告说明，SEC 注册的共同基金和 ETF 必须向股东提供年度和半年度报告；报告包括费用信息、绩效信息、统计信息、持仓图表和重大基金变化等。公告还提醒，年度报告中的绩效信息会包含叙述、折线图和表格，帮助投资者理解基金在报告期内怎样表现，以及是否符合基金目标和策略。

SEC 的 Form N-PORT 数据集页面说明，Form N-PORT 是注册管理投资公司和部分 ETF 用于月度组合持仓报告的表格；公开数据集按季度更新，SEC 同时提醒数据集不能替代完整申报文件。这为“持仓归因”提供了正式监管入口，但也要求学习者核对完整文件和发行方页面。

State Street SPY 官方页面显示，截至 2026-08-11，SPY NAV 为 770.52 美元，AUM 为 8148.1426 亿美元，费用率 0.0945%，30-day median bid/ask spread 为 0.00%，premium/discount 为 -0.01%。截至 2026-07-31，SPY 的 NAV YTD return 为 10.06%，market value YTD return 为 10.08%，S&P 500 Index YTD 为 10.14%；税后分配回报 YTD 为 9.83%，税后分配并卖出回报 YTD 为 5.95%。截至 2026-08-11，SPY 前十大持仓包括 NVIDIA 7.92%、Apple 6.74%、Microsoft 5.63%，Information Technology 行业权重为 37.51%。

State Street XLK 官方页面显示，截至 2026-08-11，XLK NAV 为 186.16 美元，AUM 为 1219.9037 亿美元，费用率 0.08%，30-day median bid/ask spread 为 0.01%，premium/discount 为 0.00%。截至 2026-07-31，XLK 的 NAV YTD return 为 22.06%，market value YTD return 为 22.06%，Technology Select Sector Index YTD 为 22.10%；税后分配回报 YTD 为 21.94%，税后分配并卖出回报 YTD 为 13.05%。截至 2026-08-11，XLK 前十大持仓包括 NVIDIA 14.19%、Apple 12.06%、Microsoft 10.08%，Semiconductors & Semiconductor Equipment 行业权重为 44.63%。

iShares SOXX 官方页面显示，截至 2026-08-11，SOXX NAV 为 534.49 美元，NAV total return YTD 为 77.70%，费用率 0.33%，净资产为 426.2595 亿美元，premium/discount 为 -0.06，30-day median bid/ask spread 为 0.04%。截至 2026-08-10，SOXX 行业暴露为 Semiconductors 78.92%、Semiconductor Equipment 20.94%。这说明它不是一般科技宽基，而是非常集中的半导体 ETF。

iShares SGOV 官方页面显示，截至 2026-08-11，SGOV NAV 为 100.50 美元，NAV total return YTD 为 2.21%，费用率 0.09%，净资产为 1018.9544 亿美元，premium/discount 为 0.01，30-day median bid/ask spread 为 0.01%；截至 2026-08-10，30-day SEC yield 为 3.59%，effective duration 为 0.10 年，weighted average maturity 为 0.11 年。这说明现金仓位也有回报来源和利率口径，不能简单写成“没贡献”。

Global X AIQ 官方页面显示，截至 2026-08-11，AIQ NAV 为 63.17 美元，市场价格为 63.20 美元，费用率 0.68%，净资产为 101.8 亿美元，持仓数量 88，30-day median bid/ask spread 为 0.02%，30-day SEC yield 为 -0.18%。截至 2026-07-31，AIQ 行业暴露中 Information Technology 为 71.5%。截至 2026-08-11，前十大持仓包括 Palantir、Microsoft、Oracle、Amazon、SpaceX、Netflix、Alphabet、Cisco、Broadcom 和 Tencent。

Global X BOTZ 官方页面显示，截至 2026-08-11，BOTZ NAV 为 37.42 美元，费用率 0.68%，净资产为 35.6 亿美元，持仓数量 61，30-day median bid/ask spread 为 0.03%，30-day SEC yield 为 -0.04%。截至 2026-07-31，BOTZ 行业暴露中 Industrials 为 45.2%，Information Technology 为 37.1%。截至 2026-08-11，前十大持仓包括 Keyence、ABB、NVIDIA、FANUC、Intuitive Surgical、SMC、Shenzhen Inovance、Daifuku、Aurora Innovation 和 Cognex。

### 为什么重要

这些事实放在一起，可以看到一个非常适合新手的归因问题：

```text
SPY 是宽基，但科技权重已经很高。
XLK 是科技板块，而且半导体与半导体设备接近半数。
SOXX 是半导体集中暴露。
AIQ 是 AI 和大数据主题，更偏信息技术和平台公司。
BOTZ 是机器人与 AI 主题，更偏工业自动化和全球制造链。
SGOV 是短端国债现金工具，主要受短端利率环境影响。
```

如果一个组合同时持有这些 ETF，组合涨跌不能只写成“我的 ETF 涨了”。更严谨的说法应该是：

```text
宽基市场贡献了多少？
科技板块倾斜贡献了多少？
半导体集中暴露贡献了多少？
AI 主题和机器人主题分别贡献了多少？
现金仓位是降低波动、提供收益，还是拖累权益牛市中的表现？
费用、税后结果和买卖价差改变了多少最终回报？
```

### 本节采用的数据和来源

- 绩效评估方法：CFA Institute Portfolio Performance Evaluation。
- 股东报告和持仓复盘入口：Investor.gov shareholder report bulletin。
- 监管持仓数据入口：SEC Form N-PORT data sets。
- 宽基和科技板块样本：State Street SPY、XLK 官方页面。
- 半导体和现金仓位样本：iShares SOXX、SGOV 官方页面。
- AI 与机器人主题样本：Global X AIQ、BOTZ 官方页面。

### 这些现实事件如何连接理论

一个入门级绩效归因流程可以写成：

```text
账户总回报
-> 单只 ETF 回报
-> 单只 ETF 起始权重
-> 收益贡献
-> 对应基准回报
-> 基准差异
-> 持仓和行业变化
-> 费用、价差、溢价折价
-> 税前和税后口径
-> 写入决策日志
```

用 2026-06-30 的月末数据做一个只用于教学的同步日期示例，假设一个组合在年初为：

```text
60% SPY
20% XLK
10% SOXX
10% SGOV
```

对应发行方页面可读取的 2026-06-30 YTD NAV return 为：

```text
SPY 10.13%
XLK 32.68%
SOXX 113.00%
SGOV 1.77%
```

粗略收益贡献为：

```text
SPY: 60% × 10.13% ≈ 6.08 个百分点
XLK: 20% × 32.68% ≈ 6.54 个百分点
SOXX: 10% × 113.00% ≈ 11.30 个百分点
SGOV: 10% × 1.77% ≈ 0.18 个百分点
```

这个示例告诉我们：即使 SOXX 年初只有 10%，强回报也可能成为组合最主要的收益贡献来源。它也提醒我们，收益贡献不是独立风险来源，因为 SPY、XLK 和 SOXX 的科技与半导体暴露本来就有重叠。

### 至少一个实时新闻、往期事件或真实市场机制案例

本课案例是“半导体卫星仓位对组合绩效的贡献”。SOXX 官方页面截至 2026-08-11 显示，其 NAV total return YTD 为 77.70%，行业暴露几乎全部在半导体和半导体设备；XLK 截至 2026-08-11 的行业配置中，Semiconductors & Semiconductor Equipment 为 44.63%；SPY 的 Information Technology 权重为 37.51%。

这意味着：

```text
同一条 AI 算力和半导体链条
可能同时通过宽基、科技板块、半导体行业和 AI 主题进入账户。
```

因此，一个看起来分散的 ETF 组合，可能在绩效来源上高度集中。复盘时要从“收益好不好”继续追问“收益来自哪里”。

## 政治、制度和规则视角

### 涉及的政策、监管、制度或国际关系

- SEC 披露制度：股东报告、N-PORT、基金官网披露和 EDGAR 文件是基金复盘的正式入口。
- 指数许可与方法论：SPY、XLK、SOXX、AIQ 和 BOTZ 的基准不同，不能用同一个指数评价所有基金。
- ETF 交易制度：NAV、市场价格、溢价折价和 bid/ask spread 决定投资者实际交易结果。
- 税务制度：税后回报字段显示，应税账户里的实际结果可能明显不同于税前总回报。
- 产业政策：AI、半导体、机器人和自动化相关 ETF 会受到出口管制、供应链、资本开支和国际产业政策影响。

### 已确认事实

- CFA Institute 区分 performance measurement、performance attribution 和 performance appraisal，并强调归因方法和数据限制。
- Investor.gov 说明共同基金和 ETF 股东报告包括费用、绩效、统计信息、持仓图表和重大基金变化。
- SEC Form N-PORT 是注册基金和部分 ETF 月度组合持仓报告入口，公开数据集按季度更新，但不能替代完整申报文件。
- SPY、XLK、SOXX、SGOV、AIQ 和 BOTZ 的发行方页面均披露了可用于复盘的 NAV、价格、费用、持仓、行业暴露、分配或收益字段。
- SPY 与 XLK 官方页面给出了税前、税后分配、税后分配并卖出等不同绩效口径。

### 市场可能如何传导

如果 AI、半导体和大型科技继续强势，组合回报可能主要来自同一条链条的叠加；如果这条链条回撤，多个 ETF 可能同时贡献负收益。SGOV 这类短端国债 ETF 在权益强势期可能显得“拖累”，但在波动期可能提供流动性和短端利息收入。复盘要同时记录收益贡献和风险作用。

### 仍需核验或观察

- 各 ETF 的持仓和行业权重是否继续集中。
- 基金回报和基准回报之间的 tracking difference 是否扩大。
- 费用率、股东报告、资本利得分配和税务补充文件是否更新。
- premium/discount 和 bid/ask spread 是否在压力日扩大。
- AIQ、BOTZ 等主题 ETF 的指数方法论和持仓是否改变。
- 组合是否在再平衡后改变了收益来源。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Performance Measurement | 绩效衡量 | 先算赚了多少或亏了多少 | 是复盘第一步 |
| Performance Attribution | 绩效归因 | 解释收益或亏损来自哪里 | 防止把结果误认为能力 |
| Performance Appraisal | 绩效评价 | 判断过程和能力是否可靠 | 不只看单期结果 |
| Total Return | 总回报 | 价格变化加分配再投资 | 比单看价格更完整 |
| NAV Return | 净值回报 | 按基金净资产价值计算的回报 | 衡量基金本身表现 |
| Market Price Return | 市价回报 | 按交易价格计算的回报 | 反映投资者交易口径 |
| Benchmark Return | 基准回报 | 用来比较基金表现的参照 | 没有基准就难以判断好坏 |
| Excess Return | 超额回报 | 基金回报减去基准回报 | 判断是否跑赢或跑输 |
| Contribution to Return | 收益贡献 | 权重乘以回报的近似贡献 | 找出主要收益来源 |
| Allocation Effect | 配置效应 | 多配或少配某类资产带来的影响 | 判断权重选择是否有用 |
| Selection Effect | 选择效应 | 在同类资产中选中具体标的的影响 | 判断具体选择是否有用 |
| Tracking Difference | 跟踪差异 | 基金回报和基准回报的差 | 检查费用、复制和交易影响 |
| Fee Drag | 费用拖累 | 费用率、价差、佣金等降低回报 | 影响长期复利 |
| Tax Drag | 税务拖累 | 税务让税后结果低于税前结果 | 应税账户必须看 |
| Cash Drag | 现金拖累 | 现金仓位在强行情中可能落后 | 但也能管理流动性 |
| Decision Journal | 决策日志 | 记录事实、假设、行动和复查点 | 让复盘可追溯 |

## 回顾提示

- 学到本课前建议回顾：可回顾第 50 课基金表现归因、第 51 课基金风险指标、第 52 课核心/卫星配置、第 82 课组合重叠和风险预算、第 83 课税务敏感再平衡。
- 本课哪些内容会在后续课程继续使用：收益贡献、配置效应、选择效应、跟踪差异、费用拖累、税务拖累、现金拖累和决策日志。
- 如果看不懂本课，可以先回到：第 4 课基金和 ETF 入门、第 48 课 ETF 持仓穿透、第 49 课 ETF 交易机制。

## 案例拆解

### 案例对象

SPY、XLK、SOXX、AIQ、BOTZ 和 SGOV 的 ETF 组合绩效复盘。

### 已确认事实

- SPY 截至 2026-07-31 的 NAV YTD return 为 10.06%，S&P 500 Index YTD 为 10.14%；截至 2026-08-11，Information Technology 权重为 37.51%。
- XLK 截至 2026-07-31 的 NAV YTD return 为 22.06%，Technology Select Sector Index YTD 为 22.10%；截至 2026-08-11，半导体与半导体设备行业权重为 44.63%。
- SOXX 截至 2026-08-11 的 NAV total return YTD 为 77.70%，行业暴露中 Semiconductors 为 78.92%、Semiconductor Equipment 为 20.94%。
- SGOV 截至 2026-08-11 的 NAV total return YTD 为 2.21%，截至 2026-08-10 的 30-day SEC yield 为 3.59%，effective duration 为 0.10 年。
- AIQ 截至 2026-08-11 的费用率为 0.68%，净资产为 101.8 亿美元，持仓数量 88；截至 2026-07-31，Information Technology 权重为 71.5%。
- BOTZ 截至 2026-08-11 的费用率为 0.68%，净资产为 35.6 亿美元，持仓数量 61；截至 2026-07-31，Industrials 权重为 45.2%，Information Technology 权重为 37.1%。

### 来源日期和链接

- CFA Institute Portfolio Performance Evaluation, 2026: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
- Investor.gov shareholder report bulletin, 2024-01-19: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
- SEC Form N-PORT Data Sets, last reviewed or updated 2026-06-30: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
- State Street SPY official page, data as of 2026-08-11 and 2026-07-31: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- State Street XLK official page, data as of 2026-08-11 and 2026-07-31: https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- iShares SOXX official page, data as of 2026-08-11 and 2026-08-10: https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- iShares SGOV official page, data as of 2026-08-11 and 2026-08-10: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
- Global X AIQ official page, data as of 2026-08-11 and 2026-07-31: https://www.globalxetfs.com/funds/AIQ
- Global X BOTZ official page, data as of 2026-08-11 and 2026-07-31: https://www.globalxetfs.com/funds/BOTZ

### 分析推理

如果一个组合今年表现很好，第一步不是问“下一只买什么”，而是做归因：

```text
宽基贡献了多少？
科技板块贡献了多少？
半导体集中暴露贡献了多少？
主题 ETF 是否只是重复同一条 AI 链条？
现金仓位是保护了组合，还是在强行情中形成机会成本？
```

在本课的教学示例里，SOXX 的强回报可能让一个小卫星仓位成为主要收益来源。但这并不自动说明应扩大半导体仓位，因为强贡献也可能意味着风险预算被动上升。

### 后续验证指标

- 每只 ETF 的 NAV return、market price return、benchmark return。
- 每只 ETF 的前十大持仓、行业权重和持仓变化。
- 组合里 NVIDIA、Apple、Microsoft、Broadcom、Micron 等共同持仓的穿透权重。
- Expense ratio、bid/ask spread、premium/discount 和分配历史。
- SPY、XLK、SOXX、AIQ、BOTZ、SGOV 的股东报告和 N-PORT / 完整持仓文件。
- 账户层面的税前和税后回报。

## 个人情境连接

- 对关注清单的启发：不要只记录“涨跌幅”，还要记录“收益贡献”和“对应原因”。
- 对持仓或基金选择的启发：强贡献的仓位要同时检查是否超过风险预算，而不是只庆祝结果。
- 对工作、收入、消费或风险管理的启发：复盘时要区分结果和过程，很多生活决策也是同理。

## 结论边界

- 可以确定：ETF 绩效复盘必须同时看总回报、基准、持仓、行业暴露、费用、交易价格和税务口径。
- 不能确定：某只 ETF 未来是否继续贡献正收益，也不能凭单期归因判断投资能力。
- 需要继续观察：持仓变化、基准差异、费用、分配、税务、溢价折价、买卖价差和再平衡记录。
- 不构成投资建议的原因：本课只训练复盘和归因方法，不提供任何买入、卖出或持有建议。

## 练习题

1. 用自己的话区分 performance measurement、performance attribution 和 performance appraisal。
2. 为什么同一个 ETF 要同时看 NAV return 和 market price return？
3. 假设某组合年初 10% 持有 SOXX，年内 SOXX 涨幅很高，这说明了什么？又不能说明什么？
4. 用 `权重 × 回报` 写出一个三资产组合的粗略收益贡献表。
5. 为什么现金仓位既可能是 cash drag，也可能是风险管理工具？

## 学习交接

- 本课已经完成：把 ETF 组合管理从税务敏感再平衡推进到绩效衡量、绩效归因、收益贡献、配置效应、选择效应、跟踪差异、费用拖累、税务拖累、现金拖累和研究日志。
- 本课最重要的一句话：账户涨跌只是结果，归因要回答结果来自哪里，复盘要回答这个过程是否值得重复。
- 需要复习的关键词：Performance Attribution、Contribution to Return、Allocation Effect、Selection Effect、Tracking Difference、Fee Drag、Tax Drag、Cash Drag、Decision Journal。
- 还不稳定、下次要回看的地方：不同日期、不同回报口径和不同税务账户不能混在一起做硬结论。
- 适合下次打开仓库先读的文件：`lessons/2026-08-12-lesson-85-etf-decision-journal-review-cadence.md`

## 下节课安排

- 建议主题：第八十五课：ETF 决策日志、反证指标与复查节奏入门：把复盘写成可执行的研究流程。
- 学习目标：理解 thesis、base case、bear case、bull case、pre-commitment、review trigger、反证指标、no-action decision、source log 和 handoff note。
- 建议案例：继续使用 AIQ、BOTZ、SOXX、XLK、SPY 和 SGOV，演示如何把“AI 主题表现好/差”写成可核验的决策日志，而不是事后找理由。
- 必须解释的关键词：Thesis、Base Case、Bear Case、Bull Case、Disconfirming Evidence、Review Trigger、No-Action Decision、Source Log、Handoff Note。
- 下节课开始前需要联网核验的数据：AIQ/BOTZ 官方持仓、行业暴露、费用、价差、净资产、指数方法论、股东报告；SOXX/XLK/SPY 的半导体和科技穿透权重；SGOV 的 30-day SEC yield 和短端期限结构。

## 来源

- CFA Institute, Portfolio Performance Evaluation: https://www.cfainstitute.org/insights/professional-learning/refresher-readings/2026/portfolio-performance-evaluation
- Investor.gov, How to Read a Mutual Fund or ETF Shareholder Report: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-investor-bulletin-how-read-mutual-fund-or-etf-shareholder-report
- SEC, Form N-PORT Data Sets: https://www.sec.gov/data-research/sec-markets-data/form-n-port-data-sets
- State Street, SPY: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- State Street, XLK: https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- iShares, SOXX: https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- iShares, SGOV: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
- Global X, AIQ: https://www.globalxetfs.com/funds/AIQ
- Global X, BOTZ: https://www.globalxetfs.com/funds/BOTZ
