# 第五十四课：货币市场基金、T-Bill、短债 ETF 与现金管理入门

## 基本信息

- 日期：2026-07-17
- 数据截至：2026-07-17 21:50（Asia/Shanghai）。实时数据采用 Federal Reserve H.15 2026-07-16 发布、截至 2026-07-15 的短端利率；iShares SGOV 页面 2026-07-16 / 2026-07-15 指标；Vanguard VMFXX 页面 2026-07-14 / 2026-07-13 指标；SEC、FDIC、SIPC 和 TreasuryDirect 官方说明按页面核验日使用。
- 主题：现金管理不是“放着不动”；如何区分银行存款、货币市场基金、T-Bill 和短债 ETF。
- 学习目标：理解 Bank Deposit、Money Market Fund、Treasury Bill、Ultra-short Bond ETF、7-Day SEC Yield、30-Day SEC Yield、FDIC Insurance、SIPC Protection、Liquidity Fee、Settlement 和 Reinvestment Risk。
- 相关资产：银行存款、货币市场基金、美国国库券、短债 ETF、经纪账户现金、短端利率。
- 核心来源：
  - SEC Investor.gov, Money Market Funds: Investor Bulletin: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-12
  - SEC, Money Market Fund Reforms, press release 2023-129: https://www.sec.gov/newsroom/press-releases/2023-129
  - FDIC, Deposit Insurance FAQs: https://www.fdic.gov/resources/deposit-insurance/faq
  - SIPC, What is SIPC?: https://www.sipc.org/for-investors/introduction
  - Federal Reserve, H.15 Selected Interest Rates, release date 2026-07-16: https://www.federalreserve.gov/releases/h15/
  - TreasuryDirect, Treasury Bills: https://www.treasurydirect.gov/marketable-securities/treasury-bills/
  - iShares SGOV product page: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
  - Vanguard Federal Money Market Fund VMFXX product page: https://advisors.vanguard.com/investments/products/vmfxx/vanguard-federal-money-market-fund

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲了债券基金不是存款。今天继续问一个更贴近日常的问题：

> 手里暂时不用的钱，放银行、货币市场基金、T-Bill、短债 ETF，到底有什么区别？

初学者容易把它们都叫“现金”。但在金融里，“现金管理”至少要拆成四个问题：

```text
1. 安全性：我承担谁的信用风险？
2. 流动性：我要用钱时，多久能拿出来？
3. 收益率：收益来自哪里，会不会随利率变？
4. 规则边界：有没有 FDIC、SIPC、赎回费、结算日、价格波动？
```

现金管理的核心不是追最高收益，而是让钱的期限、用途和风险边界匹配。

### 参考的教材式概念顺序

1. Cash：现金，最强流动性，但通常收益最低。
2. Bank Deposit：银行存款，是对银行的债权，符合条件时受 FDIC 存款保险保护。
3. Money Market Deposit Account：银行货币市场存款账户，名字像基金，但本质是银行存款产品。
4. Money Market Fund：货币市场基金，是共同基金，投资短期债务、现金和现金等价物。
5. Treasury Bill：美国国库券，1 年以内到期，通常折价发行，到期按面值支付。
6. Short Treasury ETF / Ultra-short Bond ETF：短债 ETF，像基金一样持有短期债券，在交易所买卖。
7. Yield：收益率，会随着短端利率、费用、持仓再投资和基金规则变化。
8. Liquidity：流动性，不只是能不能卖，还包括到账、结算、赎回规则和极端市场限制。
9. Reinvestment Risk：再投资风险，短期工具到期后，新利率可能变低。

### 核心概念

同样是“短期放钱”，四类工具的风险来源不同：

```text
银行存款：
- 主要看银行和 FDIC 保险边界
- 适合日常支付和应急周转
- 收益率由银行定价，不一定等于市场短端利率

货币市场基金：
- 是共同基金，不是银行存款
- 主要看持仓、基金类型、7-day yield、费用和赎回规则
- 收益通常随短端利率变化

T-Bill：
- 是美国财政部发行的短期国债
- 通常折价买入，到期拿面值
- 持有到期时路径清楚，但中途卖出仍有价格和流动性问题

短债 ETF：
- 在交易所交易，有 NAV 和市场价格
- 持有一篮子短期债券或国库券
- 比中长期债券基金久期短，但不是 FDIC 存款
```

### 用自己的话解释

现金管理像给钱贴标签：

```text
明天要交房租的钱：优先流动性和确定到账
三个月后要用的钱：可以考虑短期限工具，但要看结算和价格波动
一年内可能用的钱：可以用分层方式管理，但不能只盯收益率
长期不用的钱：才进入更广的债券、股票或基金组合问题
```

现金不是一个单一资产，而是一组“期限很短、用途很明确”的资产安排。

### 常见误区

- 误区一：货币市场基金等于银行存款。SEC Investor.gov 明确说明，money market fund 是共同基金，资金不由 FDIC 像银行账户那样保证。
- 误区二：SIPC 等于投资收益保险。SIPC 保护的是经纪商失败且资产缺失时的客户财产恢复，不保护市场亏损。
- 误区三：T-Bill 没有风险。持有到期的现金流较清楚，但中途卖出、再投资利率和账户操作仍有风险。
- 误区四：短债 ETF 就是现金。短债 ETF 久期短，但仍有 NAV、市场价格、买卖价差和结算问题。
- 误区五：收益率最高就是最好。短期钱最怕的是需要用钱时取不出来或本金波动超过计划。

## 第二大板块：实时背景与市场传导

### 发生了什么

Federal Reserve H.15 2026-07-16 release 显示，2026-07-15 的 effective federal funds rate 为 3.63%。同一表中，Treasury bills secondary market 2026-07-15 数据为：

- 4-week：3.64%。
- 3-month：3.70%。
- 6-month：3.77%。
- 1-year：3.80%。

Treasury constant maturity 2026-07-15 短端数据为：

- 1-month：3.73%。
- 3-month：3.83%。
- 6-month：3.93%。
- 1-year：3.97%。

这些数字说明：现金管理工具的收益不是孤立的，短端收益率会围绕货币政策、国库券供需、基金费用和资金市场压力变化。

SEC Investor.gov 说明，money market funds 投资流动性强的短期债务证券、现金和现金等价物，收益一般反映短期利率变化。它还区分 government、tax-exempt 和 prime money market funds。SEC 2023 年 money market fund reforms 提高了流动性要求，取消了基金董事会在流动性低于阈值时临时暂停赎回的旧规则，并为部分机构 prime / tax-exempt money market funds 引入流动性费用框架。

FDIC FAQ 说明，FDIC 保险保护 FDIC-insured bank 的存款账户，标准额度是每个存款人、每家受保银行、每个所有权类别至少 250,000 美元。SIPC 页面说明，若 SIPC member brokerage firm 失败，SIPC 对证券和现金的保护最高 500,000 美元，其中现金限额 250,000 美元；但 SIPC 不保护市场亏损或投资表现承诺。

iShares SGOV 页面显示，SGOV 跟踪 ICE 0-3 Month US Treasury Securities Index。页面指标包括：

- NAV：100.54 美元，as of 2026-07-16。
- Closing price：100.55 美元，as of 2026-07-16。
- 30 Day SEC Yield：3.57%，as of 2026-07-15。
- Expense ratio：0.09%。
- Effective duration：0.10 years，as of 2026-07-16。
- Average yield to maturity：3.69%，as of 2026-07-16。
- Weighted average maturity：0.10 years，as of 2026-07-16。

Vanguard VMFXX 页面显示，Vanguard Federal Money Market Fund 的 NAV 为 1.0000 美元，as of 2026-07-14；7-day SEC yield 为 3.55%，as of 2026-07-13；expense ratio 为 0.11%，as of 2025-12-19。

### 为什么重要

同一个利率环境下，不同现金工具的“收益率数字”不能直接机械比较：

```text
银行存款 APY：
- 银行给存款人的报价
- 要看 FDIC 保险、银行、账户限制和提款规则

货币市场基金 7-day yield：
- 过去 7 天收入年化后的基金口径
- 会受短端利率和基金费用影响

T-Bill auction / secondary yield：
- 来自财政部拍卖或二级市场
- 折价买入、到期按面值支付

短债 ETF 30 Day SEC Yield：
- 标准化基金收入口径
- 仍要看 NAV、市场价、久期、买卖价差和费用
```

所以现金管理的最小检查顺序是：

```text
1. 这笔钱什么时候要用？
2. 工具是不是 FDIC 存款、共同基金、国债，还是 ETF？
3. 收益率口径是什么？
4. 到账和结算规则是什么？
5. 价格会不会波动？
6. 极端情况下有哪些限制、费用或保护边界？
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| Effective federal funds rate | 3.63% | Federal Reserve H.15, 2026-07-15 数据 / 2026-07-16 发布 | 短端利率锚 |
| 4-week T-Bill secondary rate | 3.64% | Federal Reserve H.15, 2026-07-15 | 现金工具收益背景 |
| 3-month T-Bill secondary rate | 3.70% | Federal Reserve H.15, 2026-07-15 | 短端市场背景 |
| 6-month T-Bill secondary rate | 3.77% | Federal Reserve H.15, 2026-07-15 | 期限比较 |
| 1-year T-Bill secondary rate | 3.80% | Federal Reserve H.15, 2026-07-15 | 再投资风险背景 |
| FDIC coverage | 每存款人、每受保银行、每所有权类别至少 250,000 美元 | FDIC FAQ | 存款保险边界 |
| SIPC coverage | 最高 500,000 美元，含现金 250,000 美元限额 | SIPC | 经纪账户保护边界 |
| SGOV NAV | 100.54 美元 | iShares, 2026-07-16 | ETF 净值 |
| SGOV closing price | 100.55 美元 | iShares, 2026-07-16 | ETF 市场价格 |
| SGOV 30 Day SEC Yield | 3.57% | iShares, 2026-07-15 | 短债 ETF 收入口径 |
| SGOV effective duration | 0.10 年 | iShares, 2026-07-16 | 利率敏感度 |
| VMFXX NAV | 1.0000 美元 | Vanguard, 2026-07-14 | 货币市场基金稳定 NAV 案例 |
| VMFXX 7-day SEC yield | 3.55% | Vanguard, 2026-07-13 | 货币市场基金收益口径 |

### 这些现实事件如何连接理论

把四类工具放在一页：

```text
银行存款：
- 目标：支付、应急、确定性
- 核心问题：是否在 FDIC 保险范围内
- 收益率：银行报价，不一定随市场完全同步

货币市场基金：
- 目标：现金替代、经纪账户闲置资金管理
- 核心问题：基金类型、7-day yield、费用、赎回规则
- 收益率：通常跟短端利率变化

T-Bill：
- 目标：明确到期日的短期国债现金流
- 核心问题：拍卖价、到期日、税务、再投资
- 收益率：折价与面值差形成利息

短债 ETF：
- 目标：交易便利的一篮子短期国债/短债暴露
- 核心问题：NAV、市场价、久期、价差、费用
- 收益率：30 Day SEC Yield 是标准化口径，不是保证收益
```

SGOV 案例说明：短债 ETF 的 duration 只有 0.10 年，利率敏感度很短，但它仍然有 NAV、closing price、bid/ask spread 和 expense ratio。它不是银行存款，也不是 FDIC 保险账户。

VMFXX 案例说明：货币市场基金可以努力维持 1 美元稳定 NAV，并用 7-day SEC yield 表示近期收入能力，但它仍然是基金，不是银行存款。Investor.gov 明确提醒 money market fund 不由 FDIC 保证，并存在亏损可能。

### 至少一个真实市场机制案例

2023 年 SEC money market fund reforms 是现金管理的重要制度案例。改革的教学意义是：

```text
货币市场基金看起来很稳定
但监管仍然要处理压力市场下的赎回、流动性和成本分配问题

稳定 NAV 不等于没有风险
高流动性要求不等于永远没有挤兑压力
规则改变会影响投资者在压力时的实际体验
```

这提醒我们：现金管理不只看收益率，还要读规则。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：FDIC 存款保险、SIPC 经纪账户保护、SEC money market fund rules、TreasuryDirect 国库券发行制度、Federal Reserve 利率政策。
- 已确认事实：FDIC 保险适用于符合条件的受保存款账户；SIPC 不保护市场亏损；money market fund 是共同基金；T-Bill 由 Treasury 发行，通常折价或按面值出售，到期按面值支付。
- 市场可能如何传导：FOMC 和短端利率影响 T-Bill、货币市场基金和短债 ETF 的收益；基金费用会降低投资者到手收益；压力市场下赎回规则和流动性费用会影响现金工具体验。
- 仍需核验或观察：最新 FOMC 目标利率、H.15 短端利率、具体基金 7-day yield、30-day SEC yield、费用率、持仓、交易价差和赎回规则。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Cash Management | 现金管理 | 按用途和期限安排短期资金 | 决定钱能不能按时安全使用 |
| Bank Deposit | 银行存款 | 存款人对银行的债权 | 可能受 FDIC 保险保护 |
| Money Market Deposit Account | 货币市场存款账户 | 银行提供的存款账户 | 名字像基金但本质是存款 |
| Money Market Fund | 货币市场基金 | 投资短期债务和现金等价物的共同基金 | 不是 FDIC 存款 |
| Government Money Market Fund | 政府货币市场基金 | 主要投政府证券、现金和相关回购 | 风险结构不同于 prime fund |
| Prime Money Market Fund | 优质货币市场基金 | 投资短期公司和银行债务 | 信用和流动性风险更复杂 |
| Stable NAV | 稳定净值 | 力求维持每份 1 美元 | 不等于绝对无风险 |
| Floating NAV | 浮动净值 | 净值随资产市场价值变化 | 机构 prime 等基金常见 |
| Treasury Bill | 美国国库券 | 1 年以内短期国债 | 短期无风险利率观察入口 |
| 7-Day SEC Yield | 7 日 SEC 收益率 | 货币市场基金近期收入年化口径 | 比较货币基金时常用 |
| 30-Day SEC Yield | 30 日 SEC 收益率 | 债券基金/ETF 标准化收入口径 | 不是未来保证收益 |
| FDIC Insurance | FDIC 存款保险 | 银行倒闭时保护合格存款 | 有额度和账户类别边界 |
| SIPC Protection | SIPC 保护 | 经纪商失败时恢复客户资产 | 不保护市场亏损 |
| Settlement | 结算 | 交易后资金和证券正式交割 | 决定现金何时真正可用 |
| Liquidity Fee | 流动性费用 | 压力赎回时可能收取的费用 | 影响赎回成本 |
| Reinvestment Risk | 再投资风险 | 到期后新利率可能下降 | 短期工具最常见风险之一 |

## 回顾提示

- 学到本课前建议回顾：第 4 课基金和 ETF、第 5 课债券和利率、第 49 课 ETF 交易机制、第 53 课债券基金。
- 本课哪些内容会在后续课程继续使用：T-Bill 阶梯、收益率曲线、货币政策传导、应急资金分层。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图，重新分清“存款、债券、基金、ETF”的法律关系。

## 案例拆解

- 案例对象：VMFXX 与 SGOV 的现金管理工具对照。
- 已确认事实：
  - VMFXX 页面显示 NAV 为 1.0000 美元，7-day SEC yield 为 3.55%。
  - SGOV 页面显示 NAV 为 100.54 美元、closing price 为 100.55 美元、30 Day SEC Yield 为 3.57%、effective duration 为 0.10 年。
  - H.15 显示 2026-07-15 effective federal funds rate 为 3.63%，4-week T-Bill secondary rate 为 3.64%。
  - FDIC 和 SIPC 的保护对象不同，且 SIPC 不保护市场亏损。
- 来源日期和链接：见本课“来源”。
- 分析推理：VMFXX 更像经纪账户或基金账户里的现金替代工具；SGOV 更像可交易的短期国债 ETF。二者都可能服务现金管理，但规则、收益率口径和保护边界不同。
- 后续验证指标：基金最新 7-day yield、30 Day SEC Yield、expense ratio、duration、holdings、NAV、market price、bid/ask spread、SEC 规则变化、FDIC/SIPC 规则变化。

## 一页现金工具检查表

```text
这笔钱的用途：
最晚需要用钱日期：
可以接受的价格波动：
是否需要当日到账：

工具类型：
- 银行存款 / 货币市场基金 / T-Bill / 短债 ETF / 其他

保护边界：
- FDIC 是否适用：
- SIPC 是否适用：
- 是否有市场价格波动：

收益率口径：
- APY：
- 7-day SEC yield：
- 30-day SEC yield：
- T-Bill auction / secondary yield：
- 费用率：

流动性：
- 赎回或卖出时间：
- 结算日：
- 买卖价差：
- 极端情况下是否可能有费用或限制：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：现金类工具也要记录来源、日期、收益率口径、费用、结算和保护边界。
- 对持仓或基金选择的启发：短债 ETF、货币市场基金和银行存款不能只按收益率排序，要按用钱日期和规则边界排序。
- 对工作、收入、消费或风险管理的启发：应急资金优先解决“什么时候必须能用”，再考虑收益；短期收益不能牺牲确定性。

## 结论边界

- 可以确定：货币市场基金不是 FDIC 银行存款；SIPC 不保护市场亏损；T-Bill 通常折价或面值发行，到期按面值支付；短债 ETF 仍有 NAV 和交易价格。
- 不能确定：本课不能预测未来短端利率、具体基金未来收益或任何现金工具的最优比例。
- 需要继续观察：FOMC 决策、H.15 短端利率、基金 7-day yield、SGOV duration 和 yield、基金规则和账户结算规则。
- 不构成投资建议的原因：本课只解释现金管理工具的基础差异，不建议买入、卖出或持有任何具体产品。

## 练习题

1. 为什么 money market fund 和 money market deposit account 不能混为一谈？请从产品法律关系和 FDIC 保护角度解释。
2. SIPC 保护和 FDIC 保险的核心区别是什么？为什么 SIPC 不等于“投资不亏保险”？
3. 如果一笔钱 20 天后必须使用，你会重点检查哪些现金工具指标？至少写出 5 个。
4. SGOV 的 effective duration 很短，为什么仍然不能把它当成银行存款？
5. 任选一个现金工具，按本课检查表记录收益率口径、费用率、保护边界和结算规则。

## 学习交接

- 本课已经完成：把现金管理拆成银行存款、货币市场基金、T-Bill 和短债 ETF 四类工具，并建立收益率、流动性、保护边界和规则检查框架。
- 本课最重要的一句话：现金管理不是追最高收益，而是让钱的用途、期限和风险边界匹配。
- 需要复习的关键词：Bank Deposit、Money Market Fund、Treasury Bill、7-Day SEC Yield、30-Day SEC Yield、FDIC Insurance、SIPC Protection、Settlement、Liquidity Fee、Reinvestment Risk。
- 还不稳定、下次要回看的地方：T-Bill 拍卖中的 discount rate、investment rate、price per 100、bid-to-cover，以及如何做 T-Bill ladder。
- 适合下次打开仓库先读的文件：`lessons/2026-07-17-lesson-54-money-market-tbill-short-etf-cash-management.md`

## 下节课安排

- 建议主题：第五十五课：T-Bill 阶梯、拍卖口径与再投资风险入门。
- 学习目标：理解 T-Bill 为什么折价发行，学会区分 discount rate、investment rate、price per 100、maturity date、rollover、ladder 和 reinvestment risk。
- 建议案例：使用 TreasuryDirect 的 T-Bill 说明和 FiscalData 最新已完成 T-Bill 拍卖结果，手算 4-week T-Bill 的折价价格。
- 必须解释的关键词：Discount Rate、Investment Rate、Price per 100、Face Value、Maturity Date、Auction Date、Issue Date、Bid-to-Cover、T-Bill Ladder、Rollover、Reinvestment Risk。
- 下节课开始前需要联网核验的数据：Treasury FiscalData 已完成 T-Bill 拍卖结果；Federal Reserve H.15 短端利率；TreasuryDirect 对 T-Bill 定价和拍卖机制的说明。

## 来源

- SEC Investor.gov, Money Market Funds: Investor Bulletin: https://www.investor.gov/introduction-investing/general-resources/news-alerts/alerts-bulletins/investor-bulletins/updated-12
- SEC, Money Market Fund Reforms, press release 2023-129: https://www.sec.gov/newsroom/press-releases/2023-129
- FDIC, Deposit Insurance FAQs: https://www.fdic.gov/resources/deposit-insurance/faq
- SIPC, What is SIPC?: https://www.sipc.org/for-investors/introduction
- Federal Reserve, H.15 Selected Interest Rates: https://www.federalreserve.gov/releases/h15/
- TreasuryDirect, Treasury Bills: https://www.treasurydirect.gov/marketable-securities/treasury-bills/
- iShares SGOV product page: https://www.ishares.com/us/products/314116/ishares-0-3-month-treasury-bond-etf
- Vanguard Federal Money Market Fund VMFXX product page: https://advisors.vanguard.com/investments/products/vmfxx/vanguard-federal-money-market-fund
