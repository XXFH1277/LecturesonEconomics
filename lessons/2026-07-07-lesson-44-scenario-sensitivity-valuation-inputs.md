# 第四十四课：情景假设、敏感性表与估值输入入门

## 基本信息

- 日期：2026-07-07
- 数据截至：2026-07-07 20:05（Asia/Shanghai）。公司事实采用 Microsoft 2026-04-29 Form 10-Q XBRL 表、Adobe 2026-06-11 Form 8-K exhibit 99.1 与 2026-06-15 Form 10-Q；利率背景采用 Federal Reserve 2026-06-17 FOMC statement 与 Federal Reserve H.15 2026-07-06 release（利率表最新市场数据到 2026-07-02，2026-07-03 标注为市场休市）。
- 主题：为什么预测不能只给一个数字，而要用 Base / Bull / Bear、敏感性表和估值输入来表达边界。
- 学习目标：理解情景假设、关键驱动、敏感性表、WACC、终值增长率、退出倍数和安全边际如何连接三表预测、DCF 与估值倍数。
- 相关资产：股票、软件公司、云计算、AI 基础设施、自由现金流、DCF、利率、回购和每股指标。
- 核心来源：
  - Microsoft Form 10-Q XBRL income statement table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
  - Microsoft Form 10-Q XBRL balance sheet table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R4.htm
  - Microsoft Form 10-Q XBRL cash flow table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
  - Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
  - Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
  - Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
  - Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/

## 第一大板块：理论基础

### 本课从哪个零基础问题开始

上一课把收入、毛利、费用、现金流、资本开支和股数连成三表预测。今天继续问一个更实用的问题：

> 如果模型里填出一个未来自由现金流，为什么还不能说“这就是公司的价值”？

因为预测不是事实，而是一组假设。收入增长可能更强也可能更弱，毛利率可能扩张也可能被 AI 基础设施成本压低，WACC 可能因为利率变化而上升或下降。真正有用的模型不是给一个漂亮数字，而是告诉你：哪些假设在控制结论。

### 参考的教材式概念顺序

1. Base Case：最中性的基准情景。
2. Bull Case：更乐观但仍要有证据的情景。
3. Bear Case：更保守或压力更大的情景。
4. Key Driver：真正推动模型变化的变量。
5. Sensitivity Table：让两个关键变量同时变化，看结论如何改变。
6. Valuation Input：进入 DCF 或倍数估值前必须明确的输入。
7. Margin of Safety：用不确定性要求折扣，而不是用乐观故事消灭风险。

### 核心概念

最小情景模型可以先从这一张表开始：

| 输入 | Bear | Base | Bull | 为什么是关键驱动 |
| --- | ---: | ---: | ---: | --- |
| Revenue Growth | 低 | 中 | 高 | 决定收入起点 |
| Gross Margin | 承压 | 稳定 | 扩张 | 决定收入留下多少毛利 |
| Operating Expense Ratio | 上升 | 稳定 | 下降 | 决定经营杠杆 |
| Capex Intensity | 高 | 中 | 低 | 决定利润能否变成自由现金流 |
| WACC | 高 | 中 | 低 | 决定未来现金流折回今天的力度 |
| Terminal Growth | 低 | 中 | 高 | 决定终值假设 |
| Diluted Share Count | 稀释 | 稳定 | 回购抵消稀释 | 决定每股结果 |

DCF 里最容易放大结论的简化公式是：

```text
Terminal Value = 下一期自由现金流 / (WACC - Terminal Growth)
```

这个公式的重点不是让初学者机械算目标价，而是看到一个事实：当 WACC 和长期增长率的差距很小，终值会被明显放大；当 WACC 上升或长期增长率下降，估值会快速收缩。

### 用自己的话解释

Base / Bull / Bear 像是给未来画三条路：

- Base：正常走路，假设大多数事情按目前证据延续。
- Bull：顺风走路，假设产品、客户、成本和利率都更配合。
- Bear：逆风走路，假设需求、毛利、费用、资本开支或利率出现压力。

敏感性表像是把模型最脆弱的两个旋钮放到桌面上。比如 WACC 从 8% 到 10%，终值增长率从 2% 到 4%，你马上能看到结论差异。它训练的不是“预测更准”，而是“知道自己哪里最可能错”。

### 常见误区

- 误区一：Bull Case 可以随便乐观。乐观情景也必须有收入驱动、毛利率和现金流证据。
- 误区二：Bear Case 只是把增长率调低。真正的压力可能来自毛利率、费用率、资本开支、股数、税率和利率。
- 误区三：敏感性表越复杂越专业。初学者先看两个关键变量，通常比堆很多参数更有用。
- 误区四：估值输入等于估值结论。输入只说明假设，不能替代投资判断。
- 误区五：一个季度的数据可以直接外推五年。单季数据适合作锚点，不适合作承诺。

## 第二大板块：实时背景与市场传导

### 发生了什么

Microsoft 2026-04-29 Form 10-Q XBRL income statement table 显示，FY2026 Q3 revenue 为 828.86 亿美元，gross margin 为 560.58 亿美元，operating income 为 383.98 亿美元，net income 为 317.78 亿美元。现金流表显示，FY2026 Q3 net cash from operations 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元，common stock repurchased 为 46.27 亿美元，cash dividends paid 为 67.56 亿美元。

Adobe 2026-06-11 Form 8-K exhibit 99.1 显示，Q2 FY2026 revenue 为 66.18 亿美元，同比增长 13%，constant currency 增长 11%；gross profit 为 59.03 亿美元，GAAP operating income 为 22.38 亿美元，cash flows from operations 为 21.65 亿美元，repurchases of common stock 为 21.11 亿美元，diluted shares 为 4.02 亿股。Adobe 2026-06-15 Form 10-Q 还披露，2026-05-29 remaining performance obligations 为 222.7 亿美元，约 67% 预计在未来 12 个月确认。

Federal Reserve 2026-06-17 FOMC statement 显示，FOMC 维持 federal funds rate 目标区间在 3.50%-3.75%。Federal Reserve H.15 2026-07-06 release 显示，2026-07-02 的 10-year Treasury constant maturity yield 为 4.49%，10-year TIPS yield 为 2.26%。

### 为什么重要

同样是高质量科技公司，Microsoft 和 Adobe 的情景输入会很不一样：

- Microsoft 的 AI/cloud 增长强，但 property and equipment additions 很高，Capex Intensity 是必须单独做情景的变量。
- Adobe 的毛利率和资本开支结构更轻，但回购、SBC、并购、RPO、递延收入和 guidance 仍会影响每股现金流。
- Fed 利率和 Treasury yield 不直接决定公司收入，但会影响 WACC、债务成本和市场愿意给未来现金流的折现倍数。

### 本节采用的数据和来源

| 输入 | 已核验数据 | 来源与日期 | 本课用途 |
| --- | ---: | --- | --- |
| Microsoft revenue | 828.86 亿美元 | SEC XBRL R2, 2026-04-29 | 情景收入起点 |
| Microsoft gross margin | 560.58 亿美元，约 67.6% | SEC XBRL R2, 2026-04-29 | 毛利率输入 |
| Microsoft operating income | 383.98 亿美元，约 46.3% operating margin | SEC XBRL R2, 2026-04-29 | 费用率和经营杠杆 |
| Microsoft operating cash flow | 466.79 亿美元 | SEC XBRL R6, 2026-04-29 | 现金流输入 |
| Microsoft additions to property and equipment | 308.76 亿美元，约为收入 37.2% | SEC XBRL R6, 2026-04-29 | Capex Intensity 输入 |
| Adobe revenue | 66.18 亿美元，+13% | SEC 8-K exhibit 99.1, 2026-06-11 | 情景收入起点 |
| Adobe gross profit | 59.03 亿美元，约 89.2% gross margin | SEC 8-K exhibit 99.1, 2026-06-11 | 毛利率输入 |
| Adobe operating cash flow | 21.65 亿美元 | SEC 8-K exhibit 99.1, 2026-06-11 | 现金流输入 |
| Adobe purchases of property and equipment | 0.58 亿美元，约为收入 0.9% | SEC 8-K exhibit 99.1, 2026-06-11 | 资产轻模式对照 |
| Adobe RPO | 222.7 亿美元，约 67% 预计 12 个月内确认 | SEC Form 10-Q, 2026-06-15 | 收入可见度边界 |
| Federal funds target range | 3.50%-3.75% | Fed FOMC statement, 2026-06-17 | 折现率背景 |
| 10-year Treasury / 10-year TIPS | 4.49% / 2.26%（2026-07-02） | Fed H.15, 2026-07-06 | 无风险利率和实际利率背景 |

### 这些现实事件如何连接理论

Microsoft 的教学口径自由现金流可以先粗略写成：

```text
FCF = Operating Cash Flow - Additions to Property and Equipment
FCF = 466.79 - 308.76 = 约 158.03 亿美元
```

Adobe 的教学口径自由现金流可以写成：

```text
FCF = Operating Cash Flow - Purchases of Property and Equipment
FCF = 21.65 - 0.58 = 约 21.07 亿美元
```

这不是说 Adobe 一定比 Microsoft 好，也不是说 Microsoft 一定投资过度。它只说明：情景表里必须把资本开支强度单独拿出来。AI/cloud 的 Bear Case 可能不是收入差，而是收入不错但 Capex 继续高；资产轻软件的 Bear Case 可能不是 Capex 高，而是增长、ARR、并购整合、回购价格或客户续费不达预期。

### 至少一个真实市场机制案例

真实市场机制是：利率通过折现率影响估值输入。假设某公司第 N 年后的稳定自由现金流为 100，终值增长率为 3%：

| WACC | Terminal Growth | 简化终值倍数：1 / (WACC - g) | 教学含义 |
| ---: | ---: | ---: | --- |
| 8% | 3% | 20.0x | 低折现率会放大长期现金流 |
| 9% | 3% | 16.7x | WACC 上升 1 个百分点，终值明显下降 |
| 10% | 3% | 14.3x | 长期价值对折现率很敏感 |
| 9% | 2% | 14.3x | 长期增长率下调也会压缩终值 |
| 9% | 4% | 20.0x | 乐观长期增长率会明显放大终值 |

这张表不用于给 Microsoft、Adobe 或任何证券定价，只用于说明敏感性：当估值结论主要来自远期终值时，WACC 和 terminal growth 的小变化会造成大差异。

## 政治、制度和规则视角

- 涉及的政策、监管、制度或国际关系：SEC 披露制度、U.S. GAAP、非 GAAP 指标、公司 forward-looking statements、Fed 利率政策、美国国债收益率曲线、AI 基础设施资本开支。
- 已确认事实：公司数据来自 SEC 文件；利率数据来自 Federal Reserve；本课未使用实时股票价格或交易所报价。
- 市场可能如何传导：利率上升会提高折现率和资金机会成本；AI 资本开支若持续偏高，会让市场从收入增长转向自由现金流质量；回购能改善每股指标，但会消耗现金。
- 仍需核验或观察：Microsoft AI/cloud 投资回报、Adobe AI-first ARR 和 Semrush 并购贡献、RPO 转收入节奏、SBC 与回购对股数的净影响、Fed 后续利率路径。

## 关键词词典

| 关键词 | 中文翻译 | 白话解释 | 为什么重要 |
| --- | --- | --- | --- |
| Base Case | 基准情景 | 最中性的假设组合 | 防止只看乐观或悲观 |
| Bull Case | 乐观情景 | 需要证据支撑的顺风假设 | 看上行空间来自哪里 |
| Bear Case | 悲观情景 | 需求、利润率、现金流或利率承压 | 看下行风险来自哪里 |
| Key Driver | 关键驱动 | 最能改变结论的变量 | 把注意力放到真正重要处 |
| Sensitivity Table | 敏感性表 | 同时改变关键假设，看结果变化 | 识别模型脆弱点 |
| WACC | 加权平均资本成本 | 股权和债务资金成本的合成 | DCF 折现率核心输入 |
| Terminal Growth | 终值增长率 | 稳定期以后假设的长期增长 | 会明显影响终值 |
| Exit Multiple | 退出倍数 | 用未来 EBITDA、收入或 FCF 乘倍数估终值 | 倍数法终值输入 |
| Margin of Safety | 安全边际 | 用折扣吸收不确定性 | 防止把估算当事实 |
| Capex Intensity | 资本开支强度 | 资本开支占收入比例 | 判断增长是否消耗大量现金 |
| FCF Margin | 自由现金流率 | 自由现金流占收入比例 | 连接三表预测和估值 |
| Forward-looking Statement | 前瞻性陈述 | 公司对未来的估计或目标 | 不是确定承诺 |

## 回顾提示

- 学到本课前建议回顾：第 30 课 DCF、第 31 课情景分析与敏感性分析、第 32 课 WACC、第 41 课稀释与回购、第 43 课三表预测。
- 本课哪些内容会在后续课程继续使用：估值区间、概率权重、安全边际、反证指标、投资备忘录和复盘制度。
- 如果看不懂本课，可以先回到：第 29 课自由现金流、第 35 课增长质量、第 42 课收入驱动。

## 案例拆解

- 案例对象：Microsoft 与 Adobe 的情景输入对照。
- 已确认事实：
  - Microsoft FY2026 Q3 revenue 为 828.86 亿美元，gross margin 为 560.58 亿美元，operating cash flow 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元。
  - Adobe Q2 FY2026 revenue 为 66.18 亿美元，gross profit 为 59.03 亿美元，operating cash flow 为 21.65 亿美元，purchases of property and equipment 为 0.58 亿美元，remaining performance obligations 为 222.7 亿美元。
  - Fed 2026-06-17 维持 federal funds target range 在 3.50%-3.75%；H.15 2026-07-06 显示 2026-07-02 的 10-year Treasury 为 4.49%，10-year TIPS 为 2.26%。
- 来源日期和链接：见本课“来源”。
- 分析推理：Microsoft 的情景模型必须重点追踪 Capex Intensity、AI/cloud 增长和现金流转换；Adobe 的情景模型必须重点追踪 ARR/RPO、毛利率、回购、股数和并购整合。两者都必须把利率作为估值输入，而不是只看收入增长。
- 后续验证指标：segment revenue growth、gross margin、operating expense ratio、operating cash flow、capex, depreciation, RPO/cRPO, SBC, repurchases, diluted shares, 10-year Treasury, 10-year TIPS, Fed statement。

## 个人情境连接

- 对关注清单的启发：每家公司至少写出 Bear / Base / Bull 三种假设，不要只保存一个目标价。
- 对持仓或基金选择的启发：主题基金里的 AI/cloud 公司可能共享同一个 Capex 和利率风险，不能只看名称是否都属于“科技”。
- 对工作、收入、消费或风险管理的启发：个人职业规划也可以做情景表：收入增长、技能投入、现金储备、利率和不可预期支出都会改变最终自由现金流。

## 结论边界

- 可以确定：情景分析和敏感性表能帮助初学者看到估值结论由哪些假设控制。
- 不能确定：本课不能给出 Microsoft、Adobe 或任何证券的内在价值，也没有使用实时股票价格。
- 需要继续观察：AI 投资回报、资本开支强度、Fed 利率路径、公司回购价格、SBC 稀释和 RPO 转收入速度。
- 不构成投资建议的原因：本课只训练模型假设和风险边界，不建议买入、卖出或持有任何证券。

## 练习题

1. 为什么 Base / Bull / Bear 不是“随便填三个增长率”，而是一组完整假设？
2. Microsoft FY2026 Q3 operating cash flow 为 466.79 亿美元，additions to property and equipment 为 308.76 亿美元。教学口径 FCF 约是多少？
3. Adobe Q2 FY2026 gross profit 为 59.03 亿美元，revenue 为 66.18 亿美元。毛利率约是多少？
4. 如果 WACC 从 8% 上升到 10%，而 terminal growth 不变，终值方向会怎样变化？为什么？
5. 选一家公司，写出你认为最关键的两个敏感性变量，并说明为什么不是其他变量。

## 学习交接

- 本课已经完成：把第 43 课的三表预测推进到 Base / Bull / Bear 情景、敏感性表和估值输入。
- 本课最重要的一句话：模型的价值不在于给出一个数字，而在于暴露哪些假设决定了这个数字。
- 需要复习的关键词：Base Case、Bull Case、Bear Case、Key Driver、Sensitivity Table、WACC、Terminal Growth、Exit Multiple、Margin of Safety、Capex Intensity、FCF Margin。
- 还不稳定、下次要回看的地方：如何把情景结果进一步变成估值区间、概率权重、安全边际和反证指标。
- 适合下次打开仓库先读的文件：`lessons/2026-07-07-lesson-44-scenario-sensitivity-valuation-inputs.md`

## 下节课安排

- 建议主题：第四十五课：从估值区间到安全边际、反证指标与学习型风控。
- 学习目标：理解如何把 Bear / Base / Bull 的输出变成估值区间、概率加权结果、反向 DCF 问题、复盘触发条件和非投资建议式的风险清单。
- 建议案例：继续使用 Microsoft 与 Adobe，把“一个估值数字”拆成“区间 + 假设 + 反证指标 + 复盘节奏”。
- 必须解释的关键词：Valuation Range、Probability Weighting、Reverse DCF、Margin of Safety、Thesis、Variant Perception、Kill Criteria、Review Trigger、Hurdle Rate。
- 下节课开始前需要联网核验的数据：Microsoft 与 Adobe 最新 SEC/IR 披露、Fed H.15 最新利率、最新 FOMC statement 或 minutes；如使用市场价格或估值倍数，必须从交易所、Nasdaq、公司 IR、指数公司或权威数据源重新核验。

## 来源

- Microsoft Form 10-Q XBRL income statement table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R2.htm
- Microsoft Form 10-Q XBRL balance sheet table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R4.htm
- Microsoft Form 10-Q XBRL cash flow table, period ended 2026-03-31: https://www.sec.gov/Archives/edgar/data/789019/000119312526191507/R6.htm
- Adobe Form 8-K exhibit 99.1, 2026-06-11: https://www.sec.gov/Archives/edgar/data/796343/000079634326000109/adbeex991q226.htm
- Adobe Form 10-Q, period ended 2026-05-29: https://www.sec.gov/Archives/edgar/data/796343/000079634326000112/adbe-20260529.htm
- Federal Reserve FOMC statement, 2026-06-17: https://www.federalreserve.gov/newsevents/pressreleases/monetary20260617a.htm
- Federal Reserve H.15 Selected Interest Rates, release dated 2026-07-06: https://www.federalreserve.gov/releases/h15/
