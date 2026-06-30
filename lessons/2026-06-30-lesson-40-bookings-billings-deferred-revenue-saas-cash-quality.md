# 第四十课：Bookings、Billings、递延佣金与 SaaS 现金流质量入门

## 基本信息

- 日期：2026-06-30
- 数据截至：2026-06-30 20:05（Asia/Shanghai）；公司财务采用 Salesforce 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-28 Form 10-Q、Datadog 2026-05-07 Form 8-K exhibit 99.1 与 Form 10-Q、Snowflake 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-29 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 U.S. Treasury 2026-06-29 最新可得收益率。
- 主题：为什么 SaaS 公司“签了单、开了票、收了钱、确认收入、产生自由现金流”不是同一件事。
- 学习目标：理解 Bookings、Billings、Deferred Revenue、Unearned Revenue、Deferred Commissions、Capitalized Contract Costs、Operating Cash Flow、Free Cash Flow 与收入确认之间的时间差。
- 相关资产：SaaS、订阅软件、云服务、收入确认、RPO、经营现金流、自由现金流、销售效率、估值质量。
- 已核验来源（核心来源）：
  - Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
  - Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
  - Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
  - Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
  - Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
  - Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-29: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲 Sales Efficiency、Magic Number 和 Rule of 40。今天继续问：

> 为什么一家软件公司明明增长很好，现金流却可能突然很强，也可能突然变弱？

初学者容易把“订单、开票、收款、收入、现金流”混在一起。SaaS 和云服务的难点在于：客户可能今天签多年合同，今天或未来开票，未来几个月或几年慢慢确认收入；销售佣金也可能今天支付，但按几年摊到费用里。

### 参考的教材式概念顺序

1. Bookings：先看客户承诺购买了多少。
2. Billings：再看公司向客户开票或产生应收的金额。
3. Deferred Revenue / Unearned Revenue：已经开票或收款，但还没有履约确认收入的负债。
4. Revenue Recognition：随着服务交付，把递延收入转成收入。
5. Deferred Commissions / Capitalized Contract Costs：销售佣金先资本化，再在未来期间摊销。
6. Operating Cash Flow：经营活动实际产生或消耗的现金。
7. Free Cash Flow：经营现金流扣除资本开支和必要的软件资本化支出后的现金。
8. Seasonality：续约、开票和大客户采购季节性会让单季现金流失真。

### 核心概念

入门关系可以这样记：

```text
Bookings = 客户新签或续签的合同承诺

Billings = 已经向客户开票或有权收款的金额

Deferred Revenue = 已开票或已收款，但还没有确认收入的部分

Revenue = 已经履约并按会计规则确认的收入
```

如果只做教学简化，在递延收入口径稳定、没有并购和汇率干扰时，可以粗略理解：

```text
Billings 近似值 = Revenue + Deferred Revenue 的增加额
```

但真实财报里这个公式很容易被并购、外汇、合同资产、提前收款、退款、专业服务、消费型合同和续约时间打断。因此正式分析时要读公司自己的注释，而不是只套公式。

现金流也要拆开看：

```text
Operating Cash Flow = 净利润 + 非现金费用 +/- 营运资本变化

Free Cash Flow = Operating Cash Flow - 资本开支 - 资本化软件开发支出（若公司这样定义）
```

### 用自己的话解释

Bookings 像“客户答应买多少”。Billings 像“公司已经开了多少账单”。Deferred Revenue 像“钱或账单到了，但服务还没交完，所以先记成负债”。Revenue 像“服务已经交付，可以确认收入”。Deferred Commissions 像“销售拿到佣金，但公司把这笔获客成本分几年摊销”。

所以 SaaS 现金流不是只看收入增长。收入增长可能来自前期订单消耗，现金流可能来自本季集中续约收款；也可能本季收入很好，但递延收入下降，说明确认收入跑得比开票更快。

### 常见误区

- 误区一：把 bookings、billings 和 revenue 当成同一个数字。它们分别代表承诺、开票和履约。
- 误区二：看到递延收入下降就直接说公司变差。递延收入可能受续约季节性、消费节奏、合同期限和并购影响。
- 误区三：看到经营现金流很强就直接年化。SaaS 第一季度或第四季度常受续约和收款集中影响。
- 误区四：把销售佣金当成当期全部费用。很多订阅公司会把部分合同取得成本资本化，再按受益期摊销。
- 误区五：用一家公司披露的 billings 口径机械比较另一家公司。固定订阅、消费型云、混合软件和专业服务的口径不一样。

## 第二大板块：实时背景与市场传导

### 发生了什么

Salesforce 2027 财年第一季度披露，revenue 为 111.33 亿美元，current RPO 为 336 亿美元，RPO 为 679 亿美元。10-Q 进一步披露，unearned revenue 从 243.17 亿美元降至 203.63 亿美元；同季度 `billings and other` 为 71.79 亿美元，确认收入包括 over time 104.86 亿美元和 point in time 6.47 亿美元。Salesforce 也说明，第四季度通常是新业务和续约最强季度，因此第一季度往往是收款和经营现金流最大的季度。

Datadog 2026 年第一季度披露，revenue 为 10.064 亿美元，operating cash flow 为 3.346 亿美元，free cash flow 为 2.891 亿美元。10-Q 披露 deferred revenue 合计约 12.821 亿美元，RPO 为 34.844 亿美元，deferred contract costs 为 2.180 亿美元，销售佣金相关合同取得成本按四年受益期摊销。

Snowflake 2027 财年第一季度披露，product revenue 为 13.343 亿美元，RPO 为 92.1 亿美元，free cash flow margin 为 16.7%。10-Q 披露 deferred revenue 合计约 28.775 亿美元，deferred commissions 合计约 4.349 亿美元；公司还说明递延收入在本季减少 5.285 亿美元，原因之一是预付 capacity agreements 的收入确认超过开票。

Adobe 2026 财年第二季度披露，revenue 为 66.18 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%，operating cash flow 为 21.65 亿美元。10-Q 披露 deferred revenue 为 72.5 亿美元，capitalized contract acquisition costs 为 7.82 亿美元，subscription revenue 为 64.16 亿美元。

### 为什么重要

Fed 2026-06-17 维持 federal funds rate 目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-29 的 10 年期 Treasury par yield 为 4.38%。利率仍不低时，市场更重视现金流质量：

- 如果增长靠真实新增客户、续约和扩容支撑，未来收入更有可见度。
- 如果自由现金流主要来自一季集中收款，不能直接年化。
- 如果递延佣金和合同成本持续堆高，要看未来收入和毛利能否覆盖这些先发生的获客投入。
- 如果 RPO 高但消费节奏不确定，不能把 RPO 机械等同于下一季度收入。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Salesforce revenue | 111.33 亿美元，+13% | Salesforce 2026-05-27 8-K | 总收入与订阅规模 |
| Salesforce current RPO / RPO | 336 亿美元 / 679 亿美元 | Salesforce 2026-05-27 8-K | 合同可见度 |
| Salesforce unearned revenue | 203.63 亿美元 | Salesforce 2026-05-28 10-Q | 递延收入案例 |
| Salesforce costs capitalized to obtain revenue contracts | current 20.65 亿美元；noncurrent 29.20 亿美元 | Salesforce 2026-05-28 10-Q | 递延佣金和合同取得成本 |
| Salesforce operating cash flow / capex | 67.01 亿美元 / 1.45 亿美元 | Salesforce 2026-05-28 10-Q | 单季现金流与季节性 |
| Datadog deferred revenue | current 12.3115 亿美元；noncurrent 0.5092 亿美元 | Datadog 2026-05-07 10-Q | 递延收入案例 |
| Datadog RPO | 34.844 亿美元 | Datadog 2026-05-07 10-Q | 已签未确认收入 |
| Datadog deferred contract costs | 2.180 亿美元 | Datadog 2026-05-07 10-Q | 佣金资本化 |
| Datadog free cash flow | 2.891 亿美元 | Datadog 2026-05-07 10-Q | FCF 口径 |
| Snowflake RPO | 约 92 亿美元 | Snowflake 2026-05-29 10-Q | 消费型云 RPO |
| Snowflake deferred commissions | 约 4.349 亿美元 | Snowflake 2026-05-29 10-Q | 递延佣金 |
| Snowflake deferred revenue change | 减少 5.285 亿美元 | Snowflake 2026-05-29 10-Q | 收入确认超过开票案例 |
| Adobe deferred revenue / RPO | 72.5 亿美元 / 222.7 亿美元 | Adobe 2026-06-15 10-Q | 订阅递延收入案例 |
| Adobe capitalized contract acquisition costs | 7.82 亿美元 | Adobe 2026-06-15 10-Q | 销售佣金资本化 |
| 10 年期 Treasury yield | 4.38% | U.S. Treasury, 2026-06-29 | 折现率和现金流质量背景 |

### Salesforce：为什么第一季度现金流很强，但不能直接年化

Salesforce Q1 FY2027 operating cash flow 为 67.01 亿美元，capital expenditures 为 1.45 亿美元，教学口径下：

```text
Free Cash Flow 近似值 = 67.01 - 1.45 = 65.56 亿美元
```

但 Salesforce 自己在 10-Q 中说明，unearned revenue、accounts receivable 和 operating cash flow 有明显季节性。第四季度通常是新业务和续约最强季度，因此第一季度常是收款和经营现金流最大的季度。

这给初学者一个重要提醒：单季现金流强，不一定说明全年每季都一样强。要看 TTM、全年指引、续约季节性、合同期限和应收账款变化。

### Datadog：deferred contract costs 让获客成本跨期摊销

Datadog Q1 2026 deferred contract costs 为 2.180 亿美元，相关摊销费用为 2,030 万美元。公司说明，销售佣金属于取得客户合同的增量且可回收成本，因此先递延，再按四年受益期摊销。

这说明销售效率不能只看本季 sales and marketing 费用。部分销售佣金已经进入资产负债表，以后再进入费用。对学习者来说，必须同时看：

```text
当期 sales and marketing expense
+ deferred contract costs 的增加
- deferred contract costs 的摊销
```

如果只看利润表，可能低估当期获客投入；如果只看现金流，又要注意佣金支付时点。

### Snowflake：消费型模型下，RPO 高不等于收入机械入账

Snowflake 披露 Q1 FY2027 RPO 约 92 亿美元，但公司说明 RPO 不一定指示未来 product revenue growth，因为收入确认取决于客户未来消费、超额消费、合同容量使用和 rollover 规则。

本季 Snowflake deferred revenue 减少 5.285 亿美元，管理层解释的核心原因之一是预付 capacity agreements 的收入确认超过开票。这和固定订阅软件很不一样：客户买了 capacity，不代表每个季度按完全固定节奏消耗。

所以 Snowflake 的分析顺序应是：

```text
RPO -> deferred revenue -> product revenue -> consumption pattern -> FCF
```

而不是把 RPO 直接除以季度数，机械预测收入。

### Adobe：高订阅收入也要看合同资产和递延成本

Adobe Q2 FY2026 subscription revenue 为 64.16 亿美元，deferred revenue 为 72.5 亿美元，RPO 为 222.7 亿美元，capitalized contract acquisition costs 为 7.82 亿美元。Adobe 的订阅收入占比高、RPO 可见度强，但仍然需要看合同资产、应收账款、销售佣金资本化、Semrush 并购和回购等因素。

教学口径下，Adobe Q2 operating cash flow 为 21.65 亿美元，property and equipment purchases 为 0.58 亿美元：

```text
Free Cash Flow 近似值 = 21.65 - 0.58 = 21.07 亿美元
```

这个数字有学习价值，但不能替代公司全年现金流、并购现金支出和资本配置分析。

### 这些现实事件如何连接理论

- Salesforce 展示了固定订阅公司开票和收款季节性怎样影响递延收入、应收账款和经营现金流。
- Datadog 展示了合同取得成本如何把销售佣金从“今天支付”变成“未来摊销”。
- Snowflake 展示了消费型云模型中 RPO、递延收入和收入确认之间的断裂。
- Adobe 展示了成熟订阅软件公司仍需要同时观察 RPO、递延收入、合同取得成本、并购和现金流。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP 收入确认、非 GAAP 指标披露、企业软件合同、政府云认证、数据隐私监管、Fed 利率政策和美国国债收益率曲线。
- 已确认事实：本课所有公司数据来自 SEC 文件；利率背景来自 Federal Reserve 和 U.S. Treasury。
- 市场可能如何传导：利率较高时，远期现金流折现更重，市场会更关注 billings、RPO、递延收入和自由现金流是否可持续。
- 仍需核验或观察：公司是否改变 RPO 或 billings 口径，AI 产品是否改变消费节奏，客户是否缩短合同期限，佣金资本化是否持续增加。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Bookings | 订单或签约额 | 客户新签、续签或扩容的合同承诺 | 观察销售前端动能 |
| Billings | 开票额 | 公司向客户开票或产生收款权利的金额 | 连接订单和现金回收 |
| Deferred Revenue | 递延收入 | 已开票或已收款但还没确认收入的负债 | 判断未来履约和现金时点 |
| Unearned Revenue | 未赚收入 | Salesforce 对递延收入使用的常见名称 | 本质是还没履约完成的客户款项 |
| Revenue Recognition | 收入确认 | 按履约进度把合同转成收入 | 防止把收款误当收入 |
| Contract Asset | 合同资产 | 已履约但还没有无条件收款权 | 说明收入可能先于开票 |
| RPO | 剩余履约义务 | 已签合同中尚未确认的未来收入 | 衡量合同可见度 |
| Deferred Commissions | 递延佣金 | 销售佣金先资本化，未来摊销 | 影响获客成本和利润节奏 |
| Capitalized Contract Costs | 资本化合同取得成本 | 为取得合同发生且可回收的成本 | 让销售费用跨期确认 |
| Operating Cash Flow | 经营现金流 | 主营经营活动产生的现金 | 检查利润是否转成现金 |
| Free Cash Flow | 自由现金流 | 经营现金流扣除资本开支等必要投入 | 估值和资本配置的重要输入 |
| Seasonality | 季节性 | 某些季度天然更强或更弱 | 防止单季年化误判 |

## 回顾提示

- 学到本课前建议回顾：第 18 课 RPO 与收入确认、第 19 课递延收入、第 29 课自由现金流收益率、第 39 课 Rule of 40。
- 本课哪些内容会在后续课程继续使用：Non-GAAP、股权激励、稀释、自由现金流质量、三表预测和 SaaS 估值。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 20 课应收账款、第 21 课营运资本。

## 案例拆解

- 案例对象：Salesforce、Datadog、Snowflake 与 Adobe 的订单、开票、递延收入和现金流质量。
- 已确认事实：
  - Salesforce Q1 FY2027 RPO 为 679 亿美元，unearned revenue 为 203.63 亿美元，operating cash flow 为 67.01 亿美元。
  - Datadog Q1 2026 RPO 为 34.844 亿美元，deferred contract costs 为 2.180 亿美元，free cash flow 为 2.891 亿美元。
  - Snowflake Q1 FY2027 RPO 约 92 亿美元，deferred commissions 约 4.349 亿美元，deferred revenue 本季减少 5.285 亿美元。
  - Adobe Q2 FY2026 RPO 为 222.7 亿美元，deferred revenue 为 72.5 亿美元，capitalized contract acquisition costs 为 7.82 亿美元。
- 来源日期和链接：见本课“来源”。
- 分析推理：Salesforce 更适合观察固定订阅和季节性现金流；Datadog 适合观察递延合同成本；Snowflake 适合观察消费型模型的 RPO 边界；Adobe 适合观察成熟订阅软件的 RPO 和合同成本。
- 后续验证指标：新订单、续约订单、billings、RPO、cRPO、deferred revenue、contract assets、deferred commissions、operating cash flow、free cash flow、capitalized software、客户数和 NRR。

## 个人情境连接

- 对关注清单的启发：看到 SaaS 公司现金流很强时，先问这是不是续约和开票季节性，而不是直接认为全年都能复制。
- 对持仓或基金选择的启发：基金重仓云软件时，要看组合公司是否有真实现金流，还是只是单季收款节奏好。
- 对工作、收入、消费或风险管理的启发：个人服务或咨询收入也有 bookings、billings 和 cash collection。签约不等于收款，收款不等于已经完成交付。

## 结论边界

- 可以确定：Bookings、billings、deferred revenue、RPO 和 free cash flow 是理解 SaaS 现金流质量的核心链条。
- 不能确定：本课不能用公开披露精确还原所有真实 bookings，也不能把单季 FCF 直接年化。
- 需要继续观察：公司是否持续披露相同口径，AI 产品是否改变合同和消费节奏，递延佣金是否持续上升，开票季节性是否变化。
- 不构成投资建议的原因：本课只训练现金流和收入确认阅读框架，不推荐买入或卖出任何证券。

## 练习题

1. 为什么公司已经收到客户的钱，仍可能不能立刻确认收入？
2. 一个公司当季收入 100，递延收入从 40 增加到 55。在没有并购和汇率影响的极简条件下，billings 近似是多少？
3. 为什么 Salesforce 第一季度 operating cash flow 很强，仍不能直接乘以 4 当全年现金流？
4. Snowflake 的 RPO 为什么不能机械等同于未来几个季度的收入？
5. 如果一家公司 deferred commissions 快速上升，你会继续追问哪三个问题？

## 学习交接

- 本课已经完成：把 Sales Efficiency 和 Rule of 40 推进到订单、开票、递延收入、递延佣金和 SaaS 现金流质量。
- 本课最重要的一句话：SaaS 现金流质量要沿着 `签约 -> 开票 -> 收款 -> 递延收入 -> 收入确认 -> 自由现金流` 一步步核验。
- 需要复习的关键词：Bookings、Billings、Deferred Revenue、Unearned Revenue、RPO、Deferred Commissions、Capitalized Contract Costs、Operating Cash Flow、Free Cash Flow、Seasonality。
- 还不稳定、下次要回看的地方：Non-GAAP 和股权激励为什么会让利润、现金流和股东回报看起来不一致。
- 适合下次打开仓库先读的文件：`lessons/2026-06-30-lesson-41-sbc-non-gaap-dilution-cash-flow-quality.md`

## 下节课安排

- 建议主题：第四十一课：股权激励、Non-GAAP、稀释与现金流质量入门。
- 学习目标：理解 stock-based compensation、GAAP 与 non-GAAP、稀释股数、回购和自由现金流质量之间的关系。
- 建议案例：Datadog、Snowflake、Salesforce 与 Adobe，用官方披露的 stock-based compensation、non-GAAP operating margin、diluted shares、repurchases 和 free cash flow 做对照。
- 必须解释的关键词：Stock-based Compensation、RSU、GAAP、Non-GAAP、Dilution、Diluted EPS、Share Repurchase、Treasury Stock、Owner Earnings、Net Share Settlement。
- 下节课开始前需要联网核验的数据：上述公司最新 SEC/IR 披露中的 SBC、non-GAAP 调整、基本和稀释股数、回购、股权激励税款、自由现金流和债务变化。

## 来源

- Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
- Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
- Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
- Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
- Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
- Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-29: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
