# X 安全情报晚报 · 2026-08-26

> 搜集窗口：圣地亚哥时间 **2026-08-25 20:00 至 2026-08-26 20:05**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周三）。**
> **20:00 后 X Latest 已补录**（logged_in=true；搜索3 blocked=true）。文件 `/workspace/x-posts-2026-08-26.json`（**56** 条，collected_at **2026-08-26T20:35:00-04:00**）。搜索1 Latest 最旧可见 **2026-08-26T20:12:21Z**（约 **4 小时**，**不可当作完整 24h CVE 检索**）。搜索2 最旧可见 **2026-08-09T21:09:38Z**（窗口已覆盖，量少）。搜索3 fallback 持续 Retry／限流，**0 条**（apt 条目来自搜索1）。公开备援仍为 KEV／厂商 PRIMARY。
> 公开备援（本轮 PRIMARY）：`/workspace/security-watch-public-backup-2026-08-26.json`，**collected_at 2026-08-26T20:05:00-04:00**。CISA KEV catalogVersion **2026.08.26**／**1682** 条／dateReleased **2026-08-26T17:00:09.8976Z**。**KEV 本日新增六条**（dateAdded **2026-08-26**）：**CVE-2026-8452**、**CVE-2019-1068**、**CVE-2021-23758**、**CVE-2022-0995**、**CVE-2015-3246**、**CVE-2015-5287**。GitLab **CVE-2026-19478** 仍未入目。ICS 仍为 **ICSA-26-237-01..07**（8/26 无新 ICS）。NVD API 2.0 本轮 **HTTP 200**（昨日 503）。目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、请求样例或 PoC。

## 今日摘要

- **KEV 本日六连加**：CISA 警报 **2026-08-26** 一次列入六条（catalogVersion **2026.08.26**／**1682**）。领头两条联邦期限均为 **2026-08-29**：**Citrix NetScaler ADC／Gateway CVE-2026-8452**（CWE-119 内存越界／溢出导致 DoS，CVSS v4 **8.8**；前提 Gateway SSL VPN／ICA／CVPN／RDP Proxy **或** AAA；补丁 **14.1-72.61＋／13.1-63.18＋** 及对应 FIPS；仅客户自管，Citrix 托管云已更新）＋ **Microsoft SQL Server CVE-2019-1068**（以 Database Engine 服务账户 RCE；按 MSRC 打补丁）。其余四条联邦期限 **2026-09-09**：**Ajax.NET Professional CVE-2021-23758**（CWE-502，或已 EoL，停用或迁到受支持版本）、**Linux Kernel CVE-2022-0995**（CWE-787 本地提权／DoS）、**Red Hat Libuser CVE-2015-3246** ＋ **ABRT CVE-2015-5287**。knownRansomwareCampaignUse 均为 Unknown。狩猎：互联网暴露的 Gateway／AAA、SQL Server、嵌入 AjaxPro 的应用、未打补丁内核／libuser／ABRT；曾暴露主机按 BOD 26-04 取证分诊。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog https://support.citrix.com/external/article/CTX696604 https://nvd.nist.gov/vuln/detail/CVE-2026-8452 https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
 X：https://x.com/__kokumoto/status/2092750778654208359
- **期限明日 · Oracle HTTP Server／WebLogic Server Proxy Plug-in CVE-2026-21962**：KEV dateAdded **2026-08-24**；联邦缓解期限 **明日 2026-08-27**。CWE-284；未认证 HTTP；CVSS 10.0。补丁：**2026 年 1 月 CPU**。本日无厂商／KEV 重写。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-21962 https://www.oracle.com/security-alerts/cpujan2026.html https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- **期限后天 · Gitea CVE-2026-60004**：KEV dateAdded **2026-08-25**；联邦缓解期限 **2026-08-28**。补丁 **1.27.1**。本日无新的厂商／KEV 重写。BC Gitea 文 URL 本轮遇 Cloudflare——**不把该页当已核验正文**，仍依 CISA／KEV／GHSA。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m https://github.com/go-gitea/gitea/releases/tag/v1.27.1
 X：https://x.com/DFIR_Radar/status/2092749588880834631 https://x.com/EvanKirstel/status/2092741377700540626 https://x.com/SecAlertsCo/status/2092715814805749939
- **期限已过 · Windows afd.sys CVE-2026-68820**：KEV dateAdded **2026-08-11**；联邦缓解期限原为 **2026-08-25**，现已**过期**。本地提权（UAF）。打补丁后**需重启**。本日无 CISA 重写。IoC：未见公开 IoC。https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820 https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- **期限已过／短 · Zimbra CVE-2026-73570 ＋ TrueConf CVE-2026-72529／72530**：Zimbra 联邦期限原 **2026-08-24** 已过，补丁 **10.1.20＋**；昨日 Shadowserver 重写仍有效，本日无新重写。TrueConf **72529** 期限 **2026-08-23** 已过；**72530** 期限 **2026-09-03**；补丁 **5.3.9／5.4.9／5.5.5**。IoC：未见公开 IoC。https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/ https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
 X：https://x.com/InfosecDotWatch/status/2092733984803258674 https://x.com/reach2ratan/status/2092711233325551724
- **本窗口新报 · SharePoint 链探测 CVE-2026-55040＋CVE-2026-63520**：BleepingComputer **2026-08-26**。JWT 绕过 **CVE-2026-55040**（已于 **2026-08-18** 入 KEV，联邦期限原为 **2026-08-21**）与 BCS **CVE-2026-63520**（**截至 1682 条目未入 KEV**）被探测；Defused 蜜罐：**尚未观察到代码执行**。Shadowserver **>8700** 台互联网暴露 SharePoint＝**暴露面遥测，不是 IoC**。**不转载 PoC。** 狩猎：打 SharePoint 补丁／加固；非必要勿直接暴露互联网；复查是否已被预入侵。IoC：未见公开攻击者 IoC。https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-sharepoint-rce-chain-with-poc-exploit/
 X：https://x.com/securityLab_jp/status/2092764129417453942 https://rocket-boys.co.jp/security-measures-lab/microsoft-sharepoint-cve-2026-55040-cve-2026-63520/
- **本窗口新报 · Adobe Campaign Classic APSB26-134 CVE-2026-76195／CVE-2026-76197**：NVD CRITICAL **CVSS 10.0**，CWE-78。受影响 ACC v7 **7.4.4 build 9400 及更早**；补丁 **build 9401**。**Adobe helpx HTML 本轮超时／未拉到**——版本取自 MITRE CNA＋NVD，非渲染后的 Adobe 页面。狩猎：盘点本地 ACC，升到 **9401＋**。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-76195 https://nvd.nist.gov/vuln/detail/CVE-2026-76197 https://helpx.adobe.com/security/products/campaign/apsb26-134.html
- **本窗口新报 · ChromeOS M-151**：Chrome Releases **Wednesday, August 26, 2026**。ChromeOS／Flex Stable **16733.57.0**（Browser **151.0.7922.221**）。桌面 Chrome 152 为昨日项。渲染摘要未见在野声称。狩猎：ChromeOS 更新到 **16733.57.0＋**。IoC：未见公开 IoC。https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-chromeos_0131656799.html
- **续报 · GitLab GraphQL CVE-2026-19478 仍未入 KEV**：对照 catalogVersion **2026.08.26**／**1682** 确认缺席。补丁仍为 **18.11.11／19.0.8／19.1.6／19.2.4**。本窗口未见新的 GitLab 厂商安全发布。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-19478 https://github.com/advisories/GHSA-6whr-xjjm-6pf8
 X：https://x.com/dejital_secure/status/2092730122029891769
- **工具**：nuclei-templates **仍为 v10.4.8**。Sliver **仍为 v1.7.3**（**2026-02-24**）。**本日无显著 C2 新版本**。GitHub API 本轮限速，发布页经 **HTML 核验**。IoC：未见公开 IoC。https://github.com/projectdiscovery/nuclei-templates/releases https://github.com/BishopFox/sliver/releases
 X 后到：nuclei-templates PR **17012**（Log4j 检测模板，不转载）。https://x.com/Redpatronus/status/2092626521034736110 https://github.com/projectdiscovery/nuclei-templates/pull/17012
- **APT／恶意软件**：Kaspersky Securelist **Q2 2026** 漏洞与利用季度报告（**2026-08-26**，文章，非新家族／非新战役）。本日无新的 Unit42／Mandiant／CrowdStrike／ESET／Trend／Proofpoint 战役文。Talos／MSTIC 首页 **HTTP 403**。X 未回收推文，**不列泄露站声称**。IoC：未见公开 IoC。https://securelist.com/vulnerabilities-and-exploits-in-q2-2026/121091/
 X 后到（未独立核验／一源）：见 APT 节。https://x.com/Core_LN/status/2092755509510283423
- **续报／仍有效（短）**：Keycloak **CVE-2026-18963**、Calix **CVE-2026-75501**、miniOrange **CVE-2026-61979／CVE-2026-15981**、rConfig **CVE-2026-77915**、DrayTek DSA-2026-003、Chrome **152** 桌面（昨日）、ICS **ICSA-26-237-01..07**（昨日，索引仍最新）、Entra **CVE-2026-69836** 走回——**仍有效，不重写昨日全文**。https://www.cisa.gov/known-exploited-vulnerabilities-catalog https://www.cisa.gov/news-events/ics-advisories https://chromereleases.googleblog.com/ https://www.keycloak.org/
 Chrome 152 日文续报：https://x.com/securityLab_jp/status/2092749027775549732 https://x.com/Syynya/status/2092764132676415587

## CVE / POC / 漏洞

### 1. 【KEV 本日新增】Citrix NetScaler ADC／Gateway CVE-2026-8452（dateAdded 2026-08-26；联邦期限 2026-08-29）

晚间公开备援。CISA 警报 **2026-08-26** 将本条列入 KEV（六连加之一）；catalogVersion **2026.08.26**／count **1682**。CWE-119。KEV：不当限制内存缓冲区边界操作，可导致拒绝服务。Citrix CTX696604（初刊 **2026-06-30**）：内存溢出导致不可预测／错误行为与 DoS；**CVSS v4.0 8.8**。触发前提：已配置 **Gateway**（SSL VPN／ICA／CVPN／RDP Proxy）**或** **AAA** 虚拟服务器。

受影响（均 **BEFORE** 所列补丁）：ADC／Gateway **14.1** 于 **14.1-72.61** 之前；**13.1** 于 **13.1-63.18** 之前；FIPS **14.1** 于 **14.1-72.61 FIPS** 之前；FIPS／NDcPP **13.1** 于 **13.1-37.272** 之前。补丁：**14.1-72.61＋**、**13.1-63.18＋**、**14.1-72.61 FIPS＋**、**13.1-37.272 FIPS／NDcPP＋**。**仅客户自管实例**；Citrix 托管云侧**已更新**。knownRansomwareCampaignUse Unknown。**不转写请求样例、不链 PoC。**

狩猎：盘点互联网暴露且启用 Gateway／AAA 的 NetScaler；立即升级到上列版本；曾暴露主机按 **BOD 26-04** 取证分诊。

地址：
- CISA 警报（2026-08-26，新增六条）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- KEV JSON 源：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- Citrix CTX696604：https://support.citrix.com/external/article/CTX696604
- Citrix 备用检索：https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX696604
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 2. 【KEV 本日新增】Microsoft SQL Server CVE-2019-1068（dateAdded 2026-08-26；联邦期限 2026-08-29）

CISA 同日六连加之一。KEV：Microsoft SQL Server 远程代码执行，攻击者可以 **SQL Server Database Engine 服务账户** 上下文执行代码。按 MSRC 安全更新／厂商缓解处置；暴露资产按 BOD 26-04；曾暴露主机取证分诊。仅高阶，不写利用原语。knownRansomwareCampaignUse Unknown。

地址：
- CISA 警报（2026-08-26）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- MSRC 门户（旧指引）：https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2019-1068
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2019-1068
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 3. 【KEV 本日新增】Ajax.NET Professional CVE-2021-23758（dateAdded 2026-08-26；联邦期限 2026-09-09）

CISA 六连加之一。CWE-502。KEV：AjaxPro 反序列化不可信数据，可导致任意 .NET 类上的远程代码执行。产品**可能已 EoL／EoS**——停用或迁到受支持版本。KEV 注明为开源组件。狩猎：盘点嵌入 Ajax.NET Professional 的应用；移除／替换或按厂商缓解；BOD 26-04。不写反序列化 gadget 或请求体。

地址：
- CISA 警报（2026-08-26）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2021-23758
- 上游提交（修补参考）：https://github.com/michaelschwarz/Ajax.NET-Professional/commit/b0e63be5f0bb20dfce507cb8a1a9568f6e73de57
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 4. 【KEV 本日新增】Linux Kernel CVE-2022-0995（dateAdded 2026-08-26；联邦期限 2026-09-09）

CISA 六连加之一。CWE-787。KEV：越界写，本地用户可提权或造成 DoS。按发行版／厂商内核更新处置；BOD 26-04。仅高阶，不写利用原语。

地址：
- CISA 警报（2026-08-26）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2022-0995
- 内核提交（修补参考）：https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=93ce93587d36493f2f86921fa79921b3cba63fbb
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 5. 【KEV 本日新增】Red Hat Libuser CVE-2015-3246 ＋ ABRT CVE-2015-5287（dateAdded 2026-08-26；联邦期限均为 2026-09-09）

CISA 六连加之两条。**CVE-2015-3246**：libuser 竞态——已认证本地用户可破坏 `/etc/passwd`，造成 DoS 或提权。**CVE-2015-5287**：ABRT 经可预测名称的符号链接提权；产品**可能已 EoL／EoS**。按 Red Hat／发行版更新处置，或不支持的 ABRT 停用。BOD 26-04。不写利用步骤。

地址：
- CISA 警报（2026-08-26）：https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- Red Hat：https://access.redhat.com/articles/1537873
- NVD CVE-2015-3246：https://nvd.nist.gov/vuln/detail/CVE-2015-3246
- NVD CVE-2015-5287：https://nvd.nist.gov/vuln/detail/CVE-2015-5287
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 6. 【期限明日】Oracle HTTP Server／WebLogic Server Proxy Plug-in CVE-2026-21962（dateAdded 2026-08-24；联邦期限 2026-08-27）

仍在 KEV（2026.08.26／1682）。不当访问控制（CWE-284）。未认证攻击者具备 HTTP 网络访问即可。CVSS 3.1 **10.0**。补丁：**2026 年 1 月 Critical Patch Update**。联邦缓解期限 **明日 2026-08-27**。狩猎：盘点互联网暴露的 OHS／WebLogic 代理插件；打 CPU；曾暴露主机按 BOD 26-04 取证分诊。本日无厂商／KEV 重写。

地址：
- CISA 警报（2026-08-24）：https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- 厂商 2026 年 1 月 CPU：https://www.oracle.com/security-alerts/cpujan2026.html
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 7. 【期限后天】Gitea CVE-2026-60004（dateAdded 2026-08-25；联邦期限 2026-08-28）

仍在 KEV。CWE-94。补丁 **1.27.1**；GHSA-rcr6-4jqh-j84m。联邦缓解期限 **2026-08-28**。狩猎：盘点互联网暴露且 **<1.27.1** 的 Gitea；升级 **1.27.1＋**；关闭开放注册；曾暴露主机按 BOD 26-04 取证分诊。本日无新的厂商公告重写。BC Gitea 文 URL 本轮返回 Cloudflare 挑战——**正文未独立核验**，不把该页当信源，仍依 CISA／KEV／GHSA。不转写请求样例、不抄 hook／补丁体。

地址：
- CISA 警报（2026-08-25）：https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- GHSA：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- 厂商发布 v1.27.1：https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 8. 【期限已过】Windows afd.sys CVE-2026-68820（CISA 期限原为 2026-08-25）

仍在 KEV。dateAdded **2026-08-11**。本地提权，释放后使用（UAF），组件 **afd.sys**。联邦缓解期限原为 **2026-08-25**，现已**过期**。处置：按 MSRC 安装对应安全更新；**补丁后需重启**。仅高阶，不写利用原语。本日无 CISA 对本 CVE 的重写。

地址：
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 9. 【期限已过／仍须补丁 · 短】Zimbra CVE-2026-73570 ＋ TrueConf CVE-2026-72529／CVE-2026-72530

仍在 KEV。**Zimbra CVE-2026-73570** 联邦期限原为 **2026-08-24**（已过）；补丁 **10.1.20＋**。昨日 Help Net Security／Shadowserver 重写仍有效（**不把主机计数当 IoC**）；本日无新重写。**TrueConf CVE-2026-72529** 期限 **2026-08-23** 已过——若尚未完成，仍须立即打补丁。**CVE-2026-72530** 期限 **2026-09-03**。补丁：**5.3.9**、**5.4.9** 或 **5.5.5**。狩猎：盘点暴露的 **4307/TCP**；曾暴露主机按可能已被预入侵处置。本日无 CISA 重写。

地址：
- Help Net Security（2026-08-25，昨日重写）：https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/
- CISA 警报（2026-08-21）：https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA 警报（2026-08-20，新增两条）：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开攻击者 IoC。不把 Shadowserver 主机计数当 IoC。

### 10. 【本窗口新报】SharePoint 链探测 CVE-2026-55040 ＋ CVE-2026-63520（BC 2026-08-26）

已核验 BleepingComputer 正文（**2026-08-26 10:47 AM**；Defused 蜜罐记录 **2026-08-25**）：攻击者在探测 SharePoint JWT 认证绕过 **CVE-2026-55040**，并与 BCS **CVE-2026-63520** 链接。Defused：先行使 JWT 绕过，随后管理员枚举／BDC 探测；**尚未观察到代码执行**。**CVE-2026-55040** 已在 KEV（dateAdded **2026-08-18**，联邦期限原为 **2026-08-21**）。**CVE-2026-63520 截至 catalogVersion 2026.08.26／1682 未入 KEV**。Shadowserver 统计 **>8700** 台互联网暴露 SharePoint——**暴露面遥测，不是 IoC**。BC 另称 CISA 注明 **CVE-2026-45659** 现已见于勒索使用（按 BC 转述，**不升格为本日新 KEV**）。**本报不转载 PoC、不抄利用步骤。** 狩猎：按微软补丁／加固 SharePoint；非必要勿直接暴露到互联网；复查是否已被预入侵。

地址：
- BleepingComputer（2026-08-26）：https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-sharepoint-rce-chain-with-poc-exploit/
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开攻击者 IoC。不把 Shadowserver 暴露计数当 IoC。

### 11. 【本窗口新报】Adobe Campaign Classic APSB26-134 CVE-2026-76195／CVE-2026-76197（NVD 发布 2026-08-25；CVSS 10.0）

NVD CRITICAL **10.0**，CWE-78 操作系统命令注入；无需用户交互、权限无。NVD 发布时间 **2026-08-25T18:18:04Z／18:18:05Z**。MITRE CNA：受影响 **ACC v7 7.4.4 build 9400 及更早**；不受影响 **ACC v7 7.4.4 build 9401**。公告号 **APSB26-134**。**helpx.adobe.com APSB 页本轮拉取失败／超时**——版本取自 MITRE CVE CNA＋NVD 描述，**非**渲染后的 Adobe HTML。NVD 正文未见在野声称。狩猎：盘点本地部署 ACC；升级到 **build 9401＋**；限制暴露面。

地址：
- NVD CVE-2026-76195：https://nvd.nist.gov/vuln/detail/CVE-2026-76195
- NVD CVE-2026-76197：https://nvd.nist.gov/vuln/detail/CVE-2026-76197
- Adobe APSB26-134（本轮 HTML 未拉到，仅列尝试）：https://helpx.adobe.com/security/products/campaign/apsb26-134.html
- MITRE CNA：https://cveawg.mitre.org/api/cve/CVE-2026-76195

IoC：未见公开 IoC。

### 12. 【本窗口新报】ChromeOS／ChromeOS Flex Stable M-151（2026-08-26）

Chrome Releases **Wednesday, August 26, 2026** Stable Channel Update for ChromeOS／ChromeOS Flex：平台 **M-151**，ChromeOS 版本 **16733.57.0**（Browser **151.0.7922.221**）推到 Stable。permalink 已核验。桌面 Chrome **152** 为昨日项，不在此重写。渲染帖摘要**未见在野利用声称**。狩猎：将 ChromeOS 设备更新到 **16733.57.0＋**。

地址：
- ChromeOS Stable 更新（permalink）：https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-chromeos_0131656799.html
- Chrome Releases 首页：https://chromereleases.googleblog.com/

IoC：未见公开 IoC。

### 13. 【续报】GitLab GraphQL CVE-2026-19478（仍未入 KEV）

对照 live KEV JSON catalogVersion **2026.08.26**／**1682** **确认缺席**。补丁仍为 **18.11.11／19.0.8／19.1.6／19.2.4**。本窗口未见新的 GitLab 厂商安全发布。狩猎：限制未认证 `/api/graphql`；升级。不写 GraphQL 查询体。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- GHSA：https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- CISA KEV 目录（复核缺席）：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 14. 【续报／仍有效 · 短】Keycloak／Calix／miniOrange／rConfig／DrayTek／Chrome 152／ICS-237／Entra 走回（本日无新重写）

下列昨日已展开，本窗口无新厂商主文或 KEV 重写；**仍开放／仍有效**，不重写全文。NVD API 本轮 **HTTP 200**（昨日 503），近 48h 另有若干 HIGH／CRITICAL 发布——除 Adobe ACC 已升格为厂商公告级外，其余不展开，避免编造利用。

- **Keycloak CVE-2026-18963**：补丁 **26.7.2／26.6.6／26.4.15**。临时：按 realm 关闭 Forgot password。**未入 KEV**。https://www.keycloak.org/2026/08/keycloak-2672-released https://nvd.nist.gov/vuln/detail/CVE-2026-18963
- **Calix GS7 XGS CVE-2026-75501**：CERT/CC VU#756733。覆盖范围内**未见厂商补丁**。**未入 KEV**。https://kb.cert.org/vuls/id/756733 https://nvd.nist.gov/vuln/detail/CVE-2026-75501
- **miniOrange SAML SSO WordPress CVE-2026-61979／CVE-2026-15981**：**未入 KEV**。https://www.bleepingcomputer.com/news/security/hackers-target-wordpress-sites-in-miniorange-auth-bypass-attacks/
- **rConfig CVE-2026-77915**：**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-77915 https://github.com/rconfig/rconfig/security/advisories/GHSA-w3hx-9cxg-5ccr
- **DrayTek DSA-2026-003**：**未入 KEV**。https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/
- **Chrome 152 桌面**（昨日 2026-08-25）：Linux **152.0.7977.64**；Win／Mac **152.0.7977.64／.65**。https://chromereleases.googleblog.com/
- **CISA ICS ICSA-26-237-01..07**（2026-08-25）：8/26 索引无新 ICS，仍为该批次。https://www.cisa.gov/news-events/ics-advisories
- **Entra ID CVE-2026-69836 走回仍有效**：云侧已缓解，客户无需打补丁。**未入 KEV**。https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836

IoC：未见本窗口新增公开 IoC。

## 工具与 GitHub 发布

### 1. nuclei-templates 仍为 v10.4.8

GitHub 发布页 HTML 核验：最新标签仍为 **v10.4.8**（**2026-08-24**）。本轮 GitHub API **限速**，以 HTML 页为准。定位为防御性扫描包。**未克隆模板、不转载 payload。**

地址：
- 发布页：https://github.com/projectdiscovery/nuclei-templates/releases
- 发布标签 v10.4.8：https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

### 2. Sliver 仍为 v1.7.3（2026-02-24）；本日无显著 C2 新版本

BishopFox/sliver HTML 核验最新标签 **v1.7.3**，日期 **2026-02-24**。Havoc／Mythic API 本轮不可用（限速）——**不编造发布**。**本日无显著 C2 新版本。**

地址：
- Sliver 发布页：https://github.com/BishopFox/sliver/releases
- nuclei-templates 发布页：https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。


### 3. 【本窗口 X】nuclei-templates PR 17012

X（@Redpatronus／@maldbx0）。nuclei-templates **PR 17012**（Log4j／Log4j2 检测模板）。定位防御性检测。**未克隆、不转载模板或绕过描述。**

地址：
- X（@Redpatronus）：https://x.com/Redpatronus/status/2092626521034736110
- X（@maldbx0）：https://x.com/maldbx0/status/2092669771330273551
- PR 17012：https://github.com/projectdiscovery/nuclei-templates/pull/17012

IoC：未见公开 IoC。

### 4. 【本窗口 X】ADScanPro／Claude-AD（仅仓库）

X（@Dinosn）链 GitHub **ADScanPro/Claude-AD**。定位为面向 Claude Code 的 AD 评估仓库。**只列 URL，不写攻击手法或复现。未克隆。**

地址：
- X（@Dinosn）：https://x.com/Dinosn/status/2092455415355146728
- 仓库：https://github.com/ADScanPro/Claude-AD

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. 【本窗口】Kaspersky Securelist：2026 年第二季度漏洞与利用（文章，非家族）

Securelist 季度统计报告，**datePublished 2026-08-26T10:00:04+00:00**。**不是新战役、不是新恶意软件家族**。已核验导语／目录：注册 CVE 数量上升、提及 Dirty Frag Linux 本地提权家族、APT 利用新公开漏洞、LLM／AI 工具漏洞条目（目录列 OpenClaw／Dify／Open WebUI／Exchange 等 CVE——**不把 TOC 升格为已核新洞或新 KEV**）。防御建议：打补丁，并加强凭据／代理控制。已核验导语未见可抄 IoC 清单。

地址：
- https://securelist.com/vulnerabilities-and-exploits-in-q2-2026/121091/

IoC：未见公开 IoC。

### 2. 【本窗口】威胁博客核验：无 8/26 新战役；Talos／MSTIC 403

Unit42 首页仍为 **8/25** AI 恶意软件文（昨日已报，**本日不重抄哈希**）。Mandiant／CrowdStrike／ESET／Trend／Proofpoint 抓取首页未见 8/25–26 战役日期。Talos 博客 **HTTP 403**；Microsoft Security Blog（MSTIC）**HTTP 403**。Wiz／SentinelOne／Zimperium 有 8/26 日期卡片，本轮**未独立核验为新 APT／恶意软件战役**（成本／遥测／产品向），不编造战役。X Latest 本轮 0 条，**不列泄露站声称**。

地址：
- https://unit42.paloaltonetworks.com/
- https://blog.talosintelligence.com/
- https://www.mandiant.com/resources/blog
- https://www.wiz.io/blog
- https://www.sentinelone.com/blog/
- https://securelist.com/

IoC：未见本窗口新增公开 IoC。昨日 Unit42 哈希不重抄。


### 3. 【本窗口 X · 一源】Core Lightning 官方称正在分诊大量 AI 生成 CVE 报告

X 官方账号 @Core_LN：**2026-08-26**。称大量 AI 生成 CVE 报告中有若干属实，协调修复中；建议节点以 `--offline` 重启。@TFTC21 称 BTCPay 默认部署已关掉到 Core Lightning／Eclair 的路由。仓库：https://github.com/ElementsProject/lightning 。**本轮无已核验的新 CVE 编号。** 不当作 KEV。

地址：
- X（@Core_LN）：https://x.com/Core_LN/status/2092755509510283423
- X（@TFTC21）：https://x.com/TFTC21/status/2092753728550150418
- 仓库：https://github.com/ElementsProject/lightning

IoC：未见公开 IoC。

### 未独立核验（仅 X；不当作今夜新 KEV／新战役）

下列仅为 X 一源或二手。**不把受害主机或端口清单当攻击者 IoC。** 今夜已核 KEV 六条**不含** CVE-2026-33824。

- Gitea 被用于投放挖矿：X／BC 链接，BC 正文本轮未核。https://x.com/EvanKirstel/status/2092741377700540626 https://bleepingcomputer.com/news/security/hackers-now-exploit-critical-gitea-flaw-in-code-injection-attacks/
- Windows IKE CVE-2026-33824「入 KEV」声称：https://x.com/MalwareBibleJP/status/2092733331305869481
- vCenter CVE-2026-59310「中国系 APT」声称：https://x.com/iss_kk_official/status/2092752983566197005
- macOS Screen Sharing CVE-2026-65400／端口 5900／门罗矿工（较旧 KEV 续报）：https://x.com/akihirot_/status/2092725602650583261
- 西门子 S7「AI 生成利用脚本」联合警告声称：https://x.com/unccno/status/2092726177215737866
- Huntress／Akira／SonicWall VPN 无 MFA 声称：https://x.com/alkeraithenw/status/2092739629854429692
- GitLab THN 标题（正文未独立渲染）：https://x.com/dejital_secure/status/2092730122029891769

IoC：未见公开攻击者 IoC（5900 为服务端口，不当攻击者 IoC）。

## 地址／IoC 汇总

### 本窗口新报

- KEV 本日六条（CVE-2026-8452／CVE-2019-1068／CVE-2021-23758／CVE-2022-0995／CVE-2015-3246／CVE-2015-5287）：未见公开 IoC
- SharePoint 链探测：未见公开攻击者 IoC；**不把 Shadowserver >8700 暴露计数当 IoC**
- Adobe ACC APSB26-134：未见公开 IoC
- ChromeOS M-151：未见公开 IoC
- Securelist Q2 2026 文章：未见公开 IoC
- nuclei-templates／Sliver：未见公开 IoC

### 续报（本窗口无新哈希）

- Oracle／Gitea／afd.sys／Zimbra／TrueConf／GitLab 缺席：未见本窗口新增公开 IoC
- 昨日 Unit42 SHA256：**本日不重抄**
- Keycloak／Calix／miniOrange／rConfig／DrayTek／Chrome 152／ICS-237／Entra：未见本窗口新增公开 IoC
- X 本轮 0 条：无泄露站声称可列；不把受害站点当 IoC

### 参考 URL（情报页，非恶意基础设施）

- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- https://support.citrix.com/external/article/CTX696604
- https://support.citrix.com/support-home/kbsearch/article?articleNumber=CTX696604
- https://nvd.nist.gov/vuln/detail/CVE-2026-8452
- https://nvd.nist.gov/vuln/detail/CVE-2019-1068
- https://nvd.nist.gov/vuln/detail/CVE-2021-23758
- https://nvd.nist.gov/vuln/detail/CVE-2022-0995
- https://nvd.nist.gov/vuln/detail/CVE-2015-3246
- https://nvd.nist.gov/vuln/detail/CVE-2015-5287
- https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- https://nvd.nist.gov/vuln/detail/CVE-2026-76195
- https://nvd.nist.gov/vuln/detail/CVE-2026-76197
- https://nvd.nist.gov/vuln/detail/CVE-2026-68820
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2019-1068
- https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/CVE-2019-1068
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- https://www.oracle.com/security-alerts/cpujan2026.html
- https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- https://github.com/michaelschwarz/Ajax.NET-Professional/commit/b0e63be5f0bb20dfce507cb8a1a9568f6e73de57
- https://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git/commit/?id=93ce93587d36493f2f86921fa79921b3cba63fbb
- https://access.redhat.com/articles/1537873
- https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-chromeos_0131656799.html
- https://chromereleases.googleblog.com/
- https://helpx.adobe.com/security/products/campaign/apsb26-134.html
- https://cveawg.mitre.org/api/cve/CVE-2026-76195
- https://www.bleepingcomputer.com/news/security/hackers-target-microsoft-sharepoint-rce-chain-with-poc-exploit/
- https://securelist.com/vulnerabilities-and-exploits-in-q2-2026/121091/
- https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/
- https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- https://github.com/projectdiscovery/nuclei-templates/releases
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/BishopFox/sliver/releases
- https://unit42.paloaltonetworks.com/
- https://blog.talosintelligence.com/
- https://www.mandiant.com/resources/blog
- https://www.keycloak.org/2026/08/keycloak-2672-released
- https://kb.cert.org/vuls/id/756733
- https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/26/cisa-adds-six-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/ics-advisories
- https://support.citrix.com/external/article/CTX696604
- https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-chromeos_0131656799.html
- https://securelist.com/vulnerabilities-and-exploits-in-q2-2026/121091/
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
