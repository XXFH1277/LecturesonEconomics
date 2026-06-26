# 第三十四课：ROIC、ROE、投入资本与经济利润入门

## 基本信息

- 日期：2026-06-26
- 数据截至：2026-06-26 20:05（Asia/Shanghai）；公司财务采用 Microsoft 2026-04-29 Form 8-K exhibit 99.1、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 Adobe 2026-06-15 Form 10-Q；利率与信用利差采用 FRED / Federal Reserve / ICE BofA 2026-06-24 最新可得数据；Fed 政策采用 2026-06-17 FOMC statement；Microsoft 股价采用 Nasdaq quote API 2026-06-25 10:50 AM ET。
- 主题：公司赚到的钱，和它占用的资本相比，到底够不够好。
- 学习目标：理解 ROIC、ROE、Invested Capital、NOPAT、Economic Profit、Spread、Goodwill、Operating Assets、Capital Intensity 和 Reinvestment，把“利润多”推进到“资本回报是否超过资本成本”。
- 相关资产：股票、公司债、国债收益率、公司财报、DCF、WACC、回购、并购。
- 已核验来源（核心来源）：
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity, 2026-06-24: https://fred.stlouisfed.org/series/DGS10
  - FRED / ICE BofA US Corporate Index Effective Yield, 2026-06-24: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
  - FRED / ICE BofA US Corporate Index Option-Adjusted Spread, 2026-06-24: https://fred.stlouisfed.org/series/BAMLC0A0CM
  - FRED / ICE BofA BBB US Corporate Index Option-Adjusted Spread, 2026-06-24: https://fred.stlouisfed.org/series/BAMLC0A4CBBB
  - Nasdaq MSFT quote API, retrieved 2026-06-26: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

前面两课学了 WACC 和债务风险。现在继续问：

> 公司赚很多钱，是否一定说明它创造了很多价值？

不一定。要看它为了赚这些钱占用了多少资本。如果一家公司赚 10 亿美元，但要占用 1,000 亿美元资本，回报率只有 1%；另一家公司赚 10 亿美元，只占用 50 亿美元资本，回报率是 20%。两家公司利润数字一样，但资本效率完全不同。

### 参考的教材式概念顺序

1. Operating Profit：先看经营本身产生多少营业利润。
2. NOPAT：把营业利润扣除正常税负，得到税后经营利润。
3. Invested Capital：看经营占用了多少股东和债权人资本。
4. ROIC：用 NOPAT 除以投入资本，观察经营资本回报率。
5. WACC：资本提供者要求的最低综合回报。
6. Spread：ROIC 减 WACC，观察回报率是否超过资本成本。
7. Economic Profit：超过资本成本之后留下的经济利润。
8. ROE：用净利润除以股东权益，观察股东账面权益回报。

### 核心概念

最小公式：

```text
NOPAT = Operating Income x (1 - 税率)

Invested Capital 教学近似 =
  Stockholders' Equity + Interest-bearing Debt - Cash and Short-term Investments

ROIC = NOPAT / Invested Capital

ROE = Net Income / Stockholders' Equity

Economic Profit = Invested Capital x (ROIC - WACC)
```

这里的关键不是背公式，而是理解三个问题：

- 利润是经营赚来的，还是靠投资收益、税率、一次性项目推高的？
- 投入资本是真正服务经营，还是被大量现金、并购商誉、库存或应收账款占住了？
- 回报率是否高于资本成本，而不是只看增长率是否漂亮？

### 用自己的话解释

ROIC 像是在问：“公司每占用 100 元经营资本，税后经营能赚回多少元？”它更偏经营质量。

ROE 像是在问：“股东账面权益每 100 元，净利润能赚回多少元？”它更偏股东权益回报，但会被负债、回购、会计权益和一次性项目影响。

经济利润像是在问：“扣掉资本本来应该拿到的最低回报后，还剩多少？”如果 ROIC 高于 WACC，公司增长更可能创造价值；如果 ROIC 低于 WACC，增长可能只是把更多钱投进低回报项目。

### 常见误区

- 误区一：只看净利润，不看占用资本。利润规模大不等于资本效率高。
- 误区二：把 ROE 当成万能指标。高负债、回购减少权益或一次性利润都可能推高 ROE。
- 误区三：把现金全部当经营资本。大量闲置现金通常要从投入资本中扣除，否则会低估经营回报率。
- 误区四：忽略商誉。并购形成的 goodwill 代表历史买入资产时支付的溢价，可能影响投入资本和未来减值风险。
- 误区五：把单季或半年 ROIC 机械年化。本课只做入门教学估算，不把中期数字年化为正式结论。

## 第二大板块：实时背景与市场传导

### 发生了什么

截至本课核验时，FRED 显示 2026-06-24 的 10 年期 Treasury yield 为 4.41%，ICE BofA US Corporate Index Effective Yield 为 5.14%，US Corporate Index OAS 为 0.75%，BBB OAS 为 0.94%。Federal Reserve 2026-06-17 FOMC statement 维持 federal funds rate 目标区间在 3.50%-3.75%，并指出通胀仍高于 2% 目标。

这给 ROIC 课程一个现实背景：资本不是免费的。只要利率和信用利差仍然有高度，公司投资项目就要跨过 WACC 这条门槛。增长本身不够，增长的回报率必须够高。

### 为什么重要

如果一家公司课堂估算 WACC 约为 8%，但 ROIC 只有 5%，它每多投 1 元资本，可能是在扩大低回报资产。相反，如果 ROIC 长期明显高于 WACC，它才更可能通过再投资创造复利。

这也是为什么市场会关心 AI、云计算、并购和回购背后的资本回报：同样是花钱，可能是高回报再投资，也可能是低回报扩张。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| 10 年期 Treasury yield | 4.41% | FRED / H.15, 2026-06-24 | WACC 和资本成本背景 |
| IG corporate effective yield | 5.14% | FRED / ICE BofA, 2026-06-24 | 债务成本背景 |
| IG corporate OAS | 0.75% | FRED / ICE BofA, 2026-06-24 | 信用利差背景 |
| BBB corporate OAS | 0.94% | FRED / ICE BofA, 2026-06-24 | 较低投资级信用风险背景 |
| Microsoft nine-month operating income | 1,146.34 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | NOPAT 教学估算 |
| Microsoft nine-month provision for income taxes | 239.04 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 税率教学估算 |
| Microsoft stockholders' equity | 4,143.67 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | ROE 与投入资本 |
| Microsoft cash, cash equivalents and short-term investments | 782.72 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 投入资本扣除项 |
| Adobe six-month operating income | 46.56 亿美元 | Adobe 2026-06-11 Form 8-K exhibit 99.1 | NOPAT 教学估算 |
| Adobe stockholders' equity | 115.18 亿美元 | Adobe 2026-06-11 Form 8-K exhibit 99.1 / 2026-06-15 Form 10-Q | ROE 与投入资本 |
| Adobe goodwill | 140.41 亿美元 | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 商誉和并购资本案例 |

### Microsoft 的教学估算：高利润不等于不用看资本

Microsoft 2026 财年前九个月披露：

- revenue 为 2,418.32 亿美元。
- operating income 为 1,146.34 亿美元。
- income before income taxes 为 1,218.87 亿美元。
- provision for income taxes 为 239.04 亿美元。
- net income 为 979.83 亿美元。
- stockholders' equity 为 4,143.67 亿美元。
- current portion of long-term debt 为 88.39 亿美元，long-term debt 为 314.23 亿美元。
- cash, cash equivalents and short-term investments 为 782.72 亿美元。

课堂税率估算：

```text
税率 ≈ 239.04 / 1,218.87 = 19.6%
NOPAT ≈ 1,146.34 x (1 - 19.6%) = 921.52 亿美元
投入资本 ≈ 4,143.67 + 88.39 + 314.23 - 782.72 = 3,763.57 亿美元
九个月 ROIC 教学估算 ≈ 921.52 / 3,763.57 = 24.5%
九个月 ROE 教学估算 ≈ 979.83 / 4,143.67 = 23.6%
```

这些数字说明 Microsoft 在这个课堂口径下表现出很高的资本回报，但这不是公司的官方 ROIC，也没有年化。后续研究要继续检查云和 AI 基础设施资本开支、折旧、长期经营利润率、税率、并购、股权投资和资本结构变化。

### Adobe 的教学估算：资产轻不代表不用看商誉和回购

Adobe 2026 财年上半年披露：

- revenue 为 130.16 亿美元。
- operating income 为 46.56 亿美元。
- income before income taxes 为 46.60 亿美元。
- provision for income taxes 为 10.59 亿美元。
- net income 为 36.01 亿美元。
- cash and cash equivalents 为 49.19 亿美元，short-term investments 为 7.07 亿美元。
- current debt 为 18.43 亿美元，long-term debt 为 48.02 亿美元。
- stockholders' equity 为 115.18 亿美元。
- goodwill 为 140.41 亿美元。

课堂税率估算：

```text
税率 ≈ 10.59 / 46.60 = 22.7%
NOPAT ≈ 46.56 x (1 - 22.7%) = 35.98 亿美元
投入资本 ≈ 115.18 + 18.43 + 48.02 - 49.19 - 7.07 = 125.37 亿美元
六个月 ROIC 教学估算 ≈ 35.98 / 125.37 = 28.7%
六个月 ROE 教学估算 ≈ 36.01 / 115.18 = 31.3%
```

Adobe 的 goodwill 大于期末 stockholders' equity，这提醒我们：并购价格、无形资产、商誉减值和回购都会影响账面资本。Adobe 2026 Q2 还披露 GAAP 结果包含与 Publishing & Advertising reporting unit 相关的 0.70 亿美元非现金商誉减值。这个事实不代表 Adobe 整体经营突然失效，但说明商誉不是装饰数字，未来可能影响利润和资本回报解释。

### 这些现实事件如何连接理论

- 利率和信用利差：WACC 的门槛不会凭空消失。ROIC 必须和资本成本比较。
- AI 和云资本开支：项目可能带来长期增长，也会先占用大量资本。
- 并购和商誉：并购可以带来客户、技术和收入，也可能形成高额商誉和后续减值风险。
- 股票回购：回购减少股东权益时，ROE 可能上升，但不一定说明经营变好。
- 高 ROIC 公司：如果还能找到足够多高回报再投资机会，增长质量会更好；如果找不到，分红或回购可能更合理。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 利率政策、SEC 披露制度、公司回购和并购披露、商誉减值会计规则、信用市场利差。
- 已确认事实：Fed 2026-06-17 维持目标区间 3.50%-3.75%；FRED 显示 2026-06-24 10 年期 Treasury yield 为 4.41%；Adobe 2026 Q2 披露 0.70 亿美元非现金商誉减值；Microsoft 和 Adobe 的经营利润、税费、现金、债务、股东权益来自 SEC 文件。
- 市场可能如何传导：利率影响 WACC；WACC 影响经济利润；经济利润影响估值；商誉减值、回购和资本开支会改变投资者对增长质量的判断。
- 仍需核验或观察：Microsoft 下一季 AI 资本开支、云收入增长和折旧；Adobe Semrush 整合、ARR、RPO、商誉变化、回购节奏和税率；信用利差和 Treasury yield 后续变化。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| ROIC | 投入资本回报率 | 税后经营利润除以投入资本 | 衡量经营资本效率，常用来和 WACC 比较 |
| ROE | 净资产收益率 | 净利润除以股东权益 | 衡量股东账面权益回报，但会受杠杆和回购影响 |
| Invested Capital | 投入资本 | 支撑经营活动所占用的股东和债权人资本 | 是 ROIC 的分母，口径选择会影响结论 |
| NOPAT | 税后净营业利润 | 不考虑融资结构后的税后经营利润 | 让不同资本结构公司更可比 |
| Economic Profit | 经济利润 | 超过资本成本后的利润 | 解释增长是否真正创造价值 |
| Spread | 利差 / 回报差 | ROIC 减 WACC 的差额 | 正 spread 才更可能创造价值 |
| Goodwill | 商誉 | 并购价格超过可辨认净资产公允价值的部分 | 代表历史并购溢价，也可能发生减值 |
| Operating Assets | 经营资产 | 用于主营业务的资产 | 区分经营资本和闲置金融资产 |
| Capital Intensity | 资本强度 | 获得收入或增长需要投入多少资本 | 影响现金流、ROIC 和增长质量 |
| Reinvestment | 再投资 | 把利润或现金继续投回业务 | 高 ROIC 再投资才更容易复利 |

## 回顾提示

- 学到本课前建议回顾：第 32 课 WACC、无风险利率、资本结构；第 33 课信用利差、税盾与债务风险。
- 本课哪些内容会在后续课程继续使用：增长质量、再投资率、回购质量、并购质量、护城河、资本配置和长期复利。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 17 课 Capex 与自由现金流、第 29 课自由现金流收益率。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的 ROIC / ROE 教学估算。
- 已确认事实：
  - Microsoft 2026 财年前九个月 operating income 为 1,146.34 亿美元，net income 为 979.83 亿美元。
  - Microsoft 2026-03-31 stockholders' equity 为 4,143.67 亿美元，cash / short-term investments 为 782.72 亿美元，current + long-term debt 为 402.62 亿美元。
  - Adobe 2026 财年上半年 operating income 为 46.56 亿美元，net income 为 36.01 亿美元。
  - Adobe 2026-05-29 stockholders' equity 为 115.18 亿美元，cash / short-term investments 为 56.26 亿美元，current + long-term debt 为 66.45 亿美元，goodwill 为 140.41 亿美元。
- 来源日期和链接：见本课“来源”。
- 分析推理：两家公司在课堂估算口径下都有较高 ROIC，但 Microsoft 的资本强度正在受 AI 基础设施投入影响，Adobe 的资本结构和商誉更受回购、订阅现金流和并购影响。
- 后续验证指标：下一季 operating income、tax rate、cash、debt、stockholders' equity、goodwill、capex、operating cash flow、RPO、ARR、回购和管理层资本配置说明。

## 个人情境连接

- 对关注清单的启发：看公司时，不只问“赚多少钱”，还要问“用了多少钱赚这些钱”。
- 对持仓或基金选择的启发：基金重仓高 ROIC 公司不代表一定便宜；还要看估值、增长持续性和资本再投资空间。
- 对工作、收入、消费或风险管理的启发：个人也有资本回报。时间、学习成本、创业投入和债务都要看回报是否超过机会成本。

## 结论边界

- 可以确定：ROIC 用来观察经营资本效率，ROE 用来观察股东权益回报；二者都必须结合 WACC、资本结构、现金、商誉和一次性项目解释。
- 不能确定：本课没有给出 Microsoft 或 Adobe 的正式 ROIC，也没有判断股票贵或便宜；中期数字没有年化，不能直接当全年结论。
- 需要继续观察：利率、信用利差、资本开支、AI 投资回报、并购整合、商誉减值、回购节奏和税率。
- 不构成投资建议的原因：本课只训练财务指标拆解和资本回报思维，不推荐买入或卖出任何证券。

## 练习题

1. 为什么 ROIC 要用 NOPAT，而不是直接用净利润？
2. 一家公司 NOPAT 为 20 亿元，投入资本为 200 亿元，WACC 为 9%。它的 ROIC 和 economic profit 分别是多少？
3. 为什么高 ROE 可能来自高负债或回购，而不一定来自经营改善？
4. Adobe 的 goodwill 大于 stockholders' equity 时，学习者应该提出哪三个问题？
5. 如果一家公司 ROIC 很高，但没有足够高回报再投资机会，它应该优先考虑哪些资本配置选择？

## 学习交接

- 本课已经完成：把 WACC 和债务风险推进到 ROIC、ROE、NOPAT、投入资本、商誉和经济利润。
- 本课最重要的一句话：增长是否创造价值，取决于回报率是否超过资本成本，而不只取决于收入或利润是否变大。
- 需要复习的关键词：ROIC、ROE、Invested Capital、NOPAT、Economic Profit、Spread、Goodwill、Operating Assets、Capital Intensity、Reinvestment。
- 还不稳定、下次要回看的地方：高 ROIC 只有在能继续找到高回报再投资机会时，才更容易转化成高质量增长。
- 适合下次打开仓库先读的文件：`lessons/2026-06-26-lesson-35-reinvestment-growth-quality.md`

## 下节课安排

- 建议主题：第三十五课：再投资率、增量 ROIC 与增长质量入门。
- 学习目标：理解为什么“增长”要拆成增长速度、再投资规模、增量回报率和现金流压力，避免把所有增长都看成好事。
- 建议案例：继续使用 Microsoft 的 AI/cloud 资本开支与 Adobe 的订阅现金流、Semrush 并购和回购。
- 必须解释的关键词：Reinvestment Rate、Incremental ROIC、Maintenance Capex、Growth Capex、Operating Leverage、Unit Economics、Organic Growth、Acquired Growth、Buyback Yield、Capital Allocation。
- 下节课开始前需要联网核验的数据：Microsoft 最新 cloud / AI revenue、capex、operating cash flow、stock repurchases；Adobe 最新 revenue guidance、ARR、RPO、operating cash flow、property and equipment purchases、Semrush acquisition、stock repurchases。

## 来源

- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity: https://fred.stlouisfed.org/series/DGS10
- FRED / ICE BofA US Corporate Index Effective Yield: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
- FRED / ICE BofA US Corporate Index Option-Adjusted Spread: https://fred.stlouisfed.org/series/BAMLC0A0CM
- FRED / ICE BofA BBB US Corporate Index Option-Adjusted Spread: https://fred.stlouisfed.org/series/BAMLC0A4CBBB
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
