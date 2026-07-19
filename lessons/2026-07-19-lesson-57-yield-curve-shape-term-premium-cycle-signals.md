# 第五十七课：收益率曲线形状、期限溢价与周期信号入门

## 基本信息

- 日期：2026-07-19
- 数据截至：2026-07-19 21:20（Asia/Shanghai）。收益率数据采用 Federal Reserve H.15 2026-07-17 发布、截至 2026-07-16 的数据；收益率曲线定义和模型边界采用 Federal Reserve Yield Curve Models and Data、U.S. Treasury Yield Curve Methodology、U.S. Treasury Interest Rates FAQ；政策背景采用 Federal Reserve 2026-06-17 FOMC statement。
- 主题：为什么收益率曲线有形状；如何读短端、中端、长端、期限利差、期限溢价、实际利率和通胀补偿。
- 学习目标：理解 Yield Curve、Term Structure、Maturity、Term Spread、Normal Curve、Flat Curve、Inverted Curve、Steepening、Flattening、Term Premium、Real Yield、Inflation Compensation 和 Duration。
- 相关资产：美国国债、T-Bill、Treasury note、Treasury bond、TIPS、债券基金、黄金、股票估值、现金管理工具。
- 核心来源：
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-17: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, Yield Curve Models and Data: https://www.federalreserve.gov/data/yield-curve-models.htm
  - U.S. Treasury, Treasury Yield Curve Methodology: https://home.treasury.gov/policy-issues/financing-the-government/interest-rate-statistics/treasury-yield-curve-methodology
  - U.S. Treasury, Interest Rates FAQ: https://home.treasury.gov/policy-issues/financing-the-government/interest-rate-statistics/interest-rates-frequently-asked-questions
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲了短端利率如何从 FOMC 传到 SOFR、T-Bill 和现金产品。今天把视角拉长：

> 为什么 1 个月利率、2 年利率、10 年利率和 30 年利率不一样？

因为它们不是同一笔钱的同一期限。借钱 1 个月和借钱 30 年，面对的通胀、经济、政策、财政、供需和价格波动风险都不一样。收益率曲线就是把不同期限的利率排成一条线。

### 参考的教材式概念顺序

1. Maturity：到期期限，债券本金什么时候归还。
2. Yield：收益率，用价格和未来现金流反推出来的回报率。
3. Yield Curve：收益率曲线，把不同期限的收益率连起来。
4. Term Structure：利率期限结构，不同期限利率之间的关系。
5. Short End：短端，通常指几天到 1 年附近的利率。
6. Belly：中段，通常指 2 年到 7 年附近的利率。
7. Long End：长端，通常指 10 年、20 年、30 年附近的利率。
8. Term Spread：期限利差，长端利率减短端利率，例如 10Y - 2Y。
9. Steepening：变陡，长短利差扩大。
10. Flattening：变平，长短利差缩小。
11. Inversion：倒挂，短端利率高于长端利率。
12. Expectations：预期，市场对未来短端利率路径的看法。
13. Term Premium：期限溢价，投资者为承担长期利率风险要求的补偿。
14. Real Yield：实际利率，扣除通胀补偿后的利率观察口径。
15. Inflation Compensation：通胀补偿，名义收益率与通胀保值债券收益率之间的差异所反映的通胀相关补偿。

### 核心概念

收益率曲线可以先用一个最小公式理解：

```text
长期名义收益率
= 未来短期利率预期
+ 期限溢价
+ 通胀补偿和其他市场因素
```

这不是精确分解公式，而是入门框架。它提醒我们：10 年期收益率不是“今天的政策利率乘以 10 年”，而是市场把未来很多年的政策、通胀、增长、财政供给、风险偏好和持有长期债券的补偿一起定价。

### 用自己的话解释

收益率曲线像一张借钱价目表：

```text
借 1 个月：主要看今天和很近的政策利率
借 2 年：开始看未来几次 FOMC 和经济周期
借 10 年：更看长期增长、通胀、财政供给和期限溢价
借 30 年：还要加上更长时间里的不确定性和久期风险
```

曲线不是算命工具。它是市场当天给不同期限现金流标出的价格。

### 常见误区

- 误区一：收益率曲线可以直接预测未来。Treasury FAQ 明确提醒，CMT rates 只表示过去和现在的利率，预测未来利率有风险。
- 误区二：10 年期收益率就是未来 10 年平均政策利率。它还包含期限溢价、供需、通胀补偿和流动性因素。
- 误区三：收益率曲线倒挂一定马上衰退。倒挂是风险信号，不是日期和幅度的保证。
- 误区四：长端收益率上升一定是经济更好。也可能是通胀补偿上升、财政供给压力、期限溢价上升或流动性变化。
- 误区五：实际利率只影响债券。实际利率会影响黄金、股票估值、房地产折现率和汇率吸引力。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve H.15 2026-07-17 release 显示，截至 2026-07-16，美国国债 nominal constant maturity yields 为：

| 期限 | 收益率 |
| --- | ---: |
| 1-month | 3.76% |
| 3-month | 3.84% |
| 6-month | 3.94% |
| 1-year | 3.99% |
| 2-year | 4.16% |
| 3-year | 4.20% |
| 5-year | 4.28% |
| 7-year | 4.41% |
| 10-year | 4.57% |
| 20-year | 5.09% |
| 30-year | 5.09% |

同一 H.15 release 显示，Treasury inflation-indexed constant maturity yields 为：

| 期限 | TIPS 实际收益率 |
| --- | ---: |
| 5-year | 2.04% |
| 7-year | 2.18% |
| 10-year | 2.35% |
| 20-year | 2.71% |
| 30-year | 2.91% |

几个入门利差可以这样算：

```text
10Y - 2Y = 4.57% - 4.16% = +0.41 个百分点
10Y - 3M = 4.57% - 3.84% = +0.73 个百分点
30Y - 1M = 5.09% - 3.76% = +1.33 个百分点
10Y 名义 - 10Y TIPS = 4.57% - 2.35% = 约 2.22 个百分点
```

最后一个只是教学近似，用来理解“名义利率和实际利率之间有通胀相关补偿”。严谨研究应使用同口径的 breakeven inflation / inflation compensation 数据和模型说明。

Federal Reserve 2026-06-17 FOMC statement 同时给了政策背景：FOMC 维持 target range 在 3.50%-3.75%，并表示通胀相对 2% 目标仍然偏高，部分反映能源等供给冲击。这意味着曲线短端仍然被较高政策利率锚住，而中长端还会定价未来通胀、增长、财政供给和期限风险。

### 为什么重要

这条曲线当前不是“短端极高、长端极低”的倒挂形状，而是从 1-month 的 3.76% 到 30-year 的 5.09% 整体向上。入门读法是：

```text
短端：
接近 Fed 当前政策和隔夜资金市场

中段：
反映未来几年的政策路径、增长和通胀预期

长端：
更受长期通胀补偿、期限溢价、财政供给和久期风险影响
```

对第 54-56 课的现金管理来说，短端更重要。对第 53 课的债券基金久期来说，2 年、5 年、10 年和 30 年利率更重要。对股票估值、黄金和房地产来说，实际利率和长端折现率更重要。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| FOMC target range | 3.50%-3.75% | Federal Reserve, 2026-06-17 | 短端政策锚 |
| 1-month CMT | 3.76% | H.15, 2026-07-16 | 曲线短端 |
| 3-month CMT | 3.84% | H.15, 2026-07-16 | 曲线短端 |
| 2-year CMT | 4.16% | H.15, 2026-07-16 | 政策预期敏感区域 |
| 5-year CMT | 4.28% | H.15, 2026-07-16 | 中段利率 |
| 10-year CMT | 4.57% | H.15, 2026-07-16 | 长端核心锚 |
| 30-year CMT | 5.09% | H.15, 2026-07-16 | 超长端 |
| 10-year TIPS yield | 2.35% | H.15, 2026-07-16 | 实际利率观察 |
| Treasury curve methodology | 官方 par yield curve 使用 bid-side market price quotations 和 monotone convex 方法 | U.S. Treasury, revised 2025-02-18 | 曲线口径边界 |
| CMT FAQ | CMT 是固定期限点，不一定等于某一只真实债券收益率 | U.S. Treasury FAQ | 防止误读 |
| Fed yield curve models | 收益率曲线常被市场和政策制定者用于观察政策路径与宏观前景线索，但模型是研究产品，不是官方统计发布 | Federal Reserve | 模型边界 |

### 这些现实事件如何连接理论

用 2026-07-16 的曲线看三个层次：

```text
第一层：短端由政策利率锚住
1-month 3.76%、3-month 3.84%，与 FOMC 目标区间 3.50%-3.75% 相邻，但略有差异。

第二层：中段开始加入未来路径
2-year 4.16%、5-year 4.28%，反映市场对未来政策、通胀和增长的综合定价。

第三层：长端加入期限风险
10-year 4.57%、30-year 5.09%，不仅看 Fed 近期动作，还看长期通胀、财政供给、投资者久期偏好和期限溢价。
```

如果长端上升而短端不动，曲线会 steepen。可能含义包括：长期通胀补偿上升、财政债券供给压力、期限溢价上升，或市场要求更高长期补偿。

如果短端上升而长端不动，曲线会 flatten，甚至 inversion。可能含义包括：当前政策更紧，但市场认为未来增长或通胀会下降，长期利率不愿跟着上。

### 至少一个真实市场机制案例

2026-07-16 的 10Y-2Y spread 为 +0.41 个百分点。这是一个简单但有用的机制案例：

```text
2-year yield = 4.16%
10-year yield = 4.57%
10Y - 2Y = +0.41%
```

这个正利差告诉我们，当天 10 年期收益率高于 2 年期收益率。它不能单独说明经济一定强，也不能说明债券一定该买或该卖。它只能说明当天不同期限国债的市场定价结构：持有更长期限现金流，需要更高名义收益率补偿。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 货币政策、Treasury 国债发行与曲线方法、财政融资需求、通胀目标、TIPS 市场、全球美元资产需求。
- 已确认事实：H.15 提供截至 2026-07-16 的 nominal 和 inflation-indexed constant maturity yields；Treasury 说明 CMT 读自 daily par yield curve 的固定期限点；Fed 说明收益率曲线被市场和政策制定者关注，但模型输出不是官方统计发布。
- 市场可能如何传导：短端政策利率影响现金工具和浮动利率；中长端影响债券基金价格、股票估值折现率、房贷利率、美元吸引力和黄金机会成本。
- 仍需核验或观察：未来 FOMC 决议、通胀数据、财政部发行计划、10Y-2Y 和 10Y-3M 利差、实际利率、TIPS breakeven、债券市场流动性。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Yield Curve | 收益率曲线 | 不同期限债券收益率连成的线 | 是利率市场的地图 |
| Term Structure | 利率期限结构 | 不同期限利率之间的关系 | 解释为什么长短利率不同 |
| Maturity | 到期期限 | 本金归还的时间 | 决定现金流暴露多久 |
| Constant Maturity | 固定期限点 | 曲线上固定期限的理论收益率 | 不一定对应某一只真实债券 |
| Term Spread | 期限利差 | 长端收益率减短端收益率 | 观察曲线形状 |
| Normal Curve | 正常曲线 | 长端高于短端 | 常见于长期风险补偿为正时 |
| Inverted Curve | 倒挂曲线 | 短端高于长端 | 常被当作周期风险信号 |
| Steepening | 曲线变陡 | 长短利差扩大 | 可能来自长端上行或短端下行 |
| Flattening | 曲线变平 | 长短利差缩小 | 可能来自短端上行或长端下行 |
| Term Premium | 期限溢价 | 持有长期债券承担利率风险要求的补偿 | 影响长端收益率 |
| Real Yield | 实际收益率 | 剔除通胀补偿后的收益率观察 | 影响黄金和估值折现 |
| TIPS | 通胀保值国债 | 本金随通胀调整的国债 | 观察实际利率 |
| Inflation Compensation | 通胀补偿 | 名义和实际收益率差异中的通胀相关部分 | 帮助拆解长端利率 |
| Duration | 久期 | 债券价格对利率变化的敏感度 | 长端利率变动会放大价格波动 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和利率、第 15 课估值倍数与利率、第 30-32 课 DCF 与 WACC、第 53 课债券基金、第 56 课短端利率传导。
- 本课哪些内容会在后续课程继续使用：实际利率与黄金、长端利率与股票估值、债券基金久期、房贷利率、美元和汇率。
- 如果看不懂本课，可以先回到：第 5 课，重新理解“债券价格和收益率反向变化”。

## 案例拆解

- 案例对象：2026-07-16 美国国债收益率曲线。
- 已确认事实：
  - 1-month CMT 为 3.76%，2-year CMT 为 4.16%，10-year CMT 为 4.57%，30-year CMT 为 5.09%。
  - 10Y-2Y spread 为 +0.41 个百分点。
  - 10Y-3M spread 为 +0.73 个百分点。
  - 10-year TIPS yield 为 2.35%。
  - 10Y nominal - 10Y TIPS 的教学近似差值约为 2.22 个百分点。
- 来源日期和链接：见本课“来源”。
- 分析推理：当前曲线整体向上，说明长端名义收益率高于短端；但这不能自动解释为“经济一定更强”，还必须拆分政策预期、通胀补偿、期限溢价和财政供需。
- 后续验证指标：10Y-2Y、10Y-3M、30Y-2Y、5Y/10Y/30Y TIPS yields、FOMC statement、CPI/PCE、财政部季度再融资计划、债券基金久期和资金流。

## 一页收益率曲线检查表

```text
数据日期：

短端：
- FOMC target range：
- 1-month：
- 3-month：
- 6-month：

中段：
- 2-year：
- 5-year：
- 7-year：

长端：
- 10-year：
- 20-year：
- 30-year：

关键利差：
- 10Y - 2Y：
- 10Y - 3M：
- 30Y - 1M：

实际利率和通胀补偿：
- 5Y TIPS：
- 10Y TIPS：
- 30Y TIPS：
- 10Y nominal - 10Y TIPS：

解释：
- 已确认事实：
- 我的推理：
- 不能确定：
- 下次要复核的数据：
```

## 个人情境连接

- 对关注清单的启发：观察债券基金时要记录 duration 和曲线哪一段变化，而不是只写“利率涨/跌”。
- 对持仓或基金选择的启发：现金工具看短端，债券基金看所持债券期限分布，股票估值更容易受中长端折现率和风险偏好影响。
- 对工作、收入、消费或风险管理的启发：房贷、车贷、企业融资和就业周期都会受到曲线不同部分影响；个人决策不能只盯 Fed 一句话。

## 结论边界

- 可以确定：收益率曲线是不同期限利率的结构；截至 2026-07-16，H.15 显示美国国债曲线从短端到长端整体向上。
- 不能确定：本课不能预测未来曲线会变陡、变平还是倒挂；也不能用一条曲线直接判断经济衰退或资产涨跌。
- 需要继续观察：未来 FOMC、通胀、就业、财政发行、TIPS、期限利差、信用利差和债券市场流动性。
- 不构成投资建议的原因：本课只解释收益率曲线读法，不建议买入、卖出或配置任何债券、基金、股票、黄金或现金工具。

## 练习题

1. 什么是 10Y-2Y spread？用 2026-07-16 的数据手算一次。
2. 为什么 10 年期收益率不等于未来 10 年政策利率的简单平均？
3. 曲线变陡可能由哪些原因造成？至少写出 3 个。
4. 为什么 10Y nominal - 10Y TIPS 只能作为通胀补偿的入门近似，不能当成完整投资结论？
5. 任选一个债券基金，查它的 effective duration，并说明它更容易受曲线哪一段影响。

## 学习交接

- 本课已经完成：把收益率曲线从“长短利率不同”推进到曲线形状、期限利差、期限溢价、实际利率和通胀补偿。
- 本课最重要的一句话：收益率曲线是市场当天给不同期限现金流标出的价格，不是自动预测未来的水晶球。
- 需要复习的关键词：Yield Curve、Term Structure、Maturity、Term Spread、Steepening、Flattening、Inversion、Term Premium、Real Yield、Inflation Compensation、Duration。
- 还不稳定、下次要回看的地方：实际利率如何影响黄金，长端利率如何影响股票估值、债券基金和美元。
- 适合下次打开仓库先读的文件：`lessons/2026-07-19-lesson-57-yield-curve-shape-term-premium-cycle-signals.md`

## 下节课安排

- 建议主题：第五十八课：实际利率、通胀补偿、黄金与股票估值传导入门。
- 学习目标：理解 nominal yield、real yield、breakeven inflation、opportunity cost、discount rate、gold holding cost 和 equity valuation multiple 如何联动但不能机械推导。
- 建议案例：使用 Federal Reserve H.15 TIPS yields、Treasury nominal yields、World Gold Council 或 LBMA 黄金资料、以及一个宽基 ETF 或大型公司估值口径，解释实际利率变化为什么会影响黄金和股票估值叙事。
- 必须解释的关键词：Nominal Yield、Real Yield、TIPS、Breakeven Inflation、Opportunity Cost、Discount Rate、Equity Risk Premium、Gold ETF、Valuation Multiple。
- 下节课开始前需要联网核验的数据：H.15 nominal/TIPS yields、最新 FOMC statement、World Gold Council 或 LBMA 黄金数据、一个 ETF 或公司官方估值/持仓页面。

## 来源

- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, Yield Curve Models and Data: https://www.federalreserve.gov/data/yield-curve-models.htm
- U.S. Treasury, Treasury Yield Curve Methodology: https://home.treasury.gov/policy-issues/financing-the-government/interest-rate-statistics/treasury-yield-curve-methodology
- U.S. Treasury, Interest Rates FAQ: https://home.treasury.gov/policy-issues/financing-the-government/interest-rate-statistics/interest-rates-frequently-asked-questions
- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
