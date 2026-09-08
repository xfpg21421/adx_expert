# 08_海外广告生态

> **本目录用途**：海外生态的**主索引**。按协作规则，海外内容是本项目的研究重点，本目录是重点中的骨架——
> 平台、程序化供应链、隐私法规、地域分层四条主线。

**在全局中的位置**：生态层。与 `14_国内市场与生态` 构成对照组（两边用相同的表格维度写，便于直接 diff）；
是 `09_联盟营销Affiliate` 与 `10_广告套利Arbitrage` 的上游背景。

---

## 文档清单

### 全景与围墙花园
- [ ] `海外广告生态全景.md` —— 一张生态图：**围墙花园（Walled Garden）** vs **开放互联网（Open Web）**；两大阵营的玩家、流量、份额与博弈
- [ ] `Google广告体系.md` —— Search / Display（GDN）/ YouTube / Discover / Shopping / PMax / AdMob / Ad Manager 全矩阵；Smart Bidding；Privacy Sandbox 的"既是裁判又是运动员"问题
- [ ] `Meta广告体系.md` —— FB / IG / Audience Network / Messenger；Advantage+ 自动化投放；CAPI 与信号质量；ATT 冲击后的恢复路径；竞价与排名机制
- [ ] `TikTok与短视频广告.md` —— TikTok Ads / Pangle / Spark Ads；短视频创意逻辑；东南亚 / 中东 / 拉美的差异化表现；与 Reels / Shorts 对比
- [ ] `AmazonAds与零售媒体.md` —— Sponsored Products / Brands / Display、Amazon DSP、AMC（Marketing Cloud）；零售媒体为何是当前增长最快的板块
- [ ] `其他主流平台-Microsoft-X-Snap-Reddit.md` —— Microsoft Advertising（Bing / LinkedIn 生态）、X Ads、Snapchat、Reddit、Pinterest、Spotify、Unity / AppLovin（游戏侧）

### 开放互联网与程序化
- [ ] `程序化生态与主要玩家.md` —— Open Web 程序化全链路玩家图谱；供应链路径（Supply Path）与 SPO（供应链优化）；Reseller 与 `ads.txt` / `sellers.json` / `app-ads.txt` / SupplyChain Object
- [ ] `头部DSP盘点.md` —— The Trade Desk / DV360 / Amazon DSP / Criteo / MediaMath（历史）/ Xandr / Yahoo DSP：定位、优势、计费、适用客户
- [ ] `头部SSP与ADX盘点.md` —— Magnite / PubMatic / OpenX / Index Exchange / Google AdX / Smart / Equativ：流量结构、Take Rate、接入要求

### 合规与地域
- [ ] `海外隐私法规-GDPR-CCPA-TCF.md` —— GDPR 核心条款与执法案例、CCPA/CPRA、美国各州法拼图、**TCF 2.2 字符串结构与 Vendor 管理**、IAB 合规要求、罚则量级
- [ ] `海外流量Tier分层与地域特征.md` —— T1/T2/T3 国家清单与 eCPM 量级差异；各地区主流平台、支付方式、内容偏好、合规特殊要求（印度 / 巴西 / 印尼 / 中东）
- [ ] `出海广告投放与结算.md` —— 出海主体与账户开设、支付与结算通道、税务（预扣税 / 发票）、多币种、代理与返点、常见踩坑

**建议顺序**：海外广告生态全景 → 程序化生态与主要玩家 → 海外隐私法规 → 海外流量Tier分层（这四篇是海外认知的四根柱子）→ Google → Meta → 其余平台与盘点

---

## 写作要点

### 平台类文档的统一维度（8 项，便于横向对比）

| 维度 | 要写清什么 |
|---|---|
| 流量来源 | 自有产品 / 联盟 / 第三方；量级与地区分布 |
| 广告产品矩阵 | 各产品线定位与适用目标 |
| 竞价与计费 | 拍卖机制、计费方式、最低门槛 |
| 定向能力 | 一方数据丰富度、可用定向维度、隐私限制后的变化 |
| 报表与 API | 数据粒度、延迟、Raw Data 出口、API 能力 |
| 准入门槛 | 开户要求、审核、最低预算、代理体系 |
| 抽成结构 | Take Rate / 分成比例（标时点与来源） |
| 适用场景 | 什么行业、什么目标、什么阶段最该用它 |

### 其他要求

- **围墙花园 vs 开放互联网**是本目录最重要的心智模型，第一篇就要立住：
  前者数据闭环、自报数、不可核查；后者供应链长、可验证、但存在套利与欺诈空间。
- **供应链透明度**要单独讲透：`ads.txt`（谁授权卖）、`sellers.json`（谁是卖家）、
  SupplyChain Object（这一跳经过了谁）——这三件套是识别供应链套利的唯一手段。
- 盘点类文档**用表格 + 分层**，不做无根据的排名；每家标清数据来源与时间。
- 合规文档必须标 `[政策]` + 时点，并列入 `研究进度看板.md` §六 失效复核清单。TCF 字符串要能逐段解读。
- Tier 分层要说明**同一个 Tier 内差异也很大**（如 T1 的美国 vs 加拿大 eCPM 差 30%+），给区间不给单点。

## 关联目录

- 国内对照 → [`../14_国内市场与生态/国内vs海外关键差异对照.md`](../14_国内市场与生态/)
- 联盟体系（Open Web 的重要变现出口）→ [`../09_联盟营销Affiliate/`](../09_联盟营销Affiliate/)
- 套利玩法（依赖海外流量差价）→ [`../10_广告套利Arbitrage/`](../10_广告套利Arbitrage/)
- 合规对追踪的影响 → [`../07_追踪Cookie与归因/第三方Cookie消亡与替代方案.md`](../07_追踪Cookie与归因/)
- 合规对定向的影响 → [`../06_定向数据与算法/上下文定向与内容理解.md`](../06_定向数据与算法/)
- 各平台投放操作 → [`../11_广告投放实操/各平台投放手册/`](../11_广告投放实操/)
