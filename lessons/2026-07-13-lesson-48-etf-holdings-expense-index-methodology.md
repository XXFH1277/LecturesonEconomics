# 第四十八课：基金与 ETF 持仓穿透、费用率和指数方法论入门

## 基本信息

- 日期：2026-07-13
- 数据截至：2026-07-13 20:24（Asia/Shanghai）。SPY 基金页面采用 State Street 页面显示的 2026-07-13 基金信息、2026-07-10 NAV/持仓/行业权重；QQQ 采用 Invesco 页面截至 2026-07-13 可核验内容，其中 performance 页面注明 QQQ total expense ratio 为 0.18%；指数方法论采用 S&P Dow Jones Indices 2026-06《S&P U.S. Indices Methodology》和 Nasdaq 2026《Nasdaq-100 Index Methodology》。
- 主题：为什么基金不是黑箱；如何从持仓、费用率、基准和指数方法论拆解 ETF 的真实风险暴露。
- 学习目标：理解 Holdings、Expense Ratio、Benchmark、Index Methodology、Top Holdings、Sector Weight、Tracking Error、Turnover 和 Concentration 的入门含义；学会把“买一个 ETF”改写成“买一篮子规则、持仓和费用”。
- 相关资产：ETF、指数基金、SPY、QQQ、S&P 500、Nasdaq-100、股票组合、行业暴露、费用。
- 核心来源：
  - State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - Invesco QQQ About page: https://www.invesco.com/qqq-etf/en/about.html
  - Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html
  - S&P Dow Jones Indices, S&P U.S. Indices Methodology, June 2026: https://www.spglobal.com/spdji/en/documents/methodologies/methodology-sp-us-indices.pdf
  - Nasdaq, Nasdaq-100 Index Methodology, 2026: https://indexes.nasdaqomx.com/docs/Methodology_NDX.pdf
  - SEC Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.sec.gov/investor/alerts/etfs.pdf

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课说“基金名字不同，不代表底层风险不同”。今天从一个更具体的问题开始：

> 我买的是 SPY、QQQ 这样的 ETF，还是买了一个指数规则、持仓篮子和费用结构？

答案是后者。ETF 的表面名字只是入口，真正决定风险和收益来源的是：它跟踪什么基准、按什么规则选股票、实际持有什么、费用是多少、是否集中在少数公司或行业，以及基金能不能长期贴近基准。

### 参考的教材式概念顺序

1. Fund / ETF：基金或交易所交易基金，是把许多投资者的钱放进一个投资组合。
2. Benchmark：基准，基金说自己要跟踪或比较的对象。
3. Holdings：持仓，基金真实拥有的一篮子证券。
4. Top Holdings：前十大持仓，帮助快速看集中度。
5. Sector Weight：行业权重，帮助看行业暴露。
6. Expense Ratio：费用率，基金每年从资产中扣除的运营成本比例。
7. Index Methodology：指数方法论，决定哪些公司能进指数、权重如何计算、何时再平衡。
8. Tracking Error / Tracking Difference：基金表现与基准之间的偏离。
9. Turnover：换手率，组合在一定期间内更换持仓的程度。
10. Concentration：集中度，少数公司或行业占比过高时形成的风险。

### 核心概念

读 ETF 最小顺序可以写成：

```text
ETF 名称
-> 跟踪哪个 Benchmark
-> Benchmark 用什么 Index Methodology
-> 基金实际 Holdings 是否贴近 Benchmark
-> Top Holdings 和 Sector Weight 是否集中
-> Expense Ratio 和交易成本是多少
-> 历史上 NAV 回报与 Benchmark 是否接近
```

初学者最容易犯的错误，是把“指数基金”理解成“自动分散”。指数基金确实能降低单一公司选择错误，但它不会自动消除行业集中、估值集中、利率暴露或少数巨头权重过高的问题。

### 用自己的话解释

ETF 像一份菜单，但菜单背后还有采购规则。Benchmark 告诉你这家餐厅主打什么菜系；Index Methodology 告诉你厨师按什么规则采购；Holdings 是今天厨房里实际有什么；Expense Ratio 是你为这套服务每年付的管理成本。

所以，读基金不是问“它过去涨了多少”就结束，而是问：

- 它为什么持有这些公司？
- 权重为什么是这样？
- 这些规则什么时候会更新？
- 我为这套规则付多少钱？
- 如果少数大公司同时下跌，基金会受到什么影响？

### 常见误区

- 误区一：ETF 名字里有“500”就一定只持有 500 只股票。实际基金持仓数量可能因 share class、现金、过渡调整或复制方式和指数成分数量不同。
- 误区二：费用率低就一定更适合所有人。长期持有时费用很重要，但交易价差、流动性、税务、跟踪质量和投资目标也要看。
- 误区三：指数方法论不重要。指数不是自然存在的，它是规则产品。
- 误区四：前十大持仓都是好公司，所以风险低。好公司也可能估值高、权重集中，或者一起暴露于同一宏观变量。
- 误区五：行业分散等于风险分散。行业权重只是第一层，还要看利率、美元、监管、AI 资本开支、消费周期等共同暴露。

## 第二大板块：实时背景与市场传导

### 发生了什么

State Street 的 SPY 页面显示，SPY seeks to provide investment results that, before expenses, correspond generally to the price and yield performance of the S&P 500 Index；其 benchmark 为 S&P 500 Index，inception date 为 1993-01-22，gross expense ratio 为 0.0945%。页面还显示，SPY 的 AUM 为 789,225.89 million 美元（as of 2026-07-10），fund number of holdings 为 504，index number of holdings 为 503。

SPY 2026-07-10 的前十大持仓中，NVIDIA 权重 7.84%、Apple 7.11%、Microsoft 4.39%、Amazon 3.69%、Alphabet Class A 3.22%。行业权重中，Information Technology 为 37.66%、Financials 为 12.08%、Communication Services 为 9.98%。这些数字说明：一个 S&P 500 ETF 虽然覆盖很多公司，但仍然可能在少数大型科技和通信平台上有明显暴露。

Invesco 的 QQQ 页面显示，QQQ tracks the Nasdaq-100 Index，提供 Nasdaq 上 100 largest non-financial companies 的暴露，fund 和 index quarterly rebalance、annual reconstitution。Invesco performance 页面注明 QQQ total expense ratio 为 0.18%。这说明 QQQ 和 SPY 都是大盘股票 ETF，但它们的基准、指数规则、行业结构和费用口径不同，不能只按“都是美国股票 ETF”机械比较。

### 为什么重要

从第 47 课的组合暴露角度看，ETF 是“已经打包好的组合”。但打包不等于风险消失，只是风险被装进了基金规则里。

一个初学者可以先这样拆：

| 问题 | SPY 入门观察 | QQQ 入门观察 | 学习含义 |
| --- | --- | --- | --- |
| 跟踪什么 | S&P 500 Index | Nasdaq-100 Index | 基准不同 |
| 规则来自哪里 | S&P U.S. Indices Methodology | Nasdaq-100 Index Methodology | 指数不是自然事实 |
| 费用率 | 0.0945% gross expense ratio | 0.18% total expense ratio | 成本口径要核验 |
| 持仓范围 | 大型美国股票，覆盖 11 个 GICS sectors | Nasdaq 上大型非金融公司 | 行业和交易所暴露不同 |
| 集中度 | 前五大合计超过 26% | 需从 QQQ 持仓页持续核验 | 名字多也可能集中 |

这张表不是推荐 SPY 或 QQQ，而是训练读基金的顺序。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| SPY benchmark | S&P 500 Index | State Street, fund information as of 2026-07-13 | 基准识别 |
| SPY gross expense ratio | 0.0945% | State Street, fund information as of 2026-07-13 | 费用率 |
| SPY AUM | 789,225.89 million 美元 | State Street, as of 2026-07-10 | 规模观察 |
| SPY fund holdings | 504 | State Street, as of 2026-07-10 | 持仓穿透 |
| SPY top holding | NVIDIA 7.84% | State Street, as of 2026-07-10 | 集中度观察 |
| SPY IT sector weight | 37.66% | State Street, as of 2026-07-10 | 行业暴露 |
| QQQ index | Nasdaq-100 Index | Invesco About QQQ, accessed 2026-07-13 | 基准识别 |
| QQQ total expense ratio | 0.18% | Invesco performance page, accessed 2026-07-13 | 费用率比较 |
| S&P 500 methodology | large-cap U.S. market, float-adjusted market capitalization weighting | S&P DJI methodology, June 2026 | 指数规则 |
| Nasdaq-100 methodology | annual reconstitution, quarterly rebalance, company-level weight constraints | Nasdaq methodology, 2026 | 指数规则 |

### 这些现实事件如何连接理论

S&P DJI 2026-06 方法论说明，S&P U.S. Indices 用于衡量在美国交易所交易的美国注册股票市场表现，相关指数按 float-adjusted market capitalization 加权；S&P 500 衡量美国 large-cap segment，由 500 constituent companies 组成。方法论还列出入选条件，例如美国 domicile、SEC periodic reporting obligations、合格交易所、普通股、market capitalization、float 和 liquidity 等。

Nasdaq-100 方法论说明，指数 annual reconstitution、quarterly rebalance；如果单家公司权重超过 24%，或权重超过 4.5% 的公司合计超过 48%，可能触发 special rebalance。这个规则告诉我们：QQQ 的持仓权重不是“基金经理随便决定”，而是跟 Nasdaq-100 的指数规则相连。

把这两套规则放在一起，初学者就能明白：同样是被动 ETF，也可能因为指数提供商、入选范围、权重约束和再平衡频率不同，而形成不同风险暴露。

### 至少一个真实市场机制案例

真实机制是“市值加权带来的集中”。如果某些大型公司股价和市值持续上升，它们在市值加权指数里的权重会变大；跟踪这些指数的 ETF 也会自然增加对这些公司的暴露。

这有两个结果：

```text
大型公司上涨
-> 指数中权重变大
-> 跟踪指数的 ETF 对这些公司的暴露变大
-> 基金看似持有很多公司，但收益和风险更受少数公司影响
```

反过来，如果这些大权重公司同时承压，基金可能并不像“持有 500 只股票”听起来那么分散。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 投资公司监管、基金招募说明书和定期披露、指数提供商方法论、交易所上市、GICS / ICB 行业分类、ETF 发行人与指数授权。
- 已确认事实：SPY 数据来自 State Street；QQQ 数据来自 Invesco；S&P 500 和 Nasdaq-100 规则来自官方指数方法论；ETF 基础监管解释来自 SEC Investor Bulletin。
- 市场可能如何传导：指数规则改变会影响 ETF 持仓；大型公司市值变化会改变权重；费用率影响长期净回报；行业集中会影响组合波动。
- 仍需核验或观察：基金下一次持仓数据、指数成分调整、费用率变动、基金规模变化、跟踪误差、行业权重和前十大持仓集中度。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| ETF | 交易所交易基金 | 像股票一样在交易所买卖的一篮子基金份额 | 连接基金和二级市场交易 |
| Holdings | 持仓 | 基金实际拥有的证券清单 | 看真实风险暴露 |
| Expense Ratio | 费用率 | 基金每年从资产中扣除的费用比例 | 长期影响净回报 |
| Benchmark | 基准 | 基金追踪或比较的指数 | 判断基金目标 |
| Index Methodology | 指数方法论 | 指数选股、加权和再平衡规则 | 决定 ETF 买什么 |
| Top Holdings | 前十大持仓 | 权重最大的若干证券 | 快速观察集中度 |
| Sector Weight | 行业权重 | 各行业占基金比例 | 观察行业暴露 |
| Tracking Error | 跟踪误差 | 基金与指数表现偏离的波动 | 判断复制质量 |
| Tracking Difference | 跟踪差异 | 一段时间内基金回报与指数回报的差 | 常受费用和复制影响 |
| Turnover | 换手率 | 组合更换持仓的频率 | 影响交易成本和税务 |
| Float-adjusted Market Cap | 流通市值调整 | 只按可交易流通部分计算权重 | 避免不可流通股份夸大权重 |
| Reconstitution | 重新构成 | 定期重选指数成分 | 改变持仓名单 |
| Rebalance | 再平衡 | 调整权重回到规则要求 | 改变持仓比例 |

## 回顾提示

- 学到本课前建议回顾：第 4 课基金和 ETF、第 15 课估值倍数和利率、第 47 课组合暴露。
- 本课哪些内容会在后续课程继续使用：ETF 交易机制、NAV、premium/discount、creation/redemption、基金表现归因。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图、第 5 课债券利率、第 46 课投资备忘录。

## 案例拆解

- 案例对象：SPY 与 QQQ 的基金穿透对照。
- 已确认事实：
  - SPY 的 benchmark 为 S&P 500 Index，gross expense ratio 为 0.0945%，AUM 为 789,225.89 million 美元，fund holdings 为 504，Information Technology 权重为 37.66%。
  - QQQ tracks the Nasdaq-100 Index，目标是提供 Nasdaq 上 100 largest non-financial companies 的暴露，total expense ratio 为 0.18%。
  - S&P 500 是 large-cap U.S. market 指数，采用 float-adjusted market capitalization weighting。
  - Nasdaq-100 年度重构、季度再平衡，并有公司层面权重约束。
- 来源日期和链接：见本课“来源”。
- 分析推理：SPY 更像大型美国股票市场代理，但仍有大型科技权重集中；QQQ 更偏 Nasdaq 大型非金融公司，可能更集中于成长、科技和创新叙事。
- 后续验证指标：最新 holdings、sector allocation、expense ratio、index methodology updates、tracking difference、fund AUM、premium/discount、bid/ask spread。

## 个人情境连接

- 对关注清单的启发：把“我关注某 ETF”改成“我关注这个 ETF 的基准、前十大持仓、行业权重和费用”。
- 对持仓或基金选择的启发：不要只比较历史收益，先比较底层规则和风险暴露。
- 对工作、收入、消费或风险管理的启发：如果个人收入、奖金和投资都暴露在同一行业或同一宏观变量上，ETF 也可能没有想象中分散。

## 结论边界

- 可以确定：ETF 需要从基准、持仓、费用率和指数方法论共同阅读；基金名字和历史收益不能替代底层穿透。
- 不能确定：本课不判断 SPY、QQQ 或任何 ETF 是否值得买入，也不预测未来收益。
- 需要继续观察：基金持仓、行业权重、指数成分调整、费用率、基金规模、交易价差和 premium/discount。
- 不构成投资建议的原因：本课只训练基金阅读框架，不建议买入、卖出、持有或配置任何证券或基金。

## 练习题

1. 为什么“持有 500 只股票”不等于没有集中度风险？
2. 用 SPY 的前十大持仓和行业权重，写出两个可能的共同暴露。
3. QQQ 跟踪 Nasdaq-100，这和“买全部 Nasdaq 股票”有什么不同？
4. Expense Ratio 和 bid/ask spread 分别影响哪类成本？
5. 找一个你关注的 ETF，按“Benchmark -> Methodology -> Holdings -> Expense Ratio -> Sector Weight”的顺序写一页笔记。

## 学习交接

- 本课已经完成：把第 47 课的组合暴露框架扩展到基金与 ETF，学会从持仓、费用率、基准和指数方法论拆解基金。
- 本课最重要的一句话：ETF 不是黑箱，而是一套指数规则、持仓篮子、费用结构和交易机制的组合。
- 需要复习的关键词：Holdings、Expense Ratio、Benchmark、Index Methodology、Top Holdings、Sector Weight、Tracking Error、Turnover、Concentration。
- 还不稳定、下次要回看的地方：ETF 在二级市场交易时，市场价格为什么可能偏离 NAV，以及 creation/redemption 如何帮助价格回归。
- 适合下次打开仓库先读的文件：`lessons/2026-07-13-lesson-48-etf-holdings-expense-index-methodology.md`

## 下节课安排

- 建议主题：第四十九课：ETF 交易机制、NAV、申购赎回与溢价折价入门。
- 学习目标：理解 ETF 为什么像股票一样交易，但又有基金 NAV；学会区分 market price、NAV、IIV/IOPV、bid/ask spread、premium/discount、authorized participant 和 creation unit。
- 建议案例：继续使用 SPY 的 2026-07-10 NAV、closing price、bid/ask midpoint、premium/discount 和 SEC ETF bulletin。
- 必须解释的关键词：NAV、Market Price、IIV、IOPV、Premium、Discount、Bid/Ask Spread、Authorized Participant、Creation Unit、Arbitrage、Limit Order、Market Order。
- 下节课开始前需要联网核验的数据：ETF 发行人官网的 NAV、market price、premium/discount、bid/ask spread、基金招募说明书；SEC 或 FINRA 的 ETF 交易教育材料。

## 来源

- State Street SPY product page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Invesco QQQ About page: https://www.invesco.com/qqq-etf/en/about.html
- Invesco QQQ Performance page: https://www.invesco.com/qqq-etf/en/performance.html
- S&P Dow Jones Indices, S&P U.S. Indices Methodology, June 2026: https://www.spglobal.com/spdji/en/documents/methodologies/methodology-sp-us-indices.pdf
- Nasdaq, Nasdaq-100 Index Methodology, 2026: https://indexes.nasdaqomx.com/docs/Methodology_NDX.pdf
- SEC Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.sec.gov/investor/alerts/etfs.pdf
