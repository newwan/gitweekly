# X 安全情报晚报 · 2026-08-20

> 搜集窗口：约过去 24 小时（圣地亚哥时间 2026-08-19 20:35 至 2026-08-20 20:10，America/Santiago / UTC-4）
> 主源：X 已登录 Latest 后到（搜索 1 Latest 在 ~20:36Z 报错，窗口前约 20 小时 CVE 检索不全；搜索 2／3 覆盖完整）。公开备援已先出报，本节为 X 补录。不编造未核验 CVE。
> 公开备援：CISA KEV / CISA 警报与 ICS / NVD / Cisco Talos / Unit 42 / GitHub / StepSecurity / Wiz / BleepingComputer / CERT Polska
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。
> 说明：防御向晚报。不转载利用代码、payload 或复现步骤。UAT-10147 仅高阶（谁／打什么／补丁与狩猎），不抄利用手册。

## 今日摘要

- **CISA KEV catalogVersion 2026.08.20（1673 条，+2）**：新入 KEV 的是 TrueConf Server **CVE-2026-72529**（缺认证 CWE-306，dateAdded 2026-08-20，联邦期限 **2026-08-23**）与 **CVE-2026-72530**（代码注入／隔离环境逃逸 CWE-94，期限 **2026-09-03**）。勒索活动字段均为 Unknown。补丁 5.3.9／5.4.9／5.5.5。Kaspersky ICS 公告日期 2026-08-11（窗口前，仅作厂商细节）。不展开 Head Mare／PhantomCore。
- **crates.io 供应链投毒（2026-08-20 UTC）**：被劫持的 arrayref **0.3.10**／internment **0.8.7**／append-only-vec **0.1.9** 注入 typosquat **proc-macro1 1.0.107**。暴露窗口约 **07:11–09:25 UTC**。最后安全版本 0.3.9／0.8.6／0.1.8。Wiz 称基础设施与 DPRK／Sapphire Sleet／UNC1069 有重叠，**不据此单独归因**。
- **ICSA-26-232-01** Johnson Controls Simplex Incident Manager **CVE-2026-27875**（CWE-316，本地内存明文凭据，CVSS 3.1 5.8）。补丁 v2.01.01。CISA：不可远程利用，发布时未见已知公开利用。
- **Zimbra CVE-2026-73570**：BleepingComputer **2026-08-20** 英文转述 CERT Polska **2026-08-17** 通告。未认证 OS 命令注入（可选 zimbra-snmp + 通知 + swatchdog）。厂商补丁 ZCS **10.1.20**（**2026-07-20**）。本窗口未入 KEV。
- **Cisco Talos UAT-10147（2026-08-20 06:00）**：以牟利为动机的中文行为体集群，打互联网暴露的 IIS／Linux Web；行业政／教／媒／科技／游戏；已观察受害巴西／玻利维亚／中国／加拿大／越南。约 17 万 URL 目标清单。植入 BadIIS、QuasarRAT、Gh0stCringe、Noodle RAT、Meterpreter、SPECTRE。AI 辅助工具仅记名称（PentestGPT／DeepAudit），不抄利用手册。
- **Unit 42（2026-08-20）**：协作频道（Teams／Slack）身份滥用综述，复述既有案例，**不是新战役起点**。hooks.slack.com 是合法 webhook，不当恶意域名列。
- **工具**：nuclei-templates 仍为 v10.4.7（2026-08-03）。窗口内新见公开仓 flask-c2-server、Mimic、Doxbin-Botnet-Logs、blindaje-redteam、sentient-zero/research（仅 URL＋描述，未克隆）。
- **X 补录 Socket／Rust 官方 crates.io 文**：Socket 2026-08-20 与 Rust 官方确认 arrayref／internment／append-only-vec 投毒；补 SHA256 二阶段与 Aug 20–24 DGA 狩猎域名。
- **X 补录 Mythic LLDP／Kassandra／ET v11261**：Mythic C2 藏 LLDP Type-127 TLV；Rust Mythic agent Kassandra（未克隆）；Emerging Threats v11261（ClickFix／EtherHiding）。
- 短提醒（昨日已展开，不重复）：Ray **CVE-2025-62593** 仍在 KEV，联邦期限 **今日 2026-08-20**，窗口内无新 CISA 说明；8/18 四条 KEV **CVE-2026-33824／55040／59310／65400** 期限 **2026-08-21**。

## CVE / POC / 漏洞

### 1. CISA KEV 新列入 TrueConf Server 双洞（catalog 2026.08.20）

CISA 于 2026-08-20T17:00:27.8837Z 发布 catalogVersion **2026.08.20**，条目 **1673**（昨日 2026.08.19／1671，+2）。窗口内 dateAdded 2026-08-20 的两条均为 TrueConf Server，knownRansomwareCampaignUse=Unknown，经 TCP/**4307** 网络可达。厂商补丁：**5.3.9／5.4.9／5.5.5**。Kaspersky ICS CERT 公告页日期为 **2026-08-11**（窗口前，仅作厂商与 CWE／CVSS 细节，不把 8/11 当窗口内新发现）。本晚报不展开 Head Mare／PhantomCore（窗口前研究）。X 称在野投 PhantomCore（HeadMare）；Kaspersky ICS 8/11 已提狩猎，本日随 KEV 回流，不展开战役。未见公开 IoC。按 BOD 26-04 做联邦／云服务侧风险排序。本晚报不转载接口或复现步骤。

**CVE-2026-72529**（CWE-306，缺关键功能认证）：CNA Kaspersky Labs CVSS 3.1 **9.8**。未授权攻击者在网络可达 TCP/4307 时可调用未文档化关键功能并执行任意脚本。厂商受影响：<5.3；5.3.x<5.3.9；5.4.x<5.4.9；5.5.x<5.5.5。NVD published 2026-08-19，last modified 2026-08-20；CISA-ADP SSVC exploitation 于 2026-08-20T17:44:08Z 标为 active。联邦期限 **2026-08-23**。

**CVE-2026-72530**（CWE-94，代码注入／隔离环境逃逸）：CNA Kaspersky Labs CVSS 3.1 **9.0**。未授权攻击者经 TCP/4307 可用特制脚本脱离隔离环境并在宿主机执行任意代码。厂商受影响：<5.3.9；5.4.x<5.4.9；5.5.x<5.5.5。CISA-ADP SSVC exploitation 于 2026-08-20T17:44:03Z 标为 active。联邦期限 **2026-09-03**。与 72529 构成利用链，只记补丁版本，不写链式步骤。

地址：
- CISA 警报：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- CISA JSON：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- 厂商：https://trueconf.com/blog/news/security-fixes-updates-and-advisories
- NVD CVE-2026-72529：https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- NVD CVE-2026-72530：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- Kaspersky ICS（72529，2026-08-11）：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- Kaspersky ICS（72530，2026-08-11）：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-breakout-from-isolated-environment/
- BOD 26-04：https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-risk
- 文章：https://securityonline.info/trueconf-cve-2026-72529-exploited/

X：https://x.com/__kokumoto/status/2090574451628998676
X：https://x.com/Daily_CyberSec/status/2090552081023205651

IoC：未见公开 IoC。

### 2. ICSA-26-232-01 Johnson Controls Simplex Incident Manager CVE-2026-27875

CISA 于 **2026-08-20** 将 Johnson Controls PSA 转载为 **ICSA-26-232-01**。**CVE-2026-27875**：Simplex Incident Manager 在内存中以明文存放用户口令与认证令牌（CWE-316）。本地低权限攻击者可提取凭据。CVSS 3.1 **5.8**（MEDIUM）。厂商补丁 **v2.01.01**；CISA 正文亦写升级至 **v1.01.05** 或更高（按原文照录）。CISA：不可远程利用，攻击复杂度高；发布时未见已知公开利用。行业：关键制造、商业设施、政府服务与设施、交通、能源。NVD 页本轮未取到，不编造 NVD 链接。

地址：
- CISA ICS：https://www.cisa.gov/news-events/ics-advisories/icsa-26-232-01
- 厂商：https://www.johnsoncontrols.com/trust-center/cybersecurity/security-advisories

IoC：未见公开 IoC。

### 3. crates.io 供应链投毒：arrayref 0.3.10／internment 0.8.7／append-only-vec 0.1.9 + proc-macro1 1.0.107

2026-08-20，被评估为凭据失陷的 crates.io 维护者账号 **droundy** 发布了三个高下载量 Rust crate 的投毒版本，注入 typosquat **proc-macro1@1.0.107**。该 crate 的 build.rs 在编译期拉取二阶段二进制（源 **23.254.165.112:9089**，TLS 证书校验被关闭），并以 **23.254.165.112:443** 作为 C2（argv[1]）。暴露窗口约 **07:11–09:25 UTC**。crates.io 当日删除恶意版本并锁定账号。最后安全版本：**arrayref 0.3.9**／**internment 0.8.6**／**append-only-vec 0.1.8**。Wiz 称基础设施与 DPRK／Sapphire Sleet（Mastra）及 UNC1069（axios）有重叠（共享 Hostwinds 网段、POST /49890878、SSL 颁发者 WIN-A6QF8AHPQH1），**重叠 ≠ 已归因，不据此单独定性为国家行为**。防御：在 Cargo.lock／CI 缓存中搜下列 crate 版本；窗口内执行过构建的主机按失陷处置并轮换凭据；拦截下列 IP／域名。本晚报不转载 payload 或复现步骤。

地址：
- StepSecurity：https://www.stepsecurity.io/blog/arrayref-rust-crate-supply-chain-attack
- Wiz：https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns
- BleepingComputer：https://www.bleepingcomputer.com/news/security/hackers-poison-arrayref-rust-crate-to-push-infostealer-malware/
- RustSec issue：https://github.com/rustsec/advisory-db/issues/3161
- Socket（2026-08-20）：https://socket.dev/blog/popular-rust-crates-compromised
- Rust 官方：https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/

X：https://x.com/SocketSecurity/status/2090478845145080072
X：https://x.com/aviatrixtrc/status/2090590522645598298

地址／IoC（抄自公开备援 JSON，包／哈希／IP／域名／路径）：
- 包：arrayref@0.3.10（最后安全 0.3.9）
- 包：internment@0.8.7（最后安全 0.8.6）
- 包：append-only-vec@0.1.9（最后安全 0.1.8）
- 包：proc-macro1（1.0.106 诱饵，1.0.107 武器化；各版本已删）
- 包：proc-macro-en（各版本已删）
- 包：aovine、arone、aronenao、tinymember（攻击者自有；已删）
- SHA256 25ad700976873c76af785cb99b33c48db7df8b81f21d1e9e06b3676b9a9373ae（arrayref-0.3.10.crate）
- SHA256 61198155da51b838772eecf5bfaac6cbc4dcc388dccc56658fc28a8e831b34d4（proc-macro1-1.0.107.crate）
- SHA256 b5c1b5b0763a8809a644a8f92224653f0aca623a98eecc714d27f74b80fbe436（proc-macro1-1.0.106.crate）
- SHA1 f22e3e01e38bcdf001f0d15a2dbfdec5a1cf8eff（proc-macro1-1.0.107.crate，Wiz）
- SHA1 f4767ad92cb61401fd69139cade563501c39b991（rust-crate_0.1.0 Linux 二阶段，Wiz）
- SHA1 fc0fdb978eac72f4484b48db058e4473f1bc516e（rust-crate_0.2.0 Windows 二阶段，Wiz）
- SHA1 ff7e20cf642346bf893f1eca808df82035bb53d0（rust-crate_0.4.0 macOS arm64 二阶段，Wiz）
- 23.254.165.112:9089（二阶段载荷主机，Hostwinds）
- 23.254.165.112:443（C2，argv[1]）
- 23.254.167.107:443（额外 C2，Wiz／RustSec 帖）
- 23.254.167.216（感染 Linux 主机上报的二阶段 C2；Wiz 称与 UNC1069 axios 重叠）
- hwsrv-798836.hostwindsdns.com
- POST /49890878（二阶段 C2 路径；Wiz 称 Mastra 亦用）
- /tmp/rust-setup
- %TEMP%\rust-setup.ps1（仅作狩猎路径，不转载脚本）
- %TEMP%\rust-setup-launch.vbs
- $HOME/.config/AzureKits、$HOME/.config/ServiceKit；二进制 MonoService／MonoXpc（rustsec/advisory-db#3161 第三方感染主机报告）
- SHA256 408ef22050ffc5a67e005802809026b29f297a8019f8fda91a2afa8e877ba434 Linux rust-crate_0.1.0
- SHA256 492f2ab86f8d8911adc79c10ec1541704f5311d207d9d799b0d2a57fcc6a4391 Windows rust-crate_0.2.0
- SHA256 c9561a3b00a0fa38b7772675d987f84bd429c55cd024fc08a98245c2d1632848 macOS x86 rust-crate_0.3.0
- SHA256 74d3447e7cf99c99ea01a16332ec27432dfb0f491e10e67cd118065a60483306 macOS arm rust-crate_0.4.0
- SHA256 cb7778eb6dda91028abf087eb7c3553f981a67e756769507d348e8c201805568 build.rs
- Download hosts (defensive, no steps): https://23.254.165.112:9089/rust-crate_0.1.0 through 0.4.0
- DGA hunt (Socket: Aug 20–24 UTC, may be unregistered): rasGThauFD.com feVVKIiEiU.com phrpjTNckF.com PrOkXLgfjW.com ackeoTaWtl.com GAFWVCMAja.com RNSsddnEgK.com pfHlVOqEeg.com aBEcOrkups.com epOdIaTMaM.com

### 4. Zimbra CVE-2026-73570（BC 2026-08-20 英文转述；CERT Polska 原文 2026-08-17）

BleepingComputer **2026-08-20** 英文报道转述 CERT Polska 通告 **145/2026**（日期 **2026-08-17**，原文在窗口外；因 8/20 英媒跟进列入）。**CVE-2026-73570**：Zimbra Collaboration Suite 未认证 OS 命令注入，前提为可选组件 **zimbra-snmp** 已安装、SNMP 通知已启用、且 **swatchdog** 在运行。厂商修复：**ZCS 10.1.20**（厂商日期 **2026-07-20**）。本窗口 **未入 KEV**。狩猎只列路径，不写利用。Shadowserver：逾 12,100 台互联网暴露 Zimbra（仅地理／暴露面，无利用细节）。

狩猎路径：
- /opt/zimbra/jetty/webapps/
- /opt/zimbra/jetty_base/webapps/
- /tmp/ 下由用户 zimbra 创建的文件
- /var/log/zimbra.log 中的 service status change（stopped↔running）

地址：
- 文章：https://www.bleepingcomputer.com/news/security/critical-zimbra-rce-flaw-now-actively-exploited-in-attacks/
- CERT Polska（2026-08-17）：https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570

X：https://x.com/__kokumoto/status/2090577657209684306

IoC：上列狩猎路径；未见本晚报已核验的样本哈希。

### 5. 短提醒（昨日已覆盖，不展开）

- Ray **CVE-2025-62593** 仍列于 catalogVersion 2026.08.20（dateAdded 2026-08-17），联邦期限 **今日 2026-08-20**。窗口内无针对该 CVE 的新 CISA 警报或说明。knownRansomwareCampaignUse=Unknown。
- 8/18 四条 KEV **CVE-2026-33824**、**CVE-2026-55040**、**CVE-2026-59310**、**CVE-2026-65400** 联邦期限均为 **2026-08-21**。不展开。
- X 亦回流 Laundry Bear／AA26-204A（7 月）、Ghost CVE-2026-26980（2 月）、NCSC-2026-0280（8/12 已随 65400 报过）、Huntress FakeAgent（7/21–22）。不展开。

地址：
- CISA 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- CISA JSON：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json

IoC：未见公开 IoC。

## 工具与 GitHub 发布

### 1. nuclei-templates 版本核对

projectdiscovery/nuclei-templates 最新标签仍为 **v10.4.7**（published_at 2026-08-03T07:21:59Z），本窗口无新版本。

地址：
- GitHub 发布页：https://github.com/projectdiscovery/nuclei-templates/releases

IoC：未见公开 IoC。

### 2. 窗口内新见公开仓（仅 URL＋描述，未克隆）

GitHub Search API 对 c2／redteam／red-team／command-and-control、created:2026-08-19..2026-08-20 返回大量误报。下列为创建时间 ≥ 2026-08-20T00:35:00Z、描述明确指向 C2 或红队工具的公开仓。本晚报仅记录 URL 与公开描述，**未克隆、不分析、不转载用法**。防御侧可将仓 URL 当作出现面指标。

- https://github.com/4ynow/flask-c2-server （2026-08-20T22:35:50Z）— Flask C2 任务服务器，带交互式 operator CLI；持久 agent 注册、任务队列、结果收集、TLS、kill switch。描述自称教育／授权测试。
- https://github.com/0x4meliorate/Mimic （2026-08-20T22:47:50Z）— 无框 Browser-in-the-Browser（BitB）钓鱼模拟库（Shadow DOM／MutationObserver）。仅记出现面。
- https://github.com/ClumsyLulz/Doxbin-Botnet-Logs （2026-08-20T22:35:02Z）— 描述为 “Doxbin C2 Logs”。**仅列 URL**，不转载日志内容。
- https://github.com/josedelsol1/blindaje-redteam （2026-08-20T23:08:22Z）— Claude Code 用红队／蓝队 skill：OWASP Top 10 攻击代理与修代码代理。描述自称仅授权目标。
- https://github.com/sentient-zero/research （2026-08-20T01:38:34Z）— Offensive security and AI red teaming research。

地址：
- https://github.com/4ynow/flask-c2-server
- https://github.com/0x4meliorate/Mimic
- https://github.com/ClumsyLulz/Doxbin-Botnet-Logs
- https://github.com/josedelsol1/blindaje-redteam
- https://github.com/sentient-zero/research

IoC：上列仓 URL（出现面）。

### 3. Whispergate/lldp（Mythic C2 藏 LLDP Type-127 TLV，仅 URL，未克隆）

GitHub 仓 https://github.com/Whispergate/lldp ：Mythic C2 藏 LLDP Type-127 TLV。本晚报仅记录 URL，**未克隆、不分析、不转载用法**。防御：盯异常 LLDP OUI。

X：https://x.com/ipurple/status/2090383814795120726

地址：
- GitHub：https://github.com/Whispergate/lldp

IoC：https://github.com/Whispergate/lldp

### 4. Kassandra（Rust Mythic agent，仅 URL，未克隆）

GitHub 仓 https://github.com/PatchRequest/Kassandra ：Rust Mythic agent。本晚报仅记录 URL，**未克隆、不分析、不转载用法**。

X：https://x.com/PatchRequest/status/2090542120868233528

地址：
- GitHub：https://github.com/PatchRequest/Kassandra

IoC：https://github.com/PatchRequest/Kassandra

### 5. Emerging Threats ruleset v11261（2026-08-20）

ET ruleset **v11261**（**2026-08-20**）：ClickFix／EtherHiding 等。本晚报仅记规则集出现面，不转载规则正文。

X：https://x.com/ET_Labs/status/2090545113780932694

地址：
- ET：https://community.emergingthreats.net/t/ruleset-update-summary-2026-08-20-v11261/3425

IoC：未见公开 IoC。

### 6. GCleaner 分析仓（仅 URL）

GitHub 仓 https://github.com/kaandemir993/Dropper-GCleaner-C2-Infrastructure-Kernel-Driver-PowerShell-Conhost-Payload-Analysis 。本晚报**仅列 URL**，未克隆、不分析、不转载用法。

X：https://x.com/Dinosn/status/2090410529420456232

地址：
- GitHub：https://github.com/kaandemir993/Dropper-GCleaner-C2-Infrastructure-Kernel-Driver-PowerShell-Conhost-Payload-Analysis

IoC：上列仓 URL（出现面）。

## APT / Malware 分析

### 1. Cisco Talos UAT-10147（2026-08-20 06:00；仅高阶）

Talos 于 **2026-08-20 06:00** 发布：以牟利为动机的中文行为体集群 **UAT-10147**，目标为互联网暴露的 Windows **IIS** 与 **Linux Web** 服务器。行业：政府、教育、媒体、科技、游戏。已观察受害地：巴西、玻利维亚、中国、加拿大、越南。发现起点是失陷主机回连开放目录 **139.180.197.150**。行为体持有约 **17 万** URL 目标清单。

手法高阶（谁／打什么／补丁与狩猎，**不抄利用手册**）：混用针对暴露 Web 的 one-day RCE；事后用 AI 辅助工具（仅记名称：**PentestGPT**、**DeepAudit**）生成／校验后续操作说明。本晚报不抄利用手册、不转载复现步骤。植入／工具家族： **BadIIS**、**QuasarRAT**、**Gh0stCringe**、**Noodle RAT**、**Meterpreter**、**SPECTRE**。

同日配套 SPECTRE 文：自定义 **C** 语言跨平台植入（Windows＋Linux ELF）。Linux 侧 LKM 伪装 **acpi_pad.ko**，systemd 单元 **hardware-monitor.service**；Windows 侧可选把 C2 放在 NTFS ADS **C:\Windows\System32\drivers\etc\hosts:cache**。防御狩猎上列文件名／ADS／开放目录，并按厂商建议给暴露 IIS／Linux Web 打补丁、收紧出站。完整哈希见 Talos GitHub IOC 仓，本晚报不抄 40+ 哈希。

地址：
- Talos 主文：https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- Talos SPECTRE：https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- Talos IOC（主文）：https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt
- Talos IOC（SPECTRE）：https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20deploys%20SPECTRE.txt

地址／IoC（仅关键项；完整哈希见 Talos GitHub IOC 仓）：
- 139.180.197.150
- 18.140.163.186
- adminapi.tippusoni.in
- kl21177.com
- js.jyzyps.com
- vip8888vn.xyz
- 27.124.2.46
- 27.124.2.48
- 27.124.2.52
- acpi_pad.ko
- hardware-monitor.service
- C:\Windows\System32\drivers\etc\hosts:cache
- ClamAV：Py.Loader.Tool-10060293-1、Py.Loader.Tool-10060293-2、Win.Malware.Generic-10060228-0、Win.Loader.Downloader-10060287-1、Unix.Rootkit.Spectre-10060260-0、Unix.Rootkit.Malware-10060258-0、Win.Malware.BadIIS-10059985-0、Asp.Rootkit.Badiis-10060290-1、Win.Loader.BadiisSet-10060291-1
- Snort2／Snort3 SID：1:66697、1:66696、1:66690、1:66688、1:66689；Snort3 另有 1:301548

### 2. Unit 42：协作频道（Teams／Slack）身份滥用（2026-08-20，综述）

Unit 42 研究日期 **2026-08-20**。协作工具端点告警 12 个月内翻两番以上；相关告警约 99% 与聊天钓鱼有关。文中复述既有案例（APT29 Teams 联邦钓鱼、Okta 记录的 Slack 工作区钓鱼至 AiTM、Fireblocks 2026-01 Google Meet 诱饵、Axios 维护者 2026-03 Slack／Teams 社工、OpenSSF TODO Group 2026-04 Slack 假冒、CERT Polska 2025-12 Slack webhook 被用于 VPN 设备凭据外带），**不是窗口内新战役起点**。防御：收紧联邦／访客、高风险请求出带外核实、监控 Slack／Teams 拉起 shell、审查设备上意外的 hooks.slack.com POST。**hooks.slack.com 是合法 Slack webhook，不要当恶意域名列。** 未见恶意基础设施 IoC。本晚报不转载检测查询中的命令行。

地址：
- Unit 42：https://unit42.paloaltonetworks.com/communication-channel-identity-risks/

IoC：未见恶意基础设施 IoC（hooks.slack.com 为合法 webhook）。

## 地址／IoC 汇总

### URL
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://trueconf.com/blog/news/security-fixes-updates-and-advisories
- https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-breakout-from-isolated-environment/
- https://www.cisa.gov/news-events/directives/bod-26-04-prioritizing-security-updates-based-risk
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-232-01
- https://www.johnsoncontrols.com/trust-center/cybersecurity/security-advisories
- https://www.stepsecurity.io/blog/arrayref-rust-crate-supply-chain-attack
- https://www.wiz.io/blog/rust-supply-chain-attack-on-arrayref-significant-overlap-with-dprk-campaigns
- https://www.bleepingcomputer.com/news/security/hackers-poison-arrayref-rust-crate-to-push-infostealer-malware/
- https://github.com/rustsec/advisory-db/issues/3161
- https://www.bleepingcomputer.com/news/security/critical-zimbra-rce-flaw-now-actively-exploited-in-attacks/
- https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://github.com/projectdiscovery/nuclei-templates/releases
- https://github.com/4ynow/flask-c2-server
- https://github.com/0x4meliorate/Mimic
- https://github.com/ClumsyLulz/Doxbin-Botnet-Logs
- https://github.com/josedelsol1/blindaje-redteam
- https://github.com/sentient-zero/research
- https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt
- https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20deploys%20SPECTRE.txt
- https://unit42.paloaltonetworks.com/communication-channel-identity-risks/
- https://securityonline.info/trueconf-cve-2026-72529-exploited/
- https://x.com/__kokumoto/status/2090574451628998676
- https://x.com/Daily_CyberSec/status/2090552081023205651
- https://x.com/__kokumoto/status/2090577657209684306
- https://socket.dev/blog/popular-rust-crates-compromised
- https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/
- https://x.com/SocketSecurity/status/2090478845145080072
- https://x.com/aviatrixtrc/status/2090590522645598298
- https://github.com/Whispergate/lldp
- https://x.com/ipurple/status/2090383814795120726
- https://github.com/PatchRequest/Kassandra
- https://x.com/PatchRequest/status/2090542120868233528
- https://community.emergingthreats.net/t/ruleset-update-summary-2026-08-20-v11261/3425
- https://x.com/ET_Labs/status/2090545113780932694
- https://github.com/kaandemir993/Dropper-GCleaner-C2-Infrastructure-Kernel-Driver-PowerShell-Conhost-Payload-Analysis
- https://x.com/Dinosn/status/2090410529420456232

### TrueConf KEV／Johnson Controls／Zimbra 短提醒
- TrueConf／Johnson Controls／Ray 与 8/18 四条 KEV：未见公开 IoC
- Zimbra 狩猎：/opt/zimbra/jetty/webapps/ ；/opt/zimbra/jetty_base/webapps/ ；/tmp/ 下用户 zimbra 文件 ；/var/log/zimbra.log service status change

### crates.io 供应链（包／哈希／IP／域名／路径）
- arrayref@0.3.10（最后安全 0.3.9）
- internment@0.8.7（最后安全 0.8.6）
- append-only-vec@0.1.9（最后安全 0.1.8）
- proc-macro1 1.0.106／1.0.107；proc-macro-en；aovine；arone；aronenao；tinymember
- SHA256 25ad700976873c76af785cb99b33c48db7df8b81f21d1e9e06b3676b9a9373ae
- SHA256 61198155da51b838772eecf5bfaac6cbc4dcc388dccc56658fc28a8e831b34d4
- SHA256 b5c1b5b0763a8809a644a8f92224653f0aca623a98eecc714d27f74b80fbe436
- SHA1 f22e3e01e38bcdf001f0d15a2dbfdec5a1cf8eff
- SHA1 f4767ad92cb61401fd69139cade563501c39b991
- SHA1 fc0fdb978eac72f4484b48db058e4473f1bc516e
- SHA1 ff7e20cf642346bf893f1eca808df82035bb53d0
- 23.254.165.112:9089
- 23.254.165.112:443
- 23.254.167.107:443
- 23.254.167.216
- hwsrv-798836.hostwindsdns.com
- POST /49890878
- /tmp/rust-setup
- %TEMP%\rust-setup.ps1
- %TEMP%\rust-setup-launch.vbs
- $HOME/.config/AzureKits
- $HOME/.config/ServiceKit
- MonoService／MonoXpc
- SHA256 408ef22050ffc5a67e005802809026b29f297a8019f8fda91a2afa8e877ba434 Linux rust-crate_0.1.0
- SHA256 492f2ab86f8d8911adc79c10ec1541704f5311d207d9d799b0d2a57fcc6a4391 Windows rust-crate_0.2.0
- SHA256 c9561a3b00a0fa38b7772675d987f84bd429c55cd024fc08a98245c2d1632848 macOS x86 rust-crate_0.3.0
- SHA256 74d3447e7cf99c99ea01a16332ec27432dfb0f491e10e67cd118065a60483306 macOS arm rust-crate_0.4.0
- SHA256 cb7778eb6dda91028abf087eb7c3553f981a67e756769507d348e8c201805568 build.rs
- Download hosts (defensive, no steps): https://23.254.165.112:9089/rust-crate_0.1.0 through 0.4.0
- DGA hunt (Socket: Aug 20–24 UTC, may be unregistered): rasGThauFD.com feVVKIiEiU.com phrpjTNckF.com PrOkXLgfjW.com ackeoTaWtl.com GAFWVCMAja.com RNSsddnEgK.com pfHlVOqEeg.com aBEcOrkups.com epOdIaTMaM.com

### UAT-10147／SPECTRE（关键项；完整哈希见 Talos GitHub IOC 仓）
- 139.180.197.150
- 18.140.163.186
- adminapi.tippusoni.in
- kl21177.com
- js.jyzyps.com
- vip8888vn.xyz
- 27.124.2.46／27.124.2.48／27.124.2.52
- acpi_pad.ko
- hardware-monitor.service
- C:\Windows\System32\drivers\etc\hosts:cache
- ClamAV Py.Loader.Tool-10060293-1／-2、Win.Malware.Generic-10060228-0、Win.Loader.Downloader-10060287-1、Unix.Rootkit.Spectre-10060260-0、Unix.Rootkit.Malware-10060258-0、Win.Malware.BadIIS-10059985-0、Asp.Rootkit.Badiis-10060290-1、Win.Loader.BadiisSet-10060291-1
- Snort SID 1:66697、1:66696、1:66690、1:66688、1:66689、1:301548

### Unit 42
- 未见恶意基础设施 IoC（hooks.slack.com 为合法 webhook，不列入）

### 工具仓 URL
- https://github.com/4ynow/flask-c2-server
- https://github.com/0x4meliorate/Mimic
- https://github.com/ClumsyLulz/Doxbin-Botnet-Logs
- https://github.com/josedelsol1/blindaje-redteam
- https://github.com/sentient-zero/research
- https://github.com/Whispergate/lldp
- https://github.com/PatchRequest/Kassandra
- https://github.com/kaandemir993/Dropper-GCleaner-C2-Infrastructure-Kernel-Driver-PowerShell-Conhost-Payload-Analysis
- https://community.emergingthreats.net/t/ruleset-update-summary-2026-08-20-v11261/3425

## 来源搜索 URL

- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20%28C2%20OR%20%22red%20team%22%20OR%20nuclei%29&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
- https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://nvd.nist.gov/
- https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt
- https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20deploys%20SPECTRE.txt
