# X 安全情报晚报 · 2026-08-23

> 搜集窗口：圣地亚哥时间 **2026-08-22 20:00 至 2026-08-23 20:05**（America/Santiago / UTC-4）。**本报为官方 20:00 cron 晚报。**
> **20:00 本轮 X Latest 已回收**（logged_in=true, blocked=false, 首次尝试成功）。文件 `/workspace/x-posts-2026-08-23.json`（**41** 条）。搜索1 Latest（CVE／POC／exploit／0day）噪声极重，最旧可见约 **2026-08-23T22:32Z**（覆盖短，**不可当作完整 24h CVE 检索**）。搜索2 github.com (C2 OR "red team" OR nuclei) Latest 量少，但可回溯至 **8 月中旬**（满 24h）。搜索3 原 APT 查询为 apartment／俚语噪声；改用 fallback「malware analysis／threat report／threat actor」Latest，最旧可见约 **2026-08-23T12:36Z**。
> 公开备援：**晚间公开备援后到**（`/workspace/security-watch-public-backup-2026-08-23.json`，**collected_at 2026-08-23T20:09:28-04:00**）。CISA KEV catalogVersion **2026.08.21**／**1674** 条已用 JSON 复核；最近一次已核新增仍为 **2026-08-21** Zimbra **CVE-2026-73570**。**未见已核验的 2026-08-22／2026-08-23 KEV 或 ICS。** Windows afd.sys **CVE-2026-68820** KEV 联邦期限确认为 **2026-08-25**。目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
> 规则：每条含完整 https URL；没有指标就写「未见公开 IoC」；不编造 CVE、URL、哈希、日期、推文或 IoC。无 URL 不写叙事。
> 说明：防御向晚报。只记谁／打什么／补丁与狩猎。不转载利用代码、payload、HTTP 头样例、上传绕过或复现步骤。

## 今日摘要

- **期限今日 · TrueConf CVE-2026-72529**：CISA KEV 联邦缓解期限 **今日 2026-08-23**。缺认证；未授权可达 **TCP/4307**。补丁 **5.3.9／5.4.9／5.5.5**。同批 **CVE-2026-72530**（代码注入／隔离逃逸）期限 **2026-09-03**。https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- **期限明日 · Zimbra CVE-2026-73570**：KEV dateAdded **2026-08-21**；联邦期限 **明日 2026-08-24**。补丁 **10.1.20+**（可选 zimbra-snmp 通知启用时）。X 本日：https://x.com/isectech_/status/2091666749653467542

- **晚间备援后到 · ToxicPanda 2.0**（Android 银行木马）：BleepingComputer **2026-08-23 10:23**；Zimperium 资源页 **2026-08-19**。VPN 权限阻断 Play／Play Protect；无障碍；Wireless Debugging／ADB。狩猎：异常 VPN／无障碍／无线调试。IoC：Zimperium 声称见 https://github.com/Zimperium/IOC —— **未见本轮抄录的公开哈希**。https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/
- **晚间备援后到 · llama.cpp ggml-RPC CVE-2026-78147**（现已核验；原晚报因未核验跳过）：NVD published **2026-08-23T23:16:46Z**。`deserialize_tensor` 不信任参数反序列化。与 **CVE-2026-34159** 不同。防御：不要把 llama.cpp RPC 暴露到不可信网络。**未入 KEV**。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-78147
- **晚间备援后到 · WordPress 插件 Security Hardener CVE-2026-16149**（NVD HIGH **8.8**）：**≤2.4.4** REST `/wp/v2/users` `permission_callback` 过弱，Subscriber+ 可建管理员／重置管理员密码。补丁 changeset **3630896**（二手称 **2.4.5**）。**未入 KEV**。IoC：未见公开 IoC。https://nvd.nist.gov/vuln/detail/CVE-2026-16149
- **Entra ID CVE-2026-69836（走回仍有效）**：X 与部分文章仍写在野。**沿用昨日已核验走回**：微软曾误标为已利用；BleepingComputer **2026-08-22 02:56 EDT**；Cybersecurity Dive 周五更新称**无利用**。云侧已缓解，**客户无需打补丁**。**未入 KEV**。https://x.com/JustinMiddler/status/2091670391349510241 https://x.com/so_sthbryan/status/2091660756727316519 https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- **本窗口新报 · TRENDnet TEW-WLC100 CVE-2026-75784**：NVD published **2026-08-18**。固件 **1v2.07b01**。未认证远程、HTTP 头处理栈溢出。VulDB 称 PoC 公开——本报不转载。**未入 KEV**。二手覆盖未见厂商补丁。狩猎：隔离管理面 HTTP。IoC：未见公开 IoC。https://x.com/SecAlertsCo/status/2091658620551274724 https://nvd.nist.gov/vuln/detail/CVE-2026-75784
- **本日回流 · Elementor Pro CVE-2026-32475**：补丁 **4.2.2**。狩猎：`wp-content/uploads/elementor/forms/` 下意外 PHP。不描述绕过。https://x.com/sitedock_jp/status/2091655476677329059 https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- **窗口前 KEV／本日期限提醒 · Windows afd.sys CVE-2026-68820**：KEV 自 **2026-08-11**（Patch Tuesday）。本地提权 UAF。晚间 KEV JSON 复核期限 **2026-08-25**。打补丁后需重启。仅高阶。https://x.com/iss_kk_official/status/2091669227464020277 https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- **本窗口新报 · BabaDeda-RAT**：原始分析 **2026-08-23**。仅高阶。IoC：`c68bffb8c177ade24a91666c3103e6c19097890abc558233ba0eb4f745f41e96`。https://x.com/douglasmun/status/2091545027365490759
- **本日回流 · GoldDigger Android**：IBM 分析日期 **11-08-2026**。高阶：WebSocket C2／无障碍服务。IoC：未见公开 IoC。https://x.com/rst_cloud/status/2091518858989302245 https://www.ibm.com/think/security/golddigger-android-malware-analysis
- **续报 · 车机 HU MoYu／DoFun**：X 本日加链。IoC：cardoor.cn。https://x.com/NSIguy/status/2091518320239374834
- **工具（未克隆）**：APT-Attack-Simulation、rag-redteam。nuclei-templates 本窗口未见新版本。https://github.com/S3N4T0R-0X0/APT-Attack-Simulation https://github.com/Srivatsa03/rag-redteam
- **续报／仍有效（短）**：GitLab CVE-2026-19478、SPIP CVE-2026-77806、NetScaler CVE-2026-19490、WordPress CVE-2026-64638、crates.io 供应链、Talos UAT-10147——仍开放，不重写昨日全文。
- **未独立核验**：SilkParasite 与多条勒索／泄密广告（仅 X URL）。llama.cpp **CVE-2026-78148** 本轮仍未独立核验，不独立成条。

## CVE / POC / 漏洞

### 1. 【期限今日】TrueConf Server CVE-2026-72529／CVE-2026-72530（KEV；72529 联邦期限今日）

已见 8/20、8/22 晚报。CISA **2026-08-20** 将两条列入 KEV。

- **CVE-2026-72529**：缺认证；联邦期限 **今日 2026-08-23**。
- **CVE-2026-72530**：代码注入／隔离环境逃逸；联邦期限 **2026-09-03**。

未授权远程攻击者在可访问 **TCP/4307** 时可影响 TrueConf Server。补丁：**5.3.9**、**5.4.9** 或 **5.5.5**。狩猎：盘点暴露的 4307/TCP；曾暴露主机按可能已被预入侵处置。不写战役剧本或链式步骤。

地址：
- CISA 警报（2026-08-20，新增两条）：https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD CVE-2026-72529：https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- NVD CVE-2026-72530：https://nvd.nist.gov/vuln/detail/CVE-2026-72530
- Kaspersky ICS CERT：https://ics-cert.kaspersky.com/advisories/2026/08/11/trueconf-server-missing-authentication-for-critical-function/
- 文章（BleepingComputer 2026-08-21）：https://www.bleepingcomputer.com/news/security/cisa-orders-feds-to-patch-actively-exploited-trueconf-server-flaws/

IoC：未见公开 IoC。

### 2. 【期限明日】Zimbra Collaboration Suite CVE-2026-73570（KEV dateAdded 2026-08-21）

已见 8/21–8/22。CISA 警报与 KEV dateAdded 均为 **2026-08-21**；联邦缓解期限 **明日 2026-08-24**。影响 Zimbra Collaboration **10.1.20 之前**，在可选 **zimbra-snmp** 已安装且 SNMP 通知已启用时，特制 SMTP 可导致以 zimbra 用户执行操作系统命令。补丁：**10.1.20+**。狩猎（对照昨日 CERT Polska）：`/var/log/zimbra.log` 中意外 Service status change；检查 jetty webapps 与 `/tmp/` 下近期由 zimbra 用户拥有的文件。只记路径，不写利用。本轮检索 **未见 8/23 新 KEV**（目录仍 1674 条）。

地址：
- X（@isectech_，本日）：https://x.com/isectech_/status/2091666749653467542
- CISA 警报（2026-08-21）：https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- 厂商：https://wiki.zimbra.com/wiki/Zimbra_Security_Advisories
- CERT Polska：https://moje.cert.pl/komunikaty/2026/145/aktywnie-wykorzystywana-podatnosc-w-zimbra-collaboration-suite/

IoC：未见公开 IoC。

### 3. 【走回仍有效】Microsoft Entra ID CVE-2026-69836（云侧已缓解；勿写成已核实在野）

X 本日（@JustinMiddler／@so_sthbryan）与 The Register／The Hacker News 等仍写 CVSS 10.0、在野或「攻击中」。**沿用 8/22 已核验走回**：BleepingComputer **2026-08-22 02:56 EDT** 称微软曾**误标为已利用**；Cybersecurity Dive：周五更新称**无利用**。托管云服务已缓解，**客户无需打补丁、无客户侧补丁包**。**未入 KEV**。防御：审阅 Entra 登录与特权角色日志。本晚报不把本日 X 复述覆盖已核走回。

地址：
- X（@JustinMiddler）：https://x.com/JustinMiddler/status/2091670391349510241
- X（@so_sthbryan）：https://x.com/so_sthbryan/status/2091660756727316519
- 文章（The Register）：https://www.theregister.com/cyber-crime/2026/08/21/microsoft-sounds-alarm-as-perfect-10-entra-id-flaw-comes-under-attack/5290925
- 文章（The Hacker News）：https://thehackernews.com/2026/08/microsoft-entra-id-flaw-cvss-100.html
- 文章（BleepingComputer，走回已核验）：https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- 文章（Cybersecurity Dive）：https://www.cybersecuritydive.com/news/microsoft-maximum-severity-flaw-entra-id-exploitation/828501/
- 厂商 MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-69836

IoC：未见公开 IoC。

### 4. 【本窗口新报】TRENDnet TEW-WLC100 HTTP 头处理栈溢出 CVE-2026-75784（未入 KEV）

X（@SecAlertsCo）。NVD published **2026-08-18**。产品 **TEW-WLC100**，固件 **1v2.07b01**。未认证远程可达；HTTP 头处理中的栈溢出，完整性／机密性／可用性均可受影响。VulDB 称 PoC 公开——**本报不转载 PoC、不写请求头样例或 payload**。**未入 KEV**。二手覆盖中**未见厂商补丁**。狩猎：将无线控制器**管理 HTTP 与业务网隔离**，限制对管理面的网络可达性；盘点仍跑 1v2.07b01 的设备。函数名不是 IoC，不列入指标。

地址：
- X（@SecAlertsCo）：https://x.com/SecAlertsCo/status/2091658620551274724
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-75784
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-75784

IoC：未见公开 IoC。

### 5. 【本日回流】Elementor Pro CVE-2026-32475（补丁 4.2.2；未当大规模在野）

昨日晚报已报；X 本日再回流（@sitedock_jp／@yousukezan）。Forms File Upload 未认证文件上传可至远程代码执行。影响 **≤4.2.1**（已发布表单含 File Upload 时）。补丁 **4.2.2**（2026-08-19）。狩猎：`wp-content/uploads/elementor/forms/` 下意外 PHP。**不描述绕过细节。** Patchstack 8/19 二手综述：未见已确认大规模利用——**不当成在野事实**。

地址：
- X（@sitedock_jp）：https://x.com/sitedock_jp/status/2091655476677329059
- X（@yousukezan）：https://x.com/yousukezan/status/2091660967902142685
- Patchstack：https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- CVE：https://www.cve.org/CVERecord?id=CVE-2026-32475

IoC：未见公开 IoC。

### 6. 【窗口前 KEV／本日期限提醒】Windows afd.sys CVE-2026-68820（CISA 期限 8/25）

KEV 自 **2026-08-11**（八月 Patch Tuesday）。本地提权，释放后使用（UAF），组件 **afd.sys**。晚间 KEV JSON 复核：联邦期限确认为 **2026-08-25**（X @iss_kk_official 日文解说亦称 8/25）。处置：按 MSRC 安装对应安全更新；**补丁后需重启**。仅高阶，不写利用原语。本窗口检索未见 8/23 新 KEV 条目。

地址：
- X（@iss_kk_official）：https://x.com/iss_kk_official/status/2091669227464020277
- MSRC：https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- Qualys（BOD 26-04 要求综述）：https://blog.qualys.com/product-tech/2026/08/18/cve-2026-68820-kev-bod-26-04-requirements
- CISA KEV 目录：https://www.cisa.gov/known-exploited-vulnerabilities-catalog

IoC：未见公开 IoC。

### 7. 【晚间备援后到 · 现已核验】llama.cpp ggml-RPC CVE-2026-78147（原晚报未核验跳过）

NVD published **2026-08-23T23:16:46.243Z**（HIGH，CNA CVSS 3.1 **7.3**）。ggml-org llama.cpp 组件 ggml-RPC：`deserialize_tensor` 对不信任的 `op`／`op_params` 反序列化。NVD 写明与 **CVE-2026-34159**（GHSA-j8rj-fmpv-wcxw／PR 20908，仅拒绝 nullptr buffer）**不同**。GitHub issue **25289** 因不活跃关闭。本轮未见独立 GHSA 映射。防御：**不要把 llama.cpp RPC 暴露到不可信网络**。不写利用细节。**未入 KEV**。同窗口 CVEnew 曾并列 **CVE-2026-78148**——本报仍未独立核验，不展开。对照窗口前已公开 **CVE-2026-39909**（GHSA **2026-08-21**）。

地址：
- NVD CVE-2026-78147：https://nvd.nist.gov/vuln/detail/CVE-2026-78147
- GitHub issue 25289：https://github.com/ggml-org/llama.cpp/issues/25289
- 仓：https://github.com/ggml-org/llama.cpp/
- 对照 GHSA CVE-2026-39909：https://github.com/advisories/GHSA-fpvp-jgx3-4w9q
- 对照 NVD CVE-2026-39909：https://nvd.nist.gov/vuln/detail/CVE-2026-39909

IoC：未见公开 IoC。

### 8. 【晚间备援说明 · 非新 0-day】justhtml CVE-2026-5388／7808／8445（NVD 8/23 刊出；GHSA 2026-04-09 延迟编号）

NVD 于 **2026-08-23** 刊出 justhtml sanitizer 相关 CRITICAL 条目。这是**延迟分配的 CVE 编号**，**不是 8/23 新 0-day**。GHSA-c9vm-hv86-f23r 日期 **2026-04-09**（Moderate；补丁 **1.15.0**）。备援摘要：多数自定义策略问题不打默认 `sanitize=True`。CVE-2026-7808 补丁 **1.16.0**；CVE-2026-8445（Markdown `to_markdown`）补丁 **1.12.0**。处置：升到当前 justhtml。**未入 KEV**。本报不展开 docker-socket 相关声称。

地址：
- NVD CVE-2026-5388：https://nvd.nist.gov/vuln/detail/CVE-2026-5388
- NVD CVE-2026-7808：https://nvd.nist.gov/vuln/detail/CVE-2026-7808
- NVD CVE-2026-8445：https://nvd.nist.gov/vuln/detail/CVE-2026-8445
- GHSA（2026-04-09）：https://github.com/EmilStenstrom/justhtml/security/advisories/GHSA-c9vm-hv86-f23r

IoC：未见公开 IoC。


### 9. 【续报／仍有效 · 短】GitLab／SPIP／NetScaler／WordPress／crates.io

下列昨日已展开，本窗口无新厂商主文；**仍开放／仍有效**，不重写全文。

- **GitLab GraphQL CVE-2026-19478**：数据完整性（不是已确认 RCE）；补丁 **18.11.11／19.0.8／19.1.6／19.2.4**。WatchTowr 蜜罐见披露后约 2 日探测。**仍未入 KEV**。狩猎：日志 `@gl_introduced`；限制未认证 `/api/graphql`。https://www.securityweek.com/critical-gitlab-flaw-exploited-shortly-after-disclosure/ https://github.com/advisories/GHSA-6whr-xjjm-6pf8
- **SPIP CVE-2026-77806**：补丁 **4.4.21**。厂商／CVE 称利用尝试或 8 月在野；NVD SSVC 快照曾标 exploitation none；**未入 KEV**。狩猎：只查意外 **X-Spip-Filtre** 请求头（只记头名）。https://blog.spip.net/Mise-a-jour-critique-de-securite-sortie-de-SPIP-4-4-21.html
- **NetScaler CVE-2026-19490**：认证绕过。补丁 **14.1-73.32／13.1-63.21／FIPS 14.1-73.32／13.1-37.277**。https://support.citrix.com/external/article/CTX696939/netscaler-adc-and-netscaler-gateway-secu.html
- **WordPress CVE-2026-64638**：官方 **7.0.3**（2026-08-06）。登录页预认证反射型 XSS；完整 PHP 路径需已登录管理员交互，**不可蠕虫化**。https://wordpress.org/news/2026/08/wordpress-7-0-3-release/
- **crates.io arrayref／internment／append-only-vec ＋ proc-macro1**（CVE-2026-77651／77649／77650）：钉死 **0.3.9／0.8.6／0.1.8**。IoC 见 8/22 晚报，本窗口无新哈希。https://blog.rust-lang.org/2026/08/20/supply-chain-attack-on-arrayref/

IoC：未见本窗口新增公开 IoC（crates.io 既有指标见昨日汇总）。

### 10. 【晚间备援后到】WordPress 插件 Security Hardener CVE-2026-16149（NVD HIGH 8.8；未入 KEV）

NVD published **2026-08-23T00:16:50.233Z**。插件 **Security Hardener ≤2.4.4**。默认开启的用户枚举防护把 REST `/wp/v2/users` 的 `permission_callback` 弱化为仅 `is_user_logged_in()`，剥掉 `create_users`／`promote_user`／`edit_users`／`delete_users`。已认证 **Subscriber+** 可创建管理员或重置现有管理员密码。CNA CVSS **8.8**。补丁：WordPress.org changeset **3630896**（二手称安全修复为 **2.4.5**）。狩猎：意外管理员创建与 REST `/wp/v2/users` 写操作。**不写请求体样例。****未入 KEV**。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-16149
- changeset 3630896：https://plugins.trac.wordpress.org/changeset/3630896/security-hardener
- Wordfence（NVD 参考）：https://www.wordfence.com/threat-intel/vulnerabilities/id/64f1a71f-e210-4191-bfb4-56f8568180ed?source=cve

IoC：未见公开 IoC。

### 11. 【晚间备援后到】Mailgun for WordPress CVE-2026-78003（未认证 SSRF；CVSS 9.8）

NVD published **2026-08-22T09:16:53.543Z**（昨晚报漏报；晚间备援补入）。插件 **≤2.2.0**。未认证 SSRF：经 `add_list()` 使用站点 Mailgun API 密钥向 Mailgun API 发已认证 POST。Wordfence／NVD：入站路由可截获密码重置邮件并导致管理员接管。CNA CVSS **9.8**。NVD 参考**未见已列补丁版本**。狩猎：盘点 Mailgun 入站路由与意外 `add_list`／API 使用。**不写路径穿越或请求样例。****未入 KEV**。

地址：
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-78003
- Wordfence（NVD 参考）：https://www.wordfence.com/threat-intel/vulnerabilities/id/110e888d-69fc-4682-b908-2b62288c5227?source=cve

IoC：未见公开 IoC。

### 12. 【晚间备援后到 · 短】IoT：Comfast CF-N1-S CVE-2026-78050／TRENDnet TEW-821DAP CVE-2026-77946（NTP 时区栈溢出家族；不转载 PoC）

- **Comfast CF-N1-S CVE-2026-78050**：固件 **2.6.0.1**。Web 管理 NTP 时区处理栈溢出。NVD published **2026-08-23T00:16:50.590Z**。CNA CVSS **9.9**。VulDB 称利用已公开——**本报不转载、不写 CGI／参数样例**。NVD **未见厂商补丁 URL**。
- **TRENDnet TEW-821DAP CVE-2026-77946**：固件 **2.2.01b05**。相关 NTP 时区处理栈溢出。NVD published **2026-08-22T11:16:54.447Z**。CNA CVSS **10.0**。同样不转载 PoC。NVD **未见厂商补丁 URL**。

狩猎：将设备**管理 HTTP 与业务网隔离**；盘点上述固件。**未入 KEV**。

地址：
- NVD CVE-2026-78050：https://nvd.nist.gov/vuln/detail/CVE-2026-78050
- NVD CVE-2026-77946：https://nvd.nist.gov/vuln/detail/CVE-2026-77946

IoC：未见公开 IoC。

### 13. 【晚间备援后到】Netty netty-handler CVE-2026-62243（OPENSSL 主机名校验绕过）

GHSA-p85m-gvr3-788c。**CVE-2026-62243**（备援 NVD 已列）。`SslProvider.OPENSSL` 客户端路径在无法包装普通（非 extended）`X509TrustManager` 时跳过主机名校验（GHSA：Java 25+ 上 Unsafe 包装不可用）。中间人可出示其他主机名证书。影响 **4.2.0.Final–4.2.16.Final** 与 **≤4.1.136.Final**。补丁：**4.2.17.Final**／**4.1.137.Final**。变通：使用 `X509ExtendedTrustManager` 或 `SslProvider.JDK`。**未入 KEV**。

地址：
- GHSA：https://github.com/netty/netty/security/advisories/GHSA-p85m-gvr3-788c
- GHSA 镜像：https://github.com/advisories/GHSA-c3j3-64rf-grvf
- NVD：https://nvd.nist.gov/vuln/detail/CVE-2026-62243

IoC：未见公开 IoC。

### 其他 NVD HIGH（一句话，不展开）

TaxHacker **CVE-2026-78062**（硬编码 JWT）；Tenda CH22 **CVE-2026-78063**／**CVE-2026-78141**（命令注入声称）；Barangay **CVE-2026-78143**（SQLi）；PPWP Password Protect Pages **CVE-2026-0551**（Contributor+ 对象注入）。隔离管理面／升补丁。**未入 KEV**。不转载 PoC。https://nvd.nist.gov/vuln/detail/CVE-2026-78062 https://nvd.nist.gov/vuln/detail/CVE-2026-0551

## 工具与 GitHub 发布

### 1. 【本窗口】S3N4T0R-0X0／APT-Attack-Simulation（仅 URL，未克隆）

X（@_thegb_）分享对抗模拟仓库，含 APT 战役仿真（C2／技术复现面向防御测试）。**未克隆**。本报只记仓库 URL，不抄利用手册或仿真剧本。

地址：
- X（@_thegb_）：https://x.com/_thegb_/status/2091405653101228107
- GitHub：https://github.com/S3N4T0R-0X0/APT-Attack-Simulation

IoC：未见公开 IoC。

### 2. 【本窗口】Srivatsa03／rag-redteam（仅 URL，未克隆）

X（@Dinosn）。面向 RAG 流水线的 CI 友好红队：提示注入、源文档泄漏、跨文档夹带。定位在 RAG 评估工具与 LLM 扫描器之间。**未克隆**。不写攻击 payload。

地址：
- X（@Dinosn）：https://x.com/Dinosn/status/2091392888500351167
- GitHub：https://github.com/Srivatsa03/rag-redteam

IoC：未见公开 IoC。

### 3. nuclei／红队框架版本

projectdiscovery/nuclei-templates 昨日核验最新标签仍为 **v10.4.7**（2026-08-03）。本窗口 X 有 nuclei 仓链接回流，**未见已核验的 nuclei／nuclei-templates 新版本**。未见已核验的 Sliver／Havoc／Mythic 新版本。ESP32-C2 硬件／OTA 项目命中「C2」芯片名，**与命令控制无关，跳过**。

地址：
- nuclei-templates 发布页：https://github.com/projectdiscovery/nuclei-templates/releases
- nuclei 仓：https://github.com/projectdiscovery/nuclei

IoC：未见公开 IoC。

## APT / Malware 分析

### 1. 【晚间备援后到】ToxicPanda 2.0 Android 银行木马（BC 2026-08-23；Zimperium 2026-08-19）

BleepingComputer **2026-08-23 10:23** 覆盖 Zimperium zLabs **2026-08-19** 研究。高阶：针对 **349** 银行／金融／加密／电子钱包应用、**16** 国、**167** 条远程命令。以 VPN 权限阻断 Google Play／Play Protect／Play Services，再索无障碍（Accessibility）；自动化 Wireless Debugging／ADB 配对以获 shell 后提权与持久化。BC／Zimperium 另记 PIN 收割（约 **140** 应用）、AWS 托管桶分发、OEM 自启动（Xiaomi／OPPO／Vivo／Samsung／Huawei）、HTTPS 后 AES-ECB WebSocket。狩猎：异常 VPN／无障碍／无线调试；意外 AWS APK 下载；锁屏／覆盖层钓鱼。Zimperium 声称 IoC 在 https://github.com/Zimperium/IOC —— **本轮未检索到可核验的文件列表，未见本轮抄录的公开哈希**（不编造）。仅高阶，不写命令协议或复现步骤。

地址：
- 文章（BleepingComputer 2026-08-23 10:23）：https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/
- Zimperium 资源页（2026-08-19）：https://zimperium.com/resources/zimperium-zlabs-uncovers-toxicpanda-2.0-a-significantly-more-powerful-android-banking-trojan
- Zimperium 博文：https://zimperium.com/blog/the-toxicpanda-never-sleeps-toxicpanda-2.0-prepares-its-next-strike-on-mobile
- 声称 IoC 仓（本轮未见列表）：https://github.com/Zimperium/IOC

IoC：未见本轮抄录的公开哈希。

### 2. 【本窗口新报】BabaDeda-RAT／CNCMachineRMS 样本集（原始分析 2026-08-23）

@douglasmun **2026-08-23** 发布 CNCMachineRMS BabaDeda-RAT 样本集分析（桌面／移动版报告）并指向 MalwareBazaar。仅高阶：远程访问木马样本集，不写命令协议、配置解密或利用步骤。哈希照录推文／Bazaar 卡。

地址：
- X（@douglasmun）：https://x.com/douglasmun/status/2091545027365490759
- 分析（desktop）：https://douglasmun.github.io/CNCMachineRMS%20BabaDeda-RAT%20Sample%20Set%20Malware%20Analysis%20Report%20(desktop).html
- MalwareBazaar：https://bazaar.abuse.ch/sample/c68bffb8c177ade24a91666c3103e6c19097890abc558233ba0eb4f745f41e96/

IoC：
- c68bffb8c177ade24a91666c3103e6c19097890abc558233ba0eb4f745f41e96

### 3. 【本日回流】GoldDigger Android（IBM 分析日期 11-08-2026）

X（@rst_cloud）本日回流 IBM「Striking gold: Inside the GoldDigger Android malware」。报告日期 **11-08-2026**。高阶：WebSocket C2；无障碍（accessibility）服务滥用；报道还提及应用虚拟化与凭据／设备信息外泄。关联家族名 Golddigger／Godfather（IBM／卡片，不据此单独归因）。本报未从 IBM 页核出可照录哈希，**不编造哈希**。

地址：
- X（@rst_cloud）：https://x.com/rst_cloud/status/2091518858989302245
- IBM：https://www.ibm.com/think/security/golddigger-android-malware-analysis

IoC：未见公开 IoC。

### 4. 【续报】Android 车机头单元 BADBOX／MoYu／DoFun（X 本日加链）

昨日 Kaspersky／BleepingComputer **2026-08-22**：针对 Android 车机头单元的供应链／更新应用感染，用于广告欺诈或住宅代理。X 本日 @NSIguy 加链回流。DoFun 称已处理。高阶模块名可记，不写样本内容。

地址：
- X（@NSIguy）：https://x.com/NSIguy/status/2091518320239374834
- Kaspersky：https://www.kaspersky.com/blog/car-botnet-malware-for-head-units-with-android/56296/
- BleepingComputer：https://www.bleepingcomputer.com/news/security/hackers-infect-android-car-head-units-with-proxy-botnet-malware/

IoC：
- cardoor.cn

### 5. 【续报／仍有效 · 短】Cisco Talos UAT-10147 与 SPECTRE

已见 8/20、8/22。本窗口无新 Talos 主文。中文语境牟利集群，打暴露的 IIS／Linux Web；植入仅记名称。狩猎仍可用昨日 C2／域名／哈希。仅高阶，不抄利用手册。

地址：
- Talos 主文：https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/
- Talos SPECTRE：https://blog.talosintelligence.com/uat-10147-deploys-spectre-a-cross-platform-implant-with-linux-rootkit-and-byovd-capabilities/
- GitHub IoC：https://github.com/Cisco-Talos/IOCs/blob/main/2026/08/UAT-10147%20integrates%20agentic%20AI.txt

IoC：本窗口无新增；既有指标见 8/22 晚报。

### 未独立核验（SilkParasite／勒索与泄密广告；仅 X URL）

下列仅为 X 广告或单源声称，**未独立核验**。**不把受害站点当作 IoC。** 未见公开攻击者 IoC。

- SilkParasite（声称 China-nexus、中亚政府；DailyDarkWeb，无厂商主文）：https://x.com/DailyDarkWeb/status/2091541717761642775
- shinyhunters 声称 CyrusOne：https://x.com/ThreatAtlas/status/2091625209358848406
- LockBit 5.0 声称 ADT（帖称 2026-04-24 曾上 ShinyHunters 清单）：https://x.com/FalconFeedsio/status/2091592068644884789
- CoinbaseCartel 声称 Westwing Group SE：https://x.com/FalconFeedsio/status/2091643392816214268
- GENESIS 声称 Hospitality Health ER：https://x.com/FalconFeedsio/status/2091643285140046025
- Storm 声称 City of Mitchell：https://x.com/FalconFeedsio/status/2091633510524338435
- Qilin 声称 S.E.M.P. s.r.l. 等意大利目标：https://x.com/FalconFeedsio/status/2091596271819853894
- Barracuda 勒索／勒索活动（新兴声称）：https://x.com/DailyDarkWeb/status/2091561084096319534
- 其他泄密／失陷声称（Integrity Technology Group、Andover、AdaptHealth、FFT、TF1、mgovcloud、Calypso Portal、K7 RAT 广告）：https://x.com/DailyDarkWeb/status/2091543243317993969 https://x.com/DailyDarkWeb/status/2091556289805476278 https://x.com/GullyStaten/status/2091553888121881019 https://x.com/DailyDarkWeb/status/2091525011899113721 https://x.com/intels_daily/status/2091586508436160548 https://x.com/ThreatIntelIN/status/2091630271376535961 https://x.com/CyberPulse56/status/2091678135960166907 https://x.com/CyberPulse56/status/2091553000485769699

IoC：未见公开攻击者 IoC。

## 地址／IoC 汇总

### 本窗口新报
- c68bffb8c177ade24a91666c3103e6c19097890abc558233ba0eb4f745f41e96（BabaDeda-RAT／MalwareBazaar）
- ToxicPanda 2.0：Zimperium 声称 IoC 仓未在本轮抄录 —— **未见本轮抄录的公开哈希**
- llama.cpp CVE-2026-78147／Security Hardener CVE-2026-16149／Mailgun CVE-2026-78003／Comfast CVE-2026-78050／TEW-821DAP CVE-2026-77946／Netty CVE-2026-62243／justhtml 延迟编号：未见公开 IoC（不把函数名或环境变量名当 IoC）
- TRENDnet CVE-2026-75784／Elementor／Entra／TrueConf／Zimbra／afd.sys／GoldDigger：未见公开 IoC

### 续报（本窗口无新哈希）
- cardoor.cn（车机 HU／MoYu）
- crates.io 与 UAT-10147／SPECTRE 既有指标：见 2026-08-22 晚报，本窗口不重抄

### 参考 URL（情报页，非恶意基础设施）
- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/20/cisa-adds-two-known-exploited-vulnerabilities-catalog
- https://www.cisa.gov/news-events/alerts/2026/08/21/cisa-adds-one-known-exploited-vulnerability-catalog
- https://nvd.nist.gov/vuln/detail/CVE-2026-72529
- https://nvd.nist.gov/vuln/detail/CVE-2026-73570
- https://nvd.nist.gov/vuln/detail/CVE-2026-75784
- https://www.cve.org/CVERecord?id=CVE-2026-75784
- https://nvd.nist.gov/vuln/detail/CVE-2026-69836
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-69836
- https://msrc.microsoft.com/update-guide/vulnerability/CVE-2026-68820
- https://blog.qualys.com/product-tech/2026/08/18/cve-2026-68820-kev-bod-26-04-requirements
- https://patchstack.com/articles/critical-unauthenticated-file-upload-to-rce-in-elementor-pro-plugin/
- https://www.cve.org/CVERecord?id=CVE-2026-32475
- https://github.com/advisories/GHSA-fpvp-jgx3-4w9q
- https://nvd.nist.gov/vuln/detail/CVE-2026-39909
- https://nvd.nist.gov/vuln/detail/CVE-2026-8445
- https://nvd.nist.gov/vuln/detail/CVE-2026-7808
- https://nvd.nist.gov/vuln/detail/CVE-2026-78147
- https://github.com/ggml-org/llama.cpp/issues/25289
- https://nvd.nist.gov/vuln/detail/CVE-2026-16149
- https://plugins.trac.wordpress.org/changeset/3630896/security-hardener
- https://nvd.nist.gov/vuln/detail/CVE-2026-78003
- https://nvd.nist.gov/vuln/detail/CVE-2026-78050
- https://nvd.nist.gov/vuln/detail/CVE-2026-77946
- https://nvd.nist.gov/vuln/detail/CVE-2026-62243
- https://github.com/netty/netty/security/advisories/GHSA-p85m-gvr3-788c
- https://nvd.nist.gov/vuln/detail/CVE-2026-5388
- https://github.com/EmilStenstrom/justhtml/security/advisories/GHSA-c9vm-hv86-f23r
- https://www.bleepingcomputer.com/news/security/toxicpanda-android-malware-uses-vpn-permissions-to-block-google-play/
- https://zimperium.com/resources/zimperium-zlabs-uncovers-toxicpanda-2.0-a-significantly-more-powerful-android-banking-trojan
- https://zimperium.com/blog/the-toxicpanda-never-sleeps-toxicpanda-2.0-prepares-its-next-strike-on-mobile
- https://github.com/Zimperium/IOC
- https://github.com/S3N4T0R-0X0/APT-Attack-Simulation
- https://github.com/Srivatsa03/rag-redteam
- https://github.com/projectdiscovery/nuclei-templates/releases
- https://douglasmun.github.io/CNCMachineRMS%20BabaDeda-RAT%20Sample%20Set%20Malware%20Analysis%20Report%20(desktop).html
- https://bazaar.abuse.ch/sample/c68bffb8c177ade24a91666c3103e6c19097890abc558233ba0eb4f745f41e96/
- https://www.ibm.com/think/security/golddigger-android-malware-analysis
- https://www.kaspersky.com/blog/car-botnet-malware-for-head-units-with-android/56296/
- https://www.bleepingcomputer.com/news/security/hackers-infect-android-car-head-units-with-proxy-botnet-malware/
- https://www.bleepingcomputer.com/news/microsoft/microsoft-warns-of-max-severity-entra-id-flaw-exploited-in-attacks/
- https://thehackernews.com/2026/08/microsoft-entra-id-flaw-cvss-100.html
- https://www.theregister.com/cyber-crime/2026/08/21/microsoft-sounds-alarm-as-perfect-10-entra-id-flaw-comes-under-attack/5290925
- https://blog.talosintelligence.com/uat-10147-chinese-speaking-adversary-integrates-agentic-ai-into-post-compromise-operations/

## 来源搜索 URL

- https://www.cisa.gov/known-exploited-vulnerabilities-catalog
- https://nvd.nist.gov/
- https://x.com/search?q=CVE%20OR%20POC%20OR%20exploit%20OR%200day&src=typed_query&f=live
- https://x.com/search?q=github.com%20(C2%20OR%20%22red%20team%22%20OR%20nuclei)&src=typed_query&f=live
- https://x.com/search?q=APT%20OR%20%22malware%20analysis%22%20OR%20%22threat%20report%22&src=typed_query&f=live
- https://x.com/search?q=%22malware%20analysis%22%20OR%20%22threat%20report%22%20OR%20%22threat%20actor%22&src=typed_query&f=live
