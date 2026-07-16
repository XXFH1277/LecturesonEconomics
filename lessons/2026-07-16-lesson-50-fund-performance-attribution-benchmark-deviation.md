# 第五十课：基金表现归因、基准偏离与主动/被动差异入门

## 基本信息

- 日期：2026-07-16
- 数据截至：2026-07-16 16:12（Asia/Shanghai）。SPY 采用 State Street 页面显示的 2026-07-16 基金信息、2026-07-15 NAV/市场价格、2026-06-30 月末业绩、2026-07-14 持仓和行业权重；S&P 500 Equal Weight Index 采用 S&P DJI 页面截至 2026-07-16 可核验内容；主动基金对比采用 S&P DJI SPIVA U.S. Year-End 2025（2026-03-03）；基金基础规则采用 SEC《Mutual Funds and ETFs: A Guide for Investors》。
- 主题：为什么基金“涨了多少”不是完整答案；如何把基金回报拆成基准回报、费用拖累、跟踪差异、行业配置、个股选择和主动/被动差异。
- 学习目标：理解 Benchmark Return、Active Return、Tracking Difference、Tracking Error、Expense Drag、Sector Allocation、Security Selection、Style Exposure、Cash Drag 和 Attribution；学会用官方基金页做最小归因表。
- 相关资产：ETF、指数基金、主动基金、SPY、S&P 500、S&P 500 Equal Weight Index、QQQ、基金业绩披露。
- 核心来源：
  - State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - S&P DJI, S&P 500 Equal Weight Index: https://www.spglobal.com/spdji/en/indices/equity/sp-500-equal-weight-index/
  - S&P DJI, SPIVA U.S. Year-End 2025: https://www.spglobal.com/spdji/en/spiva/article/spiva-us/
  - SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
  - Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经知道 ETF 的成交价格可能偏离 NAV。今天的问题是：

> 如果一个基金今年涨了 10%，这到底算好还是不好？

不能只看 10%。要先问它本来应该和谁比较。如果基金的基准涨了 15%，基金涨 10% 可能是落后；如果基准跌了 5%，基金涨 10% 可能是明显超额。基金表现归因就是把“涨跌结果”拆成“基准本来给了多少、基金经理或指数规则多做了什么、费用和交易拖累了多少”。

### 参考的教材式概念顺序

1. Total Return：总回报，包含价格变化和分红再投资。
2. Benchmark：基准，用来判断基金目标和表现的参照物。
3. Benchmark Return：基准回报，基准本身在同一时间段的收益。
4. Active Return：主动回报，基金回报减去基准回报。
5. Tracking Difference：跟踪差异，一段时间内基金回报和基准回报的差。
6. Tracking Error：跟踪误差，这个差异的波动程度。
7. Expense Drag：费用拖累，费用率、交易成本和税务造成的净回报下降。
8. Sector Allocation：行业配置，行业权重和基准不同带来的影响。
9. Security Selection：个股选择，同一行业里选中的证券表现不同带来的影响。
10. Style Exposure：风格暴露，例如成长、价值、大盘、小盘、质量、动量。
11. Cash Drag：现金拖累，基金保留现金而没有完全投入市场时的影响。

### 核心概念

最小归因框架可以写成：

```text
基金回报 = 基准回报 + 主动回报

主动回报 = 行业配置影响
        + 个股选择影响
        + 风格暴露影响
        - 费用拖累
        - 现金拖累
        +/- 交易、税务、复制方式和其他影响
```

对指数基金来说，目标通常不是创造很大的主动回报，而是尽量贴近基准，扣除费用后保持可解释的 tracking difference。对主动基金来说，目标是通过配置和选股在扣除费用后超过基准，但这个目标不能当成保证。

### 用自己的话解释

基准像考试标准答案，基金回报像你的答卷得分。只说“我考了 80 分”不够，要看标准答案平均多少、题目难不难、你在哪些题上多拿分、在哪些题上丢分。

基金表现也是一样：

- 市场整体上涨带来的部分，叫基准回报。
- 基金自己偏离基准带来的部分，叫主动回报。
- 费用、现金、交易和税务，通常会拖累净回报。
- 行业和个股偏离可能带来超额，也可能带来落后。

### 常见误区

- 误区一：基金涨了就是基金经理厉害。可能只是基准也涨了。
- 误区二：指数基金没有归因问题。指数基金也要看 tracking difference、费用、现金和复制方式。
- 误区三：主动基金短期跑赢就证明长期能力。短期结果可能来自风格、行业、运气或市场阶段。
- 误区四：等权指数就是主动基金。等权是规则化指数方法，但相对于市值加权 S&P 500，它会形成主动暴露。
- 误区五：回报越高越好。还要看承担了多少波动、回撤、集中度和流动性风险；这会留到第 51 课继续讲。

## 第二大板块：实时背景与市场传导

### 发生了什么

State Street SPY 页面显示，SPY 的 benchmark 为 S&P 500 Index，gross expense ratio 为 0.0945%，基金目标是在扣除费用前大体对应 S&P 500 的价格和收益表现。该页面 2026-06-30 月末业绩显示：

| 期间 | SPY NAV 回报 | SPY Market Value 回报 | S&P 500 Index 回报 | 入门解读 |
| --- | ---: | ---: | ---: | --- |
| 1 Month | -0.96% | -1.07% | -0.95% | NAV 与基准接近，市场价格口径略低 |
| YTD | 10.13% | 10.02% | 10.21% | NAV 较基准低 0.08 个百分点 |
| 1 Year | 22.15% | 22.08% | 22.32% | 费用和复制差异会累积 |
| 3 Year | 20.46% | 20.44% | 20.61% | 长期仍需看年化差异 |
| 10 Year | 15.35% | 15.34% | 15.51% | 指数回报不扣基金费用 |
| Since Inception | 10.83% | 10.83% | 10.97% | 小差异长期也会复利 |

S&P DJI 的 S&P 500 Equal Weight Index 页面说明，S&P 500 Equal Weight Index 包含与市值加权 S&P 500 相同的成分股，但在每次季度再平衡时，每家公司固定为指数总权重的 0.2%。这说明“同样 500 家公司”也可以因为权重规则不同而产生不同表现。

S&P DJI 的 SPIVA U.S. Year-End 2025 显示，2025 年 79% 的主动大盘美国股票基金跑输 S&P 500，高于 2024 年的 65%。这个事实不是说主动管理永远没用，而是提醒初学者：主动基金必须用基准、费用、风格和周期一起评估。

### 为什么重要

第 48 课解决“基金买了什么”，第 49 课解决“基金份额怎么交易”。本课解决“基金表现从哪里来”。

同一个结果可能来自不同原因：

```text
基金 A 涨 10%：
- 基准涨 12%：基金落后 2 个百分点
- 基准涨 5%：基金超额 5 个百分点
- 基准涨 10%，基金也涨 10%：看费用、跟踪差异和交易口径
- 基准跌 5%，基金涨 10%：要问是否承担了完全不同风险
```

所以，基金表现归因的第一步不是预测，而是对齐比较对象。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| SPY benchmark | S&P 500 Index | State Street, fund information as of 2026-07-16 | 基准识别 |
| SPY gross expense ratio | 0.0945% | State Street, fund information as of 2026-07-16 | 费用拖累 |
| SPY NAV | 754.68 美元 | State Street, as of 2026-07-15 | 净值口径 |
| SPY closing price | 754.81 美元 | State Street, as of 2026-07-15 | 市场价格口径 |
| SPY YTD NAV return | 10.13% | State Street, month-end as of 2026-06-30 | 归因演示 |
| S&P 500 YTD return | 10.21% | State Street benchmark table, as of 2026-06-30 | 基准回报 |
| Equal weight rule | 每次季度再平衡时，每家公司固定 0.2% | S&P DJI S&P 500 Equal Weight Index page, accessed 2026-07-16 | 权重方法论 |
| Active large-cap underperformance | 2025 年 79% 主动大盘美国股票基金跑输 S&P 500 | S&P DJI SPIVA U.S. Year-End 2025, 2026-03-03 | 主动/被动差异 |
| QQQ expense ratio | total expense ratio 0.18% | Invesco QQQ Performance page, accessed 2026-07-16 | 费用比较入口 |

### 这些现实事件如何连接理论

用 SPY 做最小归因，不需要复杂模型：

```text
时间段：2026 年 YTD，截至 2026-06-30
基金 NAV 回报：10.13%
基准 S&P 500 回报：10.21%
Tracking Difference = 10.13% - 10.21% = -0.08 个百分点

初步解释：
- SPY 的目标是跟踪 S&P 500，不是大幅跑赢 S&P 500。
- 指数回报不扣基金费用，基金净回报会受到费用、复制方式、现金、交易和税务影响。
- Market Value 回报为 10.02%，说明真实二级市场买卖还可能受到成交口径影响。
```

再看等权指数：

```text
市值加权 S&P 500：
大公司权重大，NVIDIA、Apple、Microsoft 等大权重公司影响更大。

S&P 500 Equal Weight Index：
同样成分股，但季度再平衡时每家公司约 0.2%。

结论：
等权不是“更正确”，只是另一种规则。
它降低少数巨头影响，同时提高较小成分股、行业广度和再平衡交易的重要性。
```

### 至少一个真实市场机制案例

真实机制是“同一批股票，不同权重，会产生不同归因”。

如果某一阶段大型科技股强势：

```text
市值加权指数
-> 大型科技股权重高
-> 基准回报更多受少数巨头推动
-> 跟踪市值加权指数的 ETF 表现更像巨头组合
```

如果市场上涨从少数巨头扩散到更多公司：

```text
等权指数
-> 每家公司权重更接近
-> 中小权重成分股贡献更明显
-> 相对市值加权指数可能阶段性改善
```

这不是预测哪一个会赢，而是训练你问：回报来自哪里？

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 基金披露、基金招募说明书、指数授权、基金业绩标准化披露、SPIVA 主动基金对比、指数提供商方法论。
- 已确认事实：SPY 数据来自 State Street；S&P 500 Equal Weight Index 规则来自 S&P DJI；主动基金跑输比例来自 S&P DJI SPIVA；SEC 指出基金和 ETF 有成本、风险和披露要求。
- 市场可能如何传导：基准集中度上升会提高指数基金对少数公司的依赖；费用率影响长期净回报；主动基金的行业和风格偏离会在不同市场阶段放大领先或落后。
- 仍需核验或观察：基金下一期业绩、基准变化、费用变化、持仓和行业权重、主动基金换手率、税务分配、现金比例和风格暴露。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Benchmark Return | 基准回报 | 基金参照对象的收益 | 判断表现好坏的起点 |
| Active Return | 主动回报 | 基金回报减基准回报 | 看是否真正跑赢 |
| Attribution | 归因 | 把回报拆成来源 | 防止只看涨跌 |
| Tracking Difference | 跟踪差异 | 基金与基准一段时间的回报差 | 指数基金核心观察项 |
| Tracking Error | 跟踪误差 | 跟踪差异的波动程度 | 看复制是否稳定 |
| Expense Drag | 费用拖累 | 费用和运营成本对净回报的扣减 | 长期复利会放大 |
| Sector Allocation | 行业配置 | 行业权重相对基准的偏离 | 主动回报来源之一 |
| Security Selection | 个股选择 | 同一行业中选股好坏 | 主动基金核心能力之一 |
| Style Exposure | 风格暴露 | 成长、价值、大盘、小盘等倾向 | 解释阶段性表现 |
| Cash Drag | 现金拖累 | 持有现金而未完全投资 | 上涨市场中可能落后 |
| Equal Weight | 等权 | 每个成分股权重相等或接近 | 改变集中度和风格 |
| Passive Fund | 被动基金 | 按规则跟踪基准 | 重点看费用和跟踪质量 |
| Active Fund | 主动基金 | 主动偏离基准以争取超额 | 重点看能力、费用和持续性 |

## 回顾提示

- 学到本课前建议回顾：第 4 课基金和 ETF、第 47 课组合暴露、第 48 课持仓穿透、第 49 课 ETF 交易机制。
- 本课哪些内容会在后续课程继续使用：风险调整收益、基金筛选、组合构建、核心/卫星配置、再平衡。
- 如果看不懂本课，可以先回到：第 1 课价格不是价值、第 3 课金融产品地图、第 46 课投资备忘录。

## 案例拆解

- 案例对象：SPY 的 2026-06-30 月末业绩与 S&P 500 benchmark。
- 已确认事实：
  - SPY benchmark 为 S&P 500 Index，gross expense ratio 为 0.0945%。
  - SPY 2026-06-30 YTD NAV return 为 10.13%，S&P 500 Index 为 10.21%。
  - SPY 2026-06-30 10-year NAV return 为 15.35%，S&P 500 Index 为 15.51%。
  - SPY 2026-07-15 NAV 为 754.68 美元，closing price 为 754.81 美元。
- 来源日期和链接：见本课“来源”。
- 分析推理：SPY 作为被动 ETF，主要任务是跟踪 S&P 500；小幅落后基准符合费用和复制差异的方向，不应机械解读为“基金经理输给市场”。
- 后续验证指标：月末 NAV return、market value return、benchmark return、expense ratio、premium/discount、holdings、sector weight、cash position、turnover。

## 一个可复制的基金归因检查页

```text
基金名称：
数据截至：
基准：

回报口径：
- NAV return：
- Market price return：
- Benchmark return：
- Active return：

拖累项：
- Expense ratio：
- Bid/ask spread：
- Premium/discount：
- Cash drag：
- Tax distribution：

偏离项：
- Sector allocation：
- Security selection：
- Style exposure：
- Concentration：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
```

## 个人情境连接

- 对关注清单的启发：记录基金时不要只写“涨跌”，要同时写基准和时间段。
- 对持仓或基金选择的启发：指数基金重点看基准、费用和跟踪质量；主动基金还要看是否长期、扣费后、同口径地跑赢。
- 对工作、收入、消费或风险管理的启发：选择任何方案都要先找到参照物。没有基准，评价很容易被短期结果带偏。

## 结论边界

- 可以确定：基金表现必须和基准比较；指数基金也有 tracking difference；主动基金跑赢需要扣除费用和风险后再判断。
- 不能确定：本课不能判断 SPY、QQQ、等权指数或任何主动基金未来谁会跑赢，也不能证明某个基金经理有持续能力。
- 需要继续观察：基金最新业绩、费用率、持仓、行业权重、跟踪差异、主动基金换手和风险调整收益。
- 不构成投资建议的原因：本课只训练基金表现阅读和归因方法，不建议买入、卖出、持有或配置任何基金。

## 练习题

1. 一个基金涨 8%，它的基准涨 12%。请计算 active return，并解释为什么“涨了”不等于“表现好”。
2. 用 SPY 的 2026-06-30 YTD 数据计算 NAV tracking difference。
3. 为什么等权 S&P 500 和市值加权 S&P 500 持有同一批股票，也可能表现不同？
4. 主动基金短期跑赢基准时，你至少还要核验哪三件事？
5. 选一个基金，按“基金回报 -> 基准回报 -> active return -> 费用 -> 偏离来源”的顺序写一页笔记。

## 学习交接

- 本课已经完成：把第 48-49 课的 ETF 持仓和交易机制推进到基金表现归因、基准偏离和主动/被动差异。
- 本课最重要的一句话：基金回报不是孤立数字，必须先找到基准，再拆出费用、跟踪、配置和选择。
- 需要复习的关键词：Benchmark Return、Active Return、Tracking Difference、Tracking Error、Expense Drag、Sector Allocation、Security Selection、Style Exposure、Cash Drag、Attribution。
- 还不稳定、下次要回看的地方：同样的超额回报是否承担了更高波动、回撤、集中度或流动性风险。
- 适合下次打开仓库先读的文件：`lessons/2026-07-16-lesson-50-fund-performance-attribution-benchmark-deviation.md`

## 下节课安排

- 建议主题：第五十一课：基金风险指标、波动率、最大回撤与 Sharpe Ratio 入门。
- 学习目标：理解为什么基金表现要同时看收益和路径，学会用 volatility、maximum drawdown、Sharpe ratio、downside risk、beta、concentration 和 liquidity 读基金风险。
- 建议案例：继续使用 SPY 的官方风险披露、持仓集中度、行业权重和业绩口径，并加入 U.S. Treasury 利率作为风险调整收益的背景。
- 必须解释的关键词：Volatility、Standard Deviation、Maximum Drawdown、Sharpe Ratio、Risk-free Rate、Excess Return、Beta、Downside Risk、Liquidity Risk、Concentration Risk。
- 下节课开始前需要联网核验的数据：基金公司官网的风险披露、持仓集中度、行业权重、历史业绩、基金招募说明书；Treasury 最新短端和长端利率；如引用第三方风险评级，必须标注口径和局限。

## 来源

- State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- S&P DJI, S&P 500 Equal Weight Index: https://www.spglobal.com/spdji/en/indices/equity/sp-500-equal-weight-index/
- S&P DJI, SPIVA U.S. Year-End 2025: https://www.spglobal.com/spdji/en/spiva/article/spiva-us/
- SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
- Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html
