# 第二十课：应收账款、DSO、坏账准备与现金回收周期入门

## 基本信息

- 日期：2026-06-19
- 数据截至：2026-06-19 18:30（Asia/Shanghai）；公司数据采用截至本次写作时 SEC 已披露的最新 10-Q/10-K 与 SEC companyfacts；利率背景采用 2026-06-18 U.S. Treasury 和 2026-06-17 Federal Reserve。
- 主题：从“已经确认收入”继续追到“现金是否真的收回来”
- 学习目标：理解应收账款、DSO、坏账准备和信用风险怎样把利润表、资产负债表、现金流量表连接起来。
- 相关资产：股票、公司财报、企业信用、短期利率、软件订阅业务。
- 核心来源：
  - SEC companyfacts: Microsoft Corporation, CIK 0000789019, `AccountsReceivableNetCurrent`、`AllowanceForDoubtfulAccountsReceivableCurrent`、`RevenueFromContractWithCustomerExcludingAssessedTax`，最新 10-Q filed 2026-04-29, report date 2026-03-31: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
  - Microsoft FY2026 Q3 Form 10-Q, accession `0001193125-26-191507`: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上节课我们已经知道：收入确认不等于收钱。那今天的问题就是：

> 如果公司已经把收入记进利润表，但客户还没付钱，这笔钱在财报里放在哪里？

答案通常是：放在资产负债表的“应收账款”里。

### 参考的教材式概念顺序

1. 先确认收入：公司交付商品或服务，满足收入确认条件。
2. 再看收款：客户可能立刻付钱，也可能 30 天、60 天、90 天后才付。
3. 没收到的钱先成为资产：应收账款代表公司对客户的收款权利。
4. 资产不是现金：应收账款要靠后续回款才变成现金。
5. 不是所有客户都会准时付款：公司要估计可能收不回来的部分，形成坏账准备。

### 核心概念

- 应收账款（Accounts Receivable, A/R）：公司已经向客户提供商品或服务、已经有权收款，但现金还没到账。
- DSO（Days Sales Outstanding，应收账款周转天数）：平均需要多少天把销售变成现金。
- 坏账（Bad Debt）：客户最终可能不付款，导致公司无法收回的款项。
- 坏账准备（Allowance for Doubtful Accounts）：公司提前估计可能收不回来的金额，用来把应收账款从“纸面权利”调整得更接近可收回现金。
- 信用风险（Credit Risk）：客户能不能按时付款、有没有能力付款的不确定性。

### 用自己的话解释

应收账款像“客户欠公司的账单”。它不是空气，因为公司确实有收款权利；但它也不是现金，因为公司还不能拿这笔钱去发工资、还债或回购股票。

DSO 就像回款速度表。DSO 越长，说明收入到现金之间隔得越久。坏账准备则像会计上的保守提醒：账单上写着能收 100 元，不代表最后一定能收满 100 元。

### 常见误区

- 误区一：收入增长就一定现金增长。实际可能是应收账款增长更快，现金没有同步回来。
- 误区二：应收账款越多越好。应收账款增加可能来自销售增长，也可能来自客户付款变慢。
- 误区三：坏账准备只是会计小项目。它直接影响资产质量、利润质量和管理层对客户信用风险的判断。

## 第二大板块：实时背景与市场传导

### 发生了什么

截至 Microsoft 2026-03-31 的 10-Q，SEC companyfacts 显示：

- Microsoft FY2026 Q3 期末应收账款为 600.41 亿美元。
- 2025-12-31 的应收账款为 565.35 亿美元。
- FY2026 Q3 单季收入为 828.86 亿美元。
- FY2026 Q3 期末坏账准备为 7.94 亿美元。

用一个入门估算：

```text
平均应收账款 = (565.35 + 600.41) / 2 = 582.88 亿美元
DSO = 平均应收账款 / 单季收入 * 90
DSO ≈ 582.88 / 828.86 * 90 ≈ 63 天
坏账准备 / 期末应收账款 ≈ 7.94 / 600.41 ≈ 1.3%
```

这不是精确估值模型，只是零基础读财报时的第一把尺子。

### 为什么重要

当利率较高时，“晚一点收到现金”的成本会变高。U.S. Treasury 2026-06-18 的 10 年期国债收益率为 4.46%，30 年期为 4.90%；Federal Reserve 2026-06-17 维持联邦基金目标区间在 3.50%-3.75%，并表示通胀仍高于 2% 目标。

这会让市场更在意：

- 公司收入是否能快速变成现金；
- 客户付款周期是否拉长；
- 坏账准备是否跟随信用风险上升；
- 公司是否需要更多外部融资来填补回款时间差。

### 本节采用的数据和来源

- Microsoft 最新 10-Q 和 SEC companyfacts，用于应收账款、收入、坏账准备。
- Federal Reserve 2026-06-17 FOMC statement，用于利率政策背景。
- U.S. Treasury 2026-06-18 Daily Treasury Rates，用于市场利率背景。

### 这些现实事件如何连接理论

理论上，应收账款只是资产负债表里的一个项目。现实中，它会影响现金流、融资需求和估值。若公司收入高增长但 DSO 拉长，市场会追问：这是销售太快导致账期自然拉长，还是客户付款能力变弱？

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP 收入确认与信用损失估计、Federal Reserve 利率政策。
- 已确认事实：Microsoft 最新 10-Q 已在 SEC 披露；Fed 2026-06-17 维持目标利率区间；Treasury 2026-06-18 发布收益率曲线。
- 市场可能如何传导：高利率提高资金时间价值，回款变慢会降低现金质量；信用压力上升时坏账准备可能增加。
- 仍需核验或观察：下一季 Microsoft 应收账款、坏账准备和经营现金流是否与收入同步变化。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Accounts Receivable / A/R | 应收账款 | 客户欠公司的账单 | 判断收入能否变成现金 |
| DSO | 应收账款周转天数 | 平均多少天收回货款 | 衡量回款速度 |
| Allowance | 坏账准备 | 公司估计可能收不回来的部分 | 反映资产质量和信用风险 |
| Bad Debt | 坏账 | 最终收不回来的客户欠款 | 影响利润和现金流 |
| Credit Risk | 信用风险 | 客户不按时付款或不付款的风险 | 连接财报和宏观利率环境 |
| Working Capital | 营运资本 | 日常经营占用的短期资金 | 下一课会继续展开 |

## 回顾提示

- 学到本课前建议回顾：第 10 课三张报表、第 18 课 RPO 与收入确认、第 19 课递延收入与预付款。
- 本课哪些内容会在后续课程继续使用：DSO、坏账准备、营运资本、现金转换周期。
- 如果看不懂本课，可以先回到：第 10 课“利润表、资产负债表、现金流量表”。

## 案例拆解

- 案例对象：Microsoft FY2026 Q3 应收账款和坏账准备。
- 已确认事实：SEC companyfacts 显示 Microsoft FY2026 Q3 单季收入 828.86 亿美元、期末应收账款 600.41 亿美元、期末坏账准备 7.94 亿美元。
- 来源日期和链接：Microsoft 10-Q filed 2026-04-29；SEC companyfacts 数据截至 2026-06-19 写作时可查。
- 分析推理：粗略 DSO 约 63 天，说明即使是大型软件公司，也需要把“确认收入”和“收回现金”分开观察。
- 后续验证指标：下一季收入增速、应收账款增速、坏账准备比例、经营现金流。

## 个人情境连接

- 对关注清单的启发：不要只看收入增长，也要看应收账款是否同步膨胀。
- 对持仓或基金选择的启发：如果基金重仓高增长公司，要理解高增长可能伴随回款周期和信用风险。
- 对工作、收入、消费或风险管理的启发：个人接项目、做销售、做小生意时，“开票”和“到账”也不是同一件事。

## 结论边界

- 可以确定：应收账款是已确认但未收现的客户欠款；DSO 可用于观察回款速度；坏账准备是信用风险的会计估计。
- 不能确定：单季 DSO 上升或下降一定代表公司变好或变坏，因为季节性、合同结构、客户结构都会影响应收账款。
- 需要继续观察：多季趋势、同行对比、经营现金流和管理层解释。
- 不构成投资建议的原因：本课只解释财报科目和读表方法，不判断 Microsoft 或任何证券是否值得买卖。

## 练习题

1. 如果一家公司收入增长 20%，但应收账款增长 60%，你会提出哪三个问题？
2. 用“开票、收款、坏账准备”三个词解释为什么利润不等于现金。
3. 为什么高利率环境下，市场会更重视 DSO？
4. 找一家你熟悉的上市公司，查看最新 10-Q 或半年报中的应收账款，判断它相对收入是变大还是变小。

## 学习交接

- 本课已经完成：把收入确认之后的第一站“应收账款”讲清楚，并引入 DSO、坏账准备和信用风险。
- 本课最重要的一句话：利润表说“赚到了”，现金流量表才告诉你“钱有没有回来”。
- 需要复习的关键词：Accounts Receivable、DSO、Allowance、Bad Debt、Credit Risk。
- 还不稳定、下次要回看的地方：DSO 只是粗略指标，必须结合行业账期、季节性和经营现金流。
- 适合下次打开仓库先读的文件：`lessons/2026-06-19-lesson-21-working-capital-cash-conversion-cycle.md`

## 下节课安排

- 建议主题：第二十一课：营运资本与现金转换周期入门。
- 学习目标：把应收账款、库存、应付账款连成“钱在经营里转一圈要多久”。
- 建议案例：Apple、NVIDIA、Nike 的最新 10-Q 对比。
- 必须解释的关键词：Working Capital、Inventory、Accounts Payable、DIO、DPO、Cash Conversion Cycle。
- 下节课开始前需要联网核验的数据：Apple/NVIDIA/Nike 最新 SEC 10-Q、U.S. Treasury 利率背景、Fed 最新政策声明是否变化。

## 来源

- SEC companyfacts, Microsoft Corporation: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
- Microsoft FY2026 Q3 Form 10-Q: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
