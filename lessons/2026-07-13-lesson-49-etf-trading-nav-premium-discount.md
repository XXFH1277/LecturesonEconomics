# 第四十九课：ETF 交易机制、NAV、申购赎回与溢价折价入门

## 基本信息

- 日期：2026-07-13
- 数据截至：2026-07-13 20:24（Asia/Shanghai）。ETF 机制采用 SEC Investor Bulletin；SPY 交易与 NAV 数据采用 State Street 页面显示的 2026-07-10 NAV、closing price、bid/ask midpoint、premium/discount、exchange volume 和 30-day median bid/ask spread；QQQ 交易教育材料采用 Invesco 2026-01-15 ETF guide 和 QQQ 页面截至 2026-07-13 可核验内容。
- 主题：为什么 ETF 像股票一样交易，却又围绕基金 NAV 运转；如何理解申购赎回、授权参与者、套利、溢价折价和买卖价差。
- 学习目标：理解 NAV、Market Price、IIV/IOPV、Authorized Participant、Creation Unit、Arbitrage、Premium/Discount、Bid/Ask Spread、Limit Order 和 Market Order 的入门含义；学会把 ETF 成本拆成持有成本和交易成本。
- 相关资产：ETF、SPY、QQQ、S&P 500、Nasdaq-100、二级市场交易、基金申购赎回、流动性。
- 核心来源：
  - SEC Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.sec.gov/investor/alerts/etfs.pdf
  - State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - Invesco, An investor's guide to ETFs, 2026-01-15: https://www.invesco.com/qqq-etf/en/etf-insights/a-quick-qa-on-etfs.html
  - Invesco QQQ About page: https://www.invesco.com/qqq-etf/en/about.html
  - Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经知道 ETF 是一篮子持仓和指数规则。今天的问题是：

> 如果 ETF 是一篮子股票，为什么它又能像一只股票一样在交易所随时买卖？价格又为什么不总是等于基金净值？

答案在 ETF 的两层市场结构里：普通投资者在二级市场买卖 ETF 份额；授权参与者在一级市场和基金直接做大额申购赎回。二级市场价格会围绕 NAV 波动，一级市场申购赎回和套利机制会帮助价格靠近底层资产价值，但不保证任何时候完全相等。

### 参考的教材式概念顺序

1. NAV：基金净值，基金资产减负债后除以份额。
2. Market Price：市场价格，ETF 在交易所成交的价格。
3. Bid / Ask：买价和卖价，形成买卖价差。
4. Premium / Discount：市场价格高于或低于 NAV。
5. Authorized Participant：授权参与者，通常是大型 broker-dealer，能和 ETF 直接申购赎回。
6. Creation Unit：申购赎回单位，通常是一大篮子 ETF 份额。
7. Creation / Redemption：一级市场申购和赎回机制。
8. Arbitrage：套利，利用 ETF 与底层资产之间的价格差。
9. IIV / IOPV：日内参考价值，用来估算 ETF 持仓的日内价值。
10. Order Type：委托类型，market order 和 limit order 会影响成交确定性和价格控制。

### 核心概念

ETF 有两个市场：

```text
二级市场：
普通投资者 <-> 交易所 <-> 普通投资者/做市商
价格：market price
成本：bid/ask spread、premium/discount、佣金、滑点

一级市场：
Authorized Participant <-> ETF 基金
机制：creation/redemption
价格锚：NAV 或基金规定的篮子价值
作用：帮助 ETF 市场价格贴近底层资产价值
```

普通投资者通常不能直接拿一股 ETF 去基金公司赎回底层股票。你在券商账户里买卖的是二级市场份额。只有授权参与者能按大额 creation unit 直接和基金申购赎回。

### 用自己的话解释

ETF 的 market price 像商店里的成交价，NAV 像这篮商品按当天收盘价值算出来的清单价。平时两者很接近，因为如果商店价格明显贵了，专业参与者有动力用底层股票换 ETF 再卖出；如果商店价格明显便宜了，他们有动力买入 ETF 再赎回底层股票。这个过程就是套利。

但“有套利机制”不等于“没有风险”。在市场剧烈波动、底层持仓流动性变差、跨市场时间差、债券或海外资产估值不及时、或交易拥挤时，premium/discount 和 bid/ask spread 可能变大。

### 常见误区

- 误区一：ETF market price 必然等于 NAV。SEC 明确说明 ETF shares trade at market prices that may or may not be the same as NAV。
- 误区二：费用率就是 ETF 的全部成本。交易时还要看 bid/ask spread、premium/discount、佣金和执行价格。
- 误区三：交易量低的 ETF 一定没有流动性。ETF 流动性还取决于底层持仓流动性、做市和申购赎回机制。
- 误区四：市价单永远最好。市价单执行快，但在波动或价差宽时成交价格可能偏离预期。
- 误区五：premium 一定是好事，discount 一定是坏事。它们首先说明交易价格偏离 NAV，含义要结合买入还是卖出、底层市场和流动性判断。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC Investor Bulletin 说明，ETF shares are traded on a national stock exchange and at market prices that may or may not be the same as NAV。SEC 还说明，retail investors 通常只能通过市场交易买卖 ETF；ETF sponsors 与 Authorized Participants 建立关系；只有 Authorized Participants 能直接向 ETF 申购或赎回大额 creation units，例如 50,000 ETF shares。

State Street SPY 页面显示，SPY 在 2026-07-10 的 NAV 为 754.93 美元，closing price 为 754.95 美元，bid/ask midpoint 为 754.89 美元，premium/discount 为 -0.01%，30-day median bid/ask spread 为 0.00%，primary exchange volume 为 7,748,170 shares。这个案例很适合初学者观察：大型高流动性 ETF 的 market price、midpoint 和 NAV 通常可以很接近，但页面也同时提示 ETF 可能以高于或低于 NAV 的价格交易。

Invesco 2026-01-15 ETF guide 说明，ETF 成本不只包括 expense ratio，还包括 bid/ask spreads、trading commissions、premiums and discounts。Invesco 也提示，limit orders 给投资者更多执行价格控制，但不保证成交；market orders 执行快，但在波动或价差宽时成交价格可能变化。Invesco 还给出一个交易习惯提示：通常避免在开盘和收盘附近交易 ETF，因为最初和最后 30 分钟可能更波动、价差可能更宽。

### 为什么重要

第 48 课讲的是“ETF 买了什么”。本课讲的是“ETF 份额如何成交”。这两件事必须分开：

- 持有成本：expense ratio、基金税务效率、跟踪差异。
- 交易成本：bid/ask spread、premium/discount、佣金、下单方式、交易时段。
- 结构风险：授权参与者、做市商、底层资产流动性、市场压力下的折价。

如果只看费用率，可能忽略买卖价差；如果只看成交量，可能忽略底层持仓流动性；如果只看 NAV，可能忽略自己真实成交的是 market price。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| ETF market price vs NAV | 市场价格可能不等于 NAV | SEC Investor Bulletin | 基本机制 |
| Authorized Participant | 只有 AP 通常能直接申购赎回 creation units | SEC Investor Bulletin | 一级市场机制 |
| SPY NAV | 754.93 美元 | State Street, as of 2026-07-10 | 净值锚点 |
| SPY closing price | 754.95 美元 | State Street, as of 2026-07-10 | 市场价格 |
| SPY bid/ask midpoint | 754.89 美元 | State Street, as of 2026-07-10 | 交易参考 |
| SPY premium/discount | -0.01% | State Street, as of 2026-07-10 | 偏离观察 |
| SPY 30-day median bid/ask spread | 0.00% | State Street, as of 2026-07-10 | 交易成本观察 |
| SPY exchange volume | 7,748,170 shares | State Street, as of 2026-07-10 | 二级市场流动性 |
| QQQ total expense ratio | 0.18% | Invesco performance page, accessed 2026-07-13 | 持有成本 |
| ETF trading costs | 费用率之外还要看价差、佣金、溢价折价 | Invesco ETF guide, 2026-01-15 | 总成本框架 |

### 这些现实事件如何连接理论

SPY 的 2026-07-10 数据可以写成一个最小交易观察表：

```text
ETF：SPY
NAV：754.93
Closing Price：754.95
Bid/Ask Midpoint：754.89
Premium/Discount：-0.01%
30-Day Median Bid/Ask Spread：0.00%
Exchange Volume：7,748,170 shares

初步解释：
- NAV 和 market price 很接近，说明当天收盘附近折溢价很小。
- 30-day median bid/ask spread 很窄，说明交易成本指标较低。
- 这只是某一天和某一类高流动性大盘 ETF 的观察，不能推广到所有 ETF。
```

这个表训练的是读数顺序，不是交易建议。

### 至少一个真实市场机制案例

真实机制是 creation/redemption 和 arbitrage。

如果 ETF market price 高于底层篮子价值，授权参与者可能：

```text
买入底层证券篮子
-> 向 ETF 申购 creation units
-> 获得 ETF shares
-> 在二级市场卖出 ETF shares
-> 增加 ETF 供给，压低 premium
```

如果 ETF market price 低于底层篮子价值，授权参与者可能：

```text
在二级市场买入 ETF shares
-> 向 ETF 赎回 creation units
-> 获得底层证券或现金
-> ETF 份额供给减少，discount 有机会收窄
```

这套机制的目标是让 ETF 市场价格靠近底层价值，但它依赖底层资产流动性、做市意愿、市场稳定性和交易成本。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 1940 Act 注册基金框架、ETF 招募说明书、交易所二级市场、授权参与者合同、做市和套利机制、基金披露。
- 已确认事实：ETF 机制来自 SEC Investor Bulletin；SPY 数字来自 State Street；ETF 交易成本解释来自 Invesco 教育材料；本课不使用未核验的实时买卖建议。
- 市场可能如何传导：市场压力会扩大价差和折溢价；底层持仓流动性变差会影响 ETF 交易；利率或波动率上升会改变投资者对 ETF 的交易成本敏感度。
- 仍需核验或观察：不同 ETF 的实时 premium/discount、bid/ask spread、creation unit size、底层持仓流动性、开盘/收盘附近成交质量和基金公告。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| NAV | 净资产价值 | 基金资产减负债后除以份额 | ETF 的价值锚 |
| Market Price | 市场价格 | ETF 在交易所成交的价格 | 你真正买卖的价格 |
| IIV | 日内指示价值 | 日内估算的基金持仓价值 | 辅助观察价格是否偏离 |
| IOPV | 日内组合价值 | 与 IIV 类似的日内参考价值 | ETF 特有参考指标 |
| Premium | 溢价 | 市场价格高于 NAV | 买入时可能多付 |
| Discount | 折价 | 市场价格低于 NAV | 卖出时可能吃亏 |
| Bid/Ask Spread | 买卖价差 | 卖价减买价 | 直接交易成本 |
| Authorized Participant | 授权参与者 | 能和 ETF 直接申购赎回的大型机构 | ETF 套利机制核心 |
| Creation Unit | 申购赎回单位 | 一大块 ETF 份额 | 普通投资者通常接触不到 |
| Creation | 申购 | AP 向基金交篮子换 ETF 份额 | 增加 ETF 供给 |
| Redemption | 赎回 | AP 交 ETF 份额换回篮子或现金 | 减少 ETF 供给 |
| Arbitrage | 套利 | 利用价格差交易 | 让价格接近 NAV |
| Market Order | 市价单 | 立即按市场可得价格成交 | 快但价格控制弱 |
| Limit Order | 限价单 | 设定可接受价格 | 价格控制强但不保证成交 |

## 回顾提示

- 学到本课前建议回顾：第 4 课 ETF 入门、第 47 课组合暴露、第 48 课持仓穿透和指数方法论。
- 本课哪些内容会在后续课程继续使用：基金总成本、跟踪差异、ETF 交易纪律、基金表现归因。
- 如果看不懂本课，可以先回到：第 1 课价格不是价值、第 3 课金融产品地图、第 5 课利率和流动性。

## 案例拆解

- 案例对象：SPY 的 NAV、市场价格和折溢价。
- 已确认事实：
  - SPY 2026-07-10 NAV 为 754.93 美元。
  - SPY 2026-07-10 closing price 为 754.95 美元。
  - SPY 2026-07-10 bid/ask midpoint 为 754.89 美元。
  - SPY 2026-07-10 premium/discount 为 -0.01%。
  - SPY 30-day median bid/ask spread 为 0.00%。
  - SEC 说明 ETF market price may or may not be the same as NAV；AP creation/redemption 和 arbitrage 帮助价格接近底层价值。
- 来源日期和链接：见本课“来源”。
- 分析推理：SPY 这类大型、高流动性、底层持仓主要为美国大盘股票的 ETF，收盘附近 NAV 与 market price 可能非常接近；但其他 ETF、压力市场或底层资产不流动时，偏离可能明显扩大。
- 后续验证指标：每日 NAV、closing price、bid/ask midpoint、premium/discount、30-day median spread、交易量、底层资产流动性、市场波动率和基金公告。

## 一个可复制的 ETF 交易检查页

```text
ETF：
数据截至：

持有成本：
- Expense Ratio：
- Tracking Difference：

交易成本：
- Bid/Ask Spread：
- Premium/Discount：
- 佣金：
- 下单时间：
- 下单类型：

流动性：
- ETF 交易量：
- 底层持仓流动性：
- 是否有做市支持：

结论边界：
- 已确认事实：
- 我的推理：
- 不能确定：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：观察 ETF 时同时记录持仓信息和交易信息，不要只保存收益曲线。
- 对持仓或基金选择的启发：长期持有者要重视费用率和跟踪差异；频繁交易者还要重视价差、折溢价和下单方式。
- 对工作、收入、消费或风险管理的启发：买卖成本并不总在标价里，现实生活中的汇款、换汇、保险、贷款也有显性费用和隐性价差。

## 结论边界

- 可以确定：ETF 的二级市场价格可能偏离 NAV；授权参与者和申购赎回机制有助于缩小偏离；投资者要同时看持有成本和交易成本。
- 不能确定：本课不能保证任何 ETF 在未来都保持低折溢价或窄价差，也不判断具体交易时点。
- 需要继续观察：实时 market price、NAV、IIV/IOPV、bid/ask spread、premium/discount、市场压力和底层持仓流动性。
- 不构成投资建议的原因：本课只解释 ETF 交易机制和成本结构，不建议买入、卖出、持有或配置任何基金。

## 练习题

1. 为什么普通投资者通常不能直接把 ETF 份额拿去换底层股票？
2. 用 SPY 的 2026-07-10 数据解释 market price、NAV 和 premium/discount 的关系。
3. 为什么 expense ratio 不是 ETF 的全部成本？
4. 什么情况下 limit order 可能比 market order 更适合初学者理解风险？
5. 选一个 ETF，记录它的 NAV、market price、premium/discount 和 bid/ask spread，并写明数据日期。

## 学习交接

- 本课已经完成：把第 48 课的 ETF 持仓穿透推进到 ETF 二级市场交易、NAV、申购赎回、授权参与者、套利和折溢价。
- 本课最重要的一句话：ETF 的市场价格围绕 NAV 运转，但你真实成交的是市场价格，不是课本里的净值。
- 需要复习的关键词：NAV、Market Price、IIV、IOPV、Premium、Discount、Bid/Ask Spread、Authorized Participant、Creation Unit、Arbitrage、Limit Order、Market Order。
- 还不稳定、下次要回看的地方：如何把基金表现拆成基准回报、费用、跟踪差异、行业暴露、风格暴露和主动/被动差异。
- 适合下次打开仓库先读的文件：`lessons/2026-07-13-lesson-49-etf-trading-nav-premium-discount.md`

## 下节课安排

- 建议主题：第五十课：基金表现归因、基准偏离与主动/被动差异入门。
- 学习目标：理解基金回报不能只看涨跌，要拆成 benchmark return、expense drag、tracking difference、sector allocation、security selection、style exposure 和 cash drag。
- 建议案例：可继续使用 SPY、QQQ，并加入一个主动基金或等权 ETF 作对照，但必须重新核验基金官网、招募说明书、持仓、费用率、表现、基准和数据日期。
- 必须解释的关键词：Benchmark Return、Active Return、Tracking Difference、Tracking Error、Expense Drag、Sector Allocation、Security Selection、Style Exposure、Cash Drag、Attribution。
- 下节课开始前需要联网核验的数据：基金公司官网的最新 performance、NAV return、market price return、benchmark return、expense ratio、holdings、sector weights、turnover 和相关指数方法论。

## 来源

- SEC Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.sec.gov/investor/alerts/etfs.pdf
- State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Invesco, An investor's guide to ETFs, 2026-01-15: https://www.invesco.com/qqq-etf/en/etf-insights/a-quick-qa-on-etfs.html
- Invesco QQQ About page: https://www.invesco.com/qqq-etf/en/about.html
- Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html
