# 第五十九课：美元、汇率、利差与跨资产风险偏好入门

## 基本信息

- 日期：2026-07-21
- 数据截至：2026-07-21 21:50（Asia/Shanghai）。汇率采用 Federal Reserve H.10 2026-07-20 release、截至 2026-07-17 的数据；利率采用 Federal Reserve H.15 2026-07-20 release、截至 2026-07-17 的数据；储备货币背景采用 IMF COFER 2026Q1 data brief，发布日期 2026-07-01；黄金资金流采用 World Gold Council 2026-07-08 Gold ETF Flows: June 2026。
- 主题：为什么美元和汇率会影响黄金、股票、基金净值和跨境资产回报。
- 学习目标：理解 exchange rate、base currency、quote currency、dollar index、interest-rate differential、capital flow、FX translation、reserve currency、hedging 和 risk appetite。
- 相关资产：美元、人民币、欧元、日元、黄金、美国国债、海外股票 ETF、黄金 ETF、跨境基金。
- 核心来源：
  - Federal Reserve, Foreign Exchange Rates H.10, release date 2026-07-20: https://www.federalreserve.gov/releases/H10/current/default.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-20: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - IMF Data, COFER Q1 2026 data brief, 2026-07-01: https://data.imf.org/en/news/imf%20data%20brief%20july%201
  - World Gold Council, Gold ETF Flows: June 2026, 2026-07-08: https://www.gold.org/goldhub/research/gold-etfs-holdings-and-flows/2026/07

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲实际利率如何影响黄金和股票估值。今天补上跨资产里最容易被忽略的一层：

> 为什么同一个资产，用美元看和用人民币看，回报可能不一样？

因为跨境资产有两层价格：

```text
第一层：资产本身涨跌
第二层：计价货币相对你的本币升贬
```

如果买的是美元资产，而你的生活支出在人民币里，最后还要把美元结果翻译回人民币。这就是汇率层。

### 参考的教材式概念顺序

1. Currency：货币，一国或地区的记账和支付单位。
2. Exchange Rate：汇率，两种货币之间的兑换价格。
3. Base Currency：基准货币，汇率报价里被标价的那种货币。
4. Quote Currency：报价货币，用来衡量基准货币价格的那种货币。
5. USD per EUR：每 1 欧元值多少美元。
6. CNY per USD：每 1 美元值多少人民币。
7. Dollar Index：美元指数，用一篮子货币衡量美元整体强弱。
8. Interest-rate Differential：利差，不同货币资产之间的利率差。
9. Capital Flow：资本流动，资金在国家、货币和资产之间移动。
10. FX Translation：汇兑折算，把外币资产价值换回本币。
11. Hedging：套期保值，用工具降低汇率波动影响。
12. Reserve Currency：储备货币，央行和官方机构持有的外汇储备货币。

### 核心概念

汇率可以先用一条简单公式理解：

```text
本币回报 ~= 外币资产回报 + 外币兑本币变化
```

举例：

```text
一个美元资产本身上涨 5%
如果美元兑人民币又上涨 2%
人民币视角的近似回报会高于 5%

反过来：
如果美元兑人民币下跌 2%
人民币视角的回报会被汇率吃掉一部分
```

这只是入门近似，实际基金还会有交易费用、税费、申赎时间、汇率牌价和是否做汇率对冲等差异。

### 用自己的话解释

美元像全球金融系统里的主干计价货币之一。黄金常用美元报价，许多大宗商品用美元报价，美国国债用美元支付利息和本金，很多跨境基金也用美元资产做底层。

当美元变强时：

- 用非美元货币看，美元资产折算价值可能上升。
- 黄金如果用美元报价，可能面临“美元更强、黄金美元价格更难涨”的压力，但不是机械关系。
- 新兴市场货币和美元债压力可能上升，因为还美元更贵。

当美元变弱时：

- 非美元资产折算成美元可能更好看。
- 黄金、部分商品和海外资产可能获得汇率层面的叙事支持。
- 但如果美元走弱来自美国衰退或风险事件，股票不一定受益。

### 常见误区

- 误区一：汇率就是“人民币升值/贬值”一句话。必须先看报价方向，是 CNY per USD 还是 USD per CNY。
- 误区二：美元强，所有美元资产都涨。美元强可能压制海外收入折算、商品价格和风险偏好。
- 误区三：利差决定一切。资本流还看通胀、信用风险、政治风险、流动性和预期。
- 误区四：不出国就没有汇率风险。进口商品、能源价格、跨境基金、企业利润和就业链条都可能受汇率影响。
- 误区五：对冲一定更好。对冲会降低某些汇率波动，但也有成本和期限错配。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve H.10 2026-07-20 release 显示，截至 2026-07-17，几个常用汇率和美元指数为：

| 项目 | 2026-07-17 | 报价解释 |
| --- | ---: | --- |
| China, P.R. yuan | 6.7760 | 1 美元 = 6.7760 人民币 |
| EMU euro | 1.1440 | 1 欧元 = 1.1440 美元 |
| Japan yen | 162.4300 | 1 美元 = 162.43 日元 |
| United Kingdom pound | 1.3446 | 1 英镑 = 1.3446 美元 |
| Broad dollar index | 120.5315 | 2006 年 1 月 = 100 |
| AFE dollar index | 113.4919 | 发达经济体篮子 |
| EME dollar index | 129.4359 | 新兴市场经济体篮子 |

H.10 明确说明，多数汇率是“每 1 美元兑换多少外币”，但带星号的货币是“每 1 外币兑换多少美元”。所以欧元、英镑、澳元、新西兰元的方向和人民币、日元不同。

同一天的 H.15 利率背景显示，截至 2026-07-17，effective federal funds rate 为 3.63%，10 年 nominal CMT 为 4.55%，10 年 TIPS yield 为 2.31%。Fed 2026-06-17 FOMC statement 维持 3.50%-3.75% 的 federal funds target range。

IMF COFER 2026Q1 data brief 显示，全球官方外汇储备为 13.10 万亿美元；美元在外汇储备中的份额从 2025Q4 的 56.42% 上升到 2026Q1 的 57.13%；欧元份额为 20.03%，人民币份额为 1.99%。IMF 同时提醒，储备货币份额变动会受到汇率估值效应、债券价格变化和主动管理共同影响。

黄金资金流方面，World Gold Council 2026-07-08 报告显示，6 月全球实物支持黄金 ETF 流出 89 亿美元，月末总持仓降至 4,047 吨；但 2026 年上半年全球黄金 ETF 资金流仍为正，合计流入 80 亿美元。报告把美国利率预期、实际收益率和美元作为影响黄金 ETF 资金流的重要宏观背景之一。

### 为什么重要

同一组数据可以连接成一条跨资产链：

```text
Fed policy rate 和实际利率
-> 美元利差吸引力
-> 美元指数和双边汇率
-> 黄金美元价格、海外资产折算、跨境基金回报
-> 风险偏好和资金流
```

如果美元兑人民币从 6.77 走到 6.90，美元资产折算成人民币会多一层汇率收益；如果从 6.77 走到 6.50，美元资产折算成人民币会少一层汇率收益。资产本身没变，计价货币变了，投资者看到的本币结果也会变。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| USD/CNY | 6.7760 | Fed H.10, 2026-07-17 | 人民币视角汇率折算 |
| EUR/USD | 1.1440 | Fed H.10, 2026-07-17 | 反向报价例子 |
| USD/JPY | 162.4300 | Fed H.10, 2026-07-17 | 利差和汇率敏感例子 |
| Broad dollar index | 120.5315 | Fed H.10, 2026-07-17 | 一篮子美元强弱 |
| EME dollar index | 129.4359 | Fed H.10, 2026-07-17 | 新兴市场篮子 |
| Effective federal funds rate | 3.63% | Fed H.15, 2026-07-17 | 美元短端利率背景 |
| 10Y TIPS yield | 2.31% | Fed H.15, 2026-07-17 | 实际利率背景 |
| 全球外汇储备 | 13.10 万亿美元 | IMF COFER, 2026Q1 | 储备货币背景 |
| 美元储备份额 | 57.13% | IMF COFER, 2026Q1 | 美元制度地位 |
| 6 月黄金 ETF 流出 | 89 亿美元 | WGC, 2026-07-08 | 资金流案例 |

### 这些现实事件如何连接理论

第一条链：利差与美元。

```text
美元短端利率仍在 3.50%-3.75% 目标区间附近
-> 美元现金和短债仍有收益率吸引力
-> 如果其他货币利率更低，资金可能更愿意持有美元资产
-> 美元可能获得支撑
```

这不是保证。汇率还会看增长、通胀、贸易、财政、政治风险和市场预期。

第二条链：美元与黄金。

```text
黄金通常以美元报价
美元走强 + 实际利率上升
-> 非美元买家的黄金成本可能上升
-> 黄金 ETF 机会成本可能上升
```

但央行购金、地缘风险和避险需求可能抵消这条压力，所以不能把美元强弱当成金价公式。

第三条链：美元与海外基金。

```text
底层资产回报
+ 汇率折算
- 基金费用
- 对冲成本
= 投资者本币看到的近似结果
```

很多人只看第一层资产涨跌，忽略了第二层汇率折算。

### 至少一个真实市场机制案例

案例：用 Fed H.10 的 2026-07-17 USD/CNY 做折算练习。

```text
USD/CNY = 6.7760
假设某美元 ETF 价格为 100 美元
人民币折算价值约为 677.60 元
```

如果 ETF 美元价格不变，但 USD/CNY 变成 6.90：

```text
100 美元 x 6.90 = 690.00 元
```

如果 ETF 美元价格不变，但 USD/CNY 变成 6.50：

```text
100 美元 x 6.50 = 650.00 元
```

这说明汇率本身就能改变本币结果。真实投资还要考虑买卖价差、基金净值时间、申赎规则、税费和是否汇率对冲。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 货币政策、美元作为储备货币、IMF COFER 统计、跨境资本流动、央行储备管理、基金汇率对冲规则。
- 已确认事实：Fed H.10 提供截至 2026-07-17 的主要汇率和美元指数；IMF COFER 显示 2026Q1 美元仍是最大官方外汇储备货币；Fed H.15 提供美元利率背景；WGC 提供黄金 ETF 资金流背景。
- 市场可能如何传导：美元利差和实际利率影响资本流；美元强弱影响黄金美元报价、非美元投资者成本和海外资产本币回报；储备货币地位影响全球资金对美元资产的基础需求。
- 仍需核验或观察：下一期 H.10、H.15、FOMC、主要央行政策、IMF 后续 COFER、贸易与资本流数据、黄金 ETF flow、跨境基金汇率对冲成本。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Exchange Rate | 汇率 | 两种货币的兑换价格 | 决定外币资产折算成本 |
| Base Currency | 基准货币 | 报价中被标价的货币 | 避免看错方向 |
| Quote Currency | 报价货币 | 用来给基准货币标价的货币 | 决定“每 1 单位值多少” |
| USD Index | 美元指数 | 美元相对一篮子货币的强弱 | 比单一汇率更全面 |
| Interest-rate Differential | 利差 | 两种货币资产收益率差 | 影响资金持有哪种货币 |
| Capital Flow | 资本流动 | 资金跨国家和资产移动 | 影响汇率和资产价格 |
| FX Translation | 汇兑折算 | 把外币资产换成本币价值 | 跨境投资必须看 |
| Reserve Currency | 储备货币 | 央行持有的外汇储备货币 | 反映制度和流动性地位 |
| Hedging | 套期保值 | 用工具降低汇率风险 | 降波动但有成本 |
| Risk Appetite | 风险偏好 | 市场愿不愿意承担风险 | 影响美元、黄金和股票同向或反向变化 |

## 回顾提示

- 学到本课前建议回顾：第 1 课市场地图、第 5 课利率、第 6 课黄金原油、第 15 课利率与估值、第 58 课实际利率与黄金股票传导。
- 本课哪些内容会在后续课程继续使用：跨境 ETF、QDII/互联互通、美元债、新兴市场、商品、企业海外收入折算。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图，重新理解“资产关系”和“计价单位”。

## 案例拆解

- 案例对象：2026-07-17 Fed H.10 汇率与美元指数。
- 已确认事实：
  - USD/CNY 为 6.7760。
  - EUR/USD 为 1.1440。
  - USD/JPY 为 162.4300。
  - Broad dollar index 为 120.5315。
  - IMF COFER 显示 2026Q1 美元储备份额为 57.13%。
- 来源日期和链接：见本课“来源”。
- 分析推理：美元强弱会通过汇率折算、利差吸引力、黄金机会成本和跨境资金流影响投资者看到的本币结果。
- 后续验证指标：H.10 broad/AFE/EME dollar indexes、USD/CNY、EUR/USD、USD/JPY、10Y TIPS、FOMC statement、IMF COFER、WGC ETF flow。

## 一页汇率检查表

```text
数据日期：

报价方向：
- 这是每 1 美元兑多少外币？
- 还是每 1 外币兑多少美元？

美元背景：
- Federal funds target range：
- 10Y nominal：
- 10Y TIPS：
- Broad dollar index：

双边汇率：
- USD/CNY：
- EUR/USD：
- USD/JPY：

资产折算：
- 底层资产货币：
- 我的生活/记账货币：
- 是否有汇率对冲：
- 对冲成本和期限：

判断边界：
- 已确认事实：
- 我的推理：
- 不能确定：
- 下次要复核的数据：
```

## 个人情境连接

- 对关注清单的启发：记录海外资产时同时写下底层资产回报和汇率变化，不把两者混成一个原因。
- 对持仓或基金选择的启发：选择跨境基金时要看计价货币、底层资产货币、申赎汇率、是否汇率对冲和费用。
- 对工作、收入、消费或风险管理的启发：汇率影响进口商品、留学旅游、能源成本、外贸企业利润和跨国公司财报折算。

## 结论边界

- 可以确定：截至 2026-07-17，Fed H.10 显示 USD/CNY 为 6.7760、EUR/USD 为 1.1440、USD/JPY 为 162.4300；IMF COFER 显示 2026Q1 美元仍是全球官方外汇储备最大货币。
- 不能确定：本课不能预测美元、人民币、欧元、日元、黄金或海外股票未来走势。
- 需要继续观察：Fed、其他央行、通胀、利差、资本流、贸易数据、地缘风险、黄金 ETF flow 和储备货币份额。
- 不构成投资建议的原因：本课只解释汇率和跨资产传导，不建议买入、卖出、换汇或对冲任何资产。

## 练习题

1. Fed H.10 里 EUR/USD 和 USD/CNY 的报价方向有什么不同？
2. 用 USD/CNY = 6.7760，把 100 美元资产折算成人民币。
3. 如果美元资产上涨 5%，但美元兑人民币下跌 3%，人民币视角的近似回报会怎样变化？
4. 为什么美元强不等于所有美元资产都会上涨？
5. 选择一个跨境基金，查它是否做汇率对冲，并写出你还需要核验的三个字段。

## 学习交接

- 本课已经完成：把实际利率传导扩展到美元、汇率、资本流、黄金和海外资产折算。
- 本课最重要的一句话：跨境资产回报至少有两层，底层资产涨跌是一层，汇率折算是另一层。
- 需要复习的关键词：Exchange Rate、Base Currency、Quote Currency、USD Index、Interest-rate Differential、Capital Flow、FX Translation、Reserve Currency、Hedging、Risk Appetite。
- 还不稳定、下次要回看的地方：如何把汇率层和商品供需层结合起来读原油、能源通胀和企业成本。
- 适合下次打开仓库先读的文件：`lessons/2026-07-21-lesson-59-dollar-fx-rate-differentials-cross-asset-risk.md`

## 下节课安排

- 建议主题：第六十课：原油、能源通胀、美元与利率传导入门。
- 学习目标：理解 crude oil、Brent、WTI、inventory、OPEC+、refining margin、energy inflation、real income 和 policy reaction function 如何把商品供需连接到通胀、利率、美元和股票行业表现。
- 建议案例：使用 EIA Weekly Petroleum Status Report、EIA oil price data、OPEC monthly report、Federal Reserve FOMC statement 与 H.15，解释油价变化为什么会影响通胀预期、实际收入、央行政策和行业利润。
- 必须解释的关键词：WTI、Brent、Inventory、OPEC+、Spare Capacity、Refining Margin、Energy Inflation、Real Income、Policy Reaction Function、Pass-through。
- 下节课开始前需要联网核验的数据：EIA weekly petroleum status、EIA spot prices、OPEC monthly report、最新 FOMC statement、H.15 利率和美元 H.10。

## 来源

- Federal Reserve, Foreign Exchange Rates H.10: https://www.federalreserve.gov/releases/H10/current/default.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- IMF Data, COFER Q1 2026 data brief: https://data.imf.org/en/news/imf%20data%20brief%20july%201
- World Gold Council, Gold ETF Flows: June 2026: https://www.gold.org/goldhub/research/gold-etfs-holdings-and-flows/2026/07
