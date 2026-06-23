# 第二十六课：P/E、市盈率、EPS 预期与估值倍数入门

## 基本信息

- 日期：2026-06-23
- 数据截至：2026-06-23 15:44（Asia/Shanghai）；股票价格采用 Nasdaq quote API 的 2026-06-22 last sale；公司财务数据采用截至本次写作时 SEC 已披露的最新 10-Q/10-K；SPY 估值口径采用 State Street 页面 2026-06-18 数据；利率背景采用 Federal Reserve 2026-06-17 声明和 U.S. Treasury 2026-06-22 收益率曲线。
- 主题：为什么市场常用价格除以每股收益来谈估值，trailing P/E 和 forward P/E 有什么区别。
- 学习目标：理解 Price、Market Cap、P/E、Trailing P/E、Forward P/E、Consensus EPS、Multiple Expansion 和 Multiple Compression，知道估值倍数不是公司质量本身，而是市场愿意为利润支付的价格。
- 相关资产：股票、ETF、公司财报、指数估值、利率。
- 核心来源：
  - Microsoft FY2026 Q3 Form 10-Q filing detail, accession `0001193125-26-191507`, period 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
  - Microsoft SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
  - Adobe FY2026 Q2 Form 10-Q SEC HTML, period 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Adobe SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
  - Nasdaq quote API for MSFT and ADBE, retrieved 2026-06-23: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks and https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
  - Nasdaq analyst earnings forecast API for MSFT and ADBE, retrieved 2026-06-23: https://api.nasdaq.com/api/analyst/MSFT/earnings-forecast and https://api.nasdaq.com/api/analyst/ADBE/earnings-forecast
  - State Street SPDR S&P 500 ETF Trust page, SPY fund and index characteristics: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

第二十五课讲到 EPS。今天继续问：

> 如果每股收益已经算出来了，为什么市场还要看股价除以 EPS？

因为买股票不是只看公司赚了多少钱，还要看你为这份利润付了多少钱。P/E 把“价格”和“每股利润”放在一起，让不同价格和不同利润水平的股票可以先做一个粗略对比。

### 参考的教材式概念顺序

1. 股票价格是市场交易出来的每股价格。
2. 市值是每股价格乘以流通在外普通股数量。
3. EPS 是每股分摊到的净利润。
4. P/E 是 Price divided by Earnings Per Share，也就是价格除以每股收益。
5. Trailing P/E 用已经披露的过去利润。
6. Forward P/E 用未来预期利润，通常依赖分析师一致预期。
7. 倍数扩张或压缩，反映市场愿意为同一美元利润支付更高或更低价格。

### 核心概念

最小公式：

```text
P/E = Price / EPS
```

也可以从整体公司角度理解：

```text
P/E = Market Cap / Net Income
```

这两个公式说的是同一件事：市场愿意为公司每 1 美元利润支付多少美元价格。

### 用自己的话解释

假设一家公司每股收益是 10 美元，股价是 200 美元：

```text
P/E = 200 / 10 = 20 倍
```

这不表示 20 年一定回本，也不表示一定贵或便宜。它只是说：按当前利润口径，市场给这家公司 20 倍利润的价格。真正判断时还要看增长、利率、风险、现金流、行业周期和会计质量。

### 常见误区

- 误区一：P/E 越低越便宜。低 P/E 可能反映利润下滑风险、行业衰退、一次性利润或财务风险。
- 误区二：P/E 越高越优秀。高 P/E 可能反映高增长，也可能反映过高预期。
- 误区三：forward P/E 比 trailing P/E 更真实。forward P/E 依赖预测，预测会变。
- 误区四：不同公司 P/E 可以机械比较。行业、资本结构、利润质量、周期位置不同，倍数含义不同。

## 第二大板块：实时背景与市场传导

### 发生了什么

本课继续使用 Microsoft 和 Adobe 做估值入门。下表只用于教学演示，不是投资结论。

| 公司 | Nasdaq last sale | 最新财报口径 | 粗略 TTM 稀释 EPS | 粗略 trailing P/E | Nasdaq 下一财年 consensus EPS | 粗略 forward P/E |
| --- | ---: | --- | ---: | ---: | ---: | ---: |
| Microsoft | 367.34 美元，lastTradeTimestamp 2026-06-22 | FY2026 Q3 10-Q，报告期 2026-03-31 | 16.79 美元 | 21.9 倍 | FY2027 19.28 美元，19 个估计 | 19.1 倍 |
| Adobe | 194.90 美元，lastTradeTimestamp 2026-06-22 | FY2026 Q2 10-Q，报告期 2026-05-29 | 17.48 美元 | 11.2 倍 | FY2027 22.25 美元，15 个估计 | 8.8 倍 |

这里的 TTM 稀释 EPS 用教学口径粗算：

```text
TTM diluted EPS ~= 最近完整财年 EPS - 上年同期 YTD EPS + 今年最新 YTD EPS
```

Microsoft：

```text
13.64 - 9.99 + 13.14 = 16.79
367.34 / 16.79 ~= 21.9
```

Adobe：

```text
16.70 - 8.08 + 8.86 = 17.48
194.90 / 17.48 ~= 11.2
```

再看 ETF 口径。State Street 的 SPY 页面显示，SPY fund characteristics as of 2026-06-18 的 `Price/Earnings Ratio FY1` 为 22.63；S&P 500 Index characteristics as of 2026-06-18 的 `Price/Earnings` 为 27.55，`Price/Earnings Ratio FY1` 为 22.51。页面说明 FY1 P/E 是用当前价格除以预测的一年 EPS，并且底层估计来自 FactSet Estimates。

这说明一件很重要的事：估值口径必须看清楚。公司 trailing P/E、公司 forward P/E、ETF fund P/E、指数 P/E 不是同一个口径。

### 为什么重要

Federal Reserve 2026-06-17 声明维持联邦基金目标区间在 3.50%-3.75%。U.S. Treasury 2026-06-22 收益率曲线显示：1 个月 3.66%、2 年期 4.24%、10 年期 4.51%、30 年期 4.95%。

利率进入 P/E 的方式不难理解：

- 股票价格代表未来利润和现金流的现值。
- 利率越高，未来现金流折现回今天的价值通常越低。
- 高增长公司的利润更偏未来，因此对利率和预期变化更敏感。
- 如果利润预期下调，即使股价不动，forward P/E 也会上升；如果股价下跌且利润预期不变，P/E 会下降。

### 本节采用的数据和来源

- Microsoft 和 Adobe 的 EPS、净利润、YTD 数据来自 SEC Company Facts XBRL 与最新 10-Q。
- Microsoft 和 Adobe 的当前股票价格来自 Nasdaq quote API，两个接口均显示 lastTradeTimestamp 为 2026-06-22，且 `isRealTime` 为 false，因此本课把它当作延迟或最近成交数据。
- consensus EPS 来自 Nasdaq analyst earnings forecast API。该 API payload 的 `asOf` 字段为 null，所以本课明确写明检索时间为 2026-06-23，不把它当成公司官方 guidance。
- SPY 的 P/E 和 FY1 P/E 来自 State Street 发行人页面，页面给出 fund/index characteristics as of 2026-06-18。
- 利率背景来自 Federal Reserve 和 U.S. Treasury。

### 这些现实事件如何连接理论

P/E 的分子是市场价格，分母是利润。分子每天变化，分母按财报和预期变化。Microsoft、Adobe 与 SPY 的例子提醒我们：同一个 P/E 名词背后可能有不同分母，分别是过去 EPS、未来 EPS、基金底层持仓的加权指标或指数口径。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、交易所市场数据、ETF 发行人披露、分析师预期数据供应商、央行利率政策。
- 已确认事实：Microsoft 和 Adobe 已披露最新 10-Q；Nasdaq quote API 提供 2026-06-22 last sale；State Street 页面提供 2026-06-18 SPY 与指数估值口径；Fed 与 Treasury 已发布最新政策和利率数据。
- 市场可能如何传导：利率上行会压低高久期利润的估值容忍度；EPS 预期上修可能降低 forward P/E；EPS 预期下修可能让看似便宜的股票重新变贵。
- 仍需核验或观察：Nasdaq consensus EPS 的供应商口径和更新时间、公司后续 guidance、下季度实际 EPS、利率是否继续上行。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Price | 价格 | 一股股票当前或最近成交的市场价格 | 是 P/E 的分子 |
| Market Cap | 市值 | 股价乘以普通股数量 | 从整体公司角度看估值 |
| P/E | 市盈率 | 价格除以每股收益 | 表示市场为每 1 美元利润付多少价格 |
| Trailing P/E | 过去十二个月市盈率 | 用已经披露的过去利润算 P/E | 更接近已确认事实 |
| Forward P/E | 预期市盈率 | 用未来预测 EPS 算 P/E | 更贴近市场预期，但依赖预测 |
| Consensus EPS | 一致预期每股收益 | 多个分析师预测的平均或汇总口径 | 是 forward P/E 的常见分母 |
| Multiple Expansion | 估值倍数扩张 | 利润不变时市场愿意付更高倍数 | 股价可因风险偏好或预期改善上涨 |
| Multiple Compression | 估值倍数压缩 | 利润不变时市场只愿意付更低倍数 | 股价可因利率、风险或叙事恶化下跌 |

## 回顾提示

- 学到本课前建议回顾：第 14 课 guidance 与预期差、第 15 课估值倍数和利率、第 24 课净利润、第 25 课 EPS。
- 本课哪些内容会在后续课程继续使用：PEG、EV/EBITDA、自由现金流收益率、DCF、指数估值和资产配置。
- 如果看不懂本课，可以先回到：第 25 课“EPS、稀释、回购与股本数量入门”。

## 案例拆解

- 案例对象：Microsoft、Adobe 与 SPY 的 P/E 口径对照。
- 已确认事实：
  - Nasdaq quote API 显示 Microsoft 2026-06-22 last sale 为 367.34 美元，Adobe 为 194.90 美元。
  - Microsoft FY2025 diluted EPS 为 13.64，FY2025 Q3 YTD diluted EPS 为 9.99，FY2026 Q3 YTD diluted EPS 为 13.14。
  - Adobe FY2025 diluted EPS 为 16.70，FY2025 Q2 YTD diluted EPS 为 8.08，FY2026 Q2 YTD diluted EPS 为 8.86。
  - Nasdaq analyst API 显示 Microsoft FY2027 consensus EPS 为 19.28 美元，Adobe FY2027 consensus EPS 为 22.25 美元。
  - State Street 页面显示 SPY fund FY1 P/E 为 22.63，S&P 500 Index trailing P/E 为 27.55，index FY1 P/E 为 22.51。
- 来源日期和链接：SEC 最新 10-Q 和 Company Facts、Nasdaq quote/analyst API、State Street SPY 页面、Fed 2026-06-17 statement、Treasury 2026-06-22 rates。
- 分析推理：Microsoft 的 forward P/E 低于 trailing P/E，说明可访问的 consensus EPS 口径中下一财年 EPS 高于 TTM EPS；Adobe 也是如此。但这只说明预期分母更高，不自动说明股票便宜。
- 后续验证指标：下季度实际 EPS、公司 guidance、分析师预期调整、股价变化、10 年期 Treasury yield、SPY 和指数估值口径变化。

## 个人情境连接

- 对关注清单的启发：看到 P/E 时先问“分母是什么”，不要只看倍数大小。
- 对持仓或基金选择的启发：指数基金也有估值倍数，但基金 P/E 是底层股票的组合口径，不能和单一公司机械比较。
- 对工作、收入、消费或风险管理的启发：如果把职业收入也想成“未来现金流”，利率和稳定性会影响别人愿意为这份收入支付的价格。越不稳定的未来收入，折现越重。

## 结论边界

- 可以确定：P/E 把价格和利润连接起来；trailing P/E 更依赖已披露事实，forward P/E 更依赖预测；估值倍数会受利率、风险偏好和增长预期影响。
- 不能确定：低 P/E 不必然便宜，高 P/E 不必然泡沫；forward P/E 不代表公司承诺。
- 需要继续观察：consensus EPS 是否调整、实际 EPS 是否兑现、Fed 和 Treasury 利率背景是否继续变化。
- 不构成投资建议的原因：本课只解释估值倍数的计算和口径，不判断 Microsoft、Adobe、SPY 或任何证券是否值得买卖。

## 练习题

1. 用自己的话解释：为什么 P/E 的分母不同，结论可能完全不同？
2. 如果一家公司的 trailing P/E 很高，但 forward P/E 明显下降，你会追问哪三个问题？
3. 为什么利率上升可能导致估值倍数压缩？
4. SPY 的 FY1 P/E 和单个公司的 forward P/E 为什么不能机械比较？

## 学习交接

- 本课已经完成：把 EPS 连接到价格、市值、trailing P/E、forward P/E、consensus EPS 和指数/ETF 估值口径。
- 本课最重要的一句话：P/E 不是“便宜或贵”的答案，而是“市场为哪一种利润口径付了多少价格”的问题。
- 需要复习的关键词：Price、Market Cap、P/E、Trailing P/E、Forward P/E、Consensus EPS、Multiple Expansion、Multiple Compression。
- 还不稳定、下次要回看的地方：forward P/E 的预测口径和更新时间，不能把第三方 consensus 当成公司官方承诺。
- 适合下次打开仓库先读的文件：`lessons/2026-06-23-lesson-27-enterprise-value-ev-ebitda.md`

## 下节课安排

- 建议主题：第二十七课：企业价值、净现金/净债务与 EV/EBITDA 入门。
- 学习目标：理解为什么有时不能只看股权市值，还要把债务和现金放进估值。
- 建议案例：继续使用 Microsoft 与 Adobe，用 Nasdaq 最新价格、SEC 股数、现金、短期投资和债务数据做教学演示。
- 必须解释的关键词：Enterprise Value、Equity Value、Net Cash、Net Debt、EBITDA、EV/EBITDA、Capital Structure、Non-GAAP。
- 下节课开始前需要联网核验的数据：目标公司最新股价、普通股数、现金和短期投资、债务、D&A、税费、利息费用、净利润和最新利率背景。

## 来源

- Microsoft FY2026 Q3 Form 10-Q filing detail: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/0001193125-26-191507-index.html
- Microsoft SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000789019.json
- Adobe FY2026 Q2 Form 10-Q SEC HTML: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Adobe SEC Company Facts XBRL: https://data.sec.gov/api/xbrl/companyfacts/CIK0000796343.json
- Nasdaq MSFT quote API: https://api.nasdaq.com/api/quote/MSFT/info?assetclass=stocks
- Nasdaq ADBE quote API: https://api.nasdaq.com/api/quote/ADBE/info?assetclass=stocks
- Nasdaq MSFT analyst earnings forecast API: https://api.nasdaq.com/api/analyst/MSFT/earnings-forecast
- Nasdaq ADBE analyst earnings forecast API: https://api.nasdaq.com/api/analyst/ADBE/earnings-forecast
- State Street SPDR S&P 500 ETF Trust page: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Rates, June 2026 XML: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value_month=202606
