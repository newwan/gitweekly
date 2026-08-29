# X 安全情报晚报 · 2026-08-25

> 搜集窗口：圣地亚哥时间 **2026-08-24 20:00 至 2026-08-25 20:05**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周二）。**
> **本轮 X Latest 已回收**（logged_in=true, blocked=false）。文件 `/workspace/x-posts-2026-08-25.json`（**52** 条，collected_at **2026-08-25T20:40:00-04:00**）。搜索1 Latest（CVE／POC／exploit／0day）最旧可见 **2026-08-25T23:26:32Z**（覆盖约 **37 分钟**，**不可当作完整 24h CVE 检索**）。搜索2 github.com (C2 OR "red team" OR nuclei) Latest 最旧可见 **2026-08-18T08:00:00Z**（满窗口）。搜索3 「malware analysis／threat report／threat actor」Latest 最旧可见 **2026-08-25T16:10:25Z**（约 **8 小时**）。公开备援仍为 KEV／厂商 PRIMARY。
> 公开备援（本轮 PRIMARY）：`/workspace/security-watch-public-backup-2026-08-25.json`，**collected_at 2026-08-25T20:08:00-04:00**。CISA KEV catalogVersion **2026.08.25**／**1676** 条／dateReleased **2026-08-25T17:43:58.4301Z**。**KEV 本日新增** **CVE-2026-60004**（Gitea）。GitLab **CVE-2026-19478** 仍未入目。ICS 本日批次 **ICSA-26-237-01..07**（昨日最新仍为 **ICSA-26-232-01**）。NVD API 2.0 近 48h HIGH／CRITICAL 拉取失败 **HTTP 503**——**不编造额外 NVD CVE**。目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、SOAP 体、CGI、Git hook／diffpatch 样例或 PoC。本文件已按后到 X Latest 就地补丁（原 20:00 晚报为公开备援-only）。

## 今日摘要

- **KEV 本日新增 · Gitea CVE-2026-60004**：CISA KEV dateAdded **2026-08-25**；联邦缓解期限 **2026-08-28**。CWE-94 代码注入。具备仓库写权限者可向 diffpatch API 提交恶意补丁，植入可执行 Git hook，并以 Gitea 服务账户执行命令。GHSA Critical **9.8**；受影响 **>=1.17 <1.27.1**；补丁 **1.27.1**。默认开放注册可在注册后获得写权限。本轮 NVD 详情页返回 CVE ID Not Found，仍列尝试 URL。狩猎：盘点互联网暴露且 **<1.27.1** 的 Gitea；升级 **1.27.1+**；关闭开放注册；曾暴露主机按 BOD 26-04 取证分诊。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog https://www.cisa.gov/known-exploited-vulnerabilities-catalog https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m https://github.com/go-gitea/gitea/releases/tag/v1.27.1 https://nvd.nist.gov/vuln/detail/CVE-2026-60004 https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- **期限今日 · Windows afd.sys CVE-2026-68820**：KEV dateAdded **2026-08-11**；联邦缓解期限 **今日 2026-08-25**。本地提权（UAF）。打补丁后**需重启**。本日无 CISA 重写。IoC：未见公开 IoC。https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820 https://www.cisa.gov/known-exploited-vulnerabilities-catalog https://x.com/iss_kk_official/status/2092396783804760318
- **期限后天 · Oracle HTTP Server / WebLogic Server Proxy Plug-in CVE-2026-21962**：KEV dateAdded **2026-08-24**；联邦缓解期限 **2026-08-27**。CWE-284；未认证 HTTP；CVSS 10.0。补丁：**2026 年 1 月 CPU**。本日无厂商／KEV 重写。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-21962 https://www.oracle.com/security-alerts/cpujan2026.html https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog https://x.com/tsumikasanedev/status/2092400211402584257 https://x.com/markovichio/status/2092396137227448829
- **期限已过 · Zimbra CVE-2026-73570**（联邦期限原为 **2026-08-24**）＋ **本日新重写**：Help Net Security **2026-08-25** 引 Shadowserver——**2026-08-22** 扫描见 **274** 台互联网暴露实例带失陷制品（8/20 为 155，随后上升）；至少约 **8200** 台尚未升到 **10.1.20**（**并非全部可利用**；依赖非默认 SNMP 配置）。补丁 **10.1.20+**。**不把主机清单当 IoC**。IoC：未见公开攻击者 IoC。https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/ https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- **期限已过／仍须补丁 · TrueConf CVE-2026-72529／CVE-2026-72530**：72529 联邦期限 **2026-08-23** 已过；72530 期限 **2026-09-03**。补丁 **5.3.9／5.4.9／5.5.5**。本日无 CISA 重写。IoC：未见公开 IoC。https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- **本窗口新报 · Chrome 152 稳定通道 2026-08-25**：Chrome Releases 首页 **Tuesday August 25, 2026** 宣布 Stable：Linux **152.0.7977.64**，Win／Mac **152.0.7977.64／.65**；**327** 项安全修复。首条 Critical：**CVE-2026-79282** ANGLE UAF。渲染页**未见在野声称**。通用 slug 解析到 8/04 旧帖，**不编造独立 permalink**，只引首页。IoC：未见公开 IoC。https://chromereleases.googleblog.com/
- **本窗口新报 · CISA ICS 七条 ICSA-26-237-01..07**（2026-08-25）：昨日最新仍为 ICSA-26-232-01。CISA：发布时**未见针对这些漏洞的已知公开利用**。突出：Siemens IoT2050 **CVE-2026-58115** CVSS **10.0**（Node-RED 缺认证）；FURUNO FA-50 **EOL** 无软件更新、勿暴露互联网；ZoneMinder 存在公开 PoC（**本报不转载**）。IoC：未见公开 IoC。https://www.cisa.gov/news-events/ics-advisories
- **续报 · GitLab GraphQL CVE-2026-19478 仍未入 KEV**：对照 catalogVersion **2026.08.25**／**1676** 确认缺席。补丁仍为 **18.11.11／19.0.8／19.1.6／19.2.4**。本窗口未见新的 GitLab 厂商安全发布。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-19478 https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- **续报／仍有效（短）**：Keycloak **CVE-2026-18963**（**26.7.2／26.6.6／26.4.15**）、Calix **CVE-2026-75501**（未见厂商补丁）、miniOrange **CVE-2026-61979／CVE-2026-15981**、rConfig **CVE-2026-77915**、DrayTek DSA-2026-003、Entra **CVE-2026-69836** 走回（云侧已缓解）——**仍有效，不重写昨日全文**。https://www.cisa.gov/known-exploited-vulnerabilities-catalog https://www.keycloak.org/2026/08/keycloak-2672-released https://kb.cert.org/vuls/id/756733 https://x.com/securityLab_jp/status/2092401762867237094 https://rocket-boys.co.jp/security-measures-lab/wordpress-miniorange-saml-sso-auth-bypass-takeover/
- **工具**：nuclei-templates **仍为 v10.4.8**（**2026-08-24T13:01:50Z**）。**v10.4.7**（2026-08-03）已含 Gitea CVE-2026-60004 模板——**早于**本日 CISA KEV；项目 vKEV 标签**不是** CISA KEV。Sliver **仍为 v1.7.3**（**2026-02-24**）。**本日无显著 C2 新版本**。X 后到：nuclei-templates PR **17002**（模板问题修复）；SliverMirage 为 Sliver **PICO loader 分支**（仅记仓位）。https://github.com/projectdiscovery/nuclei-templates/releases https://github.com/BishopFox/sliver/releases https://x.com/DhiyaneshDK/status/2092184450272833615 https://github.com/projectdiscovery/nuclei-templates/pull/17002 https://github.com/daniomass/SliverMirage https://x.com/st8less/status/2092341064753426923 https://x.com/ipurple/status/2092131944054116585
- **APT／恶意软件**：AnonyMousKIT 语音代理针对 iPhone 用户；Unit 42：生产端点上观察到的 AI 赋能样本；挪威 Digdir DDoS 干扰政府数字服务（文章，非恶意软件）；OX：注册表包被用作 HTML 托管。IoC：api.keyval.org、login.microsofte.live。Talos 8/25 为评论、不列战役。 https://www.bleepingcomputer.com/news/security/anonymouskit-phaas-uses-voice-ai-agents-to-phish-iphone-passcodes/ https://unit42.paloaltonetworks.com/ai-enabled-malware-analysis/ https://x.com/swif_ai/status/2092395632409587962 https://www.bleepingcomputer.com/news/security/massive-ddos-attack-disrupts-norways-government-digital-services/ https://www.ox.security/blog/research-clickfix-phishing-npm-packages/

## CVE / POC / 漏洞

### 1. 【KEV 本日新增】Gitea CVE-2026-60004（dateAdded 2026-08-25；联邦期限 2026-08-28）

晚间公开备援。CISA 警报 **2026-08-25** 将本条列入 KEV；catalogVersion **2026.08.25**／count **1676** 中本日新增为 **CVE-2026-60004**（昨日 Oracle **CVE-2026-21962** 仍在目）。CWE-94。KEV／GHSA 高阶：具备仓库写权限的攻击者可向 diffpatch API 提交恶意补丁，植入可执行 Git hook，并以 Gitea 服务账户执行命令。**不转写请求样例、不抄 hook／补丁体、不链 PoC。**

GHSA-rcr6-4jqh-j84m：厂商 Critical **CVSS 9.8**；受影响 **>=1.17 <1.27.1**；已修补 **1.27.1**（发布 **2026-07-27T20:20:33Z**；GHSA **2026-07-28**）。默认开放注册时，注册并建仓后即可获得所需写权限。knownRansomwareCampaignUse Unknown。本轮采集时 NVD 详情页返回 **CVE ID Not Found**——仍列尝试 URL，不编造 NVD 字段。

狩猎：盘点互联网暴露、版本 **<1.27.1** 的 Gitea；立即升级 **1.27.1+**；对暴露实例关闭开放注册；曾暴露主机按 **BOD 26-04** 取证分诊。

地址：
- CISA 警报（2026-08-25，新增一条）：https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- KEV JSON 源：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- GHSA：https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- 厂商发布 v1.27.1：https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- NVD（本轮页返回 CVE ID Not Found，仅作尝试）：https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 2. 【期限今日】Windows afd.sys CVE-2026-68820（CISA 期限今日 2026-08-25）

仍在 KEV（2026.08.25／1676）。dateAdded **2026-08-11**（八月 Patch Tuesday）。本地提权，释放后使用（UAF），组件 **afd.sys**（Windows Ancillary Function Driver for WinSock）。联邦缓解期限 **今日 2026-08-25**。处置：按 MSRC 安装对应安全更新；**补丁后需重启**。仅高阶，不写利用原语。本日无 CISA 对本 CVE 的重写。

地址：
- X（@iss_kk_official）：https://x.com/iss_kk_official/status/2092396783804760318
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 3. 【期限后天】Oracle HTTP Server / WebLogic Server Proxy Plug-in CVE-2026-21962（dateAdded 2026-08-24；联邦期限 2026-08-27）

仍在 KEV。不当访问控制（CWE-284）。未认证攻击者具备 HTTP 网络访问即可。CVSS 3.1 **10.0**。受支持受影响版本：**12.2.1.4.0**、**14.1.1.0.0**、**14.1.2.0.0**；IIS 插件仅 **12.2.1.4.0**。补丁：**2026 年 1 月 Critical Patch Update**。联邦缓解期限 **2026-08-27**。狩猎：盘点互联网暴露的 OHS／WebLogic 代理插件；打 CPU；曾暴露主机按 BOD 26-04 取证分诊。本日无厂商／KEV 重写。

地址：
- CISA 警报（2026-08-24）：https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- X（@tsumikasanedev）：https://x.com/tsumikasanedev/status/2092400211402584257
- X（@markovichio）：https://x.com/markovichio/status/2092396137227448829
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- 厂商 2026 年 1 月 CPU：https://www.oracle.com/security-alerts/cpujan2026.html
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- CISA BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk

IoC：未见公开 IoC。

### 4. 【期限已过＋本日新重写】Zimbra Collaboration Suite CVE-2026-73570（KEV dateAdded 2026-08-21；联邦期限原为 2026-08-24）

仍在 KEV；联邦缓解期限现已**过期**。影响 Zimbra Collaboration **10.1.20 之前**，在可选 **zimbra-snmp** 已安装且 SNMP 通知已启用时。补丁：**10.1.20+**。

**本日新重写**（Help Net Security **2026-08-25**，引 Shadowserver）：**2026-08-22** 扫描见 **274** 台互联网暴露实例带失陷制品（**2026-08-20** 为 155，随后上升）；至少约 **8200** 台尚未升到 **10.1.20**——**并非全部可利用**（依赖非默认配置）。行为者未知。BC 同题 URL 本轮被 Cloudflare 拦截；已核验正文为 Help Net Security。狩猎：`/var/log/zimbra.log` 中意外 Service status change；检查 jetty webapps 与 `/tmp/` 下近期由 zimbra 用户拥有的文件。只记路径，不写利用。曾暴露主机按可能已被预入侵处置。**不把主机清单或 Shadowserver 计数当 IoC。**

地址：
- Help Net Security（2026-08-25）：https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/
- CISA 警报（2026-08-21）：https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- 厂商：https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开攻击者 IoC。不把 Shadowserver 主机计数当 IoC。

### 5. 【期限已过／仍须补丁】TrueConf Server CVE-2026-72529／CVE-2026-72530

仍在 KEV。CISA **2026-08-20** 将两条列入。**CVE-2026-72529** 联邦期限为 **2026-08-23**（已过）——若尚未完成，仍须立即打补丁。**CVE-2026-72530** 期限 **2026-09-03**。补丁：**5.3.9**、**5.4.9** 或 **5.5.5**。狩猎：盘点暴露的 **4307/TCP**；曾暴露主机按可能已被预入侵处置。本日无 CISA 重写。不写战役剧本。

地址：
- CISA 警报（2026-08-20，新增两条）：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- NVD CVE-2026-72529：https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- NVD CVE-2026-72530：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 6. 【本窗口新报】Chrome 152 稳定通道（2026-08-25；未见在野声称）

Chrome Releases 首页渲染 **Tuesday August 25, 2026** Stable Channel Update，宣布 Chrome **152**：Linux **152.0.7977.64**；Windows／Mac **152.0.7977.64／.65**；**327** 项安全修复。首条 Critical：**CVE-2026-79282** Use after free in ANGLE。备援另列 Critical：CVE-2026-79290 Aura、CVE-2026-79054／CVE-2026-79121／CVE-2026-79224 Chromecast、CVE-2026-79052 Aura、CVE-2026-79150 Views、CVE-2026-78935 Mobile、CVE-2026-79012 Safebrowsing、CVE-2026-79200 Aura。渲染页**未见在野利用声称**。通用 slug `/2026/08/stable-channel-update-for-desktop.html` 本轮解析到 **2026-08-04** 旧帖——**不编造独立 permalink**，只引首页。狩猎：将 Chrome／Edge／Chromium 更新到 **152.0.7977.64+**。

地址：
- Chrome Releases 首页：https://chromereleases.googleblog.com/

IoC：未见公开 IoC。

### 7. 【本窗口新报】CISA ICS 批次 ICSA-26-237-01 至 ICSA-26-237-07（2026-08-25）

CISA ICS 索引本日新增七条（昨日最新仍为 **2026-08-20 ICSA-26-232-01**）。CISA：发布时**未见针对这些漏洞的已知公开利用**。高阶（只记谁／CVE／补丁；不抄 PoC）：

1. **ICSA-26-237-01** Rently Smart Home **<=20.1.0** **CVE-2026-75960** CVSS **8.1**；厂商称已于 6 月底修补，用户无需操作。
2. **ICSA-26-237-02** ZoneMinder **1.37.48／1.38.3** **CVE-2026-76060** 认证后 OS 命令注入 CVSS **8.8**；升级 **1.38.3+**。CISA 注明存在公开 PoC——**本报不转载、不链利用步骤**。
3. **ICSA-26-237-03** Siemens SIMATIC IoT2050 Advanced **<V4.3.4.1** **CVE-2026-58115** Node-RED HTTP 缺认证 CVSS **10.0**；更新 **V4.3.4.1** 或卸载／加固 Node-RED。CISA 再刊 SSA-834709。
4. **ICSA-26-237-04** PayRange API **CVE-2026-18965** 缺授权 CVSS **8.8**；厂商尚未协调补丁。
5. **ICSA-26-237-05** Bendix EC80 Brake ECU **CVE-2026-67560／68967／71396**；按型号固件 **Z300822／Z302578／Z302579**。
6. **ICSA-26-237-06** Ebyte NE2-D11 FW-9167-0-11 多条 CRITICAL（含 **CVE-2026-73125／71187／76179／69658** CVSS **9.8**）；补丁状态未知。
7. **ICSA-26-237-07** FURUNO FA-50 AIS 自 **2020 年 10 月 EOL** **CVE-2026-59769／67578**；**无软件更新**；**勿暴露到互联网**。

狩猎：隔离 OT 管理面；按上列固件／版本升级；盘点 IoT2050 上的 Node-RED 与 ZoneMinder 暴露面。

地址：
- CISA ICS 索引：https://www.cisa.gov/news-events/ics-advisories
- ICSA-26-237-01：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-01
- ICSA-26-237-02：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-02
- ICSA-26-237-03：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-03
- ICSA-26-237-04：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-04
- ICSA-26-237-05：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-05
- ICSA-26-237-06：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-06
- ICSA-26-237-07：https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-07
- ZoneMinder GHSA：https://github.com/ZoneMinder/zoneminder/security/advisories/GHSA-88m4-hrgp-m9v3
- Siemens SSA：https://support.industry.siemens.com/cs/ww/en/view/109741799/

IoC：未见公开 IoC。

### 8. 【续报】GitLab GraphQL CVE-2026-19478（仍未入 KEV）

对照 live KEV JSON catalogVersion **2026.08.25**／**1676** **确认缺席**。补丁仍为 **18.11.11／19.0.8／19.1.6／19.2.4**。本窗口未见新的 GitLab 厂商安全发布。狩猎：日志 `@gl_introduced`；限制未认证 `/api/graphql`。不写 GraphQL 查询体。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- GHSA：https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- CISA KEV 目录（复核缺席）：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 9. 【续报／仍有效 · 短】Keycloak／Calix／miniOrange／rConfig／DrayTek／Entra 走回（本日无新重写）

下列昨日已展开，本窗口无新厂商主文或 KEV 重写；**仍开放／仍有效**，不重写全文。NVD API 本轮 **HTTP 503**，不编造额外 NVD CVE。

- **Keycloak CVE-2026-18963**：补丁 **26.7.2／26.6.6／26.4.15**。临时：按 realm 关闭 Forgot password。**未入 KEV**。不写重置凭据走流程。https://www.keycloak.org/2026/08/keycloak-2672-released https://nvd.nist.gov/vuln/detail/CVE-2026-18963
- **Calix GS7 XGS CVE-2026-75501**：EXOS through **6.6.47**；CERT/CC VU#756733。覆盖范围内**未见厂商补丁**。缓解：关闭 UPnP 或联系 ISP；过滤入站 TCP/5000。不抄 SOAP。**未入 KEV**。https://kb.cert.org/vuls/id/756733 https://nvd.nist.gov/vuln/detail/CVE-2026-75501
- **miniOrange SAML SSO WordPress CVE-2026-61979／CVE-2026-15981**：Free **5.4.5**；Premium **13.0.4**；Standard **17.0.6** 等（七版本线见昨日）。狩猎：预期范围外的 WP 管理员会话。**未入 KEV**。https://www.bleepingcomputer.com/news/security/hackers-target-wordpress-sites-in-miniorange-auth-bypass-attacks/ https://patchstack.com/articles/one-slug-seven-editions-the-miniorange-saml-sso-bug-that-let-anyone-log-in-as-your-wordpress-admin/
  X（@securityLab_jp）：https://x.com/securityLab_jp/status/2092401762867237094 ；日文续报：https://rocket-boys.co.jp/security-measures-lab/wordpress-miniorange-saml-sso-auth-bypass-takeover/
- **rConfig CVE-2026-77915**：未认证 POST /register 可自注册管理员。GHSA 称补丁 **8.2.10**；NVD 文称 **8.2.13 之前**——口径不一致，照录不裁定。**未入 KEV**。https://nvd.nist.gov/vuln/detail/CVE-2026-77915 https://github.com/rconfig/rconfig/security/advisories/GHSA-w3hx-9cxg-5ccr
- **DrayTek DSA-2026-003 VigorSwitch CVE-2026-71915-71943**：突出 **CVE-2026-71921** 9.8。固件见表见昨日。不抄 CGI。**未入 KEV**。https://www.draytek.com/about/security-advisory/multiple-vulnerabilities-in-vigorswitch-series-august-2026/ https://nvd.nist.gov/vuln/detail/CVE-2026-71921
- **Entra ID CVE-2026-69836 走回仍有效**：云侧已缓解，客户无需打补丁。**未入 KEV**。https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/ https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- 备援亦核验本日无新重写：ipTIME **CVE-2026-78168**、Netis **CVE-2026-76071**、Xinference **CVE-2026-76841**、nektos/act **CVE-2026-76847**、llama.cpp **CVE-2026-78147／78148**、Elementor Pro **4.2.2**、SPIP **4.4.21**、NetScaler **CVE-2026-19490**、TRENDnet **CVE-2026-75784**——仍有效，不重写。https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见本窗口新增公开 IoC（miniOrange 既有扫描 IP 见 8/24 晚报，本窗口不重抄）。

## 工具与 GitHub 发布

### 1. nuclei-templates 仍为 v10.4.8（2026-08-24T13:01:50Z）

GitHub 最新发布标签仍为 **v10.4.8**（**2026-08-24T13:01:50Z**）。**v10.4.7**（**2026-08-03**）已含 Gitea **CVE-2026-60004** 检测模板——**早于**本日 CISA KEV 列入。项目自标 vKEV **不是** CISA KEV。定位为防御性扫描包。**未克隆模板、不转载 payload。**

地址：
- 发布页：https://github.com/projectdiscovery/nuclei-templates/releases
- 发布标签 v10.4.8：https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

IoC：未见公开 IoC。

### 2. Sliver 仍为 v1.7.3（2026-02-24）；本日无显著 C2 新版本

BishopFox/sliver 已核验最新标签 **v1.7.3**，日期 **2026-02-24**。本轮采集未见经 API 确认的 Havoc／Mythic 窗口内新发布。**本日无显著 C2 新版本。**

地址：
- Sliver 发布页：https://github.com/BishopFox/sliver/releases
- nuclei-templates 发布页：https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。


### 3. 【本窗口 X】nuclei-templates PR 17002

X（@DhiyaneshDK）。nuclei-templates **PR 17002**（修复已报模板问题）。防御性检测，**未克隆、不转载模板**。

地址：
- X（@DhiyaneshDK）：https://x.com/DhiyaneshDK/status/2092184450272833615
- PR 17002：https://github.com/projectdiscovery/nuclei-templates/pull/17002

IoC：未见公开 IoC。

### 4. 【本窗口 X】SliverMirage（Sliver PICO 加载器分支）

X（@st8less／@ipurple）链 GitHub **daniomass/SliverMirage**。定位为 Sliver 用的 PICO 加载器分支。**只列仓库，不描述绕过或投递机制。未克隆。**

地址：
- X（@st8less）：https://x.com/st8less/status/2092341064753426923
- X（@ipurple）：https://x.com/ipurple/status/2092131944054116585
- 仓库：https://github.com/daniomass/SliverMirage

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. 【本窗口】AnonyMousKIT 语音代理针对 iPhone 用户

BleepingComputer 正文渲染 **2026-08-25 04:25 PM**。SOCRadar 经 BC：声称 **506** 个域名、**168** 个店面；2025 年 8 月至 2026 年 5 月回收约 200 通通话；约 **90%** 指向巴西。渲染正文无具体域名或哈希可抄。SOCRadar 原页本轮被 Cloudflare 拦截。不把域名计数当可抄 IoC。狩猎：针对 iPhone 口令的语音来电；异常语音代理来电。

地址：
- https://www.bleepingcomputer.com/news/security/anonymouskit-phaas-uses-voice-ai-agents-to-phish-iphone-passcodes/
IoC：未见可抄录的公开域名或哈希（正文未列清单；不把域名计数当 IoC）。

### 2. 【本窗口】Unit 42：生产端点上观察到的 AI 赋能样本

Unit 42 正文已渲染。发布 **2026-08-25**。**405** 个样本，其中 **12** 个出现在生产端点，全部已被拦截。家族：FunkSec、Recipe Lister（Global Tech Allies Ltd. 证书已吊销）、Oyster／CleanBoost、Rhadamanthys、360Util.dll COM 劫持。狩猎：用下表 SHA256 做哈希匹配；防御向，不写利用。

地址：
- https://unit42.paloaltonetworks.com/ai-enabled-malware-analysis/
- X（@swif_ai）：https://x.com/swif_ai/status/2092395632409587962
- X（@sultan_alhajlah）：https://x.com/sultan_alhajlah/status/2092356782098141332
IoC（SHA256，照录）：
- 1619bcad3785be31ac2fdee0ab91392d08d9392032246e42673c3cb8964d4cb7
- 5226ea8e0f516565ba825a1bbed10020982c16414750237068b602c5b4ac6abd
- dcf536edd67a98868759f4e72bcbd1f4404c70048a2a3257e77d8af06cb036ac
- 66dbf939c00b09d8d22c692864b68c4a602e7a59c4b925b2e2bef57b1ad047bd
- c233aec7917cf34294c19dd60ff79a6e0fac5ed6f0cb57af98013c08201a7a1c
- e622f3b743c7fc0a011b07a2e656aa2b5e50a4876721bcf1f405d582ca4cda22
- b1ef7b267d887e34bf0242a94b38e7dc9fd5e6f8b2c5c440ce4ec98cc74642fb
- 20ed21bfdb7aa970b12e7368eba8e26a711752f1cc5416b6fd6629d0e2a44e5d
- dd15ce869aa79884753e3baad19b0437075202be86268b84f3ec2303e1ecd966
- c398b3e06ef860670b9597daed85632834fa961aea87164b8ba8bb2f094a14ef
- bb932056cae8940742e50b4f2b994a802e703f7bc235e7dd647d085ae2b2baf7
- 4fb58687a364c3f6d6f7e0ca03654f9dec0f8832a499d61d40b0d424db1b1b14

### 3. 【本窗口】挪威 Digdir DDoS 干扰政府数字服务（文章，非恶意软件）

BleepingComputer 正文渲染 **2026-08-25 11:52 AM**。攻击始于周一 **03:38 CEST**。ID-porten 与 eSignering 部分受影响。Digdir：无数据泄露、无个人数据影响。此为近期第三次 Digdir DDoS（前两次为 6 月与 **2026-08-03**）。渲染正文无官方归因。这是事件报道，不是恶意软件分析。

地址：
- https://www.bleepingcomputer.com/news/security/massive-ddos-attack-disrupts-norways-government-digital-services/
IoC：未见公开 IoC。

### 4. 【本窗口】OX：注册表包被用作 HTML 托管

OX 正文已核验（表内含 2026-08-24 发布；BC 首页 2026-08-25）。**24** 个包共用一页经注册表镜像提供的 HTML。不是安装时恶意软件。BC 首页列有对应标题，但文章正文本轮被拦截。IoC 仅抄录正文给出的两个域名。狩猎：阻断／告警下列域名。

地址：
- https://www.ox.security/blog/research-clickfix-phishing-npm-packages/
- https://www.bleepingcomputer.com/
IoC：api.keyval.org , login.microsofte.live

### 说明（非战役）

Talos 8/25 博文为评论，**不是新战役**，本报不列 APT 战役条。UAT-10147 日期仍为 **2026-08-20**，非同日重写。8/25 帖无新 IoC。https://blog.talosintelligence.com/


### 未独立核验（X 泄露站／单源声称；仅 X URL）

下列仅为 X 广告或单源声称，**未独立核验**。**不把受害站点当 IoC。** Vulmon／CVEnew 清单 CVE **不升格为已核新洞**。THN 西门子 S7 标题正文本轮未独立渲染。

- Qilin 声称 Brazosport College：https://x.com/FalconFeedsio/status/2092364863402344954
- SAFEPAY 声称 Air Liquide Korea：https://x.com/FalconFeedsio/status/2092362214716080314
- chaos 声称 mswalker.com：https://x.com/ThreatAtlas/status/2092333768165957818
- Kodex 声称：https://x.com/BreachNewsHQ/status/2092292809264918601
- MyNewTerm 声称：https://x.com/BreachNewsHQ/status/2092397481808351392
- PhonePe 声称：https://x.com/thecybersecguru/status/2092296421680771236
- Nutex Health 声称确认失窃：https://x.com/XQOPTRX/status/2092329090422337687
- 其他泄密声称：https://x.com/DarkWebInformer/status/2092402479971356833 https://x.com/DarkWebInformer/status/2092393088790544681 https://x.com/DarkWebInformer/status/2092291233079050748 https://x.com/DailyDarkWeb/status/2092347512833077413 https://x.com/DailyDarkWeb/status/2092346558956130339 https://x.com/DailyDarkWeb/status/2092345483968827901
- THN 西门子 S7 标题（未核正文）：https://x.com/cjshaker/status/2092399656601071874

IoC：未见公开攻击者 IoC。

## 地址／IoC 汇总

### 本窗口新报

- Unit 42 SHA256（照录 12 条）：
  - 1619bcad3785be31ac2fdee0ab91392d08d9392032246e42673c3cb8964d4cb7
  - 5226ea8e0f516565ba825a1bbed10020982c16414750237068b602c5b4ac6abd
  - dcf536edd67a98868759f4e72bcbd1f4404c70048a2a3257e77d8af06cb036ac
  - 66dbf939c00b09d8d22c692864b68c4a602e7a59c4b925b2e2bef57b1ad047bd
  - c233aec7917cf34294c19dd60ff79a6e0fac5ed6f0cb57af98013c08201a7a1c
  - e622f3b743c7fc0a011b07a2e656aa2b5e50a4876721bcf1f405d582ca4cda22
  - b1ef7b267d887e34bf0242a94b38e7dc9fd5e6f8b2c5c440ce4ec98cc74642fb
  - 20ed21bfdb7aa970b12e7368eba8e26a711752f1cc5416b6fd6629d0e2a44e5d
  - dd15ce869aa79884753e3baad19b0437075202be86268b84f3ec2303e1ecd966
  - c398b3e06ef860670b9597daed85632834fa961aea87164b8ba8bb2f094a14ef
  - bb932056cae8940742e50b4f2b994a802e703f7bc235e7dd647d085ae2b2baf7
  - 4fb58687a364c3f6d6f7e0ca03654f9dec0f8832a499d61d40b0d424db1b1b14
- OX 域名（照录）：api.keyval.org , login.microsofte.live
- KEV 条目与 Chrome／ICS：未见公开 IoC（不把主机计数或域名计数当 IoC）
- 挪威 Digdir DDoS：未见公开 IoC

### 续报（本窗口无新哈希）

- 昨日仍开放项：未见本窗口新增公开 IoC
- nuclei-templates／Sliver：未见公开 IoC
- Talos 8/25 评论／UAT-10147（8/20）：本日无新 IoC

### 参考 URL（情报页，非恶意基础设施）

- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/cybersecurity-advisories
- https://www.cisa.gov/news-events/ics-advisories
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-06
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-07
- https://nvd.nist.gov/vuln/detail/CVE-2026-60004
- https://services.nvd.nist.gov/rest/json/cves/2.0
- https://github.com/go-gitea/gitea/security/advisories/GHSA-rcr6-4jqh-j84m
- https://github.com/go-gitea/gitea/releases/tag/v1.27.1
- https://chromereleases.googleblog.com/
- https://www.cisa.gov/news-events/alerts/2026/08/24/cisa-adds-one-known-exploited-vulnerability-catalog
- https://nvd.nist.gov/vuln/detail/CVE-2026-21962
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- https://www.oracle.com/security-alerts/cpujan2026.html
- https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/
- https://unit42.paloaltonetworks.com/ai-enabled-malware-analysis/
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-on-risk
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- https://nvd.nist.gov/
- https://msrc.microsoft.com/update-guide
- https://www.bleepingcomputer.com/
- https://wordpress.org/news/
- https://www.fortiguard.com/psirt
- https://thehackernews.com/
- https://www.wiz.io/blog
- https://blog.google/threat-analysis-group/
- https://github.com/BishopFox/sliver/releases
- https://github.com/projectdiscovery/nuclei-templates/releases
- https://patchstack.com/articles/
- https://www.mandiant.com/resources/blog
- https://www.bleepingcomputer.com/news/security/anonymouskit-phaas-uses-voice-ai-agents-to-phish-iphone-passcodes/
- https://www.bleepingcomputer.com/news/security/massive-ddos-attack-disrupts-norways-government-digital-services/
- https://blog.talosintelligence.com/
- https://www.ox.security/blog/
- https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- https://github.com/ZoneMinder/zoneminder/security/advisories/GHSA-88m4-hrgp-m9v3
- https://support.industry.siemens.com/cs/ww/en/view/109741799/
- https://www.ox.security/blog/research-clickfix-phishing-npm-packages/

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/news-events/alerts/2026/08/25/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/ics-advisories
- https://chromereleases.googleblog.com/
- https://unit42.paloaltonetworks.com/ai-enabled-malware-analysis/
- https://www.helpnetsecurity.com/2026/08/25/zimbra-cve-2026-73570-compromised/
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
