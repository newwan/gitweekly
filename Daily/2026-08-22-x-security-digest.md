# X 安全情报晚报 · 2026-08-22

> 搜集窗口：圣地亚哥时间 **2026-08-21 20:00 至 2026-08-22 20:05**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报。** 下午曾有手动重跑草稿（窗口 13:20–13:30），本版在其已核公开条目与 X 补录上更新，不以该草稿为正式口径。
> **20:00 本轮 X Latest 已回收**（logged_in=true, rate-limited）。搜索1：00:06Z 回到 19:00Z（~5h），17:20Z–19:00Z 与 13:52Z 之前仍未覆盖。搜索2：满 24h。搜索3 收窄后：00:03Z 回到 2026-08-21 13:45Z（满窗口含下午漏的时段）。文件 /workspace/x-posts-2026-08-22-evening.json（77 条）。
> 公开备援（晚间核验）：CISA KEV 目录（catalogVersion **2026.08.21**，**1674** 条）与 2026-08-21「新增一条」警报、CISA ICS ICSA-26-232-01、NVD、Chrome 稳定通道、HKCERT、Zimbra Wiki、CERT Polska、SPIP 厂商、GitLab 补丁说明、Rust 官方、JFrog、Wiz、Help Net Security、Truffle Security、BleepingComputer、Cybersecurity Dive、SecurityWeek、GovInfoSecurity、MSRC、Cisco Talos / Cisco-Talos/IOCs、TruffleHog GitHub、nuclei-templates releases。备援 JSON：`/workspace/security-watch-public-backup-2026-08-22-evening.json`（collected_at **2026-08-22T20:14:04-04:00**）。**未见 2026-08-22 KEV 或 ICS。** 对照 8/20 晚报与下午草稿以区分「新入 KEV／晚报新报」与「续报／仍有效」。
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、GraphQL 查询体、XSS／SPIP 过滤 payload 或 Unisoc PoC。UAT-10147 仅高阶。Adobe／Fortinet／Ivanti 本窗口未见 2026-08-21／22 公告。

## 今日摘要

- **晚报新报 · Elementor Pro CVE-2026-32475**（CVSS 9.0）：Forms File Upload 未认证文件上传可至 RCE。影响 **≤4.2.1**（已发布表单含 File Upload 时）。补丁 **4.2.2**（2026-08-19）。X 本日回流。狩猎：`wp-content/uploads/elementor/forms/` 下意外 PHP。Patchstack 8/19 咨询二手综述：未见已确认大规模利用——**不当成在野事实**。IoC：未见公开 IoC。https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- **窗口前／本日回流 · LiteSpeed cPanel 插件 CVE-2026-48172**：真实漏洞，**2026 年 5 月**（当时已利用；CISA KEV 约 **2026-05-26**）。已认证 cPanel 用户可至 root。补丁：用户端插件 **2.4.5+**／建议 **2.4.7** 并配合 WHM **5.3.1.0**。狩猎：日志串 `cpanel_jsonapi_func=redisAble`（只记名）。IoC：未见公开 IoC。https://github.com/advisories/GHSA-fxrh-cwjh-m33v
- **晚报新报 · NetScaler CVE-2026-19490**（CVSS 4.0 **9.3**）认证绕过。Citrix 公告；Help Net Security **2026-08-21**。Gateway／AAA（较新构建有 SAML 前置条件）。补丁 **14.1-73.32／13.1-63.21／FIPS 14.1-73.32／13.1-37.277**。同公告另列 **CVE-2026-19489**（本报不编造其细节）。IoC：未见公开 IoC。https://support.citrix.com/external/article/CTX696939/netscaler-adc-and-netscaler-gateway-secu.html
- **晚报新报（下午漏报）**：SPIP **CVE-2026-77806**。厂商 **2026-08-20**，NVD **2026-08-21**。补丁 **4.4.21**。通用预认证 RCE（**4.4.20 亦中**；安全屏挡不住）。厂商／ANSSI：利用尝试；CVE 正文称 2026 年 8 月在野；NVD CISA-ADP SSVC 仍标 exploitation **none**；**未入 KEV**（catalogVersion 2026.08.21）。狩猎：只查意外 **X-Spip-Filtre** 请求头（只记头名，不写利用）。IoC：未见公开 IoC。https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- **晚报更新 · GitLab GraphQL CVE-2026-19478**：WatchTowr 蜜罐在 **8/17** 披露约 **2 日**后见探测（SecurityWeek／GovInfoSecurity）。**仍未入 KEV**。NVD SSVC 仍 **none**。影响为**数据完整性，不是已确认 RCE**。补丁 **18.11.11／19.0.8／19.1.6／19.2.4**。狩猎：日志中的 `@gl_introduced`；限制未认证 `/api/graphql`。下午 X 链保留。https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/
- **晚报更新 · Entra ID CVE-2026-69836**：BleepingComputer **2026-08-22 02:56 EDT** 走回**已核验**（晚间重抓成功）。微软称曾**误标为已利用**。Cybersecurity Dive：周五更新称**无利用**。云侧已缓解，**客户无需打补丁**。**未入 KEV**。https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- **期限明日**：TrueConf **CVE-2026-72529** 联邦期限 **2026-08-23（明日）**；**CVE-2026-72530** 期限 **2026-09-03**。补丁 5.3.9／5.4.9／5.5.5。TCP/4307。https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- **新入 KEV（2026-08-21）**：Zimbra Collaboration Suite **CVE-2026-73570**。CISA 警报与 KEV dateAdded 均为 2026-08-21；联邦期限 **2026-08-24**。补丁 **10.1.20+**。KEV catalogVersion **2026.08.21**／**1674** 条；8/22 无新 KEV。https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- **本窗口新报／跟进**：Chrome 151 **CVE-2026-76017**（Chrome 博文 8/20，HKCERT 8/21）；升级 **151.0.7922.173／.174**。NVD SSVC 快照 exploitation 为 none。https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-desktop_0404570826.html
- **续报／仍有效（已见 8/20 晚报）**：crates.io arrayref／internment／append-only-vec ＋ proc-macro1（CVE-2026-77651／77649／77650）。钉死 0.3.9／0.8.6／0.1.8。晚间加 Wiz 额外狩猎指标（与 Sapphire Sleet／UNC1069 **基础设施重叠，不据此单独归因**）。https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- **续报／仍有效**：CISA ICS **ICSA-26-232-01** Johnson Controls **CVE-2026-27875**（仅本地）。补丁 v2.01.01。8/21–8/22 未见新 ICS。https://www.cisa.gov/news-events/ics-advisories/icsa-26-232-01
- **续报／仍有效**：Talos UAT-10147 ＋ SPECTRE（2026-08-20 06:00）。仅高阶。https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- **本窗口新报（工具／情报）**：Truffle Security／BleepingComputer 8/21：768 枚仍有效的企业 AWS root／AdministratorAccess 密钥。未公布任何密钥材料。https://trufflesecurity.com/blog/leaked-corporate-aws-keys-held-full-admin-rights
- **红队工具版本**：nuclei-templates 仍为 v10.4.7（2026-08-03）。本窗口未见已核验的 nuclei／Sliver／Havoc／Mythic 新版本。https://github.com/projectdiscovery/nuclei-templates/releases

### X 补录（下午已核 ＋ 20:00 Latest 已回收，见文首）

- **X 补录 · Elementor Pro CVE-2026-32475**（CVSS 9.0）：Forms File Upload 未认证上传可至 RCE；**≤4.2.1**（已发布表单含 File Upload）。补丁 **4.2.2**（2026-08-19）。X 本日回流。狩猎：`wp-content/uploads/elementor/forms/` 下意外 PHP。不当成已确认大规模在野。https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- **X 补录 · 窗口前／本日回流 LiteSpeed cPanel CVE-2026-48172**（2026 年 5 月；KEV 约 2026-05-26）。已认证 cPanel 用户可至 root。补丁用户端 **2.4.5+**／建议 **2.4.7**＋WHM **5.3.1.0**。狩猎：`cpanel_jsonapi_func=redisAble`。https://nvd.nist.gov/vuln/detail/CVE-2026-48172
- **X 补录 · NetScaler CVE-2026-19490**（CVSS 4.0 9.3）认证绕过。Citrix；HNS 2026-08-21。补丁 **14.1-73.32／13.1-63.21／FIPS 14.1-73.32／13.1-37.277**。同公告含 **CVE-2026-19489**。https://www.helpnetsecurity.com/2026/08/21/citrix-netscaler-gateway-cve-2026-19490/
- **X 晚间只加链**：Entra（不重写成已利用）、GitLab、TrueConf、Zimbra。未核验声称见文末短小节。
- **X 补录 · GitLab GraphQL CVE-2026-19478**（厂商博客 CVSS 9.4）：未认证经 GraphQL 指令修改／删除公开项目与用户数据（**数据完整性，不是已确认 RCE**）。晚间公开源：WatchTowr 蜜罐见披露后约 2 日探测。CE/EE 补丁 **18.11.11／19.0.8／19.1.6／19.2.4**。**未入 KEV**。https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- **X 补录 · WordPress CVE-2026-64638**：官方 **7.0.3** 安全版 **2026-08-06**（X 本日回流，不是今天才披露）。登录页预认证反射型 XSS；完整 PHP 执行路径需已登录管理员与攻击者页面交互，**不可蠕虫化**。https://wordpress.org/news/2026/08/wordpress-7-0-3-release/
- **X 补录 · Unisoc VoLTE 视频通话链**：接听视频通话即可作为受害语境；部分芯片（二手报道提及 T606／T612／T616／T7250）可由调制解调器隔离问题到达 Android 内核。中旬报道时**未见厂商补丁／未见 CVE**。https://ssd-disclosure.com/unisoc-t612-lpe/
- **X 补录 · Android 车机 BADBOX／MoYu**（Kaspersky／BC **2026-08-22**）：MQTT **cardoor.cn**；恶意软件 JarService；代理模块 zhima；TWCore。广告欺诈／住宅代理。DoFun 称已处理。https://www.kaspersky.com/blog/car-botnet-malware-for-head-units-with-android/56296/
- **X 补录 · Unit 42 DeepSeek＋Hermes Agent**（knaithe／KnYuan；7 月／8 月初研究本日回流）：**不是 UAT-10147，勿合并**。中文语境投机型；Telegram 编排；部分目标自动侦察失败，人工活动有影响。https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/
- **X 补录 · Sonatype 2026-08-10**（X 本日回流）。六包见下方 IoC 汇总。https://www.sonatype.com/blog/six-npm-packages-use-ethereum-transactions-to-retrieve-malicious-payloads
- **X 补录 · 已有条目只加链**：Entra 走回、Zimbra＋SOCRadar、crates.io @blackanger、UAT-10147 DFIR_Radar。勒索／泄密广告见文末「未独立核验」。

## CVE / POC / 漏洞

### 1. 【本窗口新入 KEV】Zimbra Collaboration Suite OS 命令注入 CVE-2026-73570

8/20 晚报已报 CERT Polska／英媒跟进，并写明**当时尚未入 KEV**。CISA 于 **2026-08-21** 发布警报，将该 CVE 加入已知被利用漏洞目录（KEV dateAdded 2026-08-21），联邦缓解期限 **2026-08-24**。

NVD：Zimbra Collaboration **10.1.20 之前**，在可选组件 **zimbra-snmp** 已安装且 SNMP 通知已启用时，特制 SMTP 可导致以 **zimbra** 用户执行操作系统命令（远程代码执行）。补丁：升级至 **10.1.20+**。厂商咨询见 Zimbra Security Advisories。

CERT Polska（原文日期 2026-08-17，通告 145/2026；本窗口作狩猎对照）：在 `/var/log/zimbra.log` 中寻找意外的 Service status change 行；检查 jetty webapps 与 `/tmp/` 下近期由 zimbra 用户拥有的文件。只记路径，不写利用。本晚报不转载复现步骤。

地址：
- CISA 警报（2026-08-21，新增一条 KEV）：https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- 厂商：https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- CERT Polska：https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/
- X（@DFIR_Radar）：https://x.com/DFIR_Radar/status/2091194165581553672
- X（@DFIR_Radar，指向 SOCRadar）：https://x.com/DFIR_Radar/status/2091194167502537139
- 文章（SOCRadar）：https://socradar.io/blog/cve-2026-73570-zimbra-rce/
- X（晚间 @PCMedicalist）：https://x.com/PCMedicalist/status/2091257477530574970

IoC：未见公开 IoC。

### 2. 【本窗口新报／HKCERT 8/21】Google Chrome 151 Chromoting 释放后使用 CVE-2026-76017

Chrome 稳定通道博文日期 **2026-08-20**；HKCERT 安全通报日期 **2026-08-21**。NVD：Google Chrome **151.0.7922.173 之前** 的 Chromoting 存在释放后使用（Chromium 严重级别 Critical），特制网络流量可能导致沙箱外远程代码执行。

HKCERT 列受影响版本：Android／Linux 低于 **151.0.7922.173**；Windows／macOS 低于 **151.0.7922.173／.174**。处置：更新 Chrome 并重启。本轮抓取的 NVD SSVC 快照将 exploitation 标为 **none**。JSON 未见公开 IoC。

地址：
- 厂商（Chrome 稳定通道）：https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-desktop_0404570826.html
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-76017
- HKCERT（2026-08-21）：https://www.hkcert.org/security-bulletin/google-chrome-multiple-vulnerabilities_20260821

IoC：未见公开 IoC。

### 3. 【晚报新报／下午漏报】SPIP 预认证 RCE CVE-2026-77806（未入 KEV）

厂商博文 **2026-08-20**；NVD published **2026-08-21**。SPIP **4.4.21 之前**：未认证远程代码执行。厂商：**4.4.21** 修复一条**通用预认证 RCE**（**4.4.20 亦中**）；**安全屏挡不住**；经 **ANSSI** 报告，厂商写明已观察到利用尝试。CVE 正文称 **2026 年 8 月在野利用**。本轮抓取的 NVD CISA-ADP SSVC 快照仍将 exploitation 标为 **none**（与厂商／CVE 措辞冲突）。CISA KEV catalogVersion **2026.08.21**（1674 条）**未见此条**，**不当成 KEV 事实**。补丁：升级至 **4.4.21**。狩猎：只查意外的 **X-Spip-Filtre** HTTP 请求头（**只记头名**，不写过滤表达式或复现）。本晚报不转载 SPIP 过滤相关复现材料。

地址：
- 厂商（SPIP 2026-08-20）：https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-77806
- CVE 记录：https://www.cve.org/CVERecord?id=CVE-2026-77806

IoC：未见公开 IoC。


### 4. 【晚报更新】Microsoft Entra ID 反序列化 RCE CVE-2026-69836（云侧已缓解；走回已核验）

Help Net Security **2026-08-21** 转述微软：Entra ID 对不可信数据反序列化，可使未授权攻击者经网络执行代码（CVE-2026-69836，报道 CVSS 10.0）。微软称托管云服务**已经全面缓解**，**客户无需打补丁、无客户侧补丁包**。披露日期按二手来源为 2026-08-20。

下午草稿因 BleepingComputer 页超时，只写「利用状态有争议」。**晚间重抓成功，走回现已核验**：BleepingComputer **2026-08-22 02:56 EDT** 更新称，微软表示曾**误将该 CVE 标为已利用**。Cybersecurity Dive：MSRC 起初写已利用，**周五更新称无利用**，未解释状态变更原因。因此本报按核验后口径：**不要写成已核实在野利用**。**未入 KEV**。防御：审阅 Entra 登录与特权角色日志。JSON 未见公开 IoC。

地址：
- 厂商 MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-69836
- 文章（BleepingComputer，走回已核验）：https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- 文章（Cybersecurity Dive）：https://www.cybersecuritydive.com/news/microsoft-maximum-severity-flaw-entra-id-exploitation/828501/
- 文章（Help Net Security 2026-08-21）：https://www.helpnetsecurity.com/2026/08/21/microsoft-entra-id-vulnerability-cve-2026-69836/
- X（走回／误标，@windowsforum）：https://x.com/windowsforum/status/2091167299881365611
- X（链到 MSRC，@VixWizzer）：https://x.com/VixWizzer/status/2091185783340491186
- 注：@Npj8448 仍复述已利用——相对已核验走回视为过时，不当成事实。https://x.com/Npj8448/status/2091171456755577069
- X（晚间 @SecureChap；写早期咨询有误，不重写成已利用）：https://x.com/SecureChap/status/2091314748805505224
- X（晚间 @NeriaBasha 仍写在野——对照已核走回，不当成事实）：https://x.com/NeriaBasha/status/2091306011290136745

IoC：未见公开 IoC。


### 5. 【续报／仍有效】CISA KEV TrueConf Server CVE-2026-72529 与 CVE-2026-72530（BC 8/21 跟进；**72529 联邦期限明日 2026-08-23**）

已见 8/20 晚报。CISA 于 **2026-08-20** 将两条列入 KEV。BleepingComputer **2026-08-21** 跟进联邦补丁令。

- **CVE-2026-72529**：缺认证；联邦期限 **2026-08-23（明日）**。
- **CVE-2026-72530**：代码注入／隔离环境逃逸；联邦期限 **2026-09-03**。

未授权远程攻击者在可访问 **TCP/4307** 时可影响 TrueConf Server。补丁：**5.3.9**、**5.4.9** 或 **5.5.5**。Kaspersky ICS CERT 与 BleepingComputer 称 **Head Mare** 使用该组合植入 webshell，并以 **PhantomCore** 包替换客户端安装程序——仅高阶点名，**不写战役剧本、不写链式步骤**。狩猎：盘点暴露的 4307/TCP；曾暴露主机按可能已被预入侵处置。JSON 未见公开 IoC。

地址：
- CISA 警报（2026-08-20，新增两条）：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD CVE-2026-72529：https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- Kaspersky ICS CERT：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- 文章（BleepingComputer 2026-08-21）：https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-actively-exploited-trueconf-server-flaws/
- X（晚间 @Joe_Biden_ja）：https://x.com/Joe_Biden_ja/status/2091300354642051238

IoC：未见公开 IoC。

### 6. 【续报／仍有效】crates.io 供应链：arrayref／internment／append-only-vec ＋ proc-macro1（CVE-2026-77651／77649／77650）

已见 8/20 晚报。Rust Security Response Team 确认 crates.io 维护者账号失陷。恶意版本 **arrayref 0.3.10**（约 86 分钟）、**internment 0.8.7**（约 90 分钟）、**append-only-vec 0.1.9**（约 107 分钟）依赖 typosquat **proc-macro1**，其 **build.rs** 在编译期下载载荷。相关 crate **proc-macro1**、**proc-macro-en**、**aovine**、**arone**、**aronenao**、**tinymember** 已删除。NVD 发布 2026-08-20，last modified **2026-08-21**。

最后安全版本：**arrayref 0.3.9**、**internment 0.8.6**、**append-only-vec 0.1.8**。防御：检查 Cargo.lock 与 cargo 缓存；拦截既有 23.254.165.112:9089 与 :443，以及晚间 Wiz 额外指标；在解析过恶意版本的构建机上轮换机密。不转载复现步骤。

晚间跟进：Wiz 指出基础设施与 **Sapphire Sleet／UNC1069** 活动**有重叠**（SecurityWeek 转述；晚间备援注明 Wiz 页抓取超时、SecurityWeek 综述已核）。**重叠不等于单独归因，不据此单独写成朝鲜／DPRK 行动。**

地址：
- 厂商（Rust 官方 2026-08-20）：https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- NVD CVE-2026-77651：https://nvd.nist.gov/vuln/detail/CVE-2026-77651
- NVD CVE-2026-77649：https://nvd.nist.gov/vuln/detail/CVE-2026-77649
- NVD CVE-2026-77650：https://nvd.nist.gov/vuln/detail/CVE-2026-77650
- GitHub RustSec：https://github.com/rustsec/advisory-db/issues/3161
- 文章（JFrog）：https://research.jfrog.com/post/arrayref-proc-macro1-crates-io/
- 文章（Wiz）：https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns
- 文章（SecurityWeek）：https://www.securityweek.com/rust-supply-chain-attack-linked-to-north-korean-hackers/
- X 事后分析（@blackanger）：https://x.com/blackanger/status/2091204794929328537

IoC（照录本轮 JSON ＋ 晚间 Wiz 额外狩猎）：
- 23.254.165.112:9089
- 23.254.165.112:443
- https://23.254.165.112:9089/
- /tmp/rust-setup
- arrayref@0.3.10
- internment@0.8.7
- append-only-vec@0.1.9
- proc-macro1@1.0.107
- https://23.254.165.112:9089/rust-crate_0.1.0
- https://23.254.165.112:9089/rust-crate_0.2.0
- https://23.254.165.112:9089/rust-crate_0.3.0
- https://23.254.165.112:9089/rust-crate_0.4.0
- %TEMP%\\rust-setup.ps1
- %TEMP%\\rust-setup-launch.vbs
- proc-macro-en@1.0.10
- 23.254.167.107:443
- hwsrv-798836.hostwindsdns.com
- POST /49890878
- SHA256 25ad700976873c76af785cb99b33c48db7df8b81f21d1e9e06b3676b9a9373ae（arrayref-0.3.10.crate）
- 61198155da51b838772eecf5bfaac6cbc4dcc388dccc56658fc28a8e831b34d4（proc-macro1-1.0.107.crate）
- b5c1b5b0763a8809a644a8f92224653f0aca623a98eecc714d27f74b80fbe436（proc-macro1-1.0.106.crate）

### 7. 【续报／仍有效】CISA ICS ICSA-26-232-01 Johnson Controls Simplex Incident Manager CVE-2026-27875

已见 8/20 晚报。CISA 于 **2026-08-20** 转载 Johnson Controls JCI-PSA-2026-28。Simplex Incident Manager **≤ V2.01** 在内存中明文存放口令与认证令牌（CVE-2026-27875，CVSS 3.1 **5.8**）。需**本地低权限**才能提取凭据。厂商补丁 **v2.01.01**。CISA：发布时未见已知公开利用；**不可远程利用**。限制本地访问，监控内存转储类工具。本轮备援注明：**未见 2026-08-21／22 的 CISA 警报或 ICS**。JSON 未见公开 IoC。本轮 NVD 页未列入该 CVE 的 sources_checked，不编造 NVD URL。

地址：
- CISA ICS：https://www.cisa.gov/news-events/ics-advisories/icsa-26-232-01
- 厂商：https://www.johnsoncontrols.com/trust-center/cybersecurity/security-advisories

IoC：未见公开 IoC。

### 8. 厂商窗口核对（Adobe／Fortinet／Ivanti）

本轮备援核对：未见 Adobe 2026-08-21／22 公告；未见 Fortinet／Ivanti 2026-08-21／22 咨询。**本日无显著更新。**

地址：
- Adobe 公告索引：https://helpx.adobe.com/security/security-bulletin.html
- Ivanti 2026 年 8 月安全更新博文（窗口内核对、无 8/21–22 新条）：https://www.ivanti.com/blog/august-2026-security-update
- FortiGuard PSIRT 索引：https://www.fortiguard.com/psirt

IoC：未见公开 IoC。


### 9. 【晚报更新／X 补录】GitLab GraphQL 指令 CVE-2026-19478（数据完整性；非已确认 RCE；仍未入 KEV）

GitHub Advisory **GHSA-6whr-xjjm-6pf8** 发布于 **2026-08-17**。厂商博客给出 CVSS **9.4**。影响 GitLab CE/EE：**18.2** 起至 **18.11.11** 之前、**19.0** 至 **19.0.8** 之前、**19.1** 至 **19.1.6** 之前、**19.2** 至 **19.2.4** 之前。补丁：**18.11.11／19.0.8／19.1.6／19.2.4**。GitLab.com 与 Dedicated **已经打补丁**。影响：未认证攻击者可经 GraphQL **指令**修改或删除公开项目与用户数据。**不要写成已确认 RCE**；厂商影响是**数据完整性**。本晚报不写 GraphQL 查询体或利用样例。

晚间公开跟进：SecurityWeek／GovInfoSecurity 转述 **WatchTowr** 蜜罐在披露约 **2 日**后见到探测（披露 2026-08-17）。狩猎：Web 日志中含 **@gl_introduced** 的请求；限制未认证 **`/api/graphql`** 或公开仓库访问。下午 X（@Lumideezy／@RicardGardella）称在野；本轮 CISA KEV catalogVersion **2026.08.21** **未见此条**，**不当成 KEV 事实**。NVD CISA-ADP SSVC 快照仍将 exploitation 标为 **none**。

地址：
- X（@Lumideezy）：https://x.com/Lumideezy/status/2091183159119344010
- X（@RicardGardella）：https://x.com/RicardGardella/status/2091181002550833526
- X（晚间 @SOCMinute）：https://x.com/SOCMinute/status/2091312387458486331
- GitHub Advisory：https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- 厂商补丁说明：https://docs.gitlab.com/releases/patches/patch-release-gitlab-19-2-4-released
- 文章（SecurityWeek）：https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/
- 文章（GovInfoSecurity）：https://www.govinfosecurity.com/gitlab-code-injection-flaw-exploited-in-wild-a-32606
- 文章（OX Security）：https://www.ox.security/blog/gitlab-graphql-cve-2026-19478-19650/

IoC：未见公开 IoC。

### 10. 【X 补录／回流】WordPress 登录页预认证反射型 XSS CVE-2026-64638（官方 7.0.3，2026-08-06）

官方 WordPress **7.0.3** 安全发布日期 **2026-08-06**；X 本日回流，**不是今天才披露**。预认证反射型 XSS 出现在登录页。完整 PHP 执行路径需要**已登录管理员**与攻击者页面交互（社会工程）。**不可蠕虫化**。补丁：**7.0.3** 及受维护分支回移植至 **4.7**。本晚报**不抄利用链步骤**。

地址：
- X（@fiona_novesai）：https://x.com/fiona_novesai/status/2091163963094376488
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-64638
- GHSA：https://github.com/WordPress/wordpress-develop/security/advisories/GHSA-52p2-r8wf-jcrf
- 厂商：https://wordpress.org/news/2026/08/wordpress-7-0-3-release/
- 文章（Pwn.ai，不抄链）：https://pwn.ai/blog/xss2shell
- 文章（The Hacker News）：https://thehackernews.com/2026/08/new-wordpress-pre-auth-xss-could-lead.html

IoC：未见公开 IoC。

### 11. 【X 补录】Unisoc VoLTE 视频通话链（SSD／THN／Dark Reading；仅高阶）

仅高阶：VoLTE **视频通话**加上调制解调器隔离问题，可在部分 Unisoc 芯片组上到达 Android 内核。二手报道提及 **T606／T612／T616／T7250**。截至 8 月中旬报道：**未见厂商补丁、那些报道中未见 CVE**。受害语境：用户**接听视频通话**即可。本晚报不抄信令、地址或复现材料。

地址：
- X（@LifeboatHQ）：https://x.com/LifeboatHQ/status/2091178860662432007
- 文章（The Hacker News）：https://thehackernews.com/2026/08/unisoc-volte-video-call-exploit-chain.html
- 文章（Dark Reading）：https://www.darkreading.com/mobile-security/video-call-exploit-chains-two-flaws-unisoc-modems
- SSD Advisory：https://ssd-disclosure.com/unisoc-t612-lpe/

IoC：未见公开 IoC。

### 12. 【可选／非核心】The Sandbox 跨链桥（加密，非本报核心）

X 本日转 The Defiant：The Sandbox 称已遏制桥上利用，曾在 Base 与 BNB Smart Chain 上铸造无抵押 SAND。非本报核心条目。https://thedefiant.io/news/hacks/the-sandbox-says-it-contained-bridge-exploit-that-minted-unbacked-sand-on-base-and-bsc

IoC：未见公开攻击者 IoC（不把交易所／项目站当 IoC）。

### 13. 【晚报新报／X 本日回流】Elementor Pro Forms File Upload CVE-2026-32475（未当在野）

X 本日回流。Elementor Pro **CVE-2026-32475**（CVSS **9.0**）：Forms **File Upload** 未认证文件上传可导致远程代码执行。影响 **≤4.2.1**，且仅当已发布表单包含 File Upload 字段时。补丁：**4.2.2**（**2026-08-19**）。狩猎：在 `wp-content/uploads/elementor/forms/` 查找意外 PHP。本晚报不描述绕过细节。Patchstack 咨询（8/19）经二手综述：**未见已确认大规模利用**——**不要写成在野事实**。JSON 未见公开 IoC。

地址：
- X（@so_sthbryan）：https://x.com/so_sthbryan/status/2091309190312861982
- Patchstack：https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-32475

IoC：未见公开 IoC。


### 14. 【窗口前／本日回流】LiteSpeed cPanel 插件 CVE-2026-48172（2026 年 5 月；当时已利用）

**真实漏洞，但是 2026 年 5 月**（当时已被利用；CISA KEV 约 **2026-05-26**）。标签：**窗口前／本日回流**。已认证 cPanel 用户可提升至 **root**。补丁：用户端插件 **2.4.5+**；建议 **2.4.7** 并配合 WHM **5.3.1.0**。狩猎：日志中出现 `cpanel_jsonapi_func=redisAble`（**只记该串名**，不写利用步骤）。JSON 未见公开 IoC。

地址：
- X（@blueteamsec1）：https://x.com/blueteamsec1/status/2091309750063611943
- GHSA：https://github.com/advisories/GHSA-fxrh-cwjh-m33v
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-48172

IoC：未见公开 IoC。


### 15. 【晚报新报】NetScaler ADC／Gateway 认证绕过 CVE-2026-19490（CVSS 4.0 9.3）

Citrix 安全公告；Help Net Security **2026-08-21**。**CVE-2026-19490** 为认证绕过（报道 CVSS 4.0 **9.3**），影响 Gateway／AAA（较新构建有 **SAML 前置条件**）。补丁：**14.1-73.32**、**13.1-63.21**、FIPS **14.1-73.32**／**13.1-37.277**。同一 Citrix 公告另覆盖 **CVE-2026-19489**——本报不编造该 CVE 的细节。本晚报不抄配置侧利用路径。JSON 未见公开 IoC。

地址：
- X（@bbnetman）：https://x.com/bbnetman/status/2091287599935619182
- 厂商（Citrix CTX696939）：https://support.citrix.com/external/article/CTX696939/netscaler-adc-and-netscaler-gateway-secu.html
- 文章（Help Net Security 2026-08-21）：https://www.helpnetsecurity.com/2026/08/21/citrix-netscaler-gateway-cve-2026-19490/
- 文章（Rapid7）：https://www.rapid7.com/blog/post/etr-cve-2026-19490-critical-vulnerability-affecting-citrix-netscaler-adc-and-netscaler-gateway/

IoC：未见公开 IoC。


## 工具与 GitHub 发布

### 1. 【本窗口新报】Truffle Security：768 枚仍有效的企业 AWS root／管理员密钥

Truffle Security 博文 front-matter **2026-08-21 15:15 UTC**；BleepingComputer **2026-08-21 11:55**。Truffle 于 2026-08-10 复验 10616 组完整泄露 AWS 密钥对，其中 88% 仍可认证。在 817 枚与企业关联的有效密钥中，526 枚为 root、242 枚为 IAM AdministratorAccess，合计 **768** 枚可完全控制企业账户的密钥。可枚举密钥年龄中位数 **1831** 天。Hugging Face 为最大来源（8482 枚唯一密钥）。**未公布任何密钥材料。**

防御（厂商／报道建议，非利用）：删除 root 访问密钥；轮换曾被公开提交过的密钥；关注 **AWSCompromisedKeyQuarantine**；设置预算告警。BleepingComputer **2026-08-22** 所载 AWS 声明：会通知客户，并可能隔离已暴露密钥。工具侧可对照公开仓 TruffleHog（扫描／发现，不是利用步骤）。JSON 未见公开 IoC。

地址：
- 厂商（Truffle Security）：https://trufflesecurity.com/blog/leaked-corporate-aws-keys-held-full-admin-rights
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/hundreds-of-leaked-aws-keys-give-full-control-over-corporate-accounts/
- GitHub：https://github.com/trufflesecurity/trufflehog

IoC：未见公开 IoC。

### 2. 红队框架／nuclei 版本

projectdiscovery/nuclei-templates 最新标签仍为 **v10.4.7**（2026-08-03）。本窗口未见已核验的 **nuclei／Sliver／Havoc／Mythic** 新版本。**本日无显著红队工具新版本。**

地址：
- GitHub 发布页：https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。

### 3. 【X 补录】Tencent AI-Infra-Guard v4.5.2（2026-08-17；仅 URL，未克隆）

Tencent 于 **2026-08-17** 发布 **v4.5.2**。仅记仓库与标签，**未克隆**。

地址：
- GitHub：https://github.com/Tencent/AI-Infra-Guard
- 发布标签：https://github.com/Tencent/AI-Infra-Guard/releases/tag/v4.5.2
- X（@7uanF）：https://x.com/7uanF/status/2091171187292254716

IoC：未见公开 IoC。

### 4. 【X 补录】Harden-Windows-Security（仅 URL，未克隆）

开源 Windows 加固工具集。仅记 URL，**未克隆**。

地址：
- GitHub：https://github.com/HotCakeX/Harden-Windows-Security
- X（@RoundtableSpace）：https://x.com/RoundtableSpace/status/2091212553229586450

IoC：未见公开 IoC。

### 5. 【X 补录】Cyberful（仅 URL，未克隆）

开源 AI 红队工具。仅记 URL，**未克隆**。

地址：
- GitHub：https://github.com/cyberful/cyberful
- X（@ottaviofogliata）：https://x.com/ottaviofogliata/status/2091168839840960983

IoC：未见公开 IoC。

### 6. 【X 补录】HTScanner V2.1（仅 URL，未克隆）

X 宣布 V2.1。**未克隆、仅记 URL**。

地址：
- GitHub：https://github.com/HackingTeamOficial/HTScanner
- X（@HackingTeam77）：https://x.com/HackingTeam77/status/2090913065495597075

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. 【续报／仍有效】Cisco Talos UAT-10147 与 SPECTRE（2026-08-20 06:00；仅高阶）

已见 8/20 晚报；本窗口无新 Talos 主文。Talos 于 **2026-08-20 06:00** 发布两篇报告：中文语境、以牟利为动机的集群 **UAT-10147**，针对互联网暴露的 Windows **IIS** 与 **Linux Web** 服务器，用于 SEO 欺诈与窃取；回收目标清单约 **170000** URL。

工具／家族仅记名称（不抄利用手册）：Metasploit、ysoserial、PentestGPT、DeepAudit、Potato LPE、BadIIS、QuasarRAT、Gh0stCringe、Noodle RAT、Meterpreter，以及自定义 **SPECTRE**（BYOVD 致盲 EDR；Linux Specter rootkit 伪装 **acpi_pad.ko**）。狩猎线索（高阶）：C2 **139.180.197.150**、域名 **adminapi.tippusoni.in**／**kl21177.com**、计划任务名 **Google Chrome Start**，以及 Talos IoC 文件中的哈希。本晚报不转载利用 how-to。

地址：
- Talos 主文：https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- Talos SPECTRE：https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- GitHub IoC：https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt
- Cisco-Talos/IOCs 仓：https://github.com/Cisco-Talos/IOCs
- X 周报复述（@DFIR_Radar，已有条目只加链）：https://x.com/DFIR_Radar/status/2091171217667498073

IoC（照录本轮 JSON）：
- adminapi.tippusoni.in
- kl21177.com
- 139.180.197.150
- 18.140.163.186
- https://adminapi.tippusoni.in/4/pr.exe
- https://adminapi.tippusoni.in/4/prcc2.txt
- https://adminapi.tippusoni.in/4/prcc2.rar
- https://adminapi.tippusoni.in/4/dll.zip
- https://adminapi.tippusoni.in/4/user.txt
- https://adminapi.tippusoni.in/4/back.txt
- https://adminapi.tippusoni.in/4/bai.txt
- https://adminapi.tippusoni.in/4/svchosts.exe
- https://adminapi.tippusoni.in/5/pr.exe
- https://adminapi.tippusoni.in/5/bai.txt
- https://adminapi.tippusoni.in/5/svchosts.exe
- https://kl21177.com/1/prcc1.rar
- https://kl21177.com/1/dll.zip
- https://kl21177.com/1/user.bat
- http://139.180.197.150:54321/4/pr.exe
- http://139.180.197.150:54321/4/bai.txt
- http://139.180.197.150:54321/4/svchosts.exe
- 175e83adc721cd7d634ebd2c63fb8d2404c009067bc7719ef02c5d1f9d81e9a1
- 1f0496ad392b5b9edf9e59a56af4d8e17638ddbb12e086f104d9a0f316ad59a1
- 37cabc04da36e710dd4aee8609ab7553c039a54dd085460854e9ddb49b0e7032
- 50232092004b9ad335e1e72e3a6dcfde93c4470007ddfcc637e6e5f899f68be0
- 73b272612cec9e03a7e2f7516ece600fb1b45b719fa9d93b382ed25ec314e5c0
- 9fa27b231502d6d33441ab54227da50cbd325847ce2272f9c0e79b4ea873e432
- cfce59111338701b2990be9aadc80166ac0618cb57483d6a065f1e2526a34494
- fbe9c6052d7261bd252322e155d86bd370340f1fbb2b0a1e9c7b444f6275614a
- 00892f276299a13721642e8a9bcbcb949a658547c6c8271866a1997b79f1e5c5
- 23a83c6bbdd7d6c09a5187338065d15f2a90a252772813cba83b9818aa56cef7
- 8280502c2c6902e61fc4c02a9a81b4720688449a5bca3d89dbd1e2edd507c69a
- d190b349d791267a9583ba9f4a1ab0e4199d1a3abfd4dae514ed5def0754ba94


### 2. 【X 补录／BC 2026-08-22】Android 车机头单元 BADBOX／MoYu／DoFun／TWCore

BleepingComputer **2026-08-22** 与 Kaspersky 主文：针对 **Android 车机头单元** 的感染链（报道称属首次为此类设备构建）。归属 **BADBOX／MoYu**。MQTT **cardoor.cn**；恶意软件 **JarService**；代理模块 **zhima**；**TWCore**。用途：广告欺诈／住宅代理。DoFun 称已处理。高阶模块名可记，**不写样本内容**。BC 页**无哈希**。

地址：
- Kaspersky（主文）：https://www.kaspersky.com/blog/car-botnet-malware-for-head-units-with-android/56296/
- 文章（BleepingComputer）：https://www.bleepingcomputer.com/news/security/hackers-infect-android-car-head-units-with-proxy-botnet-malware/
- X（@trubetech）：https://x.com/trubetech/status/2091170347986870296

IoC（照录公开域名）：
- cardoor.cn

### 3. 【X 补录／回流】Unit 42 DeepSeek ＋ Hermes Agent（knaithe／KnYuan；不是 UAT-10147）

7 月／8 月初研究，X 本日回流。**与 UAT-10147 不是同一活动，勿合并。** 高阶：中文语境投机型运营者；经 Hermes 调用 DeepSeek；Telegram 编排；部分目标上自主侦察失败；人工活动有实际影响。

地址：
- 厂商（Unit 42）：https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/
- X（@dongwukeji）：https://x.com/dongwukeji/status/2091154770127912980
- X（@realhisaacbrown）：https://x.com/realhisaacbrown/status/2091204594810409147

IoC：未见公开 IoC。

### 4. 【X 补录／回流】Sonatype 2026-08-10（X 本日回流）

六个包名见文末 IoC 汇总。优先引用 Sonatype 博文。

地址：
- 厂商（Sonatype）：https://www.sonatype.com/blog/six-npm-packages-use-ethereum-transactions-to-retrieve-malicious-payloads
- X（@blueteamsec1）：https://x.com/blueteamsec1/status/2091185590666695006

IoC：见文末包名列表。

### 未独立核验（勒索／泄密广告；仅 X 声称）

下列仅为 X 广告／声称，**未独立核验**。**不把受害站点当作 IoC。** 未见公开攻击者 IoC。

- EMPERADOR 声称 EVNHANOI（越南电力）：https://x.com/FalconFeedsio/status/2091215618532159789
- Storm 声称 The Cecilian Bank：https://x.com/FalconFeedsio/status/2091168478669459806
- coinbasecartel 声称清单：https://x.com/ThreatAtlas/status/2091188279487897805 https://x.com/ThreatAtlas/status/2091168535456215168 https://x.com/ThreatAtlas/status/2091165333037949174 https://x.com/ThreatAtlas/status/2091164245027098895
- FONASA 约 73.2 万条（声称）：https://x.com/CyberPulse56/status/2091200677137772975
- TELUS 约 67.2 万条（声称）：https://x.com/CyberPulse56/status/2091174010881016127
- LegalWise（声称）：https://x.com/DailyDarkWeb/status/2091208335886266851
- RAMED（声称）：https://x.com/CyberPulse56/status/2091175068261130499
- TheHatman（SecurityWeek **2026-08-17** 回流）：https://x.com/gagansuie/status/2091186891638866074

IoC：未见公开攻击者 IoC。

### 未核验／仅声称（晚间 X；短小节）

下列仅为 X 声称或单源转述，**未独立核验**。不把受害站点当 IoC。

- omarchy 两击 0-day 声称（@mdisec，无 CVE）：https://x.com/mdisec/status/2091293921468932420
- SilkParasite China-nexus 针对中亚政府：仅 DailyDarkWeb，无厂商文：https://x.com/DailyDarkWeb/status/2091294232346542234
- LockBit 将 U.S. Bank 列入泄露站；银行称暂未见失陷证据：https://x.com/DailyDarkWeb/status/2091221874562761174
- 暗网声称 OWA＋Zimbra 1-day XSS：https://x.com/DailyDarkWeb/status/2091227505843749120
- Loginsoft 称 77.90.185.20 与 CVE-2026-23744 相关（仅抄 X，未独立核样本）：https://x.com/Loginsoft_Intel/status/2091276903374327859 https://cti.loginsoft.com/ip/77.90.185.20


## 地址／IoC 汇总

### 本窗口新报条目（Zimbra 新入 KEV／Chrome／Entra／AWS 密钥／SPIP／GitLab 晚间跟进／Elementor／NetScaler；LiteSpeed 为窗口前回流）
- 未见公开 IoC（SPIP／GitLab／Entra／Zimbra／Chrome／AWS 密钥／Elementor／LiteSpeed／NetScaler JSON `iocs` 为空；77.90.185.20 见下方 X 补录，未独立核验）

### X 补录新增 IoC
- 77.90.185.20（X／Loginsoft 所称，**未独立核验**；与 CVE-2026-23744 相关之声称）
- cardoor.cn
- @kolbo/mcp
- agentgui
- godot-kit
- envpack-conf
- postcss-initial-provider
- tailwindcss-motion-advanced
- GitLab／WordPress／Unisoc／Entra／Zimbra X 补录条目：未见公开 IoC

### crates.io 供应链（照录本轮 JSON）
- 23.254.165.112:9089
- 23.254.165.112:443
- https://23.254.165.112:9089/
- /tmp/rust-setup
- arrayref@0.3.10
- internment@0.8.7
- append-only-vec@0.1.9
- proc-macro1@1.0.107
- https://23.254.165.112:9089/rust-crate_0.1.0
- https://23.254.165.112:9089/rust-crate_0.2.0
- https://23.254.165.112:9089/rust-crate_0.3.0
- https://23.254.165.112:9089/rust-crate_0.4.0
- %TEMP%\\rust-setup.ps1
- %TEMP%\\rust-setup-launch.vbs
- proc-macro-en@1.0.10

- 23.254.167.107:443
- hwsrv-798836.hostwindsdns.com
- POST /49890878
- SHA256 25ad700976873c76af785cb99b33c48db7df8b81f21d1e9e06b3676b9a9373ae（arrayref-0.3.10.crate）
- 61198155da51b838772eecf5bfaac6cbc4dcc388dccc56658fc28a8e831b34d4（proc-macro1-1.0.107.crate）
- b5c1b5b0763a8809a644a8f92224653f0aca623a98eecc714d27f74b80fbe436（proc-macro1-1.0.106.crate）

### UAT-10147／SPECTRE（照录本轮 JSON）
- adminapi.tippusoni.in
- kl21177.com
- 139.180.197.150
- 18.140.163.186
- https://adminapi.tippusoni.in/4/pr.exe
- https://adminapi.tippusoni.in/4/prcc2.txt
- https://adminapi.tippusoni.in/4/prcc2.rar
- https://adminapi.tippusoni.in/4/dll.zip
- https://adminapi.tippusoni.in/4/user.txt
- https://adminapi.tippusoni.in/4/back.txt
- https://adminapi.tippusoni.in/4/bai.txt
- https://adminapi.tippusoni.in/4/svchosts.exe
- https://adminapi.tippusoni.in/5/pr.exe
- https://adminapi.tippusoni.in/5/bai.txt
- https://adminapi.tippusoni.in/5/svchosts.exe
- https://kl21177.com/1/prcc1.rar
- https://kl21177.com/1/dll.zip
- https://kl21177.com/1/user.bat
- http://139.180.197.150:54321/4/pr.exe
- http://139.180.197.150:54321/4/bai.txt
- http://139.180.197.150:54321/4/svchosts.exe
- 175e83adc721cd7d634ebd2c63fb8d2404c009067bc7719ef02c5d1f9d81e9a1
- 1f0496ad392b5b9edf9e59a56af4d8e17638ddbb12e086f104d9a0f316ad59a1
- 37cabc04da36e710dd4aee8609ab7553c039a54dd085460854e9ddb49b0e7032
- 50232092004b9ad335e1e72e3a6dcfde93c4470007ddfcc637e6e5f899f68be0
- 73b272612cec9e03a7e2f7516ece600fb1b45b719fa9d93b382ed25ec314e5c0
- 9fa27b231502d6d33441ab54227da50cbd325847ce2272f9c0e79b4ea873e432
- cfce59111338701b2990be9aadc80166ac0618cb57483d6a065f1e2526a34494
- fbe9c6052d7261bd252322e155d86bd370340f1fbb2b0a1e9c7b444f6275614a
- 00892f276299a13721642e8a9bcbcb949a658547c6c8271866a1997b79f1e5c5
- 23a83c6bbdd7d6c09a5187338065d15f2a90a252772813cba83b9818aa56cef7
- 8280502c2c6902e61fc4c02a9a81b4720688449a5bca3d89dbd1e2edd507c69a
- d190b349d791267a9583ba9f4a1ab0e4199d1a3abfd4dae514ed5def0754ba94

### TrueConf／Johnson Controls／Chrome／Entra／AWS 密钥
- 未见公开 IoC

### 参考 URL（情报页，非恶意基础设施）
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-232-01
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- https://nvd.nist.gov/vuln/detail/CVE-2026-77651
- https://nvd.nist.gov/vuln/detail/CVE-2026-77649
- https://nvd.nist.gov/vuln/detail/CVE-2026-77650
- https://nvd.nist.gov/vuln/detail/CVE-2026-76017
- https://nvd.nist.gov/vuln/detail/CVE-2026-69836
- https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/
- https://chromereleases.googleblog.com/2026/08/stable-channel-update-for-desktop_0404570826.html
- https://www.hkcert.org/security-bulletin/google-chrome-multiple-vulnerabilities_20260821
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- https://www.helpnetsecurity.com/2026/08/21/microsoft-entra-id-vulnerability-cve-2026-69836/
- https://trufflesecurity.com/blog/leaked-corporate-aws-keys-held-full-admin-rights
- https://www.bleepingcomputer.com/news/security/hundreds-of-leaked-aws-keys-give-full-control-over-corporate-accounts/
- https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-actively-exploited-trueconf-server-flaws/
- https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- https://research.jfrog.com/post/arrayref-proc-macro1-crates-io/
- https://github.com/rustsec/advisory-db/issues/3161
- https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- https://github.com/Cisco-Talos/IOCs
- https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt
- https://github.com/trufflesecurity/trufflehog
- https://github.com/projectdiscovery/nuclei-templates/releases
- https://www.johnsoncontrols.com/trust-center/cybersecurity/security-advisories
- https://helpx.adobe.com/security/security-bulletin.html
- https://www.ivanti.com/blog/august-2026-security-update
- https://www.fortiguard.com/psirt
- https://x.com/Lumideezy/status/2091183159119344010
- https://x.com/RicardGardella/status/2091181002550833526
- https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- https://nvd.nist.gov/vuln/detail/CVE-2026-19478
- https://docs.gitlab.com/releases/patches/patch-release-gitlab-19-2-4-released
- https://www.ox.security/blog/gitlab-graphql-cve-2026-19478-19650/
- https://x.com/fiona_novesai/status/2091163963094376488
- https://www.cve.org/CVERecord?id=CVE-2026-64638
- https://github.com/WordPress/wordpress-develop/security/advisories/GHSA-52p2-r8wf-jcrf
- https://wordpress.org/news/2026/08/wordpress-7-0-3-release/
- https://pwn.ai/blog/xss2shell
- https://thehackernews.com/2026/08/new-wordpress-pre-auth-xss-could-lead.html
- https://x.com/LifeboatHQ/status/2091178860662432007
- https://thehackernews.com/2026/08/unisoc-volte-video-call-exploit-chain.html
- https://www.darkreading.com/mobile-security/video-call-exploit-chains-two-flaws-unisoc-modems
- https://ssd-disclosure.com/unisoc-t612-lpe/
- https://x.com/windowsforum/status/2091167299881365611
- https://x.com/VixWizzer/status/2091185783340491186
- https://x.com/Npj8448/status/2091171456755577069
- https://x.com/DFIR_Radar/status/2091194165581553672
- https://x.com/DFIR_Radar/status/2091194167502537139
- https://socradar.io/blog/cve-2026-73570-zimbra-rce/
- https://x.com/blackanger/status/2091204794929328537
- https://x.com/trubetech/status/2091170347986870296
- https://www.kaspersky.com/blog/car-botnet-malware-for-head-units-with-android/56296/
- https://www.bleepingcomputer.com/news/security/hackers-infect-android-car-head-units-with-proxy-botnet-malware/
- https://unit42.paloaltonetworks.com/autonomous-ai-cyber-attack-campaign/
- https://x.com/dongwukeji/status/2091154770127912980
- https://x.com/realhisaacbrown/status/2091204594810409147
- https://x.com/DFIR_Radar/status/2091171217667498073
- https://www.sonatype.com/blog/six-npm-packages-use-ethereum-transactions-to-retrieve-malicious-payloads
- https://x.com/blueteamsec1/status/2091185590666695006
- https://github.com/Tencent/AI-Infra-Guard
- https://github.com/Tencent/AI-Infra-Guard/releases/tag/v4.5.2
- https://x.com/7uanF/status/2091171187292254716
- https://github.com/HotCakeX/Harden-Windows-Security
- https://x.com/RoundtableSpace/status/2091212553229586450
- https://github.com/cyberful/cyberful
- https://x.com/ottaviofogliata/status/2091168839840960983
- https://github.com/HackingTeamOficial/HTScanner
- https://x.com/HackingTeam77/status/2090913065495597075
- https://thedefiant.io/news/hacks/the-sandbox-says-it-contained-bridge-exploit-that-minted-unbacked-sand-on-base-and-bsc

- https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- https://nvd.nist.gov/vuln/detail/CVE-2026-77806
- https://www.cve.org/CVERecord?id=CVE-2026-77806
- https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/
- https://www.govinfosecurity.com/gitlab-code-injection-flaw-exploited-in-wild-a-32606
- https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- https://www.cybersecuritydive.com/news/microsoft-maximum-severity-flaw-entra-id-exploitation/828501/
- https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns
- https://www.securityweek.com/rust-supply-chain-attack-linked-to-north-korean-hackers/

- https://x.com/so_sthbryan/status/2091309190312861982
- https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- https://www.cve.org/CVERecord?id=CVE-2026-32475
- https://x.com/blueteamsec1/status/2091309750063611943
- https://github.com/advisories/GHSA-fxrh-cwjh-m33v
- https://nvd.nist.gov/vuln/detail/CVE-2026-48172
- https://x.com/bbnetman/status/2091287599935619182
- https://support.citrix.com/external/article/CTX696939/netscaler-adc-and-netscaler-gateway-secu.html
- https://www.helpnetsecurity.com/2026/08/21/citrix-netscaler-gateway-cve-2026-19490/
- https://www.rapid7.com/blog/post/etr-cve-2026-19490-critical-vulnerability-affecting-citrix-netscaler-adc-and-netscaler-gateway/
- https://x.com/SecureChap/status/2091314748805505224
- https://x.com/NeriaBasha/status/2091306011290136745
- https://x.com/SOCMinute/status/2091312387458486331
- https://x.com/Joe_Biden_ja/status/2091300354642051238
- https://x.com/PCMedicalist/status/2091257477530574970
- https://x.com/mdisec/status/2091293921468932420
- https://x.com/DailyDarkWeb/status/2091294232346542234
- https://x.com/DailyDarkWeb/status/2091221874562761174
- https://x.com/DailyDarkWeb/status/2091227505843749120
- https://x.com/Loginsoft_Intel/status/2091276903374327859
- https://cti.loginsoft.com/ip/77.90.185.20

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
