# X 安全情报晚报 · 2026-09-01

> 搜集窗口：圣地亚哥时间 **2026-08-31 20:00 至 2026-09-01 ~20:50**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周二）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-09-01.json`（collected_at **2026-09-01T20:05:00-04:00**）。CISA KEV catalogVersion **2026.09.01**／**1687** 条／dateReleased **2026-09-01T19:22:46.2162Z**（昨日为 2026.08.31／1687）。**相对昨日：无新增 CVE**（`dateAdded=2026-09-01` 为 0；仅 catalogVersion 重盖章）。仍有效最新入目录：PaperCut **CVE-2026-82078**＋**CVE-2026-81578**（dateAdded 2026-08-31，**due 2026-09-14**）。**期限今日 09-01：无。** 期限明日 09-02：**CVE-2026-64849** MLflow SSRF。ICS：今日新 6 条 Rockwell **ICSA-26-244-01..06**。PaperCut 厂商页 Last updated **September 1, 2026**；**Emergency Patch Release 3** 于 **2026-09-01 18:22 AEST** 发布（SAML／遗留 MSSQL card-lookup 回归修复＋针对观测攻击链的硬化）；BC／SecurityWeek／Defused 报数据窃取路径升级。
> X：文件 `/workspace/x-posts-2026-09-01.json`（**210** 条，cve 62／tool 7／apt 141；含 LWiS 重合并；**logged_in=true**／账号 **@seogoogle4**；blocked=false）。搜索 A Latest 约 **2 小时 10 分**（高流量，35／477，**远不足 24h，不可当作完整日窗**）。搜索 B（github.com + C2／red team／nuclei／sliver／havoc／cobalt）约 **20h**，**4** 条工具帖，**无**「Something went wrong」软限流（相对昨日改善）。搜索 C 约 **33.5h／覆盖完整 24h+**，保留 **127**。LWiS X List 约 **25h**，534 扫中保留 **46**。**公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉。**务必注意 Search A 窗口远短于 24h。** LWiS 信源（X List 500 ＋ blogs.txt 443 ＋ Risky Business ＋ tl;dr sec）与 X Latest 交叉、不替代。
> 规则：每条含完整 https URL；分列原帖／仓库／厂商／文章；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、请求样例或 PoC。

## 今日摘要

- **【主条 · PaperCut Release 3＋KEV 续】** PaperCut NG／MF **CVE-2026-81578**／**CVE-2026-82078** 仍为最新 KEV 条目（due **2026-09-14**）。厂商 **Emergency Patch Release 3**（2026-09-01 18:22 AEST）已发布，累积 R1／R2，修复 SAML 与遗留 MSSQL card-lookup 回归并增加硬化；即便已装 R2 也应升 R3。BC／SecurityWeek／Defused：利用升级为数据窃取／动手键盘；公网未打补丁应**假定已失陷**（assume breach）。Shadowserver 提示检测 nuclei 模板 PR **#17025**（darses）。狩猎字符串未变；**新增 18 条 R3 安装包 SHA256**（见 IoC）。**不转写利用／repro。**
  厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
  文章：https://www.bleepingcomputer.com/news/security/recently-patched-papercut-zero-days-used-in-data-theft-attacks/ https://www.securityweek.com/papercut-exploitation-escalates-to-active-intrusions/
  仓库：https://github.com/projectdiscovery/nuclei-templates/pull/17025
  X：https://x.com/Shadowserver/status/2094879415100391539 https://x.com/securityLab_jp/status/2094938741551120796

- **【KEV 明日到期】** **CVE-2026-64849** MLflow SSRF，due **2026-09-02**（dateAdded 2026-08-19）。修复线索：GHSA-7gwp-5pfp-969j／PR #24258／v3.15.0。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-64849
  厂商／GHSA：https://github.com/mlflow/mlflow/security/advisories/GHSA-7gwp-5pfp-969j
  仓库：https://github.com/mlflow/mlflow/pull/24258 https://github.com/mlflow/mlflow/releases/tag/v3.15.0
  KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-64849

- **SonicWall SMA1000 CVE-2026-83548（CVSS 10 预认证 SSRF）＋ CVE-2026-83549**：媒体／NVD 引用 **SNWLID-2026-0016**；检查时渲染 PSIRT 页 **软缺失**（页面未完整公布）。立即对照厂商／NVD 与版本矩阵打补丁、限制管理面。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-83548 https://nvd.nist.gov/vuln/detail/CVE-2026-83549
  厂商（软缺失）：https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2026-0016
  文章：https://securityonline.info/sonicwall-sma1000-cve-2026-83548-ssrf/
  X：https://x.com/__kokumoto/status/2094927739908469170 https://x.com/Daily_CyberSec/status/2094910086900748319

- **JFrog Artifactory CVE-2026-82329 认证绕过，披露后遭在野利用（watchTowr／Dark Reading／THN）**：**不转写 PoC／参数细节。** 默认暴露面应立刻升级并限制访问。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82329
  厂商：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
  文章：https://aviatrix.ai/threat-research-center/jfrog-artifactory-cve-2026-82329-authentication-bypass-exploit/ https://www.darkreading.com/application-security/attackers-pounce-critical-artifactory-flaw-disclosure https://thehackernews.com/2026/09/attackers-exploit-critical-jfrog.html
  X：https://x.com/aviatrixtrc/status/2094937631767384442 https://x.com/yousukezan/status/2094927975393493098

- **Langflow CVE-2026-0768 密钥窃取活跃利用**：报导称窃取 OpenAI／AWS 环境密钥；ZDI-26-034。升级并轮换暴露密钥。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-0768
  厂商／ZDI：https://www.zerodayinitiative.com/advisories/ZDI-26-034/
  文章：https://aviatrix.ai/threat-research-center/critical-langflow-flaw-cve-2026-0768-exploited-steal-openai-aws-keys/ https://www.bleepingcomputer.com/news/security/critical-langflow-flaw-exploited-to-steal-openai-and-aws-keys/
  X：https://x.com/aviatrixtrc/status/2094939000410685881 https://x.com/yousukezan/status/2094924655324999710

- **Exchange CVE-2026-62911**：Shadowserver／BC 称约 **21,899** 台未打补丁、可被劫持邮件读写。立刻打 MSRC 补丁并缩小 OWA／ECP 暴露。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-62911
  厂商：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-62911
  文章：https://www.bleepingcomputer.com/news/security/nearly-22-000-microsoft-exchange-servers-vulnerable-to-hijack-attacks/
  X：https://x.com/connect24h/status/2094914759217057869

- **Proxmox 认证绕过 PSA-2026-00043-1／CVE-2026-51083（EOL v7／早期 v8）**：升级离开 EOL；**不转写 sed／PoC gist 细节。**
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-51083
  厂商：https://forum.proxmox.com/threads/proxmox-virtual-environment-security-advisories.149331/page-4#post-867929
  X：https://x.com/__kokumoto/status/2094926269200859377 https://x.com/nebusecurity/status/2094719919539793989

- **Sangoma Switchvox CVE-2026-9586**：Horizon3 称 honeypot 见有效利用尝试；**8.4.0.2** 修复。**不转写 SQLi／RCE 链。**
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-9586
  厂商：https://sangomakb.atlassian.net/wiki/spaces/Switchvox/pages/1802371073/Switchvox+-+Release+Notes+Version+8.4.0.2+July+14+2026
  文章：https://horizon3.ai/attack-research/disclosures/cve-2026-9586-sangoma-switchvox-rce/ https://labs.sra.io/posts/switchvox/
  X：https://x.com/Horizon3Attack/status/2094763747201929714 https://x.com/connect24h/status/2094914419902079358

- **APT／恶意软件**：GuardBreaker／**UAC-0099**（核武提示词干扰 AI 分析）；**BREEZE COMET／UNC5669**（巴西支付欺诈，Mandiant／Google）；**Mirage Kitten** NodeRabbit／PollCat（Kaspersky）；**Fire Ant** 续报（Sygnia／Cisco 等受信基础设施）；Storm-1175 GoAnywhere→Medusa；BGP Softaculous／Virtualizor 供应链；JSCeal（Check Point）；BraZetsu／Exilware（Group-IB）；QTFY（SafeBreach）；Anthropic Claude cookie／会话窃取追踪。
  例：https://thehackernews.com/2026/09/russia-aligned-uac-0099-plants-nuclear.html https://cloud.google.com/blog/topics/threat-intelligence/financially-motivated-threat-actor-breeze-comet-targets-brazil/ https://securelist.com/mirage-kitten-new-backdoors-noderabbit-pollcat/121244/ https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/

- **ICS／工具**：Rockwell 六条 **ICSA-26-244-01..06**（2026-09-01）。Sliver **仍 v1.7.6**、nuclei-templates **仍 v10.4.8**；另见 Strix、Stifle、PingCastle、nuclei PR #17025、SnappyClient ClickFix 分析（无静态 C2）。
  ICS：https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-01
  仓库：https://github.com/BishopFox/sliver/releases/tag/v1.7.6 https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8 https://github.com/usestrix/strix https://github.com/logangoins/Stifle https://github.com/netwrix/pingcastle

- **AMOS IoC（LWiS @Wietze）**：brewmacosterm[.]com／satinmaple4[.]com／flint-32[.]com（见 IoC 汇总）。
  X：https://x.com/Wietze/status/2094766933216264545

- **勒索／暗网声称（未核验）**：Rhysida、Akira、Global Secret Group、SilentRansomGroup、BravoX、Wallstreet、RansomHouse、MAJINAHANASHI、Black X、MedusaLocker、Qilin、The Gentlemen→Glassdoor（未确认）等——**均为声称**。
  例：https://x.com/FalconFeedsio/status/2094875311209086997 https://x.com/ThreatAtlas/status/2094929457702113453

## CVE / POC / 漏洞

### 1. 【KEV 续／Release 3】PaperCut NG／MF CVE-2026-81578 ＋ CVE-2026-82078（due 2026-09-14）

相对昨日：KEV 条目未变（仍 dateAdded 2026-08-31）。厂商 **Emergency Patch Release 3** 于 **01 Sep 2026, 6:22pm (AEST)** 发布，取代 Release 2；修复 SAML 与遗留 MSSQL card-lookup 回归，并针对观测到的攻击链增加硬化。公告 Last updated **September 1, 2026**。BC：Defused 蜜罐见 Derby 路径数据倾倒；SecurityWeek：从侦察升级为入侵；watchTowr 口径——公网未打补丁应假定失陷，仅打补丁可能锁住新攻击者但已有访问仍在。Shadowserver：假定入侵＋nuclei PR #17025。公网 Application Server：**立刻**限制受信 IP 并升 R3。**本报不转写根因、请求样例、Metasploit／Claude n-day 文章中的 repro。**

地址：
- 厂商紧急公告：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- Behind the scenes：https://www.papercut.com/blog/news/behind-the-scenes-august-security-incident/
- CISA 08-31 警报：https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-81578
- 另：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-82078
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-81578 https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- 文章：https://www.bleepingcomputer.com/news/security/recently-patched-papercut-zero-days-used-in-data-theft-attacks/
- 文章：https://www.securityweek.com/papercut-exploitation-escalates-to-active-intrusions/
- Qualys：https://threatprotect.qualys.com/2026/08/31/papercut-ng-mf-zero-day-vulnerability-exploited-in-the-attacks-cve-2026-82078-cve-2026-81578/
- Huntress：https://huntress.com/blog/papercut-actively-exploited
- 仓库：https://github.com/projectdiscovery/nuclei-templates/pull/17025
- X：https://x.com/Shadowserver/status/2094879415100391539
- X：https://x.com/Shadowserver/status/2094874800665636868
- X：https://x.com/securityLab_jp/status/2094938741551120796
- X：https://x.com/RedLegg/status/2094906834230358268

IoC：狩猎字符串与昨日相同＋**全部 18 条 Release 3 SHA256**，见「地址／IoC 汇总」。

### 2. 【KEV 明日到期】MLflow CVE-2026-64849 SSRF（due 2026-09-02）

CISA KEV dateAdded 2026-08-19；联邦期限明日。升级至含修复版本（厂商／社区指向 v3.15.0 一带），并限制 MLflow 跟踪服务出网与暴露面。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-64849
- GHSA：https://github.com/mlflow/mlflow/security/advisories/GHSA-7gwp-5pfp-969j
- 仓库：https://github.com/mlflow/mlflow/pull/24258 https://github.com/mlflow/mlflow/issues/24179 https://github.com/mlflow/mlflow/releases/tag/v3.15.0
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-64849

IoC：未见公开攻击者 C2／样本哈希。

### 3. 【本窗口高信号／尚未入 KEV】SonicWall SMA1000 CVE-2026-83548／83549（SNWLID-2026-0016）

CVE-2026-83548：预认证 SSRF，媒体称 CVSS **10.0**。CVE-2026-83549：认证后命令注入（同公告簇）。NVD 可查；**渲染 PSIRT 页检查时软缺失**——以 NVD／媒体摘要＋厂商一旦发布的矩阵为准，勿依赖软 404 页。限制 SMA 管理面、打厂商补丁。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-83548 https://nvd.nist.gov/vuln/detail/CVE-2026-83549
- 厂商：https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2026-0016
- 文章：https://securityonline.info/sonicwall-sma1000-cve-2026-83548-ssrf/
- X：https://x.com/__kokumoto/status/2094927739908469170
- X：https://x.com/ridvanyagli/status/2094935740572418225
- X：https://x.com/Daily_CyberSec/status/2094910086900748319
- X：https://x.com/ThreatWire_/status/2094911309666029788

IoC：未见公开 IoC。

### 4. 【本窗口／在野】JFrog Artifactory CVE-2026-82329 认证绕过

披露后数日即见在野；报导称默认可铸管理员令牌。与已在 KEV、due 09-10 的路径穿越 **CVE-2026-66384** 不是同一条。**严禁转写 PoC／Docker lab／URL 参数细节**（LWiS 上可见相关帖，本报只记谁／补丁）。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82329
- 厂商：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- 发行说明索引：https://docs.jfrog.com/releases/docs/artifactory-self-managed-releases
- 文章：https://aviatrix.ai/threat-research-center/jfrog-artifactory-cve-2026-82329-authentication-bypass-exploit/
- 文章：https://www.darkreading.com/application-security/attackers-pounce-critical-artifactory-flaw-disclosure
- 文章：https://thehackernews.com/2026/09/attackers-exploit-critical-jfrog.html
- 文章：https://www.techechelon.com/post/attackers-exploit-critical-jfrog-artifactory-authentication-bypass-flaw-within-hours-of-disclosure
- X：https://x.com/aviatrixtrc/status/2094937631767384442
- X：https://x.com/yousukezan/status/2094927975393493098
- X：https://x.com/Tech_Echelon/status/2094923653636882910

IoC：未见公开 IoC。

### 5. 【本窗口／在野】Langflow CVE-2026-0768 密钥窃取

ZDI-26-034；报导活跃利用窃取 OpenAI／AWS 环境变量密钥。升级 Langflow、轮换密钥、限制公网。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-0768
- ZDI：https://www.zerodayinitiative.com/advisories/ZDI-26-034/
- 文章：https://aviatrix.ai/threat-research-center/critical-langflow-flaw-cve-2026-0768-exploited-steal-openai-aws-keys/
- 文章：https://www.bleepingcomputer.com/news/security/critical-langflow-flaw-exploited-to-steal-openai-and-aws-keys/
- 文章：https://www.darkreading.com/vulnerabilities-threats/critical-langflow-flaw-exploited-attacks-rise
- X：https://x.com/aviatrixtrc/status/2094939000410685881
- X：https://x.com/yousukezan/status/2094924655324999710
- X：https://x.com/Dinosn/status/2094849688465764748

IoC：未见公开攻击者 C2／样本哈希（轮换环境密钥本身是缓解）。

### 6. 【本窗口】Microsoft Exchange CVE-2026-62911（约 21899 未打补丁）

Shadowserver／BC：约 21,899 台仍易受劫持（低权限可读写邮件／附件等，以 MSRC 描述为准）。立刻打补丁并收缩暴露面。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-62911
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-62911
- 文章：https://www.bleepingcomputer.com/news/security/nearly-22-000-microsoft-exchange-servers-vulnerable-to-hijack-attacks/
- X：https://x.com/connect24h/status/2094914759217057869
- X：https://x.com/Dinosn/status/2094773242707800506
- X：https://x.com/threatcluster/status/2094908721142862103

IoC：未见公开 IoC。

### 7. 【本窗口】Proxmox VE CVE-2026-51083／PSA-2026-00043-1 认证绕过

影响 EOL v7 与早期 v8；认证绕过（含 root）。缓解＝升级离开受影响版本。LWiS／X 流传 gist／sed——**本报不转载。**

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-51083
- 厂商：https://forum.proxmox.com/threads/proxmox-virtual-environment-security-advisories.149331/page-4#post-867929
- X：https://x.com/__kokumoto/status/2094926269200859377
- X：https://x.com/VistemSolutions/status/2094925816555548968
- X：https://x.com/nebusecurity/status/2094719919539793989
- X：https://x.com/Dinosn/status/2094753171931304246

IoC：未见公开 IoC。

### 8. 【本窗口】Apache CloudStack CVE-2026-50112

认证用户（默认 User 角色）经公开 API 影响其他租户虚拟机；修复 **4.20.3.1／4.22.1.1**。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-50112
- 厂商：https://cloudstack.apache.org/blog/security-release-advisory-4.20.3.1-4.22.1.1/
- 邮件列表：https://lists.apache.org/thread/g6cwddtjrwbh1d56wjz4cfp3fzfm4kbc
- X：https://x.com/MalwareBibleJP/status/2094931315460280733

IoC：未见公开 IoC。

### 9. 【LWiS／Reserved 注意】GeoNetwork 预认证 RCE 簇（CVE-2026-63219 等）

Ethiack 研究称 formatter 上传＋不安全 XSLT→RCE，并称政府系约 121 环境、均已修。**CVE-2026-63219 在 NVD 为 Reserved／API 无结果**——以研究页为准，待官方编号落地后再入库跟踪。

地址：
- 研究：https://ethiack.com/info-hub/research/geonetwork-preauth-RCE
- NVD（Reserved／待核）：https://nvd.nist.gov/vuln/detail/CVE-2026-63219
- X：https://x.com/connect24h/status/2094914671056961774
- X：https://x.com/Dinosn/status/2094734478602080548

IoC：未见公开 IoC。

### 10. 【本窗口／蜜罐】Sangoma Switchvox CVE-2026-9586

Horizon3：2026-08-30 多传感器蜜罐见有效利用尝试；修复 **8.4.0.2**。**不转写 SQLi→TO PROGRAM 细节。**

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-9586
- 厂商发行说明：https://sangomakb.atlassian.net/wiki/spaces/Switchvox/pages/1802371073/Switchvox+-+Release+Notes+Version+8.4.0.2+July+14+2026
- Horizon3：https://horizon3.ai/attack-research/disclosures/cve-2026-9586-sangoma-switchvox-rce/
- SRA labs：https://labs.sra.io/posts/switchvox/
- X：https://x.com/Horizon3Attack/status/2094763747201929714
- X：https://x.com/connect24h/status/2094914419902079358

IoC：未见公开攻击者 C2／样本哈希。

### 11. 【本窗口】HPE Fabric Composer CVE-2026-76657 等

媒体称含 RCE，建议升 **7.4.0**。NVD 引 hpesbnw05133en_us；匿名抓取遇认证墙——以 securityonline 摘要＋厂商文档（登录后）为准。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-76657
- 厂商：https://support.hpe.com/hpesc/public/docDisplay?docId=hpesbnw05133en_us&docLocale=en_US
- 文章：https://securityonline.info/hpe-fabric-composer-vulnerabilities/
- X：https://x.com/Daily_CyberSec/status/2094935824509161891

IoC：未见公开 IoC。

### 12. 【本窗口】Gravity Forms CVE-2026-19513；WPLP Cookie Consent CVE-2026-75865

Gravity Forms：未认证任意文件上传，影响至 **3.0.2**（X 称 CVSS 8.1；NGINX 场景可致 RCE——以 Wordfence／厂商为准）。WPLP／GDPR Cookie Consent：未认证 logo 上传 RCE，CVE-2026-75865，≤4.4.1，补丁 **4.4.2**；Patchstack 称已在利用。

地址：
- NVD Gravity：https://nvd.nist.gov/vuln/detail/CVE-2026-19513
- 厂商：https://docs.gravityforms.com/gravityforms-change-log/
- Wordfence：https://www.wordfence.com/threat-intel/vulnerabilities/id/d20b2d00-054e-4772-a5a5-b7b33063043c?source=cve
- X：https://x.com/DFIR_Radar/status/2094908730374848514
- NVD WPLP：https://nvd.nist.gov/vuln/detail/CVE-2026-75865
- 变更集：https://plugins.trac.wordpress.org/changeset/3674117/gdpr-cookie-consent
- Wordfence：https://www.wordfence.com/threat-intel/vulnerabilities/id/96a2a552-e73f-4b27-88de-50eb63a8d131?source=cve
- X：https://x.com/WPSecurityNinja/status/2094908439893848456

IoC：未见公开 IoC。

### 13. 【说明／勿混淆】CVE-2026-60004＝Gitea GHSA（NVD／KEV），非 research-lab 树

NVD／KEV 将该 ID 映射为 **Gitea** GHSA-rcr6-4jqh-j84m。Search A 展开到 `MangelZabalaDevelop/autonomous-research-lab/.../CVE-2026-60004` 属冲突／未核验研究仓叙事——**不是厂商公告**。以 Gitea advisory／1.27.1 为准。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- 厂商 GHSA：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- 发行：https://blog.gitea.com/release-of-1.27.1/
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-60004
- （冲突仓，仅作溯源）https://github.com/MangelZabalaDevelop/autonomous-research-lab/tree/main/CVE-2026-60004
- X：https://x.com/0x00Sector/status/2094932072838152286

IoC：未见本轮新公开 IoC。

### 14. 【LWiS 弱信号】Windows HTTP.sys CVE-2026-62735；WatchGuard 关键补丁；macOS CVE-2026-65400 营销帖

CVE-2026-62735：LWiS @Dinosn 链到 HackMD 笔记——**本报不核验 NVD／MSRC 状态**，仅作观察线索，待厂商页确认后再升格。WatchGuard：SecurityWeek「Patches Critical Vulnerabilities」综述帖，**本轮未解析到具体 CVE 编号**——跟厂商公告。macOS **CVE-2026-65400**（@kapualabs）表述像营销页——**弱信号，略记不展开**。

地址：
- HackMD（62735 线索）：https://hackmd.io/@nhh/Hy6Oem7_Me
- X：https://x.com/Dinosn/status/2094746673385758946
- WatchGuard 文章：https://www.securityweek.com/watchguard-patches-critical-vulnerabilities/
- X：https://x.com/Dinosn/status/2094722032306897028
- macOS 弱信号：https://x.com/kapualabs/status/2094930357904716083

IoC：未见公开 IoC。

### 15. 【其他／OPSWAT】CVE-2026-36425

X／希腊语文称邮件诱饵投递 Spark RAT，经 OPSWAT 驱动滥用结束安全软件。NVD 有条目；厂商页非编号 PSIRT。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-36425
- 厂商产品页：https://www.opswat.com/products/oesis-framework/application-removal
- X：https://x.com/hacksgreece/status/2094911563597496345

IoC：未见本报可核验的公开哈希表（NVD 另有 VT／GitHub 引用，未在本轮全文抄录）。

## 工具与 GitHub 发布

### 1. Sliver／nuclei-templates（无新 tag）

公开备援：Sliver **仍 v1.7.6**（2026-08-28）；nuclei-templates **仍 v10.4.8**（2026-08-24）。

地址：
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

### 2. nuclei PR #17025（PaperCut CVE-2026-81578，darses）

Shadowserver 推检测模板；**本报不转写模板匹配细节**。

地址：
- 仓库：https://github.com/projectdiscovery/nuclei-templates/pull/17025
- X：https://x.com/Shadowserver/status/2094879415100391539
- 交叉：https://huntress.com/blog/papercut-actively-exploited

IoC：见 PaperCut 狩猎字符串／R3 SHA256。

### 3. Strix（usestrix/strix）

开源 AI 渗透测试代理。防御团队可用于授权测试面；**不转写 exploit 工作流。**

地址：
- 仓库：https://github.com/usestrix/strix
- X：https://x.com/SagarXploit/status/2094589922175012992

IoC：未见公开 IoC。

### 4. Stifle（logangoins/Stifle）

.NET 后渗透工具：用传入证书在目标对象设显式证书映射（ESC14 相关）。防御：审计证书映射／AD CS。

地址：
- 仓库：https://github.com/logangoins/Stifle
- X：https://x.com/sekurlsa_pw/status/2094844852647186924

IoC：未见公开 IoC。

### 5. PingCastle

@DebugPrivilege 推荐 AD 防御起步工具。

地址：
- 仓库：https://github.com/netwrix/pingcastle
- X：https://x.com/DebugPrivilege/status/2094871455280312788

IoC：未见公开 IoC。

### 6. SnappyClient ClickFix PDF 分析（douglasmun）

伪 Cloudflare 诱饵→SnappyClient RAT；作者称 **C2 无法静态还原**（每主机派生 ChaCha 密钥）。

地址：
- 报告 PDF：https://github.com/douglasmun/Douglas-Guidebook/blob/main/ClickFix%20Chain%20Fake%20Cloudflare%20Lure%20to%20SnappyClient%20RAT.pdf
- X：https://x.com/douglasmun/status/2094642230363603375

IoC：帖内未见直接列出；见 PDF（本报不抄未核验表）。未见公开静态 C2。

## APT / Malware 分析

### 1. GuardBreaker／UAC-0099（俄系对齐，对乌）

在恶意 VBS 中植入「核武器」安全敏感提示词，干扰 AI／LLM 辅助恶意软件分析；MATCHBOIL 加载器投递后续载荷（X 综述）。

地址：
- 文章：https://thehackernews.com/2026/09/russia-aligned-uac-0099-plants-nuclear.html
- X：https://x.com/Dinosn/status/2094721631096594693
- X：https://x.com/threatcluster/status/2094833225738629270
- X：https://x.com/XQOPTRX/status/2094737824566087921
- X：https://x.com/ICPLEGEND1966/status/2094821315228156193

IoC：未见本轮公开 C2／样本哈希表。

### 2. BREEZE COMET／UNC5669（Mandiant／Google，巴西金融欺诈）

入侵银行／支付基础设施，操纵 PIX／STR／Boleto；口令喷洒、声钓鱼、内部人员招募；使用 COBALTSPIN 与特权账户；亦用生成式 AI 辅助。

地址：
- 厂商／IR：https://cloud.google.com/blog/topics/threat-intelligence/financially-motivated-threat-actor-breeze-comet-targets-brazil/
- X：https://x.com/Dinosn/status/2094649901472702953
- X：https://x.com/TweetThreatNews/status/2094893163861205202
- X：https://x.com/XQOPTRX/status/2094878926019625298
- X：https://x.com/autumn_good_35/status/2094661255013535924
- X：https://x.com/Daily_CyberSec/status/2094643215509139537

IoC：未见本报可抄录的公开哈希／C2 表（以 Google 原文附录为准，若有）。

### 3. Mirage Kitten — NodeRabbit／PollCat（Kaspersky）

LinkedIn 伪技术招聘／恶意编程题；新后门覆盖 Windows／macOS／Linux；亦见「Nimbus Manticore」同手法转述。

地址：
- 文章：https://securelist.com/mirage-kitten-new-backdoors-noderabbit-pollcat/121244/
- X：https://x.com/Dinosn/status/2094691567395016993
- X：https://x.com/XQOPTRX/status/2094741266730725882
- X：https://x.com/dailytechonx/status/2094780585277366365

IoC：以 Securelist 原文 IoC 表为准；本报未全文抄录——**未见另附独立公开表**。

### 4. Fire Ant 续报（中国背景，Sygnia）

从 VMware 虚拟化扩展到路由器、TACACS、Linux 管理机（相对昨日晚报续）。

地址：
- 厂商／IR：https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
- 新闻稿：https://www.sygnia.co/press-release/sygnia-reveals-new-activity-by-china-nexus-threat-actor-fire-ant-targeting-trusted-infrastructure/
- X：https://x.com/techintelpro/status/2094490262559228273
- X：https://x.com/AbubakarMundir/status/2094458918550352210

IoC：延续昨日 Sygnia 表（本报昨日已抄）；本轮无新抄录增量则见昨日汇总。

### 5. Storm-1175（GoAnywhere → Medusa）；Storm-2755（加国 AiTM）

Storm-1175：微软归因利用 Fortra GoAnywhere 关键漏洞部署 Medusa。Storm-2755：针对加拿大用户的 M365 AiTM 钓鱼改薪资账户。本轮主要见 X 转述，**未见本报可核验的微软博文完整 URL**——记 X 线索。

地址：
- X Storm-1175：https://x.com/pedri77/status/2094682351557091444
- X Storm-2755：https://x.com/riskawareco/status/2094488174328172581

IoC：未见公开 IoC。

### 6. BGP Softaculous／Virtualizor 供应链（2026-08-28..30）

BGP 劫持投递恶意 Virtualizor 更新。

地址：
- X：https://x.com/DailyDarkWeb/status/2094897281405530112

IoC：未见公开 IoC。

### 7. JSCeal（Check Point Research）

静态还原编译型 V8 字节码，23／23 payload 可分析；窃取器可拦截 HTTPS。

地址：
- X：https://x.com/XQOPTRX/status/2094518632692724050
- X：https://x.com/bamitav/status/2094437776364028289

IoC：未见本报抄录的公开哈希表。

### 8. BraZetsu／Exilware（Group-IB）

模块化 Python Windows 框架，高置信归于巴西行为体 Exilware；初始访问工具，非常规信息窃取器。

地址：
- X：https://x.com/GroupIB/status/2094675981042901312
- X：https://x.com/GroupIB_TI/status/2094672306371273053

IoC：未见公开 IoC（Group-IB 全文未在本轮展开）。

### 9. QTFY（SafeBreach，2026-08-31）

「The Scan Factory」报告：中国关联 QTFY「闯入即生意」。

地址：
- X：https://x.com/rst_cloud/status/2094632977409998892

IoC：未见公开 IoC。

### 10. Anthropic Claude 会话／cookie 滥用

威胁行为体用信息窃取器收集会话信息访问 Claude 账户；Anthropic 追踪中。另有官方网络安全评估事件调查页（Search A 交叉）。

地址：
- X：https://x.com/M_Miho_JPN/status/2094810515201781988
- X：https://x.com/christinayiotis/status/2094918226303910162
- 官方：https://www.anthropic.com/news/investigating-incidents-cybersecurity-evals

IoC：未见公开 IoC。

### 11. 勒索／暗网声称（未核验）

窗口内大量声称：Rhysida→匈牙利 szpi.hu；Akira→Congressional Iron Works／BYK；Global Secret Group→Quality Resource；SilentRansom／Leakeddata→Holland & Knight；BravoX→SCHMIDT；Wallstreet→TES；RansomHouse→REXT；MAJINAHANASHI→terracom.es；Black X→iWIN；MedusaLocker→Lawter；Qilin→魁北克建筑委员会；The Gentlemen→Glassdoor（**未确认**）；另有哥伦比亚市政库、Canada Goose、新加坡签证、Stats SA、Lucid Motors 等数据售卖声称——**全部为声称，未作独立核验。**

地址（例）：
- https://x.com/FalconFeedsio/status/2094875311209086997
- https://x.com/ThreatAtlas/status/2094929457702113453
- https://x.com/FalconFeedsio/status/2094938746793984223
- https://x.com/XQOPTRX/status/2094854239767925104
- https://x.com/DailyDarkWeb/status/2094942896357306597

IoC：声称受害者域名≠C2；未见可核验攻击者基础设施表。

## 地址／IoC 汇总

### PaperCut 狩猎字符串（厂商公告，相对昨日未变）

```
ERROR No suitable driver found for jdbc:no:x
ERROR DatabaseUtils - Database error looking up cardID: VALUES CAST
DB URL: jdbc:derby:memory:pwn;create=true
Database error looking up cardID: VALUES CAST(X'cafebabe
Database error looking up cardID: VALUES CAST('
DB URL: jdbc:no:x DB Driver: <5-char random name>
\server\lib\<5-char-name>.class
\server\data\content\<5-char-name>.cmd
\server\data\content\<5-char-name>.out
Windows service 'Remote Access Service' / SimpleService.exe (SimpleHelp)
unexpected AnyDesk under C:\ProgramData\AnyDesk.exe
```

厂商强调：缺失这些 IoC ≠ 未中招。公网暴露应假定失陷并取证。

### PaperCut Emergency Patch Release 3 — 全部 18 条安装包 SHA256（2026-09-01）

- `pcmf-setup-26.0.4-PO-4560.76531.exe` → `9375a9c3cf84140a1d8e21b72d3d2c57d85d4de09ea9ae1dc021b64732427da7`
- `pcmf-setup-26.0.4-PO-4560.76531.sh` → `02526fea432069eb90279c4e300ea44bf46eaf432a95b05e8a59b55a0c5c001b`
- `pcmf-setup-26.0.4-PO-4560.76531.dmg` → `bcbe7b2c2d6463b146ec870c9e584e4e404d15756ce822c9277539848d870259`
- `pcmf-setup-25.0.12-PO-4560.76532.exe` → `ba81e871ca20d688dd26fc950abaa49fb5ccb71a6dce3be97736256f644c0633`
- `pcmf-setup-25.0.12-PO-4560.76532.sh` → `03ce77aaed2c8dd8e28b76eb314ee3f5c18b4f13968e5edcb7be469a8faf1c59`
- `pcmf-setup-25.0.12-PO-4560.76532.dmg` → `2b6abda60be63d42053f3625c52b65ab45ed29b1226de7944b8724520d579ecf`
- `pcmf-setup-24.1.9-PO-4560.76534.exe` → `0c915094bbf9f6e768e0d12dc9a8005a52594cc0760262010c1cc03861b472aa`
- `pcmf-setup-24.1.9-PO-4560.76534.sh` → `61512014718d1fc2d655c298b7a78bb3ec2ee411470cb57c7df6dfbbebc782cc`
- `pcmf-setup-24.1.9-PO-4560.76534.dmg` → `6f320956b05b7b29fa2943f6a1af488a48c8a69b42a09d1f0e6d2f6b8183fe23`
- `pcng-setup-26.0.4-PO-4560.76530.exe` → `51585ee73b70362da3739b8ec77f79336a5c5db9bddcde3fd49ccfe953b529a1`
- `pcng-setup-26.0.4-PO-4560.76530.sh` → `939962a7e660e7bd90dd50e28bce2a337562140813f885c42cf792a2877d05e6`
- `pcng-setup-26.0.4-PO-4560.76530.dmg` → `2996de9a85cc5f071df126539d8af8c12b72a46146021a06e15e53aceb5f83c1`
- `pcng-setup-25.0.12-PO-4560.76533.exe` → `083e52d55a27724f3f8829537937f80b3977568c27d933cb8f89b61ddc1be9d4`
- `pcng-setup-25.0.12-PO-4560.76533.sh` → `68858979b4db69e7c4dc41f2d50ea2642a087855601bdb7f33d8a294c259fbdb`
- `pcng-setup-25.0.12-PO-4560.76533.dmg` → `9f12cc0b4cf009f01c1daba3d227e5a122c163e919517d25b01d4cada235d630`
- `pcng-setup-24.1.9-PO-4560.76535.exe` → `ebfea162e52b9f2768b15077647b78d3808473932c4c951f6e82ff9040ca8ced`
- `pcng-setup-24.1.9-PO-4560.76535.sh` → `cc010e42b0e94fe67a973a9b8303848f1ee9028b06d78ae9256daf43611b225e`
- `pcng-setup-24.1.9-PO-4560.76535.dmg` → `b655928dda17d138aea14f8a150eb0ff509d7676b33b1b569a9f853319ffd7cc`

下载目录以厂商公告为准：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/

### AMOS（LWiS @Wietze，已 defang）

- lure：`brewmacosterm[.]com`
- stage 1：`satinmaple4[.]com`
- stage 2：`flint-32[.]com`
- X：https://x.com/Wietze/status/2094766933216264545

### Citrix 狩猎路径（续，非本轮新）

- `/var/vpn/theme/x.php`
- `/var/vpn/theme/z.php`

### 其他条目

SonicWall／JFrog／Langflow／Exchange／Proxmox／CloudStack／Switchvox／HPE／Gravity／WPLP／MLflow／工具／多数 APT：**未见公开攻击者 C2／下载／钱包／样本哈希**（或仅存在于未全文抄录的厂商长附录）。勒索声称域名不作 C2。

### 全部高信号 URL（便于复制）

- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-06
- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://www.papercut.com/blog/news/behind-the-scenes-august-security-incident/
- https://www.bleepingcomputer.com/news/security/recently-patched-papercut-zero-days-used-in-data-theft-attacks/
- https://www.securityweek.com/papercut-exploitation-escalates-to-active-intrusions/
- https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://nvd.nist.gov/vuln/detail/CVE-2026-64849
- https://nvd.nist.gov/vuln/detail/CVE-2026-83548
- https://nvd.nist.gov/vuln/detail/CVE-2026-82329
- https://nvd.nist.gov/vuln/detail/CVE-2026-0768
- https://nvd.nist.gov/vuln/detail/CVE-2026-62911
- https://nvd.nist.gov/vuln/detail/CVE-2026-51083
- https://nvd.nist.gov/vuln/detail/CVE-2026-9586
- https://github.com/projectdiscovery/nuclei-templates/pull/17025
- https://cloud.google.com/blog/topics/threat-intelligence/financially-motivated-threat-actor-breeze-comet-targets-brazil/
- https://securelist.com/mirage-kitten-new-backdoors-noderabbit-pollcat/121244/
- https://thehackernews.com/2026/09/russia-aligned-uac-0099-plants-nuclear.html
- https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

## LWiS 固定信源（每日交叉，不替代 X Latest）

Bad Sector Labs [Taking a Break - 2026-04-06](https://blog.badsectorlabs.com/taking-a-break-2026-04-06.html) 公开的 LWiS 信源。情报仍与 X Latest 交叉合并。

- LWiS X List（Cybersecurity，500 Members）：https://x.com/i/lists/1239330068461244424
- List 成员页：https://x.com/i/lists/1239330068461244424/members
- 成员备份（500 handle）：`/home/box/workspace/security-watch/lwis-sources/x-list-handles.txt`
- 成员 JSON：`/home/box/workspace/security-watch/lwis-sources/x-list-members.json`
- LWiS 博客清单（443 URL）：https://blog.badsectorlabs.com/files/blogs.txt
- 博客清单本地副本：`/home/box/workspace/security-watch/lwis-sources/blogs.txt`
- Risky Business 播客：https://risky.biz/
- tl;dr sec 通讯：https://tldrsec.com/
- 复刊通知：https://subscribe.badsectorlabs.com/subscription/form

本窗口交叉：List 时间线可读（扫 534，保留 46，覆盖约 25h）。blogs.txt 高信号跟到 watchTowr／厂商交叉（JFrog／PaperCut 等）。Risky Bulletin（Dutch intel powers／RBNEWS607，08-31）在邻近窗；周播 [#850](https://risky.biz/RB850/)（08-26）与 tl;dr sec [#343](https://tldrsec.com/p/tldr-sec-343)（08-27）仍早于本窗、无新号。AMOS IoC 来自 List 成员 @Wietze。

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://nvd.nist.gov/vuln/detail/CVE-2026-64849
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day%20OR%20%220-day%22&src=typed_query&f=live
- https://x.com/search?q=(github.com)%20(C2%20OR%20%22red%20team%22%20OR%20nuclei%20OR%20sliver%20OR%20havoc%20OR%20cobalt)&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
- https://blog.badsectorlabs.com/taking-a-break-2026-04-06.html
- https://x.com/i/lists/1239330068461244424
- https://x.com/i/lists/1239330068461244424/members
- https://blog.badsectorlabs.com/files/blogs.txt
- https://risky.biz/
- https://risky.biz/RBNEWS607/
- https://risky.biz/risky-bulletin-dutch-intel-services-to-get-extensive-new-powers/
- https://tldrsec.com/
- https://tldrsec.com/p/tldr-sec-343
- https://subscribe.badsectorlabs.com/subscription/form
