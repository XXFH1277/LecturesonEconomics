# 第六十四课：期权入门：看涨、看跌、权利金、时间价值与保护性结构

## 基本信息

- 日期：2026-07-24
- 数据截至：2026-07-24（Asia/Shanghai）。EIA Weekly Petroleum Status Report 最新可用版本为 2026-07-22 发布、截至 2026-07-17 的周度数据；EIA WTI 现货价格最新可用点为 2026-07-20；Federal Reserve H.15 最新发布日为 2026-07-23、截至 2026-07-22；SEC Investor.gov 期权入门公告更新于 2026-07-16；CME、CFTC、OCC/OIC 页面采用当前可访问版本。
- 主题：为什么期权不是“更便宜的期货”，而是用权利金购买不对称风险结构。
- 学习目标：理解 call、put、premium、strike price、expiration、intrinsic value、time value、moneyness、protective put、covered call 和 futures option。
- 相关资产：WTI crude oil futures、WTI Crude Oil options、WTI weekly options、Micro WTI options、原油期货类 ETP、航空燃油成本、能源企业套保、现金和短端利率。
- 核心来源：
  - SEC Investor.gov, Investor Bulletin: An Introduction to Options, updated 2026-07-16: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-63
  - CFTC, Futures Glossary: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CFTCGlossary/index.htm
  - CME Group, Crude Oil Options Contract Specs: https://www.cmegroup.com/markets/energy/crude-oil/light-sweet-crude.contractSpecs.options.html
  - CME Group, Energy Options: https://www.cmegroup.com/markets/energy/energy-options.html
  - EIA, Weekly Petroleum Status Report, release date 2026-07-22: https://www.eia.gov/petroleum/supply/weekly/
  - EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-23: https://www.federalreserve.gov/releases/h15/
  - OCC/OIC, About The Options Industry Council: https://www.optionseducation.org/abouttheoptionsindustrycouncil/about-oic

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲到原油期货类 ETP 和杠杆产品。今天进入期权，先问一个最简单的问题：

> 如果我担心未来油价上涨，但又不想像期货那样承担线性盈亏，能不能买一种“有权利、但不一定必须执行”的工具？

这就是期权的直觉入口。期权不是免费保险，也不是稳赚工具。它更像一份带价格、期限和条件的权利合同：买方先付 premium（权利金），获得在特定时间内按 strike price（行权价）买入或卖出标的的权利；卖方收取权利金，但承担被行权时履约的义务。

SEC Investor.gov 对期权的入门定义强调：期权给持有人在未来指定日期之前或当日，以固定价格买入或卖出标的资产的权利；期权是 derivative（衍生品），价值来自底层资产。CFTC 词汇表也把 option 解释为买方拥有权利但没有义务的合约，并把 futures option 定义为期货合约上的期权。

### 参考的教材式概念顺序

1. Underlying：标的资产，期权价值依附的股票、ETF、期货或商品。
2. Call Option：看涨期权，买方拥有买入标的或进入多头期货头寸的权利。
3. Put Option：看跌期权，买方拥有卖出标的或进入空头期货头寸的权利。
4. Premium：权利金，买方向卖方支付的期权价格。
5. Strike Price：行权价，未来按这个价格买入或卖出标的。
6. Expiration：到期日，权利有效期的终点。
7. Intrinsic Value：内在价值，如果马上行权已经有利的部分。
8. Time Value：时间价值，权利金中超过内在价值的部分。
9. Moneyness：实值、平值、虚值，描述标的价格和行权价的相对位置。
10. Exercise：行权，把权利变成底层资产或期货头寸。
11. Assignment：指派，期权卖方被要求履约。
12. Protective Put：保护性看跌，持有标的同时买 put，用权利金换下行保护。
13. Covered Call：备兑看涨，持有标的同时卖 call，用上行让渡换取权利金收入。

### 核心概念

期货和期权最关键的差别是盈亏结构：

```text
期货：价格涨跌几乎线性影响多头和空头
期权买方：先付权利金，最大损失通常从权利金开始理解
期权卖方：收取权利金，但承担履约义务，风险可能明显大于收到的权利金
```

看涨期权的直觉是“我想保留未来买入的权利”；看跌期权的直觉是“我想保留未来卖出的权利”。这两个工具既可以用于投机，也可以用于套保。

对原油学习来说，要特别注意：WTI options 通常不是让你直接拿到家用油桶，而是围绕 WTI futures 的期权体系。CME 能源期权页面列出 WTI Crude Oil options 的 Globex code 为 LO，并列出 Monday、Tuesday、Wednesday、Thursday、Friday weekly options 等短期限产品。CME WTI options 页面也把 WTI futures and options 放在同一套原油价格发现与风险管理产品中。

### 用自己的话解释

假设一家航空公司担心三个月后燃油成本上涨。用期货对冲，价格上涨时保护更直接，但价格下跌时也可能失去低价好处，并且有保证金和每日盯市压力。用 call option 或类似期权结构，它先付一笔权利金，保留未来以某个价格获得油价上行保护的权利。油价没涨到需要保护的程度时，权利可能不用执行，但权利金已经花掉。

所以期权不是“便宜版期货”，而是把风险形状改了：

```text
期货：少付初始现金，但每日盯市，线性风险
买入期权：先付权利金，保留不对称权利
卖出期权：先收权利金，承担被行权义务
```

### 常见误区

- 误区一：期权买方风险一定小。买方可能亏掉全部权利金；如果频繁买入高权利金期权，长期成本可能很高。
- 误区二：期权卖方只是“收租”。卖方承担履约义务，某些卖方风险可能远大于收到的权利金。
- 误区三：虚值期权便宜就划算。便宜通常意味着需要更大的价格移动或更高波动才可能有价值。
- 误区四：到期还远就安全。时间越长通常权利金越高；而且标的、波动率、利率和流动性都可能变。
- 误区五：保护性结构等于没有亏损。保护性 put 只能保护某个价格以下的一部分风险，权利金、行权价、期限和基差都会影响最终效果。

## 第二大板块：实时背景与市场传导

### 发生了什么

EIA 2026-07-22 WPSR 显示，截至 2026-07-17 当周，美国商业原油库存为 411.7 million barrels，较前周增加 2.0 million barrels，仍比 2021-2025 年同期五年均值低 6%；汽油库存增加 0.8 million barrels，馏分油库存增加 1.4 million barrels。EIA 同日的简报还显示，美国炼厂开工率为 96.1%，四周平均 total product demand 为 20.4 million b/d，jet fuel demand 同比增加 9%。

EIA WTI 现货价格页显示，WTI-Cushing 在 2026-07-20 为 84.38 美元/桶；同页日度序列显示，2026-07-06 为 69.60 美元/桶，2026-07-17 为 83.43 美元/桶。这段快速上行背景说明：当标的价格、库存、地缘风险或运输燃料需求变化较快时，期权的“价格方向”和“保护期限”会同时变得重要。

Federal Reserve H.15 2026-07-23 release 显示，截至 2026-07-22，effective federal funds rate 为 3.63%，4-week Treasury bill secondary market rate 为 3.65%，10-year Treasury constant maturity 为 4.67%，10-year TIPS yield 为 2.39%。利率不是原油期权的唯一变量，但会影响现金抵押品收益、远期定价、折现和跨资产风险偏好。

CME 能源期权页面列出 WTI Crude Oil options、WTI weekly options 和 Micro WTI Crude Oil options，说明原油期权已经不是单一到期月份的工具，而是一套不同合约规模和期限的风险管理菜单。

### 为什么重要

期权让我们把“油价会涨还是跌”拆成更细的问题：

```text
我担心涨，还是担心跌？
我想保护多长时间？
我愿意先付多少权利金？
我保护的是现货、期货、企业成本，还是基金/ETP 净值？
我能不能承受卖出期权后的履约义务？
```

如果只看油价方向，就会把期权当成彩票；如果同时看期限、行权价、权利金、内在价值、时间价值和基差，期权才会变成风险管理工具。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| WPSR 最新周度数据 | week ending 2026-07-17，release date 2026-07-22 | EIA | 原油库存背景 |
| 商业原油库存 | 411.7 million barrels，周增 2.0 million barrels | EIA, 2026-07-22 | 标的市场背景 |
| 炼厂开工率 | 96.1% | EIA, 2026-07-22 | 成品油需求与风险 |
| Jet fuel demand | 四周平均同比增加 9% | EIA, 2026-07-22 | 航空燃油案例 |
| WTI-Cushing | 84.38 美元/桶 | EIA, 2026-07-20 | 教学价格锚 |
| 4-week T-Bill | 3.65% | Fed H.15, 2026-07-22 | 短端现金收益背景 |
| 10Y nominal CMT | 4.67% | Fed H.15, 2026-07-22 | 折现率背景 |
| 10Y TIPS yield | 2.39% | Fed H.15, 2026-07-22 | 实际利率背景 |
| WTI options product set | LO、weekly options、Micro WTI options | CME Group | 期权产品菜单 |
| Options definition | 权利而非义务；call/put、premium、strike、expiration | SEC Investor.gov、CFTC | 概念核验 |

### 这些现实事件如何连接理论

第一条链：标的价格和权利金。

```text
WTI 现货和期货价格快速变化
-> 期权买方更看重保护或方向表达
-> 卖方要求通过权利金补偿风险
-> 同样行权价的期权价格会随标的、期限和波动预期改变
```

第二条链：库存和运输燃料。

```text
商业原油库存、汽油库存、馏分油库存和炼厂开工变化
-> 市场重新评估供需紧张程度
-> 航空、炼化、运输和能源企业面临不同价格风险
-> 期权可以把一部分线性风险改成保护型或收入型结构
```

第三条链：利率和现金。

```text
短端利率影响现金和保证金收益
-> 期货/期权组合的现金管理成本变化
-> 长端利率影响通胀、美元和风险偏好
-> 原油期权不能脱离宏观背景理解
```

### 至少一个真实市场机制案例

案例：WTI call option 如何像“上行成本保险”。

假设某企业担心未来三个月油价上行。它可以买入与 WTI futures 相关的 call option。这样做的直觉是：

```text
如果油价大幅上行：
call 的价值可能上升，用来抵消部分采购成本压力

如果油价没有上行：
call 可能到期无价值，企业损失权利金，但仍可享受较低现货采购价格
```

这和直接买入期货不同。期货多头在油价上涨时受益，但油价下跌时也会线性亏损；买入 call 的损失从权利金开始理解，但权利金本身就是确定成本。对企业来说，问题不是“哪一种一定赚”，而是“哪一种更适合预算、现金流、会计和基差风险”。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 投资者教育、CFTC 期货与期权词汇、CME/NYMEX 合约和清算制度、OCC/OIC 期权教育、EIA 能源统计、Fed 利率数据。
- 已确认事实：SEC 和 CFTC 都把期权定义为权利而非义务；CFTC 明确 option writer 因收取 premium 而承担履约义务；CME 列出 WTI Crude Oil options 与多种 weekly options；EIA 最新 WPSR 确认原油库存、炼厂开工和成品油需求背景。
- 市场可能如何传导：库存和油价影响期权标的；波动预期影响权利金；利率影响现金管理；监管和交易所规则影响合约、保证金、行权和披露。
- 仍需核验或观察：CME 最新具体到期合约、strike listing、结算价、隐含波动率、保证金、企业是否采用期权套保、相关财报中的 derivative risk disclosures。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Underlying | 标的资产 | 期权依附的股票、ETF、期货或商品 | 先判断风险来源 |
| Call Option | 看涨期权 | 买方拥有按行权价买入或进入多头的权利 | 管理上涨风险 |
| Put Option | 看跌期权 | 买方拥有按行权价卖出或进入空头的权利 | 管理下跌风险 |
| Premium | 权利金 | 买方支付、卖方收取的期权价格 | 保护不是免费的 |
| Strike Price | 行权价 | 未来买卖标的的约定价格 | 决定保护层级 |
| Expiration | 到期日 | 权利有效期终点 | 时间决定价值 |
| Intrinsic Value | 内在价值 | 立即行权已有利的部分 | 区分真实保护 |
| Time Value | 时间价值 | 权利金超过内在价值的部分 | 体现未来可能性 |
| Moneyness | 实值/平值/虚值状态 | 标的价格和行权价的相对关系 | 判断期权位置 |
| Exercise | 行权 | 把期权权利变成底层头寸 | 到期和履约核心 |
| Assignment | 指派 | 卖方被要求履约 | 卖方风险核心 |
| Futures Option | 期货期权 | 以期货合约为标的的期权 | WTI 期权重点 |
| Protective Put | 保护性看跌 | 持有标的同时买 put | 下行保护结构 |
| Covered Call | 备兑看涨 | 持有标的同时卖 call | 收入与上行让渡 |

## 回顾提示

- 学到本课前建议回顾：第 8 课衍生工具入门、第 62 课期货保证金和套保、第 63 课原油期货类 ETP。
- 本课哪些内容会在后续课程继续使用：隐含波动率、Greeks、Delta 对冲、组合保护、卖方风险、结构化产品和基金风险披露。
- 如果看不懂本课，可以先回到：第 1 课机会成本，第 5 课利率，第 60 课原油与通胀传导。

## 案例拆解

- 案例对象：WTI Crude Oil options 与企业燃油成本风险。
- 已确认事实：
  - CME 列出 WTI Crude Oil options、WTI weekly options 和 Micro WTI options。
  - EIA 2026-07-22 WPSR 显示商业原油库存为 411.7 million barrels，炼厂开工率为 96.1%。
  - EIA WTI 现货页显示 2026-07-20 WTI-Cushing 为 84.38 美元/桶。
  - SEC 和 CFTC 的期权定义都强调买方权利和卖方义务。
- 来源日期和链接：见本课“来源”。
- 分析推理：当标的价格和库存背景快速变化时，期权可以把单纯方向判断改成“保护价格、保护期限和权利金成本”的组合问题。
- 后续验证指标：CME WTI option settlement、implied volatility、strike listing、open interest、EIA 下一期 WPSR、企业 10-K/10-Q 中的 derivative disclosures。

## 一页保护性期权结构检查表

```text
保护对象：
- 原油采购成本、能源基金、股票持仓，还是公司利润率：

标的匹配：
- 现货、WTI futures、Brent futures、ULSD、jet fuel 还是 ETF：
- 是否有基差风险：

期权结构：
- 买 call、买 put、卖 covered call，还是组合：
- 行权价：
- 到期日：
- 权利金：

风险边界：
- 最大可接受权利金成本：
- 若到期虚值，是否能接受权利金归零：
- 若卖出期权，是否能承受被指派：
- 是否需要保证金或现金缓冲：

复核数据：
- 标的价格：
- 期货曲线：
- 隐含波动率：
- 成交量与未平仓：
- 官方合约规则和风险披露：
```

## 个人情境连接

- 对关注清单的启发：记录期权时不要只写 call/put，要同时写标的、行权价、到期日、权利金、目标和最坏情景。
- 对持仓或基金选择的启发：含期权策略的基金、备兑策略 ETF、商品期权产品和普通现货/股票基金不是同一种风险。
- 对工作、收入、消费或风险管理的启发：期权思维的核心不是“押涨跌”，而是为不确定事件定价，知道自己愿意花多少钱买保护。

## 结论边界

- 可以确定：期权买方获得权利但不承担必须行权的义务；权利金、行权价、到期日、内在价值和时间价值是入门五件套；原油期权可以服务于方向表达和风险管理。
- 不能确定：本课不能预测 WTI、Brent、能源股、航空股、期权权利金或任何具体合约未来涨跌。
- 需要继续观察：最新 CME WTI option settlement、CME CVOL、EIA WPSR、WTI futures curve、企业套保披露和成交流动性。
- 不构成投资建议的原因：本课只解释期权基础和风险结构，不建议买入、卖出或持有任何期权、期货、股票、基金或商品产品。

## 练习题

1. 用一句话解释 call 和 put 的区别。
2. 为什么买入期权的最大风险不能简单说成“风险很小”，而应该说“权利金可能全部损失”？
3. 如果 WTI 现货约 84 美元，一个 90 美元行权价的 call 在价格位置上大致属于实值、平值还是虚值？为什么这还不是完整定价结论？
4. 企业担心燃油成本上涨时，买 call 和买期货在风险形状上有什么不同？
5. 打开一个期权产品页面，找出 underlying、strike、expiration、premium 和 volume/open interest。

## 学习交接

- 本课已经完成：把衍生工具从线性期货推进到期权权利结构，理解 call、put、premium、strike、expiration、moneyness、protective put 和 covered call。
- 本课最重要的一句话：期权买方买的是有期限的权利和不对称风险形状，不是更便宜的期货。
- 需要复习的关键词：Call Option、Put Option、Premium、Strike Price、Expiration、Intrinsic Value、Time Value、Moneyness、Futures Option、Protective Put、Covered Call。
- 还不稳定、下次要回看的地方：为什么同样方向判断下，隐含波动率、Delta、Gamma、Theta 和 Vega 会让期权价格变化完全不同。
- 适合下次打开仓库先读的文件：`lessons/2026-07-24-lesson-64-options-calls-puts-premium-protective-structures.md`

## 下节课安排

- 建议主题：第六十五课：隐含波动率、Greeks、Delta 对冲与期权风险边界入门。
- 学习目标：理解 implied volatility、historical volatility、Delta、Gamma、Theta、Vega、Rho、delta hedge、gamma risk、time decay 和 volatility risk。
- 建议案例：使用 CME WTI CVOL、OCC/OIC Greeks 教育材料、CFTC 词汇和 EIA WTI 近期价格波动，解释为什么期权交易不是只判断方向，还要判断波动、时间和敏感度。
- 必须解释的关键词：Implied Volatility、Historical Volatility、Delta、Gamma、Theta、Vega、Rho、Delta Hedge、Gamma Risk、Time Decay、Volatility Risk。
- 下节课开始前需要联网核验的数据：CME WTI CVOL 页面、CME option settlement tools、CFTC/OIC Greeks 定义、最新 EIA WPSR、WTI 日度价格、Fed H.15。

## 来源

- SEC Investor.gov, Investor Bulletin: An Introduction to Options: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-63
- CFTC, Futures Glossary: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CFTCGlossary/index.htm
- CME Group, Crude Oil Options Contract Specs: https://www.cmegroup.com/markets/energy/crude-oil/light-sweet-crude.contractSpecs.options.html
- CME Group, Energy Options: https://www.cmegroup.com/markets/energy/energy-options.html
- EIA, Weekly Petroleum Status Report: https://www.eia.gov/petroleum/supply/weekly/
- EIA, Commercial crude oil inventories increased by 2.0 million barrels: https://www.eia.gov/todayinenergy/detail.php?id=67868
- EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- OCC/OIC, About The Options Industry Council: https://www.optionseducation.org/abouttheoptionsindustrycouncil/about-oic
