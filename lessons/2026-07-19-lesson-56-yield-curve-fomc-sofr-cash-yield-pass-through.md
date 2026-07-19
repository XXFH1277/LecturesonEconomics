# 第五十六课：收益率曲线、FOMC、SOFR 与现金收益率传导入门

## 基本信息

- 日期：2026-07-19
- 数据截至：2026-07-19 21:20（Asia/Shanghai）。美国市场最新可用日度数据多截至 2026-07-16 或 2026-07-17，因为 2026-07-19 是周日。FOMC 采用 Federal Reserve 2026-06-17 statement 和 implementation note；H.15 采用 2026-07-17 发布、截至 2026-07-16 的数据；SOFR 采用 New York Fed API 最新 `last/5` 数据；T-Bill 拍卖采用 U.S. Treasury FiscalData，截至 `auction_date <= 2026-07-19`；基金和 ETF 数据采用 State Street GVMXX、iShares SGOV 官方页面。
- 主题：政策利率如何传到 effective federal funds rate、SOFR、T-Bill、货币市场基金和短债 ETF 收益率。
- 学习目标：理解 Policy Rate、Target Range、IORB、ON RRP、Standing Repo Facility、Effective Federal Funds Rate、SOFR、T-Bill Rate、7-Day SEC Yield、30-Day SEC Yield、Basis、Lag 和 Pass-through。
- 相关资产：美国短端利率、T-Bill、货币市场基金、短债 ETF、回购市场、现金管理工具。
- 核心来源：
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - Federal Reserve, Implementation Note issued 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a1.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-17: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve Bank of New York, SOFR reference rate page: https://www.newyorkfed.org/markets/reference-rates/sofr
  - New York Fed Markets Data API, SOFR last observations: https://markets.newyorkfed.org/api/rates/secured/sofr/last/5.json
  - New York Fed Markets Data API, latest reference rates: https://markets.newyorkfed.org/api/rates/all/latest.json
  - U.S. Treasury FiscalData API, Auctions Query: https://api.fiscaldata.treasury.gov/services/api/fiscal_service/v1/accounting/od/auctions_query
  - State Street Institutional U.S. Government Money Market Fund GVMXX: https://www.ssga.com/us/en/institutional/cash/state-street-institutional-us-government-money-market-fund-premier-class-gvmxx
  - iShares 0-3 Month Treasury Bond ETF SGOV: https://www.ishares.com/us/products/314116/fund

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课我们会读 T-Bill 拍卖表了。今天继续问：

> 美联储说目标利率是 3.50%-3.75%，为什么 SOFR、4-week T-Bill、货币市场基金和短债 ETF 的收益率不是同一个数字？

答案是：政策利率像方向盘，不是每个产品的挂牌价。它先影响银行准备金和隔夜资金市场，再传到国库券、回购、基金持仓和 ETF 收益率。每一层都有自己的供需、费用、期限和更新时间，所以会联动，但不会完全一样。

### 参考的教材式概念顺序

1. Policy Rate：政策利率，中央银行用来表达货币政策立场的核心利率。
2. Target Range：目标区间，FOMC 给 federal funds rate 设定的运行范围。
3. IORB：准备金余额利率，银行把准备金放在 Fed 获得的利率。
4. ON RRP：隔夜逆回购工具，部分合格机构把现金隔夜借给 Fed、拿证券作抵押的工具。
5. Standing Repo Facility：常设回购工具，Fed 向合格交易对手提供隔夜现金、收取证券抵押的工具。
6. Effective Federal Funds Rate：有效联邦基金利率，银行等机构隔夜无担保借贷美元资金的市场利率。
7. Repo：回购，带抵押的短期借钱交易，常见抵押品是美国国债。
8. SOFR：担保隔夜融资利率，以美国国债抵押的隔夜回购市场为基础。
9. T-Bill Rate：国库券利率，财政部短期债务在拍卖和二级市场中的收益率。
10. Fund Yield：基金收益率，货币市场基金或短债 ETF 持仓收入扣除费用后的口径。
11. Basis：基差，两个相关利率之间的差。
12. Lag：滞后，政策利率变化传到产品收益率需要时间。
13. Pass-through：传导，政策或市场利率变化逐步影响现金工具收益。

### 核心概念

短端利率传导可以分成三层：

```text
第一层：央行管理的利率
- FOMC target range
- IORB
- ON RRP offering rate
- Standing repo rate
- Discount window primary credit rate

第二层：隔夜资金市场利率
- Effective federal funds rate
- SOFR
- Treasury general collateral repo rates

第三层：普通投资者看到的现金工具收益
- T-Bill auction / secondary rates
- Money market fund 7-day SEC yield
- Short Treasury ETF 30 Day SEC Yield
- 银行存款 APY
```

第一层是政策工具，第二层是机构之间真实交易出来的短期资金价格，第三层是产品把短期资产装进账户或基金后呈现给投资者的收益率。

### 用自己的话解释

可以把短端利率想成水流：

```text
FOMC 决定水库闸门的高度
隔夜资金市场决定水从哪条管道流
T-Bill、货币市场基金、短债 ETF 决定水到你杯子里时还剩多少
```

为什么杯子里的水位不等于闸门高度？因为中间有管道、费用、时间和不同容器。

### 常见误区

- 误区一：FOMC target range 等于所有现金工具收益率。目标区间是政策操作目标，不是基金承诺收益。
- 误区二：SOFR 和 EFFR 是同一个利率。EFFR 是无担保隔夜资金利率，SOFR 是以美国国债抵押的隔夜回购利率。
- 误区三：货币市场基金 7-day SEC yield 可以当未来保证收益。它是近期收入年化口径，不是未来承诺。
- 误区四：短债 ETF 30 Day SEC Yield 等于 T-Bill auction yield。ETF 有费用、持仓滚动、NAV、市场价和 SEC 标准化口径。
- 误区五：利率变动会立刻、完全传导。持仓到期、基金费用、发行供需和市场压力都会造成基差和滞后。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve 2026-06-17 FOMC statement 显示，FOMC 维持 federal funds rate target range 在 3.50%-3.75%。同日 implementation note 显示：

- IORB 为 3.65%，自 2026-06-18 生效。
- Standing overnight repo operations rate 为 3.75%。
- Standing overnight reverse repo offering rate 为 3.50%。
- Primary credit rate 维持在 3.75%。

Federal Reserve H.15 2026-07-17 release 显示，截至 2026-07-16：

- Effective federal funds rate：3.63%。
- Treasury bills secondary market 4-week：3.67%。
- Treasury bills secondary market 3-month：3.70%。
- Treasury bills secondary market 6-month：3.78%。
- Treasury bills secondary market 1-year：3.82%。

New York Fed API 显示，截至 2026-07-16：

- SOFR：3.62%。
- SOFR volume：3,038 billion dollars。
- EFFR：3.63%，target range 仍为 3.50%-3.75%，volume 113 billion dollars。

U.S. Treasury FiscalData 显示，最新 T-Bill 拍卖结果中：

| Security term | Auction date | Issue date | Maturity date | High discount rate | High investment rate | Price per 100 | Bid-to-cover |
| --- | --- | --- | --- | ---: | ---: | ---: | ---: |
| 4-Week | 2026-07-16 | 2026-07-21 | 2026-08-18 | 3.660% | 3.721% | 99.715333 | 2.57 |
| 8-Week | 2026-07-16 | 2026-07-21 | 2026-09-15 | 3.650% | 3.722% | 99.432222 | 2.84 |
| 17-Week | 2026-07-15 | 2026-07-21 | 2026-11-17 | 3.745% | 3.845% | 98.762069 | 3.35 |
| 13-Week | 2026-07-13 | 2026-07-16 | 2026-10-15 | 3.760% | 3.849% | 99.049556 | 2.84 |
| 26-Week | 2026-07-13 | 2026-07-16 | 2027-01-14 | 3.860% | 3.992% | 98.048556 | 3.11 |

State Street GVMXX 页面显示，2026-07-17：

- Trans NAV：1.00 美元。
- MTM NAV：0.9999 美元。
- 1 Day yield：3.57%。
- 7 Day SEC yield：3.58%。
- 30 Day yield：3.58%。
- WAM：33 days；WAL：84 days。

iShares SGOV 页面显示：

- NAV：100.57 美元，as of 2026-07-17。
- Closing price：100.58 美元，as of 2026-07-17。
- 30 Day SEC Yield：3.57%，as of 2026-07-16。
- Effective duration：0.10 years，as of 2026-07-16。
- Average yield to maturity：3.69%，as of 2026-07-16。
- Expense ratio：0.09%。

### 为什么重要

把这些数字排在一起，短端利率传导就更清楚了：

| 层级 | 指标 | 最新核验值 | 数据日期 | 教学含义 |
| --- | --- | ---: | --- | --- |
| Fed 政策 | FOMC target range | 3.50%-3.75% | 2026-06-17 | 政策目标区间 |
| Fed 操作 | IORB | 3.65% | 2026-06-18 生效 | 准备金利率锚 |
| Fed 操作 | ON RRP offering rate | 3.50% | 2026-06-18 生效 | 隔夜现金下方锚之一 |
| Fed 操作 | Standing repo rate | 3.75% | 2026-06-18 生效 | 隔夜融资上方锚之一 |
| 市场交易 | EFFR | 3.63% | 2026-07-16 | 无担保隔夜资金价格 |
| 市场交易 | SOFR | 3.62% | 2026-07-16 | 有国债抵押的隔夜资金价格 |
| 国库券 | 4-week T-Bill secondary rate | 3.67% | 2026-07-16 | 短期国债市场锚 |
| 国库券 | 4-week auction investment rate | 3.721% | 2026-07-16 auction | 新发行拍卖口径 |
| 货币基金 | GVMXX 7-day SEC yield | 3.58% | 2026-07-17 | 基金近 7 日收入口径 |
| 短债 ETF | SGOV 30 Day SEC Yield | 3.57% | 2026-07-16 | ETF 标准化收入口径 |

这说明两件事：

```text
第一，它们确实围绕同一组短端利率运行。
第二，它们不是同一个产品，所以不会完全等于同一个数字。
```

GVMXX 的 7-day SEC yield 和 SGOV 的 30 Day SEC Yield 都低于同日附近的部分 T-Bill market / auction rates，原因通常包括基金费用、持仓结构、收益率口径、旧持仓滚动、现金比例和数据日期差异。这个差异不是错误，而是产品结构的一部分。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| FOMC target range | 3.50%-3.75% | Federal Reserve FOMC statement, 2026-06-17 | 政策利率起点 |
| IORB | 3.65% | Federal Reserve implementation note, effective 2026-06-18 | 准备金利率锚 |
| ON RRP offering rate | 3.50% | Federal Reserve implementation note, effective 2026-06-18 | 隔夜现金工具 |
| Standing repo rate | 3.75% | Federal Reserve implementation note, effective 2026-06-18 | 回购市场上方工具 |
| EFFR | 3.63% | H.15 / New York Fed API, 2026-07-16 | 隔夜无担保市场 |
| SOFR | 3.62% | New York Fed API, 2026-07-16 | 隔夜担保回购市场 |
| SOFR volume | 3,038 billion dollars | New York Fed API, 2026-07-16 | 市场规模背景 |
| 4-week T-Bill secondary rate | 3.67% | H.15, 2026-07-16 | T-Bill 二级市场 |
| 4-week auction high investment rate | 3.721% | Treasury FiscalData, auction date 2026-07-16 | 拍卖案例 |
| GVMXX 7-day SEC yield | 3.58% | State Street, 2026-07-17 | 货币市场基金传导 |
| SGOV 30 Day SEC Yield | 3.57% | iShares, 2026-07-16 | 短债 ETF 传导 |

### 这些现实事件如何连接理论

用一句话看传导链：

```text
FOMC target range
-> IORB / ON RRP / repo tools
-> EFFR 与 SOFR
-> T-Bill secondary rate 与 auction rate
-> 货币市场基金和短债 ETF 持仓收入
-> 投资者看到的 7-day / 30-day yield
```

其中每个箭头都会产生基差：

```text
EFFR - SOFR：
无担保资金和有担保回购资金的差异

SOFR - T-Bill：
隔夜回购和短期国库券期限、供需、抵押品特殊性的差异

T-Bill - 货币市场基金：
基金持仓、费用、WAM、WAL 和流动性要求的差异

T-Bill - 短债 ETF：
ETF 持仓篮子、NAV、市场价、SEC yield 口径和费用差异
```

### 至少一个真实市场机制案例

2026-07-16 是一个很好的一页教学案例：

```text
FOMC 目标区间仍为 3.50%-3.75%
EFFR = 3.63%
SOFR = 3.62%
4-week T-Bill secondary rate = 3.67%
4-week T-Bill auction high investment rate = 3.721%
GVMXX 7-day SEC yield = 3.58%（2026-07-17）
SGOV 30 Day SEC Yield = 3.57%（2026-07-16）
```

这不是六个互相矛盾的数字，而是同一条短端利率传导链上的六个观测点。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：FOMC 货币政策、Federal Reserve 公开市场操作、准备金制度、隔夜回购工具、Treasury 国库券发行、SEC 货币市场基金规则、ETF 交易和披露规则。
- 已确认事实：FOMC 2026-06-17 维持目标区间；implementation note 给出 IORB、ON RRP 和 standing repo 操作参数；H.15 和 New York Fed API 提供 EFFR、SOFR 和短端国债利率；基金发行方披露 7-day / 30-day yield。
- 市场可能如何传导：政策利率改变资金市场锚，资金市场改变国库券和回购收益，基金持仓滚动后再影响投资者看到的现金工具收益。
- 仍需核验或观察：下一次 FOMC 决议、后续 H.15、SOFR、T-Bill auction、基金 WAM/WAL、基金费用、ETF NAV 与 premium/discount。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Policy Rate | 政策利率 | 中央银行表达货币政策立场的利率 | 是短端资金价格的起点 |
| Target Range | 目标区间 | FOMC 让联邦基金利率运行的范围 | 观察 Fed 是收紧还是宽松 |
| IORB | 准备金余额利率 | 银行准备金存在 Fed 获得的利率 | 影响银行愿意出借资金的底线 |
| ON RRP | 隔夜逆回购 | 合格机构把现金隔夜借给 Fed | 给短端现金利率提供锚 |
| Standing Repo Facility | 常设回购工具 | Fed 提供隔夜现金、收取证券抵押 | 帮助稳定回购市场 |
| Effective Federal Funds Rate | 有效联邦基金利率 | 隔夜无担保美元资金交易利率 | FOMC 目标跟踪对象 |
| Repo | 回购 | 用证券作抵押的短期借钱交易 | SOFR 的核心市场 |
| SOFR | 担保隔夜融资利率 | 以美国国债抵押的隔夜回购利率 | 替代 LIBOR 后的重要基准 |
| Treasury Bill Rate | 国库券利率 | 短期美国国债的收益率 | 现金管理和无风险短端锚 |
| 7-Day SEC Yield | 7 日 SEC 收益率 | 货币基金近 7 日收入年化口径 | 观察货币基金收益传导 |
| 30-Day SEC Yield | 30 日 SEC 收益率 | 债券基金/ETF 标准化收入口径 | 比较短债 ETF 常用 |
| Basis | 基差 | 两个相关利率之间的差 | 帮助解释为什么不完全相等 |
| Lag | 滞后 | 传导需要时间 | 解释基金收益率更新慢半拍 |
| Pass-through | 传导 | 利率变化从政策端传到产品端 | 是现金管理和债券定价基础 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和利率、第 53 课债券基金、第 54 课现金管理、第 55 课 T-Bill 拍卖。
- 本课哪些内容会在后续课程继续使用：收益率曲线、期限利差、久期、实际利率、黄金和股票估值折现率。
- 如果看不懂本课，可以先回到：第 54 课，把银行存款、货币市场基金、T-Bill 和短债 ETF 的法律关系重新分清。

## 案例拆解

- 案例对象：2026-07 中旬美国短端利率传导链。
- 已确认事实：
  - FOMC target range 为 3.50%-3.75%。
  - IORB 为 3.65%，ON RRP offering rate 为 3.50%，standing repo rate 为 3.75%。
  - 2026-07-16 EFFR 为 3.63%，SOFR 为 3.62%。
  - 2026-07-16 4-week T-Bill secondary rate 为 3.67%。
  - 2026-07-16 4-week T-Bill auction high investment rate 为 3.721%。
  - 2026-07-17 GVMXX 7-day SEC yield 为 3.58%。
  - 2026-07-16 SGOV 30 Day SEC Yield 为 3.57%。
- 来源日期和链接：见本课“来源”。
- 分析推理：这些数字共同说明短端现金工具收益率围绕 Fed 政策锚运行，但每个口径都带有自己的市场、期限、费用和披露规则。
- 后续验证指标：FOMC 决议、H.15 EFFR/T-Bill、SOFR API、Treasury auction results、基金 7-day yield、ETF 30 Day SEC Yield、WAM/WAL、NAV、bid/ask spread。

## 一页短端利率传导检查表

```text
数据日期：

政策层：
- FOMC target range：
- IORB：
- ON RRP：
- Standing repo：

隔夜市场层：
- EFFR：
- SOFR：
- SOFR volume：

国库券层：
- 4-week T-Bill：
- 3-month T-Bill：
- 最新 auction high investment rate：
- bid-to-cover：

产品层：
- 货币市场基金 7-day SEC yield：
- 短债 ETF 30 Day SEC Yield：
- expense ratio：
- WAM / duration：

解释：
- 已确认事实：
- 我的推理：
- 基差来自哪里：
- 仍需观察：
```

## 个人情境连接

- 对关注清单的启发：现金工具观察表不能只记一个收益率，必须同时记录来源日期和收益率口径。
- 对持仓或基金选择的启发：看到货币基金和短债 ETF 收益率低于 T-Bill auction rate 时，不要立刻判断“差”，先检查费用、WAM、duration、NAV 和 SEC yield 口径。
- 对工作、收入、消费或风险管理的启发：如果一笔钱短期要用，利率传导只是第二层问题，第一层仍然是到账时间、规则边界和本金波动承受度。

## 结论边界

- 可以确定：Fed 目标区间、IORB、ON RRP、EFFR、SOFR、T-Bill 和基金收益率处在同一条短端利率传导链上。
- 不能确定：本课不能预测下一次 FOMC 会加息、降息还是维持；也不能预测任何基金或 ETF 未来收益。
- 需要继续观察：通胀、就业、FOMC 表述、H.15、SOFR、财政部发行供需、基金流动性和 ETF 市场价格。
- 不构成投资建议的原因：本课只解释利率传导机制，不建议买入、卖出或持有任何现金工具、基金或 ETF。

## 练习题

1. 用自己的话解释：为什么 FOMC target range 不等于 GVMXX 的 7-day SEC yield？
2. EFFR 和 SOFR 的核心区别是什么？请从“有没有抵押品”解释。
3. 如果 SOFR 为 3.62%，4-week T-Bill secondary rate 为 3.67%，这 0.05 个百分点差异可能来自哪些因素？
4. 为什么短债 ETF 的 30 Day SEC Yield 不是未来 30 天保证收益？
5. 按本课检查表，找一个现金工具，记录其收益率口径、费用率、数据日期和规则边界。

## 学习交接

- 本课已经完成：把 FOMC 目标区间、政策操作工具、EFFR、SOFR、T-Bill、货币市场基金和短债 ETF 放进同一条短端利率传导链。
- 本课最重要的一句话：政策利率是方向盘，不是每个现金产品的挂牌价。
- 需要复习的关键词：Policy Rate、Target Range、IORB、ON RRP、EFFR、SOFR、Repo、T-Bill Rate、7-Day SEC Yield、30-Day SEC Yield、Basis、Lag、Pass-through。
- 还不稳定、下次要回看的地方：为什么 1 个月、3 个月、2 年、10 年和 30 年的利率会形成不同形状的收益率曲线。
- 适合下次打开仓库先读的文件：`lessons/2026-07-19-lesson-56-yield-curve-fomc-sofr-cash-yield-pass-through.md`

## 下节课安排

- 建议主题：第五十七课：收益率曲线形状、期限溢价与周期信号入门。
- 学习目标：理解 normal curve、flat curve、inverted curve、steepening、flattening、term spread、term premium、real yield 和 inflation compensation。
- 建议案例：使用 Federal Reserve H.15 2026-07-17 release 的 1-month、3-month、2-year、10-year、30-year nominal yields，以及 5-year、10-year、30-year TIPS yields，画出当前收益率曲线的入门图。
- 必须解释的关键词：Yield Curve、Term Structure、Maturity、Term Spread、Steepening、Flattening、Inversion、Term Premium、Real Yield、Inflation Compensation、Duration。
- 下节课开始前需要联网核验的数据：Federal Reserve H.15 最新收益率曲线、Treasury yield curve methodology、Fed yield curve model说明、最新 FOMC statement。

## 来源

- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- Federal Reserve, Implementation Note issued 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a1.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve Bank of New York, SOFR reference rate page: https://www.newyorkfed.org/markets/reference-rates/sofr
- New York Fed Markets Data API, SOFR last observations: https://markets.newyorkfed.org/api/rates/secured/sofr/last/5.json
- New York Fed Markets Data API, latest reference rates: https://markets.newyorkfed.org/api/rates/all/latest.json
- U.S. Treasury FiscalData API, Auctions Query: https://api.fiscaldata.treasury.gov/services/api/fiscal_service/v1/accounting/od/auctions_query
- State Street Institutional U.S. Government Money Market Fund GVMXX: https://www.ssga.com/us/en/institutional/cash/state-street-institutional-us-government-money-market-fund-premier-class-gvmxx
- iShares 0-3 Month Treasury Bond ETF SGOV: https://www.ishares.com/us/products/314116/fund
