# X 安全情报晚报 · 2026-08-24

> 搜集窗口：圣地亚哥时间 **2026-08-23 20:00 至 2026-08-24 20:05**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周一）。**
> **20:00 本轮 X Latest 已回收**（logged_in=true, blocked=false）。文件 `/workspace/x-posts-2026-08-24.json`（**38** 条）。搜索1 Latest（CVE／POC／exploit／0day）最旧可见约 **2026-08-24T23:35Z**（覆盖短，**不可当作完整 24h CVE 检索**）。搜索2 github.com (C2 OR "red team" OR nuclei) Latest 量少，但可回溯至 **8 月 16 日**（满 24h）。搜索3 原 APT 查询为 apartment／俚语噪声；改用 fallback「malware analysis／threat report／threat actor」Latest，最旧可见约 **2026-08-24T15:56Z**。t.co 未做重定向展开，仅照录推文可见 URL。
> 公开备援：**晚间公开备援后到**（`/workspace/security-watch-public-backup-2026-08-24.json`，**collected_at 2026-08-24T20:10:39-04:00**）。CISA KEV catalogVersion **2026.08.24**／**1675** 条已用 JSON 复核；本日新增 **CVE-2026-21962**（Oracle HTTP Server / WebLogic Server Proxy Plug-in）。GitLab **CVE-2026-19478** 仍未入目。ICS 最新仍为 **2026-08-20 ICSA-26-232-01**。目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、SOAP 体、reset-credentials 走流程或 PoC。本文件已按晚间备援就地补丁（原 20:00 晚报发出时尚未落地该 JSON）。

## 今日摘要

- **KEV 本日新增 · Oracle HTTP Server / WebLogic Server Proxy Plug-in CVE-2026-21962**：CISA KEV dateAdded **2026-08-24**；联邦缓解期限 **2026-08-27**。不当访问控制 CWE-284；未认证 HTTP；CVSS 10.0。受影响 **12.2.1.4.0／14.1.1.0.0／14.1.2.0.0**（IIS 插件仅 **12.2.1.4.0**）。补丁：2026 年 1 月 CPU。狩猎：盘点互联网暴露的 OHS／WebLogic 代理插件；打 CPU；曾暴露主机按 BOD 26-04 取证分诊。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog https://www.cisa.gov/known-exploited-vulnerabilities-catalog https://nvd.nist.gov/vuln/detail/CVE-2026-21962 https://www.oracle.com/security-alerts/cpujan2026.html https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- **期限今日 · Zimbra CVE-2026-73570**：CISA KEV dateAdded **2026-08-21**；联邦缓解期限 **今日 2026-08-24**。补丁 **10.1.20+**（可选 zimbra-snmp 已安装且 SNMP 通知已启用时）。狩猎：`zimbra.log`／jetty／`/tmp`。X 本日：https://x.com/KasperskyDev/status/2092039000924336550 https://x.com/RedLegg/status/2092039438297673850 https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- **期限明日 · Windows afd.sys CVE-2026-68820**：KEV 联邦期限 **明日 2026-08-25**。本地提权。打补丁后需重启。https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- **期限已过 · TrueConf CVE-2026-72529**：联邦期限 **昨日 2026-08-23**。若未完成仍须补丁 **5.3.9／5.4.9／5.5.5**。同批 **CVE-2026-72530** 期限 **2026-09-03**。https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- **本窗口新报 · Keycloak CVE-2026-18963**（未认证账户接管）：Community 与 RHBK。补丁 **26.7.2／26.6.6／26.4.15**。临时：按 realm 关闭 Forgot password／`resetPasswordAllowed=false`。公开 nuclei 模板 PR 与 PoC 仓仅列 URL，**本报不转载利用**。**未入 KEV**。IoC：未见公开 IoC。https://x.com/pdnuclei_bot/status/2092039299172888893 https://www.keycloak.org/2026/08/keycloak-2672-released https://nvd.nist.gov/vuln/detail/CVE-2026-18963
- **本窗口新报 · Calix GS7 XGS CVE-2026-75501**：EXOS through **6.6.47**；WAN **TCP/5000** MiniUPnPd 缺认证，可改 NAT／端口转发。CERT/CC VU#756733。覆盖范围内**未见厂商补丁**。缓解：关闭 UPnP（高级 → 安全 → UPnP）或联系 ISP；过滤入站 TCP/5000。不抄 SOAP。**未入 KEV**。二手覆盖未见确认在野。IoC：未见公开 IoC。https://x.com/TweetThreatNews/status/2092035578128695405 https://kb.cert.org/vuls/id/756733 https://nvd.nist.gov/vuln/detail/CVE-2026-75501
- **续报 · GitLab CVE-2026-19478**：日文续报探测。**仍未入 KEV**（catalogVersion 2026.08.24／1675 复核确认缺席）。补丁 **18.11.11／19.0.8／19.1.6／19.2.4**。狩猎：`@gl_introduced`。https://x.com/securityLab_jp/status/2092039538411749835 https://rocket-boys.co.jp/security-measures-lab/gitlab-critical-cve-2026-19478-exploit-attempts/ https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- **Entra ID CVE-2026-69836（走回仍有效）**：X 本日亦记撤回「在野」口径。沿用已核验走回。云侧已缓解，客户无需打补丁。**未入 KEV**。https://x.com/Syynya/status/2092037782529282513 https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- **晚间备援后到 · miniOrange SAML SSO WordPress CVE-2026-61979／CVE-2026-15981**：利用尝试。Patchstack 8/21；DigitalOcean 探测 8/16；BC 8/24。一 slug 七版本。补丁：Free **5.4.5**；Premium **13.0.4**；Standard **17.0.6**；Premium/Enterprise/All-Inclusive 多站点 **20.2.8**；Enterprise/All-Inclusive 单站点 **26.0.3**；VIP 单站点 **32.0.8**；VIP 多站点 **35.0.7**。狩猎：预期范围外的 WP 管理员会话；付费版常无仪表盘提示（须手动上传）。**未入 KEV**。扫描 IP 见 IoC。https://www.bleepingcomputer.com/news/security/hackers-target-wordpress-sites-in-miniorange-auth-bypass-attacks/ https://patchstack.com/articles/one-slug-seven-editions-the-miniorange-saml-sso-bug-that-let-anyone-log-in-as-your-wordpress-admin/ https://nvd.nist.gov/vuln/detail/CVE-2026-61979 https://nvd.nist.gov/vuln/detail/CVE-2026-15981 https://github.com/advisories/ghsa-p92r-62jh-8r5w
- **晚间备援后到 · rConfig CVE-2026-77915**：NVD 9.8。未认证 `POST /register` 可自注册管理员。GHSA 称补丁 **8.2.10**；NVD 文称 **8.2.13 之前**——版本口径不一致，照录不裁定。狩猎：意外 Admin 用户；补丁前在反向代理阻断 `/register`。**未入 KEV**。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-77915 https://github.com/rconfig/rconfig/security/advisories/GHSA-w3hx-9cxg-5ccr
- **晚间备援后到 · DrayTek DSA-2026-003 VigorSwitch CVE-2026-71915–71943**：突出 NVD **CVE-2026-71921** 9.8。厂商称发布时未见已知可行路径、可行路径或需管理员；NVD CNA 对 71921 写预认证。两者照录，不抄 CGI。固件见 CVE 节。**未入 KEV**。https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/ https://nvd.nist.gov/vuln/detail/CVE-2026-71921
- **晚间备援后到 · ipTIME T24000M CVE-2026-78168／Netis NC63 CVE-2026-76071**（NVD CRITICAL；中等置信）：未见已核验厂商补丁 URL。不复述利用。隔离管理 HTTP。**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-78168 https://nvd.nist.gov/vuln/detail/CVE-2026-76071
- **晚间备援后到 · Xinference CVE-2026-76841／nektos/act CVE-2026-76847**：Xinference 补丁 **2.12.0**。**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-76841 https://nvd.nist.gov/vuln/detail/CVE-2026-76847 https://github.com/xorbitsai/inference/issues/5023 https://github.com/xorbitsai/inference/pull/5027
- **晚间备援后到 · ReliaQuest 失败式 vishing／假 SSO**：设备信任阻断后续应用；仅只读 Okta；声称无客户数据。域名 IoC：`reliaquest.claims`。狩猎：`.claims` 仿冒 SSO；意外 MFA；点名真实员工的语音钓鱼。不把受害品牌本身当攻击者 IoC。https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/
- **工具**：nuclei-templates **v10.4.8**（**2026-08-24T13:01:50Z**，112 新模板／101 CVE；项目 vKEV 标签**不是** CISA KEV）。Keycloak nuclei 模板 PR **16995** 仍为本窗口 X 侧主要工具项。本日无显著 C2 新版本（GitHub API 限流，未独立核验引擎／C2 新版本）。https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8 https://github.com/projectdiscovery/nuclei-templates/pull/16995
- **威胁报告（非恶意软件）· Cloudflare 2026 上半年 DDoS**：https://x.com/ptdbugs/status/2091995943214174685 https://blog.cloudflare.com/ddos-threat-report-2026-h1/
- **续报／仍有效（短）**：Elementor Pro **4.2.2**、SPIP **4.4.21**、crates.io 钉死、ToxicPanda 2.0、llama.cpp **CVE-2026-78147** 与同伴 **CVE-2026-78148**（NVD MEDIUM 5.3）——仍开放，不重写昨日全文。Socket 8/24 Open VSX ID 回收为清理，不是新恶意软件浪潮。https://nvd.nist.gov/vuln/detail/CVE-2026-78148 https://socket.dev/blog/open-vsx-unblocks-malicious-extension-ids
- **未独立核验**：Dark Project 勒索声称；Akira／Qilin 等勒索广告；Go SSH 不完整修复声称；DailyDarkWeb 声称约 2.4 万主机与 **CVE-2026-65400** 相关（该 CVE 为较旧 KEV，短提醒；**不把主机清单当 IoC**）。

## CVE / POC / 漏洞

### 1. 【KEV 本日新增】Oracle HTTP Server / WebLogic Server Proxy Plug-in CVE-2026-21962（dateAdded 2026-08-24；联邦期限 2026-08-27）

晚间备援后到。CISA 警报 **2026-08-24** 将本条列入 KEV；catalogVersion **2026.08.24**／count **1675** 中本日 `dateAdded` 仅此一条。不当访问控制（CWE-284），Oracle Fusion Middleware 组件：Apache HTTP Server 与 IIS 的 WebLogic Server Proxy Plug-in。未认证攻击者具备 HTTP 网络访问即可。CVSS 3.1 **10.0**。受支持受影响版本：**12.2.1.4.0**、**14.1.1.0.0**、**14.1.2.0.0**；厂商注明 IIS 插件仅 **12.2.1.4.0** 受影响。补丁：**2026 年 1 月 Critical Patch Update**。联邦缓解期限 **2026-08-27**（用 KEV `dueDate`，不用变更历史元数据日期）。`knownRansomwareCampaignUse` Unknown。NVD 上 CISA SSVC 利用状态于 **2026-08-24T18:44:03.980351Z** 由 none 翻为 active。狩猎：盘点互联网暴露、仍跑上述版本的 OHS／WebLogic 代理插件；立即打 CPU；曾暴露主机按 **BOD 26-04** 取证分诊。不转写请求样例或 PoC；不链 PoC 仓。

地址：
- CISA 警报（2026-08-24，新增一条）：https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- KEV JSON 源：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- 厂商 2026 年 1 月 CPU：https://www.oracle.com/security-alerts/cpujan2026.html
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 2. 【期限今日】Zimbra Collaboration Suite CVE-2026-73570（KEV dateAdded 2026-08-21；联邦期限今日）

已见 8/21–8/23。CISA 警报与 KEV dateAdded 均为 **2026-08-21**；联邦缓解期限 **今日 2026-08-24**。影响 Zimbra Collaboration **10.1.20 之前**，在可选 **zimbra-snmp** 已安装且 SNMP 通知已启用时，特制 SMTP 可导致以 zimbra 用户执行操作系统命令。补丁：**10.1.20+**。狩猎：`/var/log/zimbra.log` 中意外 Service status change；检查 jetty webapps 与 `/tmp/` 下近期由 zimbra 用户拥有的文件。只记路径，不写利用。晚间备援复核：本条仍在 KEV；本日新加入目的是上一节 Oracle **CVE-2026-21962**，不是本条重加。

地址：
- X（@KasperskyDev，本日）：https://x.com/KasperskyDev/status/2092039000924336550
- X（@RedLegg，本日）：https://x.com/RedLegg/status/2092039438297673850
- X（@BotBauR，本日）：https://x.com/BotBauR/status/2092034972714496024
- CISA 警报（2026-08-21）：https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- 厂商：https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- CERT Polska：https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/

IoC：未见公开 IoC。

### 3. 【期限明日】Windows afd.sys CVE-2026-68820（CISA 期限 2026-08-25）

KEV 自 **2026-08-11**（八月 Patch Tuesday）。本地提权，释放后使用（UAF），组件 **afd.sys**。联邦期限 **明日 2026-08-25**。处置：按 MSRC 安装对应安全更新；**补丁后需重启**。仅高阶，不写利用原语。晚间备援复核：本条仍在 KEV；本日新 KEV 为 Oracle **CVE-2026-21962**。

地址：
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- Qualys（BOD 26-04 要求综述）：https://blog.qualys.com/product-tech/2026/08/18/cve-2026-68820-kev-bod-26-04-requirements
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 4. 【期限已过／仍须补丁】TrueConf Server CVE-2026-72529／CVE-2026-72530（72529 联邦期限昨日）

已见 8/20–8/23。CISA **2026-08-20** 将两条列入 KEV。**CVE-2026-72529** 联邦期限为 **昨日 2026-08-23**——若尚未完成，仍须立即打补丁。**CVE-2026-72530**（代码注入／隔离环境逃逸）期限 **2026-09-03**。未授权远程攻击者在可访问 **TCP/4307** 时可影响 TrueConf Server。补丁：**5.3.9**、**5.4.9** 或 **5.5.5**。狩猎：盘点暴露的 4307/TCP；曾暴露主机按可能已被预入侵处置。不写战役剧本或链式步骤。

地址：
- CISA 警报（2026-08-20，新增两条）：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD CVE-2026-72529：https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- NVD CVE-2026-72530：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- Kaspersky ICS CERT：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- 文章（BleepingComputer 2026-08-21）：https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-actively-exploited-trueconf-server-flaws/

IoC：未见公开 IoC。

### 5. 【本窗口新报】Keycloak CVE-2026-18963（未认证账户接管；Community + RHBK；未入 KEV）

X（@pdnuclei_bot／@DhiyaneshDK／@red_darkin／@mergenewsapp）。未认证攻击者可经 **reset-credentials** 流程接管账户（跳过邮箱验证）。影响 Keycloak Community 与 Red Hat Build of Keycloak（RHBK）。**不描述状态机绕过，不写重置凭据走流程。**

补丁：**26.7.2**／**26.6.6**／**26.4.15**。厂商发布页：Keycloak **26.7.2**。临时缓解：按 realm 关闭 Forgot password，或设 `resetPasswordAllowed=false`。

公开存在 nuclei 检测模板（PR **16995**／ProjectDiscovery 云库）以及 PoC 仓库——**只列 URL，本报不转载利用**。晚间备援复核：**仍未入 KEV**。

地址：
- X（@pdnuclei_bot）：https://x.com/pdnuclei_bot/status/2092039299172888893
- X（@DhiyaneshDK）：https://x.com/DhiyaneshDK/status/2092010596980150359
- X（@red_darkin）：https://x.com/red_darkin/status/2092036386836672513
- X（@mergenewsapp）：https://x.com/mergenewsapp/status/2092040614036582581
- 厂商 26.7.2：https://www.keycloak.org/2026/08/keycloak-2672-released
- GitHub issue 51833：https://github.com/keycloak/keycloak/issues/51833
- Red Hat CVE：https://access.redhat.com/security/cve/cve-2026-18963
- 发布标签 26.7.2：https://github.com/keycloak/keycloak/releases/tag/26.7.2
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-18963
- ProjectDiscovery 云库：https://cloud.projectdiscovery.io/library/CVE-2026-18963
- nuclei-templates PR 16995：https://github.com/projectdiscovery/nuclei-templates/pull/16995
- PoC 仓（不转载）：https://github.com/Red-Darkin/CVE-2026-18963-keycloak

IoC：未见公开 IoC。

### 6. 【本窗口新报】Calix GS7 XGS（GS5239XG）CVE-2026-75501（CERT/CC VU#756733；未见厂商补丁；未入 KEV）

X（@TweetThreatNews／@aviatrixtrc）。产品 **Calix GS7 XGS（GS5239XG）**，EXOS **through 6.6.47**。WAN 侧 **TCP/5000** 上的 MiniUPnPd **缺认证**，远程攻击者可增加 NAT／端口转发，从而暴露内网设备。CERT/CC **VU#756733**。本窗口覆盖范围内**未见厂商补丁**。缓解：关闭 UPnP（高级 → 安全 → UPnP）或联系 ISP；过滤入站 **TCP/5000**。**不抄 SOAP、不写端口映射请求体。**

X 有在野声称；**二手覆盖（BleepingComputer／CERT）未见确认在野利用**。晚间备援复核：**未入 KEV**。

地址：
- X（@TweetThreatNews）：https://x.com/TweetThreatNews/status/2092035578128695405
- X（@aviatrixtrc）：https://x.com/aviatrixtrc/status/2092038578222022829
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-75501
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-75501
- CERT/CC VU#756733：https://kb.cert.org/vuls/id/756733
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/unpatched-calix-flaw-lets-hackers-bypass-nat-to-expose-internal-devices/
- 研究页：https://drkq.github.io/security-research/calix-vu756733/

IoC：未见公开 IoC。

### 7. 【续报】GitLab GraphQL CVE-2026-19478（日文探测续报；仍未入 KEV）

已见 8/22–8/23。X 本日 @securityLab_jp 链日文续报：披露后即见探测尝试。影响为**数据完整性，不是已确认 RCE**。补丁：**18.11.11／19.0.8／19.1.6／19.2.4**。晚间备援复核：**仍未入 KEV**（catalogVersion 2026.08.24／1675 确认缺席）。狩猎：日志 `@gl_introduced`；限制未认证 `/api/graphql`。不写 GraphQL 查询体。搜索2 窗口外可见 8/19 nuclei 检测仓，见工具节。

地址：
- X（@securityLab_jp）：https://x.com/securityLab_jp/status/2092039538411749835
- 日文续报：https://rocket-boys.co.jp/security-measures-lab/gitlab-critical-cve-2026-19478-exploit-attempts/
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- SecurityWeek（既有）：https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/
- GHSA：https://github.com/advisories/GHSA-6whr-xjjm-6pf8

IoC：未见公开 IoC。

### 8. 【走回仍有效】Microsoft Entra ID CVE-2026-69836（云侧已缓解；X 本日亦记撤回）

X 本日 @Syynya 日文续报：微软已修复 CVSS 10.0 的 Entra ID **CVE-2026-69836**，并**更正**此前「在野利用」表述；属云侧、非本地部署。**沿用 8/22 已核验走回**：BleepingComputer **2026-08-22 02:56 EDT** 称微软曾**误标为已利用**；Cybersecurity Dive：周五更新称**无利用**。托管云服务已缓解，**客户无需打补丁、无客户侧补丁包**。**未入 KEV**。防御：审阅 Entra 登录与特权角色日志。

地址：
- X（@Syynya）：https://x.com/Syynya/status/2092037782529282513
- 日文续报：https://rocket-boys.co.jp/security-measures-lab/microsoft-entra-id-cve-2026-69836-exploit-correction/
- 文章（BleepingComputer，走回已核验）：https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- 文章（Cybersecurity Dive）：https://www.cybersecuritydive.com/news/microsoft-maximum-severity-flaw-entra-id-exploitation/828501/
- 厂商 MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-69836

IoC：未见公开 IoC。

### 9. 【晚间备援后到】miniOrange SAML SSO WordPress CVE-2026-61979／CVE-2026-15981（利用尝试；未入 KEV）

BleepingComputer **2026-08-24**；Patchstack 文 **2026-08-21**；DigitalOcean 探测 **2026-08-16**。miniOrange SAML 2.0 Single Sign On：**一个 WordPress slug、七个独立版本线**，未认证认证绕过。公开咨询最初只覆盖免费版；付费版已打补丁但无公开变更日志，仪表盘／数据库常显示未受影响。DigitalOcean 称 8/16 拦截到来自可信网络外的管理员会话（Standard 16.1.9）。Patchstack：来自六个 IP 的机会性扫描。

补丁：Free **5.4.5**；Premium **13.0.4**；Standard **17.0.6**；Premium／Enterprise／All-Inclusive 多站点 **20.2.8**；Enterprise／All-Inclusive 单站点 **26.0.3**；VIP 单站点 **32.0.8**；VIP 多站点 **35.0.7**。狩猎：预期范围外的 WordPress 管理员会话；付费版常无仪表盘更新提示，须**手动上传**。**未入 KEV**。不写 SAML 请求体、不转载利用。CVE-2026-15981 NVD 页已独立核验存在，仅列 URL。

地址：
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/hackers-target-wordpress-sites-in-miniorange-auth-bypass-attacks/
- Patchstack：https://patchstack.com/articles/one-slug-seven-editions-the-miniorange-saml-sso-bug-that-let-anyone-log-in-as-your-wordpress-admin/
- NVD CVE-2026-61979：https://nvd.nist.gov/vuln/detail/CVE-2026-61979
- NVD CVE-2026-15981：https://nvd.nist.gov/vuln/detail/CVE-2026-15981
- GHSA：https://github.com/advisories/ghsa-p92r-62jh-8r5w

IoC（扫描 IP，照录）：207.211.214.41, 79.127.224.14, 102.91.71.83, 162.243.116.148, 84.201.6.54, 64.225.25.188

### 10. 【晚间备援后到】rConfig CVE-2026-77915（未认证管理员自注册；未入 KEV）

NVD published **2026-08-24**；CRITICAL **9.8**。未认证调用者可经 `POST /register` 自注册 Administrator 账户。GHSA-w3hx-9cxg-5ccr（**2026-08-10**）称受影响 **≥8.0.0 <8.2.10**、补丁 **8.2.10**，并注明升级**不会改写**已存在的恶意 Admin 行。NVD 文称 **8.2.13 之前**。**版本口径不一致，照录，不裁定谁对。** 狩猎：意外 Admin 用户；打补丁前在反向代理阻断 `/register`；若曾出现恶意管理员则轮换设备凭据。**未入 KEV**。不写注册请求体。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-77915
- GHSA：https://github.com/rconfig/rconfig/security/advisories/GHSA-w3hx-9cxg-5ccr

IoC：未见公开 IoC。

### 11. 【晚间备援后到】DrayTek DSA-2026-003 VigorSwitch CVE-2026-71915–71943（突出 CVE-2026-71921；未入 KEV）

厂商 DSA-2026-003（**2026-08-24**）列出 **CVE-2026-71915** 至 **CVE-2026-71943**。厂商称发布时**未见已知可行利用路径**，且可行路径**或需** Web UI 有效管理员凭据；仍发布固件。NVD CNA 对 **CVE-2026-71921**（CVSS **9.8**）独立描述为预认证。**两者照录，不裁定；不抄 CGI／参数样例。**

固定固件（厂商表）：G2540xs／P2540xs **3.9.10**；FX2120 **3.9.10**；G2282x／P2282x **2.10.6**；Q2300x／PQ2300xb **2.10.7**；G2542x／P2542x／P2542xh **3.10.6**；若干型号 **2.9.10**（以厂商表为准）。狩猎：隔离交换机管理面；盘点上列型号并升级。**未入 KEV**。

地址：
- 厂商公告：https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/
- NVD CVE-2026-71921：https://nvd.nist.gov/vuln/detail/CVE-2026-71921

IoC：未见公开 IoC。

### 12. 【晚间备援后到 · 短】ipTIME T24000M CVE-2026-78168／Netis NC63 CVE-2026-76071（NVD CRITICAL；中等置信；未入 KEV）

NVD 两条均为 CRITICAL。**未见已核验的厂商补丁 URL**。不复述利用、不链声称 PoC。狩猎：隔离设备管理 HTTP；盘点对应固件字符串。**未入 KEV**。置信：**中等**。

地址：
- NVD CVE-2026-78168：https://nvd.nist.gov/vuln/detail/CVE-2026-78168
- NVD CVE-2026-76071：https://nvd.nist.gov/vuln/detail/CVE-2026-76071

IoC：未见公开 IoC。

### 13. 【晚间备援后到 · 短】Xinference CVE-2026-76841／nektos/act CVE-2026-76847（未入 KEV）

Xinference **2.12.0 之前** 加载 Hugging Face 模型时无条件启用远程代码（`trust_remote_code`）；补丁 **2.12.0**。nektos/act Artifacts V4 控制面在使用 upload／download-artifact@v4 时缺授权。狩猎：不要把 Xinference 模型加载器或 act artifact 后端暴露到不可信网络；升级。**未入 KEV**。

地址：
- NVD CVE-2026-76841：https://nvd.nist.gov/vuln/detail/CVE-2026-76841
- NVD CVE-2026-76847：https://nvd.nist.gov/vuln/detail/CVE-2026-76847
- GitHub issue 5023：https://github.com/xorbitsai/inference/issues/5023
- GitHub PR 5027：https://github.com/xorbitsai/inference/pull/5027

IoC：未见公开 IoC。

### 14. 【续报／仍有效 · 短】Elementor／SPIP／crates.io／llama.cpp（含晚间备援同伴 CVE-2026-78148）

下列昨日已展开，本窗口无新厂商主文；**仍开放／仍有效**，不重写全文。llama.cpp **CVE-2026-78148** 为晚间备援后到、与既有 **CVE-2026-78147** 同狩猎口径。

- **Elementor Pro CVE-2026-32475**：补丁 **4.2.2**。狩猎：`wp-content/uploads/elementor/forms/` 下意外 PHP。不描述绕过。https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/ https://www.cve.org/CVERecord?id=CVE-2026-32475
- **SPIP CVE-2026-77806**：补丁 **4.4.21**。厂商／CVE 称利用尝试或 8 月在野；**未入 KEV**。狩猎：只查意外 **X-Spip-Filtre** 请求头（只记头名）。https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- **crates.io arrayref／internment／append-only-vec ＋ proc-macro1**（CVE-2026-77651／77649／77650）：钉死 **0.3.9／0.8.6／0.1.8**。本窗口无新哈希。https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- **llama.cpp ggml-RPC CVE-2026-78147**：昨日晚间备援已核验。防御：不要把 llama.cpp RPC 暴露到不可信网络。**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-78147
- **llama.cpp ggml-RPC CVE-2026-78148**（晚间备援后到）：NVD MEDIUM **5.3**。GitHub issue **25299**／PR **25670**。同狩猎：不要把 RPC 暴露到不可信网络。**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-78148 https://github.com/ggml-org/llama.cpp/issues/25299 https://github.com/ggml-org/llama.cpp/pull/25670

IoC：未见本窗口新增公开 IoC（crates.io 既有指标见 8/22 晚报）。

## 工具与 GitHub 发布

### 1. 【晚间备援后到】nuclei-templates v10.4.8（2026-08-24T13:01:50Z）

projectdiscovery/nuclei-templates **v10.4.8** 于 **2026-08-24T13:01:50Z** 发布：112 个新模板、101 个 CVE 增量。含项目自标 **vKEV** 的 GitLab CVE-2026-19478 模板——**该标签不是 CISA KEV 列入**。定位为防御性扫描包。**未克隆模板、不转载 payload。** 原 20:00 晚报称未见已核验新版本标签，本条为晚间备援更正。

地址：
- 发布标签 v10.4.8：https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- 发布页：https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。

### 2. 【本窗口主要工具项】nuclei-templates PR 16995（Keycloak CVE-2026-18963 检测模板）

X（@pdnuclei_bot／@DhiyaneshDK／@buswe_com）。ProjectDiscovery 为 **CVE-2026-18963** 发布／提交 nuclei 检测模板（PR **16995**，云库已列）。定位为**防御性检测**，用于盘点仍开放重置口令且未打补丁的 Keycloak。**未克隆模板、不转载请求样例或 PoC。**

地址：
- X（@pdnuclei_bot）：https://x.com/pdnuclei_bot/status/2092039299172888893
- X（@DhiyaneshDK）：https://x.com/DhiyaneshDK/status/2092010596980150359
- X（@buswe_com）：https://x.com/buswe_com/status/2092036527551308180
- 云库：https://cloud.projectdiscovery.io/library/CVE-2026-18963
- PR 16995：https://github.com/projectdiscovery/nuclei-templates/pull/16995
- nuclei-templates 发布页：https://github.com/projectdiscovery/nuclei-templates/releases
- 发布标签 v10.4.8：https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

### 3. 【窗口边缘／可选】Tencent AI-Infra-Guard（仅 X URL）

X（@so_sthbryan，**2026-08-24T00:58Z**，处窗口边缘）。称腾讯开源 AI-Infra-Guard：面向 agent／MCP／skills 扫描、LLM jailbreak 评估与 AI 基础设施攻击面。推文未见展开的 GitHub URL（t.co 未解析），**不编造仓库地址**。**未克隆**。不写攻击 payload。

地址：
- X（@so_sthbryan）：https://x.com/so_sthbryan/status/2091691458827112655

IoC：未见公开 IoC。

### 4. nuclei／C2／红队框架版本

本窗口 Search2 量少。**本日无显著 C2 新版本**（GitHub API 限流，未见已独立核验的 Sliver／Havoc／Mythic 新版本）。nuclei-templates 本窗口已核验版本标签为上述 **v10.4.8**；X 侧主要新项仍为 PR 16995。搜索2 回溯至 8/16 时见窗口外 @Renzi25031469（**2026-08-19**）GitLab CVE-2026-19478 nuclei 检测仓，不当作本窗口新发布。C2 关键词另命中非安全交易仓，跳过。

地址：
- 窗口外 GitLab 检测仓（8/19，仅上下文）：https://x.com/Renzi25031469/status/2089963489649361031 https://github.com/renzi25031469/CVE-2026-19478
- nuclei 仓：https://github.com/projectdiscovery/nuclei
- nuclei-templates 发布页：https://github.com/projectdiscovery/nuclei-templates/releases
- 发布标签 v10.4.8：https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. 【晚间备援后到】ReliaQuest 确认失败的 vishing／假 SSO（设备信任阻断；声称无客户数据）

BleepingComputer **2026-08-24**。ReliaQuest：攻击者致电员工、冒充安全团队成员，在仿冒域名上托管假 SSO（文章来源：`reliaquest.claims`），模式与 ReliaQuest 自身曾报告的 ShinyHunters `company.claims` 帮助台仿冒一致。一名员工提交凭据并批准 MFA；攻击者获得临时**只读**身份仪表盘访问。**设备信任**阻断了后续应用访问。ReliaQuest 称：无客户数据、无持久化；会话已终止、密码已吊销、令牌已重置。狩猎：`.claims` 仿冒 SSO 域名；意外 MFA 推送；点名真实员工的语音钓鱼。**不把受害品牌本身当作攻击者 IoC**（超出该仿冒域名模式之外）。

地址：
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/

IoC：reliaquest.claims

### 2. 【本窗口】Cloudflare 2026 上半年 DDoS 威胁报告（文章，非恶意软件）

X（@ptdbugs）链 Cloudflare **2026 H1 DDoS Threat Report**。高阶摘要（照录推文／二手口径，不编造具体 Tbps 数字）：攻击体量创新高、单次更短、放大攻击回潮。这是运营商威胁报告，**不是恶意软件分析**。无样本、无 C2。

地址：
- X（@ptdbugs）：https://x.com/ptdbugs/status/2091995943214174685
- Cloudflare 博文：https://blog.cloudflare.com/ddos-threat-report-2026-h1/

IoC：未见公开 IoC。

### 3. 【续报／仍有效 · 短】ToxicPanda 2.0 Android 银行木马

昨日晚间备援已报。BleepingComputer **2026-08-23**／Zimperium **2026-08-19**。高阶：VPN 权限阻断 Play／Play Protect；无障碍；Wireless Debugging／ADB。狩猎：异常 VPN／无障碍／无线调试。Zimperium 声称 IoC 见 https://github.com/Zimperium/IOC —— **未见本轮抄录的公开哈希**。本窗口无新主文。

地址：
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/
- Zimperium 资源页：https://zimperium.com/resources/zimperium-zlabs-uncovers-toxicpanda-2.0-a-significantly-more-powerful-android-banking-trojan

IoC：未见本轮抄录的公开哈希。

### 4. 【晚间备援后到 · 可选／短】Socket 8/24 Open VSX 扩展 ID 回收（清理，不是新浪潮）

Socket **2026-08-24**：Open VSX 解除／回收被滥用的恶意扩展 ID。定位为供应链清理跟进，**不是新的恶意软件浪潮**。本窗口未见新的 crates.io 注册表条目。对照既有 rust-lang.org 8/20 文。

地址：
- Socket：https://socket.dev/blog/open-vsx-unblocks-malicious-extension-ids
- crates.io 对照（8/20）：https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/

IoC：未见本窗口新增公开 IoC。

### 未独立核验（勒索／泄密广告／单源声称；仅 X URL）

下列仅为 X 广告或单源声称，**未独立核验**。**不把受害站点或主机清单当作 IoC。** 未见公开攻击者 IoC。

- Dark Project 勒索／数据勒索（DailyDarkWeb 称 2026-08-05 首见、首批受害者声称偏多）：https://x.com/DailyDarkWeb/status/2092011850590310766
- Akira 声称英国油气 Boustead International Heaters：https://x.com/FalconFeedsio/status/2091968990474346626
- Qilin 声称玻利维亚保险公司 CONSEGSA：https://x.com/FalconFeedsio/status/2092031362740199784
- SAFEPAY 声称意大利海鲜分销 La Ge Gè Pesca：https://x.com/FalconFeedsio/status/2091987254315245625
- PANZER 声称塞尔维亚伏伊伏丁那省政府：https://x.com/FalconFeedsio/status/2091931049203053006
- Go SSH 授权绕过声称（称对非 publickey 回调跳过 source-address 校验，为 **CVE-2024-45337** 不完整修复；**无本轮已核新 CVE 编号**）：https://x.com/tsumikasanedev/status/2092039194063643063
- DailyDarkWeb 声称约 **2.4 万** 台主机与 **CVE-2026-65400**（较旧 KEV；JSON 摘要为 macOS Screen Sharing 认证绕过）相关——**短提醒：若未打该旧 KEV 仍须补丁；不把主机清单当 IoC**：https://x.com/DailyDarkWeb/status/2092018649842491525 https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- 论坛声称 WordPress 插件 0-day 源码：https://x.com/DailyDarkWeb/status/2091926061072216505
- 其他泄密／失陷声称（Bitcoin IRA／iTrustCapital、波尔多大学、Hrvatski Telekom、Cyprus Airways、巴西库 pl4t0v、BDJobs、STC TV、Banque Alimentaire du Bas-Rhin）：https://x.com/iiam_Akshay/status/2091940660551274885 https://x.com/DailyDarkWeb/status/2092016947328090422 https://x.com/DailyDarkWeb/status/2092007753938014475 https://x.com/CyberPulse56/status/2091918144399163598 https://x.com/VECERTRadar/status/2091949216071561288 https://x.com/DailyDarkWeb/status/2092009794949505284 https://x.com/DailyDarkWeb/status/2092025533487775951 https://x.com/DarkWebInformer/status/2092009401553183205

IoC：未见公开攻击者 IoC。

## 地址／IoC 汇总

### 本窗口新报／晚间备援后到
- miniOrange SAML SSO 扫描 IP（照录）：207.211.214.41, 79.127.224.14, 102.91.71.83, 162.243.116.148, 84.201.6.54, 64.225.25.188
- ReliaQuest 仿冒 SSO 域名（照录）：reliaquest.claims —— 不把受害品牌本身当攻击者 IoC
- Oracle CVE-2026-21962／Zimbra／afd.sys／TrueConf／Keycloak／Calix／GitLab／Entra／rConfig／DrayTek／ipTIME／Netis／Xinference／act／llama.cpp：未见公开 IoC（不把 PoC 仓、nuclei 模板、受害站点或声称主机清单当 IoC）
- Cloudflare DDoS 报告：未见公开 IoC

### 续报（本窗口无新哈希）
- ToxicPanda 2.0：Zimperium 声称 IoC 仓未在本轮抄录 —— **未见本轮抄录的公开哈希**
- llama.cpp CVE-2026-78147／CVE-2026-78148／Elementor／SPIP：未见公开 IoC
- crates.io 既有指标：见 2026-08-22 晚报，本窗口不重抄
- CVE-2026-65400：较旧 KEV；**不把约 2.4 万主机清单当 IoC**
- Socket Open VSX：清理跟进，未见本窗口新增攻击者 IoC

### 参考 URL（情报页，非恶意基础设施）
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- https://www.oracle.com/security-alerts/cpujan2026.html
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- https://www.keycloak.org/2026/08/keycloak-2672-released
- https://nvd.nist.gov/vuln/detail/CVE-2026-18963
- https://github.com/keycloak/keycloak/issues/51833
- https://access.redhat.com/security/cve/cve-2026-18963
- https://github.com/keycloak/keycloak/releases/tag/26.7.2
- https://cloud.projectdiscovery.io/library/CVE-2026-18963
- https://github.com/projectdiscovery/nuclei-templates/pull/16995
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/Red-Darkin/CVE-2026-18963-keycloak
- https://www.cve.org/CVERecord?id=CVE-2026-75501
- https://nvd.nist.gov/vuln/detail/CVE-2026-75501
- https://kb.cert.org/vuls/id/756733
- https://www.bleepingcomputer.com/news/security/unpatched-calix-flaw-lets-hackers-bypass-nat-to-expose-internal-devices/
- https://drkq.github.io/security-research/calix-vu756733/
- https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- https://rocket-boys.co.jp/security-measures-lab/gitlab-critical-cve-2026-19478-exploit-attempts/
- https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/
- https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- https://rocket-boys.co.jp/security-measures-lab/microsoft-entra-id-cve-2026-69836-exploit-correction/
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- https://www.bleepingcomputer.com/news/security/hackers-target-wordpress-sites-in-miniorange-auth-bypass-attacks/
- https://patchstack.com/articles/one-slug-seven-editions-the-miniorange-saml-sso-bug-that-let-anyone-log-in-as-your-wordpress-admin/
- https://nvd.nist.gov/vuln/detail/CVE-2026-61979
- https://nvd.nist.gov/vuln/detail/CVE-2026-15981
- https://github.com/advisories/ghsa-p92r-62jh-8r5w
- https://nvd.nist.gov/vuln/detail/CVE-2026-77915
- https://github.com/rconfig/rconfig/security/advisories/GHSA-w3hx-9cxg-5ccr
- https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/
- https://nvd.nist.gov/vuln/detail/CVE-2026-71921
- https://nvd.nist.gov/vuln/detail/CVE-2026-78168
- https://nvd.nist.gov/vuln/detail/CVE-2026-76071
- https://nvd.nist.gov/vuln/detail/CVE-2026-76841
- https://nvd.nist.gov/vuln/detail/CVE-2026-76847
- https://github.com/xorbitsai/inference/issues/5023
- https://github.com/xorbitsai/inference/pull/5027
- https://nvd.nist.gov/vuln/detail/CVE-2026-78148
- https://github.com/ggml-org/llama.cpp/issues/25299
- https://github.com/ggml-org/llama.cpp/pull/25670
- https://www.bleepingcomputer.com/news/security/reliaquest-confirms-failed-data-theft-attack-after-shinyhunters-breach/
- https://socket.dev/blog/open-vsx-unblocks-malicious-extension-ids
- https://blog.cloudflare.com/ddos-threat-report-2026-h1/
- https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- https://nvd.nist.gov/vuln/detail/CVE-2026-78147
- https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
