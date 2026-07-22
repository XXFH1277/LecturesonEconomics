# 第六十课：原油、能源通胀、美元与利率传导入门

## 基本信息

- 日期：2026-07-22
- 数据截至：2026-07-22 20:05（Asia/Shanghai）。EIA Weekly Petroleum Status Report 最新可用版本为 2026-07-15 发布、截至 2026-07-10 的周度数据，下一次发布时间为 2026-07-22 美东时间；EIA 现货价格页最新可用价格发布于 2026-07-15、截至 2026-07-13；Federal Reserve H.15 最新发布日为 2026-07-21、截至 2026-07-20；Federal Reserve H.10 最新发布日为 2026-07-20、截至 2026-07-17；CPI 采用 BLS 2026-07-14 发布的 2026 年 6 月数据。
- 主题：为什么原油价格会影响通胀、利率、美元和跨资产风险偏好。
- 学习目标：理解 crude oil、WTI、Brent、inventory、refinery utilization、energy inflation、real income、policy reaction function、dollar pricing 和 pass-through。
- 相关资产：WTI、Brent、汽油、柴油、航空燃料、美国国债、美元、能源股、航空与运输行业、宽基股票基金。
- 核心来源：
  - EIA, Weekly Petroleum Status Report, release date 2026-07-15: https://www.eia.gov/petroleum/supply/weekly/
  - EIA, Spot Prices for Crude Oil and Petroleum Products, release date 2026-07-15: https://www.eia.gov/dnav/pet/pet_pri_spt_s1_d.htm
  - EIA, What Drives Crude Oil Prices: https://www.eia.gov/finance/markets/crudeoil/
  - BLS, Consumer Price Index, June 2026, release date 2026-07-14: https://www.bls.gov/cpi/
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-21: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, H.10 Foreign Exchange Rates, release date 2026-07-20: https://www.federalreserve.gov/releases/H10/current/
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - OPEC, OPEC+ countries production adjustment press release, 2026-07-05: https://www.opec.org/pr-detail/1835609-5-july-2026.html

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲美元、汇率和跨境资产折算。今天把美元旁边最重要的商品变量接上：

> 为什么油价一动，市场会同时讨论通胀、利率、美元、股票行业表现和普通人的实际收入？

因为原油不是普通商品。它既是能源投入，也是运输、化工、航空、农业和居民消费的成本入口。油价变化不只改变油企利润，还会沿着汽油、柴油、机票、运费、塑料和取暖成本进入经济。

### 参考的教材式概念顺序

1. Crude Oil：原油，未经炼制的石油。
2. Barrel：桶，原油常用计量单位，1 桶约 42 美制加仑。
3. WTI：西德州中质原油，美国常用基准，交割中心在 Cushing, Oklahoma。
4. Brent：布伦特原油，国际常用海运原油基准。
5. Spot Price：现货价格，今天附近交割的市场价格。
6. Inventory：库存，已经生产但尚未消费或加工的油。
7. Refinery：炼厂，把原油加工成汽油、柴油、航煤等产品。
8. Refinery Utilization：炼厂开工率，炼厂实际处理量相对可用产能。
9. Energy Inflation：能源通胀，能源相关价格对 CPI/PPI 的贡献。
10. Real Income：实际收入，名义收入扣除物价上涨后的购买力。
11. Policy Reaction Function：政策反应函数，央行如何根据通胀、就业和金融条件调整政策。
12. Pass-through：传导，成本从上游原油进入下游产品和最终消费价格。

### 核心概念

原油传导可以先画成一条最小链：

```text
原油供需和库存
-> WTI / Brent 价格
-> 汽油、柴油、航煤和化工成本
-> CPI、PPI、企业利润率和居民实际收入
-> 通胀预期和央行政策
-> 利率、美元、股债商品和风险偏好
```

这条链不是机械公式。油价上涨是否进入核心通胀，要看持续时间、工资价格循环、企业定价权、政府补贴、汇率和需求是否同步变弱。

### 用自己的话解释

原油像经济系统里的上游水位。水位短期上升，最先感受到的是汽油、柴油、航空燃料和运输成本；再往后，可能影响商品运输、服务价格、企业利润率和家庭预算。

如果油价上涨只是短期扰动，央行可能更关注它是否会扩散到长期通胀预期。如果油价上涨持续很久，居民实际收入被挤压，企业成本被推高，通胀预期也可能更难回落，央行就更难快速降息。

### 常见误区

- 误区一：原油涨，能源股一定涨。能源公司还要看生产成本、对冲、税费、资本开支和产量。
- 误区二：油价涨，所有股票都跌。部分能源和炼化公司可能受益，航空、运输、消费行业可能承压。
- 误区三：CPI 里的汽油涨跌等于全部通胀。核心通胀、服务通胀和工资仍要单独看。
- 误区四：WTI 和 Brent 是同一个油价。它们代表不同地区、物流和品质背景，价差本身也是信息。
- 误区五：库存下降一定意味着马上缺油。还要看季节性、炼厂开工、进口、出口、战略储备和库存可用性。

## 第二大板块：实时背景与市场传导

### 发生了什么

EIA 2026-07-15 发布的 Weekly Petroleum Status Report 显示，截至 2026-07-10 当周：

| 指标 | 最新已核验事实 | 教学解释 |
| --- | ---: | --- |
| 美国炼厂原油投入 | 17.1 million b/d | 炼厂吃进多少原油 |
| 炼厂开工率 | 96.2% | 夏季燃料需求和高利润下的高负荷 |
| 商业原油库存 | 409.7 million barrels | 不含战略石油储备 |
| 商业原油库存周变化 | -1.7 million barrels | 库存继续下降 |
| 商业原油库存相对五年均值 | 约低 6% | 库存偏紧背景 |
| 汽油库存周变化 | -1.5 million barrels | 成品油库存下降 |
| 汽油库存相对五年均值 | 约低 8% | 夏季驾驶季约束 |
| 馏分油库存周变化 | +4.6 million barrels | 柴油/取暖油类库存回补 |
| 馏分油库存相对五年均值 | 约低 11% | 即使回补，仍低于常态 |
| 总产品供应四周均值 | 20.3 million b/d | 近似观察石油产品需求 |

EIA 现货价格页显示，2026-07-13 WTI-Cushing 为 79.20 美元/桶，Brent-Europe 为 81.62 美元/桶；同日 New York Harbor regular gasoline 为 3.171 美元/加仑，New York Harbor ultra-low-sulfur diesel 为 3.866 美元/加仑。

BLS 2026-07-14 发布的 CPI 显示，2026 年 6 月 CPI 全项目环比下降 0.4%（季调），同比上升 3.5%（未季调）；能源同比上升 15.7%，汽油同比上升 26.7%，核心 CPI 同比上升 2.6%。这说明能源价格仍是总通胀读数里的重要变量，但核心通胀口径需要单独观察。

Federal Reserve 2026-06-17 FOMC statement 维持 federal funds target range 在 3.50%-3.75%，并明确把部分通胀压力与包括能源在内的供给冲击联系起来。H.15 2026-07-21 release 显示，截至 2026-07-20，effective federal funds rate 为 3.63%，10 年 nominal CMT 为 4.60%，10 年 TIPS yield 为 2.35%。

OPEC 2026-07-05 新闻稿显示，七个 OPEC+ 国家决定在 2026 年 8 月实施 188 thousand barrels per day 的产量调整，并保留根据市场情况增加、暂停或逆转调整的灵活性。

### 为什么重要

这组数据把第 56-59 课的利率、实际利率、美元和汇率放进原油场景：

```text
油价和成品油价格上行
-> 能源 CPI 压力
-> 居民实际收入和企业成本受挤压
-> Fed 更关注通胀是否扩散
-> 利率预期和美元可能变化
-> 股票行业表现分化
```

如果油价上涨来自供给冲击，经济会同时遇到“物价更高”和“实际购买力更弱”。这和普通需求强劲引起的通胀不同：前者更像成本推升，后者更像需求拉动。政策难点也不同。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| WPSR 最新周度数据 | week ending 2026-07-10 | EIA, 2026-07-15 | 库存和炼厂背景 |
| 商业原油库存 | 409.7 million barrels | EIA, 2026-07-15 | 供需平衡观察 |
| 炼厂开工率 | 96.2% | EIA, 2026-07-15 | 成品油供应链 |
| WTI-Cushing | 79.20 美元/桶 | EIA, 2026-07-13 | 美国基准油价 |
| Brent-Europe | 81.62 美元/桶 | EIA, 2026-07-13 | 国际基准油价 |
| CPI 全项目同比 | 3.5% | BLS, 2026-06 | 通胀背景 |
| 能源 CPI 同比 | 15.7% | BLS, 2026-06 | 能源通胀 |
| 汽油 CPI 同比 | 26.7% | BLS, 2026-06 | 居民成本入口 |
| FOMC target range | 3.50%-3.75% | Fed, 2026-06-17 | 政策反应背景 |
| 10Y nominal CMT | 4.60% | Fed H.15, 2026-07-20 | 长端利率 |
| 10Y TIPS yield | 2.35% | Fed H.15, 2026-07-20 | 实际利率观察 |
| USD/CNY | 6.7760 | Fed H.10, 2026-07-17 | 美元计价和汇率折算 |
| Broad dollar index | 120.5315 | Fed H.10, 2026-07-17 | 美元整体强弱 |
| OPEC+ 产量调整 | 188 thousand b/d | OPEC, 2026-07-05 | 供给规则背景 |

### 这些现实事件如何连接理论

第一条链：库存和价格。

```text
商业原油库存低于五年均值
-> 市场缓冲垫较薄
-> 同样的供给扰动更容易被价格放大
```

第二条链：成品油和通胀。

```text
原油价格 + 炼厂开工 + 汽油/柴油库存
-> 汽油、柴油、航煤价格
-> 居民交通成本和企业物流成本
-> CPI、PPI、利润率和实际收入
```

第三条链：能源冲击和政策。

```text
能源通胀持续
-> 通胀预期更难回落
-> Fed 降息空间可能受限
-> 美元利差和实际利率背景改变
```

这不是说油价一涨 Fed 就一定加息。央行还会同时看就业、核心通胀、金融条件、通胀预期和冲击是否暂时。

### 至少一个真实市场机制案例

案例：用 2026-07-13 的 EIA 现货价格做“原油到成品油”的单位转换。

```text
1 桶 = 42 加仑
WTI = 79.20 美元/桶
New York Harbor regular gasoline = 3.171 美元/加仑
汽油折成每桶价格约 = 3.171 x 42 = 133.18 美元/桶
```

这不是炼厂利润的完整计算，因为真实炼厂还要看原油品质、产品收率、运输、税费、运营成本、库存和对冲。但它能帮助零基础学习者看到：成品油价格和原油价格不是同一个数，中间隔着炼化、物流和地区市场。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：OPEC+ 产量协调、美国 EIA 能源统计、Federal Reserve 货币政策、BLS 通胀统计、美元计价商品市场、地缘运输通道。
- 已确认事实：EIA 最新周报显示美国商业原油库存下降且低于五年均值；BLS 6 月 CPI 中能源同比仍明显高于总 CPI；Fed 6 月声明维持目标利率并提到能源供给冲击；OPEC+ 七国宣布 8 月产量调整。
- 市场可能如何传导：油价影响能源 CPI 和实际收入；通胀压力影响利率预期；利率和美元影响跨资产风险偏好；行业利润在能源、炼化、航空、运输和消费之间重新分配。
- 仍需核验或观察：EIA 2026-07-22 周报、Brent/WTI 价差、汽油和馏分油库存、BLS 7 月 CPI、下一次 FOMC、OPEC+ 2026-08-02 会议、美元 H.10 和 H.15 利率。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Crude Oil | 原油 | 未炼制的石油 | 能源和化工上游 |
| WTI | 西德州中质原油 | 美国常用原油基准 | 连接美国库存和 Cushing |
| Brent | 布伦特原油 | 国际海运原油基准 | 全球油价观察入口 |
| Inventory | 库存 | 已有但尚未消费或加工的油 | 衡量供需缓冲垫 |
| Refinery Utilization | 炼厂开工率 | 炼厂实际处理量占可用产能比例 | 决定成品油供应 |
| Energy Inflation | 能源通胀 | 能源价格对物价的影响 | 影响 CPI、实际收入和政策 |
| Real Income | 实际收入 | 扣除物价后的购买力 | 油价会挤压家庭预算 |
| Policy Reaction Function | 政策反应函数 | 央行面对通胀和就业如何反应 | 连接能源和利率 |
| Dollar Pricing | 美元计价 | 原油国际价格多用美元报价 | 汇率会改变非美元买家成本 |
| Pass-through | 价格传导 | 上游成本传到下游价格 | 判断冲击是否扩散 |

## 回顾提示

- 学到本课前建议回顾：第 6 课黄金和原油入门、第 56 课政策利率传导、第 58 课实际利率、第 59 课美元与汇率。
- 本课哪些内容会在后续课程继续使用：库存、炼厂、成品油、能源 CPI、美元计价、OPEC+、风险溢价。
- 如果看不懂本课，可以先回到：第 1 课供需和价格，第 5 课利率，第 57 课收益率曲线。

## 案例拆解

- 案例对象：2026-07-10 当周 EIA 原油库存、2026-07-13 EIA 现货价格、2026 年 6 月 CPI 和 2026-06-17 FOMC statement。
- 已确认事实：
  - 美国商业原油库存为 409.7 million barrels，较前周下降 1.7 million barrels。
  - 美国炼厂开工率为 96.2%。
  - 2026-07-13 WTI 为 79.20 美元/桶，Brent 为 81.62 美元/桶。
  - 2026 年 6 月 CPI 全项目同比 3.5%，能源同比 15.7%，汽油同比 26.7%。
  - Fed 维持 3.50%-3.75% 目标区间。
- 来源日期和链接：见本课“来源”。
- 分析推理：当库存偏低、成品油价格较高、能源 CPI 仍高时，油价会成为利率预期和风险偏好的重要输入；但它不是唯一输入。
- 后续验证指标：EIA 周报库存、炼厂开工率、Brent/WTI、汽油和柴油价格、BLS CPI、FOMC、H.15、H.10、OPEC+ 会议。

## 一页原油传导检查表

```text
数据日期：

原油价格：
- WTI：
- Brent：
- Brent-WTI spread：

库存：
- 美国商业原油库存：
- 汽油库存：
- 馏分油库存：
- 是否低于五年均值：

炼厂：
- 炼厂开工率：
- 汽油产量：
- 馏分油产量：

宏观传导：
- 能源 CPI：
- 核心 CPI：
- FOMC target range：
- 10Y nominal：
- 10Y TIPS：
- Broad dollar index：

判断边界：
- 已确认事实：
- 我的推理：
- 不能确定：
- 下次要复核的数据：
```

## 个人情境连接

- 对关注清单的启发：看到油价变化时，不只写“原油涨跌”，还要同时记录库存、炼厂、汽油、柴油、美元和利率。
- 对持仓或基金选择的启发：能源 ETF、航空股、运输股和宽基指数受到油价影响的方向不同，不能把油价当成单一买卖信号。
- 对工作、收入、消费或风险管理的启发：汽油、机票、物流和取暖成本会改变家庭预算和企业利润率，最后可能影响工资、消费和就业。

## 结论边界

- 可以确定：截至本课数据口径，EIA 显示美国商业原油库存低于五年均值；BLS 显示能源同比仍明显高于总 CPI；Fed 仍把通胀稳定作为核心政策目标。
- 不能确定：本课不能预测油价、能源股、美元、利率或宽基指数的未来走势。
- 需要继续观察：下一期 EIA 周报、CPI、OPEC+ 会议、FOMC、美元指数、实际利率和地缘运输风险。
- 不构成投资建议的原因：本课只解释原油到通胀、利率和资产价格的教学传导，不建议买入、卖出或配置任何资产。

## 练习题

1. 为什么 WTI 和 Brent 都是油价，但不能机械看成同一个价格？
2. 用 3.171 美元/加仑和 42 加仑/桶，把汽油价格折成每桶口径。
3. 为什么商业原油库存低于五年均值会放大供给扰动？
4. 能源 CPI 同比高，为什么不等于核心 CPI 一定同步上升？
5. 画出“油价 -> CPI -> Fed -> 美元 -> 股票行业分化”的最小传导链。

## 学习交接

- 本课已经完成：把原油从单一商品价格推进到能源通胀、实际收入、Fed 反应、美元和跨资产风险偏好。
- 本课最重要的一句话：油价不是只影响油企利润，它会通过成品油、通胀、利率和美元进入整个资产定价环境。
- 需要复习的关键词：Crude Oil、WTI、Brent、Inventory、Refinery Utilization、Energy Inflation、Real Income、Policy Reaction Function、Dollar Pricing、Pass-through。
- 还不稳定、下次要回看的地方：库存为什么不是“越少越涨”的简单公式，期货曲线和炼化利润如何揭示真实紧张点。
- 适合下次打开仓库先读的文件：`lessons/2026-07-22-lesson-60-crude-oil-energy-inflation-dollar-rates.md`

## 下节课安排

- 建议主题：第六十一课：库存、期货曲线、炼化利润与风险溢价入门。
- 学习目标：理解 stock、working storage、tank bottoms、Cushing、futures curve、contango、backwardation、crack spread、refining margin 和 geopolitical risk premium。
- 建议案例：使用 EIA 2026-07-16 关于 tank bottoms 的 Today in Energy、EIA 2026-07-15 关于 Middle East disruptions 的 Today in Energy、EIA WPSR 和 IEA July 2026 Oil Market Report，解释为什么原油市场可能同时出现“原油价格回落、成品油利润高、库存仍紧”的组合。
- 必须解释的关键词：Working Storage、Tank Bottoms、Cushing、Futures Curve、Contango、Backwardation、Crack Spread、Refining Margin、Risk Premium、Product Market Tightness。
- 下节课开始前需要联网核验的数据：EIA WPSR、Cushing stocks、Brent/WTI spot prices、EIA/IEA/OPEC 最新市场报告、OPEC+ 会议安排和成品油价格。

## 来源

- EIA, Weekly Petroleum Status Report: https://www.eia.gov/petroleum/supply/weekly/
- EIA, Spot Prices for Crude Oil and Petroleum Products: https://www.eia.gov/dnav/pet/pet_pri_spt_s1_d.htm
- EIA, What Drives Crude Oil Prices: https://www.eia.gov/finance/markets/crudeoil/
- BLS, Consumer Price Index: https://www.bls.gov/cpi/
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, H.10 Foreign Exchange Rates: https://www.federalreserve.gov/releases/H10/current/
- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- OPEC, OPEC+ production adjustment, 2026-07-05: https://www.opec.org/pr-detail/1835609-5-july-2026.html
