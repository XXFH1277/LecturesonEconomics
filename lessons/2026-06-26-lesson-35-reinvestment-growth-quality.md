# 第三十五课：再投资率、增量 ROIC 与增长质量入门

## 基本信息

- 日期：2026-06-26
- 数据截至：2026-06-26 20:05（Asia/Shanghai）；公司财务采用 Microsoft 2026-04-29 Form 8-K exhibit 99.1、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 Adobe 2026-06-15 Form 10-Q；利率与信用利差采用 FRED / Federal Reserve / ICE BofA 2026-06-24 最新可得数据；Fed 政策采用 2026-06-17 FOMC statement。
- 主题：为什么高增长不一定是高质量增长，关键要看再投资后的增量回报。
- 学习目标：理解 Reinvestment Rate、Incremental ROIC、Maintenance Capex、Growth Capex、Operating Leverage、Unit Economics、Organic Growth、Acquired Growth、Buyback Yield 和 Capital Allocation，把“增长”拆成投入、回报和现金流压力。
- 相关资产：股票、公司债、云计算、AI 基础设施、软件订阅、并购、股票回购、自由现金流。
- 已核验来源（核心来源）：
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity, 2026-06-24: https://fred.stlouisfed.org/series/DGS10
  - FRED / ICE BofA US Corporate Index Effective Yield, 2026-06-24: https://fred.stlouisfed.org/series/BAMLC0A0CMEY

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第三十四课学了 ROIC 和经济利润。今天继续问：

> 如果一家公司的 ROIC 很高，是不是增长越快越好？

不一定。要看新增投入的回报率。如果老业务 ROIC 很高，但新项目需要大量资本、回报不确定，增长质量可能下降。真正好的增长，要同时满足三个条件：有需求、有投入、有高于资本成本的增量回报。

### 参考的教材式概念顺序

1. Growth：先看收入、利润或现金流是否增长。
2. Reinvestment：再看为了增长投了多少钱。
3. Maintenance Capex：区分维持现有业务所需的资本开支。
4. Growth Capex：区分为了未来扩张投入的资本开支。
5. Incremental ROIC：看新增投入带来多少新增税后经营利润。
6. Organic Growth：区分内生增长。
7. Acquired Growth：区分并购买来的增长。
8. Capital Allocation：把再投资、并购、回购、分红和偿债放在同一张图里比较。

### 核心概念

最小直觉：

```text
增长质量 = 增长速度 + 现金流质量 + 增量回报率

Incremental ROIC ≈ 新增 NOPAT / 新增投入资本

高质量增长：新增 ROIC > WACC，且现金流压力可承受
低质量增长：新增 ROIC < WACC，或增长需要越来越多低回报投入
```

再投资不是只有资本开支。研发、销售渠道、数据中心、库存、应收账款、并购、内容成本和客户补贴都可能是再投资。会计上有些被资本化，有些直接进费用，所以不能只看一行 capex。

### 用自己的话解释

公司增长像种地。收入增长是果实变多，再投资是施肥、买设备和扩地。只看果实，不看施了多少肥，会误判效率。最好的情况是：多施一点肥，果实持续多很多；最差的情况是：施肥越来越多，果实增长越来越少。

Incremental ROIC 就是在问：“新投进去的钱，回报是不是还像老业务一样好？”

### 常见误区

- 误区一：把收入增长自动等同于价值增长。收入可能是用低毛利、补贴、重资产或高风险并购买来的。
- 误区二：只看自由现金流，不看增长投入阶段。早期高回报项目可能先压低自由现金流。
- 误区三：只看 capex，不看研发和销售费用。软件公司很多再投资直接进费用。
- 误区四：把并购增长当成内生增长。买来的收入要看价格、整合、商誉和留存。
- 误区五：把回购当成永远正确。只有在价格合理、现金流充足且缺少更高回报再投资机会时，回购才更可能创造价值。

## 第二大板块：实时背景与市场传导

### 发生了什么

Microsoft 2026 Q3 披露：季度 revenue 为 828.86 亿美元，同比增长 18%；operating income 为 383.98 亿美元，同比增长 20%；Microsoft Cloud revenue 为 545 亿美元，同比增长 29%；Azure and other cloud services revenue 同比增长 40%。同一披露中，Microsoft 2026 财年前九个月 net cash from operations 为 1,274.94 亿美元，additions to property and equipment 为 801.46 亿美元，common stock repurchased 为 176.92 亿美元，cash dividends paid 为 196.87 亿美元。

Adobe 2026 Q2 披露：季度 revenue 为 66.18 亿美元，同比增长 13%；GAAP operating income 为 22.38 亿美元；cash flows from operations 为 21.65 亿美元；exiting quarter RPO 为 222.7 亿美元，cRPO 为 67%；total Adobe ARR 为 271.0 亿美元，其中约 4.80 亿美元来自 Semrush。Adobe 2026 财年上半年 Form 10-Q 披露，net cash provided by operating activities 为 51.23 亿美元，purchases of property and equipment 为 0.95 亿美元，acquisitions net of cash acquired 为 15.60 亿美元，repurchases of common stock 为 45.89 亿美元。

这两个案例都在增长，但增长的资本形态不同：Microsoft 更偏 AI / cloud 基础设施重投入；Adobe 更偏订阅现金流、产品研发、并购补充和回购。

### 为什么重要

如果只看收入增长，Microsoft 和 Adobe 都不错。但资本市场真正关心的是：

- Microsoft 的 AI/cloud 资本开支能不能带来足够长、足够高的增量回报？
- Adobe 的 ARR、RPO 和 Semrush 并购能不能转化为可持续现金流，而不是只形成商誉和短期叙事？
- 两家公司在再投资、回购、分红和债务之间的排序，是否和自身 ROIC、WACC、现金流质量匹配？

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Microsoft Q3 revenue growth | 18% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 观察增长速度 |
| Microsoft Q3 operating income growth | 20% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 观察经营杠杆 |
| Microsoft Cloud revenue | 545 亿美元，+29% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | AI/cloud 增长案例 |
| Azure and other cloud services growth | +40% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 观察高增长业务 |
| Microsoft nine-month operating cash flow | 1,274.94 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 现金来源 |
| Microsoft nine-month additions to property and equipment | 801.46 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 再投资强度 |
| Microsoft nine-month stock repurchases | 176.92 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 资本配置 |
| Adobe Q2 revenue growth | 13% | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 观察增长速度 |
| Adobe Q2 operating cash flow | 21.65 亿美元 | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 现金来源 |
| Adobe six-month operating cash flow | 51.23 亿美元 | Adobe 2026-06-15 Form 10-Q | 现金质量 |
| Adobe six-month property and equipment purchases | 0.95 亿美元 | Adobe 2026-06-15 Form 10-Q | 资本开支强度 |
| Adobe six-month acquisitions, net of cash acquired | 15.60 亿美元 | Adobe 2026-06-15 Form 10-Q | 并购增长 |
| Adobe six-month stock repurchases | 45.89 亿美元 | Adobe 2026-06-15 Form 10-Q | 回购配置 |
| 10 年期 Treasury yield | 4.41% | FRED / H.15, 2026-06-24 | 资本成本背景 |
| IG corporate effective yield | 5.14% | FRED / ICE BofA, 2026-06-24 | 债务市场背景 |

### Microsoft：高增长和高资本开支同时出现

Microsoft 2026 财年前九个月的课堂现金流近似：

```text
经营现金流 = 1,274.94 亿美元
Additions to property and equipment = 801.46 亿美元
自由现金流近似 = 1,274.94 - 801.46 = 473.48 亿美元
资本开支强度近似 = 801.46 / 1,274.94 = 62.9%
```

这个数字说明 Microsoft 仍然产生大量自由现金流，但 AI/cloud 基础设施投入也非常重。课堂结论不是“好”或“坏”，而是要追问：

- 这些数据中心、服务器和网络投入是维护现有业务，还是为未来增长扩容？
- Azure 增长 40% 是否能在未来覆盖折旧、能源、芯片、网络和运营成本？
- 如果利率和信用利差维持较高，项目要求的最低回报会不会上升？
- 同时回购和分红时，公司是否仍有足够安全垫？

### Adobe：低有形资本开支，但并购和回购同样是资本配置

Adobe 2026 财年上半年的课堂现金流近似：

```text
经营现金流 = 51.23 亿美元
Purchases of property and equipment = 0.95 亿美元
自由现金流近似 = 51.23 - 0.95 = 50.28 亿美元
有形资本开支强度近似 = 0.95 / 51.23 = 1.9%
Acquisitions, net of cash acquired = 15.60 亿美元
Repurchases of common stock = 45.89 亿美元
```

这说明 Adobe 的有形资本开支很轻，但它并不是“没有再投资”。研发、销售、AI 产品、Semrush 并购、客户获取和回购都是资本配置问题。Adobe Q2 披露 AI-first ARR triples year over year and exceeds 5 亿美元，同时 total Adobe ARR 为 271.0 亿美元。学习者要把这些增长信号和现金流、商誉、RPO、续费、价格、竞争和回购价格一起看。

### 这些现实事件如何连接理论

- 重资本增长：可能先压低自由现金流，但如果增量 ROIC 高，长期仍可能创造价值。
- 资产轻增长：有形 capex 少，但研发、销售和并购可能隐藏了重要投入。
- 并购增长：收入来得快，但要看买入价格、商誉、整合和留存。
- 回购：减少股数、可能提高 EPS，但如果买贵或挤压高回报再投资，就可能降低长期价值。
- 利率背景：10 年期 Treasury yield 和公司债收益率越高，资本项目需要跨过的门槛越高。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Fed 利率政策、SEC 披露制度、AI 基础设施投资、并购会计、股票回购披露、软件收入确认和商誉减值规则。
- 已确认事实：Fed 2026-06-17 维持目标区间 3.50%-3.75%；FRED 2026-06-24 10 年期 Treasury yield 为 4.41%；Microsoft 与 Adobe 的增长、现金流、资本开支、并购和回购数据来自 SEC 文件。
- 市场可能如何传导：高利率提高资本成本；AI 基础设施投资提高资本强度；并购提高商誉和整合风险；回购影响股数、现金和权益。
- 仍需核验或观察：Microsoft 后续 AI capex、Azure 增长和折旧；Adobe AI-first ARR、Semrush 整合、RPO 转收入、商誉、回购价格和现金余额。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Reinvestment Rate | 再投资率 | 公司把多少利润或现金重新投回业务 | 决定增长速度和现金流压力 |
| Incremental ROIC | 增量投入资本回报率 | 新增投入带来的新增税后经营回报 | 判断新增长是否还像老业务一样赚钱 |
| Maintenance Capex | 维持性资本开支 | 维持现有产能和服务能力必须花的钱 | 不能把所有 capex 都当增长投入 |
| Growth Capex | 增长性资本开支 | 为未来扩张投入的钱 | 可能压低短期现金流，换取未来增长 |
| Operating Leverage | 经营杠杆 | 收入增长快于固定成本时利润放大的现象 | 帮助判断增长能否转化为利润 |
| Unit Economics | 单位经济模型 | 单个客户、订单或产品的收入、成本和利润结构 | 防止只看总收入不看每单是否赚钱 |
| Organic Growth | 内生增长 | 公司靠自身产品、渠道和客户增长 | 通常比并购增长更能反映核心竞争力 |
| Acquired Growth | 并购增长 | 通过买公司或资产获得增长 | 要看价格、整合、商誉和留存 |
| Buyback Yield | 回购收益率 | 回购金额相对市值的比例 | 观察回购对股东回报和股数的影响 |
| Capital Allocation | 资本配置 | 再投资、并购、回购、分红、偿债之间的排序 | 决定现金如何转化为长期价值 |

## 回顾提示

- 学到本课前建议回顾：第 13 课资本配置、第 17 课 Capex 与自由现金流、第 34 课 ROIC 与经济利润。
- 本课哪些内容会在后续课程继续使用：护城河、竞争优势、长期增长率、终值假设、回购质量、并购质量和管理层资本配置。
- 如果看不懂本课，可以先回到：第 29 课自由现金流收益率、第 31 课情景分析与敏感性分析。

## 案例拆解

- 案例对象：Microsoft 的 AI/cloud 重投入增长，与 Adobe 的订阅现金流、并购和回购配置。
- 已确认事实：
  - Microsoft Q3 revenue 增长 18%，operating income 增长 20%，Microsoft Cloud revenue 为 545 亿美元并增长 29%，Azure and other cloud services revenue 增长 40%。
  - Microsoft 2026 财年前九个月经营现金流为 1,274.94 亿美元，additions to property and equipment 为 801.46 亿美元，common stock repurchased 为 176.92 亿美元。
  - Adobe Q2 revenue 为 66.18 亿美元并增长 13%，GAAP operating income 为 22.38 亿美元，Q2 operating cash flow 为 21.65 亿美元，RPO 为 222.7 亿美元。
  - Adobe 2026 财年上半年经营现金流为 51.23 亿美元，有形资本开支为 0.95 亿美元，并购现金流出为 15.60 亿美元，回购为 45.89 亿美元。
- 来源日期和链接：见本课“来源”。
- 分析推理：Microsoft 的增长质量更依赖未来 AI/cloud 资本开支能否持续产生高回报；Adobe 的增长质量更依赖订阅留存、AI 产品变现、Semrush 并购整合和回购价格是否合理。
- 后续验证指标：新增收入、经营利润增量、capex、折旧、RPO 转收入、ARR 留存、并购整合成本、商誉减值、股数变化、回购均价、债务成本和 WACC。

## 个人情境连接

- 对关注清单的启发：看到“高增长”时，先问增长是内生、并购、涨价、补贴还是会计口径变化。
- 对持仓或基金选择的启发：重仓 AI/cloud 或软件公司的基金，要同时看增长叙事和资本开支、现金流、回购、并购。
- 对工作、收入、消费或风险管理的启发：个人成长也需要再投资。学习、工具和时间投入要看能否提高未来收入或选择权，而不是只看短期支出。

## 结论边界

- 可以确定：增长质量必须看再投资、现金流和增量回报；capex 少不等于没有投入，capex 多也不等于浪费。
- 不能确定：本课没有判断 Microsoft 或 Adobe 的未来 AI 投资回报，也没有给出任何目标价或买卖建议。
- 需要继续观察：新增投入是否带来新增利润、现金流和客户留存；高利率环境是否改变资本配置排序；并购和回购是否改善长期每股价值。
- 不构成投资建议的原因：本课只训练增长质量拆解，不推荐买入或卖出任何证券。

## 练习题

1. 为什么“收入增长 20%”不一定等于“价值增长 20%”？
2. Microsoft 经营现金流为 1,274.94 亿美元，property and equipment additions 为 801.46 亿美元。自由现金流近似是多少？这个数为什么不是完整估值结论？
3. Adobe 有形资本开支很低，为什么仍然要看研发、销售、并购和回购？
4. 什么情况下回购可能提高 EPS，却不一定创造长期价值？
5. 任选一家公司，列出你会用来验证“增量 ROIC 是否下降”的五个指标。

## 学习交接

- 本课已经完成：把 ROIC 推进到再投资率、增量 ROIC、增长质量、AI/cloud 重资本投入、软件并购和回购质量。
- 本课最重要的一句话：好增长不是增长快，而是新增投入能持续赚到高于资本成本的回报。
- 需要复习的关键词：Reinvestment Rate、Incremental ROIC、Maintenance Capex、Growth Capex、Operating Leverage、Unit Economics、Organic Growth、Acquired Growth、Buyback Yield、Capital Allocation。
- 还不稳定、下次要回看的地方：高 ROIC 为什么能维持，背后通常需要竞争优势、网络效应、转换成本、规模经济或监管/品牌壁垒。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第三十六课：护城河、竞争优势与 ROIC 持续性入门。
- 学习目标：理解为什么有些公司能长期保持高 ROIC，而多数公司会被竞争拉回平均水平。
- 建议案例：继续使用 Microsoft 与 Adobe，可加入一只资本密集或低毛利公司作对照；必须重新核验 SEC、公司 IR、交易所或权威数据。
- 必须解释的关键词：Moat、Competitive Advantage、Switching Cost、Network Effects、Scale Economies、Brand、Pricing Power、Customer Retention、Churn、Competitive Fade。
- 下节课开始前需要联网核验的数据：Microsoft 与 Adobe 最新收入分部、毛利率、经营利润率、RPO/ARR、客户留存或相关披露、竞争风险因素、AI 投资进展、股价和利率背景；如加入对照公司，必须核验其最新 SEC/IR 披露。

## 来源

- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity: https://fred.stlouisfed.org/series/DGS10
- FRED / ICE BofA US Corporate Index Effective Yield: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
