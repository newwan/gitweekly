# X 安全情报晚报 · 2026-08-28

> 搜集窗口：圣地亚哥时间 **2026-08-27 20:00 至 2026-08-28 20:35**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周五）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-08-28.json`（collected_at **2026-08-28T20:22:14-04:00**）。CISA KEV catalogVersion **仍为 2026.08.27**／**1685** 条／dateReleased **2026-08-27T17:00:36.6632Z**。**2026-08-28 dateAdded：无新 CVE**；无 08-28 新 CISA Alert。**今日最大新项是 PaperCut Emergency Patch Release 2 + 正式 CVE**（**尚未入 KEV**）。
> X：文件 `/workspace/x-posts-2026-08-28.json`（**27** 条，cve 11／tool 6／apt 10；collected_at **2026-08-28T20:35:00-04:00**；**logged_in=true**／**blocked=false**）。搜索1 Latest 最旧可见约 **2026-08-28T22:01:09Z**（约 **1.5 小时**，高流量，**不可当作完整 24h**）。搜索2 量少可覆盖 24h+（最旧可见至 **2026-07-30**）。搜索3 最旧可见约 **2026-08-28T23:41:55Z**（约 **40 分钟**）。**公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉引用。
> 规则：每条含完整 https URL；分列原帖／仓库／厂商／文章；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、请求样例或 PoC。

## 今日摘要

- **紧急 · PaperCut NG／MF Emergency Patch Release 2 + 正式 CVE（厂商页更新 2026-08-28；尚未入 KEV）**：第一轮紧急补丁已被绕过。现公开 **CVE-2026-82078**（Unsafe Dynamic Class Loading，CWE-470，CVSS 4.0 **9.4**）与 **CVE-2026-81578**（Authentication Bypass，CWE-306，CVSS 4.0 **8.8**）。Huntress 在两个客户环境见到利用；watchTowr 报告未认证认证绕过＋RCE 链及第一轮补丁绕过。Release 2 覆盖 NG／MF **v24／v25／v26**（Win／Linux／macOS）；**即使已打第一轮也要再打**。公网 Application Server 仍须立刻把 Web 管理面限制到受信 IP。厂商称攻击有限、针对性，未点名威胁方。**不转写利用细节。** IoC：厂商狩猎字符串＋Release 2 SHA256 见地址／IoC 汇总。
  厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
  文章：https://www.bleepingcomputer.com/news/security/papercut-releases-second-emergency-patch-for-exploited-flaws/ https://thehackernews.com/2026/08/attackers-chain-two-papercut-flaws-to.html
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82078
  X：https://x.com/ZeroDayDevApp/status/2093477948699361494 https://x.com/yousukezan/status/2093480974034313709

- **期限今日 · Gitea CVE-2026-60004（KEV due 2026-08-28）**：dateAdded **2026-08-25**；CWE-94；补丁 **1.27.1**／**GHSA-rcr6-4jqh-j84m**。Shadowserver（BC 引述）：**2026-08-27 仍有 8393 个公网 IP** 未修。默认开放注册可拿到触发所需写权限。GHSA 页含完整 PoC——**本报只记 URL，不抄利用代码**。IoC：未见公开 IoC。
  厂商／GHSA：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
  文章：https://www.bleepingcomputer.com/news/security/over-8-300-gitea-servers-vulnerable-to-code-execution-attacks/
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-60004

- **KEV 未更新（延续昨日三连加）**：catalogVersion **2026.08.27**／**1685**。无 08-28 新 dateAdded。仍有效：**ownCloud CVE-2023-49105**（due **08-30**；补丁 ≥10.13.1，厂商后催 ≥10.13.3）＋ **Linux Kernel CVE-2026-53362**（due **08-30**）＋ **JFrog Artifactory CVE-2026-66384**（due **09-10**；7.146.35／7.161.16 分支）。THN 今日新报 ownCloud 被用于菲律宾核研究机构（中文语境行为体；RSS slug 与标题不符，见下）。IoC：未见公开 IoC。
  CISA：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
  文章：https://thehackernews.com/2026/08/snowflake-github-actions-flaw-lets.html
  X：https://x.com/BotBauR/status/2093477202088087719 https://x.com/snypet86/status/2093459932913774809 https://x.com/swif_ai/status/2093462921498198317

- **期限明日 · Citrix NetScaler CVE-2026-8452 ＋ SQL Server CVE-2019-1068**：联邦期限均为 **2026-08-29**。续报，无今日 KEV 增量。IoC：未见公开 IoC。
  CISA：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
  厂商：https://support.citrix.com/external/article/CTX696604 https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068

- **本窗口新报 · ServiceNow 三枚满分＋一枚高危（厂商称这四项未见恶意利用）**：**CVE-2026-18885／CVE-2026-18886／CVE-2026-74820**（max severity，未认证低复杂度）＋高危 **CVE-2026-6876**（沙箱逃逸）。云侧已打；自管须打 Xanadu／Yokohama／Zurich／Australia 热修。另：此前 **CVE-2026-6875** 曾被报利用（上下文，非本日新利用）。IoC：未见公开 IoC。
  文章：https://www.bleepingcomputer.com/news/security/servicenow-warns-of-three-max-severity-security-vulnerabilities/ https://thehackernews.com/2026/08/three-cvss-100-servicenow-flaws-could.html

- **本窗口新报 · McKesson 披露＋ShinyHunters 声称**：8-K 发现日 **2026-08-25**；第三方应用，调查早期，尚未认定重大。声称：vishing→Okta SSO→Salesforce＋Snowflake；约 1TB（8/21–25）；约 **2.84 亿数据行**（非独立患者）；赎金 **$55,236,150** 未谈。BC 引述域名 **mckesson[.]claims**（ReliaQuest `.claims` 活动形态；BC 未独立核验）。IoC：见地址／IoC 汇总。
  文章：https://www.bleepingcomputer.com/news/security/mckesson-discloses-breach-after-shinyhunters-claims-patient-data-theft/
  X：https://x.com/ThreatAtlas/status/2093489325316927669

- **工具 · Sliver v1.7.6 NEW（2026-08-28T18:37:03Z＝圣地亚哥 14:37）**：昨日晚报仍为 v1.7.3。nuclei-templates **仍为 v10.4.8**（2026-08-24）。IoC：未见公开 IoC。
  仓库：https://github.com/BishopFox/sliver/releases/tag/v1.7.6 https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
  X：https://x.com/LittleJoeTables/status/2093408059326628092

- **本窗口新报（短）**：APT28 关联 HOOKEDGE；ZBT 出厂植入 **CVE-2026-74232／74233**；cPanel **CVE-2026-65643**；Unitree G1 **CVE-2026-76639／76640**；19 个 Chrome／Edge 钱包窃取扩展；柏林州政府拒付（X 窗口将行动归 Rhysida，公开备援未点名，需厂商核验）；GiveWP **CVE-2026-82222**；Hasbro 员工泄露。ICS：**无新 ICSA-26-\***；08-27 列表另有三菱 Update A／D。
- **X 窗口提及、公开备援未独立核验（需厂商／公告交叉）**：**Adobe Commerce CVE-2026-71362**、**Argo Rollouts CVE-2026-82277**、**SparkRAT BYOVD CVE-2026-36425**、以及 **stratum-c2／tailcat／pius** 工具仓库。仅作交叉提示，不作确认在野。

## CVE / POC / 漏洞

### 1. 【紧急／在野／NEW】PaperCut NG／MF CVE-2026-82078＋CVE-2026-81578 · Emergency Patch Release 2（厂商页更新 2026-08-28；尚未入 KEV）

相对昨日晚报（当时**尚无 CVE 号**、仅 v25／v26 第一轮紧急补丁）的关键变化：厂商页 **Last updated August 28, 2026**；正式 CVE 已公开；**第一轮补丁被绕过**；已发 **Emergency Patch Release 2**（AEST 28 Aug **20:42**；v24 于 **22:08**）。Huntress／watchTowr 获致谢。

| CVE | 名称 | CWE | CVSS 4.0 | NVD |
|---|---|---|---|---|
| CVE-2026-82078 | Unsafe Dynamic Class Loading in Database Connector | CWE-470 | **9.4**（AV:N/AC:L/AT:N/PR:H/UI:N/VC:H/VI:H/VA:H/SC:H/SI:H/SA:H） | 已收录，发布／修改 **2026-08-28** |
| CVE-2026-81578 | Authentication Bypass | CWE-306 | **8.8**（AV:N/AC:L/AT:N/PR:N/UI:N/VC:L/VI:H/VA:L/SC:N/SI:N/SA:N） | 厂商页已公开；本轮 NVD 详情页未完整渲染 |

受影响（NVD／PaperCut semver，CVE-2026-82078）：MF／NG **0 < 24.1.10、25.0.13、26.0.5**。

防御动作（厂商，仅高阶）：
- 若 Application Server 暴露公网：**立刻**用防火墙／NAC 把 Web 管理面限制到受信 IP（即使未见可疑活动）。
- **安装 Emergency Patch Release 2**——即使已打第一轮紧急补丁。
- Release 2 覆盖 NG／MF **v24／v25／v26**（Windows／Linux／macOS）。**v23 及更早**：升级到最新，无旧分支紧急补丁。
- Site Server 与二级／打印服务器也要打；Print Deploy 与 Mobility Print 不受影响。
- 卡片／ID 外部库查询客户：按厂商说明在 `server/security.properties` 开启 `security.card-number-lookup.enabled=Y` 并重启（默认关）。

Huntress：两个客户环境见到利用（侦察命令；日志中有 hex 编码 Java `.class`）。watchTowr：未认证认证绕过＋RCE 链及第一轮补丁绕过。厂商称攻击有限、针对性；未点名威胁方。**本报不转写根因、请求样例或利用步骤。KEV 本轮拉取仍无此二 CVE。**

厂商时间线（AEST，摘自公告）：27 Aug 初报 → 28 Aug 02:10 第一轮 v25／v26 → 28 Aug 20:42 Release 2＋Huntress／watchTowr → 28 Aug 22:08 v24 Release 2。

狩猎信号与 Release 2 SHA256：**见地址／IoC 汇总**（厂商原文抄录）。厂商强调：**缺失这些 IoC ≠ 未中招**。

地址：
- 厂商紧急公告：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- BC（Release 2）：https://www.bleepingcomputer.com/news/security/papercut-releases-second-emergency-patch-for-exploited-flaws/
- THN（链利用）：https://thehackernews.com/2026/08/attackers-chain-two-papercut-flaws-to.html
- BC（昨日初报，当时无 CVE）：https://www.bleepingcomputer.com/news/security/papercut-warns-of-ng-mf-flaw-exploited-in-zero-day-attacks/
- THN（昨日零日综述，窗口内）：https://thehackernews.com/2026/08/papercut-zero-day-exploited-in-attacks.html
- NVD CVE-2026-82078：https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- NVD CVE-2026-81578：https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- X：https://x.com/ZeroDayDevApp/status/2093477948699361494
- X：https://x.com/yousukezan/status/2093480974034313709

IoC：厂商狩猎字符串＋全部 Release 2 SHA256 见「地址／IoC 汇总」。未见独立公开的攻击者 C2 IP／域名／样本哈希清单。

### 2. 【KEV 期限今日】Gitea CVE-2026-60004（dateAdded 2026-08-25；联邦期限 2026-08-28）

CWE-94 代码注入。受影响 **≥1.17, <1.27.1**；补丁 **1.27.1**（GHSA 发布 2026-07-28；BC：Gitea 1.27.1 于 2026-07-27 发布）。GHSA CVSS 3.1 **9.8**。默认开放注册可拿到写权限。BC 引述 Shadowserver：**2026-08-27 仍有 8393 个公网 IP** 未修；报道提及挖矿载荷。**GHSA 页含完整 PoC——本报不抄、不链利用代码。** 联邦 BOD 26-04：曾暴露主机取证分诊。

狩猎：立刻升级到 **1.27.1＋**；限制／关闭开放注册与公网暴露；盘点未修实例。

地址：
- GHSA（厂商）：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- 发布：https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- CISA 警报（2026-08-25）：https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- BC：https://www.bleepingcomputer.com/news/security/over-8-300-gitea-servers-vulnerable-to-code-execution-attacks/
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 3. 【本窗口 NEW】ServiceNow CVE-2026-18885／18886／74820／6876（厂商称这四项未见恶意利用）

BC／THN：**CVE-2026-18885、CVE-2026-18886、CVE-2026-74820** 为满分／max severity（未认证、低复杂度）；另有高危 **CVE-2026-6876** 沙箱逃逸。云托管实例厂商已更新；自管／合作伙伴须应用所列 **Xanadu／Yokohama／Zurich／Australia** 热修。厂商声明：**未掌握这四项的恶意利用**。另作上下文（非本日新利用）：此前 **CVE-2026-6875** 曾被报利用。**不转写利用细节。**

地址：
- BC：https://www.bleepingcomputer.com/news/security/servicenow-warns-of-three-max-severity-security-vulnerabilities/
- THN：https://thehackernews.com/2026/08/three-cvss-100-servicenow-flaws-could.html

IoC：未见公开 IoC。

### 4. 【本窗口 NEW】GiveWP WordPress 捐赠插件 CVE-2026-82222

GiveWP 至 **4.16.7.1** 受影响；补丁 **4.16.7.2**（**2026-08-27**）。未认证注册动作＋不安全反序列化 gadget 链（BC 综述）。研究员 Udin Chan via Patchstack。**不转写 gadget／请求样例。**

地址：
- BC：https://www.bleepingcomputer.com/news/security/givewp-wordpress-donation-plugin-flaw-lets-hackers-execute-server-commands/

IoC：未见公开 IoC。

### 5. 【本窗口 NEW】ZBT 路由器出厂植入 CVE-2026-74232／CVE-2026-74233

VulnCheck（THN）：深圳智博通（ZBT）固件出厂植入 SPEAKINGSTONE 与 DARKLANTERN；未认证远程 root。**CVE-2026-74232、CVE-2026-74233**。狩猎：盘点 ZBT 品牌／贴牌路由，隔离管理面，跟进厂商／VulnCheck 处置指引。**不转写植入触发方式。**

地址：
- THN：https://thehackernews.com/2026/08/china-made-zbt-routers-ship-with-two.html

IoC：未见本报可独立核验的 C2／样本哈希清单（以 THN／VulnCheck 原文为准）。

### 6. 【本窗口 NEW】cPanel／WHM CVE-2026-65643

THN：域名停放／附加域名路径；**所有受支持版本**；可致以 root 执行。厂商已发布补丁。托管商应立即打补丁并限制客户可配置域名操作。**不转写利用步骤。**

地址：
- THN：https://thehackernews.com/2026/08/critical-cpanel-flaw-could-let-one.html

IoC：未见公开 IoC。

### 7. 【本窗口 NEW】Unitree G1 EDU CVE-2026-76639／CVE-2026-76640

Olivier Laflamme（THN）：两条独立 root RCE 链；其中一条经 BLE 到 Locomotion PC。狩猎：隔离机器人管理／无线面，跟进厂商固件。**不转写 BLE／RCE 链。**

地址：
- THN：https://thehackernews.com/2026/08/two-unitree-g1-edu-humanoid-robot-flaws.html

IoC：未见公开 IoC。

### 8. 【KEV 延续／新报道】ownCloud CVE-2023-49105（dateAdded 2026-08-27；联邦期限 2026-08-30）

KEV 条目本身相对昨日**无变化**。THN **2026-08-28** 新报：CISA 列入 KEV 与中文语境行为体利用该漏洞、从菲律宾核研究机构窃取记录相关；文章称 CVSS 9.8。**注意 RSS 标题／permalink 不一致**：feed permalink 为 `snowflake-github-actions-flaw-lets.html`，标题为 ownCloud／PH 核研究——按 feed 已发布记录，不以 slug 改写事实。

补丁：ownCloud **≥10.13.1**（厂商后续督促 **≥10.13.3**）。X 交叉：未认证 WebDAV 预签名 URL 绕过（已知用户名＋默认无 signing-key）。**不转写请求样例。**

地址：
- CISA 警报（2026-08-27）：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- 厂商公告：https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- THN（slug 不符，按 RSS 记录）：https://thehackernews.com/2026/08/snowflake-github-actions-flaw-lets.html
- X：https://x.com/BotBauR/status/2093477202088087719
- X：https://x.com/snypet86/status/2093459932913774809
- X：https://x.com/SecNews_GR/status/2093469250207764866

IoC：未见公开 IoC。

### 9. 【KEV 延续短】Linux Kernel CVE-2026-53362（due 2026-08-30）＋ JFrog Artifactory CVE-2026-66384（due 09-10）

相对昨日无 KEV 增量。内核：按发行版更新并重启；期限 **2026-08-30**。Artifactory：自管升到 **7.146.35＋** 或高于 **7.161.16** 的分支；期限 **2026-09-10**。X 窗口有帖将内核与 OpenAI 环境／AI agent 叙事挂钩——以 CISA／发行版公告为准，不转事故利用链。

地址：
- CISA 警报：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- NVD 内核：https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- NVD Artifactory：https://nvd.nist.gov/vuln/detail/CVE-2026-66384
- JFrog：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- X：https://x.com/swif_ai/status/2093462921498198317

IoC：未见公开 IoC。

### 10. 【期限明日短】Citrix NetScaler CVE-2026-8452 ＋ Microsoft SQL Server CVE-2019-1068（due 2026-08-29）

昨日六连加之两条；联邦期限均为 **明天 2026-08-29**。Citrix 补丁 **14.1-72.61＋／13.1-63.18＋**（及对应 FIPS）；SQL Server 按 MSRC。本日无新的厂商／KEV 重写。

地址：
- CISA 警报（2026-08-26）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- Citrix CTX696604：https://support.citrix.com/external/article/CTX696604
- MSRC CVE-2019-1068：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- NVD Citrix：https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- NVD SQL Server：https://nvd.nist.gov/vuln/detail/CVE-2019-1068

IoC：未见公开 IoC。

### 11. 【ICS 延续短】无新 ICSA-26-\*；三菱 Update A／D（列表日期 2026-08-27）

自 **ICSA-26-239-01..05** 之后**无新 ICSA-26-\*** 编号。08-28 无新 ICS 公告。列表页 08-27 另有两条更新（昨日备份未单列）：
- **ICSA-26-078-05** Mitsubishi CNC Series **Update A**（CVE-2025-2399，CVSS 5.9；修订去掉 NC Trainer2／NC Trainer2 plus；补 M700V／M70V／E70 已修复；初版 2026-03-10）
- **ICSA-25-128-03** Mitsubishi Multiple FA Products **Update D**（仅列表，本轮未抓内页）

地址：
- ICS 列表：https://www.cisa.gov/news-events/ics-advisories
- ICSA-26-239-01：https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-01
- ICSA-26-239-02：https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-02
- ICSA-26-239-03：https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-03
- ICSA-26-239-04：https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-04
- ICSA-26-239-05：https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05
- ICSA-26-078-05 Update A：https://www.cisa.gov/news-events/ics-advisories/icsa-26-078-05
- ICSA-25-128-03 Update D：https://www.cisa.gov/news-events/ics-advisories/icsa-25-128-03

IoC：未见公开 IoC。

### 12. 【X 窗口提及 · 需厂商核验】Adobe Commerce CVE-2026-71362／Argo Rollouts CVE-2026-82277／SparkRAT BYOVD CVE-2026-36425

这三条**仅出现在本轮 X 短窗口**，公开备援 JSON／MD **未收录对应厂商公告或独立核验**。作交叉提示，**不升格为已确认在野／已入 KEV**。
- Adobe Commerce「CVE-2026-71362 Exploited」——仅 X＋第三方综述链，未见 Adobe／CISA 本轮备援条目。
- Argo Rollouts Dashboard ≤1.10.0 未认证变更操作 **CVE-2026-82277**（帖称绑定 0.0.0.0、缺认证／CSRF）——仓库链到 argoproj／argo-rollouts，未见官方 advisory 抓取。
- SparkRAT BYOVD **CVE-2026-36425**（帖称关闭 Defender）——THN 08-27 有 Spark RAT／柬埔寨／OPSWAT 驱动文（窗口前）；本轮未把该 CVE 写入公开备援。

地址：
- X Adobe：https://x.com/moton/status/2093460271969001576
- 文章（X 链，未作厂商核验）：https://securityonline.info/adobe-commerce-vulnerability-cve-2026-71362/
- X Argo：https://x.com/UpwindMDR/status/2093467980768129103
- 仓库：https://github.com/argoproj/argo-rollouts
- X SparkRAT：https://x.com/windowsforum/status/2093477029584810204
- 文章（X 链）：https://windowsforum.com/windows-news.4/cve-2026-36425-lets-sparkrat-disable-microsoft-defender.443771/
- THN 08-27（窗口前上下文）：https://thehackernews.com/2026/08/spark-rat-targets-cambodia-abuses.html

IoC：未见公开 IoC（Argo 帖中的 `0.0.0.0` 为监听描述，不当作攻击者基础设施）。

## 工具与 GitHub 发布

### 1. 【NEW】BishopFox／sliver v1.7.6（2026-08-28）

GitHub Releases API： **v1.7.6** 发布于 **2026-08-28T18:37:03Z**（圣地亚哥 **2026-08-28 14:37**）。昨日晚报仍为 **v1.7.3**（2026-02-24T05:08:59Z）。最近 10 条发布对象中，v1.7.6 之后直接是 v1.7.3——**未见 v1.7.4／v1.7.5 发布对象**（release notes 文本对照 v1.7.5，但 API 列表无该对象）。防御：在授权红队与威胁狩猎中识别新版本指纹；禁止未授权使用。

地址：
- 仓库发布：https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- 发布列表：https://github.com/BishopFox/sliver/releases
- X：https://x.com/LittleJoeTables/status/2093408059326628092
- X（仓库首页链，非版本）：https://x.com/the_osps/status/2093066801827705223

IoC：未见公开 IoC。

### 2. nuclei-templates 仍为 v10.4.8

最新 tag **v10.4.8**（**2026-08-24T13:01:50Z**）。相对昨日无新版本。

地址：
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。

### 3. X 窗口内提及的 GitHub 工具（防御向知晓；非 endorsements；需自行核验）

公开备援未收录这些仓库的独立安全评估。标签为 X 窗口提及。
- **stratum-c2**（云存储 dead-drop 通道类 C2 框架）：仓库 https://github.com/LAME-Projects/stratum-c2 ；X：https://x.com/Dinosn/status/2093159323450896585
- **tailscale／tailcat**（帖称红队 C2／隧道／Go 库）：仓库 https://github.com/tailscale/tailcat ；X：https://x.com/sneakerhax/status/2093453346510413927
- **praetorian-inc／pius**（帖称被动侦察管线，授权红队／赏金）：仓库 https://github.com/praetorian-inc/pius ；X：https://x.com/EsGeeks/status/2093340691443122457
- 证据分类文档（红蓝 agent fabric）：https://github.com/msaleme/red-team-blue-team-agent-fabric/blob/main/docs/EVIDENCE-CLASS-TAXONOMY.md ；X：https://x.com/mikesaleme/status/2093482649641689432

IoC：未见公开 IoC。狩猎：在授权环境识别同类工具指纹；禁止未授权使用。

## APT / Malware 分析

### 1. 【NEW】APT28 关联 HOOKEDGE 后门（Recorded Future Insikt／THN）

THN：Recorded Future Insikt 记录针对罗马尼亚、西班牙、土耳其政府／外交机构的活动（约 2025-09 末至 2026-04 初）。此前未公开记录的 **HOOKEDGE** Windows 批处理后门。防御：关注外交／政府 Windows 主机上的异常批处理持久化与 Insikt 原文狩猎点。**不转写后门协议。**

地址：
- THN：https://thehackernews.com/2026/08/apt28-linked-hookedge-backdoor-targets.html

IoC：未见公开 IoC（本报未抄录样本哈希；以 Insikt／THN 原文为准）。

### 2. 【NEW】McKesson 披露＋ShinyHunters 声称（BC；X 交叉）

McKesson 8-K：发现日 **2026-08-25**，涉及第三方应用；调查早期，**尚未认定重大**。ShinyHunters 声称：vishing → Okta SSO → Salesforce＋Snowflake；约 **1TB**（**2026-08-21 至 08-25**）；约 **2.84 亿数据行**（**非独立患者数**）；赎金 **$55,236,150** 未谈。BC 引述域名 **mckesson[.]claims**，称形态吻合 ReliaQuest 观察的 `.claims` 活动；**BC 未独立核验**。X ThreatAtlas 将受害者记为 McKesson／Healthcare／US（2026-08-28）。

地址：
- BC：https://www.bleepingcomputer.com/news/security/mckesson-discloses-breach-after-shinyhunters-claims-patient-data-theft/
- X：https://x.com/ThreatAtlas/status/2093489325316927669

IoC：声称域名 `mckesson[.]claims`（BC 转述、未核验）——见地址／IoC 汇总。未见本报可独立核验的 C2／样本哈希。

### 3. 【NEW】柏林州政府拒付赎金（THN；X 将行动归 Rhysida）

THN：柏林州政府 8 月行政网遭入侵后遭勒索，**拒付**；交通／气候／环境相关部门发现进一步外泄。X 窗口 @aviatrixtrc 将行动归 **Rhysida**，并写 VPN 凭据缺 MFA、横向多日、外泄 **5.79TB**——**这些数字与团伙名未出现在公开备援 THN 摘要中**，作 X 交叉、需原文／官方核验。

地址：
- THN：https://thehackernews.com/2026/08/berlin-refuses-to-pay-hackers-who-stole.html
- X：https://x.com/aviatrixtrc/status/2093488081496052183
- 文章（X 链）：https://aviatrix.com/threat-research-center/berlin-refuses-pay-hackers-stole-data-rhysida-2026/

IoC：未见公开 IoC。

### 4. 【NEW】19 个 Chrome／Edge 钱包窃取扩展（Socket／THN）

Socket（Karlo Zanki）：过去六个月 **18 个 Chrome ＋ 1 个 Edge** 扩展含钱包窃取／抽币代码。防御：盘点浏览器扩展、强制商店来源与企业白名单、吊销可疑钱包会话。

地址：
- THN：https://thehackernews.com/2026/08/19-chrome-and-edge-extensions-found.html

IoC：未见本报抄录的扩展 ID／哈希清单（以 Socket／THN 原文为准）。

### 5. 【NEW】Hasbro 员工数据泄露（BC）

Hasbro 麻州 AG 信函：员工 PII／财务。麻州 AG 报告：**436** 名 MA 员工（SSN／财务／驾照）。公司未披露总数。报道称**未公开挂钩** 2026-03-28 事件（约 2500 万美元营收影响）。

地址：
- BC：https://www.bleepingcomputer.com/news/security/toy-making-giant-hasbro-disclose-data-breach-affecting-employees/

IoC：未见公开 IoC。

### 6. 【NEW 短】Cosmos EVM 模块被利用（THN）

THN：**GHSA-7g4w-cg88-2cq2**（共享 Cosmos EVM 模块）；2026-08-20 至 08-25 被用来抽干六条链。文章**未给 CVE**。受影响版本在 RSS 中被截断（`<0.6.2` 及后续片段未完整）。链上安全事件，非传统主机 IoC。

地址：
- THN：https://thehackernews.com/2026/08/cosmos-evm-flaw-exploited-after-cosmos.html

IoC：未见公开主机／C2 IoC。

### 7. 【X 窗口短】勒索声称监控（需核验）

以下仅 X 短窗口监控号，公开备援无对应厂商／执法确认：
- Qilin → Newton County School System：https://x.com/sec_news_com/status/2093493184991228016
- Qilin → Alter Consultores Legales（ES）：https://x.com/sec_news_com/status/2093493164397240431 https://x.com/TMRansomMon/status/2093491835544989884
- Threeam → wmdn.net：https://x.com/ThreatAtlas/status/2093485369899573649
- 亚特兰大地铁区某市警告勒索事件：https://x.com/kiss1041fm/status/2093485240782111201 ；文章：https://www.kiss104fm.com/news/local/metro-atlanta-city-warns-about-ransomware-incident/7R5O5C62ZRE2BNTJ4JHFZQDMBY/
- Aur0ra／Cursor AI 代理叙事（X only）：https://x.com/nexta_tv/status/2093488806112436643
- 假招聘投毒 `vite.config.ts`（X only，无仓库 URL）：https://x.com/ustas_eth/status/2093488171505913935

IoC：未见公开可核验攻击者基础设施 IoC（受害站点名不当作 IoC）。

## 地址／IoC 汇总

### 本日无公开恶意基础设施 IoC（C2／样本哈希）

- 除下列**厂商狩猎信号／补丁 SHA256／声称域名**外，上述各条：**未见公开攻击者 C2／样本哈希**。
- 不把受害站点、Shadowserver 暴露计数、新闻标题或监听地址 `0.0.0.0` 当 IoC。
- Gitea GHSA 页的 PoC **不抄录**。

### PaperCut 厂商狩猎信号（非 C2；缺失 ≠ 未中招）

来源：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/

- IDS／EDR／网络告警涉及 PaperCut Application Server；`pc-app.exe` 相关可疑后利用
- `server.log` 缺失、截断或删除
- `server.log: ERROR No suitable driver found for jdbc:no:x`
- `server.log: ERROR DatabaseUtils - Database error looking up cardID: VALUES CAST`
- 厂商：缺失这些 IoC **不是**未失陷的证明

### PaperCut Emergency Patch Release 2 SHA256（厂商页原文抄录）

来源：`vendor_followups.patch_sha256_from_vendor_page` ← https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/

| 包 | SHA256 |
|---|---|
| MF_v26_win | `5c63ef18c523c85d5e73efc7fbb2bd2edacf0b03bcf80fe4d7e4c1a7c8bcbcf4` |
| MF_v26_linux | `6117b53dd0610052c53aeafced91cd3d0ad80ed1dcc578e873291a8b697b802a` |
| MF_v26_mac | `7dea84473f8d00d4608b7e797b633f130139e23bf5bba02848a1df0a7e2cc7c6` |
| MF_v25_win | `b296de7da020152a83291378ab4ca5c461d76510648347fd6e69f3fb2cd5e9c9` |
| MF_v25_linux | `296498ef5ec1ac8927dc1ccae9a9aa3c04036da6d2768813e6df818049b3f4a1` |
| MF_v25_mac | `3e5509f0514228031967934d32e4a40512bd6fb5857bfde3002866bc3ede3f9a` |
| MF_v24_win | `75aba456d6629848c89513371c44037f2bdddbc1e39bdadc16d1fed8b59766eb` |
| MF_v24_linux | `7ac8f002fb602d1f54665d8a18a25fc57cf41239ae0c03b18591ee220b57d419` |
| MF_v24_mac | `40581392cc11a1f46b90ab5c2607fdacade77aca0de6629c1d78a2a71548fc9c` |
| NG_v26_win | `c9a2b356910b5fef3c114d48cb7c508414d1d35ddac74c530d1e8923d357e7d4` |
| NG_v26_linux | `3261356ced056fd5ab0962a07178701e80c6ebbce30d7158d20ed3c57b1dcf59` |
| NG_v26_mac | `bdd54d5cb9f20924b059986a44f849df499f7de7cb5cd0a60290d2b2610850e7` |
| NG_v25_win | `b155cf19cdab1b7fc92c2dd030d1c0cd439397d83d7749042f65e2364ca03589` |
| NG_v25_linux | `282be7404a25c12317a2079eed59e8794f0c9d7bd257dee60c39b529da18a46a` |
| NG_v25_mac | `276ee64a7bb4d4e242fe7ddaecf3cd279eee91e83fbd1e6f44050db2f90bda6d` |
| NG_v24_win | `f58a3fe4e9d7543c38a3f01e53f4a9ad34884289a71df25f734af9d977c06319` |
| NG_v24_linux | `a7ea1e2cdb22a4349ae854491b10b89a52d075e9106ec68f838f12d5f2a15f51` |
| NG_v24_mac | `1e70dd6510d0b9618035a3db462b78ece06cd70f41bcccca8196c015c46a480b` |

以上为**厂商补丁包校验哈希**，不是恶意样本。

### 声称域名（新闻转述，未独立核验）

- `mckesson[.]claims` — BC 引述，称吻合 ReliaQuest `.claims` 活动形态；**未核验**。来源：https://www.bleepingcomputer.com/news/security/mckesson-discloses-breach-after-shinyhunters-claims-patient-data-theft/

### 参考 URL（情报页，非恶意基础设施）

- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://www.bleepingcomputer.com/news/security/papercut-releases-second-emergency-patch-for-exploited-flaws/
- https://thehackernews.com/2026/08/attackers-chain-two-papercut-flaws-to.html
- https://www.bleepingcomputer.com/news/security/papercut-warns-of-ng-mf-flaw-exploited-in-zero-day-attacks/
- https://thehackernews.com/2026/08/papercut-zero-day-exploited-in-attacks.html
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- https://www.bleepingcomputer.com/news/security/over-8-300-gitea-servers-vulnerable-to-code-execution-attacks/
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-078-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-25-128-03
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- https://nvd.nist.gov/vuln/detail/CVE-2026-66384
- https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- https://nvd.nist.gov/vuln/detail/CVE-2019-1068
- https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- https://support.citrix.com/external/article/CTX696604
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- https://thehackernews.com/2026/08/snowflake-github-actions-flaw-lets.html
- https://www.bleepingcomputer.com/news/security/servicenow-warns-of-three-max-severity-security-vulnerabilities/
- https://thehackernews.com/2026/08/three-cvss-100-servicenow-flaws-could.html
- https://www.bleepingcomputer.com/news/security/mckesson-discloses-breach-after-shinyhunters-claims-patient-data-theft/
- https://www.bleepingcomputer.com/news/security/givewp-wordpress-donation-plugin-flaw-lets-hackers-execute-server-commands/
- https://www.bleepingcomputer.com/news/security/toy-making-giant-hasbro-disclose-data-breach-affecting-employees/
- https://thehackernews.com/2026/08/apt28-linked-hookedge-backdoor-targets.html
- https://thehackernews.com/2026/08/china-made-zbt-routers-ship-with-two.html
- https://thehackernews.com/2026/08/critical-cpanel-flaw-could-let-one.html
- https://thehackernews.com/2026/08/two-unitree-g1-edu-humanoid-robot-flaws.html
- https://thehackernews.com/2026/08/19-chrome-and-edge-extensions-found.html
- https://thehackernews.com/2026/08/berlin-refuses-to-pay-hackers-who-stole.html
- https://thehackernews.com/2026/08/cosmos-evm-flaw-exploited-after-cosmos.html
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/LAME-Projects/stratum-c2
- https://github.com/tailscale/tailcat
- https://github.com/praetorian-inc/pius
- https://github.com/argoproj/argo-rollouts
- https://securityonline.info/adobe-commerce-vulnerability-cve-2026-71362/
- https://windowsforum.com/windows-news.4/cve-2026-36425-lets-sparkrat-disable-microsoft-defender.443771/
- https://thehackernews.com/2026/08/spark-rat-targets-cambodia-abuses.html
- https://aviatrix.com/threat-research-center/berlin-refuses-pay-hackers-stole-data-rhysida-2026/
- https://x.com/ZeroDayDevApp/status/2093477948699361494
- https://x.com/yousukezan/status/2093480974034313709
- https://x.com/BotBauR/status/2093477202088087719
- https://x.com/snypet86/status/2093459932913774809
- https://x.com/LittleJoeTables/status/2093408059326628092
- https://x.com/ThreatAtlas/status/2093489325316927669
- https://x.com/aviatrixtrc/status/2093488081496052183

## 来源搜索 URL

- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day%20OR%20%220-day%22&src=typed_query&f=live
- https://x.com/search?q=(github.com)%20(C2%20OR%20%22red%20team%22%20OR%20nuclei%20OR%20sliver%20OR%20havoc%20OR%20cobalt)&src=typed_query&f=live
- https://x.com/search?q=(APT%20OR%20%22malware%20analysis%22%20OR%20ransomware%20OR%20%22threat%20report%22%20OR%20KEV)&src=typed_query&f=live
