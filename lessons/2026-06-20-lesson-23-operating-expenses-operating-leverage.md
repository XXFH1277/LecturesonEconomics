# 第二十三课：营业费用、营业利润率与经营杠杆入门

## 基本信息

- 日期：2026-06-20
- 数据截至：2026-06-20 20:10（Asia/Shanghai）；公司数据采用截至本次写作时 SEC 已披露的最新 10-Q 与 SEC companyfacts；利率背景采用 2026-06-18 U.S. Treasury 和 2026-06-17 Federal Reserve。
- 主题：毛利之后还要扣哪些费用，为什么高毛利不等于高营业利润。
- 学习目标：理解营业费用、研发、销售营销、管理费用、营业利润率和经营杠杆，学会把“产品赚不赚钱”和“公司运营后还剩多少”分开看。
- 相关资产：股票、公司财报、软件公司、云计算、AI 竞争、利率。
- 核心来源：
  - SEC companyfacts: Microsoft Corporation, CIK 0000789019: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
  - Microsoft FY2026 Q3 Form 10-Q, accession `0001193125-26-191507`, filed 2026-04-29, report date 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
  - SEC companyfacts: Adobe Inc., CIK 0000796343: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
  - Adobe FY2026 Q2 Form 10-Q, accession `0000796343-26-000112`, filed 2026-06-15, report date 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十二课讲了毛利率。今天继续问：

> 如果一家公司毛利率很高，为什么最后营业利润率不一定同样高？

因为毛利只是第一层。公司还要花钱做研发、销售、营销、客服、管理、合规、办公和系统建设。这些费用不一定直接对应某一件商品的生产，但它们支撑公司持续经营。

### 参考的教材式概念顺序

1. 收入减收入成本，得到毛利。
2. 毛利再扣营业费用，得到营业利润。
3. 营业费用通常包括研发、销售营销、管理费用和部分摊销。
4. 营业利润除以收入，得到营业利润率。
5. 如果收入增长快于营业费用增长，经营杠杆可能释放。
6. 如果公司必须大量投入研发、销售或基础设施，经营杠杆可能暂时受压。

### 核心概念

- 营业费用（Operating Expenses, Opex）：为了维持和扩大经营而发生的费用，但不直接计入收入成本。
- 研发费用（Research and Development, R&D）：开发新产品、新技术、新功能的支出。
- 销售和营销费用（Sales and Marketing, S&M）：获客、品牌、销售团队、渠道推广相关支出。
- 管理费用（General and Administrative, G&A）：总部管理、财务、法务、人力、办公等支出。
- 营业利润（Operating Income）：毛利扣除营业费用后的经营层利润。
- 营业利润率（Operating Margin）：营业利润除以收入。
- 经营杠杆（Operating Leverage）：收入增长时，固定或半固定费用不同比例增长，从而让利润率扩张的能力。

### 用自己的话解释

可以先把利润表想成三层：

```text
第一层：收入 - 收入成本 = 毛利
第二层：毛利 - 营业费用 = 营业利润
第三层：营业利润 - 利息 - 税费 - 其他项目 = 净利润
```

高毛利说明产品或服务本身留下的钱多，但还不能说明整个公司运营后剩得多。一个软件产品的毛利率可能很高，但如果公司为了 AI、销售团队、国际扩张和客户支持投入很多，营业利润率仍可能低于毛利率很多。

### 常见误区

- 误区一：高毛利率等于高利润率。实际还要看营业费用。
- 误区二：研发费用越低越好。对技术公司来说，研发可能是未来竞争力的一部分。
- 误区三：销售营销费用越高越差。早期扩张、企业客户获客和品牌重建阶段，销售营销可能是增长投入。
- 误区四：经营杠杆一定会自动出现。只有收入增长快于费用增长，经营杠杆才会真正体现在营业利润率里。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课用 Microsoft 和 Adobe 的最新 10-Q 做对照。两家公司都属于软件和数字服务相关企业，但费用结构不同。

| 公司 | 最新 SEC 报告 | 单季收入 | 单季毛利 | 单季营业利润 | 入门观察 |
| --- | --- | ---: | ---: | ---: | --- |
| Microsoft | FY2026 Q3 10-Q, filed 2026-04-29 | 828.86 亿美元 | 560.58 亿美元 | 383.98 亿美元 | 毛利率约 67.6%，营业利润率约 46.3% |
| Adobe | FY2026 Q2 10-Q, filed 2026-06-15 | 66.18 亿美元 | 59.03 亿美元 | 22.38 亿美元 | 毛利率约 89.2%，营业利润率约 33.8% |

再看营业费用占收入的比例：

| 公司 | 研发 / 收入 | 销售营销 / 收入 | 管理费用 / 收入 | 说明 |
| --- | ---: | ---: | ---: | --- |
| Microsoft | 约 10.8% | 约 8.2% | 约 2.3% | 收入规模大，费用率被规模摊薄 |
| Adobe | 约 18.1% | 约 28.5% | 约 8.3% | 高毛利，但销售、研发和管理费用占比更高 |

这不是说 Microsoft 一定“更好”、Adobe 一定“更差”。它说明同样是软件和数字服务公司，商业组合、客户结构、增长阶段、竞争压力和销售模式不同，会让毛利率和营业利润率之间的距离不同。

### 为什么重要

Federal Reserve 2026-06-17 维持联邦基金目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-18 的 2 年期、10 年期和 30 年期收益率分别为 4.19%、4.46% 和 4.90%。

在这个利率背景下，市场更重视公司能否把收入转化成高质量经营利润和现金流：

- 如果营业费用扩张慢于收入，营业利润率可能上升。
- 如果 AI、云计算、销售团队或监管合规投入加速，营业利润率可能暂时承压。
- 高毛利公司如果获客成本很高，也可能出现“产品毛利很好，但公司运营后剩得没那么多”。

### 本节采用的数据和来源

- Microsoft FY2026 Q3 10-Q 与 SEC companyfacts，用于收入、毛利、研发、销售营销、管理费用、营业利润。
- Adobe FY2026 Q2 10-Q 与 SEC companyfacts，用于收入、毛利、研发、销售营销、管理费用、营业利润。
- Federal Reserve 2026-06-17 FOMC statement，用于利率政策背景。
- U.S. Treasury 2026-06-18 Daily Treasury Rates，用于市场利率背景。

### 这些现实事件如何连接理论

Microsoft 的毛利率低于 Adobe，但营业利润率高于 Adobe，原因不是一个数字能解释，而是费用结构和规模效应不同。Adobe 的 10-Q 还在风险因素中提到 AI 正在快速演进并改变软件行业竞争方式，这可以帮助我们理解：研发和销售营销不是简单的“能砍就砍”，而是公司在竞争环境中维持产品和客户关系的投入。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP 利润表分类、AI 竞争、利率政策、企业客户预算周期。
- 已确认事实：Microsoft 和 Adobe 最新 10-Q 已在 SEC 披露；Fed 和 Treasury 已发布最新利率背景。
- 市场可能如何传导：高利率提高远期利润折现压力，市场更偏好可持续营业利润和现金流；AI 竞争可能提高研发和基础设施投入要求。
- 仍需核验或观察：后续季度研发、销售营销、云和 AI 相关投入是否继续快于收入增长，以及营业利润率是否稳定。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Operating Expenses / Opex | 营业费用 | 经营公司需要花的钱 | 决定毛利能留下多少 |
| R&D | 研发费用 | 开发技术和产品的支出 | 关系未来竞争力 |
| Sales and Marketing / S&M | 销售和营销费用 | 获客、品牌、销售渠道支出 | 决定增长成本 |
| G&A | 管理费用 | 总部、法务、财务、人力等费用 | 反映管理和合规成本 |
| Operating Income | 营业利润 | 毛利扣除营业费用后的利润 | 衡量核心经营赚钱能力 |
| Operating Margin | 营业利润率 | 营业利润占收入比例 | 观察经营效率 |
| Operating Leverage | 经营杠杆 | 收入增长快于费用增长时利润率扩张 | 解释规模效应 |
| Fixed Cost | 固定成本 | 不随短期收入同比例变化的成本 | 固定成本被摊薄时利润率可能提升 |

## 回顾提示

- 学到本课前建议回顾：第 15 课估值倍数、第 17 课自由现金流、第 22 课毛利率。
- 本课哪些内容会在后续课程继续使用：营业利润、经营杠杆、净利润、利息费用、税率、自由现金流质量。
- 如果看不懂本课，可以先回到：第 22 课“毛利率、库存减值与折扣周期入门”。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的费用结构对比。
- 已确认事实：
  - Microsoft FY2026 Q3 单季收入 828.86 亿美元、毛利 560.58 亿美元、研发 89.15 亿美元、销售营销 68.14 亿美元、管理费用 19.31 亿美元、营业利润 383.98 亿美元。
  - Adobe FY2026 Q2 单季收入 66.18 亿美元、毛利 59.03 亿美元、研发 11.98 亿美元、销售营销 18.84 亿美元、管理费用 5.46 亿美元、营业利润 22.38 亿美元。
- 来源日期和链接：Microsoft 10-Q filed 2026-04-29；Adobe 10-Q filed 2026-06-15；SEC companyfacts 数据截至 2026-06-20 写作时可查。
- 分析推理：Adobe 的毛利率更高，但营业费用占收入比例也更高；Microsoft 的收入规模更大，费用率更低，营业利润率更高。这是费用结构和规模效应的课堂案例，不是投资排序。
- 后续验证指标：收入增速、研发费用增速、销售营销费用增速、营业利润率、经营现金流、AI 和云相关投入。

## 个人情境连接

- 对关注清单的启发：看软件公司时，不要只停在毛利率，还要看研发和销售营销费用率。
- 对持仓或基金选择的启发：基金重仓高毛利科技公司时，也要理解经营杠杆是否已经释放，还是仍在投入阶段。
- 对工作、收入、消费或风险管理的启发：个人职业也有“经营费用”。学习、设备、获客、人脉和时间投入都可能降低短期净收入，但也可能支持长期增长。

## 结论边界

- 可以确定：营业利润率由毛利率和营业费用率共同决定；高毛利不自动等于高营业利润。
- 不能确定：单季费用率高就一定不好，因为研发、销售和管理投入可能服务于长期竞争。
- 需要继续观察：多季费用增长是否低于收入增长，AI 和云投入是否带来收入和现金流回报。
- 不构成投资建议的原因：本课只解释利润表结构和经营杠杆，不判断 Microsoft、Adobe 或任何证券是否值得买卖。

## 练习题

1. 用自己的话解释：为什么 Adobe 毛利率高于 Microsoft，但本课样本期营业利润率低于 Microsoft？
2. 如果一家公司的研发费用率上升，你会如何区分“浪费”和“长期投入”？
3. 什么情况下销售营销费用率上升可能是好事？什么情况下可能是风险？
4. 写出从收入到营业利润的三步公式，并解释经营杠杆从哪里来。

## 学习交接

- 本课已经完成：把毛利之后的营业费用、营业利润率和经营杠杆讲清楚，并用 Microsoft/Adobe 最新 10-Q 对照。
- 本课最重要的一句话：毛利率回答“产品本身留下多少”，营业利润率回答“公司运营后真正留下多少”。
- 需要复习的关键词：Operating Expenses、R&D、S&M、G&A、Operating Income、Operating Margin、Operating Leverage。
- 还不稳定、下次要回看的地方：费用率必须结合增长阶段、竞争压力和管理层投入方向，不能机械地越低越好。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第二十四课：净利润、利息、税费与非经营项目入门。
- 学习目标：理解营业利润之后，为什么还要扣利息、税费和其他非经营项目，知道净利润和核心经营利润的区别。
- 建议案例：继续使用 Microsoft、Adobe，必要时加入高负债公司或银行以解释利息费用差异。
- 必须解释的关键词：Net Income、Interest Expense、Income Tax、Other Income/Expense、Effective Tax Rate、Non-operating Items、One-time Items。
- 下节课开始前需要联网核验的数据：目标公司最新 10-Q/10-K、利息费用、税费、其他收入/费用、净利润、经营现金流；Fed/Treasury 利率背景是否变化。

## 来源

- SEC companyfacts, Microsoft Corporation: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
- Microsoft FY2026 Q3 Form 10-Q: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
- SEC companyfacts, Adobe Inc.: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
- Adobe FY2026 Q2 Form 10-Q: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
