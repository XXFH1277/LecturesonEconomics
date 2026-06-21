# 第二十五课：EPS、稀释、回购与股本数量入门

## 基本信息

- 日期：2026-06-21
- 数据截至：2026-06-21 20:06（Asia/Shanghai）；公司数据采用截至本次写作时 SEC 或公司 IR 已披露的最新季度报告；利率背景采用 2026-06-18 U.S. Treasury 和 2026-06-17 Federal Reserve。
- 主题：为什么净利润还要除以股数，回购和股权激励怎样影响每股收益。
- 学习目标：理解 EPS、基本股数、稀释股数、回购、库存股和股权激励，知道“公司赚的钱”和“每股分到的利润”不是同一个观察角度。
- 相关资产：股票、公司财报、股权激励、股票回购、资本配置、利率。
- 核心来源：
  - Microsoft FY2026 Q3 Form 10-Q filing detail, accession `0001193125-26-191507`, period 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
  - Microsoft FY2026 Q3 income statement XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
  - Microsoft FY2026 Q3 balance sheet parenthetical XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R5.htm
  - Microsoft FY2026 Q3 cash flow statement XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
  - Adobe FY2026 Q2 Form 10-Q PDF, period 2026-05-29: https://www.adobe.com/cc-shared/assets/investor-relations/pdfs/adbe-10q-q226-final.pdf
  - Adobe Announces New $25 Billion Stock Repurchase Program, 2026-04-21: https://www.adobe.com/cc-shared/assets/investor-relations/pdfs/b465t3rw34.pdf
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十四课讲到净利润。今天继续问：

> 如果两家公司净利润一样，为什么每股收益可能不一样？

因为股东拥有的是“每一股”的权益。公司整体赚了多少钱是一层问题；这些利润要分摊到多少股上，是另一层问题。股数越多，每股分到的利润越薄；股数减少，每股指标可能提高。

### 参考的教材式概念顺序

1. 公司先算出净利润。
2. 净利润除以加权平均普通股数，得到基本 EPS。
3. 如果存在期权、RSU、可转债等潜在普通股，还要计算稀释 EPS。
4. 股权激励可能增加潜在股数或带来未来稀释。
5. 回购会减少流通股或抵消股权激励稀释。
6. EPS 提高不一定等于业务变强，要同时看净利润、股数、现金流和回购价格。

### 核心概念

- EPS（Earnings Per Share，每股收益）：净利润除以股份数量后的每股利润。
- 基本 EPS（Basic EPS）：用基本加权平均股数计算。
- 稀释 EPS（Diluted EPS）：假设潜在普通股转成普通股后计算，通常更保守。
- 加权平均股数（Weighted Average Shares）：报告期内按时间加权的平均股数，不等于某一天的期末股数。
- 稀释（Dilution）：新增股份或潜在股份让每股权益被摊薄。
- 股票回购（Share Repurchase）：公司用现金买回自己的股票。
- 库存股（Treasury Stock）：公司回购后持有、通常不算流通在外的股票。
- 股权激励（Stock-based Compensation, SBC）：用股票或股票相关奖励支付员工薪酬。

### 用自己的话解释

最简公式是：

```text
EPS = 净利润 / 加权平均股数
```

但是初学者要再加一句：

```text
EPS 变化 = 净利润变化 + 股数变化共同作用
```

如果净利润没变，但公司回购股票让股数下降，EPS 可能上升。反过来，如果公司发很多股票做并购或股权激励，股数上升，EPS 可能被稀释。

### 常见误区

- 误区一：EPS 上升一定代表主业变强。EPS 可能来自回购减少股数。
- 误区二：回购一定对股东有利。回购价格、资金来源和机会成本都重要。
- 误区三：股权激励是免费的。SBC 是费用，也可能带来稀释。
- 误区四：基本 EPS 足够。稀释 EPS 更能提醒潜在股份的影响。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课用 Microsoft 和 Adobe 最新披露做对照。

| 公司 | 最新报告 | 单季净利润 | 基本 EPS | 稀释 EPS | 基本加权股数 | 稀释加权股数 | 入门观察 |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- |
| Microsoft | FY2026 Q3 10-Q | 317.78 亿美元 | 4.28 美元 | 4.27 美元 | 74.26 亿股 | 74.45 亿股 | 稀释股数略高于基本股数 |
| Adobe | FY2026 Q2 10-Q | 17.12 亿美元 | 4.26 美元 | 4.25 美元 | 4.02 亿股 | 4.02 亿股 | 每股指标受较小股本基数影响更明显 |

再看回购和股权激励：

| 公司 | 回购和股数事实 | 股权激励事实 | 课堂含义 |
| --- | --- | --- | --- |
| Microsoft | FY2026 Q3 单季回购 46.27 亿美元；2026-03-31 普通股流通 74.29 亿股，低于 2025-06-30 的 74.34 亿股 | FY2026 Q3 单季 SBC 30.81 亿美元 | 大公司也要同时看回购、SBC 和股数变化 |
| Adobe | FY2026 Q2 单季回购 21.30 亿美元；2026-05-29 流通股 3.99 亿股，低于 2025-11-28 的 4.13 亿股 | FY2026 Q2 股东权益表列示 SBC 5.34 亿美元；六个月 SBC 10.43 亿美元 | 回购明显减少股数，也在抵消股权激励稀释 |

Adobe 还在 2026-04-21 宣布新的 250 亿美元股票回购授权，有效期至 2030-04-30。公司说明该计划可用于向股东返还资本、降低股票发行带来的稀释并随时间减少股数。这里的重点不是判断回购好坏，而是看到公司资本配置如何进入每股指标。

### 为什么重要

Federal Reserve 2026-06-17 维持联邦基金目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-18 的 2 年期、10 年期和 30 年期收益率分别为 4.19%、4.46% 和 4.90%。

利率环境会影响回购判断：

- 如果现金收益率较高，公司回购的机会成本也更高。
- 如果公司借债回购，利息费用可能侵蚀净利润。
- 如果公司现金流强，回购可能是资本配置的一部分。
- 如果公司用回购只是抵消 SBC 稀释，股东要看实际流通股是否减少。

### 本节采用的数据和来源

- Microsoft SEC filing detail、income statement、balance sheet parenthetical 和 cash flow statement，用于核验 EPS、股数、回购、SBC 和期末流通股。
- Adobe FY2026 Q2 Form 10-Q PDF，用于核验 EPS、股数、回购、SBC、库存股和现金流。
- Adobe 2026-04-21 回购授权新闻稿，用于核验 250 亿美元回购授权和期限。
- Federal Reserve 与 U.S. Treasury，用于核验利率背景。

### 这些现实事件如何连接理论

净利润告诉我们公司整体赚了多少钱；EPS 告诉我们每股摊到多少。Microsoft 和 Adobe 都有回购和股权激励，但股数基数、回购规模、SBC 比例不同。因此读 EPS 时，不能只看一个每股数字，而要追问它来自净利润增长，还是来自股数变化。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、董事会回购授权、交易规则、税收制度、股权激励会计、利率政策。
- 已确认事实：Adobe 已披露 FY2026 Q2 10-Q 和 2026-04-21 新回购授权；Microsoft FY2026 Q3 10-Q 已在 SEC 披露；Fed 和 Treasury 已发布最新利率背景。
- 市场可能如何传导：回购可能提高 EPS 或减少稀释，但会消耗现金；高利率提高现金和债务的机会成本；SBC 既是人才激励工具，也是每股权益稀释来源。
- 仍需核验或观察：后续季度实际回购价格、回购金额、SBC、流通股是否继续下降，以及回购是否影响研发和长期投入。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| EPS | 每股收益 | 每一股分摊到的净利润 | 是常见估值倍数 P/E 的分母 |
| Basic EPS | 基本每股收益 | 用基本加权平均股数算 EPS | 反映当前普通股分摊结果 |
| Diluted EPS | 稀释每股收益 | 假设潜在股份转成普通股后的 EPS | 更保守地看每股利润 |
| Weighted Average Shares | 加权平均股数 | 报告期内按时间加权的平均股数 | EPS 计算不用单日股数 |
| Dilution | 稀释 | 股数增加后每股权益变薄 | 影响老股东每股拥有的比例 |
| Share Repurchase | 股票回购 | 公司买回自己的股票 | 可能减少股数，也消耗现金 |
| Treasury Stock | 库存股 | 公司回购后持有的股票 | 通常不算流通股 |
| Stock-based Compensation | 股权激励费用 | 用股票或股票奖励支付员工 | 会影响费用和潜在稀释 |

## 回顾提示

- 学到本课前建议回顾：第 13 课资本配置、第 15 课估值倍数、第 24 课净利润。
- 本课哪些内容会在后续课程继续使用：P/E、PEG、自由现金流收益率、分红、回购质量、股权稀释和估值。
- 如果看不懂本课，可以先回到：第 24 课“净利润、利息、税费与非经营项目入门”。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的 EPS、回购和股数变化。
- 已确认事实：
  - Microsoft FY2026 Q3 单季净利润 317.78 亿美元，基本 EPS 4.28 美元，稀释 EPS 4.27 美元，稀释加权股数 74.45 亿股，单季回购 46.27 亿美元，单季 SBC 30.81 亿美元。
  - Adobe FY2026 Q2 单季净利润 17.12 亿美元，基本 EPS 4.26 美元，稀释 EPS 4.25 美元，单季回购 21.30 亿美元，六个月回购 46.30 亿美元，六个月 SBC 10.43 亿美元。
  - Adobe 2026-04-21 宣布新的 250 亿美元股票回购授权，有效期至 2030-04-30。
- 来源日期和链接：Microsoft SEC filing detail 显示 2026-04-29 filing date、2026-03-31 period；Adobe Form 10-Q 显示季度截至 2026-05-29；Adobe 回购授权新闻稿日期为 2026-04-21。
- 分析推理：EPS 提高可能来自利润增长，也可能来自股数下降。回购和 SBC 要放在一起看，才知道每股权益是否真正被强化。
- 后续验证指标：净利润增速、稀释股数、期末流通股、SBC、实际回购金额、回购价格、经营现金流和资本开支。

## 个人情境连接

- 对关注清单的启发：看 EPS 时顺手看股数，不要只看每股结果。
- 对持仓或基金选择的启发：基金重仓回购型公司时，要看回购是否由现金流支持，是否只是抵消股权激励。
- 对工作、收入、消费或风险管理的启发：股权激励对员工可能是收入来源，但对股东是费用和潜在稀释。站在不同角色，看到的意义不同。

## 结论边界

- 可以确定：EPS 同时受净利润和股数影响；回购、股权激励和潜在股份会改变每股指标。
- 不能确定：回购公告本身不等于一定会创造价值，最终要看执行价格、现金流、机会成本和业务投资需求。
- 需要继续观察：Adobe 新回购授权的实际执行节奏，Microsoft 和 Adobe 后续股数、SBC 和自由现金流是否匹配。
- 不构成投资建议的原因：本课只解释每股指标和资本配置机制，不判断任何股票是否值得买卖。

## 练习题

1. 用自己的话解释：为什么净利润一样的公司，EPS 可能不同？
2. 如果一家公司的 EPS 上升但净利润没有上升，你会先检查什么？
3. 股票回购可能怎样抵消股权激励稀释？为什么这不一定等于创造价值？
4. 为什么看回购时要同时看经营现金流、债务和利率？

## 学习交接

- 本课已经完成：把净利润、基本 EPS、稀释 EPS、股数、回购、库存股和股权激励连接起来。
- 本课最重要的一句话：EPS 不是只由利润决定，也由分母里的股数决定。
- 需要复习的关键词：EPS、Basic EPS、Diluted EPS、Weighted Average Shares、Dilution、Share Repurchase、Treasury Stock、SBC。
- 还不稳定、下次要回看的地方：回购要看执行和机会成本，不能把授权金额等同于已经完成的股东回报。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第二十六课：P/E、市盈率、EPS 预期与估值倍数入门。
- 学习目标：理解为什么市场常用价格除以每股收益来谈估值，知道 trailing P/E、forward P/E 和预期 EPS 的区别。
- 建议案例：继续使用 Microsoft 和 Adobe，加入主要指数或 ETF 的 P/E 口径做对照；如涉及当前价格和估值，必须重新核验交易所、公司 IR、指数公司或权威数据源。
- 必须解释的关键词：Price、Market Cap、P/E、Trailing P/E、Forward P/E、Consensus EPS、Multiple Expansion、Multiple Compression。
- 下节课开始前需要联网核验的数据：目标公司的最新股价或市值、最新 EPS、分析师一致预期来源口径、指数或 ETF 的估值口径、最新利率背景。

## 来源

- Microsoft FY2026 Q3 Form 10-Q filing detail: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
- Microsoft FY2026 Q3 income statement XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
- Microsoft FY2026 Q3 balance sheet parenthetical XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R5.htm
- Microsoft FY2026 Q3 cash flow statement XBRL report: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
- Adobe FY2026 Q2 Form 10-Q PDF: https://www.adobe.com/cc-shared/assets/investor-relations/pdfs/adbe-10q-q226-final.pdf
- Adobe Announces New $25 Billion Stock Repurchase Program, 2026-04-21: https://www.adobe.com/cc-shared/assets/investor-relations/pdfs/b465t3rw34.pdf
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, 2026-06-18: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
