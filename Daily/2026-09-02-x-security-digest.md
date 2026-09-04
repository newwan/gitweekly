# X 安全情报晚报 · 2026-09-02

> 搜集窗口：圣地亚哥时间 **2026-09-01 20:00 至 2026-09-02 ~20:30**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报（周三）。**
> **公开备援为本轮 PRIMARY**：`/workspace/security-watch-public-backup-2026-09-02.json`（collected_at **2026-09-02T20:25:00-04:00**）＋ `/workspace/tools-news-pulse-2026-09-02.md`。CISA KEV catalogVersion **2026.09.02**／**1694** 条／dateReleased **2026-09-02T16:54:39.8321Z**（昨日 2026.09.01／1687）。**相对昨日：新增 7 CVE**（`dateAdded=2026-09-02`）。警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
> **期限今日 09-02：CVE-2026-64849** MLflow SSRF。**期限明日 09-03：CVE-2026-72530** TrueConf Server。PaperCut **CVE-2026-81578/82078** 仍 due **2026-09-14**。厂商公告 Last updated **September 2, 2026**；Emergency Patch Release 3 仍为最新，并补充「第二波」更复杂的事后入侵观察。
> X：`/workspace/x-posts-2026-09-02.json`（合并 **59** 条骨架：A 9／B 8／C  salvage 42；**logged_in=true**／**@seogoogle4**；blocked=false）。Search A Latest 约 **0.18h**（高流量，**远不足 24h**）。Search B 约 **21h**／8 条工具帖。Search C CDP 导出失败，仅抢救 status id。LWiS List 采集仍在收尾／或本轮未及时落盘；以下以 X Latest A/B ＋公开备援交叉。 **公开备援仍为 KEV／厂商 PRIMARY**；X 作交叉。
> 规则：每条含完整 https URL；分列原帖／仓库／厂商／文章；没有指标就写「未见公开 IoC」；不编造；不转载利用代码／payload／PoC 步骤。

## 今日摘要

- **【主条 · CISA 一日加七条 KEV】** 2026-09-02 入目录：LiteLLM **CVE-2026-59822**（due 09-16）、Starlette **CVE-2026-48710**（due 09-16）、Kestra **CVE-2026-49869**（due **09-05**）、JFrog Artifactory **CVE-2026-82329**（due **09-05**）、Sangoma Switchvox **CVE-2026-9586**（due **09-05**）、SonicWall SMA1000 **CVE-2026-83548/83549**（due **09-05**）。联邦 BOD 26-04 按条目执行补丁与取证分诊。
  警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
  KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

- **【KEV 今日到期】** **CVE-2026-64849** MLflow SSRF（dateAdded 2026-08-19）。升级修复版本（社区／GHSA 指向 **v3.15.0** 一带），限制跟踪服务出网与暴露面。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-64849
  GHSA：https://github.com/mlflow/mlflow/security/advisories/GHSA-7gwp-5pfp-969j
  仓库：https://github.com/mlflow/mlflow/releases/tag/v3.15.0
  KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-64849

- **【PaperCut 续／第二波】** NG／MF **CVE-2026-81578/82078** 仍 KEV（due 09-14）。**Emergency Patch Release 3** 仍为当前紧急补丁；公告 **2026-09-02 16:38 AEST** 更新称公网未充分打补丁主机出现**更复杂的事后入侵**。公网 Application Server：限制受信 IP 并升 R3；假定失陷做狩猎。**不转写利用链。**
  厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
  文章：https://www.cyberdaily.au/security/14128-papercut-exploitation-continues-to-worsen-as-company-releases-third-emergency-patch https://socprime.com/blog/cve-2026-81578-analysis/ https://www.rapid7.com/blog/post/etr-papercut-ng-mf-critical-zero-day-exploited-in-the-wild/
  X：https://x.com/Shadowserver/status/2094879415100391539
  仓库：https://github.com/projectdiscovery/nuclei-templates/pull/17025

- **SonicWall SMA1000 现已入 KEV**：PSIRT **SNWLID-2026-0016** 今日可正常打开（昨日报软缺失）。CVE-2026-83548（预认证 SSRF，CVSS 10）＋83549（认证后命令注入）；厂商称已调查在野利用。热修 **12.4.3-03526**／**12.5.0-02952** 及以上；影响 6210／7210／8200v。
  厂商：https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2026-0016
  文章：https://www.securityweek.com/sonicwall-warns-of-two-sma1000-zero-days-exploited-in-attacks/
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-83548 https://nvd.nist.gov/vuln/detail/CVE-2026-83549

- **JFrog／Sangoma 入 KEV（due 09-05）**：Artifactory **CVE-2026-82329** 认证绕过／管理员令牌伪造在野；Switchvox **CVE-2026-9586** SQLi。立刻限制暴露面并打厂商修复。
  NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82329 https://nvd.nist.gov/vuln/detail/CVE-2026-9586
  文章：https://aviatrix.ai/threat-research-center/jfrog-artifactory-cve-2026-82329-admin-token-forge/ https://aviatrix.ai/threat-research-center/sangoma-switchvox-cve-2026-9586-reverse-shells/
  X：https://x.com/aviatrixtrc/status/2095301347146887306 https://x.com/aviatrixtrc/status/2095301333481894121 https://x.com/DhiyaneshDK/status/2095191115209343273
  nuclei：https://github.com/projectdiscovery/nuclei-templates/blob/main/http/cves/2026/CVE-2026-82329.yaml

- **新入 KEV 三件套（AI／编排栈）**：LiteLLM MCP 认证绕过 **CVE-2026-59822**（修 **v1.84.0**；Wiz 蜜罐见利用）；Starlette BadHost **CVE-2026-48710**（修 **1.0.1**，可与其他链组合）；Kestra OSS **CVE-2026-49869**（修 **1.0.45／1.3.21**，due **09-05**）。**不转写 PoC。**
  GHSA：https://github.com/BerriAI/litellm/security/advisories/GHSA-7488-6r32-c95q https://github.com/Kludex/starlette/security/advisories/GHSA-86qp-5c8j-p5mr https://github.com/kestra-io/kestra/security/advisories/GHSA-5vc5-wxxq-3fjx
  Wiz：https://www.wiz.io/blog/ai-infrastructure-honeypot

- **窗口内其他漏洞信号**：Redis TLS **CVE-2026-81934**（多分支修复，文章含 PoC 讨论——本报不转步骤）；SeaweedFS Filer **CVE-2026-72920**（修 **4.24**）；Static Web Server **CVE-2026-75601**（修 **v2.44.0**）。
  文章／厂商：https://rocket-boys.co.jp/security-measures-lab/redis-cve-2026-81934-tls-poc/ https://github.com/seaweedfs/seaweedfs/security/advisories/GHSA-2v6v-25fm-p4fg https://github.com/static-web-server/static-web-server/security/advisories/GHSA-97q6-jph8-rxgm
  X：https://x.com/securityLab_jp/status/2095301118515728695 https://x.com/dailycve/status/2095303548841890014

- **APT／恶意软件**：ReliaQuest **Gryxa**（AI 辅助构建的 RMM／持久化／取证回传工具包）；CSA／CloudSEK **Aurora** 勒索联盟滥用 Cursor AI 做活体横向；Wiz AI 基础设施蜜罐 IoC（LiteLLM／MCP／挖矿）。
  https://reliaquest.com/blog/threat-spotlight-gryxa-ai-built-toolkit/ https://labs.cloudsecurityalliance.org/research/csa-research-note-aurora-ransomware-cursor-ai-abuse-20260901/ https://www.wiz.io/blog/ai-infrastructure-honeypot

- **工具**：Sliver **仍 v1.7.6**；nuclei-templates **仍 v10.4.8**；另见 Mythic LLM 生成器神话、CPG→Nuclei 编译器、Awesome Red Teaming 列表更新。
  https://github.com/BishopFox/sliver/releases/tag/v1.7.6 https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8 https://github.com/Tito0015/cpg-nuclei-compiler https://github.com/0xMrNiko/Awesome-Red-Teaming
  X：https://x.com/ipurple/status/2095080036759961624 https://x.com/TITO088/status/2094963440724881493

- **ICS**：Rockwell **ICSA-26-244-01..06**（2026-09-01；JVN 09-02 转载）；明日到期 TrueConf **CVE-2026-72530**。
  https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-01 https://jvn.jp/vu/JVNVU90253159/

- **新闻备援**：Risky Business **#851**（2026-09-02）、Risky Bulletin BGP／Virtualizor；tl;dr sec 最新仍 **#343**（08-27）。
  https://www.risky.biz/RB851/ https://risky.biz/RBNEWS608/ https://tldrsec.com/p/tldr-sec-343

## CVE / POC / 漏洞

### 1. 【主条】CISA 2026-09-02 新加七条 KEV

CISA 基于在野利用证据一次性加入七条。其中 JFrog／Sangoma／SonicWall 昨日晚报已作高信号跟踪，今日正式入 KEV 且多条 **due 2026-09-05**（LiteLLM／Starlette due 09-16）。按 BOD 26-04 对公网资产优先修补并做补丁前取证分诊。

地址：
- CISA 警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
- KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- 雷达镜像：https://knutmichael.com/radar/2026-09-02-cisa-adds-seven-known-exploited-vulnerabilities-to-catalog

IoC：未见本警报附带统一狩猎哈希；逐条见下文。

### 2. 【KEV 今日到期】MLflow CVE-2026-64849 SSRF

联邦期限今日。升级至含修复版本并限制 SSRF 可达的元数据／内网。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-64849
- GHSA：https://github.com/mlflow/mlflow/security/advisories/GHSA-7gwp-5pfp-969j
- GitHub Advisory DB：https://github.com/advisories/GHSA-7gwp-5pfp-969j
- 仓库：https://github.com/mlflow/mlflow/pull/24258 https://github.com/mlflow/mlflow/releases/tag/v3.15.0
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-64849
- OSV：https://osv.dev/vulnerability/CVE-2026-64849

IoC：未见公开攻击者 C2／样本哈希。

### 3. 【KEV 续／第二波】PaperCut NG／MF CVE-2026-81578 ＋ CVE-2026-82078（due 2026-09-14）

Emergency Patch Release 3 仍为累积紧急补丁。2026-09-02 厂商补充「第二波」：未充分打补丁且公网可达主机上的事后行为更复杂。Shadowserver／Huntress／nuclei PR #17025 仍适用。公网未打补丁应假定失陷。

地址：
- 厂商：https://www.papercut.com/kb/Main/security-bulletin-27-aug-2026-urgent-security-advisory/
- Behind the scenes：https://www.papercut.com/blog/news/behind-the-scenes-august-security-incident/
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-81578 https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-82078
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-81578 https://nvd.nist.gov/vuln/detail/CVE-2026-82078
- Huntress：https://huntress.com/blog/papercut-actively-exploited
- Rapid7：https://www.rapid7.com/blog/post/etr-papercut-ng-mf-critical-zero-day-exploited-in-the-wild/
- Cyberdaily：https://www.cyberdaily.au/security/14128-papercut-exploitation-continues-to-worsen-as-company-releases-third-emergency-patch
- SOC Prime：https://socprime.com/blog/cve-2026-81578-analysis/
- 仓库：https://github.com/projectdiscovery/nuclei-templates/pull/17025
- X：https://x.com/Shadowserver/status/2094879415100391539 https://x.com/Shadowserver/status/2094874800665636868

IoC：见「地址／IoC 汇总」（狩猎字符串＋R3 SHA256＋厂商披露投放 URL 去活化）。

### 4. 【新入 KEV／due 09-05】SonicWall SMA1000 CVE-2026-83548／83549（SNWLID-2026-0016）

预认证 SSRF 与认证后 OS 命令注入；厂商调查显示在野利用。升级平台热修并限制管理面；若发现 IoC 按厂商建议重装／改密／重置 TOTP。

地址：
- 厂商：https://psirt.global.sonicwall.com/vuln-detail/SNWLID-2026-0016
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-83548 https://nvd.nist.gov/vuln/detail/CVE-2026-83549
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-83548 https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-83549
- 文章：https://www.securityweek.com/sonicwall-warns-of-two-sma1000-zero-days-exploited-in-attacks/
- 下载门户：https://www.mysonicwall.com

IoC：公开 PSIRT 页未见 IoC 列表；联系厂商支持做取证。

### 5. 【新入 KEV／due 09-05】JFrog Artifactory CVE-2026-82329

默认配置下未认证攻击者可获管理权限／伪造管理员令牌并污染制品。限制 Artifactory 暴露、升级并轮换令牌／凭证。**不转写 repro。**

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-82329
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-82329
- 厂商：https://docs.jfrog.com/releases/docs/jfrog-security-advisories
- 文章：https://aviatrix.ai/threat-research-center/jfrog-artifactory-cve-2026-82329-admin-token-forge/
- nuclei：https://github.com/projectdiscovery/nuclei-templates/blob/main/http/cves/2026/CVE-2026-82329.yaml
- X：https://x.com/aviatrixtrc/status/2095301347146887306 https://x.com/DhiyaneshDK/status/2095191115209343273

IoC：未见本窗口统一公开 C2 列表。

### 6. 【新入 KEV／due 09-05】Sangoma Switchvox CVE-2026-9586

未认证 SQLi；媒体／X 称在野反向 shell。升级至厂商修复版本（既有线索 **8.4.0.2**）并限制管理面。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-9586
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-9586
- 厂商发布说明：https://sangomakb.atlassian.net/wiki/spaces/Switchvox/pages/1802371073/Switchvox+-+Release+Notes+Version+8.4.0.2+July+14+2026
- 文章：https://aviatrix.ai/threat-research-center/sangoma-switchvox-cve-2026-9586-reverse-shells/ https://horizon3.ai/attack-research/disclosures/cve-2026-9586-sangoma-switchvox-rce/
- X：https://x.com/aviatrixtrc/status/2095301333481894121

IoC：未见本报可核验的统一公开哈希列表。

### 7. 【新入 KEV】LiteLLM CVE-2026-59822 ＋ Starlette CVE-2026-48710 ＋ Kestra CVE-2026-49869

LiteLLM MCP Streamable HTTP 任意 Bearer 即可建会话（修 v1.84.0）；Starlette Host 头污染 `request.url.path`（修 1.0.1）；Kestra OSS 认证绕过致未认证工作流／RCE（修 1.0.45／1.3.21，due 09-05）。Wiz 蜜罐将 LiteLLM／MCP 与挖矿活动关联。**不转写利用步骤。**

地址：
- LiteLLM GHSA：https://github.com/BerriAI/litellm/security/advisories/GHSA-7488-6r32-c95q
- LiteLLM 发布：https://github.com/BerriAI/litellm/releases/tag/v1.84.0
- Starlette GHSA：https://github.com/Kludex/starlette/security/advisories/GHSA-86qp-5c8j-p5mr
- OSTIF／X41：https://ostif.org/disclosing-the-badhost-vulnerability-in-starlette https://www.x41-dsec.de/lab/advisories/x41-2026-002-starlette
- Kestra GHSA：https://github.com/kestra-io/kestra/security/advisories/GHSA-5vc5-wxxq-3fjx
- Wiz：https://www.wiz.io/blog/ai-infrastructure-honeypot
- KEV 字段页：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-59822 https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-48710 https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-49869
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-59822 https://nvd.nist.gov/vuln/detail/CVE-2026-48710 https://nvd.nist.gov/vuln/detail/CVE-2026-49869

IoC：Wiz 网络／文件指标见汇总。

### 8. 【窗口高信号／尚未入本日 KEV 摘要主表】Redis CVE-2026-81934；SeaweedFS CVE-2026-72920；SWS CVE-2026-75601

Redis TLS 路径 UAF；升级官方修复标签。SeaweedFS filer 在未设 jwt 签名密钥时 gRPC 缺强制认证，升 **4.24**。Static Web Server `/metrics` 绕过 Basic Auth，升 **2.44.0**。

地址：
- Redis NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-81934
- Redis 修复标签例：https://github.com/redis/redis/releases/tag/8.2.9 https://github.com/redis/redis/releases/tag/7.4.11
- 文章：https://rocket-boys.co.jp/security-measures-lab/redis-cve-2026-81934-tls-poc/
- X：https://x.com/securityLab_jp/status/2095301118515728695
- SeaweedFS GHSA：https://github.com/seaweedfs/seaweedfs/security/advisories/GHSA-2v6v-25fm-p4fg
- SeaweedFS 4.24：https://github.com/seaweedfs/seaweedfs/releases/tag/4.24
- DailyCVE／X：https://dailycve.com/seaweedfs-filer-missing-authentication-for-critical-function-cve-2026-72920-critical-dc-sep2026-2109/ https://x.com/dailycve/status/2095303548841890014
- SWS GHSA：https://github.com/static-web-server/static-web-server/security/advisories/GHSA-97q6-jph8-rxgm
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-72920 https://nvd.nist.gov/vuln/detail/CVE-2026-75601

IoC：未见公开攻击者 C2。

### 9. 【KEV 明日到期】TrueConf Server CVE-2026-72530

dateAdded 2026-08-20；due 2026-09-03。限制 4307/TCP 暴露并按厂商／卡巴斯基建议升级。

地址：
- KEV：https://www.cisa.gov/known-exploited-vulnerabilities-catalog?field_cve=CVE-2026-72530
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- 文章：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-breakout-from-isolated-environment/ https://securelist.com/tr/head-mare-targets-trueconf-server-with-phantomcore/120988/

IoC：见厂商／Securelist 原文；本报不抄利用细节。

### 10. ICS Rockwell ICSA-26-244-01..06（2026-09-01）

昨日已报；JVN 2026-09-02 转载。升级各产品修复版本。

地址：
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-01
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-02
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-03
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-04
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-05
- https://www.cisa.gov/news-events/ics-advisories/icsa-26-244-06
- JVN：https://jvn.jp/vu/JVNVU90253159/

IoC：未见公开攻击者 IoC。

## 工具与 GitHub 发布

### 1. Sliver／nuclei-templates（无版本跃迁）

相对昨日：Sliver **仍 v1.7.6**（2026-08-28）；nuclei-templates **仍 v10.4.8**（2026-08-24）。另见 JFrog／PaperCut 相关 nuclei 模板／PR。

地址：
- https://github.com/BishopFox/sliver/releases/tag/v1.7.6
- https://github.com/projectdiscovery/nuclei-templates/releases/tag/v10.4.8
- https://github.com/projectdiscovery/nuclei-templates/blob/main/http/cves/2026/CVE-2026-82329.yaml
- https://github.com/projectdiscovery/nuclei-templates/pull/17025
- X：https://x.com/DhiyaneshDK/status/2095191115209343273 https://x.com/Shadowserver/status/2094879415100391539

IoC：未见公开 IoC。

### 2. 其他工具帖（Search B）

Mythic LLM 生成器、CPG→Nuclei 编译器、Awesome Red Teaming 列表、xosint 等——按授权红队用途跟踪，勿用于未授权目标。

地址：
- X：https://x.com/ipurple/status/2095080036759961624
- 仓库：https://github.com/Tito0015/cpg-nuclei-compiler
- 文章：https://medium.com/@mhiritarek/why-i-built-a-deterministic-cpg-to-nuclei-compiler-in-rust-bcb6c7afe4f8
- X：https://x.com/TITO088/status/2094963440724881493
- 仓库：https://github.com/0xMrNiko/Awesome-Red-Teaming
- X：https://x.com/PadhiyarRushi/status/2095043114067263543 https://x.com/EsGeeks/status/2095165008942391435

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. Gryxa（ReliaQuest）— AI 辅助构建的 RMM／持久化工具包

金融动机行动；RMM 初始访问、多层计划任务／WMI、浏览器凭证窃取；不完整清除会触发 EDR 对抗并**回传处置取证**。处置顺序：先拦基础设施，再一次性清全部持久化。

地址：
- 文章：https://reliaquest.com/blog/threat-spotlight-gryxa-ai-built-toolkit/
- 转载：https://gbhackers.com/gryxa-toolkit-uses-ai/ https://securitybrief.co.uk/story/ai-helped-build-gryxa-malware-operation-report-says

IoC：见汇总（wirbe／gryxa／seczio 等域名与 IP）。

### 2. Aurora 勒索联盟滥用 Cursor AI（CSA／CloudSEK／Gambit）

活体入侵中用 Cursor／Claude 辅助横向与 AD 相关操作；暴露目录泄露聊天记录与工具。

地址：
- CSA：https://labs.cloudsecurityalliance.org/research/csa-research-note-aurora-ransomware-cursor-ai-abuse-20260901/
- 转载：https://thecyberpost.com/news/hackers/aurora-ransomware-operators-use-cursor-ai-in-attacks-against-10-targets/

IoC：未见本摘要可核验的统一公开哈希表（以原文为准）。

### 3. Wiz AI 基础设施蜜罐（LiteLLM／MCP／挖矿）

与今日新 KEV LiteLLM／Starlette 叙事交叉；含网络与落盘路径指标。

地址：
- https://www.wiz.io/blog/ai-infrastructure-honeypot

IoC：见汇总。

### 4. Search C 说明

本轮 Search C（malware analysis／threat report／threat actor）浏览器 CDP 导出失败；仅抢救 42 个 status id 至 `/workspace/x-posts-2026-09-02-search-c.json`，**正文不可靠**，APT 段落以上述公开报告为主，不假装有完整 X 恶意软件时间线。

## 地址／IoC 汇总

### PaperCut（厂商公告，防御狩猎）
- 日志字符串：`ERROR No suitable driver found for jdbc:no:x`；`DB URL: jdbc:derby:memory:pwn;create=true`；`Database error looking up cardID: VALUES CAST(X'cafebabe`；`VALUES CAST('`；`DB URL: jdbc:no:x`
- 落盘模式：`server\lib\<5-char>.class`；`server\data\content\<5-char>.cmd`／`.out`
- 事后工具：服务名 `Remote Access Service`／`SimpleService.exe`（SimpleHelp）；`C:\ProgramData\AnyDesk.exe` 等
- 投放 URL（去活化）：`hxxps://sendit[.]sh/Gg7Rp/ace[.]exe`；`hxxps://download[.]anydesk[.]com/AnyDesk.exe`
- Release 3 安装包 SHA256（厂商表）：
  - MF v26 Win `9375a9c3cf84140a1d8e21b72d3d2c57d85d4de09ea9ae1dc021b64732427da7`
  - MF v26 Linux `02526fea432069eb90279c4e300ea44bf46eaf432a95b05e8a59b55a0c5c001b`
  - MF v26 macOS `bcbe7b2c2d6463b146ec870c9e584e4e404d15756ce822c9277539848d870259`
  - MF v25 Win `ba81e871ca20d688dd26fc950abaa49fb5ccb71a6dce3be97736256f644c0633`
  - MF v25 Linux `03ce77aaed2c8dd8e28b76eb314ee3f5c18b4f13968e5edcb7be469a8faf1c59`
  - MF v25 macOS `2b6abda60be63d42053f3625c52b65ab45ed29b1226de7944b8724520d579ecf`
  - MF v24 Win `0c915094bbf9f6e768e0d12dc9a8005a52594cc0760262010c1cc03861b472aa`
  - MF v24 Linux `61512014718d1fc2d655c298b7a78bb3ec2ee411470cb57c7df6dfbbebc782cc`
  - MF v24 macOS `6f320956b05b7b29fa2943f6a1af488a48c8a69b42a09d1f0e6d2f6b8183fe23`
  - NG v26 Win `51585ee73b70362da3739b8ec77f79336a5c5db9bddcde3fd49ccfe953b529a1`
  - NG v26 Linux `939962a7e660e7bd90dd50e28bce2a337562140813f885c42cf792a2877d05e6`
  - NG v26 macOS `2996de9a85cc5f071df126539d8af8c12b72a46146021a06e15e53aceb5f83c1`
  - NG v25 Win `083e52d55a27724f3f8829537937f80b3977568c27d933cb8f89b61ddc1be9d4`
  - NG v25 Linux `68858979b4db69e7c4dc41f2d50ea2642a087855601bdb7f33d8a294c259fbdb`
  - NG v25 macOS `9f12cc0b4cf009f01c1daba3d227e5a122c163e919517d25b01d4cada235d630`
  - NG v24 Win `ebfea162e52b9f2768b15077647b78d3808473932c4c951f6e82ff9040ca8ced`
  - NG v24 Linux `cc010e42b0e94fe67a973a9b8303848f1ee9028b06d78ae9256daf43611b225e`
  - NG v24 macOS `b655928dda17d138aea14f8a150eb0ff509d7676b33b1b569a9f853319ffd7cc`

### Gryxa（ReliaQuest，去活化）
- 域名：`wirbe[.]com`、`world.wirbe[.]com`、`cdn.wirbe[.]com`、`ver.wirbe[.]com`、`mesh.wirbe[.]com`、`seczio[.]com`、`debian.seczio[.]com`、`gryxa[.]com`、`ui.gryxa[.]com`、`update.gryxa[.]com`、`sevrz[.]com`、`ui.sevrz[.]com`、`update.sevrz[.]com`
- IP：`144.172.107[.]56`、`209.145.55[.]189`
- 路径线索：`C:\ProgramData\WinRTCS`；`...\WER\Temp\.wucache`；`...\Diagnosis\State\.etlcache`

### Wiz AI 蜜罐（去活化）
- IP／域：`185.62.1[.]8`、`185.84.98[.]85`、`94.26.106[.]29`、`pool.hashvault[.]pro`、`crazyeltonproxy[.]top`、`1710.rwlp.be`
- 路径：`/tmp/.dbus-cache/`、`/tmp/.dbus-cache/gmon`

### 其他
- SonicWall／JFrog／Sangoma／MLflow／Redis 等：**未见**本报可核验的额外统一公开 C2 表（或写「见厂商原文」）。
- Search C 抢救 id：**不可当作 IoC**。

## LWiS 固定信源（每日交叉，不替代 X Latest）

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

## 来源搜索 URL

- X Latest A：https://x.com/search?q=(CVE%20OR%20POC%20OR%20exploit%20OR%200day%20OR%20%220-day%22)%20-filter%3Areplies&src=typed_query&f=live
- X Latest B：https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei%20OR%20sliver%20OR%20havoc%20OR%20cobalt)&src=typed_query&f=live
- X Latest C：https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
- LWiS X List：https://x.com/i/lists/1239330068461244424
- LWiS blogs.txt：https://blog.badsectorlabs.com/files/blogs.txt
- Risky Business：https://risky.biz/
- tl;dr sec：https://tldrsec.com/
- 暂停说明：https://blog.badsectorlabs.com/taking-a-break-2026-04-06.html
- CISA KEV JSON：https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json
- 本日 CISA 警报：https://www.cisa.gov/news-events/alerts/2026/09/02/cisa-adds-seven-known-exploited-vulnerabilities-catalog
