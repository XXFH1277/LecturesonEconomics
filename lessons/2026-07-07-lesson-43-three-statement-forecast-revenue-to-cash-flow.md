# 第四十三课：三表预测入门：从收入驱动到利润、现金流和每股指标

## 基本信息

- 日期：2026-07-07
- 数据截至：2026-07-07 20:40（Asia/Shanghai）；公司财务采用 Microsoft 2026-04-29 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q，并回接 Salesforce、Snowflake、Datadog 的最新 SEC 披露作为收入驱动案例；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 Federal Reserve H.15 2026-07-06 release。
- 主题：为什么收入预测不能停在收入表格，而要继续传导到毛利、费用、资本开支、现金流和股数。
- 学习目标：理解 Forecast Driver、Gross Margin、Operating Expense Ratio、Operating Leverage、Working Capital Schedule、Capex Schedule、Free Cash Flow、Share Count Forecast、Scenario，并学会搭建零基础三表预测的最小框架。
- 相关资产：股票、软件公司、AI 云资本开支、自由现金流、每股指标、DCF 输入、利率、估值质量。
- 已核验来源（核心来源）：
  - Microsoft Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
  - Microsoft SEC filing directory, accession 0001193125-26-191507: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
  - Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
  - Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲收入增长从哪里来。今天继续问：

> 如果我预测收入增长 10%，为什么还不能直接说公司价值也增长 10%？

因为股东最终拿到的不是“收入”，而是收入扣掉成本、费用、税、资本开支、营运资本占用和股数变化之后的每股现金流。收入只是三表模型的第一行。

### 参考的教材式概念顺序

1. Revenue Forecast：先预测收入驱动，而不是只填增长率。
2. Gross Margin：收入扣除直接成本后剩下多少。
3. Operating Expense Ratio：研发、销售营销、管理费用占收入比例。
4. Operating Leverage：收入增长快于费用增长时，利润率可能扩张。
5. Tax and Interest：营业利润还要扣利息和税。
6. Working Capital：收入增长会影响应收、递延收入、应付和库存。
7. Capex：增长需要多少资本开支，尤其是 AI 云基础设施。
8. Free Cash Flow：经营现金流扣资本开支后才接近估值输入。
9. Share Count：回购和股权激励决定每股指标。
10. Scenario：预测不是单点答案，而是 Base / Bull / Bear 的假设区间。

### 核心概念

零基础三表预测可以先搭成一条链：

```text
Revenue
- Cost of Revenue
= Gross Profit
- Operating Expenses
= Operating Income
- Interest and Taxes
= Net Income
+ Non-cash Expenses
+/- Working Capital Changes
= Operating Cash Flow
- Capex
= Free Cash Flow
/- Share Repurchases and Dilution
= Per-share Cash Flow View
```

这不是完整投行模型，而是学习用的最小骨架。它的目的不是给出一个精确股价，而是训练你发现：哪一个假设在控制结论。

### 用自己的话解释

收入像水龙头进水，毛利率像水管里第一层漏损，营业费用像研发、销售和管理的日常消耗，营运资本像水先卡在应收账款或递延收入里，资本开支像为了让系统继续运转必须买设备，股数像最后分水的人数。

所以收入增长只是“水进来了”。如果云基础设施成本、AI 训练和推理成本、销售费用、股权激励、回购和资本开支同时上升，股东最终每股拿到的现金流可能并不会同步增长。

### 常见误区

- 误区一：收入增长等于利润增长。成本结构和费用率可能改变。
- 误区二：利润增长等于现金流增长。营运资本和资本开支会改变现金时点。
- 误区三：自由现金流增长等于每股价值增长。股数和回购价格也很重要。
- 误区四：毛利率稳定就不用看成本。AI 推理、云基础设施和数据中心成本可能改变成本结构。
- 误区五：三表模型越复杂越好。初学者先保证驱动清楚、口径一致、边界明确。

## 第二大板块：实时背景与市场传导

### 发生了什么

Microsoft FY2026 Q3 total revenue 为 828.86 亿美元，同比增长 18%；gross margin 为 560.58 亿美元；operating income 为 383.98 亿美元；net income 为 317.78 亿美元。分部上，Productivity and Business Processes revenue 为 350.13 亿美元，同比增长 17%；Intelligent Cloud revenue 为 346.81 亿美元，同比增长 30%；More Personal Computing revenue 为 131.92 亿美元，同比下降 1%。Microsoft Cloud revenue 为 545 亿美元，同比增长 29%；Azure and other cloud services revenue 增长 40%。

同一份 Microsoft 10-Q 披露，FY2026 Q3 net cash from operations 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元；截至 2026-03-31，cash、cash equivalents and short-term investments 为 782.72 亿美元，property and equipment, net 为 2,832.28 亿美元，purchases of property and equipment remaining in accounts payable 为 226 亿美元。这个案例说明：AI/cloud 收入增长很强，但资本开支和数据中心资产也会明显改变现金流。

Adobe Q2 FY2026 revenue 为 66.18 亿美元，同比增长 13%；gross profit 为 59.03 亿美元；GAAP operating income 为 22.38 亿美元；net income 为 17.12 亿美元；operating cash flow 为 21.65 亿美元；purchases of property and equipment 为 0.58 亿美元；repurchases of common stock 为 21.11 亿美元。Adobe 同季 diluted shares 为 4.02 亿股，低于上年同期 4.29 亿股。这个案例说明：资产较轻的软件公司也要把回购、股数、SBC、并购和递延收入接入三表。

### 为什么重要

Fed 2026-06-17 维持 federal funds rate 目标区间在 3.50%-3.75%；Fed H.15 2026-07-06 release 显示，2026-07-02 的 10 年期 Treasury constant maturity yield 为 4.49%，10 年期 TIPS yield 为 2.26%。

三表预测和利率背景的关系是：

- 无风险利率影响 DCF 的折现率，也影响债务成本和回购机会成本。
- AI 云扩张可能带来收入增长，也可能带来更高 capital intensity。
- 同样 10% 收入增长，在高毛利资产轻模式和高资本开支基础设施模式下，现金流含义不同。
- 每股价值要同时看 FCF、回购、股权激励和稀释股数。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Microsoft total revenue | 828.86 亿美元，+18% | Microsoft 2026-04-29 10-Q | 收入预测起点 |
| Microsoft Intelligent Cloud revenue | 346.81 亿美元，+30% | Microsoft 2026-04-29 10-Q | AI/cloud 增长 |
| Microsoft Cloud revenue | 545 亿美元，+29% | Microsoft 2026-04-29 10-Q | 云收入驱动 |
| Microsoft Azure and other cloud services growth | +40% | Microsoft 2026-04-29 10-Q | 用量和云需求 |
| Microsoft operating income | 383.98 亿美元 | Microsoft 2026-04-29 10-Q | 利润表传导 |
| Microsoft net cash from operations | 466.79 亿美元 | Microsoft 2026-04-29 10-Q | 现金流表传导 |
| Microsoft additions to property and equipment | 308.76 亿美元 | Microsoft 2026-04-29 10-Q | Capex 强度 |
| Microsoft property and equipment, net | 2,832.28 亿美元 | Microsoft 2026-04-29 10-Q | 资产负债表传导 |
| Adobe total revenue | 66.18 亿美元，+13% | Adobe 2026-06-11 8-K | 收入预测起点 |
| Adobe gross profit | 59.03 亿美元 | Adobe 2026-06-11 8-K | 毛利率传导 |
| Adobe operating cash flow | 21.65 亿美元 | Adobe 2026-06-11 8-K | 现金流表传导 |
| Adobe purchases of property and equipment | 0.58 亿美元 | Adobe 2026-06-11 8-K | 资产轻对照 |
| Adobe repurchases of common stock | 21.11 亿美元 | Adobe 2026-06-11 8-K | 每股指标 |
| Adobe diluted shares | 4.02 亿股；上年同期 4.29 亿股 | Adobe 2026-06-11 8-K | 股数预测 |
| Federal funds target range | 3.50%-3.75% | Fed 2026-06-17 FOMC statement | 利率背景 |
| 10-year Treasury / 10-year TIPS | 4.49% / 2.26%（2026-07-02） | Fed H.15 2026-07-06 release | 折现率和实际利率背景 |

## 三表预测的最小步骤

### 第一步：收入表不要只填一个增长率

从第 42 课接过来，收入预测至少要问：

```text
收入增长 =
  客户数增长
+ 每客户用量增长
+ 价格变化
+ 产品组合变化
+ 并购贡献
+/- 汇率影响
```

Microsoft 的例子里，Intelligent Cloud 增长 30%、Azure and other cloud services 增长 40%，说明云和 AI 相关需求是收入增量的核心来源之一。Adobe 的例子里，reported revenue +13%、constant currency +11%，说明汇率对 reported revenue 有帮助；同时 Semrush 并购给 Customer Group subscription revenue 带来约 4,000 万美元 contribution。

### 第二步：把收入接到毛利率

毛利率公式：

```text
Gross Margin = Gross Profit / Revenue
```

Microsoft Q3 FY2026：

```text
Gross Margin = 560.58 / 828.86 = 约 67.6%
```

Adobe Q2 FY2026：

```text
Gross Margin = 59.03 / 66.18 = 约 89.2%
```

这两个公司都是软件和云相关企业，但毛利率差异很大。原因之一是 Microsoft 的云和 AI 基础设施成本更重，Adobe 传统上更偏资产轻订阅软件。预测时不能把一家公司的毛利率直接套到另一家公司。

### 第三步：把毛利接到营业费用和经营杠杆

营业利润公式：

```text
Operating Income = Gross Profit - R&D - Sales & Marketing - G&A - Other Operating Expenses
```

Microsoft Q3 FY2026 operating income 为 383.98 亿美元，operating margin 约 46.3%。Adobe Q2 FY2026 operating income 为 22.38 亿美元，operating margin 约 33.8%。

经营杠杆的直觉是：如果收入增长 18%，但费用只增长 9%，利润率可能扩张；如果为了 AI、销售和合规投入，费用增长快于收入，利润率可能收缩。模型里要把 R&D、Sales & Marketing、G&A 分开做，而不是只写一个总费用率。

### 第四步：把净利润接到经营现金流

经营现金流不是净利润。它会加回折旧摊销、SBC 等非现金费用，并调整应收账款、递延收入、应付账款和其他营运资本。

Microsoft Q3 FY2026：

```text
Net Income = 317.78 亿美元
Net Cash from Operations = 466.79 亿美元
```

Adobe Q2 FY2026：

```text
Net Income = 17.12 亿美元
Net Cash Provided by Operating Activities = 21.65 亿美元
```

差异不代表哪一个数字“假”。净利润按权责发生制，经营现金流按现金收付和营运资本变化。三表预测必须让这两者通过折旧、SBC、递延收入、应收账款等项目连接起来。

### 第五步：把经营现金流接到资本开支

自由现金流最小公式：

```text
Free Cash Flow = Operating Cash Flow - Capex
```

Microsoft Q3 FY2026 教学口径：

```text
FCF = 466.79 - 308.76 = 约 158.03 亿美元
```

Adobe Q2 FY2026 教学口径：

```text
FCF = 21.65 - 0.58 = 约 21.07 亿美元
```

这两个例子说明：同样是高质量科技公司，capital intensity 可以完全不同。Microsoft 为 AI/cloud 投入大量 property and equipment；Adobe 的资本开支相对轻，但仍要看并购现金流、回购和递延收入变化。

### 第六步：把自由现金流接到股数

每股视角：

```text
FCF per Share = Free Cash Flow / Diluted Shares
```

Adobe Q2 FY2026 diluted shares 为 4.02 亿股，低于上年同期 4.29 亿股，同季 repurchases of common stock 为 21.11 亿美元。这个案例说明：回购可以改善每股指标，但要付出现金。Microsoft Q3 FY2026 common stock repurchased 为 46.27 亿美元，同时 dividends paid 为 67.56 亿美元，说明成熟公司资本配置要同时看投资、回购和分红。

对初学者来说，不要只预测总 FCF，要继续预测：

```text
期初股数
+ SBC / option dilution
- net share repurchases
= 期末或平均稀释股数
```

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP、非 GAAP 指标披露、AI 基础设施投资、云服务数据中心建设、税法、Fed 利率政策、美国国债收益率曲线。
- 已确认事实：本课公司数据来自 SEC 文件；利率背景来自 Federal Reserve。
- 市场可能如何传导：高利率提高折现率和债务成本；AI/cloud capital intensity 提高时，市场会更重视自由现金流而不是单纯收入增长。
- 仍需核验或观察：AI 投资能否持续转化为收入和毛利，资本开支强度是否回落，SBC 和股数是否被回购抵消，云基础设施折旧是否压低未来利润率。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Forecast Driver | 预测驱动 | 模型里真正推动数字变化的变量 | 防止机械填增长率 |
| Gross Margin | 毛利率 | 毛利除以收入 | 连接收入和成本结构 |
| Cost of Revenue | 收入成本 | 为交付产品或服务发生的直接成本 | 云和 AI 成本会反映在这里 |
| Operating Expense Ratio | 营业费用率 | 研发、销售、管理费用占收入比例 | 决定经营杠杆 |
| Operating Leverage | 经营杠杆 | 收入增长快于费用增长时利润率扩张 | 衡量规模效应 |
| Working Capital Schedule | 营运资本表 | 应收、递延收入、应付等项目预测 | 把利润接到现金流 |
| Capex Schedule | 资本开支表 | 预测 property and equipment 投入 | AI/cloud 公司尤其重要 |
| Depreciation | 折旧 | 固定资产成本分期进入费用 | 连接资产负债表和利润表 |
| Free Cash Flow | 自由现金流 | 经营现金流扣资本开支 | DCF 和资本配置核心输入 |
| Share Count Forecast | 股数预测 | 预测回购、SBC 和稀释后的股数 | 决定每股指标 |
| Scenario | 情景 | Base、Bull、Bear 等假设组合 | 预测必须带边界 |
| Sensitivity | 敏感性 | 某个假设变化对结果的影响 | 找到模型最关键变量 |

## 回顾提示

- 学到本课前建议回顾：第 10 课三张报表、第 21 课营运资本、第 29 课自由现金流、第 30 课 DCF、第 31 课情景分析、第 41 课稀释与每股现金流、第 42 课收入驱动。
- 本课哪些内容会在后续课程继续使用：DCF、估值区间、敏感性表、回购收益率、资本配置、AI 基础设施投资回报。
- 如果看不懂本课，可以先回到：第 22 课毛利率、第 23 课营业费用、第 25 课 EPS、第 32 课 WACC。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的三表预测对照。
- 已确认事实：
  - Microsoft FY2026 Q3 revenue 为 828.86 亿美元，gross margin 为 560.58 亿美元，operating income 为 383.98 亿美元，net cash from operations 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元。
  - Microsoft Intelligent Cloud revenue 为 346.81 亿美元，同比增长 30%；Microsoft Cloud revenue 为 545 亿美元，同比增长 29%；Azure and other cloud services revenue 增长 40%。
  - Adobe Q2 FY2026 revenue 为 66.18 亿美元，gross profit 为 59.03 亿美元，operating income 为 22.38 亿美元，operating cash flow 为 21.65 亿美元，purchases of property and equipment 为 0.58 亿美元，repurchases of common stock 为 21.11 亿美元。
  - Adobe Q2 FY2026 diluted shares 为 4.02 亿股，低于上年同期 4.29 亿股。
- 来源日期和链接：见本课“来源”。
- 分析推理：Microsoft 展示高增长云业务如何伴随高资本开支；Adobe 展示资产较轻订阅软件如何把收入、毛利、现金流、回购和股数连起来。
- 后续验证指标：revenue growth by segment、gross margin、R&D ratio、sales and marketing ratio、deferred revenue、accounts receivable、capex、depreciation、SBC、repurchases、diluted shares、10-year Treasury yield。

## 个人情境连接

- 对关注清单的启发：关注公司时，可以先写一个 6 行小模型，而不是直接看目标价。
- 对持仓或基金选择的启发：AI 云主题基金不只看收入增长，还要看资本开支强度、折旧、现金流和股数。
- 对工作、收入、消费或风险管理的启发：个人收入增长也不等于自由现金流增长；如果设备、学习、获客和税费投入上升，剩余现金未必同步增加。

## 结论边界

- 可以确定：三表预测的核心是驱动假设联动，不是把历史增长率机械外推。
- 不能确定：本课不能用简化模型给出 Microsoft、Adobe 或任何公司的内在价值结论。
- 需要继续观察：AI 基础设施投资是否带来足够收入和毛利，资本开支是否保持高位，回购是否超过 SBC 稀释，利率是否改变折现率。
- 不构成投资建议的原因：本课只训练财务预测框架，不推荐买入或卖出任何证券。

## 练习题

1. 为什么收入增长 10% 不一定带来净利润增长 10%？
2. Microsoft Q3 FY2026 operating cash flow 为 466.79 亿美元，capex 为 308.76 亿美元。教学口径下 FCF 约是多少？
3. Adobe Q2 FY2026 operating cash flow 为 21.65 亿美元，capex 为 0.58 亿美元。教学口径下 FCF 约是多少？
4. 为什么三表模型要预测股数，而不是只预测净利润？
5. 如果 10 年期 Treasury yield 从 4.49% 升到 5.00%，你认为三表模型本身哪些行不变，DCF 或估值输入哪些地方会变？

## 学习交接

- 本课已经完成：把第 42 课的收入驱动继续接到毛利、费用、经营现金流、资本开支、自由现金流和股数。
- 本课最重要的一句话：预测不是填数字，而是把收入、成本、资产、现金流和股数用同一组假设连起来。
- 需要复习的关键词：Forecast Driver、Gross Margin、Operating Expense Ratio、Operating Leverage、Working Capital Schedule、Capex Schedule、Free Cash Flow、Share Count Forecast、Scenario、Sensitivity。
- 还不稳定、下次要回看的地方：如何把 Base / Bull / Bear 情景和敏感性表接到 DCF、估值倍数和安全边际。
- 适合下次打开仓库先读的文件：`lessons/2026-07-07-lesson-43-three-statement-forecast-revenue-to-cash-flow.md`

## 下节课安排

- 建议主题：第四十四课：情景假设、敏感性表与估值输入入门。
- 学习目标：理解如何围绕收入增长、毛利率、费用率、资本开支、WACC、终值增长率和股数建立 Base / Bull / Bear，并看哪些假设最影响估值结论。
- 建议案例：继续使用 Microsoft、Adobe、Salesforce、Snowflake 和 Datadog；用同一组收入驱动分别观察成熟云平台、资产轻软件和消费型云服务。
- 必须解释的关键词：Base Case、Bull Case、Bear Case、Sensitivity Table、Key Driver、WACC、Terminal Growth、Exit Multiple、Margin of Safety。
- 下节课开始前需要联网核验的数据：上述公司最新 SEC/IR 披露、Fed H.15 最新利率、FOMC 最新声明或会议纪要、10 年期 Treasury、信用利差、公司最新回购和股数披露。

## 来源

- Microsoft Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
- Microsoft SEC filing directory, accession 0001193125-26-191507: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
- Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
- Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/
