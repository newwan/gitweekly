# X 安全情报晚报 · 2026-08-31

> 搜集窗口：圣地亚哥时间 **2026-08-30 20:00 至 2026-08-31 20:35**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周一）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-08-31.json`（collected_at **2026-08-31T20:08:00-04:00**）。CISA KEV catalogVersion **2026.08.31**／**1687** 条／dateReleased **2026-08-31T14:55:13.3856Z**（昨日仍为 2026.08.27／1685）。**本窗口 dateAdded：PaperCut CVE-2026-82078＋CVE-2026-81578（due 2026-09-14）**。无 08-30 新 CVE。无 08-30／08-31 新 ICSA。**期限今日：无。** 期限明日 09-01：无。PaperCut 厂商页 Last updated **August 31, 2026**（AEST 4:21pm 仅状态更新，**无新 IoC**；补丁 SHA256 未变）。
> X：文件 `/workspace/x-posts-2026-08-31.json`（**74** 条，cve 35／tool 3／apt 36；**logged_in=true**／账号 **@seogoogle4**；无登录墙／无 CAPTCHA）。搜索 A Latest 最旧可见约 **2026-08-31T20:24:01Z**（约 **3 小时 41 分**，高流量，**不可当作完整 24h**）。搜索 B（github.com + C2／red team／nuclei／sliver／havoc／cobalt）**4 次尝试均只返回 “Something went wrong. Try reloading.”，0 条帖、0% 覆盖**。搜索 C 连续覆盖至约 **2026-08-31T16:17Z**（约 **8 小时**）。LWiS X List 可读、未限流，全日时间线已扫（混有更旧引用）。**公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉。A／B／C 窗口均短于 24h。LWiS 信源（X List 500 ＋ blogs.txt 443 ＋ Risky Business ＋ tl;dr sec）与 X Latest 交叉、不替代。
> 规则：每条含完整 https URL；分列原帖／仓库／厂商／文章；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、请求样例或 PoC。

## 今日摘要

- **【主条 · 今日入 KEV】** PaperCut NG／MF **CVE-2026-81578**（缺认证）＋ **CVE-2026-82078**（不安全反射）已加入 CISA KEV。catalogVersion **2026.08.31**／1687；dateAdded **2026-08-31**；联邦期限 **2026-09-14**；ransomwareCampaignUse **Unknown**。可连锁。NVD 今日改为 Analyzed，CVSS 3.1 **9.8**／**9.1**。厂商页 Last updated August 31，AEST 4:21pm「No new information to report」——**无新 IoC**，Emergency Patch Release 2 SHA256 未变。X：Rapid7／@stephenfewer 称 Metasploit 模块已公开（MF／NG，v24／v25／v26）；传感器侧称周末已见利用链。**不转写模块或 repro。** 公网 Application Server 仍须立刻限制 Web 管理面。IoC：见汇总（仍为 30 Aug 表）。
  CISA：https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
  厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-81578 https://nvd.nist.gov/vuln/detail/CVE-2026-82078
  X：https://x.com/__kokumoto/status/2094558637855535156 https://x.com/stephenfewer/status/2094340833071804479 https://x.com/PrevidianCyber/status/2094325754540532216

- **本窗口 APT · 中国背景 Fire Ant 转向 Cisco IOS XR／受信基础设施（Sygnia 新闻稿 08-30；BC／THN 08-31）**：从 VMware 虚拟化扩展到路由器、TACACS、Linux 管理机。观察含 GRE 隐蔽隧道、抑制 syslog、FTP 出 PCAP、伪装 Zabbix 的 BridgeAgent。与 UNC3886 有重叠描述。狩猎哈希见 IoC。**不转写植入实现。**
  厂商／IR：https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
  新闻稿：https://www.sygnia.co/press-release/sygnia-reveals-new-activity-by-china-nexus-threat-actor-fire-ant-targeting-trusted-infrastructure/
  文章：https://www.bleepingcomputer.com/news/security/chinese-fire-ant-hackers-turn-cisco-routers-into-spying-platforms/ https://thehackernews.com/2026/08/china-linked-fire-ant-hijacks-cisco.html
  X：https://x.com/techintelpro/status/2094490262559228273

- **本窗口 · Unit 42 Spring Ring（08-31）**：2026 年 1–4 月 Microsoft Teams 语音钓鱼，>150 名员工／≥10 个租户，随后 RMM／自制投放或 PetitPotam NTLM 中继。IoC：SHA256、C2、VPN IP、伪装 IT 邮箱见汇总。
  文章：https://unit42.paloaltonetworks.com/spring-ring-voice-phishing-campaigns/

- **本窗口交叉 · Rails KindaRails2Shell CVE-2026-66066（尚未入 KEV）**：Active Storage＋libvips 任意文件读，GitHub GHSA CVSS 4.0 **9.5**。补丁 7.2.3.2／8.0.5.1／8.1.3.1。X 称 VulnCheck 约 7,000 台暴露且利用已开始；另有「打过 8.1.3.1 仍可能在拿到有效签名 variation-key 后走变体」的说法——**以厂商／Rapid7 补丁说明为准，本报不核验变体、不转写文件格式技巧。** NVD 状态仍 Received，lastModified 2026-08-05。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-66066
  仓库：https://github.com/rails/rails/releases/tag/v8.1.3.1 https://github.com/rails/rails-forensics-CVE-2026-66066
  文章：https://www.rapid7.com/blog/post/etr-kindarails2shell-cve-2026-66066-critical-arbitrary-file-read-and-possible-remote-code-execution-in-ruby-on-rails/ https://www.securityweek.com/critical-ruby-on-rails-vulnerability-in-attackers-crosshairs/
  X：https://x.com/connect24h/status/2094566592638312564 https://x.com/Dinosn/status/2094407077519045076

- **续报在野 · Citrix NetScaler CVE-2026-8452（KEV due 已过 08-29）**：X 转 Help Net Security／watchTowr——厂商原标 DoS，分析称为未认证 RCE；**6/30 及之后构建与本轮利用无关**。昨日晚报已收 KEV 条目。IoC 延续：`/var/vpn/theme/x.php`、`z.php`。
  厂商：https://support.citrix.com/external/article/CTX696604/netscaler-adc-and-netscaler-gateway-secu.html
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-8452
  X：https://x.com/retr0hxx/status/2094549786422837661 https://x.com/retr0hxx/status/2094549903582343239

- **本窗口新闻 · 柏林确认 Rhysida 数据失窃（BC 08-31）**：市府确认勒索后被列；行为体声称约 5.79 TB／144 万文件；市长称不付。中旬发现、08-28 公开声称。IoC：未见公开 C2／样本哈希。
  文章：https://www.bleepingcomputer.com/news/security/berlin-confirms-data-theft-after-rhysida-ransomware-attack-claims/

- **X 旧 KEV 回放（非今日新加）**：SharePoint **CVE-2026-45659**（cisaExploitAdd **2026-07-01**）；Zimbra **CVE-2026-73570**（KEV **08-21**，X 称 274 台）；JetBrains TeamCity **CVE-2026-63077**（KEV **08-05**）；Windows 内核 **CVE-2026-68820**（KEV **08-11**，X 称 Lazarus 补丁前在野）。**不要当成今日新入目录。**
  厂商：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-45659 https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories https://www.jetbrains.com/privacy-security/issues-fixed/ https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-45659 https://nvd.nist.gov/vuln/detail/CVE-2026-73570 https://nvd.nist.gov/vuln/detail/CVE-2026-63077 https://nvd.nist.gov/vuln/detail/CVE-2026-68820

- **工具**：Sliver **仍为 v1.7.6**；nuclei-templates **仍为 v10.4.8**。X：@kyleavery 发布 macOS 分析沙箱 **Bintracer** 首个公开版（本轮未解析到 GitHub URL，只记原帖）；Synacktiv 发 AD 服务仿真／GPO 研究。Search B 全灭，工具面主要靠公开备援＋List／C。IoC：未见公开 IoC。
  仓库：https://github.com/BishopFox/sliver/releases/tag/v1.7.6 https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
  文章：https://www.synacktiv.com/en/publications/simulating-legitimate-active-directory-services-on-the-network-the-case-of-gpo
  X：https://x.com/kyleavery/status/2094418970866499864 https://x.com/Synacktiv/status/2094363888292593980

- **勒索／声称（X 窗口，公开备援未逐条核验）**：BrainCipher 多条（含 icot.es）；Qilin → Allied Recycling；INC RANSOM → FFKR／New Century Ophthalmology；NightSpire → Easyoga、Truckworx；The Gentlemen → CareerSource PBC；lockbit5 → hoaattorneys.com；另有 Orova／settra／FALCON 等。暗网声称：比利时 70 万公民、Thailand Post、Libya Ports、Baguio、TAP Air Portugal flytap、Adventus 等——**均为声称，未作独立核验。**
  例：https://x.com/FalconFeedsio/status/2094475895583170846 https://x.com/ThreatAtlas/status/2094516797211046072

- **ICS／Alert**：无 08-30／08-31 新 ICSA（仍 ICSA-26-239-01..05，08-27）。**新 CISA Alert 一条**：今日两连加 KEV。Risky Bulletin [RBNEWS607](https://risky.biz/RBNEWS607/)（08-31）；周播 #850 与 tl;dr sec #343 均早于本窗口。

## CVE / POC / 漏洞

### 1. 【今日入 KEV】PaperCut NG／MF CVE-2026-81578 ＋ CVE-2026-82078（dateAdded 2026-08-31；联邦期限 2026-09-14）

相对昨日晚报：KEV **已收录**（昨日 in_kev=false）。CISA 08-31 警报点名这两条，可连锁。81578：关键功能缺认证，未认证远程可改部分系统配置。82078：不安全反射，可操纵配置并在 PaperCut 服务进程安全上下文执行 classpath 上的 Java 字节码。ransomwareCampaignUse **Unknown**。NVD Last Modified **2026-08-31**（81578 18:41:19Z／82078 18:41:41Z）；状态 Received→**Analyzed**；NVD CVSS 3.1 **9.8**（81578）／**9.1**（82078）；厂商 CVSS 4.0 仍为 8.8／9.4。

厂商页 Last updated **August 31, 2026**。新 changelog：*31 August 2026, 4:21pm (AEST) Status update posted. No new information to report.* 官方版仍在开发；当前下载集仍是 **Emergency Patch Release 2**（28 Aug AEST）。受影响至 **24.1.10／25.0.13／26.0.5** 之前。公网 Application Server：**立刻**把 Web 管理面限制到受信 IP。Site Server／二级打印服务器打同一补丁。X 称 Metasploit 模块已公开、传感器周末已见链利用。**本报不转写根因、请求样例、模块用法或 repro。**

狩猎信号与 Release 2 SHA256：**与昨日相同**，见「地址／IoC 汇总」。厂商强调：缺失这些 IoC ≠ 未中招。

地址：
- CISA 08-31 两连加警报：https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- KEV 字段页：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-81578
- 另：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-82078
- 厂商紧急公告：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- NVD CVE-2026-81578：https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- NVD CVE-2026-82078：https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- Huntress：https://www.huntress.com/blog/papercut-actively-exploited
- Rapid7：https://www.rapid7.com/blog/post/etr-papercut-ng-mf-critical-zero-day-exploited-in-the-wild/
- BC（Release 2）：https://www.bleepingcomputer.com/news/security/papercut-releases-second-emergency-patch-for-exploited-flaws/
- 仓库（框架，不链具体 module 路径）：https://github.com/rapid7/metasploit-framework
- X：https://x.com/__kokumoto/status/2094558637855535156
- X：https://x.com/stephenfewer/status/2094340833071804479
- X：https://x.com/PrevidianCyber/status/2094325754540532216
- X：https://x.com/SecAlertsCo/status/2094541440873328851
- X：https://x.com/N3mes1s/status/2094483447372824824

IoC：厂商狩猎字符串＋30 Aug 追加路径／SimpleHelp／AnyDesk／defanged 下载 URL＋全部 Release 2 SHA256 见「地址／IoC 汇总」。31 Aug **无新增 IoC 行**。

### 2. 【尚未入 KEV】Ruby on Rails CVE-2026-66066 KindaRails2Shell

GitHub CNA CVSS 4.0 **9.5**（CRITICAL）。NVD 发布 2026-07-30，状态 **Received**，lastModified **2026-08-05**，**cisaExploitAdd 无**。Active Storage 在 libvips 变体处理器下不安全默认初始化（CWE-1188），可导致任意文件读，进而可能拿到签名材料走到代码执行。补丁：7.2.3.2、8.0.5.1、8.1.3.1。临时：libvips ≥8.13 设 `VIPS_BLOCK_UNTRUSTED`。X 今日放大 VulnCheck 暴露面与「补丁后变体」说法；公开备援以 NVD／Rails advisory／Rapid7 ETR 为准。**不转写 MAT／HDF5 或 variation 链。**

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-66066
- 仓库补丁标签：https://github.com/rails/rails/releases/tag/v7.2.3.2
- 另：https://github.com/rails/rails/releases/tag/v8.0.5.1
- 另：https://github.com/rails/rails/releases/tag/v8.1.3.1
- 取证工具仓：https://github.com/rails/rails-forensics-CVE-2026-66066
- Rapid7 ETR：https://www.rapid7.com/blog/post/etr-kindarails2shell-cve-2026-66066-critical-arbitrary-file-read-and-possible-remote-code-execution-in-ruby-on-rails/
- Rapid7 技术分析：https://www.rapid7.com/blog/post/ra-kindarails2shell-technical-analysis-cve-2026-66066/
- SecurityWeek：https://www.securityweek.com/critical-ruby-on-rails-vulnerability-in-attackers-crosshairs/
- X：https://x.com/connect24h/status/2094566592638312564
- X：https://x.com/Dinosn/status/2094407077519045076

IoC：未见公开 C2／样本哈希。

### 3. 【昨日到期／续报在野】Citrix NetScaler CVE-2026-8452（KEV due 2026-08-29）

仍在 KEV，due 已过。X 今日两条：Help Net Security 称先前已补漏洞在野；日文帖称 Citrix 写作 DoS、watchTowr 分析为未认证 RCE，**6/30 构建与本轮利用无关**。狩猎路径延续昨日。**不转写利用。**

地址：
- 厂商：https://support.citrix.com/external/article/CTX696604/netscaler-adc-and-netscaler-gateway-secu.html
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- CISA KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-8452
- X：https://x.com/retr0hxx/status/2094549786422837661
- X：https://x.com/retr0hxx/status/2094549903582343239

IoC：`/var/vpn/theme/x.php`；`/var/vpn/theme/z.php`。未见本轮新 C2。

### 4. 【NVD 今日新 Received】Kirby CMS CVE-2026-71415

NVD 发布／lastModified **2026-08-31T21:17:48.057**，状态 Received。CWE-862 缺授权。GitHub CNA CVSS 4.0 **7.1**。修复见 5.5.2 与 GHSA-67mx-6wf2-92xp。**尚未入 KEV。** X @dailycve 今日转载。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-71415
- 仓库 release：https://github.com/getkirby/kirby/releases/tag/5.5.2
- GHSA：https://github.com/getkirby/kirby/security/advisories/GHSA-67mx-6wf2-92xp
- 提交：https://github.com/getkirby/kirby/commit/37e206f3ed40ad3fab2e47e055ccb19e9c207dab
- X：https://x.com/dailycve/status/2094567504320360466

IoC：未见公开 IoC。

### 5. 【NVD 今日 lastModified】WP Full Pay／Stripe 插件 CVE-2026-80311；JFrog CVE-2026-82329 续

CVE-2026-80311：NVD 发布 08-29，lastModified **2026-08-31T20:14:36.250**，状态 Deferred，CVSS 3.1 **4.3**（MEDIUM）。WPScan：未授权可取消他人订阅。X 西语帖写「取消他人订阅」。**未入 KEV。**

CVE-2026-82329：JFrog Artifactory，NVD lastModified **2026-08-31T19:17:18.813**，仍 Awaiting Analysis，厂商 CVSS 3.1 **9.8**，**仍未入 KEV**。与已在 KEV、due 09-10 的路径穿越 **CVE-2026-66384** 不是同一条。

地址：
- NVD CVE-2026-80311：https://nvd.nist.gov/vuln/detail/CVE-2026-80311
- WPScan：https://wpscan.com/vulnerability/e1b0e815-e803-4a14-ab2a-ed860e82c782/
- X：https://x.com/CibersegLATAM/status/2094560181229060522
- NVD CVE-2026-82329：https://nvd.nist.gov/vuln/detail/CVE-2026-82329
- 厂商索引：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- NVD CVE-2026-66384：https://nvd.nist.gov/vuln/detail/CVE-2026-66384

IoC：未见公开 IoC。

### 6. 【X 窗口／NVD 已存在／非今日 KEV】Oracle AHF CVE-2026-70728；Linux tc UAF CVE-2026-53264

CVE-2026-70728：Oracle Autonomous Health Framework Trace File Analyzer v26.x。NVD Analyzed，发布 08-18，lastModified 08-26，Oracle CVSS 3.1 **8.5**，**未入 KEV**。X @DFIR_Lab 今日提示打补丁。厂商集合页：Oracle CPU/CSPU Aug 2026。

CVE-2026-53264：内核 traffic-control UAF。NVD Modified，CVSS 3.1 **7.8**，**未入 KEV**。稳定树多条提交。X @integ_sec 今日写业务影响帖。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-70728
- 厂商：https://www.oracle.com/security-alerts/cspuaug2026.html
- X：https://x.com/DFIR_Lab/status/2094577361547120760
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-53264
- Kernel 提交：https://git.kernel.org/stable/c/18af5d2ef0c4f65787fd1280c8b23286b9f2a835
- X：https://x.com/integ_sec/status/2094534449459236922

IoC：未见公开 IoC。

### 7. 【旧 KEV 回放】SharePoint CVE-2026-45659；Zimbra CVE-2026-73570；TeamCity CVE-2026-63077；Win 内核 CVE-2026-68820

四条均早已在 KEV（cisaExploitAdd 分别为 2026-07-01、08-21、08-05、08-11）。X 今日当作新闻转。SharePoint 帖 t.co 未展开。Zimbra：X 称未认证 SMTP 命令注入、公开利用、274 台。TeamCity：X 称失陷服务器使 CVE-2026-63077 被用来暴露云／备份／AWS 凭据。68820：X 称 Lazarus 在 8 月补丁星期二前在野。**本报不升格为今日新加。**

地址：
- MSRC SharePoint：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-45659
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-45659
- X：https://x.com/blueteamsec1/status/2094571382223065444
- Zimbra 安全中心：https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- KEV 字段：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-73570
- X：https://x.com/leonov_av/status/2094531587232723151
- JetBrains：https://www.jetbrains.com/privacy-security/issues-fixed/
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-63077
- X：https://x.com/TweetThreatNews/status/2094527223256514974
- MSRC 68820：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-68820
- X：https://x.com/SJE1981/status/2094524901096931744

IoC：本轮这些 X 帖未见公开 C2／样本哈希。

### 8. 【昨日到期续】ownCloud CVE-2023-49105 ＋ Linux Kernel CVE-2026-53362（due 已过 08-30）

仍在 KEV，due 昨日。NVD lastModified 未变。ownCloud：已知用户名且未配 signing-key 时可未认证动文件。Kernel：IPv6 子系统提权。按 BOD 26-04 补丁前取证分诊。

地址：
- CISA 08-27 三连加：https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- 厂商 ownCloud：https://owncloud.com/security-advisories/webdav-api-authentication-bypass-using-pre-signed-urls/
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- Kernel：https://git.kernel.org/stable/c/14200d435af9a9eeb444f529fc2f689a236b7962

IoC：未见公开 IoC。

### 9. 【X 声称／本报不展开】HardBreacher Kaspersky LPE；未编号 Win 内核 0-day；evil.blog Safari 诱饵

X 转载 HardBreacher 声称 Win11 上 Kaspersky Endpoint Security 本地提权 PoC——**未见 CVE、未见厂商确认**。@gr4ss341 称又向 MSRC 报了一条未编号内核 LPE。@PaulosYibelo 帖点名 `evil.blog` 为声称的 Safari 0day 诱饵——**不要访问**。**不转写 PoC。**

地址：
- 文章：https://cybersecuritynews.com/hardbreacher-kaspersky-zero-day/
- X：https://x.com/moton/status/2094536211474067608
- X：https://x.com/gr4ss341/status/2094440372458181076
- X：https://x.com/PaulosYibelo/status/2094508325471674389

IoC：声称诱饵域 `evil.blog`（未访问、未解析）。其余未见公开 IoC。

## 工具与 GitHub 发布

### 1. Sliver／nuclei-templates：本日无显著更新

Sliver **v1.7.6**（published 2026-08-28T18:37:03Z）。nuclei-templates **v10.4.8**（2026-08-24T13:01:50Z）。均早于本窗口。X 搜索 B 因软限流 **0 条**，不能用 X 否定其他 C2 发布。

地址：
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

### 2. Bintracer（macOS 恶意软件分析沙箱，X 首发）

@kyleavery 称发布 @BintracerLabs 首个公开版：引爆 Mach-O／app bundle／dylib，解 DMG／PKG，分析 JXA／AppleScript／Python／Perl／shell。本轮 Web 检索**未解析到独立 GitHub／产品 URL**，只保留原帖。防御向分析工具，不是 C2。

地址：
- X：https://x.com/kyleavery/status/2094418970866499864

IoC：未见公开 IoC。

### 3. Synacktiv：内网仿真合法 AD 服务（GPO 场景）

文章讲用灵活脚本仿真 LDAP／SMB 等合法 AD 服务，并以 GPO 利用作演示。防御／红队研究。**不转写利用步骤。**

地址：
- 文章：https://www.synacktiv.com/en/publications/simulating-legitimate-active-directory-services-on-the-network-the-case-of-gpo
- X：https://x.com/Synacktiv/status/2094363888292593980

IoC：未见公开 IoC。

### 4. 其他

@fr0gger_ 提醒可用 https://novahunting.ai/skill-scanner/ 扫 AI skill（转述聊天里恶意下载）。PaperCut Metasploit 模块见 CVE 第 1 条，此处不重复。

## APT / Malware 分析

### 1. Fire Ant（中国背景）扩展到 Cisco IOS XR／TACACS／Linux 管理面

Sygnia 新闻稿日期 August 30, 2026；BC／THN 08-31。行为体从 hypervisor 转向组织依赖的路由、认证、管理基础设施。公开描述：Cisco IOS XR 作作业平台（acpid 植入）、GRE 隐蔽、TacTap 针对 tac_plus、抑制日志、FTP 出包、BridgeAgent（伪装 Zabbix）。与 UNC3886 有重叠表述。狩猎：厂商 IoC 表 SHA1＋YARA SHA256，见汇总。**不转写植入／隧道细节。**

地址：
- Sygnia：https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
- 新闻稿：https://www.sygnia.co/press-release/sygnia-reveals-new-activity-by-china-nexus-threat-actor-fire-ant-targeting-trusted-infrastructure/
- BC：https://www.bleepingcomputer.com/news/security/chinese-fire-ant-hackers-turn-cisco-routers-into-spying-platforms/
- THN：https://thehackernews.com/2026/08/china-linked-fire-ant-hijacks-cisco.html
- X：https://x.com/techintelpro/status/2094490262559228273
- X：https://x.com/DailyDarkWeb/status/2094479603498680576

IoC：见「地址／IoC 汇总」Fire Ant 节。

### 2. Unit 42 Spring Ring：Teams 语音钓鱼

报告日期 2026-08-31。2026 年 1–4 月，Microsoft Teams vishing，>150 员工、≥10 租户；得手后 RMM／定制投放或 PetitPotam NTLM 中继。伪装 IT helpdesk 的 onmicrosoft 身份。完整 IP／身份表在厂商文；本报抄 SHA256、C2、示例身份与 VPN IP。

地址：
- 文章：https://unit42.paloaltonetworks.com/spring-ring-voice-phishing-campaigns/

IoC：见汇总 Spring Ring 节。

### 3. ValleyRAT 藏在已签名广告软件；Aurora＋Cursor AI（X 交叉）

ValleyRAT（亦称 Winos 4.0）经已签名 QN Wallpaper 一类广告软件 DLL 侧载；用户常把此类软件加进杀软排除。Kaspersky／THN。地理以中国、印度检测为主。Silver Fox 被指向。

Aurora：X 转 THN「对 10 个目标用 Cursor AI」。公开报道主体多在 **08-27 Reuters／Gambit**（略早于本窗口起点）；本报作 X 交叉，不把 08-27 调查写成今日新披露。

地址：
- Kaspersky Securelist：https://securelist.com/valleyrat-backdoor-adware/121175/
- THN：https://thehackernews.com/2026/08/valleyrat-backdoor-hides-in-signed.html
- X：https://x.com/Dinosn/status/2094434283888722067
- X（Aurora）：https://x.com/Dinosn/status/2094423104969757175

IoC：Kaspersky 文给出初始样本 MD5 `c24e99f9437feacaa63766a3cde3fe3d`（侧载宿主分析入口）。其余完整哈希见 Securelist 原文。本轮 X 帖本身未见 C2。

### 4. JSCeal 研究（hasherezade 交叉 Check Point）

@hasherezade 称 JSCeal（V8 字节码／加密货币窃取相关）研究博文发出，引用 Check Point Research。卡片域 research.checkpoint.com，单帖未展开完整 slug。

地址：
- X：https://x.com/hasherezade/status/2094422378293932516

IoC：该帖未见公开 IoC。

### 5. Storm-2755 加拿大 AiTM／工资劫持（X 回放）

X @riskawareco 今日写「微软刚记录 Storm-2755」。厂商主文日期是 **2026-04-09**（Payroll Pirate），**不是今日新披露**。AiTM 打 M365 会话、改工资账户。狩猎仍看微软文。

地址：
- 厂商：https://www.microsoft.com/en-us/security/blog/2026/04/09/investigating-storm-2755-payroll-pirate-attacks-targeting-canadian-employees/
- X：https://x.com/riskawareco/status/2094488174328172581

IoC：以微软官方表为准；本轮 X 帖未抄新指标。

### 6. TerminalFix（微软 08-28；BC 08-31 放大）

假 Cloudflare CAPTCHA → 把 PowerShell 粘进 Windows Terminal → DLL 侧载 `LockScreenContentServer.exe`＋`dui70.dll` → PNG 隐写 → Python 反向隧道到 `gitnow[.]dev:443`。**不转写粘贴命令。** IoC 仍用微软 08-28 表。

地址：
- 厂商：https://www.microsoft.com/en-us/security/blog/2026/08/28/terminalfix-campaign-deploys-reverse-tunnel-through-multistage-intrusion/
- BC 08-31：https://www.bleepingcomputer.com/news/security/microsoft-warns-of-terminalfix-attacks-deploying-reverse-tunnels/
- THN（昨日已见）：https://thehackernews.com/2026/08/terminalfix-uses-fake-cloudflare.html

IoC：见汇总 TerminalFix 节。

### 7. 柏林／Rhysida；Cronos／Tectonic（新闻，非传统 APT 报告）

柏林市府确认 Rhysida 列名后的数据失窃，拒付。Cronos 链在 Tectonic 约 7400 万美元价格操纵事件后重启（PeckShield：借出约 7400 万，链上仅约 600 万 ETH 离场）；2026-08-30 23:49:01 UTC 起自块 90,896,189 出块。

地址：
- https://www.bleepingcomputer.com/news/security/berlin-confirms-data-theft-after-rhysida-ransomware-attack-claims/
- https://www.bleepingcomputer.com/news/security/cronos-blockchain-restarts-after-74-million-tectonic-exploit/

IoC：这两篇未见公开恶意 C2／样本哈希。

### 8. 勒索声称与暗网帖（X 窗口，未独立核验）

公开备援未逐条核验下列受害者。只记行为体／声称对象／原帖。

| 行为体 | 声称对象 | X |
|---|---|---|
| Qilin | Allied Recycling（alliedrecycling.ie，IE） | https://x.com/FalconFeedsio/status/2094475895583170846 |
| INC RANSOM | FFKR Architects（ffkr.com，US）；New Century Ophthalmology（ncophth.com，US） | https://x.com/FalconFeedsio/status/2094488401236160771 https://x.com/FalconFeedsio/status/2094468283110166978 |
| NightSpire | Easyoga、Truckworx | https://x.com/FalconFeedsio/status/2094529744981364929 |
| The Gentlemen | CareerSource Palm Beach County（careersourcepbc.com，US） | https://x.com/FalconFeedsio/status/2094495081214677205 |
| FALCON | Hayward Holdings（hayward.com，US） | https://x.com/FalconFeedsio/status/2094480111299088831 |
| BrainCipher | icot.es、syc.es、ahadandco.com、aeiconsultants.com、ccsperfusion.com、crmeyer.com、sago.com 等 | https://x.com/ThreatAtlas/status/2094516797211046072 https://x.com/H4ckmanac/status/2094507516327494015 |
| lockbit5 | hoaattorneys.com（US） | https://x.com/ThreatAtlas/status/2094564553598140471 |
| Orova | Fu Sheng Industrial（HK）；ASYS Corporation（TW） | https://x.com/ThreatAtlas/status/2094471239246958713 |
| settra | manhattanloft.co.uk（GB） | https://x.com/ThreatAtlas/status/2094459554293841929 |
| （暗网声称） | 比利时约 70 万公民记录；Thailand Post；Libya Ports；Baguio 市政府；TAP Air Portugal flytap[.]com；Adventus；Castella Sports | https://x.com/DailyDarkWeb/status/2094581032146079748 https://x.com/intels_daily/status/2094500685358182718 |

IoC：上表域名为**声称受害者站点**，不是攻击者 C2。未见配套样本哈希。

### 9. ICS：本日无显著更新

无 08-30／08-31 新 ICSA。列表仍以 08-27 ICSA-26-239-01..05 为顶。X 提到的 Ebyte NA111-M CVE-2026-73125 对应 ICSA-26-239-05（08-27，非今日新发）。

地址：
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-239-05

## 地址／IoC 汇总

### PaperCut（厂商页；31 Aug 无新增，仍含 30 Aug 15:35 AEST 追加）

日志字符串：
- `ERROR No suitable driver found for jdbc:no:x`
- `ERROR DatabaseUtils - Database error looking up cardID: VALUES CAST`
- `DB URL: jdbc:derby:memory:pwn;create=true`
- `Database error looking up cardID: VALUES CAST(X'cafebabe`
- `Database error looking up cardID: VALUES CAST('`
- `DB URL: jdbc:no:x DB Driver: <5-char random name>`

落盘路径模式：
- `<install>\server\lib\<5-char-name>.class`
- `<install>\server\data\content\<5-char-name>.cmd`
- `<install>\server\data\content\<5-char-name>.out`

进程／服务：
- `pc-app.exe`／`pc-app` 拉起 `cmd.exe`（厂商观察）
- Windows 服务名 `Remote Access Service`，路径 `C:\ProgramData\JWrapper-Remote Access\JWAppsSharedConfig\restricted\SimpleService.exe`（SimpleHelp）
- `C:\ProgramData\ace.exe`；`C:\ProgramData\AnyDesk.exe`

厂商观察下载（已 defang，勿直接访问）：
- `hxxps://sendit[.]sh/Gg7Rp/ace[.]exe`
- `hxxps://download[.]anydesk[.]com/AnyDesk.exe`

**Emergency Patch Release 2 SHA-256（厂商表，与 08-30 相同）**

PaperCut MF：
- v26 Win `5c63ef18c523c85d5e73efc7fbb2bd2edacf0b03bcf80fe4d7e4c1a7c8bcbcf4`／Linux `6117b53dd0610052c53aeafced91cd3d0ad80ed1dcc578e873291a8b697b802a`／macOS `7dea84473f8d00d4608b7e797b633f130139e23bf5bba02848a1df0a7e2cc7c6`
- v25 Win `b296de7da020152a83291378ab4ca5c461d76510648347fd6e69f3fb2cd5e9c9`／Linux `296498ef5ec1ac8927dc1ccae9a9aa3c04036da6d2768813e6df818049b3f4a1`／macOS `3e5509f0514228031967934d32e4a40512bd6fb5857bfde3002866bc3ede3f9a`
- v24 Win `75aba456d6629848c89513371c44037f2bdddbc1e39bdadc16d1fed8b59766eb`／Linux `7ac8f002fb602d1f54665d8a18a25fc57cf41239ae0c03b18591ee220b57d419`／macOS `40581392cc11a1f46b90ab5c2607fdacade77aca0de6629c1d78a2a71548fc9c`

PaperCut NG：
- v26 Win `c9a2b356910b5fef3c114d48cb7c508414d1d35ddac74c530d1e8923d357e7d4`／Linux `3261356ced056fd5ab0962a07178701e80c6ebbce30d7158d20ed3c57b1dcf59`／macOS `bdd54d5cb9f20924b059986a44f849df499f7de7cb5cd0a60290d2b2610850e7`
- v25 Win `b155cf19cdab1b7fc92c2dd030d1c0cd439397d83d7749042f65e2364ca03589`／Linux `282be7404a25c12317a2079eed59e8794f0c9d7bd257dee60c39b529da18a46a`／macOS `276ee64a7bb4d4e242fe7ddaecf3cd279eee91e83fbd1e6f44050db2f90bda6d`
- v24 Win `f58a3fe4e9d7543c38a3f01e53f4a9ad34884289a71df25f734af9d977c06319`／Linux `a7ea1e2cdb22a4349ae854491b10b89a52d075e9106ec68f838f12d5f2a15f51`／macOS `1e70dd6510d0b9618035a3db462b78ece06cd70f41bcccca8196c015c46a480b`

### Fire Ant（Sygnia 厂商表，防御狩猎；完整表以原文为准）

YARA meta SHA-256：
- `110e6fb23be00d2ed251a445ee5b65aadf23b48b8db7419900d64539ad90c5a3` FIREANT_BridgeAgent_Backdoor
- `251c7a2684542c29ae2c1e1282b780163bf9f844179ef0759094b2b7e2f62f0f` FIREANT_BridgeAgent_Systemd_Unit companion

SHA1（文件名＋角色，原文）：
- `/bin/atd` `C164BFC953C66E58B11FC280E69FD43B8F255839` Custom SSH backdoor
- `/usr/sbin/cupsdd` `1aa6ab2006b5d9199aa87bb0bbd995aec698ac4f` Custom SSH backdoor
- `/usr/sbin/smartdd` `c164bfc953c66e58b11fc280e69fd43b8f255839` Medusa rootkit binary
- `/usr/sbin/acppid` `36005f5e4398a1c62a2a9271eddfcc1b44b1ad00` TacTap injector targeting tac_plus
- `/lib/libseconfd.so` `955cd45a2f6f226a2fdf44b329af1c8dde90cb38` TacTap injected TACACS library
- `/var/tmp/audit` `13f0c2a598e3aa63856c032a96b110aed963f0e8` VMCI/VSOCK-based backdoor
- `/var/tmp/ping` `5ba1242050b5b447052b210788a5a25593d6987d` REPTILE like binary later renamed
- `/var/tmp/sync` `7dab017f14628345d47bd4eb69cc49224f3054a7` Tineyshell
- `/usr/bin/acpid` `be6b27f429324a4af05a310d8ec9635e37c68a94` IOS XR implant
- `/pkg/bin/dhcpd_show_issu_status` `1682b652a15bde732489f22809b0b7594c228fd3` IOS XR implant
- `/pkg/bin/hd` `b149fa3a34bd585e7a674a4fd9538437bd06f514` IOS XR implant
- `/etc/rc.d/init.d/grub-rommon` `6ef7d2985edf743ebff413a9298a127e9475d72f` Masqueraded startup script used for persistence

### Spring Ring（Unit 42 厂商 IoC 节）

SHA-256：
- `24ab9fe5d5be62d3bf055a0ca4508e8bca2996b6d78649dce8145d8a27bc1c5b` obfuscated PowerShell payload / RAT dropper

URL（已 defang）：
- `hxxps[:]//san-sid[.]com/owners`

示例身份：
- `helpcenter@ithelpcenter365[.]onmicrosoft[.]com`
- `helpdesk@itprotectiondepartment[.]onmicrosoft[.]com`
- `ithelp@internalsystemsdaily[.]onmicrosoft[.]com`
- `ithelpdesk@certifiedupdatenetwork[.]onmicrosoft[.]com`

VPN／代理 IP（已 defang，厂商表）：
- `193.32.248[.]251` `193.138.7[.]142` `185.65.134[.]209` `178.130.47[.]46` `5.181.3[.]106` `2.56.172[.]214` `185.234.67[.]53` `45.8.157[.]185` `80.66.72[.]215` `136.0.20[.]6` `185.213.155[.]226` `185.155.99[.]161` `92.118.232[.]131` `45.182.189[.]80` `185.65.133[.]51` `45.33.22[.]47`

### TerminalFix（微软 08-28 官方表，BC 08-31 交叉）

域名：
- `gitnow[.]dev`（反向隧道 C2，443／WebSocket）
- `bestsocialmedianewspapper[.]com`（PNG 隐写投放）
- `offlineupdater[.]com`（投放 failover）
- `hxxps://linked-log[.]com/`（被黑站点样例）

文件：
- 目录 `C:\ProgramData\f47f2a8c21c9df4e`
- `LockScreenContentServer.exe`（合法签名宿主）＋恶意 `dui70.dll`
- ZIP SHA-256 `18c2090e8a0ae0568af9b87e59eaf8270f23d2909600ed9db91a9444fd8b278f`
- `client.py` SHA-256 `b8d107800403b9197e5b7609ceacd8e4cac1b0f9a1d156e6dacd6c3f7794b36a`

### ValleyRAT／其他

- 初始分析样本 MD5 `c24e99f9437feacaa63766a3cde3fe3d`（Kaspersky Securelist）
- 声称 Safari 诱饵域 `evil.blog`（X @PaulosYibelo；**不要访问**）

### Citrix 狩猎线索（非本轮新）

- `/var/vpn/theme/x.php`
- `/var/vpn/theme/z.php`

### 其他条目

其余 CVE／工具／勒索声称：**未见公开攻击者 C2／下载／钱包／样本哈希**（声称受害者域名见 APT 第 8 表，不作 C2）。

### 全部 URL（便于复制）

- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/27/cisa-adds-three-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://nvd.nist.gov/vuln/detail/CVE-2026-66066
- https://nvd.nist.gov/vuln/detail/CVE-2026-71415
- https://nvd.nist.gov/vuln/detail/CVE-2026-82329
- https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- https://nvd.nist.gov/vuln/detail/CVE-2023-49105
- https://nvd.nist.gov/vuln/detail/CVE-2026-53362
- https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
- https://www.bleepingcomputer.com/news/security/chinese-fire-ant-hackers-turn-cisco-routers-into-spying-platforms/
- https://unit42.paloaltonetworks.com/spring-ring-voice-phishing-campaigns/
- https://www.rapid7.com/blog/post/etr-kindarails2shell-cve-2026-66066-critical-arbitrary-file-read-and-possible-remote-code-execution-in-ruby-on-rails/
- https://github.com/rails/rails-forensics-CVE-2026-66066
- https://www.bleepingcomputer.com/news/security/berlin-confirms-data-theft-after-rhysida-ransomware-attack-claims/
- https://www.microsoft.com/en-us/security/blog/2026/08/28/terminalfix-campaign-deploys-reverse-tunnel-through-multistage-intrusion/
- https://securelist.com/valleyrat-backdoor-adware/121175/
- https://thehackernews.com/2026/08/valleyrat-backdoor-hides-in-signed.html
- https://www.synacktiv.com/en/publications/simulating-legitimate-active-directory-services-on-the-network-the-case-of-gpo
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://risky.biz/RBNEWS607/
- https://x.com/__kokumoto/status/2094558637855535156
- https://x.com/stephenfewer/status/2094340833071804479
- https://x.com/kyleavery/status/2094418970866499864
- https://x.com/techintelpro/status/2094490262559228273

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

本窗口交叉：List 时间线可读（扫约 1045 条，覆盖 08-31 全日）。blogs.txt 高信号跟到 Unit 42 Spring Ring（该域在 443 清单内）。Risky Bulletin [RBNEWS607](https://risky.biz/RBNEWS607/)（31 Aug）在窗口内；周播 [#850](https://risky.biz/RB850/)（26 Aug）与 tl;dr sec #343（Aug 27）不在窗口。Sygnia／CISA／PaperCut 厂商页为高信号但不在 443 清单内，仍作交叉。

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/31/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- https://nvd.nist.gov/vuln/detail/CVE-2026-81578
- https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- https://unit42.paloaltonetworks.com/spring-ring-voice-phishing-campaigns/
- https://www.sygnia.co/blog/fire-ant-evolves-from-hypervisors-to-trusted-infrastructure/
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
- https://tldrsec.com/
- https://subscribe.badsectorlabs.com/subscription/form
