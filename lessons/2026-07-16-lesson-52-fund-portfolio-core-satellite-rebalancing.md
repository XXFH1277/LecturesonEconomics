# 第五十二课：基金组合构建、核心/卫星配置与再平衡入门

## 基本信息

- 日期：2026-07-16
- 数据截至：2026-07-16 21:35（Asia/Shanghai）。资产配置和再平衡规则采用 SEC Investor.gov 初学者指南；基金风险底线采用 SEC《Mutual Funds and ETFs: A Guide for Investors》；SPY 采用 State Street 页面显示的 2026-07-16 基金信息、2026-07-15 NAV/市场价格、持仓和行业权重；QQQ 采用 Invesco 页面截至本次核验可见的基金目标、费用和风险披露；债券基金案例采用 iShares AGG 页面显示的 2026-07-15 组合指标、2026-07-14 SEC yield 和 2026-06-30 业绩；利率背景采用 U.S. Treasury Daily Treasury Par Yield Curve Rates 2026-07-15。
- 主题：为什么买了多个基金不等于组合合理；如何用资产配置、核心/卫星、风险预算和再平衡规则组织基金组合。
- 学习目标：理解 Asset Allocation、Diversification、Correlation、Core-Satellite、Risk Budget、Position Sizing、Liquidity Reserve、Rebalancing 和 Rebalancing Band；学会写一页基金组合检查表。
- 相关资产：ETF、股票基金、债券基金、SPY、QQQ、AGG、现金和美国国债收益率。
- 核心来源：
  - SEC Investor.gov, Beginners' Guide to Asset Allocation, Diversification, and Rebalancing: https://www.investor.gov/additional-resources/general-resources/publications-research/info-sheets/beginners-guide-asset
  - SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
  - State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - Invesco QQQ pages: https://www.invesco.com/qqq-etf/en/about.html and https://www.invesco.com/qqq-etf/en/performance.html
  - iShares AGG product page: https://www.ishares.com/us/products/239458/ishares-core-total-us-bond-market-etf
  - U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课学会了看单个基金的波动、回撤和 Sharpe Ratio。今天的问题是：

> 我买了好几个基金，是不是就已经分散风险了？

不一定。如果这些基金都重仓同一批大型科技股，它们名字不同，但风险来源可能很像。组合构建不是把基金名称堆起来，而是先决定每类资产承担什么任务，再选择工具，并写清楚何时检查、何时再平衡。

### 参考的教材式概念顺序

1. Asset Allocation：资产配置，把资金分到股票、债券、现金等类别。
2. Diversification：分散化，把风险分到不同资产、行业、地区和策略。
3. Correlation：相关性，看不同资产是否经常同涨同跌。
4. Core Holding：核心仓位，承担组合主要市场暴露。
5. Satellite Holding：卫星仓位，承担更窄、更主动或更高风险的主题暴露。
6. Risk Budget：风险预算，决定每个风险来源最多能占多少。
7. Position Sizing：仓位规模，决定每个基金或资产类别买多大。
8. Liquidity Reserve：流动性储备，留给短期支出、应急和再平衡。
9. Rebalancing：再平衡，把偏离目标的组合拉回原来的资产配置。
10. Rebalancing Band：再平衡区间，事先规定偏离多少才行动。

### 核心概念

一个入门组合可以拆成四层：

```text
组合 = 目标权重 + 工具选择 + 风险预算 + 再平衡规则

目标权重：
- 股票类承担长期增长
- 债券类承担收入、波动缓冲和利率暴露
- 现金类承担短期流动性

工具选择：
- 核心：宽基、低成本、透明的基金
- 卫星：主题、行业、因子、主动基金或更集中基金

风险预算：
- 不能只看基金数量
- 要看行业、公司、利率、信用、汇率和流动性暴露

再平衡规则：
- 用日历或偏离区间触发
- 先考虑新增资金和现金流
- 再考虑交易成本和税务后果
```

核心/卫星不是固定比例公式，而是一种组织语言。核心仓位负责让组合不偏离主要目标太远；卫星仓位负责表达有限的主题判断。对初学者来说，卫星仓位越大，越需要解释为什么承担这份额外风险。

### 用自己的话解释

组合像一支球队。核心基金是主力阵容，负责稳定完成基本任务；卫星基金像特殊战术，可能在某些阶段有用，但不能让整支队伍变成只有一种打法。再平衡像中场调整，不是预测下一球，而是防止某个位置因为涨太多或跌太多而控制全局。

### 常见误区

- 误区一：基金数量多就一定分散。多个基金可能持有相同股票或同一行业。
- 误区二：股票基金加股票基金就是资产配置。资产配置要跨资产类别，而不只是跨产品名称。
- 误区三：债券基金等于现金。债券基金有利率、信用、久期和流动性风险。
- 误区四：再平衡就是高抛低吸赚钱技巧。再平衡的第一目标是控制风险暴露，不是保证更高收益。
- 误区五：目标权重一旦写下就永远不变。时间期限、收入稳定性、负债和风险承受能力变化时，配置也要重新审视。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC Investor.gov 的初学者指南把 asset allocation 定义为把投资组合分到股票、债券和现金等资产类别，并提醒合适配置取决于 time horizon 和 risk tolerance。该指南还说明，rebalancing 是把组合带回原来的资产配置，因为部分资产会涨得比其他资产快；再平衡可通过卖出超配资产、买入低配资产，或把新增资金投向低配资产完成。

SEC《Mutual Funds and ETFs: A Guide for Investors》提示，基金和 ETF 不由 FDIC 或其他政府机构担保，投资者可能亏钱；成本会降低回报；基金和 ETF 可提供分散化，但投资者仍需阅读招募说明书和风险披露。

State Street SPY 页面显示，SPY 的 benchmark 为 S&P 500 Index，gross expense ratio 为 0.0945%；2026-07-15 NAV 为 754.68 美元，closing price 为 754.81 美元，premium/discount 为 0.01%，30-day median bid/ask spread 为 0.00%。同日 SPY 持有 504 只证券，前三大持仓为 NVIDIA 7.90%、Apple 7.39%、Microsoft 4.51%，Information Technology 行业权重为 37.32%。

Invesco 页面说明，QQQ 跟踪 Nasdaq-100 Index，提供 Nasdaq 上市的 100 家最大非金融公司暴露；基金和指数 quarterly rebalance、annually reconstitute。Invesco QQQ 的 total expense ratio 为 0.18%；风险披露说明，集中在特定行业如 technology 的投资风险更大，QQQ 为 non-diversified fund，波动性可能高于更分散投资。

iShares AGG 页面显示，AGG 跟踪 Bloomberg US Aggregate Bond Index，2026-07-15 NAV 为 98.17 美元，expense ratio 为 0.03%，持仓数量 13,265；2026-07-14 30 Day SEC Yield 为 4.58%；2026-07-15 effective duration 为 5.74 年，average yield to maturity 为 4.81%，Treasury 权重 46.44%，MBS Pass-Through 权重 23.10%，AA rated 权重 73.49%，BBB rated 权重 11.59%。

U.S. Treasury Daily Treasury Par Yield Curve Rates 显示，2026-07-15 的 3-month rate 为 3.83%，2-year rate 为 4.13%，10-year rate 为 4.55%，30-year rate 为 5.08%。Treasury 说明这些 CMT 利率来自每日收益率曲线插值，输入为纽约联储在每个交易日约 15:30 获取的指示性买方报价。

### 为什么重要

SPY、QQQ 和 AGG 可以做一个入门组合案例，但不是推荐组合：

```text
SPY：宽基美国大盘股票暴露，但信息技术和少数巨头权重不低
QQQ：Nasdaq-100 暴露，更偏大型成长和科技相关风险
AGG：美国投资级债券暴露，但不是现金，有久期和信用风险
现金或短期工具：承担应急、支出和再平衡弹药
```

如果同时持有 SPY 和 QQQ，组合可能不是更分散，而是更集中于大型科技和成长股。加入 AGG 可以引入债券暴露，但 AGG 的 5.74 年 effective duration 说明它会受到利率变化影响。现金储备看起来回报低，却能减少在下跌时被迫卖出长期资产的概率。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| 资产配置定义 | 组合分到股票、债券、现金等资产类别 | SEC Investor.gov | 组合起点 |
| 再平衡定义 | 把组合带回原始资产配置 | SEC Investor.gov | 规则框架 |
| 基金风险底线 | 基金和 ETF 可亏钱，成本会降低回报 | SEC guide | 结论边界 |
| SPY gross expense ratio | 0.0945% | State Street, 2026-07-16 | 核心工具成本 |
| SPY holdings | 504 | State Street, 2026-07-15 | 宽基程度 |
| SPY top holding | NVIDIA 7.90% | State Street, 2026-07-15 | 集中度 |
| SPY IT sector weight | 37.32% | State Street, 2026-07-15 | 行业暴露 |
| QQQ total expense ratio | 0.18% | Invesco, accessed 2026-07-16 | 卫星工具成本 |
| QQQ index rule | Nasdaq-100，季度再平衡、年度重构 | Invesco, accessed 2026-07-16 | 指数规则 |
| AGG 30 Day SEC Yield | 4.58% | iShares, 2026-07-14 | 债券收入口径 |
| AGG effective duration | 5.74 年 | iShares, 2026-07-15 | 利率敏感度 |
| U.S. 10-year Treasury rate | 4.55% | U.S. Treasury, 2026-07-15 | 利率背景 |

### 这些现实事件如何连接理论

假设一个学习用组合目标是：

```text
核心股票基金：50%
卫星股票基金：20%
债券基金：20%
现金储备：10%
```

这不是投资建议，只是为了演示规则。

如果一段时间后组合变成：

```text
核心股票基金：55%
卫星股票基金：25%
债券基金：15%
现金储备：5%
```

问题不是“股票还会不会涨”，而是“组合已经比原计划更依赖股票、科技、成长和低现金储备”。再平衡可以有三种做法：

```text
1. 用新增资金买债券基金和现金类资产
2. 暂停给超配资产加钱
3. 在考虑税务和交易成本后，卖出一部分超配资产
```

再平衡不是为了预测顶部，而是让组合回到自己能承受的风险水平。

### 至少一个真实市场机制案例

真实机制是“两个看似不同的股票 ETF 可能共享风险来源”。

SPY 是 S&P 500 暴露，持仓数量很多；但 State Street 数据显示，2026-07-15 SPY 的 Information Technology 权重为 37.32%，NVIDIA、Apple、Microsoft 合计超过 19%。QQQ 又跟踪 Nasdaq-100，Invesco 明确披露特定行业集中和 non-diversified fund 风险。

因此：

```text
买 SPY + QQQ
不等于
自动买了两个独立风险来源

它可能意味着：
- 美国大盘股票暴露更高
- 大型科技和成长股暴露更高
- 同一利率、估值和 AI 叙事风险更高
```

这就是组合构建要看穿透持仓和相关性的原因。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 投资者教育、基金招募说明书、ETF 发行人披露、指数授权和方法论、美国国债收益率曲线。
- 已确认事实：SEC 与 Investor.gov 提供资产配置、分散化、再平衡和基金风险底线；SPY、QQQ、AGG 数据来自基金发行人页面；利率来自 U.S. Treasury。
- 市场可能如何传导：利率变化会同时影响股票估值和债券价格；科技集中会让多个基金在同一叙事下同涨同跌；债券基金可降低某些股票波动，但也会带来久期和信用风险。
- 仍需核验或观察：不同基金之间的真实相关性、持仓重叠、行业权重变化、债券 duration、信用质量、现金收益、交易成本和税务影响。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Asset Allocation | 资产配置 | 把钱分到股票、债券、现金等类别 | 决定组合主要风险 |
| Diversification | 分散化 | 不把风险压在一个来源上 | 降低单点失败影响 |
| Correlation | 相关性 | 两个资产是否经常同涨同跌 | 判断是否真分散 |
| Core Holding | 核心仓位 | 组合中最基础、最大块的配置 | 稳住主要目标 |
| Satellite Holding | 卫星仓位 | 围绕核心的小比例主题或主动配置 | 表达有限判断 |
| Risk Budget | 风险预算 | 给每种风险来源设上限 | 防止单一风险失控 |
| Position Sizing | 仓位规模 | 每个基金或资产占组合多少 | 决定影响力大小 |
| Liquidity Reserve | 流动性储备 | 可应急、可支出、可再平衡的资金 | 避免被迫卖出 |
| Rebalancing | 再平衡 | 把偏离目标的组合拉回目标 | 控制风险漂移 |
| Rebalancing Band | 再平衡区间 | 偏离多少才行动的阈值 | 减少频繁交易 |
| Overlap | 持仓重叠 | 不同基金持有相同证券 | 名字不同但风险相同 |
| Drift | 权重漂移 | 涨跌后权重偏离原计划 | 再平衡触发信号 |

## 回顾提示

- 学到本课前建议回顾：第 47 课组合暴露、相关性与再平衡；第 48 课 ETF 持仓穿透；第 51 课基金风险指标。
- 本课哪些内容会在后续课程继续使用：债券基金筛选、现金管理、基金组合检查表、个人风险预算。
- 如果看不懂本课，可以先回到：第 1 课收益与风险、第 4 课基金和 ETF、第 5 课债券和利率。

## 案例拆解

- 案例对象：SPY、QQQ 与 AGG 作为教学用组合工具对照。
- 已确认事实：
  - SPY 2026-07-15 持有 504 只证券，Information Technology 权重 37.32%，NVIDIA 权重 7.90%。
  - QQQ 跟踪 Nasdaq-100，Invesco 披露其 total expense ratio 为 0.18%，基金和指数季度再平衡、年度重构。
  - AGG 2026-07-15 持有 13,265 只证券，effective duration 为 5.74 年，Treasury 权重 46.44%。
  - U.S. Treasury 2026-07-15 10-year rate 为 4.55%，30-year rate 为 5.08%。
- 来源日期和链接：见本课“来源”。
- 分析推理：SPY 与 QQQ 都可能增加美国大型成长和科技相关暴露；AGG 引入债券资产类别，但不是现金替代；组合需要同时看资产类别、持仓重叠、行业集中、久期和现金储备。
- 后续验证指标：基金持仓重叠、行业权重、相关性、AGG duration、SEC yield、信用质量、Treasury 曲线、再平衡触发区间和交易成本。

## 一个可复制的基金组合检查页

```text
组合名称：
数据截至：
投资目标：
时间期限：
可承受最大回撤：
应急现金需求：

目标权重：
- 核心股票：
- 卫星股票：
- 债券：
- 现金：
- 其他：

工具：
- 基金名称：
- 基准：
- 费用率：
- 持仓数量：
- 前十大权重：
- 行业权重：
- 久期 / 信用质量：
- 流动性指标：

风险预算：
- 单一基金上限：
- 单一行业上限：
- 单一公司穿透上限：
- 债券久期上限：
- 现金储备下限：

再平衡规则：
- 日历检查频率：
- 再平衡区间：
- 优先用新增资金还是卖出：
- 税务和交易成本：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：记录基金时增加“组合角色”：核心、卫星、债券、现金或观察。
- 对持仓或基金选择的启发：先问基金给组合增加了什么风险来源，再问它过去涨了多少。
- 对工作、收入、消费或风险管理的启发：如果收入、职业和投资都依赖同一行业，就要降低组合中同一风险来源的集中度。

## 结论边界

- 可以确定：资产配置要先于选基金；多个基金不一定分散；再平衡的核心作用是控制风险漂移；债券基金和现金不是同一种东西。
- 不能确定：本课不能证明 SPY、QQQ、AGG 或任何组合未来会有更高收益，也不能给出适合每个人的固定比例。
- 需要继续观察：个人时间期限、收入稳定性、现金需求、基金持仓重叠、行业集中、利率曲线和税务成本。
- 不构成投资建议的原因：本课只解释基金组合构建和再平衡框架，不建议买入、卖出、持有或配置任何基金。

## 练习题

1. 如果一个组合目标是股票 60%、债券 30%、现金 10%，上涨后变成股票 72%、债券 23%、现金 5%，它多承担了哪些风险？
2. 为什么同时持有 SPY 和 QQQ 不一定等于充分分散？请用“持仓重叠”和“行业集中”解释。
3. 用 AGG 的 effective duration 5.74 年解释：为什么债券基金不是现金？
4. 写一个自己的 rebalancing band。例如某资产目标 20%，偏离到多少才检查？为什么？
5. 选三个基金，按“核心/卫星/债券/现金”的角色重新分类，并写出每个基金的主要风险来源。

## 学习交接

- 本课已经完成：把单个基金风险指标推进到组合层面的资产配置、核心/卫星、风险预算和再平衡规则。
- 本课最重要的一句话：组合不是基金数量清单，而是风险来源、目标权重和再平衡纪律的组合。
- 需要复习的关键词：Asset Allocation、Diversification、Correlation、Core-Satellite、Risk Budget、Position Sizing、Liquidity Reserve、Rebalancing、Rebalancing Band、Overlap。
- 还不稳定、下次要回看的地方：债券基金为什么会涨跌、SEC yield 和 distribution yield 有什么区别、duration 如何把利率变化传导到基金价格。
- 适合下次打开仓库先读的文件：`lessons/2026-07-16-lesson-52-fund-portfolio-core-satellite-rebalancing.md`

## 下节课安排

- 建议主题：第五十三课：债券基金、久期、信用质量与 SEC Yield 入门。
- 学习目标：理解债券基金不是存款，学会用 duration、maturity、yield to maturity、30 Day SEC Yield、credit quality、OAS 和 prepayment risk 阅读债券基金。
- 建议案例：继续使用 iShares AGG 的官方页面，并结合 U.S. Treasury 最新收益率曲线和 SEC 债券基金风险说明。
- 必须解释的关键词：Bond Fund、Fixed Income、Coupon、Yield、Yield to Maturity、30 Day SEC Yield、Duration、Effective Duration、Maturity、Credit Quality、OAS、Prepayment Risk、Interest Rate Risk。
- 下节课开始前需要联网核验的数据：AGG 或同类债券基金的最新 SEC yield、effective duration、average yield to maturity、credit quality、maturity breakdown、Treasury 最新收益率曲线和基金历史回报。

## 来源

- SEC Investor.gov, Beginners' Guide to Asset Allocation, Diversification, and Rebalancing: https://www.investor.gov/additional-resources/general-resources/publications-research/info-sheets/beginners-guide-asset
- SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
- State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Invesco QQQ About page: https://www.invesco.com/qqq-etf/en/about.html
- Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html
- iShares AGG product page: https://www.ishares.com/us/products/239458/ishares-core-total-us-bond-market-etf
- U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
