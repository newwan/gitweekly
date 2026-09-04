# X 安全情报晚报 · 2026-09-03

> 搜集窗口：圣地亚哥时间 **2026-09-02 20:00 至 2026-09-03 ~20:45**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周四）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-09-03.json`（collected_at **2026-09-03T20:25:54-04:00**）＋ `/workspace/tools-news-pulse-2026-09-03.md`。CISA KEV catalogVersion **2026.09.02**／**1694** 条／dateReleased **2026-09-02T16:54:39.8321Z**（相对昨日 **+0**，无 09-03 新入目录 CVE）。
> **期限今日 09-03：CVE-2026-72530** TrueConf Server。**期限明日 09-04：无。** **期限 09-05（5 条紧急）**：Kestra 49869、JFrog 82329、Sangoma 9586、SonicWall 83548/83549。PaperCut **CVE-2026-81578/82078** 仍 due **2026-09-14**。厂商公告 Last updated **September 3, 2026**（4:55pm AEST 状态更新：无新情报，正式版仍在推进）；Emergency Patch Release 3 仍为最新。
> X：`/workspace/x-posts-2026-09-03.json`（合并 **56** 条：A 6／B 12／C 26／LWiS 12；**logged_in=true**／**@seogoogle4**；blocked=false）。Search A Latest 约 **0.45h**（高流量，**远不足 24h**）。Search B 约 **41h**（窗内 6 条工具帖）。Search C 约 **9.3h**／26 条。LWiS List 约 **22h**／12 条（`/workspace/x-posts-2026-09-03-lwis-list.json`）。**公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉。
> 规则：每条含完整 https URL；分列原帖／仓库／厂商／文章；没有指标就写「未见公开 IoC」；不编造；不转载利用代码／payload／PoC 步骤。

## 今日摘要

- **【主条 · KEV 今日到期】TrueConf Server CVE-2026-72530**（代码注入／沙箱逃逸；与 CVE-2026-72529 同批 08-20 入 KEV）。联邦 BOD 26-04 期限今日。升级至厂商修复版本，限制 **4307/TCP** 暴露，并按 BOD 做补丁前取证分诊。**不转写利用链。**
  厂商：https://trueconf.com/blog/news/security-fixes-updates-and-advisories
  Kaspersky ICS：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-breakout-from-isolated-environment/
  CISA 警报：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
  KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-72530

- **【期限倒计时 09-05】** 昨日新入 KEV 五条仍 due **2026-09-05**：Kestra **CVE-2026-49869**、JFrog Artifactory **CVE-2026-82329**、Sangoma **CVE-2026-9586**、SonicWall SMA1000 **CVE-2026-83548/83549**。LiteLLM／Starlette due 09-16。
  警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
  KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

- **【PaperCut 续】** NG／MF **CVE-2026-81578/82078** 仍 KEV（due 09-14）。**R3** 仍为紧急补丁；09-03 仅状态更新。Help Net Security／X：公网 Application Server 上出现**合法远程访问工具**落地（与厂商 IoC 中 SimpleHelp／AnyDesk 叙述一致）。公网未打补丁应假定失陷。
  厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
  文章：https://www.helpnetsecurity.com/2026/08/31/papercut-attack-remote-access-tools/
  X：https://x.com/ShringTech/status/2095527271264063902

- **【新 ICS · 09-03】** CISA 发布 **ICSA-26-246-01..08**（含 Ignition **CVE-2026-77393**、Rockwell 多条、OPC UA LDS、IXON VPN Client、Pyramid NetStaX、Tycon 等）＋ Update A（ICSA-26-169-07／ICSA-26-202-01）。
  例：https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-06
  目录 RSS：见各 ICSA-26-246-* 链接（CVE 小节）

- **【X 交叉 · Elementor Pro】** **CVE-2026-32475**（≤4.2.1 未认证上传→RCE）；Aviatrix TRC：Wordfence 称补丁后数日近 **20 万**次利用尝试；修 **4.2.2+**，检查 `wp-content/uploads/elementor/forms/` 异常 PHP。**不转写上传绕过细节。**
  文章：https://aviatrix.ai/threat-research-center/critical-elementor-pro-flaw-cve-2026-32475-wordpress-takeover/ https://www.bleepingcomputer.com/news/security/critical-elementor-pro-bug-exposes-wordpress-sites-to-rce-attacks/ https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
  CVE：https://www.cve.org/CVERecord?id=CVE-2026-32475
  X：https://x.com/aviatrixtrc/status/2095666369811337587

- **【工具】Sliver v1.7.7**（今日相对 v1.7.6 新发；端口转发／SOCKS5 硬化等）。nuclei-templates **仍 v10.4.8**。X 工具窗：Malleon、SpecterOps skills、Cybermes、Awesome-Red-Teaming、JFrog nuclei 模板等。
  仓库：https://github.com/BishopFox/sliver/releases/tag/v1.7.7 https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8

- **【APT／恶意软件】** BraZetsu（拉美 IAB／Python 框架）；Unit 42 企业 AI 代理入侵案（09-02 文，今日 X 仍在传，无 0day）；SilentEncryptor／StopAndProtect；Virtualizor BGP 劫持投毒更新；GRU／Bauman 培训泄密报道。
  https://aviatrix.ai/threat-research-center/brazetsu-malware-initial-access-broker-marketplace-2026/ https://unit42.paloaltonetworks.com/ai-assisted-cyber-attack-inside-a-unit-42-investigation/ https://www.securityweek.com/malicious-virtualizor-update-served-via-bgp-hijacking/ https://securityaffairs.com/198332/intelligence/2000-leaked-documents-reveal-how-russia-turns-engineering-students-into-gru-cyber-operators.html

- **【LWiS 交叉】** 朝鲜关联 **macOS.Gaslight**（Rust 植入体，对 AI 分诊做 prompt injection）；SpecterOps AI 红队 skills 仓；X 帖提及 **CVE-2026-84670** QEMU guest-to-host 线索（公开 CVE 库暂未见该编号，仅作线索）。
  Gaslight：https://www.sentinelone.com/labs/macos-gaslight-rust-backdoor-turns-prompt-injection-on-the-analyst-not-the-sandbox/ · X：https://x.com/TakSec/status/2095364914856755448
  SpecterOps：https://github.com/SpecterOps/skills · X：https://x.com/cr3ghost/status/2095497047709225034
  QEMU 线索 X：https://x.com/pruvadev/status/2095639229296443859

- **【新闻备援】** Risky Biz 新 **SRB182**（中国僵尸网络扰动／ATF／水务）；RB851／RBNEWS608／BTN181；tl;dr sec 仍 **#343**。
  https://risky.biz/SRB182/ https://risky.biz/RB851/ https://risky.biz/RBNEWS608/ https://tldrsec.com/p/tldr-sec-343

## CVE / POC / 漏洞

### 1. 【KEV 今日到期】TrueConf Server CVE-2026-72530

代码注入／隔离环境逃逸；常与 **CVE-2026-72529**（4307/TCP 缺失认证）链式出现。修复构建见厂商页（5.3.9／5.4.9／5.5.5 各平台构建号）。限制公网 4307，补丁后做取证。**不转写 PoC。**

地址：
- 厂商：https://trueconf.com/blog/news/security-fixes-updates-and-advisories
- Kaspersky：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-breakout-from-isolated-environment/ https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- CISA：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-72530 https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-72530 https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-72529
- 文章：https://securityaffairs.com/197602/security/u-s-cisa-adds-trueconf-server-flaws-to-its-known-exploited-vulnerabilities-catalog.html https://blog.gridinsoft.com/trueconf-server-cve-2026-72529-72530/

IoC：未见本报窗口内统一公开狩猎哈希；关注 4307/TCP 异常与厂商／Kaspersky 公告。

### 2. 【KEV 续／due 09-05】昨日七条中的五条紧急

JFrog／Sangoma／SonicWall／Kestra 仍 due **2026-09-05**；LiteLLM／Starlette due 09-16。X 仍见 JFrog nuclei 模板传播。

地址：
- CISA 警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82329 https://nvd.nist.gov/vuln/detail/CVE-2026-9586 https://nvd.nist.gov/vuln/detail/CVE-2026-83548 https://nvd.nist.gov/vuln/detail/CVE-2026-83549 https://nvd.nist.gov/vuln/detail/CVE-2026-49869 https://nvd.nist.gov/vuln/detail/CVE-2026-59822 https://nvd.nist.gov/vuln/detail/CVE-2026-48710
- SonicWall：https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2026-0016
- nuclei：https://github.com/projectdiscovery/nuclei-templates/blob/main/http/cves/2026/CVE-2026-82329.yaml
- X：https://x.com/DhiyaneshDK/status/2095191115209343273

IoC：未见本条新增统一 IoC；逐厂商公告。

### 3. 【KEV 续】PaperCut NG／MF CVE-2026-81578 ＋ CVE-2026-82078（due 2026-09-14）

Emergency Patch Release 3 仍为累积紧急补丁。09-03 厂商仅发状态更新。Help Net Security：入侵后植入合法远程访问软件。对照厂商 IoC（SimpleHelp／AnyDesk／投放 URL 等，已去活化叙述）。

地址：
- 厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- KEV／NVD：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-81578 https://nvd.nist.gov/vuln/detail/CVE-2026-81578 https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- 文章：https://www.helpnetsecurity.com/2026/08/31/papercut-attack-remote-access-tools/ https://www.rapid7.com/blog/post/etr-papercut-ng-mf-critical-zero-day-exploited-in-the-wild/
- X：https://x.com/ShringTech/status/2095527271264063902

IoC：见「地址／IoC 汇总」（厂商披露狩猎字符串与 R3 SHA256；投放 URL 去活化）。

### 4. 【X 交叉】Elementor Pro CVE-2026-32475（未入 KEV）

未认证危险类型上传→RCE；影响 ≤4.2.1，修 4.2.2+。条件常为带 File Upload 的已发布 Elementor Form。狩猎上传目录异常 PHP。**不转写 multipart 绕过步骤。**

地址：
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-32475
- Patchstack：https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- 文章：https://aviatrix.ai/threat-research-center/critical-elementor-pro-flaw-cve-2026-32475-wordpress-takeover/ https://www.bleepingcomputer.com/news/security/critical-elementor-pro-bug-exposes-wordpress-sites-to-rce-attacks/
- X：https://x.com/aviatrixtrc/status/2095666369811337587

IoC：公开狩猎侧重 `wp-content/uploads/elementor/forms/` 下非预期可执行文件；未见本报统一哈希列表。

### 5. 【X 交叉】Linux Kernel CVE-2026-68162（SCTP UAF，本地提权讨论）

日文实验室卡片／PoC 讨论帖；**本报不转载 PoC 步骤。** 按发行版补丁通道升级内核。

地址：
- 文章：https://rocket-boys.co.jp/security-measures-lab/linux-kernel-cve-2026-68162-sctp-poc/
- X：https://x.com/securityLab_jp/status/2095663454023815474

IoC：未见公开攻击者 C2／样本哈希。

### 6. 【X 交叉／KEV 旧条回响】Progress Kemp LoadMaster CVE-2026-8037

已在 KEV（dateAdded 2026-08-07，due 已过）。THN：41 天内约 792 次利用尝试。升级固件并限制 API 管理面。

地址：
- CISA：https://www.cisa.gov/news-events/alerts/2026/08/07/cisa-adds-one-known-exploited-vulnerability-catalog
- 厂商：https://community.progress.com/s/article/LoadMaster-Critical-Security-Bulletin-June-2026-CVE-2026-8037-CVE-2026-33691
- 文章：https://thehackernews.com/2026/08/progress-kemp-loadmaster-flaw-hits-cisa.html
- X：https://x.com/nik_kale/status/2095663136175226944
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-8037

IoC：未见本帖附带新哈希。

### 7. 【新 ICS】ICSA-26-246-01..08（2026-09-03）

含 Ignition 默认权限 **CVE-2026-77393**（升 8.1.54+ 或配置 Create Project Role(s)）、Rockwell ControlFLASH／ArmorStart／1756-ENBT、OPC UA LDS、IXON VPN Client、Pyramid NetStaX、Tycon TPDIN-WEB3 等。另有 Schneider／Tycon Update A。

地址：
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-06
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-07
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-246-08
- Update A：https://www.cisa.gov/news-events/ics-advisories/icsa-26-169-07 https://www.cisa.gov/news-events/ics-advisories/icsa-26-202-01
- Ignition Trust Center：https://security.inductiveautomation.com/?tcuUid=34477620-731d-4b70-b22b-9450f9a659a3

IoC：CISA 称 Ignition 条未见针对该漏洞的已知公开在野利用报告（以 advisory 原文为准）。

## 工具与 GitHub 发布

### 1. Sliver v1.7.7（今日新发）

相对 v1.7.6：OPFOR CNA BOF、Windows shell、反向端口转发生命周期、portfwd／SOCKS5 硬化等。X Search B 本轮未见该版本帖，以 GitHub 发布为准。

地址：
- 仓库发布：https://github.com/BishopFox/sliver/releases/tag/v1.7.7
- 对比：https://github.com/BishopFox/sliver/compare/v1.7.6...v1.7.7

IoC：不适用（合法红队框架发布）。

### 2. nuclei-templates 仍 v10.4.8；JFrog 模板交叉

地址：
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/projectdiscovery/nuclei-templates/blob/main/http/cves/2026/CVE-2026-82329.yaml
- X：https://x.com/DhiyaneshDK/status/2095191115209343273

IoC：未见公开攻击者 IoC。

### 3. 窗口内其他工具／技能仓（X Search B）

防御向记录仓库地址，不展开攻击用法。

地址：
- Malleon：https://github.com/r3xmax/Malleon · X：https://x.com/ipurple/status/2095440262172422580
- SpecterOps skills：https://github.com/SpecterOps/skills · X：https://x.com/BlaiseBits/status/2095528431635022300
- Claude-BugHunter：https://github.com/elementalsouls/Claude-BugHunter · X：https://x.com/thscherf/status/2095523968866300385
- Cybermes：https://github.com/Zyrexnn/Cybermes · X：https://x.com/Mobile_Dev97/status/2095308543960158698
- Awesome-Red-Teaming：https://github.com/0xMrNiko/Awesome-Red-Teaming · X：https://x.com/_MrNiko/status/2095398176522199141
- G0DM0D3：https://github.com/elder-plinius/G0DM0D3 · X：https://x.com/ptlegion/status/2095588135686095083
- mythic_ornn（窗外稍早，交叉保留）：https://github.com/n0qword/mythic_ornn · X：https://x.com/ipurple/status/2095080036759961624
- cpg-nuclei-compiler：https://github.com/Tito0015/cpg-nuclei-compiler · X：https://x.com/TITO088/status/2094963440724881493

IoC：未见公开攻击者 IoC。


### 4. LWiS：SpecterOps skills／AgentJudge

SpecterOps 公开面向 AI agents 的 infosec tradecraft 仓；Dreadnode AgentJudge 在工具调用前做意图／规则拦截（防御向治理）。

地址：
- https://github.com/SpecterOps/skills
- X：https://x.com/cr3ghost/status/2095497047709225034 https://x.com/BlaiseBits/status/2095528431635022300 https://x.com/dreadnode/status/2095537344858202584

IoC：不适用。

## APT / Malware 分析

### 1. BraZetsu（Aviatrix TRC）

Python 恶意软件框架／初始访问经纪平台，针对拉美组织；金融数据外泄与 WebSocket C2 叙述。**不转写部署步骤。**

地址：
- 文章：https://aviatrix.ai/threat-research-center/brazetsu-malware-initial-access-broker-marketplace-2026/
- X：https://x.com/aviatrixtrc/status/2095662470127886458

IoC：未见本帖附带完整公开哈希列表；详见 TRC 原文。

### 2. Unit 42：AI 代理加速企业入侵（无 0day）

09-02 发布、09-03 澄清为入侵案（非勒索终态叙述修正）。前沿模型代理压缩 >50 个 ATT&CK 技术至 **<10 小时**；劫持 CI/CD 与云 AI 端点；留下约 80 页“审计”。今日 X 仍在传播。

地址：
- 文章：https://unit42.paloaltonetworks.com/ai-assisted-cyber-attack-inside-a-unit-42-investigation/
- 报道：https://www.theregister.com/security/2026/09/02/ai-agents-carried-out-every-step-of-this-ransomware-attack-then-left-the-victim-an-80-page-security-audit/5294009
- X：https://x.com/Vishakuthota/status/2095668220497920314

IoC：未见公开统一哈希；狩猎侧重突发性并行 API、Markdown 协作痕迹、异常模型调用身份（以 Unit 42 原文为准）。

### 3. SilentEncryptor／StopAndProtect

DFIR Radar：自 2026-05 活跃，称确认 22 个变种。**省略利用指令。**

地址：
- X：https://x.com/DFIR_Radar/status/2095543320546259226

IoC：未见公开帖内哈希。

### 4. Virtualizor 恶意更新（BGP 劫持）

Softaculous Virtualizor 用户在流量被劫持期间收到恶意更新（约两天）。与 Risky Bulletin RBNEWS608 同题。

地址：
- 文章：https://www.securityweek.com/malicious-virtualizor-update-served-via-bgp-hijacking/
- Risky：https://risky.biz/RBNEWS608/
- X：https://x.com/blackwired32799/status/2095587634605130209

IoC：未见本报抄录完整恶意更新哈希；以 SecurityWeek／厂商响应为准。

### 5. macOS.Gaslight（LWiS／SentinelOne；DPRK 关联）

Rust macOS 后门／窃密；内嵌约 3.5KB、38 条伪造“系统消息”以干扰 LLM 分诊；C2 经 Telegram Bot API（AES-GCM／证书固定）。Apple XProtect：`MACOS_BONZAI_COBUCH`。**不转写注入正文。**

地址：
- 文章：https://www.sentinelone.com/labs/macos-gaslight-rust-backdoor-turns-prompt-injection-on-the-analyst-not-the-sandbox/ https://securityaffairs.com/194256/malware/macos-gaslight-north-korea-linked-malware-that-tries-to-gaslight-the-analyst.html
- X：https://x.com/TakSec/status/2095364914856755448

IoC：样本 SHA-256（公开报道）：`6328567511d88fdc2ae0939c5ef17b7a63d2a833881900de018a4f12f4982525`；LaunchAgent 标签叙述：`com.apple.system.services.activity`（以 SentinelOne 原文为准）。

### 6. 【线索】QEMU CVE-2026-84670（LWiS X 帖；未核验）

@pruvadev 帖标注 guest-to-host DoS／escape 讨论与 **CVE-2026-84670** 图片。本报检索公开 CVE／NVD **未见该编号落库**；仅作线索，**不转写利用**。关注上游 QEMU／发行版公告。

地址：
- X：https://x.com/pruvadev/status/2095639229296443859

IoC：未见公开 IoC。

### 7. 其他威胁信号（X Search C）


未确认勒索／数据出售声称（Space Bears、Leakeddata、SilentRansomGroup、INC、Shinyhunters、Settra 等）、FulcrumSec／机场数据声称、FortiGate 凭证声称、Motorola AI 访问声称、自定义 Python RMM 求助帖、GRU／Bauman 培训泄密报道。均为**声称／报道**，需独立验证。

地址：
- GRU 报道：https://securityaffairs.com/198332/intelligence/2000-leaked-documents-reveal-how-russia-turns-engineering-students-into-gru-cyber-operators.html · X：https://x.com/bamitav/status/2095536035266728042
- PaperCut RAT 落地：https://www.helpnetsecurity.com/2026/08/31/papercut-attack-remote-access-tools/ · X：https://x.com/ShringTech/status/2095527271264063902
- 自定义 RMM：https://x.com/Kostastsale/status/2095657669218742732
- 工业 AI 利用测试：https://www.cybersecuritydive.com/news/frontier-ai-exploit-flaws-water-PLCs-industrial-devices/829307/ · X：https://x.com/JosephLykowski/status/2095664551656030305
- CTI 聚合：https://x.com/VECERTRadar/status/2095667121225101425

IoC：上述声称帖多数未见公开哈希；FortiGate／数据出售帖不转载凭证内容。

## 地址／IoC 汇总

- **TrueConf**：关注 **4307/TCP** 暴露与异常脚本执行；升级至厂商列出的 5.3.9／5.4.9／5.5.5 修复构建。
- **PaperCut（厂商公告摘录，防御向）**：
  - 狩猎：Application Server 上可疑后利用；`C:\ProgramData\ace.exe`；SimpleHelp 路径 `C:\ProgramData\JWrapper-Remote Access\JWAppsSharedConfig\restricted\SimpleService.exe`（服务名 “Remote Access Service”）；AnyDesk 落盘 `C:\ProgramData\AnyDesk.exe`。
  - 投放 URL（去活化）：`hxxps://sendit[.]sh/Gg7Rp/ace[.]exe`；`hxxps://download[.]anydesk[.]com/AnyDesk.exe`（后者为合法下载域被滥用场景，需结合上下文）。
  - Emergency Patch R3 示例 SHA256（Windows v26 Build 76531）：`9375a9c3cf84140a1d8e21b72d3d2c57d85d4de09ea9ae1dc021b64732427da7`（完整多版本校验和见厂商页 Checksums 节）。
- **Elementor**：检查 `wp-content/uploads/elementor/forms/` 非预期 PHP／webshell。
- **macOS.Gaslight**：SHA-256 `6328567511d88fdc2ae0939c5ef17b7a63d2a833881900de018a4f12f4982525`（公开报道）；LaunchAgent `com.apple.system.services.activity`（叙述）。
- **其余条目**：未见额外可核验公开 IoC，或仅见于原文附件——写「未见公开 IoC」者以上各节为准。

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

> LWiS List 本轮：`logged_in=true`／@seogoogle4；覆盖约 **22h**；保留 **12** 条（`/workspace/x-posts-2026-09-03-lwis-list.json`）。要点：Gaslight、SpecterOps skills、AgentJudge、QEMU CVE-2026-84670 线索、offsec agent 失控讨论。渲染时间线未见非 X 外链锚点。

### LWiS List 摘录（交叉）

1. Gaslight：https://x.com/TakSec/status/2095364914856755448
2. QEMU 线索：https://x.com/pruvadev/status/2095639229296443859
3. SpecterOps skills：https://x.com/cr3ghost/status/2095497047709225034
4. AgentJudge：https://x.com/dreadnode/status/2095537344858202584
5. offsec agent／疑似 SQLi：https://x.com/bohops/status/2095331883504537838


## 来源搜索 URL

- X Latest CVE/POC：https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- X Latest 工具：https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- X Latest 威胁报告：https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
- LWiS X List：https://x.com/i/lists/1239330068461244424
- LWiS 博客清单：https://blog.badsectorlabs.com/files/blogs.txt
- Risky Business：https://risky.biz/
- tl;dr sec：https://tldrsec.com/
- 暂停说明：https://blog.badsectorlabs.com/taking-a-break-2026-04-06.html
- CISA KEV JSON：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
