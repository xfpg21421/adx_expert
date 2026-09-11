# 09_联盟营销Affiliate

> **本目录用途**：**海外重点专题**。Affiliate 是一套与"平台直投"完全不同的商业与技术体系：
> 去中心化、按效果结算、长尾参与者极多、追踪与反作弊博弈激烈。

**在全局中的位置**：玩法层第一块。上游依赖 `08_海外广告生态` 的流量与平台认知、`07_追踪Cookie与归因` 的追踪技术；
与 `10_广告套利Arbitrage` 是"卖货 vs 卖流量差价"的姐妹关系，两者经常混用同一套漏斗。

---

## 文档清单

- [x] `Affiliate体系总览.md` —— 三方/四方模型（Merchant – Affiliate – Network – Consumer）；与程序化广告、Ad Network 的**本质区别**；生态规模与主要形态
- [x] `联盟角色与佣金模型.md` —— CPS / CPA / CPL / CPI / CPC 佣金结构、Recurring Commission（订阅分成）、Tiered / 二级分销、**Cookie Duration（联盟窗口期）如何决定收益**
- [x] `主流联盟网络盘点.md` —— CJ / Impact / ShareASale（Awin）/ Rakuten / FlexOffers / PartnerStack / Tradedoubler / Pepperjam：类目优势、准入门槛、结算周期与门槛、EPC 数据透明度
- [x] `CPA网络与Offer市场.md` —— CPA 网络运作机制、Offer 类型（Nutra / Sweepstakes / Finance / App Install / Lead Gen）、Payout 与 Cap、Exclusive 的概念、Offer 质量评估
- [x] `电商Affiliate与亚马逊联盟.md` —— Amazon Associates 佣金结构变化史、Alternatives（Awin / Impact 上的品牌计划）、比价与优惠券站、内容测评站模式
- [x] `联盟追踪技术与Postback.md` —— 联盟链接结构（Affiliate ID / Sub ID / Click ID）、跳转与 Cookie 写入、**Server Postback（S2S）流程**、Pixel 回传、追踪丢单排查
- [x] `落地页与转化漏斗设计.md` —— Pre-lander / Lander / Bridge Page 的作用与合规边界、漏斗各步转化率基准、Advertorial 形态、合规红线（虚假宣称）
- [x] `Niche站与内容站变现.md` —— 选品与选关键词、SEO 与内容生产、Affiliate 链接布局、内容与广告位组合收益模型、Google 算法更新（HCU）对内容站的冲击
- [x] `邮件营销与私域List.md` —— List Building 机制、Lead Magnet、ESP 选择与送达率、邮件合规（CAN-SPAM / GDPR）、List 的资产属性与估值
- [x] `联盟反作弊与扣量.md` —— 联盟侧作弊形态（Cookie Stuffing / Brand Bidding / 优惠券劫持 / 归因抢占）与商家侧扣量（Shaving）；双方博弈与检测手段
- [x] `Affiliate单位经济与规模化.md` —— 从个人到团队的规模化路径；买量型 Affiliate 的毛利模型；人力 / 工具 / 流量成本结构；规模化后的边际收益递减
- [ ] `联盟案例拆解/` —— 具体联盟玩家、Offer、站群的拆解，命名 `YYYYMMDD_案例名.md`

**建议顺序**：Affiliate体系总览 → 联盟角色与佣金模型 → 联盟追踪技术与Postback → 主流联盟网络盘点（先分清概念与佣金逻辑，再打通追踪技术，最后盘点网络）→ CPA网络 → 落地页漏斗 → Niche站 → 单位经济

---

## 写作要点

### 红线：三个"联盟"必须分清

中文里 **Affiliate Network / CPA Network / Ad Network 都译作"联盟"**，这是本领域最大的混淆源。
`Affiliate体系总览.md` 开篇必须给出对照表，其他文档引用时不得混用：

| | Affiliate Network | CPA Network | Ad Network |
|---|---|---|---|
| 英文 | Affiliate Network | CPA Network / Offer Network | Ad Network |
| 结算依据 | 多为 CPS（成交分成） | CPA/CPL/CPI（动作付费） | CPM/CPC（展示点击） |
| 推广者是谁 | 内容站、博主、KOL、比价站 | 买量投放者、Media Buyer | 广告主（买方视角） |
| 典型代表 | CJ、Impact、Awin、Rakuten | ClickDealer、Adsterra、Zeydoo | AdSense（展示侧）、穿山甲 |
| 核心资产 | 内容 + SEO + 邮件列表 | 投放能力 + 漏斗优化 | 流量池 + 定价能力 |
| 我赚的是 | 商家的佣金 | 商家的佣金 | 买卖流量的差价 |

### 其他要求

- **追踪链路必须画图**，从"用户点击联盟链接"到"佣金到账"逐跳标出：
  跳转服务 → Cookie/Click ID 写入 → 商家转化 → 网络回传（Postback/Pixel）→ 审核期 → 结算。
  每一跳标明**丢单原因**（Cookie 被拦、跨设备、窗口期过期、退货撤单、被判定作弊）。
- **Cookie Duration 是联盟经济学的核心变量**，要单独讲：7 天 vs 30 天 vs 90 天 vs Session-only
  对同一流量 EPC 的影响量级，以及为什么商家在缩短窗口期。
- 所有玩法**算到单位经济**：
  ```
  利润 = UV × 点击率 × 转化率 × Payout − 流量成本 − 工具成本 − 人力
  EPC  = 收入 / 点击数        （联盟侧核心指标）
  EPK  = 收入 / 千次点击       （便于与买量 CPC 直接比较）
  ```
- **合规边界要写清**：Advertorial 与虚假宣称、健康类（Nutra）宣称红线、FTC 披露义务（`#ad` / affiliate disclosure）、
  GDPR 下的 Cookie 同意要求。研究"为什么有人越线"但不提供越线方法。
- 涉及具体平台佣金比例、结算门槛的一律标 `[政策]` + 时点（Amazon Associates 佣金表历史上改过多次）。

## 关联目录

- 追踪技术原理 → [`../07_追踪Cookie与归因/服务端追踪与S2S回传.md`](../07_追踪Cookie与归因/)
- 归因劫持与联盟作弊 → [`../13_反作弊与流量质量/扣量与联盟作弊博弈.md`](../13_反作弊与流量质量/)
- 买量做联盟 = 套利 → [`../10_广告套利Arbitrage/联盟套利漏斗.md`](../10_广告套利Arbitrage/)
- 海外流量地域与 Tier → [`../08_海外广告生态/海外流量Tier分层与地域特征.md`](../08_海外广告生态/)
- 内容站另一条变现腿 → [`../12_流量变现与商业化/`](../12_流量变现与商业化/)
- 术语 → [`../02_核心术语与知识库/联盟与套利术语.md`](../02_核心术语与知识库/)
