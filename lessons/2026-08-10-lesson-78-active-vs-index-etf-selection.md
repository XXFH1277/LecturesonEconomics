# 第七十八课：主动 ETF 与指数 ETF 的选择入门：主动管理、透明持仓、费用率、换手率、税务效率与基准偏离

## 基本信息

- 日期：2026-08-10
- 数据截至：2026-08-10（Asia/Shanghai）。ETF 监管和投资者教育材料采用 SEC/Investor.gov 当前可访问页面；SPY 案例采用 State Street 官方页面 2026-08-10 基金信息、2026-08-07 NAV/市场价格和 2026-08-06 持仓数据；VTI 案例采用 Vanguard 官方页面 2026-07-07 价格、2026-06-30 30-day SEC yield、2026-05-31 组合和 2025 财年换手率数据；主动 ETF 案例采用 J.P. Morgan 2025-11-01 prospectus、2025-12-31 shareholder report、ARK 官方页面和费用说明；利率背景采用 Federal Reserve H.15 2026-08-07 发布、数据截至 2026-08-06。
- 主题：如何区分主动 ETF 和指数 ETF，以及为什么选择 ETF 时不能只看“主动/被动”标签。
- 学习目标：理解 active ETF、index ETF、benchmark、active share、active return、tracking difference、turnover、expense ratio、portfolio transparency、creation/redemption、capital gains distribution 和 tax efficiency。
- 相关资产：SPDR S&P 500 ETF Trust（SPY）、Vanguard Total Stock Market ETF（VTI）、JPMorgan Equity Premium Income ETF（JEPI）、JPMorgan Active Value ETF（JAVA）、ARK Innovation ETF（ARKK）。
- 核心来源：
  - Investor.gov, Exchange-Traded Funds (ETFs): https://www.investor.gov/introduction-investing/investing-basics/investment-products/mutual-funds-and-exchange-traded-2
  - Investor.gov, Active Fund or Actively Managed Fund: https://www.investor.gov/introduction-investing/investing-basics/glossary/active-fund-actively-managed-fund
  - Investor.gov, Index Funds: https://www.investor.gov/introduction-investing/investing-basics/investment-products/mutual-funds-and-exchange-traded-4
  - State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - Vanguard, Vanguard Total Stock Market ETF (VTI): https://investor.vanguard.com/investment-products/etfs/profile/vti
  - SEC EDGAR, J.P. Morgan Exchange-Traded Fund Trust prospectus dated 2025-11-01: https://www.sec.gov/Archives/edgar/data/1485894/000119312525261032/d96835d497.htm
  - SEC EDGAR, J.P. Morgan ETF shareholder report for period ended 2025-12-31: https://www.sec.gov/Archives/edgar/data/1485894/000119312526085186/R2.htm
  - ARK, ARK Innovation ETF (ARKK): https://www.ark-funds.com/funds/arkk
  - ARK Help Center, ARK management fee / expense ratio: https://helpcenter.ark-funds.com/what-is-arks-management-fee-expense-ratio
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-08-07: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课已经把收益型 ETF 推进到税后总回报和账户位置。今天换一个更基础、但更容易被营销话术带偏的问题：

```text
主动 ETF 一定更聪明吗？
指数 ETF 一定更安全、更便宜、更分散吗？
```

答案都不是。

主动 ETF 和指数 ETF 首先是两种“谁来决定持仓”的机制：

```text
指数 ETF：主要跟随一个公开或半公开的指数规则。
主动 ETF：主要依赖投资顾问或投资团队的判断。
```

ETF 只是外壳。真正要比较的是：

```text
我买到什么暴露？
这个暴露由谁决定？
成本是多少？
换手和税务会不会拖累复利？
持仓是否透明？
它和我已有组合重不重叠？
```

### 参考的教材式概念顺序

1. ETF shell：ETF 外壳，指基金份额在交易所交易，同时基金内部持有证券或其他资产。
2. Index ETF：指数 ETF，目标是追踪某个市场指数。
3. Active ETF：主动 ETF，由投资顾问根据策略主动选择或调整持仓。
4. Benchmark：基准，用来比较基金表现和风险的参照物。
5. Active return：主动回报，基金相对基准的超额或落后。
6. Tracking difference：跟踪差异，基金回报和指数回报的差距。
7. Active share：主动份额，组合与基准成分和权重不同的程度。
8. Turnover：换手率，组合买卖频率。
9. Expense ratio：费用率，基金每年从资产中扣除的经营费用比例。
10. Portfolio transparency：持仓透明度，投资者能否及时看到基金到底持有什么。
11. Creation/redemption：申购赎回机制，授权参与者用一篮子证券或现金与 ETF 交换基金份额。
12. Capital gains distribution：资本利得分配，基金卖出获利证券后可能向投资者分配的税务事件。

### 核心概念

主动 ETF 的核心不是“经理更努力”，而是“投资顾问有权偏离指数”。这种偏离可能带来超额回报，也可能带来更高费用、更高换手、更高税务拖累和更大基准偏离。

指数 ETF 的核心也不是“没有风险”，而是“规则先定好”。如果指数本身是市值加权，涨得越大的公司权重越高；如果指数集中在单一行业、主题或少数大公司，指数 ETF 也会集中。

最小比较框架可以写成：

| 问题 | 指数 ETF 重点 | 主动 ETF 重点 |
| --- | --- | --- |
| 持仓从哪里来 | 指数方法论 | 投资团队判断 |
| 成本从哪里来 | 费用率、交易成本、跟踪误差 | 费用率、研究成本、交易成本、换手 |
| 主要风险 | 指数集中、跟踪差异、市场下跌 | 管理人判断错误、风格漂移、税务拖累 |
| 透明度 | 通常看指数规则和基金持仓 | 看基金是否每日披露、是否半透明、是否有模型组合 |
| 适合角色 | 常用于核心暴露 | 常用于卫星、替代、收入或特定风格 |

### 用自己的话解释

可以把 ETF 想成一辆公交车：

```text
指数 ETF：路线图提前写好，司机主要按路线开。
主动 ETF：司机有更多选择路线的空间，但必须遵守招募说明书写下的目的地和限制。
```

指数 ETF 的问题是：路线图可能本来就偏向某些大公司、行业或国家。

主动 ETF 的问题是：司机可能判断对，也可能判断错；即使判断方向对，费用、换手、税务和交易时机也会影响乘客最后到达的财富结果。

### 常见误区

- 误区一：主动 ETF 一定比指数 ETF 更能赚钱。主动基金表现依赖管理人能力、市场环境、费用和税务，不是标签决定结果。
- 误区二：指数 ETF 一定分散。市值加权指数可能高度集中在少数大公司或行业。
- 误区三：费用率小到可以忽略。长期复利中，费用率、交易成本和税务拖累会累积。
- 误区四：高 active share 一定好。偏离基准越大，只说明不同，不说明更好。
- 误区五：ETF 都天然税优。ETF 的实物申购赎回机制有助于降低资本利得分配，但高换手、衍生品、现金赎回或特殊策略仍可能产生税务影响。

## 第二大板块：实时背景与市场传导

### 发生了什么

Investor.gov 的 ETF 页面说明，ETF 通常注册为 1940 Act 下的开放式投资公司或单位投资信托，基金会把投资者的钱汇集起来持有股票、债券、短期货币市场工具或其他资产。ETF 在交易所按 market price 买卖，交易价格可能高于或低于 NAV。Investor.gov 同一页面还提示，许多 ETF 通过实物交换买卖组合证券，通常比共同基金有更少资本利得分配，但这不是无条件保证。

Investor.gov 对主动基金的定义是：主动基金依赖投资顾问构建和管理组合，目标可能是获得某类暴露或跑赢基准；顾问可以不按指数成分买卖，但必须符合基金投资目标和策略。该页面同时提醒，主动管理通常费用更高，更频繁买卖可能增加换手成本和税务后果。

Investor.gov 对指数基金的定义是：指数基金试图追踪市场指数回报。指数基金可能持有指数全部成分，也可能用抽样方法；市值加权指数会让市值更大的公司占更高权重。Investor.gov 也提醒，指数基金仍有缺乏灵活性、跟踪误差和扣费后跑输指数的风险。

State Street 官方 SPY 页面显示，SPY 的基准是 S&P 500 Index，2026-08-10 基金信息列示 gross expense ratio 为 0.0945%；2026-08-06 的基金特征显示持仓数量为 504，30-day SEC yield 为 0.94%；2026-08-06 的前十大持仓中 NVIDIA 为 8.00%、Apple 为 6.92%、Microsoft 为 5.60%；信息技术行业权重为 37.64%。这说明指数 ETF 也会随着市值变化产生明显大公司和行业权重。

Vanguard 官方 VTI 页面显示，VTI 是 index management style，目标是追踪 CRSP US Total Market Index；费用率为 0.03%（截至 2026-04-28），30-day SEC yield 为 1.02%（截至 2026-06-30），2025 财年换手率为 2.6%，2026-05-31 持股数量为 3,484。VTI 的例子说明，全市场指数 ETF 的成本和换手可以很低，但它仍然受美国股票整体估值、行业集中和市场下跌影响。

J.P. Morgan 2025-11-01 prospectus 显示，JEPI 的目标是 current income，同时保持 capital appreciation 前景；其年度经营费用为 0.35%。同一文件说明 JEPI 通过主动管理股票组合，并通过 ELN 卖出与 S&P 500 Total Return Index 相关的看涨期权敞口。J.P. Morgan 2025-12-31 shareholder report 显示，JEPI 当期基金净资产约 415.82 亿美元、持仓数量 125、portfolio turnover rate 93%。这些数字说明，主动 ETF 可以规模很大，也可以有显著换手和衍生品结构。

J.P. Morgan Active Value ETF（JAVA）提供了另一种主动 ETF 案例。J.P. Morgan prospectus 显示，JAVA 目标是 long-term capital appreciation，年度经营费用为 0.44%，最近财年 portfolio turnover 为 111%，策略主要是投资顾问认为估值有吸引力且有长期增长潜力的股票，并采用 bottom-up stock selection。它和 JEPI 都是主动 ETF，但一个偏价值选股，一个偏权益收益和期权/ELN overlay，不能只看“active ETF”四个字。

ARK 官方 ARKK 页面显示，ARKK 是 actively managed ETF，目标是 long-term growth of capital，并通常至少把 65% 资产投资于与 disruptive innovation 主题相关的国内外股票。ARK 费用说明页面显示，ARK 的主动 ETF 年度 expense ratio 通常为 0.75%，ARKW 为 0.88%。ARKK 页面也明确提示，组合比 broad market averages 更波动，并有管理、非分散、行业、外国证券和主题相关风险。

利率背景仍要纳入比较。Federal Reserve H.15 2026-08-07 发布的表格显示，2026-08-06 effective federal funds rate 为 3.63%，3-month Treasury bill 二级市场利率为 3.74%，10-year Treasury constant maturity 为 4.69%。当现金和短债仍有可观察收益时，主动 ETF 必须解释自己承担的股票、行业、衍生品、管理人和税务风险，是否有足够补偿。

### 为什么重要

同样叫 ETF，经济含义可能完全不同：

```text
SPY：跟踪 S&P 500，核心问题是美国大盘股和市值加权集中。
VTI：跟踪美国全市场，核心问题是全市场股票风险和美国市场集中。
JEPI：主动股票组合 + ELN/covered call 机制，核心问题是收入、上行让渡、换手、税务和 ELN 风险。
JAVA：主动价值选股，核心问题是管理人选股、价值风格和基准偏离。
ARKK：主动创新主题，核心问题是主题判断、集中度、波动和非分散风险。
```

主动/指数只是第一层分类，不能替代完整尽调。

### 本节采用的数据和来源

- ETF 监管结构、交易价格与 NAV、资本利得分配：Investor.gov ETF 页面。
- 主动基金定义、管理人依赖、费用和换手风险：Investor.gov active fund 页面。
- 指数基金定义、市值加权、跟踪误差和费用影响：Investor.gov index funds 页面。
- SPY 费用率、持仓数量、前十大持仓、行业权重、溢价折价和总回报口径：State Street 官方页面。
- VTI 管理风格、费用率、SEC yield、换手率、持股数量和分配记录：Vanguard 官方页面。
- JEPI/JAVA 目标、费用、换手、策略和风险：J.P. Morgan prospectus 与 shareholder report。
- ARKK 主动管理、主题范围、费用和风险：ARK 官方页面与帮助中心。
- 利率背景：Federal Reserve H.15。

### 这些现实事件如何连接理论

ETF 选择的传导链可以写成：

```text
产品目标
-> 持仓决定方式
-> 基准和偏离
-> 费用率和换手率
-> 税务和交易成本
-> NAV / market price 总回报
-> 个人组合里的角色
```

市场上涨时，指数 ETF 可能因为低成本和宽暴露显得有效；市场风格分化时，主动 ETF 可能通过选股、低波动、收益或主题判断与指数拉开差异；市场急跌时，主动管理也不保证防守成功。最终比较的是“扣除成本和税务后的风险调整结果”，不是产品标签。

### 至少一个实时新闻、往期事件或真实市场机制案例

本课采用 SPY、VTI、JEPI、JAVA、ARKK 五只 ETF 做真实机制案例。

SPY 和 VTI 都是指数 ETF，但 SPY 是 S&P 500 大盘股暴露，VTI 是美国全市场暴露；两者都低成本，但前十大持仓和信息技术权重会随着美国股票市值变化而集中。

JEPI、JAVA 和 ARKK 都是主动 ETF，但三者不是同一种主动：JEPI 的重点是权益收益和 ELN/期权结构，JAVA 的重点是价值选股，ARKK 的重点是 disruptive innovation 主题。主动 ETF 的尽调必须进入 prospectus、shareholder report、持仓披露和费用表，而不是只看基金名称。

## 政治、制度和规则视角

### 涉及的政策、监管、制度或国际关系

- 1940 Act 投资公司监管框架：决定大多数注册 ETF 的基金治理、估值、托管和投资者保护。
- SEC/Investor.gov 投资者教育：要求投资者阅读 prospectus 和 shareholder report。
- ETF 申购赎回制度：授权参与者通过 creation/redemption 维持 ETF 市价与 NAV 之间的联系。
- 税务制度：资本利得分配、股息分配、应税账户和税优账户会改变投资者真实回报。
- 信息披露制度：主动 ETF、指数 ETF、半透明 ETF 的持仓披露频率和细节会影响投资者核验能力。

### 已确认事实

- ETF 可以在交易所按市场价格交易，市场价格可能偏离 NAV。
- 指数 ETF 目标是追踪指数，但仍会有费用、交易成本、跟踪误差和指数集中风险。
- 主动 ETF 可偏离指数，但表现依赖管理人能力、费用、换手、市场环境和税务结果。
- SPY、VTI、JEPI、JAVA、ARKK 在策略、费用率、换手率、透明度和风险来源上明显不同。
- 截至 2026-08-06，美国短端利率和 10 年期国债收益率仍为所有股票 ETF 选择提供机会成本背景。

### 市场可能如何传导

如果投资者重新偏好低成本核心暴露，资金可能流向宽基指数 ETF；如果市场风格分化、收益需求上升或主题叙事升温，资金可能流向主动 ETF、收益型 ETF 或主题 ETF。基金公司会围绕低费用、主动能力、税务效率、日披露、半透明结构和期权收益设计更多产品。

### 仍需核验或观察

- 主动 ETF 的年度报告和 shareholder report 是否显示持续超额收益。
- 换手率是否持续偏高，以及是否带来资本利得分配。
- ETF 的日常溢价/折价、bid-ask spread 和成交量是否稳定。
- 指数 ETF 的大公司权重是否继续集中。
- 利率下行或上行时，投资者是否重新在现金、债券、指数 ETF 和主动 ETF 之间切换。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Active ETF | 主动 ETF | 投资顾问主动选择或调整持仓的 ETF | 决定风险来自管理人判断 |
| Index ETF | 指数 ETF | 追踪某个指数的 ETF | 决定风险主要来自指数规则和市场暴露 |
| Benchmark | 基准 | 用来比较表现和风险的参照指数 | 没有基准就很难判断好坏 |
| Active Share | 主动份额 | 组合和基准不同的程度 | 衡量偏离，但不代表能力 |
| Active Return | 主动回报 | 基金相对基准的回报差 | 判断主动管理是否创造价值 |
| Tracking Difference | 跟踪差异 | 基金回报和指数回报之间的差 | 指数 ETF 尽调核心 |
| Turnover | 换手率 | 一年内组合买卖频率 | 影响交易成本和税务 |
| Expense Ratio | 费用率 | 基金每年扣除的经营费用 | 长期复利中影响很大 |
| Portfolio Transparency | 持仓透明度 | 投资者能否及时看到基金持仓 | 影响核验和风险识别 |
| Creation/Redemption | 申购赎回 | 授权参与者与 ETF 交换篮子证券或现金 | 影响溢价折价和税务效率 |
| Capital Gains Distribution | 资本利得分配 | 基金实现并分给投资者的资本利得 | 应税账户可能即刻纳税 |
| Tax Efficiency | 税务效率 | 投资策略减少非必要税务拖累的能力 | 税后回报比税前回报更接近真实结果 |

## 回顾提示

- 学到本课前建议回顾：可回顾第 4 课基金和 ETF 入门、第 48 课持仓穿透和指数方法论、第 49 课 ETF 交易机制、第 50 课基金表现归因、第 76-77 课税后总回报。
- 本课哪些内容会在后续课程继续使用：benchmark、active return、turnover、tax efficiency、portfolio transparency 和 ETF 尽调表。
- 如果看不懂本课，可以先回到：第 52 课基金组合构建和第 53 课基金风险指标。

## 案例拆解

### 案例对象

SPY、VTI、JEPI、JAVA、ARKK。

### 已确认事实

- SPY 跟踪 S&P 500 Index，gross expense ratio 为 0.0945%，2026-08-06 持仓数量为 504，信息技术权重为 37.64%。
- VTI 是指数管理风格，追踪 CRSP US Total Market Index，expense ratio 为 0.03%，2025 财年换手率为 2.6%，2026-05-31 持股数量为 3,484。
- JEPI 是主动 ETF，目标是 current income 和 capital appreciation；2025-11-01 prospectus 显示 expense ratio 为 0.35%，2025-12-31 shareholder report 显示净资产约 415.82 亿美元、持仓数量 125、portfolio turnover rate 93%。
- JAVA 是主动 ETF，目标是 long-term capital appreciation；expense ratio 为 0.44%，最近财年换手率为 111%。
- ARKK 是主动 ETF，目标是 long-term growth of capital，投资 disruptive innovation 主题；ARK 说明其主动 ETF 通常 expense ratio 为 0.75%，ARKK 页面提示更高波动和非分散等风险。

### 来源日期和链接

- State Street SPY official page, fund information as of 2026-08-10 and holdings as of 2026-08-06: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Vanguard VTI official page, data shown across 2026-04-28, 2026-05-31, 2026-06-30 and 2026-07-07: https://investor.vanguard.com/investment-products/etfs/profile/vti
- SEC EDGAR, J.P. Morgan prospectus dated 2025-11-01: https://www.sec.gov/Archives/edgar/data/1485894/000119312525261032/d96835d497.htm
- SEC EDGAR, J.P. Morgan shareholder report for period ended 2025-12-31: https://www.sec.gov/Archives/edgar/data/1485894/000119312526085186/R2.htm
- ARK ARKK official page and ARK fee help center: https://www.ark-funds.com/funds/arkk and https://helpcenter.ark-funds.com/what-is-arks-management-fee-expense-ratio

### 分析推理

SPY 和 VTI 可以作为低成本指数 ETF 的入门样本，但它们并不代表“无风险”。SPY 的大公司和信息技术权重说明，市值加权指数会随赢家变大而集中；VTI 覆盖更宽，但美国股票市场本身仍可能集中在少数大型公司和行业。

JEPI、JAVA 和 ARKK 则说明主动 ETF 不是一个单一类别。JEPI 的主要问题是收入、ELN、期权上行让渡和税务；JAVA 的主要问题是价值选股是否跑赢基准；ARKK 的主要问题是创新主题、集中度、波动和管理人判断。比较它们时，必须先问“这只基金在组合里承担什么任务”。

### 后续验证指标

- 每只 ETF 的年度费用、换手率、持仓数量和前十大持仓变化。
- 基金相对基准的 1 年、3 年、5 年、10 年回报和税后回报。
- 应税账户中的资本利得分配、普通股息、合格股息和 ROC。
- bid-ask spread、premium/discount、成交量和极端波动日的交易质量。
- 是否出现风格漂移：主动 ETF 是否偏离原先承诺的目标。

## 个人情境连接

- 对关注清单的启发：每只 ETF 至少记录“指数/主动、基准、费用率、换手率、持仓数量、前十大权重、分配税性、溢价折价”八个字段。
- 对持仓或基金选择的启发：核心仓位通常先问是否需要低成本宽暴露；卫星仓位才问是否愿意为主动能力、主题暴露或收益结构付费。
- 对工作、收入、消费或风险管理的启发：不要把主动 ETF 当成“专业人士替我负责”，也不要把指数 ETF 当成“闭眼不看”。责任仍然在于理解自己买到的风险。

## 结论边界

- 可以确定：主动 ETF 和指数 ETF 的关键差异在持仓决定方式、费用、换手、透明度、税务和基准偏离；ETF 外壳本身不消除市场风险。
- 不能确定：任何主动 ETF 未来能否跑赢基准，任何指数 ETF 未来能否提供正回报。
- 需要继续观察：主动策略是否持续有效、指数集中度是否加深、利率和风险偏好是否改变资金流向、资本利得分配是否出现。
- 不构成投资建议的原因：本课只提供 ETF 尽调框架和来源核验训练，不评价任何 ETF 是否适合买入、卖出或持有。

## 练习题

1. 用一句话区分 active ETF 和 index ETF，不要使用“好”或“坏”。
2. 如果一只主动 ETF 的费用率是 0.75%，一只指数 ETF 的费用率是 0.03%，主动 ETF 至少要在哪些方面证明自己值得更高成本？
3. 找一只 ETF 的官方页面，记录它的 benchmark、expense ratio、turnover、holdings count 和 top 10 concentration。
4. 为什么指数 ETF 也可能出现行业集中风险？请用市值加权解释。
5. 如果你在应税账户持有主动 ETF，为什么要特别看换手率和资本利得分配历史？

## 学习交接

- 本课已经完成：把 ETF 选择从“主动还是被动”推进到基准、费用、换手、透明度、税务效率、持仓集中和组合角色。
- 本课最重要的一句话：主动/指数只是起点，真正要比较的是扣除费用、交易、税务之后，你买到的风险暴露是否适合自己的目标。
- 需要复习的关键词：Active ETF、Index ETF、Benchmark、Active Share、Turnover、Expense Ratio、Portfolio Transparency、Creation/Redemption、Tax Efficiency。
- 还不稳定、下次要回看的地方：主动 ETF 的持续超额收益、指数 ETF 的集中度变化、换手和资本利得分配是否抬升税务拖累。
- 适合下次打开仓库先读的文件：`lessons/2026-08-10-lesson-79-factor-smart-beta-etf-exposure-risk.md`

## 下节课安排

- 建议主题：第七十九课：因子 ETF 与 Smart Beta 入门：质量、动量、价值、规模、低波动、指数规则与暴露风险。
- 学习目标：理解 factor、smart beta、parent index、factor score、sector neutral、rebalance、factor crowding、active risk、tracking difference 和 valuation exposure。
- 建议案例：对比 iShares QUAL、MTUM、LRGF 和 MSCI 质量因子指数，训练“基金名称 -> 指数方法论 -> 持仓权重 -> 估值和换手”的读表顺序。
- 必须解释的关键词：Factor、Smart Beta、Quality、Momentum、Value、Size、Minimum Volatility、Sector Neutral、Rebalance、Factor Crowding。
- 下节课开始前需要联网核验的数据：iShares 因子 ETF 官方页面、MSCI 指数页面和方法论、费用率、持仓数量、行业权重、P/E、换手率和分配历史。

## 来源

- Investor.gov, Exchange-Traded Funds (ETFs): https://www.investor.gov/introduction-investing/investing-basics/investment-products/mutual-funds-and-exchange-traded-2
- Investor.gov, Active Fund or Actively Managed Fund: https://www.investor.gov/introduction-investing/investing-basics/glossary/active-fund-actively-managed-fund
- Investor.gov, Index Funds: https://www.investor.gov/introduction-investing/investing-basics/investment-products/mutual-funds-and-exchange-traded-4
- State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- Vanguard, Vanguard Total Stock Market ETF (VTI): https://investor.vanguard.com/investment-products/etfs/profile/vti
- SEC EDGAR, J.P. Morgan Exchange-Traded Fund Trust prospectus dated 2025-11-01: https://www.sec.gov/Archives/edgar/data/1485894/000119312525261032/d96835d497.htm
- SEC EDGAR, J.P. Morgan ETF shareholder report for period ended 2025-12-31: https://www.sec.gov/Archives/edgar/data/1485894/000119312526085186/R2.htm
- ARK, ARK Innovation ETF (ARKK): https://www.ark-funds.com/funds/arkk
- ARK Help Center, ARK management fee / expense ratio: https://helpcenter.ark-funds.com/what-is-arks-management-fee-expense-ratio
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
