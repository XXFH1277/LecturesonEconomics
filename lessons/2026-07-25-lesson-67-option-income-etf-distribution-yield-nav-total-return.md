# 第六十七课：期权收益型 ETF 读表入门：Distribution Yield、SEC Yield、NAV 与总回报边界

## 基本信息

- 日期：2026-07-25
- 数据截至：2026-07-25（Asia/Shanghai）。Federal Reserve H.15 最新发布日为 2026-07-24、数据截至 2026-07-23；J.P. Morgan JEPI fact sheet 数据截至 2026-06-30；Global X QYLD 产品页采用 2026-07-21 可访问数据；Global X QYLD fact sheet 数据截至 2026-05-31；SEC、Investor.gov、Global X tax primer 页面采用当前可访问版本。
- 主题：为什么“每月分配”和“高分配率”不等于确定收益，也不等于总回报。
- 学习目标：理解 distribution rate、30-day SEC yield、trailing 12-month distribution、return of capital、NAV、market price、premium/discount、bid-ask spread、total return、after-tax return 和 NAV erosion。
- 相关资产：QYLD、JEPI、Nasdaq-100、S&P 500、短端美债、现金管理工具、期权权利金、ELN。
- 核心来源：
  - SEC Investor.gov, Updated Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-24
  - SEC Investor.gov, Mutual Fund and ETF Fees and Expenses: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/mutual-fund-and-etf-fees-and-expenses-investor-bulletin
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-24: https://www.federalreserve.gov/releases/h15/
  - Global X, QYLD official product page: https://www.globalxetfs.com/funds/QYLD
  - Global X, QYLD fact sheet, 2026-05-31: https://assets.globalxetfs.com/funds/documents/qyld/Fact-Sheet_QYLD.pdf
  - Global X, Tax Primer for Global X Covered Call ETFs, June 2024: https://assets-cms.globalxetfs.com/Covered_Call_Tax_Primer_2024_1a1a7f27df.pdf
  - SEC EDGAR, Global X NASDAQ 100 Covered Call ETF 2026 Summary Prospectus: https://www.sec.gov/Archives/edgar/data/1432353/000143235326000239/a497knasdaq100coveredcall.htm
  - J.P. Morgan Asset Management, JPMorgan Equity Premium Income ETF fact sheet, 2026-06-30: https://am.jpmorgan.com/content/dam/jpm-am-aem/americas/us/en/literature/fact-sheet/etfs/FS-JEPI.pdf
  - SEC EDGAR, JPMorgan Equity Premium Income ETF 2026 prospectus supplement: https://www.sec.gov/Archives/edgar/data/1485894/000119312526079345/d59352d497k.htm

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

今天从一个最常见的误读开始：

> 一个期权收益型 ETF 写着 10% 左右的分配率，是不是就等于我一年赚 10%？

不是。现金分配、收益率口径、税务性质和总回报是四件事。期权收益型 ETF 可能每月分配现金，但你的财富变化还要看 NAV 或市场价格有没有下跌、分配是不是资本返还、税后结果如何、交易成本是多少，以及你是否牺牲了标的上涨空间。

本课的核心是把“看到现金到账”拆成三层：

```text
现金流：我收到了多少分配？
经济结果：NAV/市场价格加分配后的总回报是多少？
税务性质：这笔分配是股息、短期资本利得、长期资本利得，还是 return of capital？
```

### 参考的教材式概念顺序

1. Distribution：基金分配，基金向持有人支付现金。
2. Distribution Rate：分配率，通常把最近一次分配年化后除以 NAV 或价格。
3. Trailing 12-Month Distribution：过去 12 个月分配率，把近 12 个月实际分配合计和当前 NAV 联系起来。
4. 30-Day SEC Yield：SEC 标准化收益率口径，用近 30 天净投资收入估算年化收益。
5. Return of Capital：资本返还，把一部分投资本金以分配形式返还给投资者。
6. NAV：基金净值，每份基金对应的资产减负债。
7. Market Price：二级市场成交价，ETF 买卖时用的是市场价格，不一定等于 NAV。
8. Premium/Discount：溢价/折价，市场价格高于或低于 NAV。
9. Bid-Ask Spread：买卖价差，买入价和卖出价之间的交易成本。
10. Total Return：总回报，把价格或 NAV 变化和分配再投资一起看。
11. NAV Erosion：净值侵蚀，若分配长期超过组合可持续收益，NAV 可能被持续消耗。
12. After-Tax Return：税后回报，分配的税务性质会改变实际结果。

### 核心概念

同一只基金可能同时出现这些数字：

```text
30-day SEC yield：标准化净投资收入估算
distribution rate：最近分配年化后的现金分配口径
trailing 12-month distribution：过去 12 个月分配合计口径
NAV return：按基金净值计算的总回报
market price return：按二级市场价格计算的总回报
after-tax return：考虑分配税务性质后的结果
```

这些数字都不是“错”，但回答的问题不同。初学者最容易犯的错误，是把 distribution rate 当成银行利率，把月度分配当成不会损失本金的现金流。

### 用自己的话解释

假设一个基金净值 100 元，一年中分配了 10 元现金。你不能立刻说赚了 10%。还要看年末净值：

```text
年初 NAV：100
全年分配：10
年末 NAV：95
简单总结果：95 + 10 - 100 = +5
```

这时你收到 10 元现金，但经济结果不是 10 元，而是 5 元。若年末 NAV 变成 85，则即使现金分配是 10 元，总结果仍是亏损。期权收益型 ETF 的读表顺序必须先看总回报，再看分配。

### 常见误区

- 误区一：分配率等于收益率。分配率描述现金支付，不自动描述财富增长。
- 误区二：30-day SEC yield 和 distribution rate 应该差不多。它们口径不同，期权策略产品可能差异很大。
- 误区三：return of capital 一定坏。税务上的资本返还可能有不同原因，但它至少提醒你不能把全部分配都理解成经营收入或债券利息。
- 误区四：市场价和 NAV 差不多就不用看。压力市场、流动性不足或交易时间错配时，premium/discount 和 bid-ask spread 都可能影响买卖结果。
- 误区五：高分配可以替代现金。期权收益型 ETF 承担股票、期权、波动率、流动性和税务风险，不能和 T-Bill 或银行存款机械比较。

## 第二大板块：实时背景与市场传导

### 发生了什么

Global X QYLD 产品页 2026-07-21 数据显示，QYLD 的 30-day SEC yield 为 0.03%，trailing 12-month distribution 为 12.48%，distribution rate 为 11.71%，分配频率为 monthly。关键不是这三个数字谁更好看，而是它们明显不是同一个口径。该产品页还提示，trailing 12-month distribution 和 distribution rate 估计包含 return of capital，且这些数值不代表未来分配率；distribution rate 也不代表基金总回报。

Global X QYLD fact sheet 2026-05-31 数据显示，QYLD 的 total expense ratio 为 0.60%，30-day SEC yield 为 0.05%，12-month trailing distribution 为 12.12%；同一文件解释，QYLD 写 Nasdaq-100 指数 covered call，卖出 covered call 会限制标的指数超过行权价后的上行，但仍承受指数下跌风险。

J.P. Morgan JEPI fact sheet 2026-06-30 数据显示，JEPI 的 value of investments 为 44.75 billion dollars，gross/net expenses 为 0.350%，30-day SEC yield 为 8.20%，12-month rolling dividend yield 为 8.06%；同页 total return 表显示，JEPI 1-year NAV total return 为 7.77%，market price return 为 7.66%。这说明即使同一只基金，同一份资料中也要把 yield、dividend yield 和 total return 分开读。

Federal Reserve H.15 2026-07-24 release 显示，截至 2026-07-23，effective federal funds rate 为 3.63%，4-week Treasury bill secondary market rate 为 3.73%，3-month Treasury bill secondary market rate 为 3.81%，10-year Treasury constant maturity 为 4.71%。这给“现金收益”和“承担股票加期权风险去换分配”的比较提供背景，但不能把期权 ETF 和 T-Bill 当作同一风险等级。

SEC Investor.gov 的 ETF bulletin 提醒：ETF 要每日计算 NAV，但 ETF 份额在交易所按市场价格交易，市场价格可能高于或低于 NAV；投资者还要阅读 summary prospectus、full prospectus、NAV、closing market price、premium/discount、holdings 和 median bid-ask spread。

### 为什么重要

期权收益型 ETF 的分配可能来自多条路径：

```text
股票股息
卖出期权收到的权利金
期权或股票实现收益
资本返还
组合现金和短债收益
```

不同来源的稳定性、税务性质和风险完全不同。高 distribution rate 可能来自真实收益，也可能部分来自资本返还或前期波动环境；高 30-day SEC yield 可能反映近 30 天净投资收入，但不保证未来持续。总回报才回答“这段时间财富有没有增加”。

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| QYLD 30-day SEC yield | 0.03% | Global X, 2026-07-21 | 标准化收益口径 |
| QYLD trailing 12-month distribution | 12.48% | Global X, 2026-07-21 | 过去分配口径 |
| QYLD distribution rate | 11.71% | Global X, 2026-07-21 | 最近分配年化口径 |
| QYLD 分配提示 | 估计包含 return of capital，不代表未来分配或总回报 | Global X, 2026-07-21 | 防止误读 |
| QYLD expense ratio | 0.60% | Global X fact sheet, 2026-05-31 | 成本 |
| JEPI value of investments | 44.75B 美元 | J.P. Morgan, 2026-06-30 | 产品规模 |
| JEPI expense ratio | 0.350% | J.P. Morgan, 2026-06-30 | 成本 |
| JEPI 30-day SEC yield | 8.20% | J.P. Morgan, 2026-06-30 | 标准化收益口径 |
| JEPI 12-month rolling dividend yield | 8.06% | J.P. Morgan, 2026-06-30 | 分配口径 |
| JEPI 1-year NAV total return | 7.77% | J.P. Morgan, 2026-06-30 | 总回报口径 |
| 4-week / 3-month T-Bill | 3.73% / 3.81% | Fed H.15, 2026-07-23 | 现金收益背景 |
| 10Y Treasury | 4.71% | Fed H.15, 2026-07-23 | 利率和估值背景 |

### 这些现实事件如何连接理论

第一条链：分配率和总回报。

```text
基金卖期权或收到股息
-> 支付月度分配
-> 投资者看见现金到账
-> 但 NAV 可能同时变化
-> 总回报必须把 NAV/价格变化和分配一起算
```

第二条链：高分配和上行封顶。

```text
卖出 call 获得权利金
-> 当期分配可能较高
-> 标的上涨超过行权价时，基金放弃部分上行
-> 牛市中可能落后普通股票指数或普通 ETF
```

第三条链：利率和风险补偿。

```text
短端 T-Bill 有自己的收益率
-> 现金类工具提供低风险收益背景
-> 期权收益型 ETF 需要额外补偿股票、波动率和结构风险
-> 不能只看分配率高于 T-Bill，就认为更划算
```

### 至少一个真实市场机制案例

案例：为什么 QYLD 的 30-day SEC yield 和 distribution rate 可以相差很大。

QYLD 产品页显示 2026-07-21 的 30-day SEC yield 为 0.03%，distribution rate 为 11.71%。这不是简单矛盾，而是口径差异：

```text
30-day SEC yield：
看近 30 天净投资收入的标准化估算，更像“收入口径”。

distribution rate：
把最近一次分配年化后除以 NAV，更像“现金分配速度口径”。

total return：
把 NAV 或市场价格变化和分配再投资一起看，更像“财富结果口径”。
```

Global X 的产品页明确提示，相关分配估计包含 return of capital，distribution rate 不代表 total return。对初学者来说，这句话比高分配率本身更重要。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC ETF 披露规则、Investor.gov 投资者教育、基金 summary prospectus、19a notice、1099 税务文件、交易所二级市场、authorized participant 机制。
- 已确认事实：SEC Investor.gov 要求投资者阅读 prospectus，并关注 NAV、closing market price、premium/discount、holdings 和 bid-ask spread；Global X QYLD 页面提示分配率不是总回报且分配可能包含 return of capital；J.P. Morgan JEPI fact sheet 对 30-day SEC yield 给出标准化定义并提示 ELN 风险。
- 市场可能如何传导：利率影响现金收益背景；波动率影响期权权利金；股票指数上涨可能让 covered call 策略出现机会成本；下跌市场中权利金缓冲可能不足以抵消标的损失。
- 仍需核验或观察：最新 19a notice、年度 tax supplement、Form 1099、daily holdings、ELN exposure、NAV trend、distribution history、after-tax return 和 benchmark relative return。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Distribution | 分配 | 基金向持有人支付的现金 | 现金到账不等于利润 |
| Distribution Rate | 分配率 | 最近分配年化后的比例 | 容易被误读成收益率 |
| 30-Day SEC Yield | 30 日 SEC 收益率 | 标准化净投资收入估算 | 可横向比较但不保证未来 |
| Trailing 12-Month Distribution | 过去 12 个月分配率 | 近 12 个月分配合计口径 | 看历史现金支付 |
| Return of Capital | 资本返还 | 把本金的一部分返还给投资者 | 影响税务和 NAV 理解 |
| NAV | 基金净值 | 每份基金对应资产净值 | 总回报基础 |
| Market Price | 市场价格 | ETF 二级市场成交价 | 买卖实际价格 |
| Premium/Discount | 溢价/折价 | 市场价高于或低于 NAV | 交易成本和退出风险 |
| Bid-Ask Spread | 买卖价差 | 买入报价和卖出报价之间差距 | 隐性交易成本 |
| Total Return | 总回报 | 价格变化加分配再投资 | 判断财富结果 |
| NAV Erosion | 净值侵蚀 | 分配或亏损导致净值长期下降 | 高分配风险信号 |
| After-Tax Return | 税后回报 | 扣除税务影响后的结果 | 分配性质很重要 |
| 19a Notice | 19a 通知 | 基金对分配来源的临时估计说明 | 辨别分配构成 |
| ELN | 股票挂钩票据 | 与股票或指数表现挂钩的票据 | 有流动性和信用风险 |

## 回顾提示

- 学到本课前建议回顾：第 49 课 ETF 交易机制，第 51 课基金风险指标，第 65 课 Greeks，第 66 课期权策略产品化。
- 本课哪些内容会在后续课程继续使用：结构化票据、ELN、autocallable、收益增强产品、下行障碍、税务口径和行为金融中的“现金分配幻觉”。
- 如果看不懂本课，可以先回到：第 54 课现金管理，第 56 课短端利率传导，第 63 课杠杆和路径风险。

## 案例拆解

- 案例对象：QYLD 和 JEPI 的收益口径对比。
- 已确认事实：
  - QYLD 2026-07-21 产品页同时显示 30-day SEC yield、trailing 12-month distribution 和 distribution rate，且提示分配可能包含 return of capital。
  - QYLD 2026 summary prospectus 提示 covered call writing 会让基金放弃标的超过行权价的部分上涨，但仍承受下跌风险。
  - JEPI 2026-06-30 fact sheet 显示 30-day SEC yield、12-month rolling dividend yield 和 1-year NAV total return 是不同口径。
  - JEPI 风险摘要提示 ELN 可能有流动性、信用和交易对手风险。
- 来源日期和链接：见本课“来源”。
- 分析推理：期权收益型 ETF 的核心不是“谁的分配率高”，而是分配来源、总回报、税务性质、标的风险、上行封顶和下行风险是否匹配投资者目标。
- 后续验证指标：分配历史、19a notice、annual tax supplement、NAV 长期趋势、benchmark total return、期权或 ELN 敞口、费用率、premium/discount 和 bid-ask spread。

## 一页期权收益型 ETF 读表顺序

```text
第一步：确认产品目标
- current income？
- total return？
- downside buffer？
- lower volatility？

第二步：确认分配口径
- 30-day SEC yield：
- distribution rate：
- trailing 12-month distribution：
- 分配频率：

第三步：确认总回报
- NAV total return：
- market price total return：
- benchmark total return：
- 是否假设分配再投资：

第四步：确认分配来源
- 股息：
- 期权权利金：
- 实现资本利得：
- return of capital：
- 19a notice 是否可读：

第五步：确认结构风险
- 是否卖 call：
- 是否上行 cap：
- 是否使用 ELN：
- 是否有交易对手风险：
- 下跌时保护是否有限：

第六步：确认交易和税务
- NAV：
- market price：
- premium/discount：
- bid-ask spread：
- expense ratio：
- 税务文件和个人税率：
```

## 个人情境连接

- 对关注清单的启发：给期权收益型 ETF 单独建立字段：分配率、SEC yield、总回报、NAV 变化、分配来源、上行封顶和结构风险。
- 对持仓或基金选择的启发：想要“月度现金流”和想要“长期总回报”不是同一个目标，不能只按分配率排序。
- 对工作、收入、消费或风险管理的启发：真正稳定的现金流要能承受本金波动、税务影响和极端市场；看到账户到账，不代表风险已经结束。

## 结论边界

- 可以确定：distribution rate、30-day SEC yield、trailing distribution 和 total return 是不同口径；期权收益型 ETF 的现金分配不能直接理解成无风险利息；NAV 和市场价格变化必须一起看。
- 不能确定：本课不能预测 QYLD、JEPI、Nasdaq-100、S&P 500、利率、分配率或任何期权策略未来表现。
- 需要继续观察：最新月度分配、19a notice、annual tax supplement、daily holdings、ELN exposure、NAV drawdown、benchmark comparison 和 Fed H.15。
- 不构成投资建议的原因：本课只用于解释基金读表和收益口径，不建议买入、卖出或持有任何 ETF、基金、期权、股票、票据或现金工具。

## 练习题

1. 为什么 distribution rate 不能直接等同于总回报？
2. 如果一个基金分配率 12%，但一年 NAV 下跌 10%，你会怎样粗略估算经济结果？
3. 30-day SEC yield 和 trailing 12-month distribution 分别回答什么问题？
4. 为什么 return of capital 至少提醒投资者不要把全部分配都当成“收入”？
5. 打开一只期权收益型 ETF 的官方页面，记录 NAV、market price、expense ratio、30-day SEC yield、distribution rate、total return 和 risk disclosure。

## 学习交接

- 本课已经完成：把期权策略 ETF 的“产品结构”推进到“收益口径读表”，区分现金分配、SEC yield、NAV、市场价格、总回报和资本返还。
- 本课最重要的一句话：分配是现金流，总回报才是财富结果，税务性质决定到账现金最终留下多少。
- 需要复习的关键词：Distribution Rate、30-Day SEC Yield、Trailing 12-Month Distribution、Return of Capital、NAV、Market Price、Premium/Discount、Bid-Ask Spread、Total Return、NAV Erosion、19a Notice、ELN。
- 还不稳定、下次要回看的地方：ELN 和 structured notes 如何把期权收益、发行人信用、障碍条款和自动赎回包装成票据。
- 适合下次打开仓库先读的文件：`lessons/2026-07-25-lesson-67-option-income-etf-distribution-yield-nav-total-return.md`

## 下节课安排

- 建议主题：第六十八课：结构化票据与 ELN 入门：收益增强、自动赎回、障碍条款与发行人信用风险。
- 学习目标：理解 equity-linked note、structured note、issuer credit risk、autocallable、coupon、barrier、knock-in、principal protection、buffer、participation rate 和 secondary market liquidity。
- 建议案例：使用 SEC/FINRA 投资者教育材料、银行或券商 structured note prospectus、JEPI 对 ELN 风险的披露，解释为什么“票息看起来高”必须同时看发行人信用、标的路径和赎回条款。
- 必须解释的关键词：Structured Note、Equity-Linked Note、Issuer Credit Risk、Autocallable、Coupon、Barrier、Knock-In、Principal Protection、Buffer、Participation Rate、Secondary Market Liquidity。
- 下节课开始前需要联网核验的数据：SEC/FINRA structured products 教育材料、至少一份最新银行结构化票据 prospectus、JEPI 最新 fact sheet 或 prospectus supplement、Fed H.15 利率背景、标的指数近期表现。

## 来源

- SEC Investor.gov, Updated Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-24
- SEC Investor.gov, Mutual Fund and ETF Fees and Expenses: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/mutual-fund-and-etf-fees-and-expenses-investor-bulletin
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- Global X, QYLD official product page: https://www.globalxetfs.com/funds/QYLD
- Global X, QYLD Fact Sheet: https://assets.globalxetfs.com/funds/documents/qyld/Fact-Sheet_QYLD.pdf
- Global X, Tax Primer for Global X Covered Call ETFs: https://assets-cms.globalxetfs.com/Covered_Call_Tax_Primer_2024_1a1a7f27df.pdf
- SEC EDGAR, Global X NASDAQ 100 Covered Call ETF 2026 Summary Prospectus: https://www.sec.gov/Archives/edgar/data/1432353/000143235326000239/a497knasdaq100coveredcall.htm
- J.P. Morgan Asset Management, JPMorgan Equity Premium Income ETF Fact Sheet: https://am.jpmorgan.com/content/dam/jpm-am-aem/americas/us/en/literature/fact-sheet/etfs/FS-JEPI.pdf
- SEC EDGAR, JPMorgan Equity Premium Income ETF 2026 Prospectus Supplement: https://www.sec.gov/Archives/edgar/data/1485894/000119312526079345/d59352d497k.htm
