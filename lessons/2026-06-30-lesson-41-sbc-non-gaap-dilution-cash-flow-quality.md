# 第四十一课：股权激励、Non-GAAP、稀释与现金流质量入门

## 基本信息

- 日期：2026-06-30
- 数据截至：2026-06-30 20:05（Asia/Shanghai）；公司财务采用 Datadog 2026-05-07 Form 8-K exhibit 99.1 与 Form 10-Q、Snowflake 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-29 Form 10-Q、Salesforce 2026-05-27 Form 8-K exhibit 99.1 与 2026-05-28 Form 10-Q、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 U.S. Treasury 2026-06-29 最新可得收益率。
- 主题：为什么“股权激励不是现金支出”不等于“对股东没有成本”。
- 学习目标：理解 Stock-based Compensation、RSU、GAAP、Non-GAAP、Dilution、Diluted EPS、Share Repurchase、Treasury Stock、Owner Earnings，并学会检查自由现金流是否被稀释成本美化。
- 相关资产：SaaS、软件公司、成长股、自由现金流、EPS、回购、股权激励、资本配置、估值质量。
- 已核验来源（核心来源）：
  - Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
  - Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
  - Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
  - Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
  - Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
  - Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-29: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲订单、开票、递延收入和自由现金流。今天继续问：

> 如果一家公司用股票发工资，没有立刻花现金，那这笔成本到底算不算成本？

答案是：对公司现金账户来说，股权激励不是当期现金流出；对股东来说，它通常是成本，因为新发股票或 RSU 归属会稀释每一股对公司的索取权。公司可以用回购抵消稀释，但回购本身要花现金，甚至可能需要发债。

### 参考的教材式概念顺序

1. GAAP：先看按会计准则确认的利润。
2. Stock-based Compensation：公司用股票或股票权利补偿员工。
3. Non-GAAP：公司把某些项目加回，展示调整后经营表现。
4. Operating Cash Flow：SBC 是非现金费用，因此会被加回经营现金流。
5. Free Cash Flow：FCF 可能很强，但未必扣除了未来抵消稀释所需的回购现金。
6. Dilution：股数增加后，每股分到的公司价值被摊薄。
7. Share Repurchase：回购可以减少股数，但要看价格、资金来源和是否只是抵消激励稀释。
8. Owner Earnings：从股东视角检查真正可分配、可持续的现金。

### 核心概念

最小公式：

```text
SBC margin = Stock-based compensation / Revenue

Dilution check = 本期稀释股数或流通股数 / 上期股数 - 1

Free Cash Flow = Operating Cash Flow - Capex - Capitalized Software（按公司口径）

股东视角现金检查 = Free Cash Flow - 为抵消稀释而需要的净回购现金（教学口径）
```

最后一个公式不是 GAAP 指标，也不是标准估值公式。它只是提醒初学者：如果公司用股票支付大量薪酬，FCF 看起来更强，但股东最终要么接受稀释，要么用现金回购抵消稀释。

### 用自己的话解释

SBC 像公司给员工一张未来拿股票的权利。它可以减少当期现金工资压力，所以现金流表看起来更舒服；但如果未来股票真的发出去，原股东拥有公司的比例就会变小。

Non-GAAP 不是不能看。它能帮助我们剔除某些非现金、一次性或波动项目，更接近管理层口径。但如果公司长期大量剔除 SBC，而 SBC 又是正常经营中用来留住员工的必要成本，那么学习者必须把它放回股东视角里。

### 常见误区

- 误区一：看到 non-GAAP 利润高，就认为 GAAP 利润不重要。两个口径都要看。
- 误区二：认为 SBC 不是现金支出，所以没有成本。它可能通过稀释转移给股东。
- 误区三：看到公司回购就认为一定利好。回购可能只是抵消员工股权激励，也可能用债务融资。
- 误区四：只看 FCF，不看股数变化。每股价值取决于总现金流和股数。
- 误区五：把所有 SBC 都看成坏事。合理股权激励可以对齐员工和股东，但规模、持续性和回报要核验。

## 第二大板块：实时背景与市场传导

### 发生了什么

Datadog 2026 年第一季度披露，revenue 为 10.064 亿美元，GAAP operating margin 为 1%，non-GAAP operating margin 为 22%，free cash flow 为 2.891 亿美元。10-Q 披露本季 stock-based compensation 为 1.968 亿美元，约占收入 19.6%；基本加权平均股数为 3.53272 亿股，稀释加权平均股数为 3.64731 亿股。

Snowflake 2027 财年第一季度披露，GAAP operating loss 为 3.262 亿美元，non-GAAP operating income 为 1.658 亿美元，non-GAAP operating margin 为 11.9%。10-Q 披露本季 stock-based compensation 为 4.0247 亿美元，约占收入 29%；基本和稀释加权平均股数为 3.45391 亿股，高于上年同期的 3.32657 亿股。公司同季 repurchases of common stock 为 3.000 亿美元，taxes paid related to net share settlement of equity awards 为 1.428 亿美元。

Salesforce 2027 财年第一季度披露，GAAP operating margin 为 21.1%，non-GAAP operating margin 为 34.8%，operating cash flow 为 67 亿美元，free cash flow 为 66 亿美元。10-Q 披露本季 stock-based compensation expense 为 8.57 亿美元；同季 repurchases of common stock 为 272.48 亿美元，payments of dividends and dividend equivalents 为 3.65 亿美元，同时 proceeds from issuance of debt 为 248.42 亿美元。

Adobe 2026 财年第二季度披露，GAAP operating income 为 22.38 亿美元，non-GAAP operating income 为 29.45 亿美元，operating cash flow 为 21.65 亿美元，repurchased approximately 8.5 million shares during the quarter。8-K reconciliation 披露 stock-based and deferred compensation expense 为 5.56 亿美元；Q2 稀释股数为 4.02 亿股，低于上年同期的 4.29 亿股。

### 为什么重要

Fed 2026-06-17 维持 federal funds rate 目标区间在 3.50%-3.75%；U.S. Treasury 2026-06-29 的 10 年期 Treasury par yield 为 4.38%。当无风险收益率不低时，市场会更严格地区分：

- 现金流是真正可分配，还是靠加回非现金股权激励显得更强。
- Non-GAAP 利润是帮助看清经营，还是掩盖长期常态成本。
- 回购是高质量资本配置，还是被动抵消稀释。
- 债务融资回购是否提高了股东回报，也提高了财务风险。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Datadog GAAP / non-GAAP operating margin | 1% / 22% | Datadog 2026-05-07 8-K | 口径差异 |
| Datadog stock-based compensation | 1.968 亿美元 | Datadog 2026-05-07 10-Q | SBC 成本 |
| Datadog free cash flow | 2.891 亿美元 | Datadog 2026-05-07 10-Q | 现金流与 SBC 对照 |
| Datadog diluted weighted shares | 3.64731 亿股 | Datadog 2026-05-07 10-Q | 稀释股数 |
| Snowflake GAAP operating loss / non-GAAP operating income | -3.262 亿美元 / 1.658 亿美元 | Snowflake 2026-05-27 8-K | 口径差异 |
| Snowflake stock-based compensation | 4.0247 亿美元 | Snowflake 2026-05-29 10-Q | SBC 成本 |
| Snowflake SBC as % of revenue | 29% | Snowflake 2026-05-29 10-Q | 成本规模 |
| Snowflake share repurchases | 3.000 亿美元 | Snowflake 2026-05-29 10-Q | 抵消稀释 |
| Salesforce GAAP / non-GAAP operating margin | 21.1% / 34.8% | Salesforce 2026-05-27 8-K | 成熟软件口径 |
| Salesforce stock-based compensation expense | 8.57 亿美元 | Salesforce 2026-05-28 10-Q | SBC 成本 |
| Salesforce common stock repurchased | 272.48 亿美元 | Salesforce 2026-05-28 10-Q | 回购和资本配置 |
| Adobe GAAP / non-GAAP operating income | 22.38 亿美元 / 29.45 亿美元 | Adobe 2026-06-11 8-K | 口径差异 |
| Adobe stock-based and deferred compensation adjustment | 5.56 亿美元 | Adobe 2026-06-11 8-K | Non-GAAP 调整 |
| Adobe diluted shares | 4.02 亿股，本年 Q2；4.29 亿股，上年 Q2 | Adobe 2026-06-11 8-K | 回购后的股数变化 |
| 10 年期 Treasury yield | 4.38% | U.S. Treasury, 2026-06-29 | 折现率背景 |

### Datadog：FCF 很强，但 SBC 也要放回股东视角

Datadog Q1 2026 revenue 为 10.064 亿美元，free cash flow 为 2.891 亿美元，stock-based compensation 为 1.968 亿美元。

教学观察：

```text
SBC margin = 1.968 / 10.064 = 约 19.6%

FCF margin = 2.891 / 10.064 = 约 28.7%
```

这不是说 Datadog 的 FCF 是假的。FCF 按公司口径是真实经营现金流扣资本开支和资本化软件后的结果。但从股东视角看，如果公司长期用大量股票补偿员工，就要同时看股数变化、未来回购需求和 non-GAAP 调整。

### Snowflake：Non-GAAP 可以帮助观察经营，但差异必须解释

Snowflake Q1 FY2027 GAAP operating loss 为 3.262 亿美元，non-GAAP operating income 为 1.658 亿美元，差异很大。主要原因之一是 stock-based compensation 规模大。本季 SBC 为 4.0247 亿美元，约占收入 29%。

这给初学者一个典型案例：同一家公司在 GAAP 下亏损，在 non-GAAP 下盈利。两个数字都不是“假”，它们回答的问题不同：

- GAAP 问：按会计准则，包括股权激励等成本后，公司本季盈利吗？
- Non-GAAP 问：如果剔除某些非现金、收购、重组或波动项目，核心经营表现大概怎样？
- 股东视角问：这些剔除项目是不是长期反复发生？如果长期反复发生，就不能完全忽略。

Snowflake 还披露基本和稀释加权平均股数为 3.45391 亿股，高于上年同期 3.32657 亿股。本季回购 3.000 亿美元，说明公司在尝试管理股数，但回购是否创造价值还要看价格、现金流、股数趋势和机会成本。

### Salesforce：回购能压低股数，但债务融资改变资本结构

Salesforce Q1 FY2027 披露 common stock repurchased 为 272.48 亿美元，payments of dividends and dividend equivalents 为 3.65 亿美元，同时 proceeds from issuance of debt 为 248.42 亿美元。公司 8-K 还说明进入 250 亿美元 accelerated share repurchase，初始交付 1.03 亿股。

从 EPS 角度，回购减少股数可能提高每股指标；从资本结构角度，债务融资回购会增加债务和利息压力。Salesforce 的例子说明，回购不是孤立动作，要和债务、现金、利率、FCF、SBC 和未来投资需求一起看。

### Adobe：回购可以真正降低股数，但仍要看 Non-GAAP 加回项

Adobe Q2 FY2026 稀释股数为 4.02 亿股，低于上年同期 4.29 亿股；同季回购约 850 万股。Adobe 的股数下降说明回购不只是口号，已经反映到每股分母上。

但 Adobe 的 non-GAAP operating income 也把 stock-based and deferred compensation expense 5.56 亿美元加回。因此初学者应同时看两件事：

```text
股数是否真的下降？
Non-GAAP 利润中剔除的 SBC 是否仍是常态经营成本？
```

成熟软件公司可以同时有强现金流、回购和股权激励。关键不是用一个标签判断好坏，而是把总现金流、每股现金流、回购价格和股数变化连起来。

### 这些现实事件如何连接理论

- Datadog 展示“高 FCF + 高 SBC”的成长软件组合。
- Snowflake 展示 GAAP 与 non-GAAP 之间的巨大差异，以及 SBC 对利润表和股数的影响。
- Salesforce 展示大规模回购、债务融资、分红和 SBC 如何同时出现。
- Adobe 展示成熟软件公司如何通过回购降低股数，但仍需要审计 non-GAAP 调整。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 非 GAAP 披露规则、GAAP 股权激励会计、公司回购披露、债券市场融资、Fed 利率政策、数据安全和 AI 产品监管。
- 已确认事实：本课公司数据来自 SEC 文件；利率背景来自 Federal Reserve 和 U.S. Treasury。
- 市场可能如何传导：利率较高时，债务融资回购成本更高；SBC 稀释如果不能被高 ROIC 增长抵消，市场可能降低估值倍数。
- 仍需核验或观察：SBC 占收入比例是否下降，回购是否超过稀释，non-GAAP 调整是否扩大，债务融资是否提高财务风险。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| GAAP | 美国通用会计准则 | 公司正式财务报表遵循的会计规则 | 是利润和费用的正式基准 |
| Non-GAAP | 非 GAAP 指标 | 公司在 GAAP 之外提供的调整后指标 | 有助观察经营，但必须看调整项 |
| Stock-based Compensation | 股权激励费用 | 用股票、期权或 RSU 支付员工报酬 | 非现金但会稀释股东 |
| RSU | 限制性股票单位 | 满足服务期等条件后交付股票的员工奖励 | 软件公司常用薪酬工具 |
| Dilution | 稀释 | 股数增加使每股权益被摊薄 | 影响每股价值 |
| Diluted EPS | 稀释每股收益 | 考虑潜在股票后的每股收益 | 比 basic EPS 更保守 |
| Share Repurchase | 股票回购 | 公司买回自己的股票 | 可降低股数，也可能只是抵消稀释 |
| Treasury Stock | 库存股 | 公司回购后持有或注销的股票 | 影响股东权益和股数 |
| Net Share Settlement | 净额股票结算 | 股权归属时公司代扣税款等处理 | 会产生税款现金流 |
| Convertible Notes | 可转换债 | 可在条件下转换成股票的债务 | 同时影响债务和潜在稀释 |
| Capped Calls | 上限看涨期权结构 | 用来减少可转债转换稀释的工具 | Snowflake 等公司会用于稀释管理 |
| Owner Earnings | 股东视角现金收益 | 股东真正能长期拥有的现金创造能力 | 防止被 FCF 和回购表象误导 |

## 回顾提示

- 学到本课前建议回顾：第 25 课 EPS 与稀释、第 29 课自由现金流、第 32 课 WACC、第 40 课 SaaS 现金流质量。
- 本课哪些内容会在后续课程继续使用：三表预测、每股自由现金流、回购收益率、资本配置和估值倍数。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 23 课营业费用、第 35 课增长质量。

## 案例拆解

- 案例对象：Datadog、Snowflake、Salesforce 与 Adobe 的 SBC、Non-GAAP、回购和稀释对照。
- 已确认事实：
  - Datadog Q1 2026 SBC 为 1.968 亿美元，约占收入 19.6%，non-GAAP operating margin 为 22%。
  - Snowflake Q1 FY2027 SBC 为 4.0247 亿美元，约占收入 29%，GAAP operating loss 为 3.262 亿美元，non-GAAP operating income 为 1.658 亿美元。
  - Salesforce Q1 FY2027 SBC expense 为 8.57 亿美元，common stock repurchased 为 272.48 亿美元，同时发行债务净额为 248.42 亿美元。
  - Adobe Q2 FY2026 stock-based and deferred compensation adjustment 为 5.56 亿美元，稀释股数为 4.02 亿股，低于上年同期 4.29 亿股。
- 来源日期和链接：见本课“来源”。
- 分析推理：Datadog 和 Snowflake 更能说明高成长公司 SBC 对利润和股东稀释的影响；Salesforce 和 Adobe 更能说明成熟软件公司如何用回购、债务和现金流管理每股指标。
- 后续验证指标：SBC margin、basic shares、diluted shares、net share settlement taxes、repurchases、debt issuance、FCF per share、GAAP 与 non-GAAP 差异、员工股权未确认成本和回购价格。

## 个人情境连接

- 对关注清单的启发：看到软件公司 FCF 很高时，要继续查 SBC、股数和回购，而不是只看现金流率。
- 对持仓或基金选择的启发：成长软件基金的“现金流质量”必须穿透到重仓公司的股权激励和稀释。
- 对工作、收入、消费或风险管理的启发：股权激励对员工可能有价值，但也有归属期、股价波动、税务和集中风险，不能把未归属股票当成确定现金收入。

## 结论边界

- 可以确定：SBC 是真实经济成本，虽然不一定是当期现金流出；Non-GAAP 有学习价值，但必须和 GAAP、SBC、股数变化和回购一起看。
- 不能确定：本课不能仅凭一个季度判断某家公司股权激励是否合理，也不能用 SBC margin 单独判断股票贵或便宜。
- 需要继续观察：SBC 占收入比例是否下降，回购是否长期超过稀释，non-GAAP 调整是否收敛，债务融资回购是否增加风险。
- 不构成投资建议的原因：本课只训练利润口径、现金流和股东稀释阅读框架，不推荐买入或卖出任何证券。

## 练习题

1. 为什么 SBC 不是当期现金流出，却仍然可能是股东成本？
2. 一家公司 revenue 为 100，SBC 为 20。SBC margin 是多少？如果公司说 non-GAAP 利润剔除了这 20，你会继续问什么？
3. Snowflake 在 GAAP 下经营亏损，在 non-GAAP 下经营盈利。两个口径各回答什么问题？
4. 为什么回购不一定等于提高股东价值？
5. 如果一家公司 FCF margin 很高，但股数每年也在上升，你会如何调整自己的分析问题？

## 学习交接

- 本课已经完成：把 SaaS 现金流质量推进到股权激励、Non-GAAP、稀释、回购和股东视角现金流。
- 本课最重要的一句话：自由现金流要除以股数看，Non-GAAP 要放回 SBC 看，回购要和债务、价格和稀释一起看。
- 需要复习的关键词：Stock-based Compensation、RSU、GAAP、Non-GAAP、Dilution、Diluted EPS、Share Repurchase、Treasury Stock、Convertible Notes、Owner Earnings。
- 还不稳定、下次要回看的地方：如何把收入增长、客户数、价格、用量、毛利率、SBC 和自由现金流放进一个简化预测模型。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第四十二课：收入增长拆解、价格、用量、客户数与三表预测入门。
- 学习目标：理解公司收入增长可以来自客户数、价格、用量、产品组合、汇率和并购，并学会把收入驱动连接到毛利、费用、现金流和每股指标。
- 建议案例：继续使用 Salesforce、Snowflake、Datadog、Adobe，可加入 Microsoft 或 Apple 作成熟公司对照，但必须重新核验最新 SEC/IR 披露。
- 必须解释的关键词：Revenue Driver、Price、Volume、Usage、Customer Count、Product Mix、FX、Organic Growth、Acquired Growth、Forecast、Three-statement Model。
- 下节课开始前需要联网核验的数据：最新 SEC/IR 披露中的 revenue by segment、customer metrics、constant currency growth、organic vs acquired growth、gross margin、operating expenses、cash flow 和 share count。

## 来源

- Datadog Form 8-K exhibit 99.1, 2026-05-07: https://www.sec.gov/Archives/edgar/data/1561550/000162828026031677/ex-991x20260331x8k.htm
- Datadog Form 10-Q, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/1561550/000162828026032328/ddog-20260331.htm
- Snowflake Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000027/fy2027q1earnings.htm
- Snowflake Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1640147/000164014726000030/snow-20260430.htm
- Salesforce Form 8-K exhibit 99.1, 2026-05-27: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000125/crm-q1fy27xexhibit991.htm
- Salesforce Form 10-Q, period ended 2026-04-30: https://www.sec.gov/Archives/edgar/data/1108524/000110852426000127/crm-20260430.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-29: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
