# 第七十五课：基金持仓穿透与 ELN 暴露入门：N-PORT、NAV、公允价值层级、发行人集中度与分配税性

## 基本信息

- 日期：2026-08-03
- 数据截至：2026-08-03（Asia/Shanghai）。基金案例采用 SEC EDGAR 上 J.P. Morgan Exchange-Traded Fund Trust 的 Form NPORT-P，filing date 2026-05-29，period of report 2026-03-31；J.P. Morgan Asset Management 衍生品收益 ETF 说明采用页面所列 2026-05-31 数据；SEC N-PORT 和 Rule 2a-5 规则材料采用当前可访问版本；IRS 1099-DIV 和 Publication 550 采用当前可访问版本；Federal Reserve H.15 采用 2026-07-31 发布、数据截至 2026-07-30。
- 主题：为什么一个“股票收益型 ETF”里会出现 ELN，以及普通学习者如何从 N-PORT、NAV 和公允价值层级读懂基金暴露。
- 学习目标：理解 fund holdings、Form N-PORT、schedule of portfolio investments、NAV、fair value hierarchy、Level 1、Level 2、Level 3、equity-linked note、issuer concentration、Rule 144A/Section 4(a)(2)、valuation designee 和 distribution tax character。
- 相关资产：JPMorgan Equity Premium Income ETF（JEPI）、S&P 500 Index-linked ELNs、美国大盘股、短期货币市场基金、美国短端和长端利率。
- 核心来源：
  - SEC EDGAR, J.P. Morgan Exchange-Traded Fund Trust, JPMorgan Equity Premium Income ETF, Form NPORT-P, filed 2026-05-29, period 2026-03-31: https://www.sec.gov/Archives/edgar/data/1485894/000207169126012729/0002071691-26-012729-index.htm
  - SEC EDGAR, JPMorgan Equity Premium Income ETF, Schedule of Portfolio Investments as of 2026-03-31: https://www.sec.gov/Archives/edgar/data/1485894/000207169126012729/JPMEPIETF.htm
  - SEC, Investment Company Reporting Modernization Rules, Form N-PORT: https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/investment-company-reporting-modernization-rules
  - SEC, Good Faith Determinations of Fair Value: A Small Entity Compliance Guide: https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/good-faith-determinations-fair-value-small-entity-compliance-guide
  - J.P. Morgan Asset Management, Across the Derivative Income Universe: https://am.jpmorgan.com/us/en/asset-management/adv/investment-strategies/etf-investing/investment-ideas/across-the-derivative-income-universe/
  - IRS, Instructions for Form 1099-DIV: https://www.irs.gov/instructions/i1099div
  - IRS, Topic No. 404, Dividends and other corporate distributions: https://www.irs.gov/taxtopics/tc404
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-31: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上节课讲的是直接持有结构化票据时的税务和 1099。今天换成基金视角：

```text
如果我买的是 ETF，
为什么还要关心基金里面有没有 ELN 或结构化票据？
```

因为基金不是一个黑箱名字，而是一篮子资产的法律外壳。你买的是基金份额，基金再持有股票、债券、现金、期权、互换、ELN 或其他证券。对普通投资者来说，最小读表顺序是：

```text
基金目标
-> 投资策略
-> 实际持仓
-> 估值方式
-> 分配税性
-> 风险是否和自己的预期一致
```

### 参考的教材式概念顺序

1. Fund Holdings：基金持仓，基金实际持有什么资产。
2. NAV：基金净资产价值，基金资产减负债后的每份价值。
3. Schedule of Portfolio Investments：投资组合明细表，列出基金在报告日持有的资产。
4. Form N-PORT：注册基金向 SEC 报告月度投资组合信息的表格，其中季度末部分信息会公开。
5. Equity-Linked Note，ELN：股票挂钩票据，付款与股票或指数表现相关，同时带有发行人信用风险。
6. Issuer Concentration：发行人集中度，基金对少数发行人或交易对手的暴露是否过高。
7. Rule 144A / Section 4(a)(2)：非公开或限定转售证券常见豁免路径，通常意味着流动性和投资者群体不同于交易所股票。
8. Fair Value：公允价值，按市场报价或合理估值方法确定的价值。
9. Level 1 / Level 2 / Level 3：公允价值输入层级，说明估值依赖报价、可观察输入还是不可观察输入。
10. Valuation Designee：估值受托执行方，基金董事会可指定投资顾问等执行公允价值判断并接受监督。
11. Distribution Tax Character：分配税性，基金发的钱可能是普通股息、合格股息、资本利得分配、利息或 return of capital。

### 核心概念

基金穿透不是为了把每个持仓背下来，而是为了回答四个问题：

```text
1. 基金实际持有什么？
2. 这些资产靠什么估值？
3. 风险集中在哪些发行人、行业、指数或交易对手？
4. 分配给投资者的钱在税务上是什么性质？
```

公允价值层级不是“风险等级”。Level 1、Level 2、Level 3 主要说明估值输入：

```text
Level 1：活跃市场中相同资产的未调整报价
Level 2：可观察输入，例如类似证券报价、利率、信用风险、市场验证输入
Level 3：重大不可观察输入，例如模型假设
```

Level 2 不等于安全，也不等于不安全。它只说明估值不是直接用活跃交易所里同一资产的未调整报价，而是依赖可观察市场输入或定价服务、交易商报价等。

### 用自己的话解释

可以把 ETF 想成一个透明箱子：

```text
箱子外面写着：Equity Premium Income ETF
箱子里面可能有：大盘股、ELN、货币市场基金、现金、应收应付
箱子每天计算：NAV
箱子定期披露：持仓和估值层级
箱子定期分配：现金，但税性要看最终分类
```

如果只看基金名字或分配率，就会漏掉两个重要问题：

```text
第一，收益从哪里来？
第二，风险最终落在谁身上？
```

ELN 暴露意味着基金并不只是持有股票组合，还通过银行或证券公司发行的票据获得某种指数或期权收益结构。投资者看到的是 ETF 份额，但基金内部仍有发行人信用、估值、流动性和衍生品结构。

### 常见误区

- 误区一：ETF 名字里有股票，就只持有普通股票。许多主动或衍生品收益 ETF 会持有期权、ELN 或其他工具。
- 误区二：NAV 每天公布，所以底层资产都一定有交易所实时报价。NAV 可以包含 Level 2 或 Level 3 估值资产。
- 误区三：ELN 在基金里就没有发行人信用风险。基金承担的是基金层面的集中和估值风险，底层票据仍有发行人风险。
- 误区四：分配率等于投资收益率。分配可能来自股息、期权/ELN 收益、资本利得、return of capital 或其他来源。
- 误区五：Level 2 比 Level 3 就一定“低风险”。层级说明估值输入，不直接等于亏损概率。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC EDGAR 显示，J.P. Morgan Exchange-Traded Fund Trust 于 2026-05-29 提交 JPMorgan Equity Premium Income ETF 的 Form NPORT-P，period of report 为 2026-03-31。该 filing 的 Part F 投资组合明细表显示，JEPI 在 2026-03-31 的 net assets 为 43,961,132,308 美元，总投资为 43,797,953,288 美元。

该投资组合明细表显示，JEPI 的 common stocks 为 84.5%，价值 37,159,256,240 美元；equity-linked notes 为 13.9%，价值 6,103,727,732 美元；short-term investments 为 1.2%，价值 534,969,316 美元。ELN 条目均标注 linked to S&P 500 Index，并列出 Barclays Bank plc、BNP Paribas、BofA Finance LLC、National Bank of Canada、Royal Bank of Canada、Societe Generale SA 和 The Goldman Sachs Group, Inc. 等发行人或关联发行主体。表格脚注说明这些 ELN 属于 Rule 144A 或 Securities Act Section 4(a)(2) 下豁免注册的证券。

同一份投资组合明细表的估值说明显示，基金投资按美国 GAAP 和基金估值政策估值；有活跃市场报价的投资按市场价值估值，没有 readily available market quotations 的投资按董事会或其指定机制善意确定的 fair value。该表还列出公允价值层级：common stocks 全部列为 Level 1；equity-linked notes 全部列为 Level 2；short-term investment companies 列为 Level 1。

按 2026-03-31 披露值粗略计算，JEPI 的 ELN 发行人暴露中，BNP Paribas 相关 ELN 合计约 1.659 billion 美元，约为基金 net assets 的 3.8%；Royal Bank of Canada 相关 ELN 合计约 1.605 billion 美元，约为 net assets 的 3.7%；Societe Generale SA 相关 ELN 合计约 1.204 billion 美元，约为 net assets 的 2.7%。这些百分比是教学用的持仓穿透计算，不是未来风险预测。

SEC 的 Form N-PORT 规则说明，注册基金需要按月度投资组合信息向 SEC 报告，季度末的月度报告部分会公开，并包含 position-by-position 的完整持仓信息。SEC Rule 2a-5 相关说明则强调，当市场报价不 readily available 时，基金需要用善意确定的公允价值；董事会可在监督条件下指定 valuation designee 执行估值。

J.P. Morgan Asset Management 2026 年关于 derivative income ETF 的页面说明，JEPI 和 JEPQ 旨在提供月度收入和股票市场暴露，并以低于对应基准波动率为目标；该页面还提示，这些基金的收入分配主要按 qualified 或 ordinary income 纳税，投资者通常在分配发生年度纳税。IRS 1099-DIV 说明和 Topic No. 404 则提供了普通股息、合格股息、资本利得分配和 RIC/ETF 分配的税务入口。

Federal Reserve H.15 2026-07-31 release 显示，截至 2026-07-30，effective federal funds rate 为 3.63%，3-month Treasury bill secondary market rate 为 3.69%，10-year Treasury constant maturity 为 4.68%。这些利率不是 JEPI 的收益承诺，只是帮助学习者比较现金、短债和衍生品收益型 ETF 的利率背景。

### 为什么重要

JEPI 的案例让基金穿透变成一张最小读表卡：

| 项目 | 2026-03-31 披露值 | 学习含义 |
| --- | ---: | --- |
| Net assets | 43.961 billion 美元 | 基金规模口径 |
| Common stocks | 37.159 billion 美元，84.5% | 股票底仓 |
| Equity-linked notes | 6.104 billion 美元，13.9% | 衍生品/票据暴露 |
| Short-term investments | 0.535 billion 美元，1.2% | 现金管理和流动性 |
| ELN fair value level | Level 2 | 依赖可观察输入或定价服务，不是交易所股票报价 |
| ELN exemption note | Rule 144A / Section 4(a)(2) | 流动性和投资者群体要额外读 |

初学者要形成一个习惯：

```text
基金名字 -> 策略描述 -> SEC 持仓 -> 估值层级 -> 分配税性
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| JEPI NPORT-P filing date | 2026-05-29 | SEC EDGAR | 披露时点 |
| JEPI period of report | 2026-03-31 | SEC EDGAR | 持仓时点 |
| JEPI net assets | 43,961,132,308 美元 | SEC EDGAR, Part F | 基金规模 |
| JEPI common stocks | 37,159,256,240 美元，84.5% | SEC EDGAR, Part F | 股票底仓 |
| JEPI equity-linked notes | 6,103,727,732 美元，13.9% | SEC EDGAR, Part F | ELN 暴露 |
| JEPI short-term investments | 534,969,316 美元，1.2% | SEC EDGAR, Part F | 现金管理 |
| ELN valuation level | Level 2 | SEC EDGAR, Part F | 公允价值输入 |
| Common stocks valuation level | Level 1 | SEC EDGAR, Part F | 交易所报价 |
| SEC N-PORT rule | 季度末报告部分公开并包含逐仓位信息 | SEC | 持仓穿透入口 |
| EFFR / 3M T-Bill / 10Y CMT | 3.63% / 3.69% / 4.68% | Fed H.15, 2026-07-30 | 利率背景 |

### 这些现实事件如何连接理论

第一条链：ETF 名称到真实持仓。

```text
看到 Equity Premium Income ETF
-> 读 summary prospectus 和 strategy
-> 打开 N-PORT / holdings
-> 发现 common stocks + ELNs + short-term investments
-> 重新理解收益来源和风险来源
```

第二条链：ELN 到发行人集中度。

```text
基金持有多张 ELN
-> 每张 ELN 有发行人或交易对手
-> 按发行人汇总市值
-> 计算占 net assets 的比例
-> 判断是否需要关注发行人信用和集中度
```

第三条链：估值层级到 NAV。

```text
股票是 Level 1
-> 多数直接使用活跃市场报价

ELN 是 Level 2
-> 依赖可观察输入、类似工具报价、利率、信用、交易商或定价服务
-> NAV 可以计算，但不是每张 ELN 都像股票一样有交易所盘口
```

第四条链：分配到税性。

```text
基金发现金分配
-> 年末或次年看 1099-DIV 分类
-> 普通股息、合格股息、资本利得分配、return of capital 影响不同
-> 分配率不能直接等于税后总回报
```

### 至少一个真实市场机制案例

案例：用 JEPI 2026-03-31 N-PORT 做三步穿透。

```text
第一步：资产结构
Common stocks 84.5%
Equity-linked notes 13.9%
Short-term investments 1.2%

第二步：ELN 发行人
Barclays、BNP Paribas、BofA Finance、National Bank of Canada、
Royal Bank of Canada、Societe Generale、Goldman Sachs

第三步：估值层级
Common stocks: Level 1
Equity-linked notes: Level 2
Short-term investment companies: Level 1
```

这张表说明，买基金不等于不用看底层工具。基金外壳提供组合管理、分散、披露和 NAV 机制，但底层 ELN 的发行人、估值和流动性问题仍然会通过基金 NAV 和分配结果传递给持有人。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 注册基金披露制度、Form N-PORT、Investment Company Act of 1940、Rule 2a-5 公允价值规则、Rule 144A/Section 4(a)(2) 豁免证券、IRS 1099-DIV 分配分类。
- 已确认事实：SEC N-PORT 规则提供注册基金持仓穿透入口；JEPI 2026-03-31 N-PORT 披露 ELN 暴露为 13.9%；该表将 ELN 列为 Level 2；SEC Rule 2a-5 框架处理没有 readily available market quotations 的投资公允价值；IRS 1099-DIV 说明覆盖股息和其他分配报告。
- 市场可能如何传导：股票市场波动影响股票底仓；S&P 500 波动率和期权/ELN 定价影响 ELN 价值；银行发行人信用和交易商报价影响 ELN 估值；分配税性影响投资者税后现金流。
- 仍需核验或观察：后续 N-PORT、每日基金官方 holdings、年报/半年报、1099-DIV 年度分类、ELN 发行人信用、Level 2 估值输入、基金是否改变策略。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Fund Holdings | 基金持仓 | 基金实际买了什么资产 | 不能只看基金名字 |
| Form N-PORT | 基金投资组合报告 | 注册基金向 SEC 报告持仓和风险信息的表格 | 穿透基金的重要入口 |
| Schedule of Portfolio Investments | 投资组合明细表 | 报告日逐项列示持仓 | 可直接看股票、ELN、现金工具 |
| NAV | 净资产价值 | 基金资产减负债后的份额价值 | 申购赎回和表现计算基础 |
| Equity-Linked Note (ELN) | 股票挂钩票据 | 回报与股票或指数相关的票据 | 带来衍生品和发行人信用暴露 |
| Issuer Concentration | 发行人集中度 | 对少数发行人暴露占比 | 影响信用和流动性风险 |
| Rule 144A | 144A 规则 | 面向合格机构买家的转售豁免路径 | 提示流动性不同于公开交易股票 |
| Section 4(a)(2) | 私募发行豁免 | 非公开发行常用证券法豁免 | 要关注转售和估值限制 |
| Fair Value | 公允价值 | 按市场报价或合理估值方法确定的价值 | 决定 NAV |
| Level 1 | 第一层级输入 | 活跃市场相同资产的报价 | 估值透明度最高 |
| Level 2 | 第二层级输入 | 可观察输入或类似资产报价 | ELN 常落在这里 |
| Level 3 | 第三层级输入 | 重大不可观察输入和模型假设 | 估值不确定性更高 |
| Valuation Designee | 估值受托执行方 | 董事会指定执行公允价值判断的一方 | 决定估值治理 |
| Distribution Tax Character | 分配税性 | 基金发钱在税务上属于什么 | 影响税后回报 |

## 回顾提示

- 学到本课前建议回顾：第 4 课基金和 ETF，第 48-49 课 ETF 持仓与交易机制，第 67 课期权收益型 ETF，第 68-74 课 ELN、结构化票据和税务口径。
- 本课哪些内容会在后续课程继续使用：N-PORT 持仓穿透、Level 1/2/3、公允价值、发行人集中度、基金分配税性。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图，先分清基金外壳、债务工具、衍生品和股票所有权。

## 案例拆解

- 案例对象：JPMorgan Equity Premium Income ETF 2026-03-31 N-PORT / Schedule of Portfolio Investments。
- 已确认事实：
  - Form NPORT-P filing date 为 2026-05-29，period of report 为 2026-03-31。
  - Net assets 为 43,961,132,308 美元。
  - Common stocks 为 84.5%，价值 37,159,256,240 美元。
  - Equity-linked notes 为 13.9%，价值 6,103,727,732 美元。
  - ELN 均 linked to S&P 500 Index。
  - ELN 发行人包括 Barclays、BNP Paribas、BofA Finance、National Bank of Canada、Royal Bank of Canada、Societe Generale 和 Goldman Sachs。
  - ELN 被列为 Level 2 fair value inputs。
  - Common stocks 被列为 Level 1 fair value inputs。
- 来源日期和链接：见本课“来源”。
- 分析推理：JEPI 的收益来源不能只理解为股票股息。它还通过 ELN 获得与 S&P 500 和期权收益结构相关的暴露；这些 ELN 的发行人信用、估值输入和转售属性都会影响基金 NAV 和分配结果。
- 后续验证指标：下一期 N-PORT、基金官方每日 holdings、ELN 发行人名单变化、ELN 占 net assets 比例、Level 2/Level 3 变化、年度 1099-DIV 分类、基金分配率与 NAV 总回报。

## 持仓穿透最小清单

```text
一、先看资产类别
- 股票占比多少？
- 债券/票据/ELN 占比多少？
- 现金或货币市场基金占比多少？

二、再看发行人和交易对手
- ELN 来自哪些银行或证券公司？
- 单一发行人占 net assets 多少？
- 是否有 Rule 144A 或 Section 4(a)(2) 标注？

三、再看估值层级
- 哪些资产是 Level 1？
- 哪些资产是 Level 2？
- 是否出现 Level 3？
- 估值政策是谁执行、谁监督？

四、最后看分配税性
- 分配来自普通股息、合格股息、资本利得还是 ROC？
- 1099-DIV 如何分类？
- 税后总回报和现金分配是否一致？
```

## 个人情境连接

- 对关注清单的启发：以后看收益型 ETF，新增三列：`ELN/derivatives exposure`、`fair value level`、`top issuers/counterparties`。
- 对持仓或基金选择的启发：同样是月度分配 ETF，底层可能是卖出交易所期权、持有 ELN、使用 ROC 分配设计或侧重 NAV 增长，不能只按分配率排序。
- 对工作、收入、消费或风险管理的启发：如果依赖基金分配支付生活开支，要同时观察 NAV 总回报、税后分配和底层风险，而不是只看每月到账金额。

## 结论边界

- 可以确定：JEPI 2026-03-31 N-PORT 披露了 84.5% common stocks、13.9% equity-linked notes 和 1.2% short-term investments；该表把 ELN 列为 Level 2；SEC N-PORT 和 Rule 2a-5 提供基金持仓和估值治理的监管框架。
- 不能确定：本课不能预测 JEPI 未来收益、分配、税务分类、NAV 表现或 ELN 发行人信用变化，也不能判断该基金是否适合任何具体投资者。
- 需要继续观察：最新持仓、后续 N-PORT、年报/半年报、1099-DIV、分配公告、ELN 发行人集中度、Level 2/Level 3 变化、利率和波动率环境。
- 不构成投资建议的原因：本课只解释基金持仓穿透和估值框架，不建议买入、卖出或持有任何 ETF、基金、股票、票据、债券或衍生品。

## 练习题

1. 为什么基金 NAV 可以包含 Level 2 资产？
2. 用 JEPI 案例说明“股票收益型 ETF”为什么仍然需要看 ELN 暴露。
3. Level 2 和 Level 3 的区别是什么？为什么它们不是简单的风险评级？
4. 把 BNP Paribas、Royal Bank of Canada 和 Societe Generale 的 ELN 合计值分别除以 JEPI net assets，练习计算发行人集中度。
5. 为什么基金分配率不能直接等于税后总回报？

## 学习交接

- 本课已经完成：把结构化票据税务口径推进到基金层面的持仓穿透、ELN 暴露、NAV、公允价值层级、发行人集中度和分配税性。
- 本课最重要的一句话：买 ETF 不等于不用看底层工具，基金外壳会把股票、ELN、估值和分配税性组合成一个 NAV 和现金分配结果。
- 需要复习的关键词：Form N-PORT、NAV、Schedule of Portfolio Investments、ELN Exposure、Issuer Concentration、Rule 144A、Section 4(a)(2)、Fair Value、Level 1、Level 2、Level 3、Valuation Designee、Distribution Tax Character。
- 还不稳定、下次要回看的地方：收益型 ETF 的分配质量、19a notice、return of capital、NAV erosion、after-tax return 和总回报之间的关系。
- 适合下次打开仓库先读的文件：`lessons/2026-08-03-lesson-75-fund-holdings-eln-fair-value-hierarchy.md`

## 下节课安排

- 建议主题：第七十六课：收益型 ETF 分配质量与税后总回报入门：19a notice、return of capital、NAV erosion、after-tax return 和再投资假设。
- 学习目标：理解 distribution rate、30-day SEC yield、19a notice、return of capital、qualified dividend、ordinary dividend、capital gain distribution、NAV erosion、total return、after-tax return 和 reinvestment assumption。
- 建议案例：对比 JEPI/JEPQ、ROCY/ROCQ 或其他基金公司官方分配文件、19a notice、1099-DIV 说明、基金 NAV 总回报和 SEC yield。
- 必须解释的关键词：Distribution Rate、30-Day SEC Yield、19a Notice、Return of Capital、Qualified Dividend、Ordinary Dividend、Capital Gain Distribution、NAV Erosion、Total Return、After-Tax Return、Reinvestment Assumption。
- 下节课开始前需要联网核验的数据：至少两只收益型 ETF 的官方分配公告或 19a notice、基金公司税务分类材料、IRS 1099-DIV/Publication 550、SEC/Investor.gov ETF 分配与费用材料、最新 Fed H.15。

## 来源

- SEC EDGAR, JEPI Form NPORT-P Filing Detail: https://www.sec.gov/Archives/edgar/data/1485894/000207169126012729/0002071691-26-012729-index.htm
- SEC EDGAR, JEPI Schedule of Portfolio Investments as of 2026-03-31: https://www.sec.gov/Archives/edgar/data/1485894/000207169126012729/JPMEPIETF.htm
- SEC, Investment Company Reporting Modernization Rules: https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/investment-company-reporting-modernization-rules
- SEC, Good Faith Determinations of Fair Value: https://www.sec.gov/resources-small-businesses/small-business-compliance-guides/good-faith-determinations-fair-value-small-entity-compliance-guide
- J.P. Morgan Asset Management, Across the Derivative Income Universe: https://am.jpmorgan.com/us/en/asset-management/adv/investment-strategies/etf-investing/investment-ideas/across-the-derivative-income-universe/
- IRS, Instructions for Form 1099-DIV: https://www.irs.gov/instructions/i1099div
- IRS, Topic No. 404: https://www.irs.gov/taxtopics/tc404
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
