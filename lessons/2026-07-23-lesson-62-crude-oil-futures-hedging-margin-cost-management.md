# 第六十二课：原油期货、套期保值、保证金与企业成本管理入门

## 基本信息

- 日期：2026-07-23
- 数据截至：2026-07-23（Asia/Shanghai）。EIA Weekly Petroleum Status Report 最新可用版本为 2026-07-22 发布、截至 2026-07-17 的周度数据；EIA WTI 现货价格最新可用点为 2026-07-20；Federal Reserve H.15 最新发布日为 2026-07-22、截至 2026-07-21；Federal Reserve H.10 最新发布日为 2026-07-20、截至 2026-07-17；Southwest Airlines 采用 2026-02-05 提交、报告期为 2025 年的 10-K。
- 主题：为什么原油期货既可以用于交易，也可以用于企业成本管理。
- 学习目标：理解 futures contract、notional value、tick、margin、mark-to-market、hedging、speculation、basis risk、variation margin 和 hedge accounting。
- 相关资产：WTI、Brent、NYMEX WTI futures、Micro WTI futures、航空燃油、炼厂、能源公司、航空公司、现金和短端利率。
- 核心来源：
  - EIA, Weekly Petroleum Status Report, release date 2026-07-22: https://www.eia.gov/petroleum/supply/weekly/
  - EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm
  - CME Group, WTI product overview: https://www.cmegroup.com/education/courses/introduction-to-energy/introduction-to-crude-oil/wti-overview
  - CME Group, WTI Crude Oil Futures: https://www.cmegroup.com/markets/energy/wti-crude-oil-futures.html
  - CFTC, Economic Purpose of Futures Markets and How They Work: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/economicpurpose.html
  - CFTC, Futures Glossary: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CFTCGlossary/index.htm
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-22: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, H.10 Foreign Exchange Rates, release date 2026-07-20: https://www.federalreserve.gov/releases/H10/current/
  - SEC EDGAR, Southwest Airlines 2025 Form 10-K, filed 2026-02-05: https://www.sec.gov/Archives/edgar/data/92380/0000092380-26-000004-index.htm

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲了库存、期货曲线、炼化利润和风险溢价。今天换一个更实用的问题：

> 如果一家航空公司担心未来燃油涨价，它能不能今天先把未来成本锁住？

可以尝试，但不是用“买很多现货油放仓库”这么简单。企业通常会使用期货、期权、互换等衍生品，把未来价格风险的一部分转移出去。这个过程叫套期保值。

注意：套保不是赚钱魔法。它的目标通常是降低不确定性，不是保证最低成本，也不是消灭所有风险。

### 参考的教材式概念顺序

1. Spot：现货，今天附近交割的油。
2. Futures Contract：期货合约，交易所标准化的未来买卖合约。
3. Contract Size：合约规模，一张合约代表多少商品。
4. Tick：最小价格变动单位。
5. Notional Value：名义价值，合约规模乘以价格。
6. Margin：保证金，履约担保金，不是买股票时的首付款。
7. Initial Margin：初始保证金，开仓时需要缴纳的最低保证金。
8. Maintenance Margin：维持保证金，持仓期间需要保持的最低权益。
9. Mark-to-market：每日盯市，每天按结算价确认盈亏。
10. Variation Margin：变动保证金，亏损后补足保证金的现金流。
11. Hedging：套期保值，用衍生品降低已有或预期业务风险。
12. Speculation：投机，主要为了表达价格方向观点。
13. Basis Risk：基差风险，套保工具和真实业务价格不完全同步。
14. Hedge Accounting：套期会计，符合条件时把套保损益和被套保项目更匹配地反映在财报里。

### 核心概念

期货是一张标准化合约，不是一张“预测油价的答案纸”。对初学者最重要的是三句话：

```text
期货给的是未来交割月份的价格
保证金控制的是履约风险和杠杆风险
套保降低的是某一类价格风险，不是全部经营风险
```

CME 的 WTI 原油期货代码通常是 CL，一张基准合约代表 1,000 桶 WTI 原油，最小价格变动通常是 0.01 美元/桶，所以一跳对应 10 美元。Micro WTI 合约是 100 桶，更小，但仍然有杠杆和保证金风险。

### 用自己的话解释

把期货想成一份标准化的“未来价格协议”。航空公司担心油价涨，可以买入与燃油相关的衍生品来对冲未来成本；石油生产商担心油价跌，可以卖出相关合约来锁定未来卖油价格。

保证金像押金，但不是买下整桶油的钱。你用较少现金控制较大的名义价值，所以价格小幅变化也会放大利润和亏损。每日盯市意味着亏损不会等到最后一天才算，交易所每天都会把当日盈亏反映到保证金账户里。

### 常见误区

- 误区一：保证金越少，风险越小。实际正相反，保证金少意味着杠杆高，同样价格波动对本金影响更大。
- 误区二：套保等于预测正确。套保的目标通常是让预算更稳定，不是抓住最低价。
- 误区三：买原油期货就等于买航空燃油。WTI、Brent、RBOB、ULSD 和 jet fuel 不是同一个价格口径。
- 误区四：企业做套保一定赚。套保可能减少成本上行风险，也可能在油价下跌时失去部分好处。
- 误区五：期货到期前随时可以忽略。临近交割、流动性、保证金、展期和实物交割规则都可能改变风险。

## 第二大板块：实时背景与市场传导

### 发生了什么

EIA 2026-07-22 WPSR 显示，截至 2026-07-17 当周，美国商业原油库存为 411.7 million barrels，较前周增加 2.0 million barrels；Strategic Petroleum Reserve 为 311.4 million barrels，较前周下降 5.1 million barrels。Cushing, Oklahoma 原油库存为 19.4 million barrels，低于前周的 20.0 million barrels。

同一份 EIA 周报显示，美国炼厂原油投入为 17.065 million b/d，炼厂开工率为 96.1%；总汽油库存为 211.3 million barrels，馏分油库存为 109.6 million barrels，总产品供应为 20.519 million b/d。

EIA WTI 现货价格页显示，WTI-Cushing 在 2026-07-20 为 84.38 美元/桶。用这个价格做入门名义价值计算：

```text
一张 CL 合约名义价值 = 1,000 桶 x 84.38 美元/桶 = 84,380 美元
一张 Micro WTI 合约名义价值 = 100 桶 x 84.38 美元/桶 = 8,438 美元
```

Federal Reserve H.15 2026-07-22 release 显示，截至 2026-07-21，effective federal funds rate 为 3.63%，10 年 Treasury constant maturity 为 4.63%，10 年 TIPS yield 为 2.37%。H.10 2026-07-20 release 显示，截至 2026-07-17，USD/CNY 为 6.7760，Broad Dollar Index 为 120.5315。

Southwest Airlines 2025 Form 10-K 提供了企业套保的真实披露案例。公司披露燃油成本高度波动，历史上把符合条件的燃油衍生品作为现金流套保处理；但 2024 年第三季度，WTI crude oil-based derivatives 因与 jet fuel prices 的相关性减弱而不再符合前瞻性 hedge accounting 条件，相关 WTI 工具在 2024 年底前结清。公司还披露 2025 年第二季度终止了剩余燃油套保组合，原计划结算期延伸至 2027 年。

### 为什么重要

这组事实把上一课的“市场结构”推进到“风险管理”：

```text
现货价格波动
-> 企业未来成本或收入不确定
-> 用期货、期权、互换做套保
-> 保证金和每日盯市带来现金流要求
-> 如果套保工具和真实业务价格不同步，就出现基差风险
-> 财报里还要处理套期会计和损益分类
```

对零基础学习者来说，最重要的不是马上会交易，而是知道企业为什么在财报里讨论 derivative instruments、AOCI、fuel and oil expense 和 other gains/losses。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| WPSR 最新周度数据 | week ending 2026-07-17 | EIA, 2026-07-22 | 原油和成品油背景 |
| 商业原油库存 | 411.7 million barrels | EIA WPSR, 2026-07-22 | 现货缓冲垫 |
| Cushing 原油库存 | 19.4 million barrels | EIA WPSR, 2026-07-22 | WTI 交割地案例 |
| 炼厂开工率 | 96.1% | EIA WPSR, 2026-07-22 | 成品油约束 |
| WTI-Cushing | 84.38 美元/桶 | EIA, 2026-07-20 | 名义价值计算 |
| CL 合约规模 | 1,000 桶 | CME Group | 标准化合约 |
| CL 最小跳动 | 0.01 美元/桶，约 10 美元/跳 | CME Group | 盈亏敏感度 |
| EFFR | 3.63% | Fed H.15, 2026-07-21 | 保证金现金收益背景 |
| 10Y nominal CMT | 4.63% | Fed H.15, 2026-07-21 | 宏观利率背景 |
| USD/CNY | 6.7760 | Fed H.10, 2026-07-17 | 美元计价折算 |
| Southwest fuel hedge case | WTI 套保工具 2024 年不再符合 hedge accounting 条件；2025 年终止剩余燃油套保组合 | SEC 10-K, 2026-02-05 | 基差风险和套期会计案例 |

### 这些现实事件如何连接理论

第一条链：名义价值和杠杆。

```text
WTI 价格 84.38 美元/桶
-> 一张 CL 合约代表 1,000 桶
-> 名义价值约 84,380 美元
-> 保证金通常远低于名义价值
-> 价格小幅波动也会明显影响账户权益
```

第二条链：企业套保和现金流。

```text
航空公司未来要买燃油
-> 担心燃油价格上涨
-> 使用衍生品减少价格上行风险
-> 若油价上涨，衍生品收益可部分抵消燃油成本
-> 若油价下跌，衍生品成本或损失可能抵消低油价好处
```

第三条链：基差风险。

```text
企业实际买的是 jet fuel
-> 套保工具可能参考 WTI、Brent、ULSD 或其他指数
-> 如果 jet fuel 和 WTI 不再同步
-> 套保保护效果下降
-> 财报会计处理也可能变化
```

### 至少一个真实市场机制案例

案例：Southwest 的燃油套保说明“锁油价”不等于锁住全部成本。

Southwest 2025 10-K 披露，燃油价格波动会显著影响盈利；公司历史上使用燃油衍生品并在符合条件时采用现金流套期会计。但披露还显示，WTI 与 jet fuel 的相关性在一段时间里不足以继续支持特定 WTI 工具的 hedge accounting。这个案例说明：

```text
套保工具价格 ≠ 企业真实采购价格
会计上能不能作为套保处理 ≠ 经济上完全没有风险
关闭套保组合 ≠ 燃油价格风险消失
```

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：CME/NYMEX 合约规则、CFTC 期货监管、交易所清算和保证金制度、SEC 公司披露、EIA 能源统计、Fed 利率和美元数据。
- 已确认事实：CFTC 将保证金解释为履约担保而非首付款；期货每日盯市；CME WTI 合约是标准化合约；EIA 确认 Cushing 是 NYMEX crude oil futures 的指定交割点；Southwest 披露了燃油衍生品和 hedge accounting 变化。
- 市场可能如何传导：油价和成品油价波动影响企业成本；期货价格进入预算和套保策略；保证金和现金收益率影响持仓现金管理；汇率影响非美元买家的能源成本。
- 仍需核验或观察：CME 最新 margin requirement、WTI/Brent 期货曲线、EIA 下一期 WPSR、航空公司后续 10-Q、炼厂和能源公司衍生品披露、H.15 和 H.10 后续更新。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Futures Contract | 期货合约 | 交易所标准化的未来买卖协议 | 衍生品入门核心 |
| Contract Size | 合约规模 | 一张合约代表多少商品 | 决定名义价值 |
| Tick | 最小跳动 | 价格最小变动单位 | 决定每跳盈亏 |
| Notional Value | 名义价值 | 合约规模乘以价格 | 衡量真实暴露 |
| Initial Margin | 初始保证金 | 开仓时要放入的履约担保 | 体现杠杆 |
| Maintenance Margin | 维持保证金 | 持仓时必须维持的最低权益 | 触发补保证金 |
| Mark-to-market | 每日盯市 | 每天按结算价确认盈亏 | 影响现金流 |
| Variation Margin | 变动保证金 | 亏损后补足保证金的资金 | 套保也有流动性压力 |
| Hedging | 套期保值 | 用工具降低已有风险 | 企业风险管理 |
| Speculation | 投机 | 为价格方向承担风险 | 和套保动机不同 |
| Basis Risk | 基差风险 | 套保工具和真实业务价格不同步 | Southwest 案例重点 |
| Hedge Accounting | 套期会计 | 将套保和被套保项目更匹配地反映 | 读财报必备 |

## 回顾提示

- 学到本课前建议回顾：第 8 课衍生工具入门、第 60 课原油与通胀传导、第 61 课库存、期货曲线和风险溢价。
- 本课哪些内容会在后续课程继续使用：期货类 ETP、期权、企业风险因素、AOCI、现金流套保、商品基金和保证金风险。
- 如果看不懂本课，可以先回到：第 1 课供需和价格，第 5 课利率，第 10 课三张报表。

## 案例拆解

- 案例对象：CME WTI futures、EIA 2026-07-22 WPSR、Southwest Airlines 2025 Form 10-K。
- 已确认事实：
  - WTI-Cushing 2026-07-20 为 84.38 美元/桶。
  - 一张 CL 合约代表 1,000 桶，按该价格名义价值约 84,380 美元。
  - EIA 最新 WPSR 显示 Cushing 库存为 19.4 million barrels。
  - Southwest 披露 WTI-based derivatives 因与 jet fuel prices 的相关性问题不再符合特定 hedge accounting 条件。
- 来源日期和链接：见本课“来源”。
- 分析推理：原油期货既是价格发现工具，也是风险管理工具；但合约标准化、保证金制度和基差风险使它不能机械等同于企业真实燃油成本。
- 后续验证指标：CME margin、WTI futures curve、EIA WPSR、jet fuel crack spread、航空公司 fuel and oil expense、AOCI、衍生品公允价值和现金流套保披露。

## 一页企业套保检查表

```text
企业名称：
数据日期：

真实风险：
- 买什么商品：
- 用什么价格口径采购：
- 风险来自价格上涨还是价格下跌：

套保工具：
- 期货、期权、互换还是组合：
- 参考 WTI、Brent、ULSD、RBOB 还是 jet fuel：
- 合约期限是否匹配真实采购月份：

规模：
- 预计采购量：
- 套保覆盖比例：
- 名义价值：
- 初始保证金和潜在追加保证金：

会计：
- 是否符合 hedge accounting：
- 损益进 Fuel and oil expense 还是 Other gains/losses：
- AOCI 是否有未来重分类金额：

边界：
- 基差风险：
- 流动性风险：
- 交易对手和清算风险：
- 不套保时的成本风险：
```

## 个人情境连接

- 对关注清单的启发：看到企业说“套保”时，要问套保对象、覆盖比例、期限、工具和会计处理，不能只写“有对冲”。
- 对持仓或基金选择的启发：能源、航空、运输和炼化企业对油价的敏感度不同；套保可能改变短期利润波动，但不会改变商业模式本身。
- 对工作、收入、消费或风险管理的启发：企业预算和家庭预算相似，关键不是预测所有价格，而是知道哪些价格变化会让现金流承压。

## 结论边界

- 可以确定：期货合约有标准化规模、保证金和每日盯市；WTI 期货连接 Cushing 现货和全球原油风险；企业可以用衍生品管理部分价格风险。
- 不能确定：本课不能预测 WTI、Brent、航空股、能源股或任何期货合约未来走势。
- 需要继续观察：CME 最新保证金、EIA 库存、期货曲线、企业后续 10-Q、燃油价格和套保组合变化。
- 不构成投资建议的原因：本课只解释衍生品和企业风险管理，不建议交易期货、买卖股票或配置基金。

## 练习题

1. 用 84.38 美元/桶计算一张 1,000 桶 WTI 合约的名义价值。
2. 为什么保证金不是“买下原油的首付款”？
3. 如果航空公司实际买 jet fuel，却用 WTI 做套保，可能出现什么基差风险？
4. 套保为什么可能降低预算波动，但不一定让企业在油价下跌时受益？
5. 从一份航空公司 10-K 里找 fuel、derivative、AOCI 三个词，判断它们分别出现在什么部分。

## 学习交接

- 本课已经完成：把原油现货结构推进到期货合约、保证金、每日盯市、套期保值、基差风险和套期会计。
- 本课最重要的一句话：期货能把价格风险转移或重排，但不会让风险凭空消失。
- 需要复习的关键词：Futures Contract、Notional Value、Tick、Initial Margin、Maintenance Margin、Mark-to-market、Variation Margin、Hedging、Speculation、Basis Risk、Hedge Accounting。
- 还不稳定、下次要回看的地方：期货类 ETP 为什么不等于现货油价，展期收益如何让长期表现偏离。
- 适合下次打开仓库先读的文件：`lessons/2026-07-23-lesson-62-crude-oil-futures-hedging-margin-cost-management.md`

## 下节课安排

- 建议主题：第六十三课：原油期货类 ETP、展期收益、杠杆产品与散户风险边界入门。
- 学习目标：理解 commodity pool、ETP、NAV、benchmark futures contract、roll period、roll yield、contango drag、backwardation benefit、tracking difference、leverage risk 和 daily reset。
- 建议案例：使用 USO 2025 Form 10-K、USCF 官方披露、CFTC commodity ETP customer advisory、FINRA futures and commodities 页面和 CME WTI futures 说明，解释为什么买期货类产品不等于买现货原油。
- 必须解释的关键词：Commodity Pool、ETP、NAV、Benchmark Oil Futures Contract、Roll、Roll Yield、Contango Drag、Backwardation Benefit、Tracking Difference、Leverage Risk、Daily Reset。
- 下节课开始前需要联网核验的数据：USO/USCF 最新披露、SEC 10-K/10-Q 或 prospectus、CFTC/FINRA/SEC 投资者教育材料、CME WTI 产品说明、EIA WTI spot 和最新 WPSR。

## 来源

- EIA, Weekly Petroleum Status Report: https://www.eia.gov/petroleum/supply/weekly/
- EIA, Cushing, OK WTI Spot Price FOB: https://www.eia.gov/dnav/pet/hist/rwtcD.htm
- CME Group, WTI product overview: https://www.cmegroup.com/education/courses/introduction-to-energy/introduction-to-crude-oil/wti-overview
- CME Group, WTI Crude Oil Futures: https://www.cmegroup.com/markets/energy/wti-crude-oil-futures.html
- CFTC, Economic Purpose of Futures Markets and How They Work: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/economicpurpose.html
- CFTC, Futures Glossary: https://www.cftc.gov/LearnAndProtect/AdvisoriesAndArticles/CFTCGlossary/index.htm
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, H.10 Foreign Exchange Rates: https://www.federalreserve.gov/releases/H10/current/
- SEC EDGAR, Southwest Airlines 2025 Form 10-K filing detail: https://www.sec.gov/Archives/edgar/data/92380/0000092380-26-000004-index.htm
