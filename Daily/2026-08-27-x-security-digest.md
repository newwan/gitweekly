# X 安全情报晚报 · 2026-08-27

> 搜集窗口：圣地亚哥时间 **2026-08-26 20:00 至 2026-08-27 20:10**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周四）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-08-27.json`（collected_at **2026-08-27T20:05:00-04:00**）。CISA KEV catalogVersion **2026.08.27**／**1685** 条／dateReleased **2026-08-27T17:00:36.6632Z**。**KEV 本日新增三条**（dateAdded **2026-08-27**）：**CVE-2023-49105**、**CVE-2026-53362**、**CVE-2026-66384**。ICS 本日新发 **ICSA-26-239-01..05**。
> X：文件 `/workspace/x-posts-2026-08-27.json`（**31** 条，cve 12／tool 5／apt 14；collected_at **2026-08-27T20:07:00-04:00**；**logged_in=true**／**blocked=false**）。搜索1 Latest 最旧可见约 **2026-08-27T22:54:58Z**（约 **1 小时**窗口，**不可当作完整 24h**；“exploit”噪声极大已过滤）。搜索2 最旧可见可至 **2026-08-19**（量少）。搜索3 约 1h。部分 t.co 已展开。**公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉引用。
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、请求样例或 PoC。

## 今日摘要

- **紧急 · PaperCut NG／MF 在野利用（厂商紧急公告 2026-08-27，尚无 CVE 号）**：PaperCut 确认客户事件、正在调查；影响**当前受支持的全部 NG／MF 版本**。缓解：若应用服务器暴露公网，**立即用防火墙将 Web 管理面限制为受信 IP**。紧急补丁已面向 **v25／v26** 发布（AEST **2026-08-28** 清晨更新；v24 仍在制作——以厂商公告为准）。狩猎信号（厂商／Help Net Security 转述）：`pc-app.exe` 异常后利用告警；`server.log` 缺失／截断；日志中出现 `ERROR No suitable driver found for jdbc:no:x` 或 `ERROR DatabaseUtils – Database error looking up cardID: VALUES CAST`。**不转写利用细节。** IoC：见地址／IoC 汇总（厂商狩猎信号）。https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/ https://www.helpnetsecurity.com/2026/08/27/papercut-ng-mf-vulnerability-attack/
 X：https://x.com/EsGeeks/status/2093110261037011106 https://x.com/connect24h/status/2093110112319873049

- **KEV 本日三连加**：CISA 警报 **2026-08-27** 列入三条（catalogVersion **2026.08.27**／**1685**）。**ownCloud CVE-2023-49105**（CWE-287 不当认证／预签名 URL；NVD **CVSS 9.8**；联邦期限 **2026-08-30**；补丁 **≥10.13.1**，厂商后续督促 **≥10.13.3**）＋ **Linux Kernel CVE-2026-53362**（IPv6 子系统提权／容器逃逸风险；NVD **CVSS 7.8**；期限 **2026-08-30**；按发行版内核更新并重启）＋ **JFrog Artifactory CVE-2026-66384**（CWE-22 路径限制；已认证用户在特定远程仓库条件下写出 Docker 缓存路径外；NVD **CVSS 5.3**；期限 **2026-09-10**；自管升级到 **7.146.35＋** 或 **高于 7.161.16** 的分支版本；云侧厂商称已加固）。knownRansomwareCampaignUse 均为 Unknown。狩猎：互联网暴露的 ownCloud／内核未打补丁主机／自管 Artifactory；曾暴露资产按 **BOD 26-04** 取证分诊。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/ https://nvd.nist.gov/vuln/detail/CVE-2023-49105 https://nvd.nist.gov/vuln/detail/CVE-2026-53362 https://docs.jfrog.com/releases/docs/jfrog-security-advisories https://nvd.nist.gov/vuln/detail/CVE-2026-66384
 X：https://x.com/__kokumoto/status/2093115603930464601
- **期限今日 · Oracle HTTP Server／WebLogic Proxy Plug-in CVE-2026-21962**：KEV dateAdded **2026-08-24**；联邦缓解期限 **本日 2026-08-27**。CWE-284；未认证 HTTP；CVSS 10.0。补丁：**2026 年 1 月 CPU**。本日无厂商重写。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-21962 https://www.oracle.com/security-alerts/cpujan2026.html https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- **期限明日 · Gitea CVE-2026-60004**：KEV dateAdded **2026-08-25**；联邦缓解期限 **2026-08-28**。补丁 **1.27.1**／GHSA-rcr6-4jqh-j84m。本日无新的厂商／KEV 重写。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- **期限后天 · Citrix NetScaler CVE-2026-8452 ＋ SQL Server CVE-2019-1068**：均为昨日六连加；联邦期限 **2026-08-29**。Citrix 补丁 **14.1-72.61＋／13.1-63.18＋**（及对应 FIPS）；SQL Server 按 MSRC。BC 今日续报督促联邦周六前打 NetScaler。IoC：未见公开 IoC。https://support.citrix.com/external/article/CTX696604 https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068 https://www.bleepingcomputer.com/news/security/cisa-hackers-now-exploiting-citrix-netscaler-rce-flaw-in-attacks/ https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- **本窗口新报 · ICS ICSA-26-239-01..05（均 2026-08-27）**：Xiiaozet LK100W、All-Line Fuel-Boss、Rockwell OTTO Fleet Manager、ASE ASE2000 V2、Ebyte NA111-M。按各公告隔离／升级。IoC：未见公开 IoC。https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-01 https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-02 https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-03 https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-04 https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05
- **本窗口新报／续 · Next.js Windows RCE CVE-2026-75604（GHSA-p293-qw3h-jr36）**：THN **2026-08-25**；CVSS **9.0**；Pages＋App Router、无 Cache Components、**Windows 文件系统** 主机未认证 RCE；Linux／macOS 不受本条影响。补丁 **15.5.24／16.3.3**。另有 AVIF 相关修复见同次安全发布（不转载 PoC）。狩猎：盘点 Windows 托管 Next.js，立即升级。IoC：未见公开 IoC。https://nextjs.org/blog/august-2026-security-release https://github.com/vercel/next.js/security/advisories/GHSA-p293-qw3h-jr36 https://vercel.com/changelog/nextjs-august-2026-security-release https://thehackernews.com/2026/08/nextjs-patches-critical-avif-and.html
 X：https://x.com/aviatrixtrc/status/2093125706771230945 https://x.com/peaks2314/status/2093122713909100831
 文章：https://aviatrix.ai/threat-research-center/nextjs-patches-critical-avif-windows-flaws-enabling-unauthenticated-rce/
- **本窗口新报 · Kaspersky Securelist 工业威胁报告 Q2 2026**（发布 **2026-08-27**）：季度态势文，非单一新家族战役 IOC 包。IoC：未见公开 IoC。https://securelist.com/industrial-threat-report-q2-2026/121159/
- **本窗口新报 · ATF／Qilin**：BleepingComputer **2026-08-27**——ATF 确认「重大事件」后与 Qilin 勒索声称相关；称未影响企业网与 eForms。IoC：未见公开攻击者基础设施 IoC（报道层）。https://www.bleepingcomputer.com/news/security/atf-confirms-major-incident-after-recent-qilin-breach-claims/
 X：https://x.com/DevaOnBreaches/status/2093122131005743533 https://x.com/securityLab_jp/status/2093119035051511922
- **关联阅读 · OpenAI／Hugging Face 事故与 Artifactory／内核零日**：OpenAI 技术报告与 THN 将训练环境中的 Artifactory 利用与后续活动关联；NVD 引用同指向 **CVE-2026-66384** 与公开报告 PDF。防御：自管 Artifactory 按上列升级；勿把事故叙事当利用手册。IoC：未见本报可独立核验的恶意 C2／哈希清单（以厂商／OpenAI 原文为准）。https://openai.com/index/hugging-face-incident-and-the-road-ahead/ https://cdn.openai.com/pdf/67869394-cb91-4c12-888c-5cbd85c7814c/OpenAI-Hugging-Face%20Incident-Technical-Report.pdf https://thehackernews.com/2026/08/openai-says-reward-hacking-drove-ai.html
 X：https://x.com/ABabino/status/2093125655189655986 https://x.com/TweetThreatNews/status/2093122719755710931
- **工具**：nuclei-templates **仍为 v10.4.8**（**2026-08-24**）。Sliver **仍为 v1.7.3**。**本日无显著 C2 新版本。** IoC：未见公开 IoC。https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8 https://github.com/BishopFox/sliver/releases/tag/v1.7.3
- **续报／仍有效（短）**：昨日 KEV 六连加其余四条（AjaxPro／内核 CVE-2022-0995／libuser／ABRT）、SharePoint 链探测、Chrome／ChromeOS 更新、GitLab **CVE-2026-19478** 仍未入 KEV（对照 **1685**）、Zimbra／TrueConf／afd.sys 等——**仍有效，不重写昨日全文**。https://www.cisa.gov/known-exploited-vulnerabilities-catalog

## CVE / POC / 漏洞

### 0. 【紧急／在野】PaperCut NG／MF 未编号漏洞（厂商公告 2026-08-27；紧急补丁 v25／v26）

PaperCut 安全响应团队确认**活跃利用**与客户事件；调查进行中，**正式 CVE 尚未分配**（以公告为准）。影响当前受支持的 PaperCut **NG／MF 全部版本**。紧急缓解：公网可达的 Application Server Web 接口**立即限制为受信 IP**。紧急补丁：面向 **v25／v26**（Windows／Linux／macOS 安装包——以下载页为准）；v24 分支补丁仍在制作中（媒体转述）。**不转写根因或利用步骤。**

狩猎（厂商／Help Net Security 转述的信号，非完整 IoC 包）：
- 终端／IDS 上涉及 PaperCut Application Server、尤其是 `pc-app.exe` 的可疑后利用活动
- `server.log` 缺失、异常截断或被删
- 日志出现：`ERROR No suitable driver found for jdbc:no:x` 或 `ERROR DatabaseUtils – Database error looking up cardID: VALUES CAST`

地址：
- 厂商紧急公告：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- Help Net Security：https://www.helpnetsecurity.com/2026/08/27/papercut-ng-mf-vulnerability-attack/
- X：https://x.com/EsGeeks/status/2093110261037011106
- X：https://x.com/connect24h/status/2093110112319873049
- BC（Cloudflare 本轮抓取受限，URL 保留）：https://www.bleepingcomputer.com/news/security/papercut-warns-of-ng-mf-flaw-exploited-in-zero-day-attacks/

IoC：厂商狩猎信号见上（日志错误串／`pc-app.exe`）；未见独立公开的攻击者 C2 IP／域名／样本哈希清单。

### 0b. 【分析文】UniFi OS Server 未认证 RCE 链（含 CVE-2026-34910 等）· Bishop Fox

Bishop Fox 公开分析 UniFi OS Server 未认证命令执行链；相关 CVE 包括 **CVE-2026-34910**（报道／分析文称 CVSS **10.0**）以及 **CVE-2026-34908／34909／34911／22557／33000** 等（以厂商与分析文列表为准）。修补后需**轮换密钥**（补丁不驱逐已入驻攻击者）。设备线版本指引（分析文）：多数 Cloud Gateway／Dream Machine／NVR 等 **5.1.12＋**，UNAS **5.1.10＋**，Dream Machine Beast **5.1.11＋**，UniFi Express **4.0.14＋**；软件发行 **5.0.8＋**。**仅防御摘要，不转利用链。** 昨日 BC Ubiquiti 高危补丁报道可交叉阅读。

地址：
- Bishop Fox：https://bishopfox.com/blog/popping-root-on-unifi-os-server-unauthenticated-rce-chain-detection-analysis
- BC Ubiquiti 补丁综述：https://www.bleepingcomputer.com/news/security/ubiquiti-patches-three-max-severity-security-vulnerabilities/
- X：https://x.com/yeahbutnahbut/status/2093119831239213227

IoC：未见公开攻击者 IoC（分析文侧重检测／补丁）。


### 1. 【KEV 本日新增】ownCloud CVE-2023-49105（dateAdded 2026-08-27；联邦期限 2026-08-30）

X 交叉：https://x.com/__kokumoto/status/2093115603930464601

CISA 警报 **2026-08-27** 三连加之一。CWE-287。KEV／NVD：若已知受害者用户名且该用户未配置 signing-key（默认常见），预签名 URL 可在未认证情况下访问／修改／删除任意文件。NVD **CVSS 3.1 9.8 CRITICAL**。受影响：ownCloud core **10.6.0–10.13.0** 一带（NVD：before **10.13.1**）；厂商安全页督促升到 **10.13.3＋**（订阅客户或可经支持获取专项补丁）。knownRansomwareCampaignUse Unknown。**不转写请求样例、不链 PoC。**

狩猎：盘点互联网暴露的 ownCloud Server；立即升级；曾暴露主机按 **BOD 26-04** 取证分诊。

地址：
- CISA 警报（2026-08-27，新增三条）：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- KEV JSON 源：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- 厂商公告（WebDAV 预签名）：https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- ownCloud 安全汇总：https://owncloud.org/security
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- CVE.org：https://www.cve.org/CVERecord?id=CVE-2023-49105
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 2. 【KEV 本日新增】Linux Kernel CVE-2026-53362（dateAdded 2026-08-27；联邦期限 2026-08-30）

CISA 三连加之一。KEV：经 IPv6 网络子系统的未充分说明漏洞，可导致提权；可影响 Suse、Red Hat 及其他采用该内核路径的产品。NVD **CVSS 3.1 7.8 HIGH**（本地／已认证用户向量）；描述指向 IPv6 分片／`__ip6_append_data` 相关修复提交。稳定树修复提交见 KEV notes／NVD references。Red Hat 等发行版另有安全公告（如 RHSB-2026-009／GHSA-3x6f-vm7x-cgm7——以发行版页面为准）。knownRansomwareCampaignUse Unknown。**仅高阶，不写利用原语。**

狩猎：按发行商内核安全更新安装并**重启**；盘点容器宿主与开启用户命名空间的主机；曾暴露／多租户主机按 BOD 26-04 分诊。

地址：
- CISA 警报（2026-08-27）：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- CVE.org：https://www.cve.org/CVERecord?id=CVE-2026-53362
- 示例稳定树提交（修补参考，非利用）：https://git.kernel.org/stable/c/14200d435af9a9eeb444f529fc2f689a236b7962
- Red Hat：https://access.redhat.com/security/vulnerabilities/RHSB-2026-009
- GHSA：https://github.com/advisories/GHSA-3x6f-vm7x-cgm7
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 3. 【KEV 本日新增】JFrog Artifactory CVE-2026-66384（dateAdded 2026-08-27；联邦期限 2026-09-10）

CISA 三连加之一。CWE-22。KEV／厂商：已认证用户在特定远程仓库条件下，可能向 Docker 缓存预期路径外写入数据。NVD **CVSS 3.1 5.3 MEDIUM**。JFrog 安全公告表：受影响 **&lt;7.146.35** 以及 **7.161.0–7.161.16**；自管请升到 **7.146.35＋** 或 **7.161.17＋**（勿停在仍列受影响的 7.161.16）。云环境：厂商称已加固。knownRansomwareCampaignUse Unknown。OpenAI Hugging Face 事故公开材料亦引用本 CVE——作关联阅读，不转利用细节。

狩猎：盘点自管 Artifactory；限制可配置 Docker 远程仓库的角色；升级后复查异常写入／仓库配置变更。

地址：
- CISA 警报（2026-08-27）：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- JFrog Security Advisories：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- Artifactory Self-Managed Releases：https://docs.jfrog.com/releases/docs/artifactory-self-managed-releases
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-66384
- CVE.org：https://www.cve.org/CVERecord?id=CVE-2026-66384
- OpenAI 事故说明：https://openai.com/index/hugging-face-incident-and-the-road-ahead/
- OpenAI 技术报告 PDF：https://cdn.openai.com/pdf/67869394-cb91-4c12-888c-5cbd85c7814c/OpenAI-Hugging-Face%20Incident-Technical-Report.pdf

IoC：未见公开 IoC。

### 4. 【期限今日】Oracle HTTP Server／WebLogic Server Proxy Plug-in CVE-2026-21962（dateAdded 2026-08-24；联邦期限 2026-08-27）

续报。CWE-284；未认证 HTTP；CVSS 10.0。补丁：**2026 年 1 月 CPU**。本日无新的厂商／KEV 重写。狩猎：确认已应用 Jan 2026 CPU；互联网暴露的 OHS／Proxy Plug-in 按 BOD 26-04 分诊。

地址：
- CISA 警报（2026-08-24）：https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- Oracle CPU：https://www.oracle.com/security-alerts/cpujan2026.html
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 5. 【期限明日】Gitea CVE-2026-60004（dateAdded 2026-08-25；联邦期限 2026-08-28）

续报。仓库写权限攻击者可经 diffpatch API 植入 Git hook。补丁 **1.27.1**。本日无新重写。

地址：
- CISA 警报（2026-08-25）：https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- GHSA：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- 发布：https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-60004

IoC：未见公开 IoC。

### 6. 【期限 08-29】Citrix NetScaler ADC／Gateway CVE-2026-8452 ＋ Microsoft SQL Server CVE-2019-1068

昨日六连加之两条；联邦期限均为 **2026-08-29**。Citrix：Gateway／AAA 前提下内存问题可致 DoS 等；补丁 **14.1-72.61＋／13.1-63.18＋**（及 FIPS 对应）。SQL Server：按 MSRC 以 Database Engine 服务账户上下文 RCE 风险处置。BC **2026-08-27** 续报敦促联邦周六前完成 NetScaler。**不转写利用细节。**

地址：
- CISA 警报（2026-08-26，六条）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- Citrix CTX696604：https://support.citrix.com/external/article/CTX696604
- MSRC CVE-2019-1068：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- NVD Citrix：https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- NVD SQL Server：https://nvd.nist.gov/vuln/detail/CVE-2019-1068
- BC 续报：https://www.bleepingcomputer.com/news/security/cisa-hackers-now-exploiting-citrix-netscaler-rce-flaw-in-attacks/

IoC：未见公开 IoC。

### 7. 【本窗口】Next.js CVE-2026-75604（Windows 路径／RCE；GHSA-p293-qw3h-jr36）

THN **2026-08-25**；官方 August 2026 Security Release。Windows 托管、同时使用 Pages Router 与 App Router 且未启用 Cache Components 时可致未认证 RCE；**Linux／macOS 不受本条影响**。补丁：**15.5.24**（Maintenance LTS）、**16.3.3**（Active LTS）。同次发布亦覆盖 AVIF 相关问题（见 Vercel／Next 说明）。**不转载 PoC。**

地址：
- Next.js 安全发布：https://nextjs.org/blog/august-2026-security-release
- GHSA：https://github.com/vercel/next.js/security/advisories/GHSA-p293-qw3h-jr36
- Vercel Changelog：https://vercel.com/changelog/nextjs-august-2026-security-release
- THN：https://thehackernews.com/2026/08/nextjs-patches-critical-avif-and.html

IoC：未见公开 IoC。

### 8. 【本窗口】CISA ICS 公告 ICSA-26-239-01..05（2026-08-27）

五份 ICS 公告同日发布（相对昨日 ICSA-26-237 系列为新批次）：

1. **ICSA-26-239-01** Xiiaozet LK100W — OS 命令注入／缺认证等；CVSS v3 **9.8**；https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-01
2. **ICSA-26-239-02** All-Line Fuel-Boss — 参数注入／缓冲区问题；https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-02
3. **ICSA-26-239-03** Rockwell OTTO Fleet Manager — 弱密码哈希等（公告提及 CVE-2026-75112）；升 **2.36.3**；https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-03
4. **ICSA-26-239-04** ASE ASE2000 V2 — XXE／证书校验；升 **2.38＋**；https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-04
5. **ICSA-26-239-05** Ebyte NA111-M — 缺认证／CSRF 等；https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05

狩猎：OT／ICS 资产盘点；能升级则升级；否则网络隔离与访问控制。不转写利用步骤。

IoC：未见公开 IoC。

### 9. 【续报短】昨日六连加其余四条仍有效

Ajax.NET Professional **CVE-2021-23758**、Linux Kernel **CVE-2022-0995**、libuser **CVE-2015-3246**、ABRT **CVE-2015-5287**（联邦期限多为 **2026-09-09**）。详见昨日晚报与 CISA 08-26 警报。https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

## 工具与 GitHub 发布

### 1. nuclei-templates 仍为 v10.4.8

发布页核验最新 tag **v10.4.8**（datetime **2026-08-24T13:01:50Z**）。相对昨日无新版本。https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8 https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。

### 2. Sliver 仍为 v1.7.3

**v1.7.3**（**2026-02-24**）。本日无显著 C2 新版本。https://github.com/BishopFox/sliver/releases/tag/v1.7.3 https://github.com/BishopFox/sliver/releases

IoC：未见公开 IoC。

### 3. Havoc

GitHub Releases API／页面本轮未见可用新正式 release 标签可报。https://github.com/HavocFramework/Havoc/releases

IoC：未见公开 IoC。

**主流 C2／nuclei 模板：本日无显著新版本。** 另见 X 提及的若干 GitHub 项目（下）。

### 4. X 窗口内提及的 GitHub 工具（防御向知晓；非 endorsements）

- stratum-c2（云存储 dead-drop 通信通道类 C2 框架，知晓面）：https://github.com/LAME-Projects/stratum-c2
  X：https://x.com/ipurple/status/2092997876334956860
- CS-EDR-Enumeration（Cobalt Strike 社区扩展，EDR／遥测枚举）：https://github.com/mohamedanas069/CS-EDR-Enumeration
  X：https://x.com/rustyLAKEX/status/2092909242978345402
- tailscale/tailcat：https://github.com/tailscale/tailcat
  X：https://x.com/mcohmi/status/2092826156089119163
- AI/LLM red team handbook：https://github.com/Shiva108/ai-llm-red-team-handbook
  X：https://x.com/_thegb_/status/2092765030714409317

IoC：未见公开 IoC。狩猎：在授权红队与威胁狩猎中识别同类工具指纹；禁止未授权使用。



## APT / Malware 分析

### 1. Kaspersky Securelist · Industrial threat report Q2 2026（2026-08-27）

工业／ICS 方向季度威胁报告（文章，非单次战役 IoC dump）。用于态势与狩猎优先级，不替代厂商/ICS 公告补丁动作。

地址：
- 文章：https://securelist.com/industrial-threat-report-q2-2026/121159/

IoC：未见公开 IoC（报告层未在本报逐条抄录样本哈希）。

### 2. ATF 确认重大事件（Qilin 相关声称）· BleepingComputer 2026-08-27

ATF 确认独立系统「重大事件」；称企业网与 eForms 未受影响；已隔离并与司法部协作。防御：关注联邦与相关组织对 Qilin 的告警，做好备份与隔离演练。

地址：
- https://www.bleepingcomputer.com/news/security/atf-confirms-major-incident-after-recent-qilin-breach-claims/

IoC：未见公开攻击者 IoC。

### 3. OpenAI Hugging Face 事故公开说明（关联 Artifactory／训练环境）

OpenAI 公开事故页与技术报告 PDF；NVD／报道侧与 **CVE-2026-66384** 等关联。防御动作落在 Artifactory／内核补丁与供应链仓库加固，不转载利用链。

地址：
- https://openai.com/index/hugging-face-incident-and-the-road-ahead/
- https://cdn.openai.com/pdf/67869394-cb91-4c12-888c-5cbd85c7814c/OpenAI-Hugging-Face%20Incident-Technical-Report.pdf
- https://thehackernews.com/2026/08/openai-says-reward-hacking-drove-ai.html

IoC：未见本报可独立核验的 C2／样本哈希清单。


### 5. FBI · TeamPCP 供应链相关起诉（X 官方账号）

FBI San Francisco：澳大利亚男子 Ruben Ian Thomson（21）因涉嫌参与针对软件供应链的 “TeamPCP” 网络攻击被起诉。防御：关注供应链软件完整性与可信构建链路。

地址：
- X：https://x.com/FBISanFrancisco/status/2093126214709854550
- 相关 THN（较早）：https://thehackernews.com/2026/08/alleged-teampcp-hackers-charged-in.html

IoC：未见本帖公开 IoC。

### 4. 其他窗口内公开报道（日期略早／续）

- SharePoint 链探测（BC **2026-08-26**）：https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-sharepoint-rce-chain-with-poc-exploit/
- Ubiquiti 高危补丁（BC **2026-08-26**）：https://www.bleepingcomputer.com/news/security/ubiquiti-patches-three-max-severity-security-vulnerabilities/
- 昨日 Securelist 漏洞季度文：https://securelist.com/vulnerabilities-and-exploits-in-q2-2026/121091/

本日无新的 Unit42／Mandiant／CrowdStrike 战役长文可独立核验为 08-27 首发。

## 地址／IoC 汇总

### 本日无公开恶意基础设施 IoC（C2／样本哈希）

- 除下列厂商狩猎信号外，上述各条：**未见公开攻击者 C2／样本哈希**（无在本窗口核验到可原样抄录的攻击者 C2 IP／域名／钱包／样本哈希清单）。
- 不把受害站点、Shadowserver 暴露计数或新闻标题当 IoC。


### PaperCut 厂商狩猎信号（非 C2）

- 进程／告警：`pc-app.exe`（PaperCut Application Server 相关可疑后利用）
- 日志异常：`server.log` 缺失／截断／删除
- 日志字符串：`ERROR No suitable driver found for jdbc:no:x`
- 日志字符串：`ERROR DatabaseUtils – Database error looking up cardID: VALUES CAST`
- 来源：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/ https://www.helpnetsecurity.com/2026/08/27/papercut-ng-mf-vulnerability-attack/

### 参考 URL（情报页，非恶意基础设施）

- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://www.helpnetsecurity.com/2026/08/27/papercut-ng-mf-vulnerability-attack/
- https://bishopfox.com/blog/popping-root-on-unifi-os-server-unauthenticated-rce-chain-detection-analysis
- https://aviatrix.ai/threat-research-center/nextjs-patches-critical-avif-windows-flaws-enabling-unauthenticated-rce/
- https://rocket-boys.co.jp/security-measures-lab/log4j-filter-bypass-rce-poc-no-cve/
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- https://owncloud.org/security
- https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- https://nvd.nist.gov/vuln/detail/CVE-2026-66384
- https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- https://nvd.nist.gov/vuln/detail/CVE-2019-1068
- https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- https://docs.jfrog.com/releases/docs/artifactory-self-managed-releases
- https://access.redhat.com/security/vulnerabilities/RHSB-2026-009
- https://github.com/advisories/GHSA-3x6f-vm7x-cgm7
- https://git.kernel.org/stable/c/14200d435af9a9eeb444f529fc2f689a236b7962
- https://support.citrix.com/external/article/CTX696604
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- https://www.oracle.com/security-alerts/cpujan2026.html
- https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- https://nextjs.org/blog/august-2026-security-release
- https://github.com/vercel/next.js/security/advisories/GHSA-p293-qw3h-jr36
- https://vercel.com/changelog/nextjs-august-2026-security-release
- https://thehackernews.com/2026/08/nextjs-patches-critical-avif-and.html
- https://thehackernews.com/2026/08/openai-says-reward-hacking-drove-ai.html
- https://openai.com/index/hugging-face-incident-and-the-road-ahead/
- https://cdn.openai.com/pdf/67869394-cb91-4c12-888c-5cbd85c7814c/OpenAI-Hugging-Face%20Incident-Technical-Report.pdf
- https://securelist.com/industrial-threat-report-q2-2026/121159/
- https://www.bleepingcomputer.com/news/security/atf-confirms-major-incident-after-recent-qilin-breach-claims/
- https://www.bleepingcomputer.com/news/security/cisa-hackers-now-exploiting-citrix-netscaler-rce-flaw-in-attacks/
- https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-sharepoint-rce-chain-with-poc-exploit/
- https://www.bleepingcomputer.com/news/security/ubiquiti-patches-three-max-severity-security-vulnerabilities/
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/BishopFox/sliver/releases/tag/v1.7.3
- https://www.cve.org/CVERecord?id=CVE-2023-49105
- https://www.cve.org/CVERecord?id=CVE-2026-53362
- https://www.cve.org/CVERecord?id=CVE-2026-66384

## 来源搜索 URL

- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/ics-advisories
- https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- https://nextjs.org/blog/august-2026-security-release
- https://securelist.com/industrial-threat-report-q2-2026/121159/
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=%22CVE-2026%22%20OR%20%22CVE-2023%22%20OR%20KEV%20OR%20CISA&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20APT%20OR%20%22threat%20report%22&src=typed_query&f=live
