# 第四十七课：组合暴露、相关性与再平衡入门

## 基本信息

- 日期：2026-07-12
- 数据截至：2026-07-12 20:04（Asia/Shanghai）。公司事实采用 Microsoft 2026-04-29 Form 10-Q XBRL 表、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 Federal Reserve H.15 release dated 2026-07-10。本课不使用未核验的实时股票价格、基金持仓或组合权重。
- 主题：为什么“持有多个名字”不等于真正分散；如何把观察清单升级成组合暴露、相关性和再平衡框架。
- 学习目标：理解 Exposure、Correlation、Diversification、Concentration、Position Sizing、Rebalancing 和 Scenario Shock 的入门含义；学会用事实来源把组合风险拆成公司特有风险、行业共同风险和宏观利率风险。
- 相关资产：股票、软件公司、云计算、AI 基础设施、自由现金流、利率、组合风险、观察清单。
- 核心来源：
  - Microsoft Form 10-Q XBRL income statement table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
  - Microsoft Form 10-Q XBRL cash flow table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-10: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经会把单个公司放进 Investment Memo、Watchlist 和 Research Log。今天的问题是：

> 如果观察清单里有 10 家公司，是不是就已经分散风险了？

不一定。10 个名字可能都在同一个行业、同一个利率环境、同一个 AI 资本开支周期、同一个美元汇率风险里。真正的分散不是“数量多”，而是风险来源不完全相同。

### 参考的教材式概念顺序

1. Exposure：你实际暴露在哪些风险来源上。
2. Concentration：某个风险来源是否过于集中。
3. Correlation：不同资产或公司是否经常同方向变化。
4. Diversification：让不同风险来源互相分散。
5. Position Sizing：用规模控制错误代价。
6. Rebalancing：当权重或风险偏离计划时重新调整。
7. Drawdown：从高点到低点的回撤。
8. Scenario Shock：假设某个宏观或行业变量突然变化，观察组合会怎样。

### 核心概念

一个最小组合暴露表可以这样写：

| 风险来源 | 相关对象 | 为什么相关 | 需要观察什么 |
| --- | --- | --- | --- |
| 利率 / WACC | 高估值成长股、长期现金流资产 | 折现率变化会改变估值输入 | Fed statement、H.15、10-year Treasury、TIPS |
| AI 基础设施资本开支 | 云平台、半导体、数据中心、软件生态 | 资本开支能支持增长，也会压低短期 FCF | capex、depreciation、FCF margin |
| 订阅收入质量 | SaaS、创意软件、云软件 | RPO/ARR/cRPO 影响收入可见度 | ARR、RPO、NRR、deferred revenue |
| 回购与股数 | 成熟软件公司 | 回购可能抵消 SBC 稀释，也可能消耗现金 | repurchases、SBC、diluted shares |
| 汇率 / FX | 跨国公司 | 美元变化影响 reported growth | constant currency、geographic revenue |

这个表不告诉你买什么，也不告诉你配多少。它只回答一个问题：如果某个风险来源出事，我的观察清单里哪些对象会一起受影响？

### 用自己的话解释

Exposure 像是站在雨里的哪个位置。你以为自己撑了三把伞，但如果三把伞都破在同一个地方，雨还是会淋到你。Correlation 是这些伞会不会在同一阵风里一起翻。Diversification 不是伞的数量，而是不同风险之间能不能互相抵消一部分。

Rebalancing 不是“跌了就买、涨了就卖”的口号，而是把组合重新拉回原来设定的风险边界。例如你原本只想让某一类风险占组合的一小部分，但因为价格上涨或新增买入，它变成了主导风险，就需要重新检查。

### 常见误区

- 误区一：股票数量多就等于分散。多个公司如果都受同一个利率、行业或情绪变量影响，分散效果有限。
- 误区二：相关性是固定的。危机或政策冲击时，平时不相关的资产也可能一起下跌。
- 误区三：再平衡等于预测短期涨跌。再平衡是风险管理，不是短线判断。
- 误区四：仓位控制只和信心有关。仓位还要看错误代价、流动性、相关性和个人现金流。
- 误区五：单公司研究做好了，组合自然就好。组合层面还要看共同暴露和情景冲击。

## 第二大板块：实时背景与市场传导

### 发生了什么

Microsoft FY2026 Q3 的 SEC XBRL 表显示，revenue 为 828.86 亿美元，operating income 为 383.98 亿美元，net cash from operations 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元。这说明它的组合暴露不能只写“软件”，还要写“AI/cloud 资本开支、数据中心、长期现金流和利率”。

Adobe 2026-06-11 SEC-filed earnings exhibit 显示，Q2 FY2026 revenue 为 66.18 亿美元，cash flows from operations 为 21.65 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%；FY2026 total revenue target 为 265.0 亿到 266.0 亿美元。Adobe 更偏订阅软件和资产轻现金流，但仍然暴露于 AI 产品转化、客户续费、RPO 转收入、回购、SBC、并购整合和宏观利率。

Federal Reserve 2026-06-17 FOMC statement 显示，政策利率目标区间维持在 3.50%-3.75%。Federal Reserve H.15 2026-07-10 release 显示，7 月上旬 10-year Treasury yield 约处于 4.48%-4.56% 区间，10-year TIPS yield 约处于 2.24%-2.31% 区间。这个利率背景会影响成长股、债券、现金、基金和公司融资成本之间的比较。

### 为什么重要

Microsoft 和 Adobe 都可以被粗略放进“软件/科技”观察清单，但它们的风险暴露并不完全一样：

- 共同暴露：利率、美元、科技估值、AI 叙事、企业软件预算、监管和竞争。
- Microsoft 特有重点：高资本开支、数据中心供给、AI/cloud 需求是否转化为未来 FCF。
- Adobe 特有重点：AI-first ARR、Semrush 并购、RPO 转收入、订阅续费、回购和股数。

如果一个组合同时有很多看似不同的科技公司，但共同暴露都指向“利率下降 + AI 增长兑现 + 企业预算强”，那么这个组合可能比表面上更集中。

### 本节采用的数据和来源

| 暴露维度 | 已核验事实 | 来源与日期 | 组合解释 |
| --- | ---: | --- | --- |
| Microsoft 经营规模 | revenue 828.86 亿美元 | SEC XBRL R2, 2026-04-29 | 大型云和软件平台暴露 |
| Microsoft 经营现金流 | 466.79 亿美元 | SEC XBRL R6, 2026-04-29 | 现金生成能力 |
| Microsoft 资本开支 | additions to property and equipment 308.76 亿美元 | SEC XBRL R6, 2026-04-29 | AI/cloud 资本强度 |
| Adobe 经营规模 | revenue 66.18 亿美元，+13% | SEC 8-K exhibit 99.1, 2026-06-11 | 订阅软件增长暴露 |
| Adobe RPO / cRPO | 222.7 亿美元 / 67% | SEC 8-K exhibit 99.1, 2026-06-11 | 收入可见度暴露 |
| Adobe operating cash flow | 21.65 亿美元 | SEC 8-K exhibit 99.1, 2026-06-11 | 资产轻现金流对照 |
| Federal funds target range | 3.50%-3.75% | Fed FOMC statement, 2026-06-17 | 政策利率背景 |
| 10-year Treasury / 10-year TIPS | 7 月上旬约 4.48%-4.56% / 2.24%-2.31% | Fed H.15, 2026-07-10 | 长端名义和实际利率背景 |

### 这些现实事件如何连接理论

一个入门组合暴露地图可以先这样写：

```text
观察清单：Microsoft、Adobe

共同暴露：
- 科技估值和利率
- 企业软件预算
- AI 产品叙事
- 美元和国际收入

Microsoft 更强暴露：
- AI/cloud capex
- 数据中心供给
- 资本开支转 FCF 的速度

Adobe 更强暴露：
- 订阅收入质量
- RPO/cRPO 转收入
- 回购和股数
- Semrush 并购整合
```

这个地图能帮助初学者避免一个错误：看到两个不同公司名称，就以为风险已经分散。真正要问的是，它们在什么情景下会一起承压，在什么情景下会表现不同。

### 至少一个真实市场机制案例

真实市场机制是利率冲击。假设 10-year Treasury 和 10-year TIPS 上升，可能出现几条传导：

```text
长端利率上升
-> WACC 或机会成本上升
-> 长期现金流折现价值承压
-> 高增长公司估值倍数可能收缩
-> 高资本开支公司的 FCF 质量被更严格审视
-> 组合里多个成长股可能同时下跌
```

这不是预测一定会发生，而是 Scenario Shock。它训练的是：当一个共同变量变化时，观察清单里的对象是否会一起受影响。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Fed 利率政策、SEC 披露制度、公司回购披露、前瞻性陈述、AI 基础设施投资、跨国软件收入和汇率。
- 已确认事实：公司数据来自 SEC 文件；利率数据来自 Federal Reserve；本课没有使用基金持仓、ETF 权重或实时价格。
- 市场可能如何传导：利率变化会影响估值输入和资产比较；企业预算变化会影响软件收入；AI 资本开支会影响现金流；回购和 SBC 会影响每股结果。
- 仍需核验或观察：下一轮公司披露、Fed 后续声明、H.15 利率、AI 投资回报、RPO 转收入、SBC 与回购对股数的净影响。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Exposure | 风险暴露 | 你实际受哪些变量影响 | 看清风险来源 |
| Correlation | 相关性 | 两个资产是否常同方向变化 | 判断分散是否真实 |
| Diversification | 分散化 | 用不同风险来源降低单一冲击 | 不等于简单增加数量 |
| Concentration | 集中度 | 某类风险是否占比过高 | 防止表面分散 |
| Position Sizing | 仓位控制 | 用规模限制错误代价 | 本课只讲概念，不给比例 |
| Rebalancing | 再平衡 | 让组合回到预设风险边界 | 管理偏离，不是预测 |
| Drawdown | 回撤 | 从高点到低点的下跌幅度 | 衡量承受压力 |
| Factor | 因子 | 共同驱动资产表现的变量 | 如利率、成长、质量、行业 |
| Sector | 行业板块 | 公司所属业务类别 | 粗分风险来源 |
| Scenario Shock | 情景冲击 | 假设某变量突然变化 | 压力测试组合 |
| WACC | 加权平均资本成本 | 股权和债务资金成本合成 | 利率影响估值的入口 |
| FCF Margin | 自由现金流率 | 自由现金流占收入比例 | 观察现金流质量 |

## 回顾提示

- 学到本课前建议回顾：第 4 课基金和 ETF、第 5 课利率、第 15 课估值倍数和利率、第 32 课 WACC、第 45 课反证指标、第 46 课研究日志。
- 本课哪些内容会在后续课程继续使用：基金与 ETF 持仓穿透、行业权重、费用率、指数方法论、组合复盘。
- 如果看不懂本课，可以先回到：第 1 课市场地图、第 3 课金融产品地图、第 29 课自由现金流收益率。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的组合暴露对照。
- 已确认事实：
  - Microsoft FY2026 Q3 revenue 为 828.86 亿美元，operating cash flow 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元。
  - Adobe Q2 FY2026 revenue 为 66.18 亿美元，operating cash flow 为 21.65 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%，FY2026 revenue target 为 265.0 亿到 266.0 亿美元。
  - Fed 2026-06-17 维持 federal funds target range 在 3.50%-3.75%；Fed H.15 2026-07-10 显示 7 月上旬 10-year Treasury yield 约 4.48%-4.56%，10-year TIPS yield 约 2.24%-2.31%。
- 来源日期和链接：见本课“来源”。
- 分析推理：
  - 两家公司共同暴露于科技估值、企业软件预算、AI 叙事和利率背景。
  - Microsoft 更需要观察高资本开支能否转化为未来 FCF。
  - Adobe 更需要观察订阅收入质量、RPO 转收入、回购和股数假设。
  - 如果组合里还有更多同类科技公司，共同暴露可能进一步集中。
- 后续验证指标：公司下一份 10-Q/8-K、capex、FCF margin、RPO/cRPO、ARR、SBC、repurchases、diluted shares、10-year Treasury、10-year TIPS、FOMC statement 或 minutes。

## 一个入门组合复盘页

```text
组合或观察清单名称：
数据截至：

主要对象：
1.
2.
3.

共同暴露：
1.
2.
3.

差异化暴露：
1.
2.
3.

情景冲击：
- 利率上升：
- 企业预算放缓：
- AI capex 回报不及预期：
- 美元明显走强：

再平衡触发：
- 某一类风险超过预设边界：
- 某个反证指标出现：
- 个人现金流或风险承受能力变化：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：给每个对象打标签，不只写公司名，还要写利率、行业、现金流、AI、汇率和监管暴露。
- 对持仓或基金选择的启发：基金名字不同，不代表底层持仓和风险来源不同；后续要学持仓穿透和指数方法论。
- 对工作、收入、消费或风险管理的启发：个人收入也有暴露。比如同一行业工资、股票、奖金和房贷利率可能一起受宏观环境影响。

## 结论边界

- 可以确定：组合风险必须看共同暴露、相关性和情景冲击，不能只数有多少个名字。
- 不能确定：本课不计算任何实际组合权重、实时相关系数、目标价或仓位比例。
- 需要继续观察：公司披露、Fed 利率、企业预算、AI 资本开支回报、基金持仓和指数方法论。
- 不构成投资建议的原因：本课只训练组合风险语言和复盘框架，不建议买入、卖出、持有或配置任何证券或基金。

## 练习题

1. 为什么持有 10 家科技公司也可能没有真正分散风险？
2. 用 Microsoft 和 Adobe 各写出两个共同暴露和两个差异化暴露。
3. 如果 10-year Treasury 明显上升，成长股组合可能通过哪些路径受影响？
4. 什么情况下再平衡不是“预测涨跌”，而是风险管理？
5. 为你自己的观察清单写一个 Scenario Shock：如果利率上升、企业预算放缓或美元走强，你需要重新检查什么？

## 学习交接

- 本课已经完成：把第 46 课的单公司研究记录推进到组合暴露、相关性、分散化、仓位控制概念和再平衡触发。
- 本课最重要的一句话：分散化不是名字数量，而是风险来源是否真的不同。
- 需要复习的关键词：Exposure、Correlation、Diversification、Concentration、Position Sizing、Rebalancing、Drawdown、Factor、Sector、Scenario Shock、WACC、FCF Margin。
- 还不稳定、下次要回看的地方：如何用基金公司官网和指数文件穿透 ETF 持仓、费用率、行业权重和指数方法论。
- 适合下次打开仓库先读的文件：`lessons/2026-07-12-lesson-47-portfolio-exposure-correlation-rebalancing.md`

## 下节课安排

- 建议主题：第四十八课：基金与 ETF 持仓穿透、费用率和指数方法论入门。
- 学习目标：理解基金不是一个黑箱，要从基金公司官网、招募说明书、定期报告、持仓、费率和指数方法论拆解真实风险暴露。
- 建议案例：可使用 SPY、QQQ 或其他主流 ETF 作为教学案例，但必须在开课前重新核验基金公司官网、招募说明书、持仓、费率、指数方法论和数据日期。
- 必须解释的关键词：Holdings、Expense Ratio、Benchmark、Index Methodology、Tracking Error、Turnover、Sector Weight、Top Holdings、Creation/Redemption、Premium/Discount。
- 下节课开始前需要联网核验的数据：基金公司官网的最新持仓、费率、资产规模、指数方法论、招募说明书或定期报告；如涉及市场价格、premium/discount 或收益率，必须使用交易所、基金公司或权威数据源，并注明数据日期。

## 来源

- Microsoft Form 10-Q XBRL income statement table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
- Microsoft Form 10-Q XBRL cash flow table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-10: https://www.federalreserve.gov/releases/h15/
