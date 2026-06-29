# 🔑 Awesome API Key Leak Detection
**语言:** [English](README.md) • **简体中文** • [繁體中文](README.zh-TW.md) • [Español](README.es.md) • [Français](README.fr.md) • [Deutsch](README.de.md) • [日本語](README.ja.md) • [한국어](README.ko.md) • [Português (BR)](README.pt-BR.md) • [Русский](README.ru.md) • [العربية](README.ar.md) • [Italiano](README.it.md)

> 一份精选的 **API key 发现 / 大模型(LLM) API key 泄露检测** 工具与资源清单。
> 在自研的 [Key Scanner](https://github.com/irmacardozo993-lgtm/key-scanner) 基础上,系统梳理前人所有相关项目 —— **站在巨人的肩膀上,避免重复造轮子**。
>
> 每个工具都标注了独特技法与「可吸收的点子」,方便你判断哪些值得借鉴进自己的企业级安全扫描器。

<a id="acknowledgments"></a>
## 🙏 致谢

- **[Telegram OpenClaw 中文社区](https://t.me/OpenClaw_Group)** — Telegram 上的 OpenClaw 中文社区 — 感谢支持与讨论。
- **[Linux.do](https://linux.do)** — 中文开发者与技术社区(Discourse) — 感谢反馈与传播。

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg) ![Tools](https://img.shields.io/badge/tools-130+-blue) ![Focus: LLM Keys](https://img.shields.io/badge/focus-LLM%20keys-purple) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)

---

## 目录

- [1. 🏆 巨人:工业级密钥扫描器](#giants)
- [2. 🚀 高性能 / 新兴扫描器](#hp-scanner)
- [3. 🔎 GitHub 侦察 & 公开仓库猎取](#github-recon)
- [4. 🤖 LLM / AI Key 专项 ⭐](#llm-key)
- [5. ✅ Key 测活 / 有效性校验](#key-validator)
- [6. 🧬 正则 / 规则库](#pattern-db)
- [7. 🕸️ JS / Web / 浏览器密钥提取](#js-web)
- [8. 🐳 容器 / 运行时 / 内存 / 网关脱敏](#container-runtime)
- [9. 🍯 蜜罐 / Canary Token](#honeypot)
- [10. 🪝 AI Agent 密钥拦截钩子](#ai-agent-hook)
- [11. 🏢 SaaS / 多平台监控](#saas)
- [12. 📚 参考资源 & 字典](#reference)
- [13. 🧪 实验性 / 小工具](#experimental)
- [14. 🧩 技术借鉴速查(吸收点子)](#absorb)
- [🙋 贡献](#contributing) · [🙏 致谢](#acknowledgments) · [📜 许可](#license)

---

## 图例

| 标记 | 含义 |
|------|------|
| ⭐ | GitHub 星数(调研时点,近似) |
| `语言` | 主语言 |
| `许可` | 开源协议 |
| 🤖 | 与 LLM/AI key 泄露检测直接相关(本清单重点) |
| · | 部分相关(覆盖 AI key 等多类) |
| 🔒归档 | 仓库已 archived |

> 🤖 标记的条目是「大模型 API key 泄露检测」赛道——目前 GitHub 上**尚无权威 awesome list 覆盖**的空白区。

---

<a id="matrix"></a>
## 🗺️ 全景图:核心工具能力矩阵

> 横向对比核心工具的能力维度,快速定位「缺什么/抄什么」。

| 工具 | ⭐ | 检测 | 测活 | 多源(网/本地) | LLM-key | 语言 |
|------|----|------|------|----------------|---------|------|
| [gitleaks](https://github.com/gitleaks/gitleaks) | 27.8k | ✅ | — | 网+本地 | — | Go |
| [trufflehog](https://github.com/trufflesecurity/trufflehog) | 26.8k | ✅ | ✅ | 本地 | ✅ | Go |
| [detect-secrets](https://github.com/Yelp/detect-secrets) | 4.6k | ✅ | — | — | ✅ | Python |
| [ggshield](https://github.com/GitGuardian/ggshield) | 2.0k | ✅ | — | — | ✅ | Python |
| [talisman](https://github.com/thoughtworks/talisman) | 2.1k | ✅ | — | 本地 | — | Go |
| [secretlint](https://github.com/secretlint/secretlint) | 1.4k | ✅ | — | 网+本地 | ✅ | TypeScript |
| [kingfisher](https://github.com/mongodb/kingfisher) | 1.1k | ✅ | ✅ | — | ✅ | Rust |
| [titus](https://github.com/praetorian-inc/titus) | 598 | ✅ | ✅ | — | ✅ | Go |
| [noseyparker](https://github.com/praetorian-inc/noseyparker) | 2.3k | ✅ | — | 网+本地 | — | Rust |
| [CredSweeper](https://github.com/Samsung/CredSweeper) | 209 | ✅ | — | 本地 | ✅ | Python |
| [keyhacks](https://github.com/streaak/keyhacks) | 6.3k | ✅ | ✅ | — | — | — |
| [keyscope](https://github.com/SpectralOps/keyscope) | 411 | ✅ | ✅ | — | — | Rust |
| [driftwood](https://github.com/trufflesecurity/driftwood) | 435 | ✅ | ✅ | 网+本地 | — | Go |
| [llm-api-key-checker](https://github.com/ssfun/llm-api-key-checker) | 147 | ✅ | ✅ | — | ✅ | JavaScript |
| [keyprobe](https://github.com/datumbrain/keyprobe) | 2 | ✅ | ✅ | 本地 | ✅ | Go |
| [keyhunter](https://github.com/fadidevv/keyhunter) | 36 | ✅ | ✅ | 网络 | ✅ | Rust |
| [keyleak-detector](https://github.com/Amal-David/keyleak-detector) | 261 | ✅ | — | — | ✅ | Python |
| [gitrob](https://github.com/michenriksen/gitrob) | 6.2k | ✅ | — | 网+本地 | — | Go |
| [shhgit](https://github.com/eth0izzle/shhgit) | 4.0k | ✅ | — | 网+本地 | — | JavaScript |
| [SecretFinder](https://github.com/m4ll0k/SecretFinder) | 2.5k | ✅ | — | 本地 | — | Python |
| [canarytokens](https://github.com/thinkst/canarytokens) | 2.1k | ✅ | — | 网络 | — | Python |
| [agent-security](https://github.com/mintmcp/agent-security) | 71 | ✅ | — | 网+本地 | ✅ | Python |
| [atalaia](https://github.com/juanfont/atalaia) | 4 | ✅ | — | 本地 | — | Go |
| [privacy-filter](https://github.com/packyme/privacy-filter) | 251 | ✅ | — | — | ✅ | Go |

---

<a id="giants"></a>
## 🏆 巨人:工业级密钥扫描器

通用密钥/凭证扫描的事实标准,生态最成熟、规则最全。是任何密钥扫描项目的第一参考。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [trivy](https://github.com/aquasecurity/trivy) | 36.5k | Go | Comprehensive security scanner (vulns/misconfig/secrets/SBOM) for containers, K8s, filesystems, and git repos. | Apache-2.0 |
| [gitleaks](https://github.com/gitleaks/gitleaks) | 27.8k | Go | Git/file/stdin secret scanner with 222 regex+entropy rules, git-history scanning, and CI/CD pre-commit integration; declared feature-complete. | MIT |
| [trufflehog](https://github.com/trufflesecurity/trufflehog) 🤖 | 26.8k | Go | Credential leak scanner with 887 provider detectors, live verification, and post-detection permission analysis across Git, cloud storage, and SaaS sources. | AGPL-3.0 |
| [semgrep](https://github.com/semgrep/semgrep) | 15.6k | OCaml | General-purpose semantic SAST engine; secrets scanning is a paid add-on, not in the OSS CLI. | LGPL-2.1 |
| [git-secrets](https://github.com/awslabs/git-secrets) | 13.3k | Shell | Git-hook pre-commit scanner that blocks commits matching configurable regex patterns, primarily targeting AWS credentials | Apache-2.0 |
| [checkov](https://github.com/bridgecrewio/checkov) | 8.8k | Python | IaC/SCA static analyzer (Terraform/K8s/Docker) with a detect-secrets-based secrets sub-module; no LLM key support. | Apache-2.0 |
| [detect-secrets](https://github.com/Yelp/detect-secrets) · | 4.6k | Python | Enterprise secret scanner with baseline-and-diff workflow: snapshots existing secrets, then blocks only NEW secrets via pre-commit hooks. | Apache-2.0 |
| [SecretScanner](https://github.com/deepfence/SecretScanner) | 3.4k | Go | Scans container image layers and host filesystems for ~140 secret types using regex+literal signature DB with multi-axis matching. | MIT |
| [talisman](https://github.com/thoughtworks/talisman) | 2.1k | Go | Git pre-commit hook scanning changesets for secrets via filename patterns, high-entropy heuristics, base64/hex detection, and severity thresholds | MIT |
| [ggshield](https://github.com/GitGuardian/ggshield) · | 2.0k | Python | CLI scanning 500+ secret types via GitGuardian API, with real-time hooks that intercept AI coding assistant prompts to block secrets before they reach LLMs. | MIT |
| [secrets-patterns-db](https://github.com/mazen160/secrets-patterns-db) | 1.5k | Python | Curated database of 1610+ regex patterns for detecting secrets/API keys/tokens, exportable to TruffleHog/Gitleaks format. | CC-BY-SA-4.0 |
| [secretlint](https://github.com/secretlint/secretlint) · | 1.4k | TypeScript | Pluggable linting tool that detects credentials via per-provider rule packages, usable as pre-commit hook and CI gate. | MIT |
| [rusty-hog](https://github.com/newrelic/rusty-hog) | 549 | Rust | Rust-based multi-source secret scanner (Git/S3/GDocs/Confluence/JIRA/Slack/filesystem) using regex+entropy, ported from TruffleHog. | Apache-2.0 |

---

<a id="hp-scanner"></a>
## 🚀 高性能 / 新兴扫描器

Rust/Go 高性能引擎、研究型或创新检测思路的扫描器,常带来可借鉴的工程技法。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [noseyparker](https://github.com/praetorian-inc/noseyparker) 🔒归档 | 2.3k | Rust | CLI secret scanner using regex rules over files, Git history, and GitHub orgs with blob-level dedup at GB/s speed. | Apache-2.0 |
| [betterleaks](https://github.com/betterleaks/betterleaks) · | 1.3k | Go | Gitleaks successor: configurable secrets scanner with CEL-based filtering/validation, BPE token-rarity FP suppression, and multi-source support (GitHub/GitLab/HF/S3). | MIT |
| [kingfisher](https://github.com/mongodb/kingfisher) 🤖 | 1.1k | Rust | Rust secret scanner with 950+ rules, Hyperscan SIMD, live validation, direct revocation, blast-radius mapping, and broad platform integrations. | Apache-2.0 |
| [titus](https://github.com/praetorian-inc/titus) 🤖 | 598 | Go | High-perf secrets scanner: 487 rules with SIMD regex, live API validation, blast-radius scoring; CLI + Go lib + Burp + Chrome extension. | Apache-2.0 |
| [pillager](https://github.com/brittonhayes/pillager) | 310 | Go | Concurrent filesystem secret scanner wrapping Gitleaks rules with red-team exfil (S3/Sliver/webhook) and a bubbletea TUI. | MIT |
| [wraith](https://github.com/N0MoreSecr3ts/wraith) | 211 | Go | Gitrob-derived Go secret scanner for GitHub/GitLab/local git repos with external YAML signature definitions and web UI | MIT |
| [CredSweeper](https://github.com/Samsung/CredSweeper) 🤖 | 209 | Python | Samsung credential scanner combining 121 regex rules with ML-based false positive filtering across source, docs, archives, and git diffs. | MIT |
| [deepsecrets](https://github.com/avito-tech/deepsecrets) | 192 | Python | Semantic secret scanner using lexer-based code understanding + regex + hashed-secret engine across 500+ languages, no LLM key rules. | MIT |
| [trufflehog3](https://github.com/feeltheajf/trufflehog3) | 125 | Python | Enhanced Python fork of truffleHog v2: regex+entropy secret scanning across git history with HTML reports and incremental mode. | GPL-2.0 |
| [detect-secrets-server](https://github.com/Yelp/detect-secrets-server) | 107 | Python | Server-side batch scanner wrapping detect-secrets: tracks multiple repos, scans new commits periodically via cron, alerts on findings. | Apache-2.0 |
| [drogonsec](https://github.com/filipi86/drogonsec) | 106 | Go | Multi-engine Go security scanner (SAST+SCA+secrets+IaC) with 50+ secret patterns and AI-powered remediation via Ollama/cloud. | Apache-2.0 |
| [stacs](https://github.com/stacscan/stacs) 🔒归档 | 95 | Python | YARA-powered static credential scanner for binary artifacts (Docker/APK/JAR/RPM) with nested archive unpacking | BSD-3-Clause |
| [keyhog](https://github.com/santhsecurity/keyhog) · | 80 | Rust | Rust secret scanner: 901 TOML-defined detectors, SIMD/GPU backends, decode-through, live verification, SARIF output, zero-config. | MIT OR Apache-2.0 |
| [DeepPass2](https://github.com/SpecterOps/DeepPass2) | 43 | Python | Multi-layer secret scanner: NoseyParker regex → fine-tuned BERT sequence labeling → LLM verification, targeting free-form passwords in documents. | Apache-2.0 |
| [secrets-scanner](https://github.com/stefansundin/secrets-scanner) | 40 | Go | Single-file Go CLI that pipes git log output through ~8 hardcoded regex patterns and optionally tests found keys against provider APIs. | GPL-3.0 |
| [PyRepScan](https://github.com/Intsights/PyRepScan) | 40 | Python | Python library backed by Rust (git2-rs + crossbeam + regex) for high-speed regex scanning of full git history across all branches. | MIT |
| [KEYSENTINEL](https://github.com/XingTuLab/KEYSENTINEL) | 40 | Python | IEEE S&P 2025 research secret scanner: regex+entropy scan with per-language AST cross-validation, CNN password model, and multi-stage wordlist/pattern FP filters | GPL-2.0 |
| [VaultHound](https://github.com/ExploitCraft/VaultHound) | 16 | Python | Pattern-based secret scanner for local dirs, git history, and live URLs with 43 regexes and entropy filtering. | MIT |
| [Whisper](https://github.com/JamesTheGiblet/Whisper) 🤖 | 0 | Python | 本地 Ollama LLM 对 regex/熵检出的候选密钥做上下文分类,区分测试假数据与真实凭证,降低假阳性。 | MIT |

---

<a id="github-recon"></a>
## 🔎 GitHub 侦察 & 公开仓库猎取

从 GitHub/Gitee/Bitbucket 公开仓库、事件流、code search 中批量猎取泄露的 key。对应 Key Scanner 的 `recent-public` / `github-events` 模式。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [gitrob](https://github.com/michenriksen/gitrob) 🔒归档 | 6.2k | Go | Clone org repos and walk git history, flagging sensitive files by filename/extension/path patterns only — no content scanning. | MIT |
| [shhgit](https://github.com/eth0izzle/shhgit) | 4.0k | JavaScript | Scans GitHub/GitLab/BitBucket repos for 150+ secret signatures with entropy fallback (abandoned) | MIT |
| [git-all-secrets](https://github.com/anshumanbh/git-all-secrets) | 1.1k | Go | Orchestrator that clones entire GitHub orgs/users/gists at scale and runs truffleHog+repo-supervisor, producing merged deduplicated secret reports. | MIT |
| [gitleaks-action](https://github.com/gitleaks/gitleaks-action) | 602 | JavaScript | GitHub Action that runs gitleaks SAST on push/PR/schedule, posts PR comments, and uploads SARIF artifacts for code scanning alerts. | — |
| [secret-magpie](https://github.com/punk-security/secret-magpie) | 243 | HTML | Orchestrator that enumerates repos from multiple Git providers and runs TruffleHog+Gitleaks on all branches, deduplicating results. | GPL-3.0 |
| [git-alerts](https://github.com/boringtools/git-alerts) | 232 | Go | 监控 GitHub 组织成员个人账号下的公开仓库,通过 TruffleHog/Gitleaks 检测泄露的密钥和敏感文件。 | Apache-2.0 |
| [gitdorks_go](https://github.com/damit5/gitdorks_go) | 229 | Go | GitHub code-search API wrapper that runs dork keyword lists against a target org to find potentially sensitive code snippets. | — |
| [repository-scanner](https://github.com/abnamro/repository-scanner) | 166 | Python | Kubernetes-deployed Gitleaks wrapper that auto-scrapes repos from GitHub/Bitbucket/Azure DevOps and presents findings in a Vue3 dashboard. | MIT |
| [GitLeak](https://github.com/5alt/GitLeak) | 128 | JavaScript | Keyword-driven GitHub code search for passwords in sensitive files (.env etc), using filename+content combo queries. | MIT |
| [LeakIXClient](https://github.com/LeakIX/LeakIXClient) | 104 | Go | Go CLI & library for querying LeakIX's internet-leak index (exposed git configs, open DBs); not a scanner itself. | BSD-3-Clause |
| [git-secret-scanner](https://github.com/padok-team/git-secret-scanner) | 68 | Go | Wraps TruffleHog+Gitleaks to scan all repos in a GitHub org or GitLab group, merging results by fingerprint with dedup and baseline diff. | Apache-2.0 |
| [xGitGuard](https://github.com/Comcast/xGitGuard) | 64 | Python | Comcast 出品,基于 GitHub Code Search API 的关键词+扩展名组合扫描器,带可训练 ML 假阳性过滤器,面向企业/公开 GitHub 仓库 | Apache-2.0 |
| [keyscan](https://github.com/aerovato/keyscan) 🤖 | 58 | Python | Scans GitHub Gists for exposed API keys using a local LLM (qwen3:1.7b) to classify candidates, then verifies against provider endpoints. | GPL-3.0 |
| [claudleak](https://github.com/hazcod/claudleak) 🤖 | 57 | Go | Scans public GitHub repos for leaked secrets specifically in AI coding tool config files (.claude/, .cursor/, .codex/, etc.) via TruffleHog. | — |
| [secret-scanner](https://github.com/grab/secret-scanner) | 55 | Go | 基于 Gitrob 的 Go CLI 工具,签名匹配扫描 GitHub/GitLab/Bitbucket 仓库中的私钥、API secret 和 token | MIT |
| [GSSAR](https://github.com/advanced-security/GSSAR) · | 51 | TypeScript | Auto-revokes secrets found by GitHub Secret Scanning via webhook-triggered Lambda remediators (AWS Step Functions); detection-free remediation layer. | MIT |
| [KeySentry](https://github.com/AdityaBhatt3010/KeySentry) | 41 | TypeScript | Simple regex-based CLI + web scanner for ~25 API key patterns and sensitive filenames in GitHub repos/local dirs. | MIT |
| [ghmon](https://github.com/sl4x0/ghmon) | 31 | Python | Python wrapper that orchestrates TruffleHog scans across GitHub/GitLab orgs with Discord/Telegram alerting and persistent state. | — |

---

<a id="llm-key"></a>
## 🤖 LLM / AI Key 专项 ⭐

**本清单核心赛道**:专门针对 OpenAI / Anthropic / Gemini / Groq / DeepSeek / 国内 OpenAI-compatible 中转 等 AI provider key 的发现与泄露检测。这是 GitHub 上**尚无权威 awesome list 覆盖**的空白区,也是 Key Scanner 的主战场。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [llm-api-key-checker](https://github.com/ssfun/llm-api-key-checker) 🤖 | 147 | JavaScript | Batch LLM API key validator: paste keys, check liveness/balance across 9 providers via CF Workers+WebSocket. | MIT |
| [keyhunter](https://github.com/fadidevv/keyhunter) 🤖 | 36 | Rust | Fast Rust scanner that searches GitHub for leaked API keys (OpenAI/Anthropic/Claude/GPT/HF + 45 providers) and verifies which are still active. | — |
| [promptshield](https://github.com/promptshieldhq/promptshield) 🤖 | 19 | TypeScript | LLM gateway proxy that scans prompt/response traffic for secrets (Gitleaks) and PII (Presidio), enforces YAML block/mask policies, and routes multi-provider. | MIT |
| [Ultimate-openai-gemini-claude-api-key-scraper](https://github.com/shjee-afridi/Ultimate-openai-gemini-claude-api-key-scraper) · | 12 | Python | Async wrapper around GitHub/GitLab code search APIs that regex-matches OpenAI/Claude/Gemini keys; mostly a portfolio project | — |
| [api-key-leak-checker-leop](https://github.com/leo-cheung-itlger/api-key-leak-checker-leop) · | 3 | PowerShell | PowerShell pre-publish gate that scans files for common API key patterns via basic regex + optional gitleaks/trufflehog delegation. | MIT |
| [Gen-AI-API-Key-Hunt](https://github.com/Aletheia-Praxis/Gen-AI-API-Key-Hunt) 🤖 | 2 | Python | GitHub code search for leaked LLM API keys with adaptive query expansion to bypass 1000-result cap, plus async key liveness validation. | MIT |
| [VibeVault](https://github.com/DataWizardd/VibeVault) · | 1 | TypeScript | VS Code extension that detects hardcoded API keys in real-time and auto-migrates them to .env with one-click fix. | MIT |
| [-openaclaw-security-check](https://github.com/Pelican0126/-openaclaw-security-check) · | 1 | Shell | OpenClaw self-hosted security audit toolkit: skill install gate, skill inventory triage, and API key plaintext leak scan with masked reports. | — |
| [openai-key-scanner](https://github.com/NKBaa/openai-key-scanner) 🤖 | 0 | Python | Searches GitHub public code for leaked OpenAI sk-* keys and validates them via chat/completions API, with balancer sync. | — |
| [grok-api-key-scraper](https://github.com/SUNDSCRIB3/grok-api-key-scraper) 🤖 | 0 | Python | Basic async GitHub code-search scraper with 4 hardcoded LLM key regexes and SQLite dedup; marketing-heavy README overstates capabilities. | MIT |

---

<a id="key-validator"></a>
## ✅ Key 测活 / 有效性校验

判断一把泄露的 key 是否仍有效、额度/权限如何——直接对应 Key Scanner 的「测活」能力。最具借鉴价值。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [keyhacks](https://github.com/streaak/keyhacks) | 6.3k | — | Curated cheatsheet of curl commands to validate whether leaked API keys from ~80 SaaS providers are still alive. | — |
| [driftwood](https://github.com/trufflesecurity/driftwood) 🔒归档 | 435 | Go | Checks if a cryptographic private key (RSA/EC/DSA PEM) is actively used as a GitHub SSH key or TLS certificate. | Apache-2.0 |
| [keyscope](https://github.com/SpectralOps/keyscope) | 411 | Rust | Rust CLI that validates whether given API keys are active/inactive against 44+ SaaS providers; no scanning or detection capability. | Apache-2.0 |
| [how-to-rotate](https://github.com/trufflesecurity/how-to-rotate) | 84 | JavaScript | Hugo-based documentation site with step-by-step API key rotation tutorials for 50+ services including AWS, GitHub, and Stripe. | AGPL-3.0 |
| [Gemini-API-Key-Exposure-Scanner](https://github.com/MuhammadKhizerJaved/Gemini-API-Key-Exposure-Scanner) 🤖 | 50 | Python | Validates a known Gemini/Google API key by probing capabilities (text/image/video/TTS) and generates a bug-bounty impact report. | — |
| [cpa-codex-auth-sweep](https://github.com/paradoxie/cpa-codex-auth-sweep) 🤖 | 35 | Python | Async Codex OAuth credential hygiene scanner: probes local auth files, classifies 401/quota/unlimited, purges dead tokens. | MIT |
| [GapiChecker](https://github.com/z3n70/GapiChecker) | 30 | Ruby | Interactive Ruby CLI that tests a user-supplied Google Maps API key against 13+ Google API endpoints to check if it's unrestricted (pentesting). | — |
| [openai_key_checker](https://github.com/aikemist/openai_key_checker) 🤖 | 26 | JavaScript | Web UI that probes an OpenAI API key to report whether it has access to GPT-4 models | — |
| [api-key-checker](https://github.com/purainity/api-key-checker) 🤖 | 15 | Python | 批量检测已有 AI API Key 的余额与可用性(OpenRouter/SiliconFlow/DeepSeek/Gemini),非扫描发现工具 | — |
| [openai_api_key_checker](https://github.com/winklemad/openai_api_key_checker) 🤖 | 7 | Python | 多线程验证 OpenAI API key 有效性并查询可用余额,支持 Ctrl+C 安全中断 | — |
| [Keyleaksecret](https://github.com/0xSojalSec/Keyleaksecret) | 7 | — | README-only cheat-sheet of curl one-liners to verify leaked API keys across 70+ services; no actual code or scanner. | — |
| [GeminiApiKeyValidator](https://github.com/chagelstein/GeminiApiKeyValidator) 🤖 | 7 | HTML | Replit-hosted Flask app that takes a user-supplied Gemini API key and tests connectivity by listing models and calling generate_content. | — |
| [KeyHunter](https://github.com/bigzooooz/KeyHunter) | 6 | Python | Subdomain enum → wayback/katana URL collection → async regex scan for API key leaks on live endpoints | MIT |
| [ApiKeyScan](https://github.com/Mouseww/ApiKeyScan) 🤖 | 6 | Go | Go CLI that searches GitHub for LLM API keys and validates them via actual API calls | — |
| [API-QuickCheck](https://github.com/som1ng/API-QuickCheck) 🤖 | 3 | TypeScript | Frontend-only browser UI where users paste an LLM API key to test liveness; not a scanner or leak detector. | — |
| [openai-key-checker](https://github.com/screedcode/openai-key-checker) 🤖 | 3 | Go | Reads a file of OpenAI keys line-by-line and prints ones that pass /v1/engines (deprecated) or /v1/models auth check. | MIT |
| [llm-api-key-checker-next](https://github.com/Selenium39/llm-api-key-checker-next) 🤖 | 2 | TypeScript | Next.js web app that batch-validates user-pasted LLM API keys by sending real chat/completions calls; no scanning or leak detection. | MIT |
| [keyprobe](https://github.com/datumbrain/keyprobe) 🤖 | 2 | Go | CLI that validates LLM API keys by auto-detecting provider from prefix and probing which models and features the key can access. | MIT |
| [gemini-api-key-validation-analysis](https://github.com/32BYTX/gemini-api-key-validation-analysis) 🤖 | 2 | Python | PoC showing Gemini API gateway returns differentiated errors that classify key state (valid/disabled/suspended/rate-limited) without model execution. | MIT |
| [KeyNest](https://github.com/Tan35/KeyNest) 🤖 | 1 | JavaScript | Bulk-validates LLM API keys (24 providers) via Cloudflare Workers + WebSocket, with persistent IndexedDB vault and regional egress proxy. | MIT |
| [api-key-checker](https://github.com/sourav-bwn/api-key-checker) · | 0 | CSS | Browser-based API key validity checker for 20+ providers; client-side only, not a leak scanner. | — |

---

<a id="pattern-db"></a>
## 🧬 正则 / 规则库

可吸收进自家 detector 的正则模式与规则数据库。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [gf-secrets](https://github.com/dwisiswant0/gf-secrets) | 245 | Shell | Static collection of 23 grep regex JSON patterns (AWS/GCP/Slack/Stripe/etc.) for the gf CLI wrapper; no scanner engine, no verification, no LLM key coverage. | MIT |
| [truffleHogRegexes](https://github.com/dxa4481/truffleHogRegexes) | 227 | Python | Flat JSON file of ~35 regex patterns for common service tokens (AWS, Slack, Stripe, Google); no scanner logic, no README, unmaintained since 2022. | GPL-3.0 |
| [scan4secrets](https://github.com/m14r41/scan4secrets) | 113 | Python | SAST/DAST scanner that regex-matches ~400 secret variable names (api_key, password, etc.) against local files and crawled URLs. | MIT |

---

<a id="js-web"></a>
## 🕸️ JS / Web / 浏览器密钥提取

从 JavaScript bundle、网页、HAR、浏览器/Burp 流量中抽取泄露的 key/token。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [SecretFinder](https://github.com/m4ll0k/SecretFinder) | 2.5k | Python | Scans JavaScript files for hardcoded secrets (API keys, tokens, JWT) using regex patterns, supports URL/file/folder input. | GPL-3.0 |
| [mantra](https://github.com/brosck/mantra) | 911 | Go | Go CLI that regex-scans JS files and HTML pages (fed via stdin URLs) for hardcoded API keys from 100+ third-party services. | GPL-3.0 |
| [Trufflehog-Chrome-Extension](https://github.com/trufflesecurity/Trufflehog-Chrome-Extension) | 423 | JavaScript | Chrome extension that passively scans visited web pages, scripts, and auto-probed .env/.git/config for leaked API keys via regex. | GPL-2.0 |
| [keyleak-detector](https://github.com/Amal-David/keyleak-detector) · | 261 | Python | 运行时 Web 密钥泄露检测器:Playwright 扫描 JS bundle 提取 key,主动验证 Supabase/Firebase RLS 是否生效,配 Chrome 扩展实时捕获 | MIT |
| [js-snitch](https://github.com/vavkamil/js-snitch) | 145 | Python | Downloads all JS files from a target website, beautifies them, runs TruffleHog + Semgrep, and aggregates verified/unverified secret findings. | Unlicense |
| [webtrufflehog](https://github.com/c3l3si4n/webtrufflehog) | 127 | Python | Chrome extension that intercepts live web traffic via webRequest API and pipes URLs to TruffleHog for real-time secret detection. | — |
| [trufflehog-burp-suite-extension](https://github.com/trufflesecurity/trufflehog-burp-suite-extension) · | 99 | Python | Burp Suite extension that intercepts HTTP traffic and runs TruffleHog every 10s to detect 800+ secret types in live requests/responses. | — |
| [keyhunter](https://github.com/DonIsaac/keyhunter) · | 40 | Rust | Rust CLI that crawls websites, parses their JS with oxc AST, and detects leaked API keys using gitleaks rules + entropy + variable-name heuristics. | GPL-3.0 |
| [google-api-key-scanner](https://github.com/its-l0bo/google-api-key-scanner) · | 1 | JavaScript | Chrome extension that detects Google API keys (AIza...) in web pages and validates them against Gemini/Maps/YouTube endpoints for bug bounty recon. | MIT |
| [api-key-exposure-auditor](https://github.com/hasif5/api-key-exposure-auditor) · | 1 | JavaScript | Chrome MV3 extension that passively finds API keys across 15+ web surfaces and live-validates them against 11 providers with risk scoring. | MIT |
| [google-api-key-checker](https://github.com/kukuxumushi/google-api-key-checker) 🤖 | 1 | JavaScript | Chrome extension that passively scans visited web pages for Google API keys and checks them against Gemini API endpoints. | MIT |
| [Gemini-API-Key-Scanner](https://github.com/Mustafa-Almohsen/Gemini-API-Key-Scanner) 🤖 | 0 | Python | Crawls JS files from target URLs, extracts Google AIza keys, validates via Gemini API, and proves write access by uploading corpora. | — |

---

<a id="container-runtime"></a>
## 🐳 容器 / 运行时 / 内存 / 网关脱敏

扫描容器镜像、进程内存,或在网关/日志层实时脱敏——运行时防护侧。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [privacy-filter](https://github.com/packyme/privacy-filter) · | 251 | Go | Go library/HTTP/gRPC gateway that redacts PII and secrets from text before it reaches an LLM, using gitleaks rules + entropy + context heuristics. | MIT |
| [pii-shield](https://github.com/pii-shield/pii-shield) | 146 | Go | K8s sidecar that sanitizes PII/secrets from application logs via entropy analysis + context keywords before logs leave the pod. | Apache-2.0 |
| [truffleproc](https://github.com/controlplaneio/truffleproc) | 125 | Shell | Dumps a running process's memory via gdb coredump, extracts strings, then runs TruffleHog to find secrets resident only in RAM. | Apache-2.0 |
| [agentveil](https://github.com/vurakit/agentveil) · | 83 | Go | Reverse proxy that anonymizes PII/secrets in LLM API requests, stores tokens in AES-256 Redis vault, rehydrates on response | MIT |
| [layerleak](https://github.com/Brumbelow/layerleak) | 40 | Go | Scans OCI container image layers, configs, and history for secrets without requiring Docker daemon | MIT |

---

<a id="honeypot"></a>
## 🍯 蜜罐 / Canary Token

部署假密钥/诱饵,追踪泄露与被利用轨迹(防御侧,可与检测互补)。含 AI/LLM 蜜罐。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [canarytokens](https://github.com/thinkst/canarytokens) | 2.1k | Python | Honeypot platform that generates decoy tokens (AWS keys, kubeconfigs, docs, URLs) and alerts when they are accessed or used. | GPL-3.0 |
| [canarytokens-docker](https://github.com/thinkst/canarytokens-docker) | 657 | Dockerfile | 一键 Docker 部署 Canarytokens 蜜罐服务器,投放 DNS/HTTP/PDF/AWS 等诱饵 token 并捕获触发告警。 | BSD-3-Clause |
| [honeyLambda](https://github.com/0x4D31/honeyLambda) | 526 | Python | Serverless URL honeytoken deployer: plants fake HTTP endpoints on AWS Lambda and alerts when attackers hit them — does NOT scan for leaked keys. | GPL-3.0 |
| [dcept](https://github.com/secureworks/dcept) | 504 | Python | Active Directory honeytoken tripwire: deploys fake creds in endpoint memory, detects their use against domain controllers. | GPL-3.0 |
| [honeybits](https://github.com/0x4D31/honeybits) 🔒归档 | 277 | Go | Archived PoC that plants fake credentials, bash_history entries, and honeyfiles on prod hosts to lure attackers toward honeypots. | GPL-3.0 |
| [Awesome-Deception](https://github.com/tolgadevsec/Awesome-Deception) | 182 | — | Curated list of deception-security resources (honeypots, honeytokens, canaries) — not a scanner or detection tool. | — |
| [CanaryTokenScanner](https://github.com/0xNslabs/CanaryTokenScanner) | 146 | Python | Detects tracking/honeypot URLs (CanaryTokens) embedded in Office docs and PDFs via static inspection, no network requests. | — |
| [thumper](https://github.com/jestasecurity/thumper) | 117 | Python | Self-hosted honeytoken tripwire platform: plants fake credentials to detect the Shai-Hulud npm worm scanning your env. | Apache-2.0 |
| [cloud-active-defense](https://github.com/SAP/cloud-active-defense) | 106 | JavaScript | Envoy WASM reverse-proxy plugin that injects decoy endpoints/cookies/headers into web apps to detect and divert intruders via deception. | Apache-2.0 |
| [IMDSpoof](https://github.com/grahamhelton/IMDSpoof) | 106 | Go | Spoofs AWS IMDS endpoint to serve honeytoken AWS credentials to attackers, triggering alerts on use. | — |
| [koney](https://github.com/dynatrace-oss/koney) | 92 | Go | K8s operator that plants honeytoken files in pods and monitors access via eBPF to detect attackers, not a secret-leak scanner. | AGPL-3.0 |
| [Trapdoor](https://github.com/3CORESec/Trapdoor) | 81 | C# | Deploys serverless HTTP honeypot endpoints on AWS Lambda that alert via Slack/webhook when visited by adversaries. | AGPL-3.0 |
| [VelLMes-AI-Deception-Framework](https://github.com/stratosphereips/VelLMes-AI-Deception-Framework) | 77 | Python | LLM-powered honeypot framework simulating SSH/MySQL/POP3/HTTP to trap attackers, not a key/secret scanner | GPL-2.0 |
| [llm-honeypot](https://github.com/PalisadeResearch/llm-honeypot) | 60 | HTML | Modified Cowrie SSH honeypot that uses hidden ANSI escape codes to detect and trap autonomous LLM-driven hacking agents. | — |
| [honey-ai](https://github.com/martidu4/honey-ai) | 13 | JavaScript | AI-driven multi-protocol honeypot with canary tokens and threat intel reporting — not a key scanner. | AGPL-3.0 |
| [llm-honeypot](https://github.com/romiisromie/llm-honeypot) | 7 | Python | FastAPI honeypot with DistilBERT classifier that detects and traps prompt injection and jailbreak attacks against LLMs. | — |
| [AI-Honeypot](https://github.com/BrightGir/AI-Honeypot) | 5 | Go | AI honeypot proxy that intercepts prompt injections/jailbreaks and feeds attackers decoy personas with fabricated data | MIT |
| [llm_based_predictive_deception](https://github.com/Festus55/llm_based_predictive_deception) | 3 | Python | LLM-powered SSH honeypot that predicts attacker actions and pre-deploys Canarytokens as traps | — |

---

<a id="ai-agent-hook"></a>
## 🪝 AI Agent 密钥拦截钩子

给 Claude Code / Cursor / Codex 等 AI 编码 agent 加的密钥扫描钩子、技能与 MCP 工具(新兴趋势)。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [ship-safe](https://github.com/asamassekou10/ship-safe) · | 733 | JavaScript | CLI with 23 parallel agents scanning for secrets, LLM/CI/CD/supply-chain vulns; includes auto-fix REPL and SARIF CI output. | MIT |
| [Claudoscope](https://github.com/cordwainersmith/Claudoscope) · | 197 | Swift | macOS menu-bar dashboard for Claude Code sessions with built-in secret scanning of local JSONL session files and 1-click security hardening. | MIT |
| [SecOpsAgentKit](https://github.com/AgentSecOps/SecOpsAgentKit) | 163 | Python | Claude Code skill pack wrapping 25+ existing sec tools (gitleaks, semgrep, trivy, nuclei etc.) — no custom secret detection logic. | — |
| [cyber-neo](https://github.com/Hainrixz/cyber-neo) | 153 | Python | Claude Code skill that orchestrates LLM subagents to run broad 11-domain security audits on local projects; secret detection is 1 of 11 domains. | MIT |
| [MaskerLogger](https://github.com/oxsecurity/MaskerLogger) | 108 | Python | Python logging formatter that masks secrets in log output using gitleaks rules, not a scanner — complementary (prevention) not overlapping (detection). | MIT |
| [securelog](https://github.com/treadiehq/securelog) | 101 | TypeScript | Runtime console.log guard that compares log args against process.env values and blocks/masks accidental secret output. | — |
| [agent-security](https://github.com/mintmcp/agent-security) · | 71 | Python | Claude Code/Cursor hook plugin that blocks or warns on secrets found in files read/written by coding agents during sessions. | Apache-2.0 |
| [skill-audit](https://github.com/pors/skill-audit) · | 59 | Python | CLI orchestrator auditing AI agent skills: wraps trufflehog/gitleaks for secrets, shellcheck/semgrep for code, plus its own prompt-injection regex scanner. | MIT |
| [nixis](https://github.com/mayankjain0141/nixis) · | 41 | Go | AI-agent firewall intercepting tool calls (file/shell/network) with CEL policies, IFC lattice, and gitleaks-based secret scanning layer. | MIT |
| [shield-claude-skill](https://github.com/alissonlinneker/shield-claude-skill) | 11 | Shell | Claude Code plugin that orchestrates gitleaks, semgrep, dep audits & pentesting into a unified security report with scoring — thin gitleaks wrapper, not a scanner. | MIT |
| [claude-security-skills](https://github.com/NovaCode37/claude-security-skills) · | 8 | Python | Suite of 6 zero-dep Claude Code security skills; secret scanner is ~25 vendor regex + Shannon entropy gating — clean but shallow vs keyscanner. | MIT |
| [claude-code-helper](https://github.com/light-merlin-dark/claude-code-helper) | 5 | TypeScript | Claude Code config cleanup/permission manager with basic regex secret detection in ~/.claude/ session data | MIT |
| [atalaia](https://github.com/juanfont/atalaia) | 4 | Go | HTTP service that runs gitleaks+trufflehog on a git diff, then uses a local LLM to classify each finding as confirmed or dismissed. | BSD-3-Clause |
| [apikeywall](https://github.com/RichardSufliarsky/apikeywall) · | 3 | Python | mitmproxy addon that swaps placeholder API keys for real keys at the HTTP layer; key gateway, not a scanner | MIT |

---

<a id="saas"></a>
## 🏢 SaaS / 多平台监控

监控 Slack / Jira / Confluence / Gitee 等协作平台暴露的密钥。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [badsecrets](https://github.com/blacklanternsecurity/badsecrets) | 804 | Python | Detects known/default cryptographic keys in web framework artifacts (cookies, JWTs, viewstates) via offline verification and active probing. | AGPL-3.0 |
| [slack-watchman](https://github.com/PaperMtn/slack-watchman) | 402 | Python | Scans Slack workspace messages/files via Slack API for leaked API keys, tokens, PII, and sensitive files using YAML signatures. | GPL-3.0 |
| [n0s1](https://github.com/spark1security/n0s1) | 77 | Python | Regex+entropy secret scanner targeting SaaS collab platforms (Slack, Jira, Confluence, Asana, Zendesk, Linear, Wrike) plus GitHub/GitLab repos and local files. | GPL-3.0 |
| [secret-scanning-tools](https://github.com/advanced-security/secret-scanning-tools) | 0 | Python | CI test suite for validating GitHub's built-in custom secret scanning patterns, not a standalone key/secret detector. | MIT |

---

<a id="reference"></a>
## 📚 参考资源 & 字典

key 校验方法学、泄露案例、payload 字典、现有 awesome list——不是工具但极具借鉴价值。

| 工具 | ⭐ | 语言 | 说明 | 许可 |
|------|----|----|------|------|
| [SecLists](https://github.com/danielmiessler/SecLists) | 71.7k | PHP | Curated collection of wordlists, payloads, and patterns for penetration testing and security assessments. | MIT |
| [nuclei](https://github.com/projectdiscovery/nuclei) | 29.3k | Go | General-purpose DAST vulnerability scanner using YAML templates; not a secret/key detection tool. | MIT |
| [APISecurityBestPractices](https://github.com/GitGuardian/APISecurityBestPractices) | 2.0k | — | GitGuardian's reference documentation with leak remediation checklists and secret management best practices—not a scanning tool, pure markdown guidance from 2019. | — |
| [changeme](https://github.com/ztgrace/changeme) | 1.5k | Python | Network default-credential scanner that probes live services (HTTP/SSH/DB) for known default passwords via YAML-defined fingerprint database. | GPL-3.0 |
| [leaky-repo](https://github.com/Plazmaz/leaky-repo) | 247 | Python | Benchmark corpus of fake secrets (configs, keys, high-entropy) for evaluating scanner tools' recall and precision. | MIT |
| [secret-scanning-custom-patterns](https://github.com/advanced-security/secret-scanning-custom-patterns) | 176 | HTML | Curated regex pattern library for GitHub Advanced Security's custom secret scanning, covering 80+ secret types across vendors, databases, PII, and generic credentials. | MIT |

---

<a id="experimental"></a>
## 🧪 实验性 / 小工具

星数低或实验性质,但代表某个细分方向或含可借鉴的小技巧。

| 工具 | ⭐ | 说明 |
|------|----|------|
| [llm-wiki_obsidian_hermes_r0b0tlabbra1n](https://github.com/r0b0tlab/llm-wiki_obsidian_hermes_r0b0tlabbra1n) | 21 | Agent memory system (Obsidian vault + SQLite FTS5) with a basic regex secret scanner as write-guard, not a dedicated key finder. |
| [ApiKeyValidator](https://github.com/Syed-Ali-Dev/ApiKeyValidator) | 0 | Web UI 粘贴 OpenAI/Anthropic key 验活(billing/rate-limit/模型列表),纯验证工具,不做扫描或泄露检测 |

---

<a id="absorb"></a>
## 🧩 技术借鉴速查(吸收点子)

> 本清单的**核心增值**:把各工具的独特技法汇总成「可吸收点子」表,直接映射到 Key Scanner 的改进方向。这是「站在巨人肩膀上」的实操清单。

| 技法 | 代表工具 | 可吸收进 Key Scanner 的点 |
|------|---------|--------------------------|
| **关键词预过滤闸门 (keyword pre-filter gate)** | truffleHog / gitleaks / kingfisher | 每个 detector 声明锚点串(如 OpenAI 的 base64 `T3BlbkFJ`),先做极速字符串匹配再跑正则,跳过无关内容——扫描吞吐可提升数倍 |
| **验证后分析 (verify-then-analyze)** | truffleHog | 测活不只返回 valid/invalid,再用 YAML 定义的 per-provider 权限模型枚举该 key 的确切 scope/额度/可见资源 |
| **blast radius 影响面映射** | mongodb/kingfisher | 泄露的 key → 云身份 → 实际暴露的资源(43 provider),把「有泄露」升级为「泄露了什么」,直接驱动处置优先级 |
| **无 API 调用的校验和判定** | mongodb/kingfisher | 对 GitHub/Confluent 等 token 用内置校验和算法判定有效性,不发起网络请求(零额度消耗、零审计留痕) |
| **基线快照 + 增量 diff** | Yelp/detect-secrets | 先把存量密钥拍成 baseline JSON,CI 里只对「新增」告警——历史误报一次清零 |
| **ML 胡言乱语分类器** | Yelp/detect-secrets | 用训练好的分类器(rfc.model)过滤高熵字符串误报,比纯熵阈值更准 |
| **正则→LLM 两阶段裁决** | juanfont/atalaia | detector 保召回,再用一次 schema 约束的 LLM 调用做精度裁决;已验证/已知测试 key 短路跳过 LLM 省 token |
| **双阈值熵 + 上下文邻近门** | packyme/privacy-filter | 有 `密码/api_key` 等上下文关键词时用低熵阈值(4.0),否则用高熵阈值(4.8)——上下文启发式的量化版 |
| **FP 拒绝流水线** | packyme/privacy-filter | 模板变量/UUID/十六进制哈希/路径URL边界/占位词/JSON逗号噪音——逐条规则剔除高熵误报 |
| **6 态 key 状态分类** | ssfun/llm-api-key-checker | 超越 valid/invalid,细分 low-balance / zero / quota-exhausted / rate-limited / 正常——测活结果更可运营 |
| **per-key 能力矩阵** | datumbrain/keyprobe | 不只测活,还报告该 key 能用哪些模型、是否支持 streaming/batch/files——直接对应 keyscanner 的 provider 映射 |
| **BaaS 可利用性主动探测** | Amal-David/keyleak-detector | 检测到 Supabase/Firebase anon key 后,主动探测 RLS 是否生效,把「发现 key」升级为「证明可利用」攻击链 |
| **AIza key 分类(Maps vs Gemini)** | Amal-David/keyleak-detector | 同是 AIza 前缀,区分预期暴露的 Maps key 和真正泄露的 Gemini key——降误报 |
| **AI 编码助手 hook 协议** | GitGuardian/ggshield / mintmcp/agent-security | 拦截 stdin JSON 事件(pretooluse/userpromptsubmit),返回 block/allow;fail-open 设计:崩溃/鉴权失败时放行+告警,绝不卡死用户 |
| **canary token as LLM key** | thinkst/canarytokens | 在测试配置/仓库里埋假 LLM API key 作为蜜签,被查询即告警——主动检测泄露链路 |
| **rotation 教程直链** | trufflesecurity/how-to-rotate | 扫描结果旁直接链到该 provider 的 key 轮换步骤,让用户拿到 finding 就能处置 |
| **声明的 per-provider 校验 spec** | SpectralOps/keyscope | 用 YAML 声明每个 provider 的校验方式(含 flip-mode:断言 key 已失效,用于轮换审计),加 provider 只改配置 |
| **mask-result 原地脱敏输出** | secretlint | 直接在源码文件里把命中值脱敏(mask),配合 SARIF 上传 GitHub Code Scanning |
| **组织级 fan-out + 文件名签名库** | michenriksen/gitrob | 枚举 org 全员后并行扫各自仓库;~90 条文件名/扩展名签名(.pem/.kdbx/.sqlite…)用于高价值文件定位 |
| **深度抽取 (zip/office/sqlite/pyc)** | mongodb/kingfisher | 从压缩包、Office 文档、SQLite、Python .pyc 里抽取密钥——覆盖 GitHub API 直扫够不到的制品 |
| **Git-blob SHA-1 去重** | praetorian-inc/noseyparker | 对相同内容做 blob 级 SHA-1 去重,把跨输入/跨仓库的相同密钥折叠成单条 finding(可压缩 10-1000x),大幅降低大规模 org 扫描的 triage 噪音 |
| **本地 LLM 区分测试假 key vs 真凭据** | JamesTheGiblet/Whisper | 用本地 Ollama 对正则/熵检出的候选做上下文分类,识别测试占位 key 与真实凭据——离线、零额度、降误报 |
| **JS AST 定位变量名→赋值** | DonIsaac/keyhunter | 用 oxc 把 JS 解析成 AST,按变量名(如 OPENAI_API_KEY)定位再取赋值,区分变量名上下文与裸值;附 CDN/库自动跳过——网页 JS 扫描降误报 |
| **ML 后过滤 + 公开基准 (CredData)** | Samsung/CredSweeper | TF→ONNX 轻量分类器对正则命中做后过滤;配套 CredData 公开基准数据集可复现评估 recall/precision |

---

<a id="contributing"></a>
## 🙋 贡献

欢迎补充!提 PR 时请给出:工具名(带跳转链接)、星数、主语言、一句话说明、许可证,并标注与「API key / LLM key 泄露检测」的相关度。若有独特技法,补到[技术借鉴速查](#absorb)。

<a id="license"></a>
## 📜 许可

清单内容采用 [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/) 公共领域贡献。各工具本身保留各自许可证。
