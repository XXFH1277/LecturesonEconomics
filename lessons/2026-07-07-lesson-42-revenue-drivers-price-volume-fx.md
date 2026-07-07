# 第四十二课：收入增长拆解、价格、用量、客户数与三表预测入门

## 基本信息

- 日期：2026-07-07
- 数据截至：2026-07-07 20:40（Asia/Shanghai）；公司财务采用 Salesforce 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-28 Form 10-Q、Snowflake 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-29 Form 10-Q、Datadog 2026-05-07 Form 8-K exhibit 99.1 与 2026-05-07 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 Federal Reserve H.15 2026-07-06 release。
- 主题：为什么“收入增长 13%”还要继续拆成客户数、用量、价格、产品组合、汇率和并购。
- 学习目标：理解 Revenue Driver、Price、Volume、Usage、Customer Count、Product Mix、FX、Constant Currency、Organic Growth、Acquired Growth，并学会把收入增长拆解接到下一课的三表预测。
- 相关资产：SaaS、软件公司、云消费、订阅收入、AI 产品、RPO、ARR、汇率、并购、财务预测。
- 已核验来源（核心来源）：
  - Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
  - Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
  - Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
  - Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
  - Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
  - Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲股权激励、Non-GAAP、回购和每股现金流。今天开始把单个指标推到简化模型：

> 公司收入增长了，究竟是因为客户更多、客户用得更多、价格更高、产品结构更好、汇率帮忙，还是因为买了别的公司？

这几个原因对应的质量不一样。客户数增长说明市场渗透；用量增长说明客户更依赖产品；价格增长说明定价权；产品组合改善说明卖出了更高价值的产品；汇率只是换算影响；并购增长需要继续看买入价格、整合成本和有机增长。

### 参考的教材式概念顺序

1. Revenue Driver：先把收入当成“驱动因素的结果”，而不是单个数字。
2. Price：单价或合同价格变化。
3. Volume / Usage：销量、座席数、API 调用、计算资源、存储或其他用量。
4. Customer Count：客户数、付费客户数、大客户数。
5. Product Mix：不同产品、分部、地区或客户群占比变化。
6. FX / Constant Currency：汇率把外币收入换算成美元后的影响。
7. Organic Growth：不靠并购的内生增长。
8. Acquired Growth：并购带来的新增收入。
9. Forecast：把上述驱动变成下一期收入假设。
10. Three-statement Model：把收入假设继续推到利润表、资产负债表和现金流量表。

### 核心概念

最小收入公式：

```text
Revenue = Customer Count x Average Revenue per Customer
```

对消费型云服务，可以拆成：

```text
Revenue = Customer Count x Average Usage x Price per Unit
```

对多产品软件公司，可以继续拆成：

```text
Total Revenue =
  Product A Revenue
+ Product B Revenue
+ Services Revenue
+ Acquired Revenue
+ FX Translation Impact
```

最重要的教学提醒：收入增长率不是结论，而是问题的开头。

### 用自己的话解释

假设一家奶茶店收入增长 20%。可能是客人多了，可能是每杯涨价了，可能是大家买更贵的大杯，可能是开了新店，也可能是把旁边咖啡店买下来并表。软件公司也是一样，只是“杯数”变成客户数、席位数、计算资源、API 调用、数据量、合同容量和订阅模块。

所以看财报时，不能只说“收入增长快”。要问：这个增长来自哪里？能不能持续？要花多少销售费用、研发费用和云基础设施成本才能维持？会不会被汇率、并购或一次性合同扭曲？

### 常见误区

- 误区一：收入增长高就一定质量高。并购、汇率和一次性大单也可能推高增长。
- 误区二：constant currency 增长等于真实增长。它只是剔除汇率换算影响，仍可能包含价格、客户、用量和并购。
- 误区三：RPO 高就等于未来收入一定高。消费型模型下，收入确认取决于客户实际消耗。
- 误区四：客户数增长就一定好。还要看每客户收入、留存率、毛利率和获客成本。
- 误区五：价格上涨就一定好。过度提价可能带来流失、降级或竞争替代。

## 第二大板块：实时背景与市场传导

### 发生了什么

Salesforce Q1 FY2027 revenue 为 111.33 亿美元，同比增长 13%，constant currency 增长 12%；其中 subscription and support revenue 为 105.93 亿美元，同比增长 14%，constant currency 增长 12%，并包含 4.28 亿美元 Informatica contribution。Salesforce 10-Q 进一步说明，本季 subscription and support revenue 的增长主要由 volume-driven new business 推动，包括新客户、升级和现有客户增加订阅，pricing 不是本期收入增长的重要驱动。

Snowflake Q1 FY2027 product revenue 为 13.343 亿美元，同比增长 34%；total revenue 为 13.9095 亿美元，同比增长 33%；net revenue retention rate 为 126%；过去 12 个月 product revenue 超过 100 万美元的客户数为 779 个。Snowflake 10-Q 说明，公司按客户消耗 compute、storage 和 data transfer 资源确认收入，因此 RPO 不能机械等同于未来 product revenue growth。

Datadog Q1 2026 revenue 为 10.064 亿美元，同比增长 32%；ARR 超过 10 万美元的客户约 4,550 个，同比增长 21%。Datadog 10-Q 披露，截至 2026-03-31，约 56% 客户使用四个或更多产品，约 35% 使用六个或更多产品，约 20% 使用八个或更多产品，约 11% 使用十个或更多产品。这个案例适合观察 product adoption 和 usage expansion。

Adobe Q2 FY2026 revenue 为 66.18 亿美元，同比增长 13%，constant currency 增长 11%；Total Customer Group subscription revenue 为 63.9 亿美元，同比增长 14%，constant currency 增长 12%，其中包含约 4,000 万美元 Semrush contribution。Adobe 10-Q 还披露，美元相对 EMEA 货币走弱带来约 1.16 亿美元收入换算增量，但现金流套期保值损失抵消了其中约 2,200 万美元。

### 为什么重要

Fed 2026-06-17 维持 federal funds rate 目标区间在 3.50%-3.75%；Fed H.15 2026-07-06 release 显示，2026-07-02 的 10 年期 Treasury constant maturity yield 为 4.49%，effective federal funds rate 为 3.63%。

利率不低时，市场更重视增长质量：

- 客户数和用量增长更容易支撑未来收入预测。
- 价格驱动要看客户是否接受，不能只看短期收入。
- 产品组合改善要继续传导到毛利率和经营利润率。
- 汇率和并购需要从 organic growth 中分离出来。
- 消费型云收入要看客户实际消耗，不宜只看合同金额。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Salesforce revenue | 111.33 亿美元，+13%；constant currency +12% | Salesforce 2026-05-27 8-K | 总增长和汇率口径 |
| Salesforce subscription and support revenue | 105.93 亿美元，+14%；含 4.28 亿美元 Informatica contribution | Salesforce 2026-05-27 8-K、2026-05-28 10-Q | 订阅收入、并购增长 |
| Salesforce revenue driver | volume-driven new business；pricing not significant | Salesforce 2026-05-28 10-Q | 客户、升级、订阅扩容 |
| Snowflake product revenue | 13.343 亿美元，+34% | Snowflake 2026-05-27 8-K、2026-05-29 10-Q | 消费型云收入 |
| Snowflake net revenue retention | 126% | Snowflake 2026-05-27 8-K | 现有客户扩容 |
| Snowflake >$1M product revenue customers | 779 个，+29% | Snowflake 2026-05-27 8-K、2026-05-29 10-Q | 大客户数量 |
| Datadog revenue | 10.064 亿美元，+32% | Datadog 2026-05-07 8-K、10-Q | 订阅与用量型增长 |
| Datadog ARR >$100K customers | 约 4,550 个，+21% | Datadog 2026-05-07 8-K | 客户数质量 |
| Datadog product adoption | 56% 客户使用 4+ 产品，35% 使用 6+ 产品 | Datadog 2026-05-07 10-Q | 产品组合与扩容 |
| Adobe revenue | 66.18 亿美元，+13%；constant currency +11% | Adobe 2026-06-11 8-K | 总增长和汇率口径 |
| Adobe Customer Group subscription revenue | 63.9 亿美元，+14%；constant currency +12%；含约 4,000 万美元 Semrush | Adobe 2026-06-11 8-K | 产品组和并购贡献 |
| Adobe FX impact | Q2 美元换算收入增量约 1.16 亿美元，套保损失抵消约 2,200 万美元 | Adobe 2026-06-15 10-Q | 汇率和套期保值 |
| Federal funds target range | 3.50%-3.75% | Fed 2026-06-17 FOMC statement | 利率背景 |
| 10-year Treasury constant maturity | 4.49%（2026-07-02） | Fed H.15 2026-07-06 release | 折现率背景 |

### Salesforce：同样是 13% 增长，要拆出并购和有机增长

Salesforce Q1 FY2027 total revenue 增长 13%，但披露中同时出现了三个重要口径：

```text
Reported revenue growth = 13%
Constant currency revenue growth = 12%
Informatica contribution = 4.44 亿美元 total revenue
```

这说明学习者不能只拿 13% 做预测。更稳的分析顺序是：

```text
先看 reported growth
再剔除 FX 看 constant currency
再剔除 acquisition contribution 看 organic growth
最后看公司说明的业务驱动：新客户、升级、追加订阅、价格
```

Salesforce 10-Q 明确说本季 subscription and support revenue 增长主要来自 volume-driven new business，包括新客户、升级和现有客户增加订阅，pricing 不是重要驱动。这个表述非常适合零基础学习：收入增长不是“价格 x 数量”那么简单，但最终仍要回到价格、客户和用量。

### Snowflake：消费型收入看客户消耗，不只看合同

Snowflake 的核心收入是 product revenue，Q1 FY2027 为 13.343 亿美元，同比增长 34%。公司 net revenue retention rate 为 126%，说明现有客户总体上还在扩容；同时，product revenue 超过 100 万美元的大客户达到 779 个。

但 Snowflake 10-Q 也提醒：它按客户 consume compute、storage、data transfer resources 来确认收入，RPO 受续约时点、合同规模、平均合同期限、季节性、汇率和未使用容量 rollover 影响，不一定直接代表未来 product revenue growth。

教学上可以这样拆：

```text
Snowflake revenue growth =
  新客户
+ 现有客户更多 workload
+ 大客户数量增加
+ AI / data workloads 迁移
- 客户优化消耗、压缩存储、提升效率
+/- 合同和汇率时点
```

这也是消费型云公司和固定订阅软件的关键区别：同样是签合同，收入确认节奏可能完全不同。

### Datadog：产品组合能推动每客户收入

Datadog Q1 2026 revenue 同比增长 32%，ARR 超过 10 万美元客户约 4,550 个，同比增长 21%。如果收入增长快于大客户数量增长，初学者就要继续问：是不是每个大客户买了更多产品、用得更多或价格更高？

Datadog 10-Q 给了一个产品组合线索：截至 2026-03-31，约 56% 客户使用四个或更多产品，35% 使用六个或更多产品，20% 使用八个或更多产品，11% 使用十个或更多产品。这个信息不能直接变成收入预测，但它告诉我们增长可能不只是新客户，还包括 cross-sell 和 product adoption。

教学拆解：

```text
Datadog revenue growth =
  客户数增加
+ 大客户数增加
+ 每客户使用更多产品
+ 使用量或承诺用量增加
+ 可能的价格和套餐变化
- 云基础设施成本、销售费用和竞争压力
```

### Adobe：汇率、并购和产品组要分开看

Adobe Q2 FY2026 revenue 为 66.18 亿美元，reported growth 为 13%，constant currency growth 为 11%。这个差异提醒我们：当美元走弱时，海外收入换算成美元可能增加；当美元走强时，同样的海外本币收入换算成美元可能减少。

Adobe 10-Q 披露，本季美元相对 EMEA 货币走弱带来约 1.16 亿美元收入换算增量，但现金流套保损失抵消约 2,200 万美元。Adobe 8-K 还披露 Customer Group subscription revenue 增长中包含约 4,000 万美元 Semrush contribution。

教学拆解：

```text
Adobe subscription growth =
  Creative & Marketing Professionals
+ Business Professionals & Consumers
+ AI-first ARR 和新产品
+ Semrush acquired revenue
+/- FX translation
+/- hedging impact
```

因此，在做三表预测前，必须先把增长拆干净。否则下一课里毛利率、销售费用率、资本开支和每股指标都会建立在错误的收入假设上。

### 这些现实事件如何连接理论

- Salesforce 适合观察 reported growth、constant currency、acquired growth 和公司直接披露的 volume-driven new business。
- Snowflake 适合观察消费型云服务中 customer consumption、RPO 和 NRR 的边界。
- Datadog 适合观察客户数、大客户数和多产品采用率怎样推动每客户收入。
- Adobe 适合观察汇率、套期保值、并购和产品组收入如何共同影响 reported revenue。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP 收入确认、非 GAAP constant currency 指标披露、并购整合、数据安全和 AI 监管、Fed 利率政策、美元汇率和企业套期保值。
- 已确认事实：本课公司事实来自 SEC 文件；利率背景来自 Federal Reserve。
- 市场可能如何传导：利率较高时，市场对“增长质量”的要求更高，低质量或不可持续增长更容易被压低估值倍数。
- 仍需核验或观察：公司是否持续披露相同口径，AI 产品是否真正带来新增付费，消费优化是否压制用量增长，美元汇率是否继续影响 reported revenue。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Revenue Driver | 收入驱动 | 推动收入变化的原因 | 是三表预测的起点 |
| Price | 价格 | 单价、订阅价、每单位用量价格 | 代表定价权，也可能影响流失 |
| Volume | 销量 | 卖出的数量或服务量 | 传统行业常用 |
| Usage | 用量 | 云资源、API、数据、座席或功能使用量 | 消费型软件核心驱动 |
| Customer Count | 客户数 | 付费客户或大客户数量 | 判断渗透率和销售效率 |
| Product Mix | 产品组合 | 不同产品收入占比变化 | 会影响毛利率和增长质量 |
| FX | 外汇 | 汇率换算影响 | 跨国公司 reported revenue 会受影响 |
| Constant Currency | 固定汇率 | 剔除汇率变动后的增长口径 | 更接近业务本身变化 |
| Organic Growth | 内生增长 | 不靠并购带来的增长 | 衡量核心业务健康度 |
| Acquired Growth | 并购增长 | 收购公司并表带来的收入 | 需要看买入价格和整合成本 |
| ARR | 年化经常性收入 | 把订阅收入年化的经营指标 | 观察订阅业务规模 |
| NRR | 净收入留存 | 现有客户收入留存和扩容后的比例 | 衡量老客户是否扩容 |
| Forecast | 预测 | 对未来收入、利润和现金流做假设 | 不是确定答案，而是假设体系 |
| Three-statement Model | 三表模型 | 利润表、资产负债表、现金流量表联动模型 | 把收入驱动转成现金流和每股指标 |

## 回顾提示

- 学到本课前建议回顾：第 18 课 RPO、第 29 课自由现金流、第 35 课增长质量、第 37 课客户留存、第 40 课 SaaS 现金流质量、第 41 课每股现金流。
- 本课哪些内容会在后续课程继续使用：收入预测、毛利率预测、销售费用率、资本开支、营运资本、自由现金流和估值输入。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 22 课毛利率、第 23 课营业费用、第 31 课情景分析。

## 案例拆解

- 案例对象：Salesforce、Snowflake、Datadog、Adobe 的收入驱动对照。
- 已确认事实：
  - Salesforce Q1 FY2027 revenue 为 111.33 亿美元，+13%，constant currency +12%，其中 Informatica contribution 为 4.44 亿美元。
  - Salesforce 10-Q 说明 subscription and support revenue 增长主要来自 volume-driven new business，pricing 不是重要驱动。
  - Snowflake Q1 FY2027 product revenue 为 13.343 亿美元，+34%，NRR 为 126%，>$1M product revenue customers 为 779 个。
  - Datadog Q1 2026 revenue 为 10.064 亿美元，+32%，ARR >$100K customers 约 4,550 个，56% 客户使用四个或更多产品。
  - Adobe Q2 FY2026 revenue 为 66.18 亿美元，+13%，constant currency +11%；Customer Group subscription revenue 中包含约 4,000 万美元 Semrush contribution。
- 来源日期和链接：见本课“来源”。
- 分析推理：同样的收入增长可以来自不同驱动；预测前必须先区分客户、用量、价格、产品组合、汇率和并购。
- 后续验证指标：customer count、ARR、NRR、RPO、cRPO、usage metrics、product revenue、constant currency growth、acquisition contribution、gross margin、sales and marketing expense。

## 个人情境连接

- 对关注清单的启发：看到收入增长时，先写出“增长来自哪里”的假设，不要直接跳到估值。
- 对持仓或基金选择的启发：软件基金重仓公司的增长质量，要穿透到客户数、用量、产品组合、并购和汇率。
- 对工作、收入、消费或风险管理的启发：个人收入也有类似驱动：客户更多、单价更高、服务更多、产品更高端、外币收入换算变化。

## 结论边界

- 可以确定：收入增长必须拆成驱动因素，reported growth、constant currency growth、organic growth 和 acquired growth不是同一个口径。
- 不能确定：本课不能仅凭一个季度判断公司长期增长质量，也不能用增长率直接判断估值便宜或昂贵。
- 需要继续观察：AI 产品是否转成付费收入，客户是否持续扩容，消费优化是否抵消用量增长，汇率和并购贡献是否持续。
- 不构成投资建议的原因：本课只训练收入拆解和预测前置框架，不推荐买入或卖出任何证券。

## 练习题

1. 一家公司 reported revenue growth 为 13%，constant currency growth 为 11%。这两个数字差异可能来自什么？
2. Salesforce 披露增长主要来自 volume-driven new business，pricing 不是重要驱动。请用自己的话解释这句话。
3. 为什么 Snowflake 的 RPO 不能直接除以季度数来预测收入？
4. Datadog 大客户数增长 21%，收入增长 32%，你会继续追问哪三个收入驱动？
5. Adobe 本季收入增长中同时有 FX 和 Semrush contribution。做预测时为什么要把它们单独列出来？

## 学习交接

- 本课已经完成：把第 41 课的每股现金流质量推进到收入增长拆解，建立了从 reported revenue 到 organic driver 的分析顺序。
- 本课最重要的一句话：收入增长率不是结论，而是预测模型的第一组假设。
- 需要复习的关键词：Revenue Driver、Price、Volume、Usage、Customer Count、Product Mix、FX、Constant Currency、Organic Growth、Acquired Growth、ARR、NRR、Forecast。
- 还不稳定、下次要回看的地方：如何把收入驱动继续接到毛利、费用、营运资本、资本开支、股数和自由现金流。
- 适合下次打开仓库先读的文件：`lessons/2026-07-07-lesson-42-revenue-drivers-price-volume-fx.md`

## 下节课安排

- 建议主题：第四十三课：三表预测入门：从收入驱动到利润、现金流和每股指标。
- 学习目标：理解收入预测如何传导到毛利率、营业费用、经营利润、税费、净利润、营运资本、资本开支、自由现金流和稀释股数。
- 建议案例：Microsoft 与 Adobe 做成熟公司对照，继续引用 Salesforce、Snowflake 和 Datadog 的收入驱动作为前置假设。
- 必须解释的关键词：Gross Margin、Operating Expense Ratio、Operating Leverage、Working Capital Schedule、Capex Schedule、Free Cash Flow、Share Count Forecast、Model Driver、Scenario。
- 下节课开始前需要联网核验的数据：Microsoft 最新 10-Q、Adobe 最新 10-Q/8-K、Fed H.15 利率、FOMC statement、相关公司的收入、毛利、费用、现金流、资本开支、回购和股数。

## 来源

- Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
- Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
- Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
- Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
- Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
- Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/
