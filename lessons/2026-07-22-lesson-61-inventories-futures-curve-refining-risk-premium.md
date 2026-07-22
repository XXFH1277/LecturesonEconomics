# 第六十一课：库存、期货曲线、炼化利润与风险溢价入门

## 基本信息

- 日期：2026-07-22
- 数据截至：2026-07-22 20:05（Asia/Shanghai）。EIA Weekly Petroleum Status Report 最新可用版本为 2026-07-15 发布、截至 2026-07-10；EIA Today in Energy 采用 2026-07-15 和 2026-07-16 两篇官方分析；EIA 现货价格采用 2026-07-15 发布、截至 2026-07-13 的数据；IEA Oil Market Report 采用 2026-07-10 发布的 July 2026 报告；OPEC+ 采用 2026-07-05 新闻稿。
- 主题：为什么库存、期货曲线、炼化利润和地缘风险会让油价信号变复杂。
- 学习目标：理解 working storage、tank bottoms、Cushing、futures curve、contango、backwardation、crack spread、refining margin、risk premium 和 product market tightness。
- 相关资产：WTI、Brent、汽油、柴油、航煤、炼厂、能源 ETF、航空运输行业、商品期货。
- 核心来源：
  - EIA, What are tank bottoms?, 2026-07-16: https://www.eia.gov/todayinenergy/detail.php?id=67866
  - EIA, Petroleum markets responded to disruptions in the Middle East in the second quarter, 2026-07-15: https://www.eia.gov/todayinenergy/detail.php?id=67865
  - EIA, Weekly Petroleum Status Report, release date 2026-07-15: https://www.eia.gov/petroleum/supply/weekly/
  - EIA, Spot Prices for Crude Oil and Petroleum Products, release date 2026-07-15: https://www.eia.gov/dnav/pet/pet_pri_spt_s1_d.htm
  - EIA, What Drives Crude Oil Prices: https://www.eia.gov/finance/markets/crudeoil/
  - IEA, Oil Market Report - July 2026, 2026-07-10: https://www.iea.org/reports/oil-market-report-july-2026
  - OPEC, OPEC+ countries production adjustment press release, 2026-07-05: https://www.opec.org/pr-detail/1835609-5-july-2026.html

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课把原油和通胀、利率、美元连起来。今天进一步问：

> 为什么有时原油价格下跌，但市场仍说供应链紧张？为什么炼厂利润可能和原油价格方向不一样？

因为“原油市场”不是一个单点价格，而是四层结构：

```text
库存是否够用
期货曲线如何定价未来
原油能不能变成需要的汽油/柴油/航煤
地缘和运输风险是否改变可达供应
```

### 参考的教材式概念顺序

1. Stock：库存，一个时间点上已经存着的数量。
2. Flow：流量，一段时间内生产、进口、加工、出口或消费的速度。
3. Working Storage：可工作库存，储罐在安全和技术上可用的库存空间。
4. Tank Bottoms：罐底油，维持储罐和管线可运行所需的最低体积。
5. Cushing：美国俄克拉荷马州 Cushing，WTI 重要交割和库存中心。
6. Futures Curve：期货曲线，不同交割月份价格组成的曲线。
7. Contango：远月高于近月，常见于当前供应相对宽松或持有成本较高时。
8. Backwardation：近月高于远月，常见于当前现货偏紧时。
9. Crack Spread：裂解价差，成品油价格减原油价格的炼厂利润代理。
10. Refining Margin：炼化利润，炼厂把原油加工成成品油后的经济空间。
11. Risk Premium：风险溢价，市场为不确定供应、运输或战争风险支付的额外价格。
12. Product Market Tightness：成品油市场紧张，汽油、柴油、航煤比原油更难获得。

### 核心概念

原油读表不能只看 WTI 或 Brent 一个价格。更稳的入门顺序是：

```text
先看库存：现货缓冲垫厚不厚
再看期货曲线：市场认为当前紧还是未来紧
再看裂解价差：原油能否顺利变成需要的成品油
最后看风险溢价：运输、战争、制裁和政策是否改变可达供应
```

如果只看原油价格，容易漏掉成品油约束。比如原油价格回落，但柴油和航煤供应紧张，炼厂利润仍可能很高，航空、物流和制造成本仍可能承压。

### 用自己的话解释

库存像水箱，流量像水龙头和下水口。水箱看起来还有水，不代表每一滴都能用。储罐需要最低运行体积，管道需要压力，库存地点也要能运到需求地点。

期货曲线像市场对“今天的紧张”和“未来的紧张”的价格表。近月特别贵，说明今天附近的货更紧；远月更贵，可能说明储存、融资、保险和未来不确定性更重要。

裂解价差像炼厂的粗略温度计。原油便宜不等于汽油、柴油便宜，因为炼厂可能受产能、检修、出口需求、产品结构和地区物流约束。

### 常见误区

- 误区一：库存不为零就不紧张。工作库存和罐底油决定了实际可用性。
- 误区二：油价下跌说明供应一定宽松。可能只是原油端缓解，成品油端仍紧。
- 误区三：contango 一定利空、backwardation 一定利多。它们只是曲线形态，要结合库存、融资成本和季节性。
- 误区四：裂解价差等于炼厂净利润。真实利润还要扣运营成本、运输、税费、对冲和原油品质差异。
- 误区五：地缘风险只影响当天油价。风险可能通过库存、保险、航线、交货时间和政策反应持续传导。

## 第二大板块：实时背景与市场传导

### 发生了什么

EIA 2026-07-16 Today in Energy 解释了 tank bottoms。EIA 表示，截至 2026-07-10 前，从 week ending 2026-06-19 开始，Cushing 原油库存一度低于 20 million barrels；当库存接近储罐和管线运行所需最低体积时，市场可用库存会比账面库存更紧。EIA 还指出，Brent-WTI 五日滚动价差曾在 2026-06-18 至 2026-06-24、以及 2026-07-02 至 2026-07-08 转为负值，意味着 WTI-Cushing 一度高于 Brent，反映 Cushing 和美国中部市场的极端紧张。

EIA 2026-07-15 Today in Energy 复盘 2026 年第二季度中东扰动。EIA 指出，Brent front-month futures 在 2Q26 高点达到 118 美元/桶（2026-04-29），低点降至 72 美元/桶（2026-06-26）；4-5 月 Brent 日均波动约 4 美元/桶，而 2025 年同期约 1 美元/桶。EIA 同时指出，中东扰动使国际买家寻找替代成品油来源，推高美国炼厂利润、产量和出口；2Q26 汽油 crack spread 较上年同期高 60%，馏分油和航煤 crack spread 超过上年同期两倍。

IEA 2026-07-10 Oil Market Report 则从全球角度给出另一层背景：6 月全球油品供应反弹 4.1 million b/d 至 98.8 million b/d，但仍低于战前水平；报告还指出成品油裂解价差和炼化利润在 7 月初升至四年高位，原因是原油供应增加压低原油价格，而成品油市场仍偏紧。

EIA 最新现货价格页显示，2026-07-13 WTI-Cushing 为 79.20 美元/桶，Brent-Europe 为 81.62 美元/桶，Brent 比 WTI 高 2.42 美元/桶。这个最新点说明此前负价差是压力阶段的市场现象，不应机械外推成永久关系。

### 为什么重要

这组事实说明原油市场可以同时出现三件看似矛盾的事：

```text
原油供应边际改善
-> 原油价格从高位回落

成品油供应仍紧
-> 汽油、柴油、航煤 crack spread 维持高位

关键库存地点偏紧
-> WTI-Cushing 和 Brent 的相对价格出现异常
```

所以，读油价时要分清“原油端”和“成品油端”。原油价格是输入，汽油、柴油、航煤才更接近居民和企业实际面对的成本。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| Cushing 库存压力 | 2026-06-19 至 2026-07-10 前一度低于 20 million barrels | EIA Today in Energy, 2026-07-16 | 工作库存和罐底油案例 |
| Brent-WTI 五日价差 | 2026-06-18 至 06-24、07-02 至 07-08 曾为负 | EIA Today in Energy, 2026-07-16 | 地区紧张和价差案例 |
| Brent 2Q26 高点 | 118 美元/桶 | EIA Today in Energy, 2026-07-15 | 地缘扰动价格案例 |
| Brent 2Q26 低点 | 72 美元/桶 | EIA Today in Energy, 2026-07-15 | 风险溢价回落案例 |
| 4-5 月 Brent 日均波动 | 约 4 美元/桶 | EIA Today in Energy, 2026-07-15 | 波动率案例 |
| 汽油 crack spread | 2Q26 均值同比高 60% | EIA Today in Energy, 2026-07-15 | 炼化利润案例 |
| 馏分油和航煤 crack spread | 超过上年同期两倍 | EIA Today in Energy, 2026-07-15 | 成品油紧张 |
| 全球供应反弹 | 6 月 +4.1 million b/d 至 98.8 million b/d | IEA OMR, 2026-07-10 | 全球供给恢复 |
| 2026-07-13 WTI | 79.20 美元/桶 | EIA Spot Prices | 最新价格锚 |
| 2026-07-13 Brent | 81.62 美元/桶 | EIA Spot Prices | 最新价格锚 |
| OPEC+ 产量调整 | 188 thousand b/d 于 2026 年 8 月实施 | OPEC, 2026-07-05 | 供给规则背景 |

### 这些现实事件如何连接理论

第一条链：库存和可用性。

```text
Cushing 库存接近 tank bottoms
-> 账面库存还存在，但可动用库存变少
-> WTI-Cushing 现货可能变得特别紧
-> Brent-WTI spread 可能异常收窄甚至转负
```

第二条链：原油和成品油分叉。

```text
原油流量恢复
-> 原油价格回落
但炼厂、航线、产品出口和需求仍受约束
-> 汽油、柴油、航煤 crack spread 仍高
-> 运输、航空和消费成本压力未必同步消失
```

第三条链：风险溢价。

```text
地缘冲突或运输通道受扰
-> 市场为供应中断风险付更高价格
-> 谈判或航运恢复
-> 风险溢价回落
-> 但如果冲突反复，风险溢价又会回来
```

### 至少一个真实市场机制案例

案例：Cushing tank bottoms 如何改变 WTI-Brent 价差。

正常直觉里，Brent 是国际海运基准，WTI 是美国内陆基准，Brent 常常比 WTI 更贵。但 EIA 2026-07-16 文章显示，当 Cushing 库存紧到接近最低可运行库存时，WTI-Cushing 可以相对变贵，Brent-WTI 五日滚动价差一度转负。

这不是说 WTI 永远会比 Brent 贵，而是说明“交割地点”和“可用库存”会改变价格关系。期货合约不是抽象数字，它背后有仓储、管道、交割、品质和时间。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：EIA 能源统计、WTI 交割机制、Cushing 仓储约束、OPEC+ 供给协调、中东运输通道、IEA 全球能源安全分析。
- 已确认事实：EIA 官方文章说明 Cushing 库存在近期接近 tank bottoms 并影响 Brent-WTI spread；EIA 复盘 2Q26 中东扰动对油价、炼厂利润和出口的影响；IEA 指出原油供应改善但成品油市场仍紧；OPEC+ 宣布 8 月产量调整。
- 市场可能如何传导：库存低会放大现货价格反应；期货曲线反映当前与未来紧张程度；裂解价差高会改善炼厂收入但提高下游成本；风险溢价会影响通胀预期和央行政策压力。
- 仍需核验或观察：Cushing 库存是否回升、Brent-WTI spread 是否稳定、近月/远月期货曲线、汽油/柴油/航煤 crack spreads、OPEC+ 2026-08-02 会议、中东运输通道和 EIA/IEA 后续报告。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Stock | 库存 | 某个时间点存着的量 | 判断缓冲垫 |
| Flow | 流量 | 一段时间内进出速度 | 判断供需变化 |
| Working Storage | 工作库存 | 实际可安全使用的储存能力 | 账面库存不等于可用库存 |
| Tank Bottoms | 罐底油 | 维持储罐和管线运行的最低油量 | 解释库存未归零也会紧 |
| Cushing | 库欣 | WTI 重要交割和库存地点 | 影响 WTI 价格 |
| Futures Curve | 期货曲线 | 不同月份期货价格连成的线 | 看当前紧还是未来紧 |
| Contango | 正向市场 | 远月价格高于近月 | 常与储存和持有成本有关 |
| Backwardation | 逆向市场 | 近月价格高于远月 | 常与现货紧张有关 |
| Crack Spread | 裂解价差 | 成品油价格减原油价格的毛利代理 | 观察炼厂经济性 |
| Refining Margin | 炼化利润 | 炼厂加工原油后的利润空间 | 解释能源行业分化 |
| Risk Premium | 风险溢价 | 为不确定性付的额外价格 | 地缘风险进入油价 |
| Product Market Tightness | 成品油紧张 | 汽油、柴油、航煤供应偏紧 | 成本传导更接近消费者 |

## 回顾提示

- 学到本课前建议回顾：第 6 课黄金和原油入门、第 55 课 T-Bill 阶梯里的期限概念、第 57 课收益率曲线、第 60 课原油与能源通胀。
- 本课哪些内容会在后续课程继续使用：商品期货、衍生品、套期保值、能源股、航空运输、通胀预期和风险溢价。
- 如果看不懂本课，可以先回到：第 1 课供需和价格，重新理解“价格是信号，不是事实本身”。

## 案例拆解

- 案例对象：EIA 2026-07-16 Cushing tank bottoms 案例、EIA 2026-07-15 Middle East disruptions 案例、IEA July 2026 Oil Market Report。
- 已确认事实：
  - Cushing 原油库存近期一度低于 20 million barrels。
  - Brent-WTI 五日滚动价差在两个时间段转负。
  - Brent front-month futures 2Q26 高点为 118 美元/桶，低点为 72 美元/桶。
  - 2Q26 汽油 crack spread 同比高 60%，馏分油和航煤 crack spread 超过上年同期两倍。
  - IEA 表示全球油品供应 6 月反弹，但成品油裂解价差和炼化利润在 7 月初升至四年高位。
- 来源日期和链接：见本课“来源”。
- 分析推理：油价信号必须拆成库存地点、时间结构、成品油约束和风险溢价；单看 Brent 或 WTI 容易误判真实紧张点。
- 后续验证指标：Cushing stocks、commercial crude stocks、Brent-WTI spread、futures curve、gasoline/diesel/jet crack spreads、refinery utilization、OPEC+ output decisions。

## 一页原油市场结构检查表

```text
数据日期：

现货：
- WTI：
- Brent：
- Brent-WTI spread：

库存：
- Commercial crude：
- Cushing：
- 是否接近 tank bottoms：
- Gasoline：
- Distillate：

期货曲线：
- 近月：
- 次月：
- 远月：
- Contango / backwardation：

炼化：
- Gasoline crack：
- Diesel crack：
- Jet fuel crack：
- Refinery utilization：

风险：
- OPEC+ 会议：
- 地缘运输通道：
- 制裁或政策变化：
- 后续确认指标：
```

## 个人情境连接

- 对关注清单的启发：记录能源变量时至少分四列：原油价格、库存位置、成品油利润、地缘风险。
- 对持仓或基金选择的启发：能源生产商、炼厂、航空公司、运输公司和宽基基金对油价的暴露不同，不能只用“油价涨跌”解释表现。
- 对工作、收入、消费或风险管理的启发：成品油紧张比原油价格本身更直接影响通勤、物流、机票和企业成本。

## 结论边界

- 可以确定：EIA 已确认近期 Cushing 库存紧张曾影响 Brent-WTI spread；EIA 和 IEA 都指出 2Q26/7 月初成品油和炼化利润是重要紧张点；OPEC+ 仍在通过会议调整供给路径。
- 不能确定：本课不能预测 Brent、WTI、期货曲线、能源股或航空运输股未来走势。
- 需要继续观察：Cushing 库存是否恢复、EIA 下一周报、OPEC+ 下一次会议、成品油 crack spreads、IEA/OPEC 后续月报和中东运输风险。
- 不构成投资建议的原因：本课只解释原油市场结构和风险传导，不建议交易期货、买卖股票或配置基金。

## 练习题

1. 为什么库存不为零，也可能接近不可用状态？
2. contango 和 backwardation 分别说明市场在担心什么？
3. 为什么原油价格回落时，汽油或柴油利润仍可能很高？
4. 用 WTI 79.20 和 Brent 81.62 计算 2026-07-13 的 Brent-WTI spread。
5. 选一个能源新闻标题，按“库存、曲线、裂解价差、风险溢价”四列拆解它。

## 学习交接

- 本课已经完成：把原油价格进一步拆成库存可用性、期货曲线、炼化利润和风险溢价四个观察层。
- 本课最重要的一句话：油价不是一个点，而是一套地点、时间、产品和风险共同决定的价格结构。
- 需要复习的关键词：Working Storage、Tank Bottoms、Cushing、Futures Curve、Contango、Backwardation、Crack Spread、Refining Margin、Risk Premium、Product Market Tightness。
- 还不稳定、下次要回看的地方：期货和套期保值的合约逻辑、保证金、每日盯市和企业如何用衍生品管理油价风险。
- 适合下次打开仓库先读的文件：`lessons/2026-07-22-lesson-61-inventories-futures-curve-refining-risk-premium.md`

## 下节课安排

- 建议主题：第六十二课：原油期货、套期保值、保证金与企业成本管理入门。
- 学习目标：理解 futures contract、notional value、margin、mark-to-market、hedging、speculation、basis risk、roll yield 和 hedge accounting 的最小框架。
- 建议案例：使用 CME WTI 合约说明、EIA spot price、航空公司或炼厂公开风险因素披露，解释企业为什么用期货或互换锁定燃料成本，但套保不能消灭全部风险。
- 必须解释的关键词：Futures Contract、Notional Value、Initial Margin、Maintenance Margin、Mark-to-market、Hedging、Speculation、Basis Risk、Roll Yield、Hedge Accounting。
- 下节课开始前需要联网核验的数据：CME WTI contract specs、EIA WTI/Brent spot prices、最新 EIA WPSR、公开公司 10-K/10-Q 风险因素和衍生品披露。

## 来源

- EIA, What are tank bottoms?, 2026-07-16: https://www.eia.gov/todayinenergy/detail.php?id=67866
- EIA, Petroleum markets responded to disruptions in the Middle East in the second quarter, 2026-07-15: https://www.eia.gov/todayinenergy/detail.php?id=67865
- EIA, Weekly Petroleum Status Report: https://www.eia.gov/petroleum/supply/weekly/
- EIA, Spot Prices for Crude Oil and Petroleum Products: https://www.eia.gov/dnav/pet/pet_pri_spt_s1_d.htm
- EIA, What Drives Crude Oil Prices: https://www.eia.gov/finance/markets/crudeoil/
- IEA, Oil Market Report - July 2026: https://www.iea.org/reports/oil-market-report-july-2026
- OPEC, OPEC+ production adjustment, 2026-07-05: https://www.opec.org/pr-detail/1835609-5-july-2026.html
