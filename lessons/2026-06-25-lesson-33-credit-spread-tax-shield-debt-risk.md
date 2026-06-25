# 第三十三课：信用利差、税盾与债务风险入门

## 基本信息

- 日期：2026-06-25
- 数据截至：2026-06-25 17:20（Asia/Shanghai）；利率和信用利差采用 FRED / Federal Reserve / ICE BofA 2026-06-23 最新可得数据；Fed 政策采用 2026-06-17 FOMC statement；Adobe 财务采用 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；Microsoft 对照数据采用 2026-04-29 Form 8-K exhibit 99.1。
- 主题：为什么债务能降低税后资本成本，却也会带来信用利差、再融资和违约风险。
- 学习目标：理解 Credit Spread、Option-Adjusted Spread、Investment Grade、High Yield、Tax Shield、Refinancing Risk、Maturity Wall、Covenant、Default Risk 和 Interest Coverage，把“便宜债务”和“债务风险”同时看见。
- 相关资产：公司债、股票、国债、信用利差、公司财报、WACC、现金流。
- 已核验来源（核心来源）：
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity, 2026-06-23: https://fred.stlouisfed.org/series/DGS10
  - FRED / ICE BofA US Corporate Index Effective Yield, 2026-06-23: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
  - FRED / ICE BofA US Corporate Index Option-Adjusted Spread, 2026-06-23: https://fred.stlouisfed.org/series/BAMLC0A0CM
  - FRED / ICE BofA BBB US Corporate Index Option-Adjusted Spread, 2026-06-23: https://fred.stlouisfed.org/series/BAMLC0A4CBBB
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第三十二课学了 WACC，其中债务成本要乘以 `(1 - 税率)`。今天继续问：

> 如果债务税后成本比股权成本低，为什么公司不尽量多借钱？

因为债务不是免费午餐。它会带来固定还本付息义务。生意顺利时，债务可以放大股东回报；生意变差或利率上升时，债务也会放大压力。信用利差就是市场对这种压力要求的额外补偿。

### 参考的教材式概念顺序

1. Treasury yield：先看无信用风险基准。
2. Credit Spread：公司债相对国债多付多少利差。
3. Cost of Debt：国债利率加信用利差，或者用公司现有债务利率观察。
4. Tax Shield：利息抵税降低税后债务成本。
5. Refinancing Risk：旧债到期时，能不能以可承受成本借新钱。
6. Maturity Wall：集中到期的债务会形成现金流压力。
7. Covenant：债务契约可能限制公司行为。
8. Default Risk：公司无法履约时，股东和债权人的风险顺序不同。

### 核心概念

最小公式：

```text
Pre-tax Cost of Debt ≈ Treasury Yield + Credit Spread

After-tax Cost of Debt = Pre-tax Cost of Debt x (1 - Tax Rate)

Interest Tax Shield ≈ Interest Expense x Tax Rate
```

但要注意：这些是课堂近似。真实公司会有不同期限、不同票息、不同币种、固定和浮动利率、利率互换、税务辖区和契约限制。

### 用自己的话解释

国债像一把尺子，公司债是在这把尺子上加风险补偿。公司越稳，市场要求的加价越低；公司越不稳，市场要求的加价越高。这个加价就是信用利差。

税盾像优惠券。公司付利息时，税前利润减少，税款可能减少，所以债务的税后成本低于票面利率。但如果公司利润不稳定、税务规则变化、债务太多或现金流不足，优惠券不能抵消破产和再融资风险。

### 常见误区

- 误区一：把票面利率当成今天的新债成本。新融资要看当前市场收益率和信用利差。
- 误区二：只看利息低，不看本金到期。债务到期集中时，压力可能突然出现。
- 误区三：把税盾当确定收益。税盾取决于公司是否有应税利润、利息能否抵扣、税法和辖区规则。
- 误区四：只看总债务，不看现金和短期投资。净债务和流动性同样重要。
- 误区五：把 investment grade 当成没有风险。投资级只是相对高信用等级，不代表不会跌价、不会利差扩大或不会被降级。

## 第二大板块：实时背景与市场传导

### 发生了什么

FRED / ICE BofA 显示，2026-06-23：

- ICE BofA US Corporate Index Effective Yield 为 5.20%。
- ICE BofA US Corporate Index Option-Adjusted Spread 为 0.74%。
- ICE BofA BBB US Corporate Index Option-Adjusted Spread 为 0.93%。

同日，FRED / H.15 显示 10 年期 Treasury yield 为 4.50%。这说明，当时投资级公司债的收益率不只是 Treasury yield，还包含信用利差、期限结构、债券选择权和市场流动性等因素。Fed 2026-06-17 statement 维持目标区间在 3.50%-3.75%，并指出通胀仍高于 2% 目标，这也是债务融资成本的重要背景。

### 为什么重要

如果课堂上用 10 年期 Treasury yield 4.50% 加 BBB OAS 0.93% 近似 BBB 债务成本：

```text
税前债务成本 ≈ 4.50% + 0.93% = 5.43%
若税率为 23%：
税后债务成本 ≈ 5.43% x (1 - 23%) = 4.18%
```

如果信用利差从 0.93% 扩到 1.80%，即使 Treasury yield 不变，税前债务成本也会从 5.43% 变成 6.30%。这会影响：

- 新发债成本。
- 旧债再融资成本。
- WACC。
- 公司回购、并购和资本开支的可承受程度。
- 股票估值中对未来现金流的折现率。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| 10 年期 Treasury yield | 4.50% | FRED / H.15, 2026-06-23 | 无风险利率锚点 |
| IG corporate effective yield | 5.20% | FRED / ICE BofA, 2026-06-23 | 投资级债券市场收益率观察 |
| IG corporate OAS | 0.74% | FRED / ICE BofA, 2026-06-23 | 广义投资级信用利差 |
| BBB corporate OAS | 0.93% | FRED / ICE BofA, 2026-06-23 | 低档投资级信用利差 |
| Adobe senior notes outstanding | 61.50 亿美元 | Adobe 2026-06-15 Form 10-Q | 公司债务结构案例 |
| Adobe commercial paper outstanding | 5.00 亿美元，carrying value 4.94 亿美元 | Adobe 2026-06-15 Form 10-Q | 短期融资案例 |
| Adobe revolving credit facility | 15 亿美元，未提款 | Adobe 2026-06-15 Form 10-Q | 流动性后备案例 |
| Adobe six-month interest expense | 1.28 亿美元 | Adobe 2026-06-15 Form 10-Q | 税盾和利息覆盖案例 |
| Adobe six-month effective tax rate | 23% | Adobe 2026-06-15 Form 10-Q | 税盾近似输入 |

### Adobe 的债务和税盾案例

Adobe 2026-06-15 Form 10-Q 披露，截至 2026-05-29：

- senior notes outstanding at par 为 61.50 亿美元。
- current portion of senior notes at par 为 13.50 亿美元。
- commercial paper outstanding 为 5.00 亿美元，carrying value 为 4.94 亿美元，weighted average interest rate 为 3.76%。
- 15 亿美元 senior unsecured revolving credit facility 未提款。
- 六个月 interest expense 为 1.28 亿美元。
- 六个月 effective tax rate 为 23%。

课堂近似税盾：

```text
六个月利息费用 1.28 亿美元 x 23% ≈ 0.294 亿美元
```

这只说明“如果利息可抵税，税盾可能降低税后债务成本”。它不是 Adobe 的正式税务结论，因为实际税务会受辖区、扣除限制、一次性项目和税法变化影响。

### 这些现实事件如何连接理论

- 信用利差压缩：公司发债看起来更便宜，回购、并购和投资更容易被融资支持。
- 信用利差扩大：新债成本上升，旧债再融资压力上升，股权投资者可能要求更高回报。
- 短期利率维持高位：commercial paper、浮动利率债务和循环信贷成本会更敏感。
- 债务到期集中：即使公司长期盈利不错，也可能在某个年份遇到现金流和市场窗口压力。
- 税率变化：税盾大小会改变，WACC 中税后债务成本也会改变。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：Federal Reserve 利率政策、FRED / ICE BofA 信用市场数据、SEC 披露制度、公司债契约、税法和全球最低税规则。
- 已确认事实：FRED / ICE BofA 2026-06-23 的 IG corporate effective yield 为 5.20%，IG OAS 为 0.74%，BBB OAS 为 0.93%；Adobe 截至 2026-05-29 有 61.50 亿美元 senior notes、5.00 亿美元 commercial paper outstanding、15 亿美元未提款循环信贷额度。
- 市场可能如何传导：国债利率和信用利差影响公司债成本；债务成本影响 WACC；WACC 影响估值；再融资环境影响回购、并购和资本开支。
- 仍需核验或观察：Adobe 下一季 debt、commercial paper、interest expense、credit facility、effective tax rate；投资级和 BBB OAS 是否继续扩大；Fed 后续政策路径。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Credit Spread | 信用利差 | 公司债收益率相对国债多出来的部分 | 补偿公司违约、降级和流动性风险 |
| Option-Adjusted Spread | 期权调整利差 | 扣除债券内含选择权影响后的利差 | 更适合比较带赎回权等债券 |
| Investment Grade | 投资级 | 信用评级较高的一类债券 | 借钱成本通常低于高收益债 |
| High Yield | 高收益债 | 信用评级较低、收益率较高的债券 | 收益高但违约和价格波动风险更高 |
| Tax Shield | 税盾 | 利息抵税带来的税后成本下降 | 解释债务为什么可能降低 WACC |
| Refinancing Risk | 再融资风险 | 旧债到期时新债借不到或成本太高 | 高利率环境下尤其重要 |
| Maturity Wall | 到期墙 | 大量债务集中到期 | 可能制造现金流压力 |
| Covenant | 债务契约 | 债权人给借款人设的限制条件 | 会影响回购、分红、并购和再融资 |
| Default Risk | 违约风险 | 不能按约还本付息的风险 | 决定债权人和股东的风险顺序 |
| Interest Coverage | 利息保障倍数 | 利润或现金流覆盖利息费用的倍数 | 判断债务压力是否可承受 |

## 回顾提示

- 学到本课前建议回顾：第 32 课 WACC、无风险利率、股权风险溢价与资本结构。
- 本课哪些内容会在后续课程继续使用：ROIC 与 WACC 的比较、经济利润、回购是否创造价值、并购融资风险、公司债和基金持仓风险。
- 如果看不懂本课，可以先回到：第 5 课“债券、利率和信用”和第 13 课“资本配置入门”。

## 案例拆解

- 案例对象：Adobe 债务结构、税盾和信用利差。
- 已确认事实：
  - Adobe 2026-05-29 senior notes outstanding at par 为 61.50 亿美元。
  - Adobe commercial paper outstanding 为 5.00 亿美元，weighted average interest rate 为 3.76%。
  - Adobe 15 亿美元 senior unsecured revolving credit facility 未提款。
  - Adobe 六个月 interest expense 为 1.28 亿美元，effective tax rate 为 23%。
  - FRED / ICE BofA 2026-06-23 的 IG corporate effective yield 为 5.20%，IG OAS 为 0.74%，BBB OAS 为 0.93%。
- 来源日期和链接：见本课“来源”。
- 分析推理：Adobe 的现有债务包含早期低票息 notes、较新 notes、commercial paper 和利率互换影响；用历史利息费用可以观察当前负担，用 FRED / ICE BofA 可以观察市场新融资背景，两者不能机械混为一个数字。
- 后续验证指标：债务到期表、commercial paper 余额、interest expense、operating cash flow、free cash flow、credit spread、Treasury yield、有效税率、回购规模和管理层融资说明。

## 个人情境连接

- 对关注清单的启发：看高负债公司时，不只看 P/E，还要看债务到期、利息费用、信用利差和现金流。
- 对持仓或基金选择的启发：信用利差扩大时，重仓公司债或高负债股票的基金可能同时受到债券价格和股票估值压力。
- 对工作、收入、消费或风险管理的启发：个人贷款也类似。低利率时期借的钱，到期或重定价时可能面对完全不同的利率环境。

## 结论边界

- 可以确定：债务有税盾，但也带来固定偿付义务；信用利差是市场对公司信用风险的补偿；再融资风险会随利率和市场情绪变化。
- 不能确定：本课没有判断 Adobe 债务是否过高，也没有给出公司债或股票买卖建议；FRED / ICE BofA 指数是市场指数，不等于 Adobe 单只债券收益率。
- 需要继续观察：债务到期、利差变化、短期融资成本、现金流稳定性、税率变化、评级变化和公司资本配置。
- 不构成投资建议的原因：本课只解释债务风险和税盾框架，不推荐买入或卖出任何证券。

## 练习题

1. 为什么税后债务成本要用 `税前债务成本 x (1 - 税率)`？
2. 如果 10 年期 Treasury yield 是 4.50%，信用利差是 1.50%，税率是 21%，税后债务成本是多少？
3. 为什么投资级债券仍然可能在利率上行或利差扩大时亏钱？
4. Adobe 的 six-month interest expense 为 1.28 亿美元，税率 23%。课堂近似税盾是多少？这个数为什么不能当成正式税务结论？
5. 一家公司有大量现金但也有大量债务时，为什么要同时看总债务、净债务和到期结构？

## 学习交接

- 本课已经完成：把债务从 WACC 的一个低成本输入，推进到信用利差、税盾、到期墙、再融资风险、契约限制和违约风险。
- 本课最重要的一句话：债务的优势来自税盾和较低成本，债务的危险来自固定义务和市场窗口不受公司控制。
- 需要复习的关键词：Credit Spread、Option-Adjusted Spread、Investment Grade、High Yield、Tax Shield、Refinancing Risk、Maturity Wall、Covenant、Default Risk、Interest Coverage。
- 还不稳定、下次要回看的地方：公司真正创造价值，不是因为能借到便宜钱，而是投资回报率能持续高于资本成本。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第三十四课：ROIC、ROE、投入资本与经济利润入门。
- 学习目标：理解公司回报率如何和 WACC 比较，为什么“增长”只有在回报率超过资本成本时才更可能创造价值。
- 建议案例：继续使用 Microsoft 与 Adobe；用 NOPAT、投入资本、经营利润、税率、现金、债务和资本开支做零基础拆解。
- 必须解释的关键词：ROIC、ROE、Invested Capital、NOPAT、Economic Profit、Spread、Goodwill、Operating Assets、Capital Intensity、Reinvestment。
- 下节课开始前需要联网核验的数据：Microsoft 与 Adobe 最新 SEC 披露、经营利润、税率、现金、债务、商誉、股东权益、资本开支、经营现金流、股价和 Treasury / WACC 背景。

## 来源

- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- FRED / Federal Reserve H.15, 10-Year Treasury Constant Maturity: https://fred.stlouisfed.org/series/DGS10
- FRED / ICE BofA US Corporate Index Effective Yield: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
- FRED / ICE BofA US Corporate Index Option-Adjusted Spread: https://fred.stlouisfed.org/series/BAMLC0A0CM
- FRED / ICE BofA BBB US Corporate Index Option-Adjusted Spread: https://fred.stlouisfed.org/series/BAMLC0A4CBBB
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
