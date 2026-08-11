# 第八十二课：ETF 组合重叠、风险预算与再平衡入门：核心/卫星、穿透暴露、主题叠加和复查频率

## 基本信息

- 日期：2026-08-11
- 数据截至：2026-08-11（Asia/Shanghai）。ETF 教育和监管框架采用 Investor.gov 与 SEC 当前可访问页面；SPY 和 XLK 案例采用 State Street 官方页面 2026-08-10 持仓、行业、NAV、AUM、买卖价差和溢价折价；SOXX 案例采用 iShares 官方页面 2026-08-10 关键事实和 2026-08-07 行业暴露；AIQ 与 BOTZ 案例采用 Global X 官方页面 2026-08-10 价格、持仓、净资产和 2026-07-31 行业暴露；SGOV 案例采用 iShares 官方页面 2026-07-28 可读取关键事实。
- 主题：为什么组合里有很多只 ETF，不等于风险已经分散。
- 学习目标：理解 portfolio overlap、look-through exposure、core-satellite、risk budget、rebalance band、review cadence、watchlist、replacement ETF 和 cash sleeve。
- 相关资产：State Street SPDR S&P 500 ETF Trust（SPY）、Technology Select Sector SPDR Fund（XLK）、iShares Semiconductor ETF（SOXX）、Global X Artificial Intelligence & Technology ETF（AIQ）、Global X Robotics & Artificial Intelligence ETF（BOTZ）、iShares 0-3 Month Treasury Bond ETF（SGOV）。
- 核心来源：
  - Investor.gov, Asset Allocation and Diversification: https://www.investor.gov/introduction-investing/getting-started/asset-allocation
  - Investor.gov, Updated Investor Bulletin: Exchange-Traded Funds (ETFs), 2023-02-23: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-24
  - SEC, Exchange-Traded Funds: A Small Entity Compliance Guide / Rule 6c-11: https://www.sec.gov/investment/exchange-traded-funds-small-entity-compliance-guide
  - State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
  - State Street, Technology Select Sector SPDR Fund (XLK): https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
  - iShares, iShares Semiconductor ETF (SOXX): https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
  - Global X, Artificial Intelligence & Technology ETF (AIQ): https://www.globalxetfs.com/funds/AIQ
  - Global X, Robotics & Artificial Intelligence ETF (BOTZ): https://www.globalxetfs.com/funds/BOTZ
  - iShares, iShares 0-3 Month Treasury Bond ETF (SGOV): https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课学了 ETF 流动性和关闭风险。今天的问题是：

```text
如果我同时买了宽基 ETF、科技 ETF、半导体 ETF、AI ETF 和机器人 ETF，
是不是因为数量多，就自动分散了？
```

不一定。

ETF 数量多，只说明账户里有多只基金。组合是否分散，要看底层资产是否真的不同。新手最容易犯的错，是把“基金名字不同”误认为“风险来源不同”。

### 参考的教材式概念顺序

1. Asset allocation：资产配置，把钱分到股票、债券、现金等资产类别。
2. Diversification：分散化，把风险分布到不同资产、行业、公司和地区。
3. Portfolio overlap：组合重叠，多只基金持有同一批证券或同一条产业链。
4. Look-through exposure：穿透暴露，不看基金名字，直接看底层持仓和行业权重。
5. Core-satellite：核心/卫星配置，用宽基或稳健资产做核心，用主题、行业或主动策略做卫星。
6. Risk budget：风险预算，预先规定某类风险最多占组合多少。
7. Rebalance band：再平衡带，当比例偏离目标太多时才调整。
8. Review cadence：复查频率，按季度、半年或事件触发检查。
9. Watchlist：观察清单，记录基金、数据日期、持仓、费用和复查理由。
10. Replacement ETF：替代 ETF，用来替换费用、规则、流动性或暴露不合适的产品。
11. Cash sleeve：现金仓位或短端现金工具，用来管理流动性，不等于无风险收益承诺。

### 核心概念

ETF 组合的第一步不是问“买哪只”，而是问：

```text
我已经通过这些基金重复承担了哪些风险？
```

一个最小读表顺序是：

```text
单只 ETF 名称
-> 投资目标和指数规则
-> 前十大持仓
-> 行业权重
-> 国家和货币暴露
-> AUM、成交量、买卖价差、溢价折价
-> 与账户里其他 ETF 的共同持仓
-> 放入组合后的总暴露
```

风险预算不是预测涨跌，而是给自己设一个上限。例如一个新手可以先问：

```text
宽基权益最多多少？
科技和半导体合计最多多少？
主题 ETF 最多多少？
现金或短债工具至少多少？
单一公司通过所有基金穿透后最多多少？
```

这些问题比“我看好 AI 吗”更适合零基础学习，因为它们把故事变成了可检查的表格。

### 用自己的话解释

可以把 ETF 组合想成一份外卖订单。你点了五个菜，看起来很丰富；但如果五个菜主要材料都是鸡肉，那营养并没有想象中分散。

ETF 也是这样：

```text
SPY 里有大型科技公司。
XLK 里更集中地持有科技公司。
SOXX 里集中持有半导体产业链。
AIQ 里有 AI 和技术平台公司。
BOTZ 里有机器人、自动化和 AI 相关公司。
```

如果这些基金同时出现 NVIDIA、Microsoft、Apple、Broadcom、Palantir、Cisco 或其他相关公司，你的账户可能不是“五个方向”，而是“同一条科技和 AI 链条的多层叠加”。

### 常见误区

- 误区一：ETF 只数数量，不看持仓。数量是表面，底层持仓才是风险。
- 误区二：宽基 ETF 一定没有集中度。市值加权宽基也可能因为大公司上涨而集中在少数行业。
- 误区三：主题 ETF 是卫星，所以可以随便加。卫星仓位小，也可能与核心仓位高度重叠。
- 误区四：再平衡就是预测高点低点。再平衡的目标是回到计划风险，不是抓顶逃底。
- 误区五：现金 ETF 等于银行存款。短端国债 ETF 仍是证券产品，有利率、价格、费用、税务和流动性口径。

## 第二大板块：实时背景与市场传导

### 发生了什么

Investor.gov 的资产配置和分散化页面说明，资产配置是把投资分到股票、债券和现金等类别；分散化是把资金分散到不同投资以降低风险。该页面还提醒，随着时间推移，有些投资涨得更快，会让持仓偏离投资目标，因此需要再平衡；再平衡可以按固定时间，也可以按预设偏离比例触发。

Investor.gov 的 ETF 投资者公告说明，ETF 投资者应查看 ETF 官网的 NAV、收盘市场价格、溢价折价、持仓、median bid-ask spread 和历史溢价折价。SEC Rule 6c-11 合规指南说明，许多 ETF 需要在官网披露前一营业日持仓、NAV、市场价格、溢价折价和最近 30 个日历日的 median bid-ask spread。

State Street SPY 官方页面显示，截至 2026-08-10，SPY 的 AUM 为 8138.6152 亿美元，费用率 0.0945%，基金持仓 504 只；前十大持仓包括 NVIDIA 7.90%、Apple 6.79%、Microsoft 5.64%、Amazon 4.08%、Alphabet A 3.14%、Broadcom 3.00%；行业权重中 Information Technology 为 37.49%。

State Street XLK 官方页面显示，截至 2026-08-10，XLK 费用率 0.08%；前十大持仓包括 NVIDIA 14.18%、Apple 12.19%、Microsoft 10.12%、Broadcom 5.38%、AMD 3.93%、Micron 3.60%；行业分配中 Semiconductors & Semiconductor Equipment 为 44.40%，Software 为 25.07%。

iShares SOXX 官方页面显示，截至 2026-08-10，SOXX 净资产约 437.61 亿美元，日成交量 8,763,460 股，premium/discount 为 -0.02，30-day median bid-ask spread 为 0.04%；截至 2026-08-07，持仓数量 30，P/E ratio 为 65.25，行业暴露中 Semiconductors 为 78.91%、Semiconductor Equipment 为 20.95%。

Global X AIQ 官方页面显示，截至 2026-08-10，AIQ 净资产 102.3 亿美元，费用率 0.68%，持仓数量 88，30-day median bid-ask spread 为 0.02%；截至 2026-07-31，行业暴露中 Information Technology 为 71.5%、Communication Services 为 12.4%、Consumer Discretionary 为 9.7%。

Global X BOTZ 官方页面显示，截至 2026-08-10，BOTZ 净资产 35.5 亿美元，费用率 0.68%，持仓数量 61，30-day median bid-ask spread 为 0.03%；截至 2026-07-31，行业暴露中 Industrials 为 45.2%、Information Technology 为 37.1%、Health Care 为 8.1%。

iShares SGOV 官方页面可读取数据表明，截至 2026-07-28，SGOV 追踪 ICE 0-3 Month US Treasury Securities Index，净资产约 999.70 亿美元，30-day SEC yield 为 3.57%，费用率 0.09%，premium/discount 为 0.00，30-day median bid-ask spread 为 0.01%。

### 为什么重要

这些事实放在一起，可以看到一个组合问题：

```text
SPY 是宽基，但 Information Technology 已经是最大行业权重。
XLK 是科技板块，半导体和软件占比很高。
SOXX 是半导体细分行业，暴露更窄。
AIQ 是 AI 主题，但信息技术权重超过七成。
BOTZ 是机器人与 AI 主题，同时落在工业和信息技术。
SGOV 更偏短端国债和流动性管理，但收益会随短端利率环境变化。
```

如果账户里同时放入这些 ETF，真正的问题不是“我买了几只”，而是：

```text
科技链条穿透后到底占了多少？
半导体链条是否超过我的风险预算？
主题 ETF 是否和宽基核心重复？
现金或短端工具是否只是暂时停靠，而不是长期收益保证？
```

### 本节采用的数据和来源

- 资产配置、分散化、再平衡：Investor.gov Asset Allocation and Diversification。
- ETF 交易和披露框架：Investor.gov ETF bulletin 与 SEC Rule 6c-11 guide。
- 宽基核心样本：State Street SPY 官方页面。
- 科技板块和半导体行业样本：State Street XLK、iShares SOXX 官方页面。
- AI 与机器人主题样本：Global X AIQ、Global X BOTZ 官方页面。
- 现金或短端国债样本：iShares SGOV 官方页面。

### 这些现实事件如何连接理论

组合穿透的传导链可以写成：

```text
单只基金名称
-> 指数或主动规则
-> 底层持仓
-> 行业和公司暴露
-> 多只基金之间的重叠
-> 组合层面实际风险
-> 是否触发风险预算或再平衡带
```

再平衡的传导链可以写成：

```text
某个主题或行业涨得更快
-> 组合权重上升
-> 风险水平偏离原目标
-> 复查是否超出 rebalance band
-> 决定新增资金投向、缩小仓位、替换 ETF 或暂时转入现金工具
-> 记录税务、交易成本和再投资计划
```

一个教学示例：

```text
假设账户目标是：
60% 宽基权益
20% 行业或主题卫星
10% 债券或现金工具
10% 观察仓
```

如果宽基里已经有很多科技权重，再叠加 XLK、SOXX、AIQ 和 BOTZ，科技和半导体链条可能很快超过原来以为的 20% 卫星预算。此时要做的是穿透计算，不是被基金名称安慰。

### 至少一个实时新闻、往期事件或真实市场机制案例

本课案例是“AI 主题热度穿透到宽基、行业和主题 ETF”。截至本次核验，SPY 的前十大持仓已有 NVIDIA、Apple、Microsoft、Amazon、Alphabet、Broadcom 等大型科技或技术平台公司；XLK 的前三大持仓是 NVIDIA、Apple 和 Microsoft；AIQ 的前十大持仓包括 Palantir、Microsoft、Oracle、Amazon、Alphabet、Cisco、Tencent 和 Broadcom；BOTZ 的前十大持仓包括 Keyence、ABB、NVIDIA、FANUC、Intuitive Surgical 等自动化和 AI 相关公司。

这说明同一条 AI 和数字基础设施链条，可以同时出现在：

```text
宽基指数
-> 科技板块
-> 半导体行业
-> AI 主题
-> 机器人主题
```

组合层面的风险管理，要把这些产品合成一张穿透表。

## 政治、制度和规则视角

### 涉及的政策、监管、制度或国际关系

- SEC ETF 披露制度：ETF 官网披露持仓、NAV、市场价格、溢价折价和买卖价差，是穿透分析的基础。
- 指数公司方法论：宽基、行业、细分行业和主题 ETF 的边界由指数规则或投资顾问规则决定。
- 半导体和 AI 产业政策：出口管制、供应链安全、财政补贴、数据中心投资和国际竞争都可能影响底层公司。
- 税务制度：再平衡如果涉及卖出，会连接到成本基础、资本利得、资本损失和账户类型。
- 交易制度：买卖价差、溢价折价、成交量和清算机制影响再平衡执行成本。

### 已确认事实

- Investor.gov 把资产配置定义为把投资分到股票、债券和现金等类别，并把再平衡描述为把组合拉回原资产配置。
- Investor.gov ETF bulletin 和 SEC Rule 6c-11 都强调 ETF 官网披露 NAV、市场价格、溢价折价、持仓和 median bid-ask spread。
- SPY 截至 2026-08-10 持仓 504 只，Information Technology 权重 37.49%，前十大持仓中包含多家大型科技公司。
- XLK 截至 2026-08-10 前三大持仓合计超过 36%，行业分配中半导体与半导体设备为 44.40%。
- SOXX 截至 2026-08-07 几乎全部落在半导体和半导体设备暴露，持仓数量 30。
- AIQ 与 BOTZ 的主题名称都涉及 AI，但行业暴露、前十大持仓和集中路径不同。

### 市场可能如何传导

如果 AI、半导体或大型科技公司继续上涨，宽基、科技、半导体和 AI 主题 ETF 可能同时受益，组合看起来会表现很好，但集中度也会被动上升。如果盈利兑现、估值、利率、出口规则或资本开支预期发生变化，多个看似不同的 ETF 也可能一起回撤。

### 仍需核验或观察

- ETF 持仓和行业权重是否继续向少数大公司集中。
- 主题 ETF 是否继续与宽基和行业 ETF 重叠。
- 30-day median bid-ask spread 和 premium/discount 是否在压力日扩大。
- 费用率、指数方法论、股息分配和资本利得分配是否改变。
- 现金或短端国债 ETF 的 SEC yield 是否随短端利率环境变化。
- 再平衡卖出是否产生税务后果。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Asset Allocation | 资产配置 | 把资金分到股票、债券、现金等类别 | 决定组合大方向风险 |
| Diversification | 分散化 | 不把风险压在同一资产或公司上 | 降低单一风险源冲击 |
| Portfolio Overlap | 组合重叠 | 多只基金重复持有同一证券或行业 | 防止误以为已经分散 |
| Look-Through Exposure | 穿透暴露 | 看到底层公司、行业和地区 | 识别基金名字背后的真实风险 |
| Core-Satellite | 核心/卫星 | 核心稳住大盘暴露，卫星表达小比例观点 | 防止主题仓位失控 |
| Risk Budget | 风险预算 | 给某类风险设置上限 | 让风险管理先于情绪 |
| Rebalance Band | 再平衡带 | 偏离目标超过阈值才调整 | 降低过度交易 |
| Review Cadence | 复查频率 | 定期或事件触发检查组合 | 让组合维护可持续 |
| Watchlist | 观察清单 | 记录基金字段和复查原因 | 防止碎片化学习 |
| Replacement ETF | 替代 ETF | 暴露类似但费用、规则或流动性更合适的候选 | 换基金前要先比较底层规则 |
| Cash Sleeve | 现金仓位 | 用现金或短端工具留出流动性 | 管理波动和再投资等待期 |

## 回顾提示

- 学到本课前建议回顾：可回顾第 47 课组合暴露、第 48 课 ETF 持仓穿透、第 49 课 ETF 交易机制、第 52 课核心/卫星配置、第 80 课主题 ETF 集中度、第 81 课 ETF 流动性与关闭风险。
- 本课哪些内容会在后续课程继续使用：portfolio overlap、look-through exposure、risk budget、rebalance band、review cadence、replacement ETF 和 tax-aware rebalancing。
- 如果看不懂本课，可以先回到：第 4 课基金和 ETF 入门、第 51 课基金风险指标、第 76-77 课收益型 ETF 税后总回报。

## 案例拆解

### 案例对象

SPY、XLK、SOXX、AIQ、BOTZ 和 SGOV 的示例组合。

### 已确认事实

- SPY 是 S&P 500 宽基 ETF，State Street 页面显示其截至 2026-08-10 的 AUM 为 8138.6152 亿美元，持仓 504 只，Information Technology 权重 37.49%。
- XLK 是科技板块 ETF，State Street 页面显示其截至 2026-08-10 的前十大持仓中 NVIDIA、Apple、Microsoft 合计约 36.49%，半导体与半导体设备行业权重 44.40%。
- SOXX 是半导体 ETF，iShares 页面显示其截至 2026-08-10 的净资产约 437.61 亿美元、30-day median bid-ask spread 0.04%，截至 2026-08-07 持仓数量 30。
- AIQ 是 AI 与技术主题 ETF，Global X 页面显示其截至 2026-08-10 的净资产 102.3 亿美元、费用率 0.68%、持仓数量 88。
- BOTZ 是机器人与 AI 主题 ETF，Global X 页面显示其截至 2026-08-10 的净资产 35.5 亿美元、费用率 0.68%、持仓数量 61。
- SGOV 是 0-3 个月美国国债 ETF，iShares 页面显示其追踪 ICE 0-3 Month US Treasury Securities Index，用于保存资本和管理流动性并寻求较低利率风险。

### 来源日期和链接

- State Street SPY official page, data as of 2026-08-10 and 2026-08-11: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- State Street XLK official page, data as of 2026-08-10 and 2026-08-11: https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- iShares SOXX official page, data as of 2026-08-10 and 2026-08-07: https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- Global X AIQ official page, data as of 2026-08-10 and 2026-07-31: https://www.globalxetfs.com/funds/AIQ
- Global X BOTZ official page, data as of 2026-08-10 and 2026-07-31: https://www.globalxetfs.com/funds/BOTZ
- iShares SGOV official page, data as of 2026-07-28 in accessible source snapshot: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond

### 分析推理

如果一个账户里已经有 SPY，再加入 XLK 和 SOXX，就不是简单增加两只基金，而是在 SPY 原有科技权重基础上继续叠加科技和半导体。如果再加入 AIQ 和 BOTZ，AI 叙事会继续通过软件、平台、半导体、自动化和机器人公司进入账户。

SGOV 这样的短端国债 ETF 可以在教学里作为现金仓位样本，但它不是收益承诺，也不等于银行存款。它的 30-day SEC yield、NAV、溢价折价和费用率仍要持续核验。

### 后续验证指标

- 每只 ETF 的前十大持仓合计权重。
- NVIDIA、Apple、Microsoft、Broadcom、AMD、Micron、Cisco、Palantir 等共同持仓的穿透权重。
- Information Technology、Semiconductors、Software、Industrials 等行业权重。
- AUM、日成交量、30-day median bid-ask spread 和 premium/discount。
- 基金费用率、资本利得分配和最近 shareholder report。
- 是否触发预设 rebalance band。

## 个人情境连接

- 对关注清单的启发：给每只 ETF 增加“组合内重叠”栏，记录它和核心 ETF 的共同前十大持仓。
- 对持仓或基金选择的启发：先定义核心和卫星，再选基金；不要先买多个主题，再回头找理由。
- 对工作、收入、消费或风险管理的启发：生活中的风险也会重叠，例如工作收入、奖金、公司股票和投资账户都可能暴露在同一行业周期。

## 结论边界

- 可以确定：ETF 组合是否分散，要看底层持仓、行业权重、交易质量和风险预算，不是看基金数量。
- 不能确定：AI、科技、半导体或机器人 ETF 未来是否继续跑赢，也不能确定任何风险预算适合某个具体投资者。
- 需要继续观察：持仓更新、行业权重、估值、流动性、费用、分配、税务和产品生命周期。
- 不构成投资建议的原因：本课只训练 ETF 组合穿透和风险预算方法，不提供任何买入、卖出或持有建议。

## 练习题

1. 用一句话解释 portfolio overlap 和 look-through exposure 的区别。
2. 为什么同时持有 SPY、XLK、SOXX、AIQ 和 BOTZ 不一定等于分散？
3. 选择两只 ETF，记录它们前十大持仓中是否有共同公司。
4. 给一个假设账户写出三个 risk budget，例如科技上限、主题 ETF 上限、现金下限。
5. 如果某个卫星 ETF 从组合 5% 涨到 12%，你会如何判断是否需要再平衡？

## 学习交接

- 本课已经完成：把 ETF 学习从单只基金的流动性和关闭风险推进到组合层面的持仓重叠、穿透暴露、核心/卫星、风险预算、再平衡带和复查频率。
- 本课最重要的一句话：ETF 数量多不等于分散，只有穿透到底层持仓和行业权重，才知道自己真正承担了什么风险。
- 需要复习的关键词：Portfolio Overlap、Look-Through Exposure、Core-Satellite、Risk Budget、Rebalance Band、Review Cadence、Replacement ETF、Cash Sleeve。
- 还不稳定、下次要回看的地方：再平衡卖出会带来交易成本和税务结果，不能只按目标权重机械操作。
- 适合下次打开仓库先读的文件：`lessons/2026-08-11-lesson-83-etf-tax-aware-rebalancing-replacement-review.md`

## 下节课安排

- 建议主题：第八十三课：ETF 税务敏感再平衡、替代 ETF 与复查流程入门：成本基础、资本利得、wash sale、费用、分配和账户位置。
- 学习目标：理解 tax-aware rebalancing、cost basis、realized gain/loss、short-term vs long-term、wash sale、tax-loss harvesting、capital gains distribution、account location 和 replacement ETF due diligence。
- 建议案例：继续使用 SPY、XLK、SOXX、AIQ、BOTZ 和 SGOV，演示主题仓位上涨后，如何在 taxable account 和 tax-advantaged account 中分别思考再平衡。
- 必须解释的关键词：Cost Basis、Realized Gain/Loss、Capital Gain、Short-Term、Long-Term、Wash Sale、Tax-Loss Harvesting、Capital Gains Distribution、Account Location、Replacement ETF。
- 下节课开始前需要联网核验的数据：IRS Topic 409、IRS Publication 550 wash sale、Investor.gov ETF fees bulletin、ETF 官网 after-tax return、distribution history、capital gains distribution 和 prospectus fee table。

## 来源

- Investor.gov, Asset Allocation and Diversification: https://www.investor.gov/introduction-investing/getting-started/asset-allocation
- Investor.gov, Updated Investor Bulletin: Exchange-Traded Funds (ETFs): https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins-24
- SEC, Exchange-Traded Funds: A Small Entity Compliance Guide / Rule 6c-11: https://www.sec.gov/investment/exchange-traded-funds-small-entity-compliance-guide
- State Street, SPDR S&P 500 ETF Trust (SPY): https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
- State Street, Technology Select Sector SPDR Fund (XLK): https://www.ssga.com/us/en/intermediary/etfs/state-street-technology-select-sector-spdr-etf-xlk
- iShares, iShares Semiconductor ETF (SOXX): https://www.ishares.com/us/products/239705/ishares-semiconductor-etf
- Global X, Artificial Intelligence & Technology ETF (AIQ): https://www.globalxetfs.com/funds/AIQ
- Global X, Robotics & Artificial Intelligence ETF (BOTZ): https://www.globalxetfs.com/funds/BOTZ
- iShares, iShares 0-3 Month Treasury Bond ETF (SGOV): https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond
