# 第三十八课：CAC、LTV 与回本周期入门

## 基本信息

- 日期：2026-06-29
- 数据截至：2026-06-29 20:08（Asia/Shanghai）；公司财务采用 Salesforce 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-28 Form 10-Q、Snowflake 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-29 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 U.S. Treasury 2026-06-26 最新可得收益率。
- 主题：一家公司花钱获得客户以后，客户贡献的毛利能不能把获客成本赚回来。
- 学习目标：理解 CAC、LTV、Payback Period、Gross Margin、ARPA、Customer Lifetime、Sales and Marketing、Unit Economics，并学会区分“真实客户队列口径”和“公开财报粗略代理”。
- 相关资产：股票、SaaS、订阅软件、云服务、收入确认、毛利率、销售费用、自由现金流、DCF。
- 已核验来源（核心来源）：
  - Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
  - Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
  - Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
  - Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-26: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?type=daily_treasury_yield_curve&field_tdr_date_value=2026

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲订阅收入质量时，我们问客户是否留下、续费和扩容。今天继续问：

> 留住客户还不够，最开始把客户找来的钱能不能赚回来？

如果一家公司花 100 元销售和营销费用获得一个客户，但这个客户未来只能贡献 30 元毛利，这种增长越快越危险。如果花 100 元获得客户，客户在一年内贡献 120 元毛利，之后还继续续费和扩容，增长质量就完全不同。

### 参考的教材式概念顺序

1. Sales and Marketing：先看公司为获客、续约、品牌和渠道花了多少钱。
2. CAC：再看获得一个新客户或一单位新增 ARR 的成本。
3. Gross Margin：客户收入扣掉服务成本后，剩下多少毛利能用来回本。
4. Payback Period：用客户毛利收回获客成本需要多久。
5. LTV：客户整个生命周期可能贡献多少毛利。
6. LTV/CAC：客户生命周期价值和获客成本的比值。
7. Unit Economics：把单个客户或单个收入单位当成一个小生意来判断是否划算。

### 核心概念

最小公式：

```text
CAC = 用于获取新客户的销售和营销成本 / 新客户数量

毛利 = 收入 x 毛利率

回本周期 = CAC / 每期客户毛利

LTV = 客户每期收入 x 毛利率 x 客户生命周期
```

如果用流失率近似客户生命周期：

```text
客户生命周期 ≈ 1 / 年流失率

LTV ≈ ARPA x 毛利率 / 年流失率
```

这里的 ARPA 是 Average Revenue per Account，意思是每个账户平均收入。这个公式很适合入门，但不能机械使用，因为真实客户会扩容、降级、涨价、流失和重新签约。

### 用自己的话解释

CAC 是“把客户请进门花了多少钱”。LTV 是“客户一生可能带来多少毛利”。Payback Period 是“多久能把请客户进门的钱赚回来”。Unit Economics 是“每一个客户这笔小账是否成立”。

一家订阅公司可能总收入增长很快，但如果必须持续用很高的销售费用补充新客户，而老客户毛利不足以回本，增长就是用现金换规模。反过来，如果客户很快回本、后续留存高、扩容多，销售费用更像可回收投资。

### 常见误区

- 误区一：把公开财报里的全部 Sales and Marketing 直接当 CAC。公开口径通常混合了新客户获取、老客户续约、品牌、渠道、销售管理和股权激励。
- 误区二：只看收入，不看毛利率。收入不是全部都能用来回本，云成本、服务成本和支持成本要先扣掉。
- 误区三：把 NRR 高于 100% 当成 LTV 已经确定。NRR 是历史客户群体收入变化，不等于未来生命周期。
- 误区四：客户生命周期用 `1 / churn` 时不看样本。流失率很低时，LTV 会被公式放得很大，结论很容易过度乐观。
- 误区五：用单季现金流或单季费用直接年化。SaaS 账单、续约、佣金和现金流都有季节性。

## 第二大板块：实时背景与市场传导

### 发生了什么

Salesforce 2027 财年第一季度披露，subscription and support revenue 为 105.93 亿美元，同比增长 14%；current remaining performance obligation 为 336 亿美元，同比增长 14%；remaining performance obligation 为 679 亿美元，同比增长 11%。同一季度 10-Q 披露 sales and marketing 为 37.69 亿美元，subscription and support cost of revenues 为 19.53 亿美元。

Snowflake 2027 财年第一季度披露，product revenue 为 13.343 亿美元，同比增长 34%；net revenue retention rate 为 126%；有 779 个过去 12 个月 product revenue 超过 100 万美元的客户；remaining performance obligations 为 92.1 亿美元。10-Q 披露 total customers 为 13,912，sales and marketing 为 5.88952 亿美元。

Adobe 2026 财年第二季度披露，total Adobe ARR 为 271.0 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%，total customer group subscription revenue 为 63.9 亿美元。10-Q 披露季度 subscription revenue 为 64.16 亿美元，subscription cost of revenue 为 5.86 亿美元，sales and marketing 为 18.84 亿美元。

### 为什么重要

利率背景让回本周期更重要。Fed 2026-06-17 维持 federal funds rate 目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-26 的 10 年期 Treasury yield 为 4.38%。当无风险利率不低时，市场更难无限容忍“很久以后才可能回本”的增长故事。

从估值角度看，CAC、LTV 和回本周期会影响三件事：

- 现金流：获客成本先发生，客户毛利后产生。
- 增长质量：同样增长 20%，低 CAC、高留存的增长比高 CAC、高流失的增长质量更高。
- 折现率敏感性：回本越慢，未来现金流越远，越容易受到利率和风险偏好变化影响。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Salesforce subscription and support revenue | 105.93 亿美元，+14% | Salesforce 2026-05-27 Form 8-K exhibit 99.1 | 订阅收入规模 |
| Salesforce current RPO / RPO | 336 亿美元 / 679 亿美元 | Salesforce 2026-05-27 Form 8-K exhibit 99.1 | 合同可见度 |
| Salesforce sales and marketing | 37.69 亿美元 | Salesforce 2026-05-28 Form 10-Q | 获客与续约投入代理 |
| Snowflake product revenue | 13.343 亿美元，+34% | Snowflake 2026-05-27 Form 8-K exhibit 99.1 | 消费型云收入规模 |
| Snowflake net revenue retention | 126% | Snowflake 2026-05-27 Form 8-K exhibit 99.1 | 老客户扩容证据 |
| Snowflake customers >$1M product revenue | 779 个 | Snowflake 2026-05-27 Form 8-K exhibit 99.1 | 大客户增长质量 |
| Snowflake total customers | 13,912 个 | Snowflake 2026-05-29 Form 10-Q | 客户规模 |
| Adobe subscription revenue | 64.16 亿美元 | Adobe 2026-06-15 Form 10-Q | 订阅收入规模 |
| Adobe sales and marketing | 18.84 亿美元 | Adobe 2026-06-15 Form 10-Q | 获客与续约投入代理 |
| Adobe RPO / cRPO | 222.7 亿美元 / 67% | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 合同可见度 |
| 10 年期 Treasury yield | 4.38% | U.S. Treasury, 2026-06-26 | 回本周期折现背景 |

### 如何用公开数据做“粗略代理”，但不把它当真实 CAC

公开财报通常没有给出真实 CAC，因为真实 CAC 需要知道哪些销售费用用于新客户、哪些用于续约、哪些用于品牌和渠道。我们只能做一个教学用的压力测试。

Salesforce 的公开代理：

```text
Q1 FY2027 subscription and support revenue = 105.93 亿美元
Q1 FY2026 subscription and support revenue = 92.97 亿美元
同比新增季度订阅支持收入 = 12.96 亿美元

subscription and support gross margin
= (105.93 - 19.53) / 105.93
= 81.6%

公开代理回本倍数
= sales and marketing / (同比新增订阅支持收入 x 订阅支持毛利率)
= 37.69 / (12.96 x 81.6%)
= 约 3.6 个季度毛利
```

这个结果不能说 Salesforce 的真实 CAC 回本期就是 3.6 个季度，因为 sales and marketing 里包含续约、老客户扩容、品牌、并购整合和股权激励，新增收入也不是同一批客户队列贡献的收入。

Adobe 的公开代理：

```text
Q2 FY2026 subscription revenue = 64.16 亿美元
Q2 FY2025 subscription revenue = 56.41 亿美元
同比新增季度订阅收入 = 7.75 亿美元

subscription gross margin
= (64.16 - 5.86) / 64.16
= 90.9%

公开代理回本倍数
= 18.84 / (7.75 x 90.9%)
= 约 2.7 个季度毛利
```

这个代理只能说明“公开费用与新增订阅毛利之间的粗略关系”。它不能替代客户队列数据，也不能证明某只股票便宜或昂贵。

### Snowflake：NRR 高说明扩容强，但 CAC 仍要单独看

Snowflake 的 net revenue retention rate 为 126%，说明历史客户群体的产品收入在扣掉流失和降级后仍有明显扩容。这个指标对 LTV 很重要，因为老客户扩容会让客户生命周期价值提高。

但 NRR 不是 CAC。Snowflake Q1 sales and marketing 为 5.88952 亿美元，说明获取、维护和扩张客户仍需要大量投入。一个更完整的问题是：

```text
高 NRR 是否足以覆盖持续销售投入、云成本、研发投入和股权激励？
```

这就是为什么 CAC、LTV、Payback Period 要和毛利率、经营利润率、自由现金流、RPO 和风险因素一起看。

### 这些现实事件如何连接理论

- Salesforce 展示了大规模订阅公司如何同时披露订阅收入、RPO、销售营销费用和现金流。
- Adobe 展示了高订阅占比和高订阅毛利率下，仍然需要观察销售营销投入、AI 产品转化、竞争和续费。
- Snowflake 展示了高 NRR 和大客户增长如何支持 LTV 推理，但消费型业务的收入节奏和订阅型软件不同。
- 利率环境提醒我们：回本周期越长，未来现金流越远，估值越依赖假设。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、Topic 606 收入确认、企业软件合同、AI 产品披露、Fed 利率政策、客户数据合规和政府云认证。
- 已确认事实：Salesforce、Snowflake 和 Adobe 的收入、RPO、销售营销费用、毛利和 NRR 来自 SEC 文件；Fed 和 Treasury 提供利率背景。
- 市场可能如何传导：利率提高会让长期回本的获客模型更受折现压力；AI 竞争会影响获客成本、续费率和定价权；并购会改变收入增长和客户指标口径。
- 仍需核验或观察：真实 CAC 队列、销售佣金资本化、客户生命周期、渠道结构、净收入留存变化、AI 产品是否带来低成本获客或更高扩容。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| CAC | 客户获取成本 | 获得一个新客户或一单位新增 ARR 的成本 | 判断增长是否烧钱过度 |
| LTV | 客户生命周期价值 | 一个客户在整个生命周期可能贡献的毛利 | 判断客户是否值得获取 |
| Payback Period | 回本周期 | 用客户毛利收回 CAC 需要多久 | 回本越慢，现金流和利率风险越高 |
| Gross Margin | 毛利率 | 收入扣掉直接服务成本后的比例 | 只有毛利能用来覆盖获客和运营 |
| ARPA | 每账户平均收入 | Average Revenue per Account | LTV 估算的基础输入 |
| Customer Lifetime | 客户生命周期 | 客户从开始付费到停止付费的时间 | 决定 LTV 的长度 |
| Sales and Marketing | 销售和营销费用 | 销售团队、渠道、广告、品牌和佣金等费用 | 公开财报里的 CAC 近似入口 |
| Unit Economics | 单位经济模型 | 单个客户或单个收入单位是否赚钱 | 把增长拆成可验证的小账 |
| Cohort | 客户队列 | 同一时期获得的一批客户 | 真实 CAC 和 LTV 最好按队列看 |
| NRR | 净收入留存 | 老客户收入扣流失后加扩容的比例 | 高 NRR 通常提高 LTV，但不是 CAC |

## 回顾提示

- 学到本课前建议回顾：第 22 课毛利率、第 23 课营业费用、第 35 课增长质量、第 37 课客户留存和 NRR。
- 本课哪些内容会在后续课程继续使用：Sales Efficiency、Magic Number、Rule of 40、递延佣金、billings、bookings 和 SaaS 现金流质量。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 18 课 RPO 与收入确认、第 29 课自由现金流收益率。

## 案例拆解

- 案例对象：Salesforce、Adobe 与 Snowflake 的公开披露数据如何帮助学习 CAC、LTV 和回本周期。
- 已确认事实：
  - Salesforce Q1 FY2027 subscription and support revenue 为 105.93 亿美元，current RPO 为 336 亿美元，RPO 为 679 亿美元，sales and marketing 为 37.69 亿美元。
  - Adobe Q2 FY2026 subscription revenue 为 64.16 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%，sales and marketing 为 18.84 亿美元。
  - Snowflake Q1 FY2027 product revenue 为 13.343 亿美元，net revenue retention rate 为 126%，RPO 为 92.1 亿美元，sales and marketing 为 5.88952 亿美元。
- 来源日期和链接：见本课“来源”。
- 分析推理：Salesforce 和 Adobe 可以用公开数据做销售营销费用与新增订阅毛利的粗略压力测试；Snowflake 的高 NRR 支持老客户扩容推理，但真实 CAC 与 LTV 仍需要客户队列和销售分层数据。
- 后续验证指标：真实新客户数、净新增 ARR、销售佣金资本化、NRR、gross margin、customer count、large customer count、RPO、deferred revenue、free cash flow、AI 产品 ARR、并购贡献和续约披露。

## 个人情境连接

- 对关注清单的启发：看到订阅公司时，不只问“收入增长多少”，还要问“增长花了多少钱、多久回本”。
- 对持仓或基金选择的启发：基金重仓 SaaS 或云公司时，要区分高增长来自高效扩容，还是来自持续高销售投入。
- 对工作、收入、消费或风险管理的启发：个人职业也有 CAC。获取客户、建立信任和交付服务都需要成本，长期复购和口碑能降低未来获客压力。

## 结论边界

- 可以确定：CAC、LTV 和回本周期是订阅公司增长质量的核心框架；公开财报能提供销售营销费用、收入、毛利、RPO、NRR 等观察入口。
- 不能确定：本课不能用公开财报精确计算 Salesforce、Adobe 或 Snowflake 的真实 CAC、真实 LTV 或真实客户队列回本期。
- 需要继续观察：AI 产品是否降低获客成本或提高扩容，客户续费是否稳定，并购是否改变指标口径，销售佣金和递延成本如何影响现金流。
- 不构成投资建议的原因：本课只训练客户经济模型，不推荐买入或卖出任何证券。

## 练习题

1. 为什么收入不能直接用来回收 CAC，而要先乘以毛利率？
2. 一家公司 CAC 为 600 元，每月客户收入 100 元，毛利率 80%。回本周期是多少个月？
3. 为什么公开财报中的 sales and marketing 不等于真实 CAC？
4. Snowflake 的 NRR 为 126%，这能支持哪些 LTV 推理？又不能证明什么？
5. 如果一家 SaaS 公司收入高增长但回本周期变长，你会继续追问哪三个问题？

## 学习交接

- 本课已经完成：把客户留存和订阅收入质量推进到 CAC、LTV、回本周期和单位经济模型。
- 本课最重要的一句话：增长不是免费午餐，客户贡献的毛利必须能在合理时间内收回获客成本。
- 需要复习的关键词：CAC、LTV、Payback Period、Gross Margin、ARPA、Customer Lifetime、Sales and Marketing、Unit Economics、Cohort、NRR。
- 还不稳定、下次要回看的地方：如何把 CAC 和 LTV 推进到 Sales Efficiency、Magic Number 和 Rule of 40。
- 适合下次打开仓库先读的文件：`lessons/2026-06-29-lesson-39-sales-efficiency-rule-of-40-unit-economics.md`

## 下节课安排

- 建议主题：第三十九课：Sales Efficiency、Magic Number、Rule of 40 与单位经济模型入门。
- 学习目标：理解销售效率如何衡量新增收入对销售投入的回报，Rule of 40 如何把增长和利润放在同一张简表中。
- 建议案例：Datadog、Snowflake 与 Salesforce，用官方披露的收入增长、销售营销费用、经营利润率、自由现金流和客户指标做对照。
- 必须解释的关键词：Sales Efficiency、Magic Number、Rule of 40、Free Cash Flow Margin、Operating Margin、Non-GAAP、Incremental ARR、Efficient Growth。
- 下节课开始前需要联网核验的数据：Datadog、Snowflake、Salesforce 最新 SEC/IR 披露；收入增长、销售营销费用、客户指标、经营利润率、自由现金流和非 GAAP 调整。

## 来源

- Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
- Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
- Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
- Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Par Yield Curve Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?type=daily_treasury_yield_curve&field_tdr_date_value=2026
