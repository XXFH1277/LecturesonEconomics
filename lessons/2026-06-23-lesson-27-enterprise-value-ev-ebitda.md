# 第二十七课：企业价值、净现金/净债务与 EV/EBITDA 入门

## 基本信息

- 日期：2026-06-23
- 数据截至：2026-06-23 15:44（Asia/Shanghai）；股票价格采用 Nasdaq quote API 的 2026-06-22 last sale；公司财务数据采用 SEC Company Facts 和最新 10-Q/10-K；利率背景采用 Federal Reserve 2026-06-17 声明和 U.S. Treasury 2026-06-22 收益率曲线。
- 主题：为什么估值有时不能只看股权市值，还要把债务和现金放进企业价值。
- 学习目标：理解 Enterprise Value、Equity Value、Net Cash、Net Debt、EBITDA、EV/EBITDA、Capital Structure 和 Non-GAAP，知道 EV/EBITDA 是在看整家公司经营利润能力的价格，而不只是普通股的价格。
- 相关资产：股票、公司财报、公司债务、现金和短期投资、软件公司、利率。
- 核心来源：
  - Microsoft FY2026 Q3 Form 10-Q filing detail, accession `0001193125-26-191507`, period 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
  - Microsoft SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
  - Microsoft Form 8-K, 2026-04-29, announcing FY2026 Q3 results: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-20260429.htm
  - Adobe FY2026 Q2 Form 10-Q SEC HTML, period 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Adobe SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
  - Adobe Form 8-K, 2026-06-11, announcing FY2026 Q2 results and CFO transition: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbe-20260608.htm
  - Nasdaq quote API for MSFT and ADBE, retrieved 2026-06-23: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks and https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十六课讲到：

```text
P/E = 股价 / 每股收益
```

今天继续问：

> 如果两家公司市值一样，但一家有很多现金，另一家有很多债务，它们真的一样贵吗？

不一定。普通股市值只看股东权益的市场价格。企业价值把股权、债务和现金放在一起，试图回答“买下整家公司经营资产大概要付多少净价格”。

### 参考的教材式概念顺序

1. Equity Value 是普通股股东拥有的市场价值，通常可近似为股价乘以普通股数。
2. Debt 是债权人对公司的索取权，收购整家公司时不能忽略。
3. Cash and Short-term Investments 可以抵减收购者实际净支付成本。
4. Enterprise Value 把股权、债务和现金合并看。
5. EBITDA 是税息折旧摊销前利润，用来粗略观察经营资产产生利润的能力。
6. EV/EBITDA 用企业价值除以 EBITDA，常用于资本结构不同的公司之间做初步比较。

### 核心概念

最小公式：

```text
Equity Value = Stock Price * Common Shares Outstanding
Enterprise Value = Equity Value + Debt - Cash and Short-term Investments
EV/EBITDA = Enterprise Value / EBITDA
```

EBITDA 的教学公式：

```text
EBITDA = Net Income + Income Tax Expense + Interest Expense + Depreciation + Amortization
```

这不是 GAAP 利润表项目，而是分析师常用的非 GAAP 分析口径。不同公司、数据库和投行模型可能处理 lease liabilities、minority interest、preferred stock、pension deficits、restricted cash 和非经常项目的方式不同。

### 用自己的话解释

假设你买一家小店：

- 店主说股权价格是 100 万。
- 店里还有 40 万贷款要还。
- 收银台和银行账户里有 20 万现金。

那么你真正看这家店经营资产的净价格，不能只看 100 万：

```text
企业价值 = 100 + 40 - 20 = 120 万
```

股票市场里的 EV 也是类似直觉。

### 常见误区

- 误区一：市值就是买下公司的全部价格。市值只看普通股权益，不含债务调整。
- 误区二：现金越多越一定好。现金可能是安全垫，也可能代表暂未有效投入。
- 误区三：EV/EBITDA 可以替代 P/E。两者看的是不同层次，一个偏全企业经营资产，一个偏普通股股东税后利润。
- 误区四：EBITDA 等于现金流。EBITDA 没扣资本开支、营运资本变化、税和利息，不等于自由现金流。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课继续用 Microsoft 和 Adobe 做教学演示。以下估算把 Nasdaq 2026-06-22 last sale 与 SEC 最新可得股数、现金、短期投资和债务放在一起。因为价格和财务报表日期不同，所以这是课堂估算，不是专业估值报告。

| 公司 | 股价和股数 | 粗略股权价值 | 现金和短期投资 | 债务 | 粗略企业价值 |
| --- | --- | ---: | ---: | ---: | ---: |
| Microsoft | 367.34 美元；SEC `EntityCommonStockSharesOutstanding` 7,428,434,704 股，end 2026-04-23 | 约 2.729 万亿美元 | 321.05 亿美元现金 + 461.67 亿美元短期投资 = 782.72 亿美元 | 88.39 亿美元 current long-term debt + 314.23 亿美元 noncurrent long-term debt = 402.62 亿美元 | 约 2.691 万亿美元 |
| Adobe | 194.90 美元；SEC `EntityCommonStockSharesOutstanding` 397,500,000 股，end 2026-06-11 | 约 774.73 亿美元 | 49.19 亿美元现金 + 7.07 亿美元短期投资 = 56.26 亿美元 | 18.43 亿美元 current debt + 48.02 亿美元 long-term debt = 66.45 亿美元 | 约 784.92 亿美元 |

这张表先给出一个直觉：

- Microsoft 是净现金状态，现金和短期投资高于列示债务，企业价值略低于股权价值。
- Adobe 在这个简化口径下是小幅净债务状态，企业价值略高于股权价值。

再把企业价值和 TTM EBITDA 连接：

| 公司 | 粗略 TTM 净利润 | 加回税费 | 加回利息 | 加回折旧摊销 | 粗略 TTM EBITDA | 粗略 EV/EBITDA |
| --- | ---: | ---: | ---: | ---: | ---: | ---: |
| Microsoft | 1,252.16 亿美元 | 292.87 亿美元 | 28.27 亿美元 | 355.00 亿美元 | 1,928.30 亿美元 | 约 14.0 倍 |
| Adobe | 72.29 亿美元 | 18.82 亿美元 | 2.61 亿美元 | 7.59 亿美元 | 101.31 亿美元 | 约 7.7 倍 |

TTM 口径同样是教学估算：

```text
TTM = 最近完整财年 - 上年同期 YTD + 今年最新 YTD
```

### 为什么重要

Federal Reserve 2026-06-17 维持联邦基金目标区间在 3.50%-3.75%。U.S. Treasury 2026-06-22 收益率曲线显示：2 年期 4.24%、10 年期 4.51%、30 年期 4.95%。

利率会影响企业价值分析：

- 债务成本越高，债务多的公司再融资压力越大。
- 现金多的公司在高利率环境下可能获得更高利息收入，但也有机会成本。
- EV 会把债务纳入估值，避免只看市值时低估负债压力。
- EBITDA 没有扣利息，所以高债务公司即使 EV/EBITDA 看起来低，也可能因利息费用影响普通股股东利润。

### 本节采用的数据和来源

- 普通股数、现金、短期投资、债务、净利润、税费、利息费用、折旧和摊销来自 SEC Company Facts XBRL 与最新 10-Q/10-K。
- 股价来自 Nasdaq quote API，lastTradeTimestamp 为 2026-06-22。
- Microsoft 2026-04-29 Form 8-K 和 Adobe 2026-06-11 Form 8-K 用于核验最新财报发布事件。
- Adobe 8-K 同时提醒：公司在新闻稿中使用 non-GAAP financial measures，并说明这些指标不应替代 GAAP 指标。这一点正好帮助理解 EBITDA 类指标的边界。
- 利率背景来自 Federal Reserve 和 U.S. Treasury。

### 这些现实事件如何连接理论

P/E 看的是普通股价格与税后利润。EV/EBITDA 看的是整家公司经营资产的价格与税息折旧摊销前利润。Microsoft 和 Adobe 的现金、债务和股数结构不同，因此只看市值或只看 P/E 都不完整。EV/EBITDA 不是更高级的万能答案，而是换了一个角度看同一家公司。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC XBRL 披露、U.S. GAAP、非 GAAP 指标监管、公司债务市场、央行利率政策。
- 已确认事实：Microsoft 和 Adobe 已披露最新 10-Q；Adobe 2026-06-11 Form 8-K 明确说明其新闻稿含 non-GAAP measures 并列出限制；Fed 和 Treasury 已发布最新利率背景。
- 市场可能如何传导：高利率提高债务再融资成本，也提高现金资产收益；企业价值把净债务纳入估值，能更清楚地看到资本结构差异。
- 仍需核验或观察：后续债务到期安排、现金是否用于回购或投资、利息费用变化、资本开支是否让 EBITDA 与自由现金流分化。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Enterprise Value | 企业价值 | 股权价值加债务再减现金后的整家公司价值 | 用来观察经营资产的净价格 |
| Equity Value | 股权价值 | 普通股股东拥有的市场价值 | P/E 和市值主要看这一层 |
| Net Cash | 净现金 | 现金和短期投资高于债务 | 企业价值可能低于股权价值 |
| Net Debt | 净债务 | 债务高于现金和短期投资 | 企业价值可能高于股权价值 |
| EBITDA | 税息折旧摊销前利润 | 净利润加回税、利息、折旧和摊销 | 用来粗略观察经营资产盈利能力 |
| EV/EBITDA | 企业价值倍数 | 企业价值除以 EBITDA | 常用于资本结构不同公司的粗略比较 |
| Capital Structure | 资本结构 | 公司用股权、债务和现金安排融资 | 决定风险和估值口径 |
| Non-GAAP | 非通用会计准则指标 | 不属于 GAAP 标准报表项目的分析指标 | 有用但必须看调整方式和限制 |

## 回顾提示

- 学到本课前建议回顾：第 13 课资本配置、第 15 课估值倍数、第 24 课净利润、第 26 课 P/E。
- 本课哪些内容会在后续课程继续使用：DCF、自由现金流收益率、并购估值、债务再融资、股票回购质量和资本结构比较。
- 如果看不懂本课，可以先回到：第 26 课“P/E、市盈率、EPS 预期与估值倍数入门”。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的企业价值和 EV/EBITDA 教学估算。
- 已确认事实：
  - Nasdaq quote API 显示 Microsoft 2026-06-22 last sale 为 367.34 美元，Adobe 为 194.90 美元。
  - Microsoft 2026-04-23 普通股数为 7,428,434,704 股；2026-03-31 现金 321.05 亿美元、短期投资 461.67 亿美元、current long-term debt 88.39 亿美元、noncurrent long-term debt 314.23 亿美元。
  - Adobe 2026-06-11 普通股数为 397,500,000 股；2026-05-29 现金 49.19 亿美元、短期投资 7.07 亿美元、current debt 18.43 亿美元、long-term debt 48.02 亿美元。
  - 用 SEC XBRL 最近完整财年、上年同期 YTD 和今年最新 YTD 粗算，Microsoft TTM EBITDA 约 1,928.30 亿美元，Adobe 约 101.31 亿美元。
- 来源日期和链接：Microsoft SEC Company Facts、Adobe SEC Company Facts、Microsoft 2026-04-29 Form 8-K、Adobe 2026-06-11 Form 8-K、Nasdaq quote API、Fed 和 Treasury。
- 分析推理：Microsoft 的净现金让 EV 略低于股权价值；Adobe 的简化净债务让 EV 略高于股权价值。EV/EBITDA 比 P/E 更关注经营资产和资本结构，但仍没有扣资本开支和营运资本。
- 后续验证指标：最新股价、实际普通股数、债务到期表、现金用途、利息费用、D&A、资本开支、经营现金流和自由现金流。

## 个人情境连接

- 对关注清单的启发：看到市值时，顺手查现金和债务，避免把“股权价格”误读成“整家公司净价格”。
- 对持仓或基金选择的启发：基金如果重仓高债务公司，P/E 可能不够用，要补看 EV、利息费用和自由现金流。
- 对工作、收入、消费或风险管理的启发：个人买房也有类似逻辑。房子的标价像资产价格，房贷像债务，手头现金像抵减项，真正风险要看净负债和现金流。

## 结论边界

- 可以确定：EV 把股权、债务和现金放在一起；EV/EBITDA 能帮助初步比较资本结构不同的公司。
- 不能确定：EV/EBITDA 低不必然便宜；EBITDA 高也不等于现金流好。
- 需要继续观察：资本开支、营运资本、实际税费、利息费用、债务到期和回购执行。
- 不构成投资建议的原因：本课只解释估值口径和财报机制，不判断 Microsoft、Adobe 或任何证券是否值得买卖。

## 练习题

1. 为什么一家净现金公司的企业价值可能低于股权价值？
2. 为什么 EV/EBITDA 比 P/E 更适合初步比较资本结构不同的公司？
3. EBITDA 为什么不等于自由现金流？至少说出三个还没扣掉的项目。
4. 如果一家公司 EV/EBITDA 很低，但利息费用快速上升，你会继续核验什么？

## 学习交接

- 本课已经完成：把股权价值、市值、现金、债务、企业价值、EBITDA 和 EV/EBITDA 连成一条估值口径。
- 本课最重要的一句话：P/E 看普通股股东的税后利润价格，EV/EBITDA 看整家公司经营资产的税息折旧摊销前利润价格。
- 需要复习的关键词：Enterprise Value、Equity Value、Net Cash、Net Debt、EBITDA、EV/EBITDA、Capital Structure、Non-GAAP。
- 还不稳定、下次要回看的地方：EBITDA 与现金流不是一回事，后续必须学习资本开支、营运资本和自由现金流收益率。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第二十八课：PEG、增长率与估值陷阱入门。
- 学习目标：理解为什么同样的 P/E 或 EV/EBITDA，在不同增长率、利润质量和利率环境下含义不同。
- 建议案例：继续使用 Microsoft、Adobe 和 SPY；可加入一只低增长或周期性公司做对照，但必须重新核验 SEC、交易所和公司 IR 来源。
- 必须解释的关键词：Growth Rate、PEG、Earnings Revision、Quality of Earnings、Value Trap、Duration、Terminal Value。
- 下节课开始前需要联网核验的数据：目标公司的最新股价、consensus EPS 和增长率来源、实际 EPS、收入增长、毛利率、经营利润率、利率背景和行业周期数据。

## 来源

- Microsoft FY2026 Q3 Form 10-Q filing detail: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
- Microsoft SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
- Microsoft Form 8-K, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-20260429.htm
- Adobe FY2026 Q2 Form 10-Q SEC HTML: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Adobe SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
- Adobe Form 8-K, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbe-20260608.htm
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
- Nasdaq ADBE quote API: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606
