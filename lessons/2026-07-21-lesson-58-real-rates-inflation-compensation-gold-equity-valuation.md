# 第五十八课：实际利率、通胀补偿、黄金与股票估值传导入门

## 基本信息

- 日期：2026-07-21
- 数据截至：2026-07-21 21:50（Asia/Shanghai）。利率采用 Federal Reserve H.15 2026-07-20 release、截至 2026-07-17 的数据；政策背景采用 Federal Reserve 2026-06-17 FOMC statement；黄金需求采用 World Gold Council 2026-04-29 Q1 2026 Gold Demand Trends 与 2026-07-08 Gold ETF Flows: June 2026；股票估值案例采用 State Street SPY 页面截至 2026-07-20 的基金特征。
- 主题：为什么实际利率会影响黄金、股票估值和跨资产风险偏好。
- 学习目标：理解 nominal yield、real yield、TIPS、breakeven inflation、opportunity cost、discount rate、equity risk premium、gold ETF 和 valuation multiple 的最小传导链。
- 相关资产：美国国债、TIPS、黄金、黄金 ETF、S&P 500 ETF、成长股、现金工具。
- 核心来源：
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-20: https://www.federalreserve.gov/releases/h15/
  - Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - World Gold Council, Gold Demand Trends: Q1 2026, 2026-04-29: https://www.gold.org/goldhub/research/gold-demand-trends/gold-demand-trends-q1-2026
  - World Gold Council, Gold ETF Flows: June 2026, 2026-07-08: https://www.gold.org/goldhub/research/gold-etfs-holdings-and-flows/2026/07
  - World Gold Council, Gold spot prices data page, data as of 2026-07-20: https://www.gold.org/goldhub/data/gold-prices
  - State Street, SPDR S&P 500 ETF Trust (SPY), fund characteristics as of 2026-07-20: https://www.ssga.com/us/en/individual/etfs/state-street-spdr-sp-500-etf-trust-spy

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课说收益率曲线不是一个点，而是一条不同期限利率的线。今天继续问一个更贴近市场的问题：

> 为什么有人说“实际利率上升会压制黄金和股票估值”？

先不要急着背结论。黄金、股票和债券不是同一种资产。它们受同一个利率背景影响，但传导路径不同。

### 参考的教材式概念顺序

1. Nominal Yield：名义收益率，市场上看到的国债收益率。
2. Inflation：通胀，货币购买力下降。
3. TIPS：通胀保值国债，本金随通胀调整。
4. Real Yield：实际收益率，扣除通胀补偿后的收益率观察口径。
5. Breakeven Inflation：盈亏平衡通胀率，名义国债和 TIPS 收益率差值的入门近似。
6. Opportunity Cost：机会成本，选择持有 A 放弃 B 的代价。
7. Discount Rate：折现率，把未来现金流折回今天的利率。
8. Equity Risk Premium：股权风险溢价，持有股票相对安全资产要求的额外补偿。
9. Valuation Multiple：估值倍数，例如 P/E。
10. Gold Holding Cost：持有黄金的机会成本，黄金本身不支付利息或股息。

### 核心概念

可以先把传导链写成三行：

```text
名义利率 - 通胀补偿 ~= 实际利率

实际利率上升 -> 持有无息黄金的机会成本上升

折现率上升 -> 未来现金流现值下降 -> 股票估值倍数可能承压
```

这个框架只解释方向压力，不给价格预测。黄金还会受央行储备、避险需求、美元、ETF 资金流和珠宝需求影响；股票还会受盈利增长、利润率、行业结构、回购和风险偏好影响。

### 用自己的话解释

实际利率像一把尺子，衡量“持有安全利息资产、扣掉通胀以后还能得到多少”。当这把尺子变高时：

- 对黄金：黄金不发利息，投资者会更认真比较“拿黄金”与“拿有实际收益的国债”。
- 对股票：股票价值来自未来利润和现金流，折现率越高，未来的钱折回今天越少。
- 对现金和短债：实际收益更高时，等待和观望的成本可能下降。

但市场不会只看一把尺子。强盈利增长可能抵消折现率压力，严重地缘风险也可能让黄金在高实际利率下仍有需求。

### 常见误区

- 误区一：实际利率上升，黄金一定跌。现实中地缘风险、央行购金、美元走势和 ETF 资金流可能改变短期表现。
- 误区二：名义利率上升等于实际利率上升。如果通胀补偿升得更快，实际利率可能不升反降。
- 误区三：P/E 下降一定说明公司变差。也可能只是折现率、风险偏好或市场结构变化。
- 误区四：TIPS 收益率就是个人真实生活通胀。TIPS 是市场化证券口径，不等于每个人的消费篮子。
- 误区五：黄金 ETF 流入流出等于所有黄金需求。黄金还有央行、金条金币、珠宝、工业和场外交易需求。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve H.15 2026-07-20 release 显示，截至 2026-07-17，美国国债和 TIPS 的关键收益率为：

| 指标 | 2026-07-17 |
| --- | ---: |
| Effective Federal Funds Rate | 3.63% |
| 2-year nominal CMT | 4.18% |
| 5-year nominal CMT | 4.28% |
| 10-year nominal CMT | 4.55% |
| 30-year nominal CMT | 5.06% |
| 5-year TIPS yield | 2.01% |
| 10-year TIPS yield | 2.31% |
| 30-year TIPS yield | 2.87% |

用入门近似计算：

```text
10Y 通胀补偿近似 = 10Y nominal - 10Y TIPS
                 = 4.55% - 2.31%
                 = 约 2.24 个百分点
```

Federal Reserve 2026-06-17 FOMC statement 维持 federal funds target range 在 3.50%-3.75%，并说明通胀仍高于 2% 目标，部分受到能源等供给冲击影响。这给了实际利率和通胀补偿讨论的政策背景。

黄金一侧，World Gold Council 的 Q1 2026 Gold Demand Trends 显示：Q1 总黄金需求含 OTC 为 1,231 吨，同比增加 2%；季度需求价值达到 1,930 亿美元；央行净购金 244 吨；LBMA PM 金价季度均值为 4,872.9 美元/盎司。其 2026-07-08 Gold ETF Flows: June 2026 报告显示，全球实物支持黄金 ETF 6 月流出 89 亿美元，月末总持仓降至 4,047 吨，但上半年资金流仍为正，合计流入 80 亿美元。

股票一侧，State Street SPY 页面显示，截至 2026-07-20，SPY 的 FY1 P/E 为 22.24，Price/Book 为 5.34，预估 3-5 年 EPS 增长为 17.81%；同日基金 NAV 为 741.84 美元，AUM 为 7,833.3403 亿美元。基金前十大权重中 NVIDIA 7.69%、Apple 7.49%、Microsoft 4.67%，信息技术板块权重 36.92%。

### 为什么重要

这些数据把“利率、黄金、股票估值”放在同一天的观察框架里：

```text
10Y TIPS yield = 2.31%
10Y nominal yield = 4.55%
SPY FY1 P/E = 22.24
全球黄金 ETF 6 月净流出，但上半年仍净流入
```

入门读法不是“买什么、卖什么”，而是：

- 10 年实际利率给黄金的机会成本和股票折现率提供背景。
- 通胀补偿帮助区分“利率上升是因为真实回报要求提高”，还是“市场要求更多通胀补偿”。
- SPY 的 P/E、EPS 增长预期和科技权重提醒我们，股指估值不只受利率影响，也受盈利增长叙事影响。
- 黄金 ETF 流出与央行购金并存，说明黄金需求不是单一人群决定的。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| FOMC target range | 3.50%-3.75% | Federal Reserve, 2026-06-17 | 政策利率背景 |
| 10Y nominal CMT | 4.55% | H.15, 2026-07-17 | 长端名义利率 |
| 10Y TIPS yield | 2.31% | H.15, 2026-07-17 | 实际利率观察 |
| 10Y nominal - 10Y TIPS | 约 2.24 个百分点 | H.15 教学计算 | 通胀补偿入门近似 |
| Q1 总黄金需求 | 1,231 吨 | WGC, 2026-04-29 | 黄金需求结构 |
| Q1 央行净购金 | 244 吨 | WGC, 2026-04-29 | 储备需求 |
| 6 月全球黄金 ETF 流出 | 89 亿美元 | WGC, 2026-07-08 | 投资资金流 |
| 全球黄金 ETF 上半年流入 | 80 亿美元 | WGC, 2026-07-08 | 中期资金流 |
| SPY FY1 P/E | 22.24 | State Street, 2026-07-20 | 股指估值口径 |
| SPY 信息技术权重 | 36.92% | State Street, 2026-07-20 | 指数结构 |

### 这些现实事件如何连接理论

第一条链：实际利率与黄金。

```text
10Y TIPS yield 较高
-> 投资者持有安全利息资产的实际回报更有吸引力
-> 持有无息黄金的机会成本上升
-> 黄金 ETF 资金流可能承压
```

但 WGC 的数据同时显示央行和部分实物投资需求仍然存在。央行买黄金通常更看储备多元化、地缘风险和资产安全，不完全按短期实际利率交易。

第二条链：实际利率与股票估值。

```text
折现率上升
-> 未来现金流现值下降
-> P/E、P/S、EV/EBITDA 等估值倍数可能承压
```

但 SPY 同时有 17.81% 的预估 3-5 年 EPS 增长和较高科技权重。市场如果相信盈利增长足够强，估值倍数不一定马上下降。反过来，如果盈利预期被下修，高估值会更脆弱。

第三条链：通胀补偿。

```text
名义收益率上升
必须拆分：
- 是实际收益率上升？
- 还是通胀补偿上升？
- 还是期限溢价、债券供给和流动性变化？
```

这就是为什么不能只看 10Y nominal yield 一个数就判断黄金和股票。

### 至少一个真实市场机制案例

案例：用 2026-07-17 的 H.15 数据做 10 年通胀补偿入门计算。

```text
10Y nominal CMT = 4.55%
10Y TIPS yield = 2.31%
入门近似通胀补偿 = 2.24 个百分点
```

如果之后 10Y nominal 不变，但 10Y TIPS 从 2.31% 升到 2.60%，说明实际利率压力更大，通胀补偿近似会下降。对黄金，这通常意味着机会成本上升；对股票，通常意味着折现率压力上升。

如果 10Y nominal 上升，但 10Y TIPS 不变，更多压力可能来自通胀补偿或期限溢价，市场解读就不同。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 通胀目标与政策利率、Treasury/TIPS 市场、央行储备管理、黄金 ETF 监管结构、指数基金披露口径。
- 已确认事实：Fed 最新已发布 FOMC statement 维持 3.50%-3.75% 目标区间；H.15 提供名义 CMT 与 TIPS constant maturity yields；WGC 披露 Q1 黄金需求和 6 月 ETF 流；State Street 披露 SPY 的估值、持仓和行业权重。
- 市场可能如何传导：实际利率影响黄金机会成本和股票折现率；央行储备需求可能让黄金与短期 ETF 资金流分化；高科技权重让宽基股指对 AI 盈利预期更敏感。
- 仍需核验或观察：下一次 FOMC statement、CPI/PCE、10Y TIPS、10Y breakeven、WGC 后续 ETF flow、SPY EPS growth、前十大权重变化和美元指数。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Nominal Yield | 名义收益率 | 没扣通胀前的市场收益率 | 是市场最常看到的利率 |
| Real Yield | 实际收益率 | 扣除通胀补偿后的收益率口径 | 影响黄金机会成本和估值折现 |
| TIPS | 通胀保值国债 | 本金随通胀调整的美国国债 | 提供实际利率观察入口 |
| Breakeven Inflation | 盈亏平衡通胀率 | 名义国债与 TIPS 收益率差的近似 | 帮助拆分名义利率 |
| Opportunity Cost | 机会成本 | 持有一个资产时放弃另一个资产的代价 | 黄金没有利息，所以机会成本重要 |
| Discount Rate | 折现率 | 把未来现金流折回今天的利率 | 估值模型核心输入 |
| Equity Risk Premium | 股权风险溢价 | 持有股票相对安全资产要求的额外回报 | 解释股票为什么不能只和国债收益率比 |
| Valuation Multiple | 估值倍数 | 价格相对盈利、收入或现金流的倍数 | 市场给未来增长贴的价格标签 |
| Gold ETF | 黄金 ETF | 通常持有实物黄金或黄金相关资产的基金工具 | 观察投资资金流 |
| Central Bank Demand | 央行需求 | 央行和官方机构买卖黄金 | 与储备安全和多元化有关 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券与利率、第 15 课估值倍数与利率、第 30-32 课 DCF/WACC、第 53 课债券基金久期、第 57 课收益率曲线。
- 本课哪些内容会在后续课程继续使用：美元、汇率、跨资产风险偏好、黄金 ETF、股指估值、国际资产比较。
- 如果看不懂本课，可以先回到：第 30 课，复习“未来现金流为什么要折现”。

## 案例拆解

- 案例对象：2026-07-17 美国 10 年名义收益率、10 年 TIPS 收益率、黄金 ETF 流和 SPY 估值口径。
- 已确认事实：
  - 10Y nominal CMT 为 4.55%。
  - 10Y TIPS yield 为 2.31%。
  - 10Y 通胀补偿入门近似为 2.24 个百分点。
  - 全球实物支持黄金 ETF 2026 年 6 月流出 89 亿美元，但上半年仍流入 80 亿美元。
  - SPY FY1 P/E 为 22.24，信息技术权重为 36.92%。
- 来源日期和链接：见本课“来源”。
- 分析推理：实际利率提供了黄金机会成本和股票折现率背景；但黄金和股票都还受资金流、央行行为、盈利增长和指数结构影响。
- 后续验证指标：10Y TIPS、10Y nominal、10Y breakeven、美元指数、WGC ETF flow、SPY EPS growth、SPY P/E、科技板块权重。

## 一页实际利率传导检查表

```text
数据日期：

利率：
- FOMC target range：
- 10Y nominal：
- 10Y TIPS：
- 10Y nominal - 10Y TIPS：

黄金：
- WGC 最新 ETF flow：
- WGC 最新央行需求：
- 是否有地缘风险或储备多元化叙事：

股票：
- 宽基 ETF P/E：
- EPS growth：
- 前十大权重集中度：
- 高估值行业权重：

判断边界：
- 已确认事实：
- 我的推理：
- 不能确定：
- 下次要复核的数据：
```

## 个人情境连接

- 对关注清单的启发：看到黄金或科技股波动时，不要只写“避险”或“AI”，要同时记录实际利率、美元、ETF 资金流和盈利预期。
- 对持仓或基金选择的启发：宽基 ETF 的估值不是孤立数字，要和盈利增长、行业权重、利率背景一起读。
- 对工作、收入、消费或风险管理的启发：实际利率影响融资成本、企业投资、估值环境和现金工具收益，最终可能传导到就业、工资和消费信心。

## 结论边界

- 可以确定：截至 2026-07-17，H.15 显示美国 10 年 TIPS yield 为 2.31%，10 年名义 CMT 为 4.55%；WGC 显示黄金 ETF 6 月流出但上半年仍净流入；State Street 显示 SPY FY1 P/E 为 22.24。
- 不能确定：本课不能预测黄金、SPY、个股或债券未来涨跌；实际利率不是唯一变量。
- 需要继续观察：下一次 FOMC、通胀数据、TIPS、黄金 ETF flow、央行购金、美元、SPY 盈利预期和科技权重。
- 不构成投资建议的原因：本课只解释利率、黄金和股票估值之间的教学传导，不建议买入、卖出或配置任何资产。

## 练习题

1. 用 2026-07-17 的数据计算 10Y nominal - 10Y TIPS，并解释这个差值为什么只是入门近似。
2. 为什么实际利率上升通常会提高持有黄金的机会成本？
3. SPY FY1 P/E 为 22.24 时，为什么还必须同时看 EPS growth 和行业权重？
4. 黄金 ETF 6 月流出、央行 Q1 仍净购金，这两个事实为什么不矛盾？
5. 如果 10Y nominal 上升但 10Y TIPS 不变，你会优先怀疑哪些变量在变？

## 学习交接

- 本课已经完成：把收益率曲线推进到实际利率、通胀补偿、黄金机会成本和股票估值折现。
- 本课最重要的一句话：实际利率是连接债券、黄金和股票估值的一条核心线索，但不是资产价格的唯一开关。
- 需要复习的关键词：Nominal Yield、Real Yield、TIPS、Breakeven Inflation、Opportunity Cost、Discount Rate、Equity Risk Premium、Gold ETF、Valuation Multiple。
- 还不稳定、下次要回看的地方：美元和汇率如何把实际利率传导到跨境资金、黄金和国际资产。
- 适合下次打开仓库先读的文件：`lessons/2026-07-21-lesson-58-real-rates-inflation-compensation-gold-equity-valuation.md`

## 下节课安排

- 建议主题：第五十九课：美元、汇率、利差与跨资产风险偏好入门。
- 学习目标：理解 exchange rate、base currency、quote currency、dollar index、interest-rate differential、capital flow、FX translation 和 reserve currency 如何连接利率、黄金、股票和海外资产。
- 建议案例：使用 Federal Reserve H.10 最新汇率、H.15 利率、IMF COFER 储备货币数据和 WGC 黄金 ETF flow，解释美元变化为什么会影响黄金、海外资产和跨境投资回报。
- 必须解释的关键词：Exchange Rate、Base Currency、Quote Currency、USD Index、Interest-rate Differential、Capital Flow、FX Translation、Reserve Currency、Hedging、Risk Appetite。
- 下节课开始前需要联网核验的数据：Federal Reserve H.10、H.15、最新 FOMC statement、IMF COFER 或官方储备数据、WGC 黄金 ETF flow。

## 来源

- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Federal Reserve, FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- World Gold Council, Gold Demand Trends: Q1 2026: https://www.gold.org/goldhub/research/gold-demand-trends/gold-demand-trends-q1-2026
- World Gold Council, Gold ETF Flows: June 2026: https://www.gold.org/goldhub/research/gold-etfs-holdings-and-flows/2026/07
- World Gold Council, Gold spot prices: https://www.gold.org/goldhub/data/gold-prices
- State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/individual/etfs/state-street-spdr-sp-500-etf-trust-spy
