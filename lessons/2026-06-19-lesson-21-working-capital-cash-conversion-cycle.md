# 第二十一课：营运资本与现金转换周期入门

## 基本信息

- 日期：2026-06-19
- 数据截至：2026-06-19 19:00（Asia/Shanghai）；公司数据采用截至本次写作时 SEC 已披露的最新 10-Q/10-K 与 SEC companyfacts；利率背景采用 2026-06-18 U.S. Treasury 和 2026-06-17 Federal Reserve。
- 主题：应收账款、库存、应付账款如何组成“经营里的现金循环”
- 学习目标：理解营运资本、库存周转、应付账款和现金转换周期，知道为什么有些公司收入很高但仍然很占现金。
- 相关资产：股票、公司财报、供应链、消费品、半导体、硬件公司。
- 核心来源：
  - SEC companyfacts: Apple Inc., CIK 0000320193: https://data.sec.gov/api/xbrl/companyfacts/CIK0000320193.json
  - Apple FY2026 Q2 Form 10-Q, accession `0000320193-26-000013`: https://www.sec.gov/Archives/edgar/data/320193/000032019326000013/aapl-20260328.htm
  - SEC companyfacts: NVIDIA Corporation, CIK 0001045810: https://data.sec.gov/api/xbrl/companyfacts/CIK0001045810.json
  - NVIDIA FY2027 Q1 Form 10-Q, accession `0001045810-26-000052`: https://www.sec.gov/Archives/edgar/data/1045810/000104581026000052/nvda-20260426.htm
  - SEC companyfacts: NIKE, Inc., CIK 0000320187: https://data.sec.gov/api/xbrl/companyfacts/CIK0000320187.json
  - Nike FY2026 Q3 Form 10-Q, accession `0000320187-26-000037`: https://www.sec.gov/Archives/edgar/data/320187/000032018726000037/nke-20260228.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十课讲的是：客户欠我的钱多久能回来。今天把问题扩展一步：

> 一家公司从买原材料、生产库存、卖给客户、收回现金，中间到底占用了多少现金？

这就是营运资本和现金转换周期要回答的问题。

### 参考的教材式概念顺序

1. 公司先准备商品或服务能力：形成库存或在制项目。
2. 公司卖出商品或服务：形成收入。
3. 客户可能晚一点付款：形成应收账款。
4. 公司也可能晚一点付供应商钱：形成应付账款。
5. 现金转换周期把这三件事合起来看：库存占用多久、客户多久付款、公司多久付供应商。

### 核心概念

- 营运资本（Working Capital）：日常经营中被应收账款、库存、应付账款等短期项目占用或释放的资金。
- 库存（Inventory）：已经买来或生产出来、准备未来销售的商品或材料。
- 应付账款（Accounts Payable, A/P）：公司欠供应商的钱，通常是已经收到货或服务但还没付款。
- DIO（Days Inventory Outstanding，库存周转天数）：库存平均要多少天卖出去。
- DPO（Days Payable Outstanding，应付账款周转天数）：公司平均多少天给供应商付款。
- CCC（Cash Conversion Cycle，现金转换周期）：现金从投入经营到收回的净天数。

### 用自己的话解释

现金转换周期可以先记成一句话：

```text
现金转换周期 = 库存占用天数 + 客户付款天数 - 公司拖到多久付供应商
CCC = DIO + DSO - DPO
```

如果 DIO 很高，钱卡在库存里。
如果 DSO 很高，钱卡在客户那里。
如果 DPO 较高，公司暂时用供应商信用缓冲现金压力。

### 常见误区

- 误区一：营运资本越高越安全。实际可能说明现金被库存和应收账款占住了。
- 误区二：应付账款越高越差。合理账期内，应付账款也可能是供应链信用。
- 误区三：现金转换周期可以跨行业直接比较。软件、消费品、硬件、半导体的商业模式差异很大，必须先同行比较。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课选择三个不同类型公司做入门观察：

| 公司 | 最新 SEC 报告 | 观察重点 | SEC companyfacts 已核验数字 |
| --- | --- | --- | --- |
| Apple | FY2026 Q2 10-Q, filed 2026-05-01 | 硬件和服务混合模式，库存相对收入较小，应付账款很大 | 2026-03-28 应收账款 303.39 亿美元、库存 67.47 亿美元、应付账款 573.49 亿美元、单季收入 1111.84 亿美元 |
| NVIDIA | FY2027 Q1 10-Q, filed 2026-05-20 | AI 芯片需求强，但库存、应收和供应链付款也要跟踪 | 2026-04-26 应收账款 407.10 亿美元、库存 257.97 亿美元、应付账款 130.97 亿美元、单季收入 816.15 亿美元 |
| Nike | FY2026 Q3 10-Q, filed 2026-04-01 | 消费品公司更容易受库存、渠道和打折周期影响 | 2026-02-28 应收账款 53.69 亿美元、成品库存 74.87 亿美元、应付账款 28.88 亿美元、单季收入 112.79 亿美元 |

这些数字的意义不是“谁一定更好”，而是让零基础学习者看到：不同商业模式的现金占用位置不同。

### 为什么重要

Federal Reserve 2026-06-17 维持联邦基金目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-18 的 2 年期国债收益率为 4.00%，10 年期为 4.34%，30 年期为 4.90%。当资金有明显时间成本时，市场会更在意：

- 库存是否需要降价清理；
- 应收账款是否变慢；
- 供应商账期是否可持续；
- 公司是否能用经营现金流支持扩张，而不是不断依赖外部融资。

### 本节采用的数据和来源

- Apple、NVIDIA、Nike 的 SEC companyfacts 与最新 10-Q。
- Federal Reserve 2026-06-17 FOMC statement。
- U.S. Treasury 2026-06-18 Daily Treasury Rates。

### 这些现实事件如何连接理论

Apple 的应付账款远高于库存，说明供应链付款节奏是其现金循环的重要组成部分。NVIDIA 在 AI 需求强劲阶段，应收账款和库存都值得跟踪，因为交付、客户集中度和供应链安排会影响现金质量。Nike 的库存占收入比例更直观，消费品公司若库存卖得慢，可能需要打折，从而影响毛利率和现金流。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、供应链账期、利率政策、国际制造与渠道库存。
- 已确认事实：三家公司最新 10-Q 已在 SEC 披露；Fed 和 Treasury 已发布最新利率背景。
- 市场可能如何传导：利率越高，库存和应收账款占用资金的机会成本越高；供应链紧张或需求下滑会改变 DIO、DSO、DPO。
- 仍需核验或观察：下一季库存是否继续上升、应收账款是否快于收入增长、应付账款账期是否稳定。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Working Capital | 营运资本 | 日常经营占用或释放的短期资金 | 连接资产负债表和现金流 |
| Inventory | 库存 | 等待销售的商品或材料 | 库存卖得慢会压住现金 |
| Accounts Payable / A/P | 应付账款 | 公司欠供应商的钱 | 供应商账期会缓冲现金压力 |
| DIO | 库存周转天数 | 库存平均多少天卖出去 | 衡量库存压力 |
| DPO | 应付账款周转天数 | 公司平均多少天付供应商 | 衡量供应链信用 |
| Cash Conversion Cycle / CCC | 现金转换周期 | 钱从投入经营到回来的净天数 | 判断经营现金效率 |

## 回顾提示

- 学到本课前建议回顾：第 10 课三张报表、第 17 课自由现金流、第 20 课应收账款与 DSO。
- 本课哪些内容会在后续课程继续使用：现金转换周期、存货减值、毛利率、供应链融资。
- 如果看不懂本课，可以先回到：第 20 课“应收账款、DSO、坏账准备”。

## 案例拆解

- 案例对象：Apple、NVIDIA、Nike 的营运资本结构对比。
- 已确认事实：
  - Apple 2026-03-28：应收账款 303.39 亿美元、库存 67.47 亿美元、应付账款 573.49 亿美元。
  - NVIDIA 2026-04-26：应收账款 407.10 亿美元、库存 257.97 亿美元、应付账款 130.97 亿美元。
  - Nike 2026-02-28：应收账款 53.69 亿美元、成品库存 74.87 亿美元、应付账款 28.88 亿美元。
- 来源日期和链接：三家公司最新 10-Q 与 SEC companyfacts，链接见本课来源。
- 分析推理：硬件平台、AI 芯片和消费品公司的现金循环压力点不同；同样是“营运资本”，不能脱离商业模式解读。
- 后续验证指标：收入增速、毛利率、库存增速、经营现金流、应收账款增速、应付账款变化。

## 个人情境连接

- 对关注清单的启发：看消费品公司时要多看库存；看企业软件和大型客户业务时要多看应收；看硬件供应链时要多看应付和库存。
- 对持仓或基金选择的启发：基金重仓的行业不同，现金循环风险也不同，不能只看市盈率。
- 对工作、收入、消费或风险管理的启发：个人经营也有现金转换周期。进货、赊销、收款、付款的节奏错配，会让“账面赚钱”变成“现金紧张”。

## 结论边界

- 可以确定：营运资本把应收账款、库存、应付账款连成经营现金循环；CCC 是理解经营现金效率的入门框架。
- 不能确定：仅凭一个季度的库存、应收或应付数字就判断公司好坏。
- 需要继续观察：至少连续三到四个季度的趋势，并结合行业季节性、毛利率和经营现金流。
- 不构成投资建议的原因：本课只讲财务分析框架，不给出任何买卖结论。

## 练习题

1. 用自己的话解释：为什么应付账款会让现金转换周期变短？
2. Apple、NVIDIA、Nike 三家公司中，哪一家最需要你重点盯库存？为什么？
3. 如果一家消费品公司收入下降但库存上升，你会担心哪些后续影响？
4. 试着写出现金转换周期公式，并说明 DIO、DSO、DPO 分别对应哪张报表里的项目。

## 学习交接

- 本课已经完成：把应收、库存、应付合并成营运资本和现金转换周期框架。
- 本课最重要的一句话：利润表展示经营成果，营运资本展示这些成果在现金回收前被卡在哪里。
- 需要复习的关键词：Working Capital、Inventory、Accounts Payable、DIO、DPO、CCC。
- 还不稳定、下次要回看的地方：现金转换周期必须同行比较，不能直接跨行业排名。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第二十二课：毛利率、库存减值与折扣周期入门。
- 学习目标：理解库存卖不动如何从资产负债表传导到利润表的毛利率和减值。
- 建议案例：Nike 或其他消费品公司库存变化；如涉及公司，必须重新核验最新 10-Q/10-K。
- 必须解释的关键词：Gross Margin、Markdown、Inventory Write-down、Obsolescence、Channel Inventory。
- 下节课开始前需要联网核验的数据：目标公司最新 10-Q/10-K、库存和毛利率变化、Fed/Treasury 利率背景是否变化。

## 来源

- SEC companyfacts, Apple Inc.: https://data.sec.gov/api/xbrl/companyfacts/CIK0000320193.json
- Apple FY2026 Q2 Form 10-Q: https://www.sec.gov/Archives/edgar/data/320193/000032019326000013/aapl-20260328.htm
- SEC companyfacts, NVIDIA Corporation: https://data.sec.gov/api/xbrl/companyfacts/CIK0001045810.json
- NVIDIA FY2027 Q1 Form 10-Q: https://www.sec.gov/Archives/edgar/data/1045810/000104581026000052/nvda-20260426.htm
- SEC companyfacts, NIKE, Inc.: https://data.sec.gov/api/xbrl/companyfacts/CIK0000320187.json
- Nike FY2026 Q3 Form 10-Q: https://www.sec.gov/Archives/edgar/data/320187/000032018726000037/nke-20260228.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
