# 第二十九课：自由现金流收益率、现金转换与估值质量入门

## 基本信息

- 日期：2026-06-23
- 数据截至：2026-06-23 20:08（Asia/Shanghai）；股票价格采用 Nasdaq quote API 2026-06-22 收盘价做估算；Microsoft 财务数据采用 2026-04-29 Form 8-K exhibit 99.1；Adobe 财务数据采用 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 声明和 U.S. Treasury 2026-06-22 收益率曲线。
- 主题：为什么 EBITDA、净利润和 EPS 之后，还要看自由现金流收益率和现金转换。
- 学习目标：理解 Operating Cash Flow、Capex、Free Cash Flow、Free Cash Flow Yield、Cash Conversion、Capex Intensity、Owner Earnings 和 Normalized FCF，知道自由现金流不是完美答案，但能帮助检验估值质量。
- 相关资产：股票、公司财报、现金流量表、回购、资本开支、利率。
- 核心来源：
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - Adobe FY2026 Q2 Form 10-Q, period 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Nasdaq MSFT quote API, retrieved 2026-06-23: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
  - Nasdaq ADBE quote API, retrieved 2026-06-23: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十七课说 EBITDA 不等于自由现金流。今天继续问：

> 如果公司利润很好，为什么还要看它真正剩下多少现金？

因为普通股股东最终拿到的不是会计利润本身，而是公司在维持和扩大经营之后还能留下的现金能力。净利润、EPS、EBITDA 都有用，但它们可能还没有扣掉资本开支、营运资本变化、税费、利息或一次性现金支出。

### 参考的教材式概念顺序

1. Operating Cash Flow 观察主营业务实际产生的现金。
2. Capex 观察为了维持和扩张经营能力花出去的长期资产投入。
3. Free Cash Flow 是经营现金流扣掉资本开支后的剩余现金。
4. Free Cash Flow Yield 把自由现金流和市值或企业价值相除。
5. Cash Conversion 观察利润能不能变成现金。
6. Capex Intensity 观察增长对资本开支的依赖程度。
7. Normalized FCF 提醒我们不要把单季或异常年份机械年化。

### 核心概念

最小公式：

```text
Free Cash Flow = Operating Cash Flow - Capex
Free Cash Flow Yield = Free Cash Flow / Market Cap
Cash Conversion = Free Cash Flow / Net Income
Capex Intensity = Capex / Revenue
```

这些公式只是入门版本。专业模型还会处理租赁、并购、资产出售、股票薪酬、重组费用、递延收入、客户预付款、季节性、税费时点和维护性资本开支。

### 用自己的话解释

如果一家店一年赚了 100 万净利润，但为了继续经营必须花 80 万装修、买设备、扩仓，那么真正更接近“可自由支配”的钱可能只有 20 万。反过来，如果另一家店赚 100 万，但只需要 5 万维护投入，现金质量就完全不同。

这就是为什么第二十七课讲 EV/EBITDA 后，必须接着学自由现金流。

### 常见误区

- 误区一：净利润高就等于现金多。应收账款、库存、税费和资本开支都可能让现金跟利润不同步。
- 误区二：EBITDA 高就等于自由现金流好。EBITDA 没扣 Capex。
- 误区三：自由现金流收益率越高越安全。高收益率可能来自股价下跌，也可能来自一次性现金流。
- 误区四：把一个季度自由现金流乘以四当成长期水平。季节性和一次性项目会扭曲年化结果。
- 误区五：回购金额等于股东收益。回购价格、股权激励、债务和现金流来源都要一起看。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课继续使用 Microsoft 和 Adobe。Microsoft 是高利润、高云和 AI 增长、但资本开支强度明显上升的案例；Adobe 是经营现金流强、资本开支较轻、但需要注意 non-GAAP 调整和回购执行的案例。

以下估算使用 Nasdaq 2026-06-22 收盘价和最新披露股数。Microsoft 使用 7,429 million shares outstanding 的近似数；Adobe 使用 2026-06-11 10-Q 封面披露的 397.5 million shares outstanding。

| 公司 | 价格与市值估算 | 期间 | 经营现金流 | Capex | 粗略自由现金流 | 粗略年化 FCF Yield |
| --- | ---: | --- | ---: | ---: | ---: | ---: |
| Microsoft | 367.34 美元；约 2.729 万亿美元 | FY2026 Q3 | 466.79 亿美元 | 308.76 亿美元 | 158.03 亿美元 | 单季年化约 2.3% |
| Microsoft | 同上 | FY2026 前三季度 | 1,274.94 亿美元 | 801.46 亿美元 | 473.48 亿美元 | 前三季度年化约 2.3% |
| Adobe | 194.90 美元；约 774.73 亿美元 | FY2026 Q2 | 21.65 亿美元 | 0.58 亿美元 | 21.07 亿美元 | 单季年化约 10.9% |
| Adobe | 同上 | FY2026 前六个月 | 51.23 亿美元 | 0.95 亿美元 | 50.28 亿美元 | 半年年化约 13.0% |

计算示例：

```text
Microsoft FY2026 Q3 FCF ~= 46.679 - 30.876 = 15.803 billion dollars
Microsoft 市值 ~= 367.34 * 7.429 billion = 2.729 trillion dollars
Microsoft 单季年化 FCF Yield ~= 15.803 * 4 / 2728.969 = 2.3%

Adobe FY2026 Q2 FCF ~= 2.165 - 0.058 = 2.107 billion dollars
Adobe 市值 ~= 194.90 * 0.3975 billion = 77.473 billion dollars
Adobe 单季年化 FCF Yield ~= 2.107 * 4 / 77.473 = 10.9%
```

再看资本开支强度：

```text
Microsoft FY2026 前三季度 Capex Intensity ~= 80.146 / 241.832 = 33.1%
Adobe FY2026 前六个月 Capex Intensity ~= 0.095 / 13.016 = 0.7%
```

这不是在说 Adobe 一定比 Microsoft 好。它只说明两家公司现金流结构不同：Microsoft 当前增长更依赖大规模云和 AI 基础设施投入；Adobe 的软件模式在本期披露中更偏资产轻型。

### 为什么重要

Microsoft 2026-04-29 8-K exhibit 显示，公司 FY2026 Q3 收入为 828.86 亿美元，同比增长 18%；Satya Nadella 称 AI business annual revenue run rate 超过 370 亿美元、同比增长 123%。同一份文件也显示 Q3 additions to property and equipment 为 308.76 亿美元，前三季度为 801.46 亿美元。

这说明高增长和高 Capex 可以同时出现。市场要继续问的是：这些投入未来能否产生足够现金回报。

Adobe 2026-06-11 8-K exhibit 显示 FY2026 Q2 经营现金流 21.65 亿美元、购买 property and equipment 0.58 亿美元；Adobe 2026-06-15 10-Q 显示前六个月经营现金流 51.23 亿美元、购买 property and equipment 0.95 亿美元，同时前六个月回购普通股现金流出 45.89 亿美元。

这说明资产轻型业务可能更容易把经营现金流转成回购或安全垫，但仍要看回购价格、股数变化、债务和后续增长。

### 本节采用的数据和来源

- Microsoft 经营现金流、additions to property and equipment、收入、净利润和股数近似来自 Microsoft 2026-04-29 Form 8-K exhibit 99.1。
- Adobe 经营现金流、purchases of property and equipment、收入、净利润、现金、短期投资、债务、回购和股数来自 Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q。
- 股票价格来自 Nasdaq quote API 的 2026-06-22 收盘价；盘前实时价变化不用于本课市值估算。
- 利率背景来自 Fed 和 Treasury；2026-06-22 Treasury 曲线显示 2 年期 4.24%、10 年期 4.51%、30 年期 4.95%。

### 这些现实事件如何连接理论

P/E 和 EV/EBITDA 看“利润价格”，自由现金流收益率看“现金价格”。当一家公司资本开支很大时，EBITDA 可能仍然漂亮，但自由现金流会被 Capex 吃掉一部分。反过来，资产轻型公司如果资本开支很低，经营现金流更容易留下来，但仍可能被回购、并购、债务或股权激励影响。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 现金流量表披露、公司 non-GAAP 指标说明、交易所价格数据、央行利率政策、债务再融资环境。
- 已确认事实：Microsoft 和 Adobe 均已披露最新 8-K；Adobe 也已披露最新 10-Q；Fed 维持目标利率区间在 3.50%-3.75%；Treasury 已发布 2026-06-22 曲线。
- 市场可能如何传导：高利率会提高资本开支项目的回报门槛；自由现金流收益率较低的公司更依赖未来增长兑现；自由现金流强但增长放缓的公司也可能面临倍数压缩。
- 仍需核验或观察：Microsoft AI 基础设施投入的回收周期、Adobe 回购对股数的实际抵消效果、未来经营现金流是否保持稳定、利率是否继续影响资本成本。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Operating Cash Flow | 经营现金流 | 主营业务实际带来的现金净流入 | 检查利润是否变成现金 |
| Capex | 资本开支 | 购买长期资产、数据中心、设备等投入 | 会直接减少自由现金流 |
| Free Cash Flow | 自由现金流 | 经营现金流扣掉资本开支后的现金 | 观察公司可支配现金能力 |
| Free Cash Flow Yield | 自由现金流收益率 | 自由现金流除以市值或企业价值 | 把现金流和价格连接起来 |
| Cash Conversion | 现金转换 | 利润转成现金的程度 | 防止只看会计利润 |
| Capex Intensity | 资本开支强度 | Capex 除以收入 | 判断增长是否很吃资本投入 |
| Owner Earnings | 所有者收益 | 更接近长期可分配给所有者的现金能力 | 是价值投资和 DCF 的重要直觉 |
| Normalized FCF | 正常化自由现金流 | 去掉季节性和异常项目后的自由现金流 | 防止把单期数据当长期事实 |
| Maintenance Capex | 维护性资本开支 | 为维持现有业务必须花的钱 | 与扩张性 Capex 区分后才能判断真实可分配现金 |

## 回顾提示

- 学到本课前建议回顾：第 10 课现金流量表、第 13 课资本配置、第 17 课 Capex 与自由现金流、第 27 课 EV/EBITDA、第 28 课 PEG。
- 本课哪些内容会在后续课程继续使用：DCF、折现率、终值、安全边际、回购质量、并购估值和资产配置。
- 如果看不懂本课，可以先回到：第 17 课“Capex、经营现金流与自由现金流入门”。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的自由现金流收益率和资本开支强度。
- 已确认事实：
  - Microsoft FY2026 Q3 经营现金流 466.79 亿美元，additions to property and equipment 308.76 亿美元；前三季度经营现金流 1,274.94 亿美元，additions to property and equipment 801.46 亿美元。
  - Microsoft FY2026 Q3 收入 828.86 亿美元，前三季度收入 2,418.32 亿美元；普通股 outstanding 约 7,429 million。
  - Adobe FY2026 Q2 经营现金流 21.65 亿美元，purchases of property and equipment 0.58 亿美元；前六个月经营现金流 51.23 亿美元，purchases of property and equipment 0.95 亿美元。
  - Adobe 10-Q 披露截至 2026-06-11 有 397.5 million shares outstanding；前六个月 repurchases of common stock 45.89 亿美元。
  - Nasdaq quote API 显示 Microsoft 和 Adobe 2026-06-22 收盘价分别为 367.34 美元和 194.90 美元。
- 来源日期和链接：Microsoft 8-K exhibit 2026-04-29；Adobe 8-K exhibit 2026-06-11；Adobe 10-Q filed 2026-06-15；Nasdaq API retrieved 2026-06-23；Fed 2026-06-17；Treasury 2026-06-22。
- 分析推理：Microsoft 的当前自由现金流收益率被高 Capex 压低，这可能是 AI 基础设施投入期的正常现象，也可能在未来需要通过更高现金回报证明合理性。Adobe 当前自由现金流收益率较高，说明资产轻型现金转换强，但仍要核验增长、竞争、non-GAAP 调整和回购价格。
- 后续验证指标：资本开支是否继续上升、AI/云收入是否带来增量现金流、经营现金流是否跟上利润、回购是否抵消股权激励、自由现金流是否能长期维持。

## 个人情境连接

- 对关注清单的启发：看到“AI 高增长”时，顺手看 Capex 和自由现金流；看到“低估值”时，顺手看现金转换。
- 对持仓或基金选择的启发：基金如果重仓高 Capex 公司，短期自由现金流收益率可能和 P/E 给出的印象不同。
- 对工作、收入、消费或风险管理的启发：个人收入高但固定支出和再投入很大，也不等于自由现金流高；企业也是一样。

## 结论边界

- 可以确定：自由现金流把经营现金流和资本开支连接起来；自由现金流收益率能补充 P/E 和 EV/EBITDA；现金转换能帮助检验利润质量。
- 不能确定：单季或半年自由现金流不能直接代表长期水平；高自由现金流收益率不自动代表便宜；低自由现金流收益率也不自动代表昂贵。
- 需要继续观察：维护性 Capex 与扩张性 Capex 的拆分、营运资本季节性、回购价格、债务和利率环境。
- 不构成投资建议的原因：本课只解释现金流估值框架，不判断 Microsoft、Adobe 或任何证券是否值得买卖。

## 练习题

1. 为什么 EBITDA 高不等于自由现金流高？
2. 用 Microsoft 的例子解释：为什么高增长和高 Capex 可以同时出现？
3. 用 Adobe 的例子解释：为什么自由现金流强也不能直接等同于股东回报？
4. 如果一家公司自由现金流收益率突然升高，你会先判断是现金流改善，还是股价下跌？
5. 为什么不能把一个季度自由现金流简单乘以四当成长期水平？

## 学习交接

- 本课已经完成：把经营现金流、资本开支、自由现金流、自由现金流收益率、现金转换和资本开支强度连成估值质量框架。
- 本课最重要的一句话：估值不是只看利润价格，还要看利润最终能不能变成扣完必要投入后的现金。
- 需要复习的关键词：Operating Cash Flow、Capex、Free Cash Flow、Free Cash Flow Yield、Cash Conversion、Capex Intensity、Owner Earnings、Normalized FCF、Maintenance Capex。
- 还不稳定、下次要回看的地方：自由现金流需要正常化，不能把单期数据机械年化；Capex 也要区分维护和扩张。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第三十课：DCF、折现率、终值与安全边际入门。
- 学习目标：把自由现金流放进未来年份，理解为什么估值要折现，为什么终值和假设边界会强烈影响结论。
- 建议案例：继续使用 Microsoft 与 Adobe；可加入 SPY 或一只成熟低增长公司做对照，但必须重新核验 SEC、公司 IR、ETF/指数发行人、交易所和利率来源。
- 必须解释的关键词：Discount Rate、Present Value、DCF、Terminal Value、Margin of Safety、Scenario Analysis、Sensitivity Analysis、Cost of Capital。
- 下节课开始前需要联网核验的数据：最新股价、股数、自由现金流、资本开支、收入增速、利润率、债务成本、10 年期 Treasury yield、公司 guidance 和 analyst estimates。

## 来源

- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- Adobe FY2026 Q2 Form 10-Q: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
- Nasdaq ADBE quote API: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606
