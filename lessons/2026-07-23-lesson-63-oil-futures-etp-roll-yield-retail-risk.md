# 第六十三课：原油期货类 ETP、展期收益、杠杆产品与散户风险边界入门

## 基本信息

- 日期：2026-07-23
- 数据截至：2026-07-23（Asia/Shanghai）。EIA Weekly Petroleum Status Report 最新可用版本为 2026-07-22 发布、截至 2026-07-17 的周度数据；EIA WTI 现货价格最新可用点为 2026-07-20；USO 采用 SEC 2026-02-23 收录的 2025 Form 10-K；USCF 官网、CFTC、FINRA 和 SEC Investor.gov 采用当前可访问页面。
- 主题：为什么原油期货类 ETP 可能和现货油价走势不一样。
- 学习目标：理解 commodity pool、ETP、NAV、benchmark futures contract、roll、roll yield、contango drag、backwardation benefit、tracking difference、leverage risk 和 daily reset。
- 相关资产：USO、WTI futures、Micro WTI futures、原油现货、货币市场工具、短期国债、杠杆/反向 ETF。
- 核心来源：
  - SEC EDGAR, United States Oil Fund, LP 2025 Form 10-K: https://www.sec.gov/Archives/edgar/data/1327068/000110465926021501/uso-20251231x10k.htm
  - USCF, United States Oil Fund official holdings/disclosures page: https://www.uscfinvestments.com/holdings/uso
  - CFTC, Learn About Risks Before Investing in Commodity ETPs or Funds: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CustomerAdvisory_CommodityETPs.htm
  - FINRA, Futures and Commodities: https://www.finra.org/investors/investing/investment-products/futures-and-commodities
  - SEC Investor.gov, Leveraged and Inverse ETFs: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-alerts/sec
  - CME Group, WTI Crude Oil Futures: https://www.cmegroup.com/markets/energy/wti-crude-oil-futures.html
  - EIA, Weekly Petroleum Status Report, release date 2026-07-22: https://www.eia.gov/petroleum/supply/weekly/
  - EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲企业用期货做套保。今天从普通投资者容易误解的问题开始：

> 如果我买一个“原油 ETF”，是不是就等于买了一桶原油？

通常不是。很多原油类交易所产品并不持有仓库里的现货原油，而是持有原油期货、现金、国债、货币市场工具、互换或其他相关工具。它们给的是“期货价格暴露”，不是“家里有一桶油”的所有权。

更准确地说，很多产品是 exchange-traded product（ETP，交易所交易产品）或 commodity pool（商品池），不是传统股票 ETF。

### 参考的教材式概念顺序

1. ETF：交易所交易基金，通常持有证券组合并在交易所交易。
2. ETP：交易所交易产品，范围比 ETF 更广，可以包括商品池、ETN 等。
3. Commodity Pool：商品池，把投资者资金集中起来交易期货、期权、互换等商品权益。
4. NAV：净资产值，基金或产品资产减负债后的每份价值。
5. Market Price：二级市场交易价格，可能偏离 NAV。
6. Benchmark Futures Contract：基准期货合约，产品用来衡量目标暴露的合约。
7. Roll：展期，把即将到期的合约卖掉，换到更远月份。
8. Roll Yield：展期收益，展期价格差带来的正或负贡献。
9. Contango Drag：正向市场拖累，远月贵于近月时展期可能付出成本。
10. Backwardation Benefit：逆向市场收益，近月贵于远月时展期可能有利。
11. Tracking Difference：跟踪差异，产品表现和目标指标之间的偏离。
12. Leverage Risk：杠杆风险，用较少本金承受较大名义价值波动。
13. Daily Reset：每日重置，杠杆/反向产品常见机制，长期收益可能偏离日目标倍数。

### 核心概念

期货类原油产品有三层价格：

```text
现货油价：今天附近交割的原油价格
期货价格：某个交割月份的原油合约价格
产品价格：ETP/基金份额在交易所的市场价格或 NAV
```

这三者会相关，但不会永远相等。差异来自合约展期、费用、现金收益、保证金、交易成本、NAV 折溢价、监管限制、流动性压力和产品自身规则。

### 用自己的话解释

想象你不能把原油放在家里，所以买了一个“帮你持续持有近月原油期货”的产品。近月合约快到期时，产品必须把旧合约换成新合约。这个换仓动作就是 roll。

如果新合约更贵，产品相当于卖便宜的、买贵的，长期可能被拖累；如果新合约更便宜，展期可能带来正贡献。这个效果和现货油价涨跌不同，所以“油价涨，产品一定同幅上涨”是错误直觉。

### 常见误区

- 误区一：原油 ETP 等于现货油价。很多产品追踪的是期货合约，不是现货桶油。
- 误区二：只要油价长期上涨，期货类产品长期一定赚钱。展期和费用可能抵消一部分现货涨幅。
- 误区三：contango 和 backwardation 只是专业术语。它们直接影响长期持有体验。
- 误区四：杠杆产品适合长期放着。许多杠杆/反向产品是每日目标，长期结果可能和直觉差很远。
- 误区五：交易所挂牌就代表低风险。产品可能仍有期货、杠杆、流动性、监管、保证金和对手方风险。

## 第二大板块：实时背景与市场传导

### 发生了什么

EIA 2026-07-22 WPSR 显示，截至 2026-07-17 当周，美国商业原油库存为 411.7 million barrels，Cushing 库存为 19.4 million barrels，炼厂开工率为 96.1%。EIA WTI 现货价格页显示，WTI-Cushing 2026-07-20 为 84.38 美元/桶。

这些数据说明，原油市场仍需要同时看现货、交割地库存、炼厂开工和期货合约。对期货类 ETP 来说，现货价格只是输入之一，产品更直接面对的是期货合约、展期和保证金现金管理。

USO 2025 Form 10-K 披露，United States Oil Fund, LP 是在 NYSE Arca 交易的 commodity pool。其目标是让每股 NAV 的每日百分比变化反映 Cushing 轻质低硫原油现货价格的每日百分比变化，这个变化通过名为 Benchmark Oil Futures Contract 的短期期货合约衡量，并加上抵押品利息、扣除费用。USO 同时披露，它的目标不是让 NAV 或市场价格在美元金额上等于现货油价，也不是让超过一天的表现机械等于某一个期货合约。

USO 10-K 还披露，Benchmark Oil Futures Contract 通常是 NYMEX light sweet crude oil 的近月合约，并在每月初约五个交易日内滚动到下一个月份。截至 2025-12-31，USO 持有 13,180 张 NYMEX light sweet crude oil futures，并有现金存放在 custodian 和 futures commission merchants。

CFTC 投资者提示提醒，商品 ETP 和基金可能使用期货、期权、互换或外汇，不一定像传统股票债券 ETF；商品池持有的是有期限的合约，不代表拥有底层实物资产。FINRA 也提示，许多商品跟踪产品追踪的是期货而非现货，并通过展期维持暴露，长期表现可能显著偏离现货。

### 为什么重要

这组事实把原油学习从“企业套保”推进到“个人产品选择边界”：

```text
投资者买入交易所产品
-> 产品持有期货和现金等资产
-> 期货临近到期需要展期
-> contango/backwardation 改变展期收益
-> 费用、现金收益和交易成本进入 NAV
-> 二级市场价格还可能与 NAV 有折溢价
```

所以，买原油期货类 ETP 前，必须先问它到底追踪什么、持有什么、怎么 roll、费用是多少、是否有杠杆或每日重置。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| WPSR 最新周度数据 | week ending 2026-07-17 | EIA, 2026-07-22 | 原油市场背景 |
| 商业原油库存 | 411.7 million barrels | EIA WPSR, 2026-07-22 | 现货库存背景 |
| Cushing 库存 | 19.4 million barrels | EIA WPSR, 2026-07-22 | WTI 交割地背景 |
| WTI-Cushing | 84.38 美元/桶 | EIA, 2026-07-20 | 现货价格锚 |
| USO 法律结构 | commodity pool，NYSE Arca 交易 | SEC 10-K, 2025 report | 产品结构 |
| USO 基准 | 短期 NYMEX light sweet crude oil futures | SEC 10-K | 追踪对象 |
| USO roll 规则 | 每月初约五日展期至下一近月合约 | SEC 10-K | 展期机制 |
| USO 持仓 | 2025-12-31 持有 13,180 张 NYMEX light sweet crude futures | SEC 10-K | 真实持仓案例 |
| 商品 ETP 风险 | 期货合约有期限，不等于拥有实物资产 | CFTC | 风险边界 |
| 期货类产品偏离 | 展期可能导致相对现货的显著差异 | FINRA | 跟踪差异 |
| USCF 披露 | USO 等产品为 CFTC 监管 commodity pools，不是 Investment Company Act 下的 mutual funds | USCF 官网 | 法律边界 |

### 这些现实事件如何连接理论

第一条链：现货、期货和产品。

```text
EIA 发布现货和库存数据
-> CME/NYMEX 期货价格反映交割月份预期
-> 期货类产品持有这些合约
-> 产品 NAV 受期货价格、现金收益和费用共同影响
```

第二条链：展期收益。

```text
近月合约快到期
-> 产品卖出近月、买入远月
-> 远月更贵：展期成本
-> 远月更便宜：展期收益
-> 长期表现可能偏离现货油价
```

第三条链：散户风险。

```text
产品在交易所买卖
-> 看起来像股票
-> 底层却可能是期货、互换、现金和国债
-> 还可能有杠杆、每日重置或复杂费用
-> 必须读 prospectus、10-K、holding 和 risk factors
```

### 至少一个真实市场机制案例

案例：USO 的“每日目标”和“展期规则”。

USO 2025 10-K 披露，产品目标围绕每日百分比变化和短期期货合约，并明确不是让份额价格等于一桶油的美元价格。它还披露，基准期货合约会在每月初约五个交易日内从近月合约换到下一近月合约。

这说明普通投资者看到“USO”和“WTI”不能直接画等号。更正确的读法是：

```text
USO 份额
-> commodity pool 份额
-> 持有期货、现金和相关工具
-> 追踪短期期货的每日变化
-> 长期结果受展期、费用和市场结构影响
```

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、CFTC 商品池监管、FINRA 投资者教育、USCF 产品披露、CME/NYMEX 期货市场、EIA 能源统计。
- 已确认事实：USO 是 commodity pool；CFTC 和 FINRA 都提示商品 ETP/期货类产品可能不等同于传统 ETF 和现货商品；USCF 明示 USO 等产品不是 Investment Company Act 下的共同基金。
- 市场可能如何传导：油价波动影响期货价格；期货曲线形态影响展期；短端利率影响现金抵押品收益；监管或仓位限制可能影响产品持仓安排。
- 仍需核验或观察：USO 最新 holdings、最新 prospectus/10-Q、CME 期货曲线、CFTC/SEC/FINRA 更新、产品是否使用 swaps、leveraged/inverse 产品是否有 daily reset。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| ETF | 交易所交易基金 | 像股票一样交易的基金 | 传统概念入口 |
| ETP | 交易所交易产品 | 比 ETF 更宽的挂牌产品类别 | 商品产品常用 |
| Commodity Pool | 商品池 | 集合资金交易期货、期权、互换等 | USO 法律结构 |
| NAV | 净资产值 | 资产减负债后的每份价值 | 判断产品真实价值 |
| Market Price | 市场价格 | 交易所成交价格 | 可能偏离 NAV |
| Benchmark Futures Contract | 基准期货合约 | 产品用来追踪的目标合约 | 判断追踪对象 |
| Roll | 展期 | 卖旧合约、买新合约 | 保持期货暴露 |
| Roll Yield | 展期收益 | 展期价差造成的收益或成本 | 解释偏离现货 |
| Contango Drag | 正向市场拖累 | 远月贵于近月时的展期成本 | 长持风险 |
| Backwardation Benefit | 逆向市场收益 | 远月便宜时的展期贡献 | 不等于现货涨跌 |
| Tracking Difference | 跟踪差异 | 产品表现和目标之间的偏离 | 产品分析核心 |
| Leverage Risk | 杠杆风险 | 小本金承受大波动 | 杠杆产品重点 |
| Daily Reset | 每日重置 | 每天重设目标倍数 | 长期表现可能偏离 |

## 回顾提示

- 学到本课前建议回顾：第 8 课衍生工具入门、第 49 课 ETF 交易机制、第 61 课期货曲线、第 62 课保证金和套保。
- 本课哪些内容会在后续课程继续使用：期权、杠杆 ETF、反向 ETF、商品基金、风险披露、产品说明书和投资者保护。
- 如果看不懂本课，可以先回到：第 4 课基金和 ETF，第 48 课 ETF 持仓穿透，第 62 课期货名义价值。

## 案例拆解

- 案例对象：United States Oil Fund, LP（USO）与 CFTC/FINRA 商品 ETP 风险提示。
- 已确认事实：
  - USO 是在 NYSE Arca 交易的 commodity pool。
  - USO 的目标围绕每日 NAV 百分比变化和 Benchmark Oil Futures Contract。
  - USO 披露目标不是让 NAV 或市场价格在美元金额上等于现货油价。
  - USO 的基准合约会在每月初约五个交易日内展期。
  - CFTC 和 FINRA 都提示期货类商品产品可能和现货表现产生差异。
- 来源日期和链接：见本课“来源”。
- 分析推理：原油期货类产品更像“持续管理的一组期货和现金暴露”，不是“现货油桶仓单”；长期表现必须拆成现货变化、期货曲线、展期、费用、现金收益和折溢价。
- 后续验证指标：USO holdings、USO prospectus/10-Q、WTI futures curve、roll schedule、expense ratio、NAV premium/discount、CME margin、CFTC/SEC/FINRA 投资者提示。

## 一页期货类 ETP 检查表

```text
产品名称：
数据日期：

法律结构：
- ETF、ETP、ETN 还是 commodity pool：
- 是否受 Investment Company Act 监管：
- 是否受 CFTC commodity pool 规则监管：

目标：
- 追踪现货、期货、指数还是每日倍数：
- 目标期限是每日、30 日还是长期：
- 是否有 leveraged / inverse / daily reset：

持仓：
- 具体期货月份：
- 现金、T-Bill、money market fund：
- 互换或其他 OTC 工具：
- 是否有仓位限制或流动性调整：

展期：
- 什么时候 roll：
- 从哪一个合约 roll 到哪一个合约：
- 当前是 contango 还是 backwardation：
- 展期可能贡献正收益还是负收益：

费用和交易：
- 管理费：
- 交易成本：
- NAV premium/discount：
- 买卖价差：

结论边界：
- 我能确定什么：
- 我不能确定什么：
- 需要下次复核什么：
```

## 个人情境连接

- 对关注清单的启发：记录商品产品时，不要只写 ticker，要记录法律结构、目标、底层持仓、展期规则和费用。
- 对持仓或基金选择的启发：同样叫“原油相关”，能源股 ETF、原油期货 ETP、杠杆产品和航空/运输股的风险完全不同。
- 对工作、收入、消费或风险管理的启发：产品名称越像快捷入口，越要回到合同和披露文件确认真实风险。

## 结论边界

- 可以确定：期货类原油 ETP 可能通过期货和相关工具获得暴露；roll、contango、backwardation、费用和现金收益会影响长期表现。
- 不能确定：本课不能预测 USO、WTI、Brent、任何杠杆产品或能源基金未来涨跌。
- 需要继续观察：产品最新持仓、期货曲线、展期日、费用、监管披露、NAV 折溢价和市场流动性。
- 不构成投资建议的原因：本课只解释商品类交易所产品结构和风险边界，不建议买入、卖出或持有任何产品。

## 练习题

1. 为什么 USO 这类产品不等于“买一桶现货原油”？
2. 如果近月 WTI 合约 84 美元、下月合约 86 美元，产品从近月展期到下月大致面对什么方向的展期影响？
3. NAV 和 market price 有什么区别？
4. 为什么一个每日 2 倍目标产品不适合用“长期应该是 2 倍”来理解？
5. 打开一个商品类产品页面，找出它的 holdings、prospectus、expense 和 risk factors。

## 学习交接

- 本课已经完成：把原油期货从企业套保扩展到交易所产品、商品池、展期收益、杠杆和散户风险边界。
- 本课最重要的一句话：买期货类原油产品，买到的是产品规则和期货暴露，不是现货油价本身。
- 需要复习的关键词：Commodity Pool、ETP、NAV、Benchmark Futures Contract、Roll、Roll Yield、Contango Drag、Backwardation Benefit、Tracking Difference、Leverage Risk、Daily Reset。
- 还不稳定、下次要回看的地方：期权如何用权利金换取不对称保护，为什么“保险式结构”和“杠杆式结构”风险不同。
- 适合下次打开仓库先读的文件：`lessons/2026-07-23-lesson-63-oil-futures-etp-roll-yield-retail-risk.md`

## 下节课安排

- 建议主题：第六十四课：期权入门：看涨、看跌、权利金、时间价值与保护性结构。
- 学习目标：理解 call、put、premium、strike price、expiration、intrinsic value、time value、moneyness、protective put、covered call 和 implied volatility。
- 建议案例：使用 CME WTI options 或 OCC/SEC/CFTC 投资者教育材料，解释期权为什么像支付权利金购买不对称风险暴露，以及企业和投资者如何用期权替代部分线性期货风险。
- 必须解释的关键词：Call Option、Put Option、Premium、Strike Price、Expiration、Intrinsic Value、Time Value、Moneyness、Protective Put、Covered Call、Implied Volatility。
- 下节课开始前需要联网核验的数据：CME WTI option specs、CFTC/OCC/SEC 期权投资者教育材料、最新 EIA WPSR、WTI 期货曲线、CME CVOL 或其他官方波动率说明。

## 来源

- SEC EDGAR, United States Oil Fund, LP 2025 Form 10-K: https://www.sec.gov/Archives/edgar/data/1327068/000110465926021501/uso-20251231x10k.htm
- USCF, United States Oil Fund official holdings/disclosures page: https://www.uscfinvestments.com/holdings/uso
- CFTC, Learn About Risks Before Investing in Commodity ETPs or Funds: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CustomerAdvisory_CommodityETPs.htm
- FINRA, Futures and Commodities: https://www.finra.org/investors/investing/investment-products/futures-and-commodities
- SEC Investor.gov, Leveraged and Inverse ETFs: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-alerts/sec
- CME Group, WTI Crude Oil Futures: https://www.cmegroup.com/markets/energy/wti-crude-oil-futures.html
- EIA, Weekly Petroleum Status Report: https://www.eia.gov/petroleum/supply/weekly/
- EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm
