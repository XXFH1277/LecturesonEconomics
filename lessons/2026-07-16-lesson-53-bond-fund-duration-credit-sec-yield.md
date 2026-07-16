# 第五十三课：债券基金、久期、信用质量与 SEC Yield 入门

## 基本信息

- 日期：2026-07-16
- 数据截至：2026-07-16 21:35（Asia/Shanghai）。债券基金风险采用 SEC《Mutual Funds and ETFs: A Guide for Investors》；债券基金案例采用 iShares AGG 页面显示的 2026-07-15 组合指标、2026-07-14 30 Day SEC Yield 和 2026-06-30 业绩；利率背景采用 U.S. Treasury Daily Treasury Par Yield Curve Rates 2026-07-15；30 Day SEC Yield 的标准化收益率口径参考基金发行人披露中的定义。
- 主题：债券基金为什么不是存款；如何用久期、到期收益率、SEC Yield、信用质量、OAS 和提前偿还风险读债券基金。
- 学习目标：理解 Bond Fund、Fixed Income、Coupon、Yield、Yield to Maturity、30 Day SEC Yield、Duration、Effective Duration、Maturity、Credit Quality、OAS、Prepayment Risk 和 Interest Rate Risk；学会做一页债券基金检查表。
- 相关资产：债券基金、ETF、AGG、美国国债、MBS、投资级信用债、利率曲线。
- 核心来源：
  - SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
  - iShares AGG product page: https://www.ishares.com/us/products/239458/ishares-core-total-us-bond-market-etf
  - U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
  - State Street SPY product page, 30 Day SEC Yield definition section: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课把 AGG 放进组合里当作债券基金案例。今天的问题是：

> 债券基金是不是就等于“稳稳收利息”？

不是。债券基金可能提供收入，也可能降低某些股票波动，但它仍然会随着利率、信用利差、提前偿还和市场流动性变化而涨跌。债券基金不是银行存款，也不是到期一定拿回本金的单只债券。

### 参考的教材式概念顺序

1. Bond：债券，发行人借钱并承诺按规则付息还本。
2. Coupon：票息，债券约定的利息支付。
3. Price：债券价格，市场愿意为这张债券支付多少。
4. Yield：收益率，用价格和现金流折算出来的回报口径。
5. Yield to Maturity：到期收益率，假设持有到期并按约定收到现金流的收益口径。
6. Bond Fund：债券基金，持有一篮子债券并不断买卖、再投资和处理申赎。
7. Duration：久期，衡量债券价格对利率变化的敏感度。
8. Effective Duration：有效久期，考虑期权、提前偿还等因素后的利率敏感度。
9. Credit Quality：信用质量，看发行人违约风险和评级结构。
10. OAS：Option Adjusted Spread，期权调整利差，用于观察信用和嵌入期权后的额外收益补偿。
11. Prepayment Risk：提前偿还风险，尤其常见于住房抵押贷款支持证券。
12. SEC Yield：标准化收益率，常用于比较基金近期收入能力，但不是保证收益。

### 核心概念

债券价格和利率通常反向变化：

```text
市场利率上升
-> 旧债券票息相对不吸引人
-> 旧债券价格下跌

市场利率下降
-> 旧债券票息相对更吸引人
-> 旧债券价格上涨
```

久期给初学者一个粗略估算：

```text
价格变化约等于 -久期 x 利率变化

如果某债券基金 effective duration 约 5.74 年：
利率上升 1 个百分点
粗略价格压力约 -5.74%

这只是教学近似：
- 实际结果还受收益收入、曲线形状、信用利差、凸性和持仓变化影响
- 不构成预测
```

债券基金和单只债券不同。单只债券有具体到期日；债券基金通常没有一个你个人可以等到的“组合到期日”。基金会持续买入新债、卖出旧债、处理申购赎回、再投资利息和管理指数跟踪。

### 用自己的话解释

债券基金像一辆装满很多债券的公交车。车上不断有人上车下车，司机也会调整路线。你不能只看车里某一张票的到期日，就以为整辆车会在那一天把所有本金还给你。你要看整辆车对利率有多敏感、车上乘客信用质量如何、收入从哪里来、价格会不会波动。

### 常见误区

- 误区一：债券基金等于存款。债券基金可亏钱，价格会波动。
- 误区二：收益率越高越好。高收益可能来自更高信用风险、久期风险或流动性风险。
- 误区三：只要持有债券就没有股票风险。债券基金仍可能和股票一起受利率、信用和流动性冲击。
- 误区四：SEC Yield 就是未来一年实际收益。它是标准化收入口径，不保证未来。
- 误区五：债券数量多就没有风险。广泛持有可以降低单一发行人风险，但不能消除利率和系统性信用风险。

## 第二大板块：实时背景与市场传导

### 发生了什么

SEC《Mutual Funds and ETFs: A Guide for Investors》说明，bond funds 主要投资债券或其他债务证券；它们通常比 money market funds 风险更高，因为债券基金可能追求更高收益。SEC 列出的债券基金风险包括 credit risk、interest rate risk 和 prepayment risk。SEC 还说明，当利率上升时，债券的市场价值会下降；投资者可以在任何债券基金中亏钱，包括只投资 insured bonds 或 U.S. Treasury bonds 的基金。

iShares AGG 页面显示，AGG 目标是跟踪 Bloomberg US Aggregate Bond Index，提供美国投资级债券市场的广泛暴露。页面显示：

- NAV：98.17 美元，as of 2026-07-15。
- 30 Day SEC Yield：4.58%，as of 2026-07-14。
- Expense ratio：0.03%。
- Number of holdings：13,265，as of 2026-07-15。
- Effective duration：5.74 年，as of 2026-07-15。
- Average yield to maturity：4.81%，as of 2026-07-15。
- Weighted average maturity：8.06 年，as of 2026-07-15。
- Option adjusted spread：25.81 bps，as of 2026-07-15。
- Sector exposure：Treasury 46.44%、MBS Pass-Through 23.10%、Industrial 14.31%、Financial Institutions 7.99%。
- Credit quality：AA rated 73.49%、A rated 11.96%、BBB rated 11.59%、cash/derivatives 0.74%。

同一页面的 calendar year performance 显示，AGG 2022 年 total return 为 -13.06%，2025 年 total return 为 7.19%。这可以作为真实市场机制案例：债券基金不是每天稳定向上，利率和债券市场环境会让总回报出现明显波动。

U.S. Treasury 2026-07-15 收益率曲线显示，3-month rate 为 3.83%，2-year rate 为 4.13%，10-year rate 为 4.55%，30-year rate 为 5.08%。这些利率提供债券基金的背景：短端、长端利率不同，债券基金持有的期限结构也会影响收益和价格波动。

### 为什么重要

同样叫“债券基金”，风险可能完全不同：

```text
短期国债基金：
- 久期短
- 利率敏感度较低
- 收入更贴近短端利率

综合债券基金：
- 久期中等
- 同时有国债、MBS、公司债等
- 利率、信用和提前偿还风险一起存在

长期债券基金：
- 久期长
- 对利率变化更敏感
- 利率上升时价格压力更大

高收益债基金：
- 信用风险更高
- 可能更像信用资产而不是纯利率资产
```

所以债券基金不能只看“收益率”。最小阅读顺序应该是：

```text
1. 它买什么债？
2. 久期是多少？
3. 信用质量如何？
4. SEC yield 和 yield to maturity 分别是多少？
5. 费用率多少？
6. 历史最差阶段怎么跌？
7. 和我的股票基金、现金需求有什么关系？
```

### 本节采用的数据和来源

| 项目 | 已核验事实 | 来源与日期 | 教学用途 |
| --- | ---: | --- | --- |
| 债券基金风险 | credit risk、interest rate risk、prepayment risk | SEC guide | 风险框架 |
| AGG benchmark | Bloomberg US Aggregate Bond Index | iShares, 2026-07-15 | 基准识别 |
| AGG NAV | 98.17 美元 | iShares, 2026-07-15 | 净值口径 |
| AGG expense ratio | 0.03% | iShares prospectus fee table | 成本 |
| AGG 30 Day SEC Yield | 4.58% | iShares, 2026-07-14 | 标准化收入口径 |
| AGG effective duration | 5.74 年 | iShares, 2026-07-15 | 利率敏感度 |
| AGG average YTM | 4.81% | iShares, 2026-07-15 | 到期收益背景 |
| AGG OAS | 25.81 bps | iShares, 2026-07-15 | 利差观察 |
| AGG Treasury weight | 46.44% | iShares, 2026-07-15 | 资产结构 |
| AGG MBS Pass-Through weight | 23.10% | iShares, 2026-07-15 | 提前偿还风险入口 |
| AGG 2022 total return | -13.06% | iShares, calendar year performance | 历史压力案例 |
| U.S. 10-year Treasury rate | 4.55% | U.S. Treasury, 2026-07-15 | 利率背景 |
| U.S. 30-year Treasury rate | 5.08% | U.S. Treasury, 2026-07-15 | 长端利率背景 |

### 这些现实事件如何连接理论

用 AGG 做一页入门读表：

```text
基金：AGG
数据截至：2026-07-15 / 2026-07-14

收入口径：
- 30 Day SEC Yield：4.58%
- Average Yield to Maturity：4.81%

价格敏感度：
- Effective Duration：5.74 年
- Weighted Avg Maturity：8.06 年

信用与结构：
- Treasury：46.44%
- MBS Pass-Through：23.10%
- AA rated：73.49%
- BBB rated：11.59%

交易和成本：
- Expense Ratio：0.03%
- Premium/Discount：-0.03
- 30 Day Median Bid/Ask Spread：0.01%
```

这张表的教学结论不是“买或不买 AGG”，而是：

```text
债券基金 = 收入 + 久期 + 信用 + 结构 + 流动性 + 费用
```

再把 Treasury 曲线放进来：

```text
2026-07-15：
3-month Treasury：3.83%
10-year Treasury：4.55%
30-year Treasury：5.08%

如果一个综合债券基金的 duration 在 5-6 年附近，
它受中长端利率变化影响明显；
如果短端利率和长端利率变化方向不同，
基金价格也不能只用一个利率解释。
```

### 至少一个真实市场机制案例

AGG 官方页面显示，2022 年 total return 为 -13.06%。这提醒初学者：

```text
债券基金有利息收入
但总回报 = 利息收入 + 价格变化

当利率上升或债券价格承压时：
利息收入可能不足以抵消价格下跌
基金总回报可以为负
```

这不是说债券基金“没用”，而是说它不是现金，也不是本金保证工具。它在组合中承担的角色应当被写清楚：收入、波动缓冲、利率暴露、信用暴露，还是短期流动性。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 基金披露、债券基金招募说明书、信用评级、美国国债收益率曲线、MBS 提前偿还机制、ETF 二级市场交易。
- 已确认事实：SEC 明确列出债券基金的 credit risk、interest rate risk 和 prepayment risk；AGG 数据来自 iShares；利率来自 U.S. Treasury。
- 市场可能如何传导：利率上升会压低久期资产价格；信用利差扩大可能压低公司债和信用基金价格；房贷提前偿还变化会影响 MBS 现金流；流动性压力会影响 ETF 折溢价和买卖价差。
- 仍需核验或观察：基金最新 duration、SEC yield、YTM、OAS、信用质量、MBS 权重、Treasury 曲线形状、信用利差和月度分红。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Bond Fund | 债券基金 | 持有一篮子债券的基金 | 不是单只到期债券 |
| Fixed Income | 固定收益 | 以债务现金流为核心的资产类别 | 理解收入来源 |
| Coupon | 票息 | 债券约定付的利息 | 决定现金流 |
| Yield | 收益率 | 用价格和现金流算出的回报口径 | 不能只看票息 |
| Yield to Maturity | 到期收益率 | 假设持有到期的收益口径 | 观察债券组合收入背景 |
| 30 Day SEC Yield | 30 日 SEC 收益率 | 标准化近期收入口径 | 便于比较基金 |
| Duration | 久期 | 利率敏感度的核心指标 | 利率变动会影响价格 |
| Effective Duration | 有效久期 | 考虑嵌入期权后的久期 | MBS 等资产更需要看 |
| Maturity | 到期年限 | 债券本金预计收回时间 | 和久期不同 |
| Credit Quality | 信用质量 | 发行人偿债能力和评级结构 | 衡量违约风险 |
| OAS | 期权调整利差 | 调整嵌入期权后的额外利差 | 看信用/结构补偿 |
| Prepayment Risk | 提前偿还风险 | 债务人提前还款改变现金流 | MBS 重要风险 |
| Interest Rate Risk | 利率风险 | 利率变化导致价格变化 | 债券基金核心风险 |
| Distribution Yield | 分配收益率 | 用实际分红计算的收益口径 | 和 SEC yield 可能不同 |

## 回顾提示

- 学到本课前建议回顾：第 5 课债券和利率、第 33 课信用利差、第 51 课基金风险指标、第 52 课基金组合构建。
- 本课哪些内容会在后续课程继续使用：现金管理、货币市场基金、短债 ETF、利率曲线、组合风险预算。
- 如果看不懂本课，可以先回到：第 3 课金融产品地图、第 4 课基金和 ETF、第 47 课组合暴露。

## 案例拆解

- 案例对象：iShares Core U.S. Aggregate Bond ETF（AGG）。
- 已确认事实：
  - AGG 2026-07-15 NAV 为 98.17 美元，benchmark 为 Bloomberg US Aggregate Bond Index。
  - AGG 2026-07-14 30 Day SEC Yield 为 4.58%。
  - AGG 2026-07-15 effective duration 为 5.74 年，average yield to maturity 为 4.81%。
  - AGG 2026-07-15 Treasury 权重为 46.44%，MBS Pass-Through 权重为 23.10%。
  - AGG 2022 年 total return 为 -13.06%。
  - U.S. Treasury 2026-07-15 10-year rate 为 4.55%，30-year rate 为 5.08%。
- 来源日期和链接：见本课“来源”。
- 分析推理：AGG 是广泛投资级债券 ETF，但广泛不等于无风险；duration 说明它会受利率变化影响，MBS 权重说明提前偿还风险不可忽略，信用质量结构说明主要是投资级但仍需观察 BBB 和利差变化。
- 后续验证指标：SEC yield、YTM、duration、maturity breakdown、credit quality、OAS、Treasury curve、monthly distribution、premium/discount、bid/ask spread。

## 一个可复制的债券基金检查页

```text
基金名称：
数据截至：
基金目标：
基准：

收入：
- 30 Day SEC Yield：
- Distribution Yield：
- Average Yield to Maturity：
- Expense Ratio：

利率风险：
- Effective Duration：
- Weighted Avg Maturity：
- Treasury curve 背景：
- 如果利率 +1%，教学近似价格压力：

信用风险：
- AAA/AA/A/BBB/High Yield 权重：
- OAS：
- 主要发行人或行业：

结构风险：
- Treasury：
- Agency：
- MBS：
- Corporate：
- Cash/Derivatives：
- Prepayment Risk：

交易和流动性：
- NAV：
- Closing Price：
- Premium/Discount：
- Bid/Ask Spread：
- Daily Volume：

历史压力：
- 最差年份：
- 最大回撤：
- 恢复时间：

结论边界：
- 已确认事实：
- 我的推理：
- 仍需观察：
- 不构成投资建议：
```

## 个人情境连接

- 对关注清单的启发：债券基金记录页必须增加 duration、credit quality、SEC yield 和 maturity breakdown。
- 对持仓或基金选择的启发：如果短期要用钱，不能把中久期债券基金当现金；如果为了组合缓冲，要确认它在压力市场里是否真的能缓冲。
- 对工作、收入、消费或风险管理的启发：债券基金的角色要和现金流期限匹配。短期支出需要流动性，长期目标才更能承受久期波动。

## 结论边界

- 可以确定：债券基金可亏钱；利率上升通常会压低债券价格；duration 是理解利率风险的核心入口；SEC yield 不是保证收益。
- 不能确定：本课不能预测未来利率方向、AGG 未来回报或任何债券基金的最佳配置比例。
- 需要继续观察：Treasury 曲线、信用利差、基金 duration、SEC yield、信用质量、MBS 提前偿还和 ETF 折溢价。
- 不构成投资建议的原因：本课只解释债券基金阅读框架，不建议买入、卖出、持有或配置任何债券基金。

## 练习题

1. 为什么债券基金不是银行存款？请从价格波动、到期日和基金申赎三个角度解释。
2. 如果某债券基金 effective duration 为 6 年，利率上升 0.5 个百分点，粗略价格压力约是多少？这个计算有什么局限？
3. AGG 的 Treasury 权重 46.44%、MBS Pass-Through 权重 23.10%。这两个部分分别带来什么主要风险？
4. 为什么 30 Day SEC Yield 为 4.58% 不等于未来一年一定赚 4.58%？
5. 选一个债券基金，按本课检查页写出 duration、SEC yield、YTM、credit quality、maturity breakdown 和费用率。

## 学习交接

- 本课已经完成：把第 52 课中的债券基金角色拆解为收入、久期、信用质量、OAS、提前偿还和交易流动性。
- 本课最重要的一句话：债券基金不是现金，它的总回报来自收入和价格变化，久期决定它对利率变化有多敏感。
- 需要复习的关键词：Bond Fund、Fixed Income、Coupon、Yield、Yield to Maturity、30 Day SEC Yield、Duration、Effective Duration、Credit Quality、OAS、Prepayment Risk、Interest Rate Risk。
- 还不稳定、下次要回看的地方：货币市场基金、T-Bill、短债 ETF 和现金储备的区别；为什么现金管理也有收益、流动性、信用和监管边界。
- 适合下次打开仓库先读的文件：`lessons/2026-07-16-lesson-53-bond-fund-duration-credit-sec-yield.md`

## 下节课安排

- 建议主题：第五十四课：货币市场基金、T-Bill、短债 ETF 与现金管理入门。
- 学习目标：理解现金不只是“放着不动”，学会区分 bank deposit、money market fund、Treasury bill、ultra-short bond ETF、7-day SEC yield、FDIC insurance、SIPC protection 和 liquidity gate/fees 的边界。
- 建议案例：使用 SEC/Investor.gov 对货币市场基金和现金等价物的说明，结合 U.S. Treasury 最新短端利率、一个官方/发行人短债或国债 ETF 页面作教学对照。
- 必须解释的关键词：Money Market Fund、Treasury Bill、Bank Deposit、FDIC Insurance、SIPC、7-Day SEC Yield、Liquidity、Settlement、Ultra-short Bond ETF、Reinvestment Risk。
- 下节课开始前需要联网核验的数据：Treasury 最新 1-month、3-month、6-month 和 1-year 利率；SEC/Investor.gov 对 money market funds 的最新说明；发行人页面的 7-day yield、duration、holdings、fees、liquidity 和风险披露。

## 来源

- SEC, Mutual Funds and ETFs: A Guide for Investors: https://www.sec.gov/investor/pubs/sec-guide-to-mutual-funds.pdf
- iShares AGG product page: https://www.ishares.com/us/products/239458/ishares-core-total-us-bond-market-etf
- U.S. Department of the Treasury, Daily Treasury Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?field_tdr_date_value=2026&type=daily_treasury_yield_curve
- State Street SPY product page, 30 Day SEC Yield definition section: https://www.ssga.com/us/en/intermediary/etfs/state-street-spdr-sp-500-etf-trust-spy
