# 第三十七课：客户留存、流失率、NRR 与订阅收入质量入门

## 基本信息

- 日期：2026-06-29
- 数据截至：2026-06-29 20:40（Asia/Shanghai）；公司财务采用 Microsoft 2026-04-29 Form 8-K exhibit 99.1、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 Adobe 2026-06-15 Form 10-Q；美国国债收益率采用 U.S. Treasury 2026-06-26 最新可得数据；信用利差采用 FRED / ICE BofA 2026-06-25 最新可得数据；Fed 政策采用 2026-06-17 FOMC statement。
- 主题：订阅收入为什么看起来稳定，但仍然要看续费、扩容、降级和流失。
- 学习目标：理解 Retention、Churn、Gross Revenue Retention、Net Revenue Retention、Expansion Revenue、Cohort、ARR、RPO、Deferred Revenue 和 cRPO，把“订阅收入”拆成客户行为和收入确认。
- 相关资产：股票、软件公司、云服务、SaaS、企业订阅、DCF、收入确认、经营现金流。
- 已核验来源（核心来源）：
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - U.S. Treasury Daily Treasury Par Yield Curve Rates, 2026-06-26: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?type=daily_treasury_yield_curve&field_tdr_date_value=2026
  - FRED / ICE BofA US Corporate Index Effective Yield, 2026-06-25: https://fred.stlouisfed.org/series/BAMLC0A0CMEY

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课讲护城河时，我们看到 ARR、RPO 和订阅收入都能作为证据入口。今天继续问：

> 订阅收入是不是一定比一次性销售更稳？

不一定。订阅收入通常更可见，但客户仍然可以不续费、减少席位、降级套餐、推迟采购、要求折扣，或者被新产品替代。真正要看的不是“是不是订阅”，而是订阅客户是否留下来、是否多买、是否愿意接受价格，以及收入确认是否和现金流匹配。

### 参考的教材式概念顺序

1. Subscription Revenue：先理解订阅收入按服务期确认。
2. ARR：再理解年化经常性收入的规模信号。
3. Retention：看客户是否继续留下。
4. Churn：看客户或收入是否离开。
5. Expansion Revenue：看老客户是否加购、扩容或升级。
6. NRR：把流失和扩容放在一起看。
7. RPO / cRPO：看已签合同中尚未确认收入的部分。
8. Deferred Revenue：看已经收钱但尚未履约确认收入的负债。
9. Cohort：按同一批客户观察留存和扩容轨迹。

### 核心概念

最小直觉：

```text
期末订阅收入质量 = 新客户 + 老客户续费 + 老客户扩容 - 降级 - 流失 - 折扣压力

Gross Revenue Retention = 不考虑扩容时，老客户保留下来的收入比例

Net Revenue Retention = 考虑扩容和涨价后，老客户群体留下来的收入比例
```

NRR 高于 100% 通常说明老客户扩容、涨价或升级超过了流失和降级。NRR 低于 100% 则说明老客户池在缩水，即使公司总收入还可能靠新客户增长。

### 用自己的话解释

订阅业务像一个水桶。新客户是往桶里加水，流失是漏水，扩容和涨价是同一批客户贡献更多水。只看水桶现在多大，不看进水和漏水，就不知道未来水位稳不稳。

ARR 和 RPO 像水位和水管，但不是完整答案。ARR 显示年化经常性收入规模；RPO 显示已签合同里还没确认的收入；留存和流失告诉我们水桶漏不漏。

### 常见误区

- 误区一：把 ARR 当收入。ARR 是年化运行口径，不等于 GAAP 当期收入。
- 误区二：把 RPO 当现金。RPO 是未履约或未确认的合同义务，不一定已经全部收现。
- 误区三：把订阅收入当永远安全。客户可以不续费、减少席位、降级或要求折扣。
- 误区四：只看新客户增长，不看老客户流失。高获客可能掩盖高流失。
- 误区五：把公司没有披露的 NRR 自己硬算。没有公开口径时，只能用 ARR、RPO、递延收入、收入增长和风险因素做间接观察。

## 第二大板块：实时背景与市场传导

### 发生了什么

Adobe 2026 Q2 披露，季度 revenue 为 66.18 亿美元，同比增长 13%；total Adobe ARR 为 271.0 亿美元，其中约 4.80 亿美元来自 Semrush；RPO 为 222.7 亿美元，cRPO 为 67%；total customer group subscription revenue 为 63.9 亿美元，同比增长 14%。Adobe 2026 Q2 Form 10-Q 披露，subscription revenue 为 64.16 亿美元，占 total revenue 的 97%；公司通常按客户订阅协议期限分期确认订阅收入，协议期限通常为 1 到 36 个月。

Microsoft 2026 Q3 披露，Microsoft Cloud revenue 为 545 亿美元，同比增长 29%；commercial remaining performance obligation 增长 99% 至 6,270 亿美元；Azure and other cloud services revenue 同比增长 40%。这些数字说明云和企业订阅合同有很强可见度，但它们仍不是客户留存率本身。

### 为什么重要

订阅业务估值通常更重视可预测性。如果市场相信客户会续费、扩容、接受涨价，并且服务毛利率稳定，DCF 中的未来现金流会更容易被赋予较高持续性。反过来，如果竞争导致续费率下降、折扣上升、AI 推理成本上升或客户减少席位，订阅收入也会被重新定价。

利率背景会放大这一点。Fed 目标区间仍在 3.50%-3.75%，10 年期 Treasury yield 最新官方值为 4.38%，投资级公司债有效收益率为 5.13%。资本成本存在时，市场会更严格地区分“可持续订阅现金流”和“需要不断高投入获客才能维持的增长”。

### 本节采用的数据和来源

| 输入 | 核验值 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Adobe Q2 revenue | 66.18 亿美元，+13% | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 总收入背景 |
| Adobe total ARR | 271.0 亿美元 | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 年化订阅规模 |
| Adobe RPO / cRPO | 222.7 亿美元 / 67% | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 合同收入可见度 |
| Adobe total customer group subscription revenue | 63.9 亿美元，+14% | Adobe 2026-06-11 Form 8-K exhibit 99.1 | 订阅增长 |
| Adobe Q2 subscription revenue share | 97% | Adobe 2026-06-15 Form 10-Q | 商业模式结构 |
| Adobe subscription agreement term | 通常 1 到 36 个月 | Adobe 2026-06-15 Form 10-Q | 收入确认节奏 |
| Microsoft Cloud revenue | 545 亿美元，+29% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 云收入规模 |
| Microsoft commercial RPO | 6,270 亿美元，+99% | Microsoft 2026-04-29 Form 8-K exhibit 99.1 | 企业合同可见度 |
| 10 年期 Treasury yield | 4.38% | U.S. Treasury, 2026-06-26 | 折现率背景 |
| IG corporate effective yield | 5.13% | FRED / ICE BofA, 2026-06-25 | 债务成本背景 |

### Adobe：订阅占比高，但仍要拆留存和扩容

Adobe Q2 subscription revenue 占 total revenue 的 97%，说明收入结构高度订阅化。订阅化的好处是收入确认更平滑，管理层和投资者可以用 ARR、RPO、cRPO 观察未来收入可见度。

但学习者要避免直接跳到“所以收入很安全”。Adobe 10-Q 提示，大多数季度订阅收入来自以前季度签下的订阅协议；竞争、AI、客户价格敏感度、新进入者和替代方案可能影响 renewal、upsell 和 cross-sell。也就是说，订阅收入的关键不是“合同曾经签过”，而是客户在下一轮续约时是否继续留下并增加购买。

课堂拆解：

```text
Adobe Q2 total revenue = 66.18 亿美元
Adobe Q2 subscription revenue = 64.16 亿美元
订阅收入占比 = 64.16 / 66.18 = 97.0%
```

这个比例说明商业模式高度依赖订阅，但不能直接推出留存率、流失率或 NRR。要继续查公司是否披露更细的 retention / churn / net expansion 指标；如果没有披露，就只能用 ARR 增长、RPO、递延收入、客户组收入、价格说明、风险因素和现金流间接判断。

### Microsoft：RPO 很大，但 RPO 不是留存率

Microsoft commercial RPO 增长 99% 至 6,270 亿美元，是一个非常大的合同可见度信号。它说明商业客户合同、云服务和企业服务存在未来收入确认基础。

但 RPO 也不是留存率。它可能受合同期限、合同规模、预付款、续约、价格、产品组合和大客户交易影响。要把 RPO 转化成订阅质量判断，还要继续看：

- RPO 后续确认成收入的速度。
- 云毛利率和 AI 推理成本是否稳定。
- 客户是否扩容，还是只签了长期合同但使用不及预期。
- 竞争是否要求降价或增加免费功能。
- 资本开支是否持续高于新增经营利润质量。

### 这些现实事件如何连接理论

- ARR 帮助观察经常性收入规模，但不是 GAAP 收入。
- RPO 帮助观察合同可见度，但不是现金，也不是留存率。
- cRPO 帮助观察较短期的收入可见度，具体口径要看公司定义。
- Deferred Revenue 代表先收钱、后履约确认收入，是负债，不是已经赚完的钱。
- 留存和流失是护城河的直接压力测试：客户留下来，护城河才更像真的；客户离开，护城河就要重新审计。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、Topic 606 收入确认、企业合同、数据安全、AI 监管、知识产权、消费者和企业客户保护。
- 已确认事实：Adobe 披露订阅协议通常在 1 到 36 个月内按服务期确认收入；Adobe 和 Microsoft 披露 ARR、RPO、云收入和订阅收入；Fed、Treasury 和 FRED 提供利率背景。
- 市场可能如何传导：留存下降会削弱 ARR 和 RPO 的解释力；折扣和降级会压低 NRR；AI 成本和竞争会影响毛利率；利率提高会降低远期订阅现金流现值。
- 仍需核验或观察：Adobe 是否披露更明确的 retention / churn / net expansion；AI-first ARR 的续费表现；Semrush 客户整合；Microsoft commercial RPO 转收入速度；云资本开支和毛利率。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Retention | 留存 | 客户继续使用或续费 | 订阅收入稳定性的核心 |
| Churn | 流失率 | 客户或收入离开的比例 | 高流失会让增长质量下降 |
| Gross Revenue Retention | 总收入留存 | 不算扩容时，老客户留下来的收入比例 | 看基础客户盘是否漏水 |
| Net Revenue Retention | 净收入留存 | 算上扩容、涨价、降级和流失后的老客户收入比例 | 看老客户群体是否越买越多 |
| Expansion Revenue | 扩容收入 | 老客户加席位、升级或买更多模块带来的收入 | 能让 NRR 超过 100% |
| Cohort | 客户队列 | 同一时期获得的一批客户 | 用来追踪真实留存路径 |
| ARR | 年化经常性收入 | 把当前订阅收入运行状态年化的指标 | 观察订阅规模，但不等于 GAAP 收入 |
| RPO | 剩余履约义务 | 已签合同中尚未确认收入的部分 | 观察合同收入可见度 |
| cRPO | 当前剩余履约义务 | RPO 中较短期预计确认的部分，具体看公司定义 | 观察较近未来收入可见度 |
| Deferred Revenue | 递延收入 | 已收钱但还没履约确认的收入 | 是负债，说明未来要提供服务 |

## 回顾提示

- 学到本课前建议回顾：第 18 课 RPO 与收入确认、第 19 课递延收入、第 36 课护城河与竞争优势。
- 本课哪些内容会在后续课程继续使用：CAC、LTV、回本周期、单位经济模型、销售效率、客户队列分析和 SaaS 估值。
- 如果看不懂本课，可以先回到：第 10 课三张报表、第 14 课 guidance 与预期差、第 35 课增长质量。

## 案例拆解

- 案例对象：Adobe 的订阅收入质量，与 Microsoft 的 commercial RPO 作对照。
- 已确认事实：
  - Adobe Q2 revenue 为 66.18 亿美元，同比增长 13%；subscription revenue 为 64.16 亿美元，占 total revenue 的 97%。
  - Adobe total Adobe ARR 为 271.0 亿美元，RPO 为 222.7 亿美元，cRPO 为 67%。
  - Adobe 披露订阅收入通常按客户订阅协议期限分期确认，协议期限通常为 1 到 36 个月。
  - Microsoft commercial RPO 增长 99% 至 6,270 亿美元，Microsoft Cloud revenue 为 545 亿美元并增长 29%。
- 来源日期和链接：见本课“来源”。
- 分析推理：Adobe 的订阅化程度很高，收入可见度较强，但客户留存、AI 替代、价格压力和竞争会决定订阅质量；Microsoft 的 RPO 巨大，说明合同可见度强，但仍要看转收入、毛利率、云资本开支和客户扩容。
- 后续验证指标：ARR 增速、RPO 与 cRPO、deferred revenue、subscription revenue growth、gross margin、operating margin、客户组收入、价格调整、续费披露、AI-first ARR、Semrush 整合、客户流失或净收入留存。

## 个人情境连接

- 对关注清单的启发：看到 SaaS 或订阅公司时，不只看收入增长，还要问“老客户是否留下并多买”。
- 对持仓或基金选择的启发：基金重仓订阅软件时，要警惕只看 ARR 或 RPO，而忽略竞争、折扣、AI 成本和客户流失。
- 对工作、收入、消费或风险管理的启发：个人收入也有“留存”。稳定客户、长期合作、复购和口碑，比一次性项目更像可持续现金流。

## 结论边界

- 可以确定：订阅收入质量必须拆成新客户、续费、扩容、降级、流失、价格和收入确认；ARR、RPO、cRPO 和递延收入各自回答不同问题。
- 不能确定：本课没有计算 Adobe 或 Microsoft 的 NRR，因为公开材料没有给出统一可直接计算的完整留存口径。
- 需要继续观察：Adobe AI-first ARR 是否留存并扩容，Semrush 是否带来高质量客户，Microsoft commercial RPO 是否高质量转收入，竞争是否压低价格和毛利率。
- 不构成投资建议的原因：本课只训练订阅收入质量和留存分析，不推荐买入或卖出任何证券。

## 练习题

1. 为什么 ARR 不等于 GAAP 收入？
2. 为什么 RPO 不是现金，也不是客户留存率？
3. 一家公司期初老客户收入为 100，流失 8，降级 4，扩容 20。它的 Gross Revenue Retention 和 Net Revenue Retention 分别是多少？
4. Adobe Q2 subscription revenue 占 total revenue 的 97%，这个事实能说明什么？不能说明什么？
5. 如果一家订阅公司总收入增长很快，但 NRR 低于 100%，你会继续追问哪三个问题？

## 学习交接

- 本课已经完成：把护城河证据推进到客户留存、流失率、NRR、ARR、RPO、cRPO 和订阅收入质量。
- 本课最重要的一句话：订阅收入不是自动安全，真正要看老客户是否留下、扩容并愿意继续付费。
- 需要复习的关键词：Retention、Churn、Gross Revenue Retention、Net Revenue Retention、Expansion Revenue、Cohort、ARR、RPO、cRPO、Deferred Revenue。
- 还不稳定、下次要回看的地方：获客成本、客户生命周期价值和回本周期如何把“客户质量”转成“单位经济模型”。
- 适合下次打开仓库先读的文件：`LEARNING_STATE.md`

## 下节课安排

- 建议主题：第三十八课：CAC、LTV 与回本周期入门。
- 学习目标：理解为什么订阅公司不仅要留住客户，还要用合理成本获得客户，并在足够短时间内收回销售和营销投入。
- 建议案例：继续使用 Adobe 与 Microsoft，可加入一只明确披露 sales and marketing、subscription revenue、customer growth 或 SaaS 指标的公司作对照；必须重新核验 SEC、公司 IR 或权威来源。
- 必须解释的关键词：CAC、LTV、Payback Period、Sales Efficiency、Magic Number、Gross Margin、Customer Lifetime、Cohort Payback、Unit Economics、Rule of 40。
- 下节课开始前需要联网核验的数据：Adobe 与 Microsoft 最新 sales and marketing、R&D、subscription revenue、gross margin、RPO、ARR、operating cash flow；如加入对照公司，必须核验其最新 SEC/IR 披露和 SaaS 指标口径。

## 来源

- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Microsoft Form 8-K exhibit 99.1, 2026-04-29: https://www.sec.gov/Archives/edgar/data/789019/000119312526191457/msft-ex99_1.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- U.S. Treasury Daily Treasury Par Yield Curve Rates: https://home.treasury.gov/resource-center/data-chart-center/interest-rates/TextView?type=daily_treasury_yield_curve&field_tdr_date_value=2026
- FRED / ICE BofA US Corporate Index Effective Yield: https://fred.stlouisfed.org/series/BAMLC0A0CMEY
