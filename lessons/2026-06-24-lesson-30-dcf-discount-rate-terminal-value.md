# 第三十课：DCF、折现率、终值与安全边际入门

## 基本信息

- 日期：2026-06-24
- 数据截至：2026-06-24 20:15（Asia/Shanghai）；股票价格采用 Nasdaq quote API 2026-06-24 08:13 ET；Treasury 曲线采用 U.S. Treasury 2026-06-23 最新可得日度数据；公司财务采用 Microsoft 2026-04-29 Form 8-K exhibit 99.1、Microsoft 2026-04-29 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 Adobe 2026-06-15 Form 10-Q。
- 主题：把未来自由现金流折回今天，理解为什么估值不是简单乘一个倍数。
- 学习目标：理解 DCF、Present Value、Discount Rate、Terminal Value、Margin of Safety、Stable Growth、FCFF 和 Equity Value，知道 DCF 是假设管理工具，不是精确预测机器。
- 相关资产：股票、公司财报、现金流量表、利率、企业价值、普通股估值。
- 已核验来源（核心来源）：
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - Microsoft Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Nasdaq MSFT quote API, retrieved 2026-06-24: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
  - Nasdaq ADBE quote API, retrieved 2026-06-24: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606
  - Aswath Damodaran, Stern/NYU terminal value note: https://pages.stern.nyu.edu/~adamodar/pdfiles/eqnotes/dcfstabl.pdf

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十九课学了自由现金流收益率。今天继续问：

> 如果公司未来很多年都会产生现金，为什么不能把今年自由现金流直接乘以一个倍数就结束？

因为未来的钱和今天的钱不是同一件事。越晚收到的钱，不确定性越高，也少了一段时间可以再投资的机会。所以 DCF 的第一层直觉是：把未来每一年的现金流折回今天，再加总。

### 参考的教材式概念顺序

1. Present Value 先解决“未来的钱今天值多少”。
2. Discount Rate 解决“用什么回报率把未来折回今天”。
3. Free Cash Flow 解决“折的到底是哪类现金流”。
4. Explicit Forecast Period 解决“前几年可以逐年预测”。
5. Terminal Value 解决“不能永远逐年预测时，剩余年份怎么处理”。
6. Enterprise Value 到 Equity Value 解决“公司整体价值怎样变成普通股价值”。
7. Margin of Safety 解决“模型不确定时，为什么不能只看一个点估值”。

### 核心概念

最小公式：

```text
Present Value = Future Cash Flow / (1 + Discount Rate)^n

DCF Value = 第1年现金流现值 + 第2年现金流现值 + ... + 终值现值

Terminal Value = 第N+1年现金流 / (Discount Rate - Terminal Growth Rate)
```

这里的 `n` 是第几年，`Discount Rate` 是折现率，`Terminal Growth Rate` 是终值阶段的长期稳定增长率。

### 用自己的话解释

如果有人说 5 年后给你 100 元，你不会把它当成今天的 100 元。原因有两个：第一，你今天拿到钱可以存款、投资或还债；第二，5 年后能不能真的拿到也有不确定性。折现率就是把“等待成本”和“风险补偿”放进同一个数字里。

DCF 不是水晶球。它更像一张假设清单：收入能增长多久，利润率能不能保持，资本开支要不要继续增加，利率环境是否变了，长期增长率是否过高。

### 常见误区

- 误区一：DCF 算出来一个数字，就代表公司真实价值。DCF 输出强烈依赖假设。
- 误区二：终值只是模型最后一行，不重要。实际模型里终值常常占很大比例。
- 误区三：折现率随便取一个整数。折现率应该和利率、业务风险、债务成本和股权风险补偿有关。
- 误区四：终值增长率可以一直高于经济长期增速。长期稳定增长不能无限快于整个经济。
- 误区五：安全边际等于悲观。安全边际是承认自己可能估错，而不是故意吓自己。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课继续用 Microsoft 和 Adobe 做教学锚点，但不做买卖结论。先把第二十九课的自由现金流数据放进 DCF 语境。

| 对象 | 核验价格与股数 | 市值粗估 | 最新披露现金流口径 | 粗略自由现金流 | 粗略年化 FCF Yield |
| --- | ---: | ---: | --- | ---: | ---: |
| Microsoft | Nasdaq 2026-06-24 08:13 ET 价格 370.92 美元；Microsoft 2026-03-31 普通股 outstanding 约 7.429 billion | 约 2.756 万亿美元 | FY2026 前三季度经营现金流 1,274.94 亿美元，additions to property and equipment 801.46 亿美元 | 前三季度约 473.48 亿美元 | 前三季度机械年化约 2.29% |
| Adobe | Nasdaq 2026-06-24 08:13 ET 价格 195.80 美元；Adobe 2026-06-11 普通股 outstanding 397.5 million | 约 778 亿美元 | FY2026 前六个月经营现金流 51.23 亿美元，purchases of property and equipment 0.95 亿美元 | 前六个月约 50.28 亿美元 | 半年机械年化约 12.92% |

这些数字只能作为课堂锚点。Microsoft 的高 AI/cloud 增长伴随高资本开支；Adobe 的现金转换更轻，但还要观察增长、竞争、non-GAAP 调整、回购和股数变化。

### 为什么重要

U.S. Treasury 2026-06-23 曲线显示 2 年期 4.16%、10 年期 4.50%、30 年期 4.94%。Federal Reserve 2026-06-17 声明维持 federal funds rate 目标区间在 3.50%-3.75%。

这对 DCF 很重要。折现率越高，未来现金流折回今天越小；终值又代表很远未来的现金流，所以对折现率特别敏感。高增长公司如果现金流主要在未来，估值对利率和长期增长假设更敏感。

### 一个零基础 DCF 小模型

假设一家虚拟公司明年自由现金流是 100，之后 5 年每年增长 5%，第 5 年后进入长期稳定阶段；折现率 9%，终值增长率 2.5%。

```text
第1-5年现金流现值合计：约 447.6
终值现值：约 1308.1
DCF 总值：约 1755.6
终值占比：约 74.5%
```

这张小模型说明一个核心事实：DCF 的大头常常不是前 5 年，而是终值。因此，终值增长率和折现率不能随便填。

### 本节采用的数据和来源

- Microsoft 经营现金流、资本开支、股数、现金和债务来自 SEC 8-K exhibit 与 10-Q；SEC submissions API 显示 Microsoft 最新财务披露包括 2026-04-29 10-Q 和 2026-04-29 8-K，之后较新的 2026-06-05 8-K 不替代季度财务表。
- Adobe 经营现金流、资本开支、回购、股数和 FY2026 EPS target 来自 2026-06-11 8-K exhibit 与 2026-06-15 10-Q；SEC submissions API 显示 2026-06-15 10-Q 是 Adobe 最新季度报告。
- 价格来自 Nasdaq quote API，课堂估算使用 2026-06-24 08:13 ET 抓取值。
- 利率来自 Federal Reserve 与 U.S. Treasury 官方页面。
- 终值公式和稳定增长边界参考 Damodaran 的 terminal value 教学笔记。

### 这些现实事件如何连接理论

DCF 把第二十九课的自由现金流继续往前推：先估未来现金流，再用利率和风险折回来。Microsoft 的案例提醒我们，高增长和高资本开支要一起看；Adobe 的案例提醒我们，高自由现金流收益率也不能跳过增长质量和竞争风险。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 财务披露制度、Nasdaq 市场价格、Federal Reserve 利率政策、U.S. Treasury 收益率曲线、公司 non-GAAP 披露边界。
- 已确认事实：Fed 最新声明维持目标区间在 3.50%-3.75%；Treasury 2026-06-23 10 年期利率为 4.50%；Microsoft 和 Adobe 的最新季度财务数据已在 SEC 可查。
- 市场可能如何传导：利率上行会抬高折现率，压低远期现金流现值；资本开支上升会压低短期自由现金流，但可能为未来增长铺路；如果未来增长兑现失败，终值假设会被市场下修。
- 仍需核验或观察：Microsoft AI 基础设施回报周期、Adobe 增长和 AI 竞争压力、后续利率路径、下一季现金流是否延续当前结构。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| DCF | 折现现金流 | 把未来现金流折回今天再加总 | 估值中最核心的现金流框架 |
| Present Value | 现值 | 未来一笔钱在今天相当于多少钱 | 解决不同时间现金流不能直接相加的问题 |
| Discount Rate | 折现率 | 把未来钱折回今天用的回报率 | 连接利率、风险和估值 |
| Terminal Value | 终值 | 预测期之后剩余现金流的价值 | 往往占 DCF 很大比例 |
| Margin of Safety | 安全边际 | 估值和价格之间留下的误差缓冲 | 承认模型和人都会估错 |
| FCFF | 公司自由现金流 | 债权人和股东共同可分享的经营现金流 | 常用于企业价值 DCF |
| Equity Value | 股权价值 | 公司价值扣掉净债务等之后属于股东的价值 | 最终要和股票市值或每股价值比较 |
| Stable Growth | 稳定增长 | 终值阶段的长期增长假设 | 不能长期高到脱离经济现实 |
| Cost of Capital | 资本成本 | 公司使用债务和股权资金的综合代价 | 是折现率的重要来源 |

## 回顾提示

- 学到本课前建议回顾：第 17 课 Capex 与自由现金流、第 27 课 EV/EBITDA、第 29 课自由现金流收益率。
- 本课哪些内容会在后续课程继续使用：WACC、股权风险溢价、情景分析、敏感性分析、估值区间和公司研究。
- 如果看不懂本课，可以先回到：第 29 课“自由现金流收益率、现金转换与估值质量入门”。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的自由现金流进入 DCF 前的第一步检查。
- 已确认事实：
  - Microsoft FY2026 前三季度经营现金流 1,274.94 亿美元，additions to property and equipment 801.46 亿美元，粗略自由现金流约 473.48 亿美元。
  - Adobe FY2026 前六个月经营现金流 51.23 亿美元，purchases of property and equipment 0.95 亿美元，粗略自由现金流约 50.28 亿美元。
  - Nasdaq quote API 在 2026-06-24 08:13 ET 显示 Microsoft 370.92 美元、Adobe 195.80 美元。
  - U.S. Treasury 2026-06-23 曲线显示 10 年期 4.50%。
- 来源日期和链接：见本课“来源”。
- 分析推理：DCF 会把自由现金流放到未来年份；Microsoft 的模型重点是高 Capex 未来能否转成现金回报，Adobe 的模型重点是现金转换和增长质量能否延续。
- 后续验证指标：下一季经营现金流、资本开支、收入增速、利润率、股数变化、回购执行、债务成本、10 年期 Treasury yield。

## 个人情境连接

- 对关注清单的启发：看公司估值时，不只问“现在几倍”，还要问“未来现金流从哪里来”。
- 对持仓或基金选择的启发：基金重仓公司如果现金流主要在远期，对利率和终值假设会更敏感。
- 对工作、收入、消费或风险管理的启发：个人职业选择也有 DCF 直觉。未来高收入如果要等很久且不确定，就不能和今天稳定收入机械比较。

## 结论边界

- 可以确定：DCF 的核心是未来现金流、折现率和终值；利率变化会影响折现率；终值假设对结果非常敏感。
- 不能确定：本课没有给出 Microsoft 或 Adobe 的真实内在价值；课堂模型不等于研究报告模型。
- 需要继续观察：利率路径、增长兑现、资本开支回报、竞争格局、现金流正常化。
- 不构成投资建议的原因：本课只解释估值方法和披露阅读框架，不判断任何证券是否值得买卖。

## 练习题

1. 为什么 5 年后的 100 元不能直接等于今天的 100 元？
2. DCF 中折现率上升，会怎样影响远期现金流的现值？
3. 为什么终值常常比前 5 年现金流更影响 DCF 结果？
4. 用 Microsoft 的例子解释：高增长为什么还要和高资本开支一起看？
5. 用 Adobe 的例子解释：高自由现金流收益率为什么仍然需要观察增长质量？

## 学习交接

- 本课已经完成：把自由现金流、现值、折现率、终值、企业价值和安全边际连接成 DCF 入门框架。
- 本课最重要的一句话：DCF 不是算出一个神奇价格，而是把未来现金流、风险和假设透明地摆出来。
- 需要复习的关键词：DCF、Present Value、Discount Rate、Terminal Value、Margin of Safety、FCFF、Equity Value、Stable Growth、Cost of Capital。
- 还不稳定、下次要回看的地方：终值占比很高，折现率和长期增长率的小变化会显著改变估值。
- 适合下次打开仓库先读的文件：`lessons/2026-06-24-lesson-31-margin-of-safety-scenario-sensitivity.md`

## 下节课安排

- 建议主题：第三十一课：安全边际、情景分析与敏感性分析入门。
- 学习目标：学会不用单点估值自欺欺人，而是把 DCF 变成估值区间和假设压力测试。
- 建议案例：继续使用 Microsoft 与 Adobe；用虚拟现金流模型展示折现率、终值增长率和 5 年增长率变化如何影响估值。
- 必须解释的关键词：Scenario Analysis、Sensitivity Analysis、Base Case、Bull Case、Bear Case、Valuation Range、Model Risk、Terminal Growth、Assumption Audit。
- 下节课开始前需要联网核验的数据：最新 Nasdaq 价格、Treasury 10 年期利率、目标公司最新 SEC 披露、资本开支、经营现金流、股数和回购情况。

## 来源

- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- Microsoft Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/msft-20260331.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
- Nasdaq ADBE quote API: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606
- Aswath Damodaran, Stern/NYU terminal value note: https://pages.stern.nyu.edu/~adamodar/pdfiles/eqnotes/dcfstabl.pdf
