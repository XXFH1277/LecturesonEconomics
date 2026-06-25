# 第三十二课：WACC、无风险利率、股权风险溢价与资本结构入门

## 基本信息

- 日期：2026-06-25
- 数据截至：2026-06-25 17:20（Asia/Shanghai）；利率采用 FRED / Federal Reserve H.15 2026-06-23 最新可得数据；Fed 政策采用 2026-06-17 FOMC statement；Microsoft 股价采用 Nasdaq quote API 2026-06-24 1:54 PM ET；公司财务采用 Microsoft 2026-04-29 Form 8-K exhibit 99.1 与 Adobe 2026-06-15 Form 10-Q；股权风险溢价采用 Damodaran / NYU 2026-01 数据作为教学估计。
- 主题：DCF 里的折现率从哪里来，为什么股权和债务要用不同的成本。
- 学习目标：理解 WACC、Risk-free Rate、Equity Risk Premium、Cost of Equity、Cost of Debt、Beta、Capital Structure、After-tax Cost of Debt 和 Market Value Weights，知道折现率不是随手填的数字。
- 相关资产：股票、公司债、国债收益率、公司财报、DCF、企业价值。
- 已核验来源（核心来源）：
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - FRED / Federal Reserve H.15, 2-Year Treasury Constant Maturity, 2026-06-23: https://fred.stlouisfed.org/series/DGS2
  - FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity, 2026-06-23: https://fred.stlouisfed.org/series/DGS10
  - Nasdaq MSFT quote API, retrieved 2026-06-25: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - SEC directory for Microsoft Form 10-Q filing package, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Aswath Damodaran, Country Default Spreads and Risk Premiums, last updated January 2026: https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/ctryprem.html

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第三十课和第三十一课已经学到：DCF 是把未来自由现金流折回今天。今天继续追问：

> 折现率到底从哪里来？为什么不能直接写 8%、9% 或 10%？

因为公司不是只用一种钱在经营。公司可能用股东的钱，也可能用债权人的钱。股东承担剩余风险，要求的回报通常更高；债权人先拿利息和本金，风险通常较低，但债务也会带来偿债压力。WACC 就是把这些资金来源按权重合成一个综合资本成本。

### 参考的教材式概念顺序

1. Risk-free Rate：先找“接近无信用风险”的基准利率。
2. Equity Risk Premium：再问投资股票要比无风险资产多要求多少补偿。
3. Beta：公司股票相对市场波动有多敏感。
4. Cost of Equity：股东要求的回报率。
5. Cost of Debt：债权人要求的利率或公司新借钱的成本。
6. Tax Shield：利息通常可以抵税，所以债务成本要看税后。
7. Capital Structure：股权和债务各占多少。
8. WACC：把股权成本和税后债务成本按市场价值权重加权。

### 核心概念

最小公式：

```text
Cost of Equity = Risk-free Rate + Beta x Equity Risk Premium

After-tax Cost of Debt = Pre-tax Cost of Debt x (1 - Tax Rate)

WACC = E / (D + E) x Cost of Equity + D / (D + E) x After-tax Cost of Debt
```

这里的 `E` 是股权市场价值，`D` 是债务市场价值或课堂近似债务价值。真正做研究时要尽量用市场价值权重，不要只用资产负债表上的账面值。

### 用自己的话解释

可以把公司想成一家需要不断投入机器、软件、人才和客户关系的店。老板自己出钱，承担最大不确定性，所以会要求更高回报；银行或债券投资者借钱给公司，先收利息，所以要求的回报通常低一些。WACC 就是在问：这家公司综合使用这些钱的最低“及格线”是多少。

如果公司项目的长期回报率低于 WACC，看起来增长了，实际可能是在消耗价值。如果项目回报率高于 WACC，增长才更可能创造价值。

### 常见误区

- 误区一：把国债利率直接当成公司折现率。国债利率只是起点，公司股权还要加风险补偿。
- 误区二：债务便宜，所以越多越好。债务便宜是因为债权人优先，但过多债务会增加违约、再融资和信用评级风险。
- 误区三：用历史平均利率替代当前利率。DCF 是对未来现金流折现，当前利率环境必须重新核验。
- 误区四：把账面股东权益当成股权价值。WACC 权重通常应看市场价值，不是会计账面数。
- 误区五：Beta、ERP 和税率都当成精确真相。它们都是估计值，必须做敏感性分析。

## 第二大板块：实时背景与市场传导

### 发生了什么

截至本课核验时，Fed 2026-06-17 FOMC statement 显示，委员会把 federal funds rate 目标区间维持在 3.50%-3.75%，并提到通胀仍高于 2% 目标。FRED / Federal Reserve H.15 显示 2026-06-23 的 2 年期 Treasury yield 为 4.16%，10 年期 Treasury yield 为 4.50%。

这些数据决定了 WACC 的第一层地基：无风险利率。课堂里常用 10 年期 Treasury yield 作为美元长期现金流折现的起点，但它不是唯一选择；如果现金流很短，可以看更短期限，如果现金流很长，也要观察更长期限和期限利差。

### 为什么重要

假设一家公司：

- 无风险利率：4.50%
- 股权风险溢价：4.46%（Damodaran 2026-01 对美国 ERP 的教学估计）
- Beta：1.0
- 税前债务成本：5.20%
- 税率：23%
- 股权权重：90%
- 债务权重：10%

那么：

```text
Cost of Equity = 4.50% + 1.0 x 4.46% = 8.96%
After-tax Cost of Debt = 5.20% x (1 - 23%) = 4.00%
WACC = 90% x 8.96% + 10% x 4.00% = 8.46%
```

如果 Beta 从 1.0 变成 1.2，股权成本变为 9.85%，WACC 也会被推高。估值里看似小小的 0.5 到 1 个百分点变化，可能会明显改变 DCF 结果。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Fed funds target range | 3.50%-3.75% | Federal Reserve, 2026-06-17 | 观察政策利率背景 |
| 2 年期 Treasury yield | 4.16% | FRED / H.15, 2026-06-23 | 观察短端利率 |
| 10 年期 Treasury yield | 4.50% | FRED / H.15, 2026-06-23 | 课堂无风险利率锚点 |
| Microsoft 股价 | 370.685 美元 | Nasdaq quote API, 2026-06-24 1:54 PM ET | 粗估股权市场价值 |
| Microsoft 普通股 outstanding | 7.429 billion | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 粗估市场权重 |
| Microsoft 现金、现金等价物和短期投资 | 782.72 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 观察净现金结构 |
| Microsoft 当前债务 + 长期债务 | 402.62 亿美元 | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 观察债务权重 |
| 美国 ERP 教学估计 | 4.46% | Damodaran / NYU, 2026-01 | 解释股权风险溢价 |

### Microsoft 的最小 WACC 直觉

Microsoft 2026-03-31 普通股 outstanding 约 7.429 billion。Nasdaq quote API 在 2026-06-24 1:54 PM ET 显示 MSFT last sale price 为 370.685 美元。课堂粗估股权市场价值：

```text
7.429 billion x 370.685 美元 ≈ 2.754 万亿美元
```

Microsoft 同一披露中，现金、现金等价物和短期投资合计 782.72 亿美元；current portion of long-term debt 为 88.39 亿美元，long-term debt 为 314.23 亿美元，合计约 402.62 亿美元。

这意味着在课堂粗估里，Microsoft 的股权市场价值远大于债务账面值。它的 WACC 通常会更接近股权成本，而不是债务成本。注意：这不是说债务不重要，而是说在当前资本结构下，股权权重对综合资本成本更有影响。

### 这些现实事件如何连接理论

- Treasury yield 上升：无风险利率上升，股权成本和债务成本的起点都可能上升。
- Fed 维持高于零的政策利率：短端融资成本不会凭空回到零利率时代。
- 公司股价变化：股权市场价值变化，WACC 权重也会变化。
- 公司借债或回购：资本结构变化，可能改变债务权重和股权权重。
- AI 资本开支上升：项目回报必须超过更高的资本成本，才是真正创造价值。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 货币政策、U.S. Treasury 收益率曲线、SEC 披露制度、Nasdaq 市场数据、公司融资与回购规则。
- 已确认事实：Fed 2026-06-17 维持目标区间 3.50%-3.75%；FRED / H.15 显示 2026-06-23 的 10 年期 Treasury yield 为 4.50%；Microsoft 最新课堂使用的季度财务锚点来自 SEC 文件。
- 市场可能如何传导：政策利率和国债收益率影响无风险利率；信用利差影响债务成本；股权风险偏好影响 ERP；公司资本结构影响 WACC。
- 仍需核验或观察：下一次 FOMC、后续 Treasury 曲线、Microsoft 与 Adobe 下一季债务和现金、信用利差、回购、股数变化，以及新的资本开支 guidance。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| WACC | 加权平均资本成本 | 公司使用股权和债务资金的综合成本 | DCF 中常用的折现率基础 |
| Risk-free Rate | 无风险利率 | 接近无信用风险的基准收益率 | 所有风险资产定价的起点 |
| Equity Risk Premium | 股权风险溢价 | 投资股票相对无风险资产要求的额外补偿 | 决定股权成本高低 |
| Cost of Equity | 股权成本 | 股东要求的回报率 | 股权现金流风险更高，通常高于债务成本 |
| Cost of Debt | 债务成本 | 公司借钱要付出的利率或债券收益率 | 影响税后债务成本和 WACC |
| Beta | 贝塔 | 股票相对市场整体波动的敏感度 | CAPM 里衡量系统性风险 |
| Capital Structure | 资本结构 | 股权和债务在融资中的比例 | 决定 WACC 权重和财务风险 |
| Tax Shield | 税盾 | 利息抵税带来的税后成本下降 | 解释为什么债务成本要乘以 `(1 - 税率)` |
| Market Value Weights | 市场价值权重 | 用市场价值计算股权和债务比例 | 比账面权重更接近投资者要求回报 |
| CAPM | 资本资产定价模型 | 用无风险利率、Beta 和 ERP 估算股权成本 | 是入门估算 Cost of Equity 的常用框架 |

## 回顾提示

- 学到本课前建议回顾：第 30 课 DCF、折现率与终值；第 31 课安全边际、情景分析与敏感性分析。
- 本课哪些内容会在后续课程继续使用：信用利差、债务税盾、ROIC、经济利润、资本配置和回购质量。
- 如果看不懂本课，可以先回到：第 15 课“估值倍数、利率与重新定价入门”和第 30 课“DCF、折现率、终值与安全边际入门”。

## 案例拆解

- 案例对象：Microsoft 的资本结构如何影响 WACC 直觉。
- 已确认事实：
  - Microsoft 2026-03-31 现金、现金等价物和短期投资为 782.72 亿美元。
  - Microsoft current portion of long-term debt 为 88.39 亿美元，long-term debt 为 314.23 亿美元。
  - Microsoft 普通股 outstanding 约 7.429 billion。
  - Nasdaq quote API 在 2026-06-24 1:54 PM ET 显示 MSFT 价格为 370.685 美元。
  - FRED / H.15 显示 2026-06-23 的 10 年期 Treasury yield 为 4.50%。
- 来源日期和链接：见本课“来源”。
- 分析推理：Microsoft 的课堂粗估股权市场价值远大于债务账面值，所以 WACC 更受股权成本影响；但如果未来大量发债、利率上行或信用利差扩大，债务成本和资本结构仍会变得更重要。
- 后续验证指标：下一季股数、现金、短期投资、债务、经营现金流、资本开支、回购、Treasury yield、公司债利差和管理层 capex guidance。

## 个人情境连接

- 对关注清单的启发：看估值模型时，先问折现率的来源，而不是只看目标价。
- 对持仓或基金选择的启发：重仓成长股的基金对股权成本和无风险利率更敏感；重仓高负债公司的基金还要看债务成本和再融资风险。
- 对工作、收入、消费或风险管理的启发：个人也有“资本成本”。如果借钱投资、买房或创业，债务成本、收入稳定性和安全垫要一起看。

## 结论边界

- 可以确定：WACC 把股权成本和税后债务成本按权重合成；无风险利率、股权风险溢价、Beta、债务成本、税率和资本结构都会影响折现率。
- 不能确定：本课没有给出 Microsoft、Adobe 或任何公司的真实 WACC；Beta、ERP 和债务市场收益率都需要在正式研究时重新核验。
- 需要继续观察：利率路径、信用利差、公司发债和回购、资本开支回报、税率变化和市场风险偏好。
- 不构成投资建议的原因：本课只训练折现率的来源拆解，不判断任何证券是否值得买卖。

## 练习题

1. 为什么 WACC 不能只用 10 年期 Treasury yield 代替？
2. 如果无风险利率从 4.50% 上升到 5.00%，在其他假设不变时，Cost of Equity 会怎样变化？
3. 为什么债务成本通常低于股权成本，但过多债务仍然危险？
4. 用 `Cost of Equity = Risk-free Rate + Beta x ERP` 计算：无风险利率 4.50%、ERP 4.46%、Beta 1.2 时，股权成本是多少？
5. 为什么 Microsoft 这种股权市场价值远大于债务的公司，WACC 更接近股权成本？

## 学习交接

- 本课已经完成：把 DCF 折现率拆成无风险利率、股权风险溢价、Beta、股权成本、债务成本、税盾和资本结构权重。
- 本课最重要的一句话：折现率不是模型里的装饰数字，而是公司使用资本的最低回报要求。
- 需要复习的关键词：WACC、Risk-free Rate、Equity Risk Premium、Cost of Equity、Cost of Debt、Beta、Capital Structure、After-tax Cost of Debt、Tax Shield、Market Value Weights。
- 还不稳定、下次要回看的地方：债务为什么能降低税后资本成本，却同时带来信用利差、再融资和违约风险。
- 适合下次打开仓库先读的文件：`lessons/2026-06-25-lesson-33-credit-spread-tax-shield-debt-risk.md`

## 下节课安排

- 建议主题：第三十三课：信用利差、税盾与债务风险入门。
- 学习目标：理解为什么债务不是“越便宜越好”，学会把税盾、信用利差、期限结构、再融资风险、契约限制和评级变化放进同一张图。
- 建议案例：使用 Adobe 的 senior notes、commercial paper、interest expense、effective tax rate，以及 FRED / ICE BofA investment grade corporate yield 和 OAS。
- 必须解释的关键词：Credit Spread、Option-Adjusted Spread、Investment Grade、High Yield、Tax Shield、Refinancing Risk、Maturity Wall、Covenant、Default Risk、Interest Coverage。
- 下节课开始前需要联网核验的数据：FRED / ICE BofA corporate yield、OAS、BBB OAS、Treasury curve、Adobe 最新债务、利息费用、商业票据、循环信贷额度和税率。

## 来源

- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- FRED / Federal Reserve H.15, 2-Year Treasury Constant Maturity: https://fred.stlouisfed.org/series/DGS2
- FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity: https://fred.stlouisfed.org/series/DGS10
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- SEC directory for Microsoft Form 10-Q filing package, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Aswath Damodaran, Country Default Spreads and Risk Premiums, January 2026: https://pages.stern.nyu.edu/~adamodar/New_Home_Page/datafile/ctryprem.html
