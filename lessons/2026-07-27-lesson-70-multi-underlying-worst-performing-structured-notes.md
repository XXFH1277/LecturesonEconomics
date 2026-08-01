# 第七十课：多标的结构化票据与最差表现风险入门：篮子、相关性、单一标的事件与分散化错觉

## 基本信息

- 日期：2026-07-27
- 数据截至：2026-07-27（Asia/Shanghai）；归档复核：2026-08-01。结构化票据案例采用 SEC EDGAR 2026-07-10 Jefferies final pricing supplement，并以 SEC EDGAR 2026-07-25 BNS preliminary pricing supplement 作为 memory coupon 识别补充；Federal Reserve H.15 已复核至 2026-07-31 发布、数据截至 2026-07-30；Nasdaq-100 与 S&P 500 官方页面采用 2026-07-24 数据；Russell 2000 采用 LSEG/FTSE Russell 当前可访问说明。
- 主题：为什么多标的结构化票据不是“更分散”，而常常是“最弱一环决定结果”。
- 学习目标：理解 worst-performing、basket note、correlation、single-index event risk、single-stock event risk、coupon barrier、call value、threshold value、memory coupon、non-call period、issuer call risk 和 scenario tree。
- 相关资产：Jefferies Financial Group Inc. 结构化票据、Nasdaq-100 Index、Russell 2000 Index、S&P 500 Index、BNS 预备条款、短端美债利率。
- 核心来源：
  - SEC EDGAR, Jefferies Financial Group Inc., Senior Autocallable Contingent Coupon Barrier Notes due July 15, 2032 Linked to the Worst-Performing of the Nasdaq-100 Index, Russell 2000 Index and S&P 500 Index, Pricing Supplement dated 2026-07-10: https://www.sec.gov/Archives/edgar/data/96223/000114036126028453/ef20077971_424b2.htm
  - SEC EDGAR, The Bank of Nova Scotia, Contingent Income Auto-Callable Securities based on the worst performing of AMZN, GOOGL and MSFT, Preliminary Pricing Supplement dated 2026-07-25: https://www.sec.gov/Archives/edgar/data/9631/000183988226031066/bns_424b2-20484.htm
  - SEC Investor.gov, Investor Bulletin: Structured Notes, 2015-01-12: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
  - FINRA, Understanding Structured Notes With Principal Protection, 2023-04-12: https://www.finra.org/investors/insights/structured-notes-principal-protection
  - FINRA Regulatory Notice 12-03, Heightened Supervision of Complex Products, 2012-01-17: https://www.finra.org/rules-guidance/notices/12-03
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-31: https://www.federalreserve.gov/releases/h15/
  - Nasdaq, Nasdaq-100 Index overview, data as of 2026-07-24: https://indexes.nasdaq.com/Index/Overview/NDX
  - S&P Dow Jones Indices, S&P 500 official index page, data as of 2026-07-24: https://www.spglobal.com/spdji/en/indices/equity/sp-500/
  - LSEG / FTSE Russell, Russell 2000 Index official page: https://www.lseg.com/en/ftse-russell/indices/russell-2000-index

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课学习了单一标的自动赎回票据。今天先问：

```text
如果一张票据挂钩三个指数或三只股票，是不是比挂钩一个标的更分散、更安全？
```

答案通常不是。很多结构化票据写的是 `worst-performing`，也就是“最差表现标的”。这类票据不是把三个标的平均起来，而是看其中表现最差的一个。只要有一个标的低于票息线、赎回线或本金风险线，整个票据的现金流就可能受影响。

### 参考的教材式概念顺序

1. Basket：篮子，一组股票、指数、商品或其他参考资产。
2. Basket Average：篮子平均表现，多个标的按权重合成一个结果。
3. Worst-Performing / Least-Performing：最差表现标的，以表现最弱的一项决定结果。
4. Correlation：相关性，多个标的同涨同跌的程度。
5. Coupon Barrier：票息障碍，决定某期是否支付票息。
6. Call Value：自动赎回线，决定产品是否提前结束。
7. Threshold Value：阈值，决定到期本金风险是否启动。
8. Non-Call Period：不可赎回期，发行人或条款在此之前不会触发自动赎回。
9. Memory Coupon：记忆票息，未来条件满足时可能补付此前未付的条件票息。
10. Scenario Tree：情景树，把每个观察日、每条价格线和每种付款路径画出来。

### 核心概念

多标的 worst-performing 票据的核心不是“有很多资产”，而是：

```text
票息：通常要求所有标的都在 coupon barrier 以上。
赎回：通常要求最差标的也回到 call value 以上。
到期本金：如果最差标的跌破 threshold value，本金风险启动。
```

这和普通分散化很不一样。普通组合里，一个资产跌、另一个资产涨，平均结果可能被缓冲。但 worst-performing 结构里，最差的那个标的会成为付款公式的关键。

### 用自己的话解释

假设一张票据挂钩 A、B、C 三个指数，每月观察一次：

```text
A 涨 10%，B 涨 5%，C 跌 35%
-> 最差表现是 C
-> 票据按 C 判断
-> A 和 B 的上涨不一定能抵消 C 的下跌
```

如果条款要求“每个标的都不低于 70% 初始值才付票息”，那么只要 C 跌到 69%，即使 A 和 B 很强，当期也可能没有票息。

### 常见误区

- 误区一：标的越多越分散。只有平均型或组合型结构才可能接近分散化；worst-performing 结构更像“多个门，每个门都要过”。
- 误区二：三个指数都很主流，所以风险低。主流指数也会有不同风格：Nasdaq-100 偏成长与科技，Russell 2000 偏小盘，S&P 500 偏美国大盘。
- 误区三：相关性高就没有最差表现风险。相关性高时可能一起跌；相关性低时更容易出现一个明显落后者。两种情况都要用情景树看。
- 误区四：只要本金线是 70%，最多亏 30%。很多 barrier 结构不是 buffer；跌破阈值后可能按最差标的从初始值起承担 1:1 下行风险。
- 误区五：自动赎回总是好事。提前赎回可能停止后续票息，也让投资者面对再投资风险。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC EDGAR 上 Jefferies Financial Group Inc. 2026-07-10 pricing supplement 显示，该产品是 Senior Autocallable Contingent Coupon Barrier Notes，2026-07-10 定价，2026-07-15 发行，若未提前赎回，到期日为 2032-07-15。票据挂钩 Nasdaq-100 Index、Russell 2000 Index 和 S&P 500 Index 的 worst-performing underlying。

该文件披露，票据本金总额为 6,035,000 美元，每张票据本金 1,000 美元，公开发行价为本金的 100%。每月 contingent coupon payment 为 8.33 美元，但只有在相关观察日最差表现指数的 observation value 不低于其 coupon barrier 时才支付。自动赎回观察日从 2027-01-11 开始，如果最差表现指数不低于 call value，票据会自动赎回，投资者收到本金加当期可能应付票息，之后不再付款。

Jefferies 文件给出的三项初始值分别为：NDX 29,825.11、RTY 2,977.805、SPX 7,575.39。coupon barrier 和 threshold value 都是各自初始值的 70%：NDX 20,877.58、RTY 2,084.464、SPX 5,302.77。call value 是各自初始值的 100%。文件还披露估计价值为每张 964.30 美元，公开发行价为每张 1,000 美元，承销折扣和佣金为 3.10%，不上市交易，所有付款取决于 Jefferies 的信用风险。

为了识别 memory coupon，SEC EDGAR 上 BNS 2026-07-25 preliminary pricing supplement 也有教学价值。它不是 final pricing supplement，具体条款仍可能改变，因此本课只把它作为“如何识别记忆票息字段”的实时补充。该预备文件写明，若某期因任一标的低于 coupon threshold 而未付条件票息，未来某个观察日若所有标的重新回到各自 coupon threshold 以上，之前未付的 contingent quarterly coupons 可能补付。

实时市场背景方面，Federal Reserve H.15 2026-07-31 release 显示，截至 2026-07-30，effective federal funds rate 为 3.63%，4-week Treasury bill secondary market rate 为 3.64%，3-month Treasury bill secondary market rate 为 3.69%，10-year Treasury constant maturity 为 4.68%。这些数字提供了现金和美债收益率背景，帮助理解为什么结构化票据的条件票息不能直接和无风险利率画等号。

Nasdaq 官方页面显示，Nasdaq-100 Index 数据截至 2026-07-24，指数为 28,128.34；页面说明 Nasdaq-100 包含 100 家在 Nasdaq 上市的大型非金融公司。S&P Dow Jones Indices 官方页面显示，S&P 500 数据截至 2026-07-24，Price Return 指数为 7,411.98，并说明该指数覆盖约 80% 的可投资市值。LSEG/FTSE Russell 页面说明 Russell 2000 衡量约 2,000 家美国小盘股表现。

### 为什么重要

Jefferies 案例把多标的结构的关键点压缩在一张表里：

```text
三个指数：NDX、RTY、SPX
判断方式：worst-performing
票息线：各自初始值的 70%
赎回线：各自初始值的 100%
本金风险线：各自初始值的 70%
票息：每月 8.33 美元 per 1,000 principal，条件满足才支付
退出：不上市，二级市场不保证
```

初学者应该先问“是否要求所有标的都满足条件”，再看票息数字。如果答案是是，这张票据的风险入口就不是平均收益，而是最弱标的。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| 发行人 | Jefferies Financial Group Inc. | SEC EDGAR, 2026-07-10 | 发行人信用 |
| 本金规模 | 6,035,000 美元 | SEC EDGAR, 2026-07-10 | 产品规模 |
| 定价日 / 发行日 / 到期日 | 2026-07-10 / 2026-07-15 / 2032-07-15 | SEC EDGAR, 2026-07-10 | 时间线 |
| 挂钩标的 | NDX、RTY、SPX 中最差表现者 | SEC EDGAR, 2026-07-10 | worst-performing 结构 |
| 每月条件票息 | 8.33 美元 per 1,000 principal | SEC EDGAR, 2026-07-10 | 现金流 |
| 初始值 | NDX 29,825.11；RTY 2,977.805；SPX 7,575.39 | SEC EDGAR, 2026-07-10 | 条款基准 |
| Coupon barrier / threshold | 均为各自初始值 70% | SEC EDGAR, 2026-07-10 | 票息和本金风险线 |
| Call value | 各自初始值 100% | SEC EDGAR, 2026-07-10 | 自动赎回线 |
| Estimated value | 964.30 美元 per note | SEC EDGAR, 2026-07-10 | 发行价和价值差异 |
| Listing | None | SEC EDGAR, 2026-07-10 | 流动性 |
| EFFR / 4-week T-Bill / 10Y Treasury | 3.63% / 3.64% / 4.68% | Fed H.15, 2026-07-30 | 利率背景 |
| Nasdaq-100 | 28,128.34 | Nasdaq, 2026-07-24 | 参考指数背景 |
| S&P 500 | 7,411.98 | S&P DJI, 2026-07-24 | 参考指数背景 |

### 这些现实事件如何连接理论

第一条链：最差表现逻辑。

```text
三个指数各自有初始值
-> 每次观察都计算每个指数相对初始值的表现
-> 选择表现最差的指数
-> 用最差者判断票息、赎回和到期本金
```

第二条链：相关性与风格差异。

```text
NDX 偏大型科技和成长
SPX 偏美国大盘
RTY 偏美国小盘
-> 风格不同会带来不同回撤路径
-> 只要一个风格明显落后，worst-performing 结构就会被拖住
```

第三条链：利率背景。

```text
短端利率提供现金收益参照
-> 条件票息看起来更高
-> 投资者实际换来的是发行人信用、最差标的、流动性和提前赎回风险
```

### 至少一个真实市场机制案例

案例：Jefferies 三指数 worst-performing 自动赎回票据。

把每 1,000 美元本金画成一棵情景树：

```text
每月 coupon observation date：
NDX、RTY、SPX 的观察值都 >= 各自 70% coupon barrier
-> 支付 8.33 美元条件票息

只要其中一个指数 < 各自 70% coupon barrier
-> 当期不支付条件票息

从 2027-01-11 开始的 call observation date：
NDX、RTY、SPX 的观察值都 >= 各自 100% call value
-> 自动赎回，支付本金 1,000 美元 + 当期可能应付票息，票据结束

如果未提前赎回并持有到 2032-07-12 valuation date：
最差表现指数 >= 70% threshold value
-> 到期返还本金 1,000 美元，最终票息还要看最终观察日是否满足 coupon barrier

最差表现指数 < 70% threshold value
-> 到期付款低于本金，可能损失部分或全部本金
```

这棵树说明，多标的不是自动分散风险，而是增加了需要同时满足的条件数量。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC EDGAR 证券披露、FINRA 复杂产品监管提示、经纪商适当性、承销利益冲突、指数许可与方法论披露、非上市结构化票据的二级市场安排。
- 已确认事实：SEC Investor.gov 把结构化票据定义为由金融机构发行、回报基于参考资产、包含债券组成部分和嵌入式衍生品的证券；FINRA 说明 worst-performing reference asset 可以用于结构化产品付款公式；FINRA Notice 12-03 提醒带有复杂衍生品特征的产品需要更高监督。
- 市场可能如何传导：指数波动、利率、信用利差和发行人对冲成本会影响新票据条款；若科技成长、小盘或大盘出现明显分化，最差表现结构会把分化放大到现金流层面。
- 仍需核验或观察：每个观察日的 NDX、RTY、SPX 官方收盘值，Jefferies 信用状态，二级市场报价，是否触发票息或自动赎回，以及投资者实际税务处理。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Worst-Performing | 最差表现标的 | 多个标的里跌得最多或相对初始值表现最弱的一个 | 决定票息、赎回和本金风险 |
| Basket Note | 篮子票据 | 挂钩多个参考资产的票据 | 先判断是平均篮子还是最差表现 |
| Basket Average | 篮子平均 | 按权重合成多个标的的平均表现 | 与 worst-performing 风险不同 |
| Correlation | 相关性 | 多个资产同涨同跌的程度 | 影响最弱一环出现的路径 |
| Coupon Barrier | 票息障碍 | 支付条件票息所需的最低水平 | 低于它可能没有票息 |
| Call Value | 赎回触发值 | 达到后可能自动赎回 | 影响期限和再投资风险 |
| Threshold Value | 阈值 | 到期本金风险启动线 | 跌破后可能亏本金 |
| Non-Call Period | 不可赎回期 | 自动赎回开始前的时间 | 决定最早什么时候结束 |
| Memory Coupon | 记忆票息 | 后续满足条件时补付之前未付票息 | 看起来补偿，但仍有条件 |
| Single-Index Event Risk | 单一指数事件风险 | 一个指数因风格或成分暴露落后 | 会拖累整个 worst-of 结构 |
| Single-Stock Event Risk | 单一股票事件风险 | 单只股票因财报、监管或公司事件暴跌 | 多股票 worst-of 产品尤其敏感 |
| Issuer Call Risk | 发行人赎回风险 | 条款有利于发行人时产品可能提前结束 | 投资者上行和票息期数受限 |
| Scenario Tree | 情景树 | 把每个观察日和付款条件画出来 | 防止只看票息数字 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和信用风险，第 49 课 ETF 交易机制，第 64-65 课期权和 Greeks，第 68-69 课结构化票据与自动赎回票据。
- 本课哪些内容会在后续课程继续使用：相关性、最弱一环、复杂产品适当性、指数方法论、estimated value、secondary market liquidity。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图和第 8 课衍生工具入门，先分清“拥有资产”和“持有条件付款合同”。

## 案例拆解

- 案例对象：Jefferies 2026-07-10 三指数 worst-performing 自动赎回票据。
- 已确认事实：
  - 发行人为 Jefferies Financial Group Inc.，票据为 senior unsecured obligations。
  - 挂钩 NDX、RTY、SPX 中的 worst-performing underlying。
  - 每月条件票息为 8.33 美元 per 1,000 principal。
  - coupon barrier 和 threshold value 都是各自初始值的 70%。
  - call value 是各自初始值的 100%，call observation dates 从 2027-01-11 开始。
  - estimated value 为 964.30 美元，低于 1,000 美元发行价。
  - 不上市交易，Jefferies 子公司可能做二级市场，但文件说明并无义务持续做市。
- 来源日期和链接：见本课“来源”。
- 分析推理：该票据的经济含义不是“同时买入三个指数”，而是“把三个指数都放进付款条件，最差者控制结果”。
- 后续验证指标：每个观察日 NDX、RTY、SPX 的官方收盘值、Jefferies 信用利差或债务披露、二级市场报价、是否发生自动赎回。

## 个人情境连接

- 对关注清单的启发：凡是看到“linked to multiple assets”，先新增一列“payoff uses average or worst-performing?”。
- 对持仓或基金选择的启发：基金或账户持有 ELN/结构化票据时，不能只看发行人和票息，还要穿透到每个参考资产和付款公式。
- 对工作、收入、消费或风险管理的启发：多条件合同常见于商业世界。看似多来源收入，也可能被一个关键条件卡住，学习 worst-performing 能训练条件约束思维。

## 结论边界

- 可以确定：worst-performing 结构由最差标的影响付款；多标的不等于平均分散；Jefferies 案例的 coupon barrier、call value、threshold value、estimated value、listing 和信用风险均已披露。
- 不能确定：本课不能预测 NDX、RTY、SPX 的未来表现，不能预测 Jefferies 信用变化，也不能预测该票据是否支付票息或自动赎回。
- 需要继续观察：指数收盘值、利率、信用利差、观察日结果、二级市场报价和税务处理。
- 不构成投资建议的原因：本课只解释结构化票据读表和风险边界，不建议买入、卖出或持有任何票据、股票、ETF、基金、债券或衍生品。

## 练习题

1. 用一句话区分“篮子平均型票据”和“worst-performing 票据”。
2. 如果 NDX、RTY、SPX 中只有 RTY 跌破 coupon barrier，为什么整个票据当期可能没有票息？
3. 为什么 estimated value 低于 issue price 是读表时必须记录的信息？
4. 相关性高和相关性低分别会怎样影响 worst-performing 结构的风险？
5. 打开一份多标的 424B2 文件，找出 issuer、underlyings、coupon barrier、call value、threshold value、estimated value 和 listing。

## 学习交接

- 本课已经完成：把多标的结构化票据从“多个资产更分散”的直觉，拆成 worst-performing、coupon barrier、call value、threshold value、correlation、memory coupon 和 scenario tree。
- 本课最重要的一句话：worst-performing 结构不是看平均成绩，而是让最差的那个标的控制关键付款。
- 需要复习的关键词：Worst-Performing、Basket Note、Correlation、Coupon Barrier、Call Value、Threshold Value、Memory Coupon、Non-Call Period、Issuer Call Risk、Scenario Tree。
- 还不稳定、下次要回看的地方：复杂指数挂钩票据里的 decrement、volatility target、futures excess return、TCA 和 back-tested performance 如何改变“看起来挂钩 S&P 500”的直觉。
- 适合下次打开仓库先读的文件：`lessons/2026-07-27-lesson-70-multi-underlying-worst-performing-structured-notes.md`

## 下节课安排

- 建议主题：第七十一课：Decrement Index 与复杂指数挂钩票据入门：波动率目标、期货超额收益、费用拖累与回测边界。
- 学习目标：理解 decrement index、excess return index、volatility target、leverage cap、transaction cost adjustment、implicit financing cost、decay effect、back-tested performance、index sponsor 和 material modification event。
- 建议案例：使用 Citigroup 2026-04-27 挂钩 S&P 500 Futures 40% Intraday Edge Volatility TCA 6% Decrement Index 的自动赎回条件票息票据，拆解为什么“挂钩 S&P 500 futures decrement index”不等于“买 S&P 500”。
- 必须解释的关键词：Decrement Index、Excess Return、Volatility Target、TCA、Implicit Financing Cost、Decay Effect、Back-Tested Performance、Index Sponsor、Calculation Agent、Material Modification Event。
- 下节课开始前需要联网核验的数据：Citigroup final pricing supplement、S&P DJI decrement index 官方页面、Citigroup index supplement、Fed H.15 最新利率、S&P 500 官方页面和 SEC/FINRA 复杂产品材料。

## 来源

- SEC EDGAR, Jefferies Financial Group Inc. 2026-07-10 Pricing Supplement: https://www.sec.gov/Archives/edgar/data/96223/000114036126028453/ef20077971_424b2.htm
- SEC EDGAR, The Bank of Nova Scotia 2026-07-25 Preliminary Pricing Supplement: https://www.sec.gov/Archives/edgar/data/9631/000183988226031066/bns_424b2-20484.htm
- SEC Investor.gov, Investor Bulletin: Structured Notes: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-76
- FINRA, Understanding Structured Notes With Principal Protection: https://www.finra.org/investors/insights/structured-notes-principal-protection
- FINRA Regulatory Notice 12-03: https://www.finra.org/rules-guidance/notices/12-03
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Nasdaq, Nasdaq-100 Index: https://indexes.nasdaq.com/Index/Overview/NDX
- S&P Dow Jones Indices, S&P 500: https://www.spglobal.com/spdji/en/indices/equity/sp-500/
- LSEG / FTSE Russell, Russell 2000 Index: https://www.lseg.com/en/ftse-russell/indices/russell-2000-index
