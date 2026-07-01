# 🔑 Awesome API Key Leak Detection
**언어:** [English](README.md) • [简体中文](README.zh-CN.md) • [繁體中文](README.zh-TW.md) • [Español](README.es.md) • [Français](README.fr.md) • [Deutsch](README.de.md) • [日本語](README.ja.md) • **한국어** • [Português (BR)](README.pt-BR.md) • [Русский](README.ru.md) • [العربية](README.ar.md) • [Italiano](README.it.md)

> **API 키 탐색 / 대형 언어 모델(LLM) API 키 노출 탐지** 도구와 자료를 엄선한 목록입니다.
> 자체 개발한 [Key Scanner](https://github.com/irmacardozo993-lgtm/key-scanner)를 기반으로, 기존 관련 프로젝트 전체를 체계적으로 정리했습니다 — **거인의 어깨 위에 서서 바퀴를 재발명하지 않습니다.**
>
> 각 도구에는 그 도구만의 고유한 기법과 "흡수 가능한 아이디어"를 주석으로 달아, 자신의 스캐너에 무엇을 차용할 가치가 있는지 판단할 수 있게 했습니다.

<a id="acknowledgments"></a>
## 🙏 감사의 말

- **[Telegram OpenClaw 中文社区](https://t.me/OpenClaw_Group)** — Telegram의 OpenClaw 중국어 커뮤니티 — 지지와 토론에 감사드립니다.
- **[Linux.do](https://linux.do)** — 중국어 개발자·기술 커뮤니티(Discourse) — 피드백과 전파에 감사드립니다.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg) ![Tools](https://img.shields.io/badge/tools-130+-blue) ![Focus: LLM Keys](https://img.shields.io/badge/focus-LLM%20keys-purple) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)

---

## 목차

- [1. 🏆 거인들: 산업급 시크릿 스캐너](#giants)
- [2. 🚀 고성능 / 신흥 스캐너](#hp-scanner)
- [3. 🔎 GitHub 정찰 및 공개 저장소 사냥](#github-recon)
- [4. 🤖 LLM / AI 키 전문 ⭐](#llm-key)
- [5. ✅ 키 활성/유효성 검사](#key-validator)
- [6. 🧬 정규식 / 규칙 데이터베이스](#pattern-db)
- [7. 🕸️ JS / 웹 / 브라우저 키 추출](#js-web)
- [8. 🐳 컨테이너 / 런타임 / 메모리 / 게이트웨이 마스킹](#container-runtime)
- [9. 🍯 허니팟 / 카나리 토큰](#honeypot)
- [10. 🪝 AI 에이전트 시크릿 가로채기 훅](#ai-agent-hook)
- [11. 🏢 SaaS / 다중 플랫폼 모니터링](#saas)
- [12. 📚 참고 자료 및 워드리스트](#reference)
- [13. 🧪 실험적 / 소규모 도구](#experimental)
- [14. 🧩 기술 차용 치트시트 (흡수 가능한 아이디어)](#absorb)
- [🙋 기여하기](#contributing) · [🙏 감사의 말](#acknowledgments) · [📜 라이선스](#license)

---

## 범례

| 표시 | 의미 |
|------|------|
| ⭐ | GitHub 스타 수 (조사 시점 기준, 대략적) |
| `Language` | 주 언어 |
| `License` | 오픈소스 라이선스 |
| 🤖 | LLM/AI 키 노출 탐지와 직접 관련 (이 목록의 초점) |
| · | 부분적으로 관련 (AI 키를 포함한 여러 카테고리를 다룸) |
| 🔒Archived | 저장소가 보관 처리됨 |

> 🤖 표시가 붙은 항목은 "LLM API 키 노출 탐지" 트랙에 속합니다 — GitHub에서 **어떤 권위 있는 awesome 목록도 현재 다루지 않는** 공백 영역입니다.

---

<a id="matrix"></a>
## 🗺️ 개요: 핵심 도구 역량 매트릭스

> 핵심 도구들을 역량 차원에서 비교해 "무엇이 빠져 있는지" / "무엇을 차용할지"를 빠르게 파악합니다.

| 도구 | ⭐ | 탐지 | 활성 | 다중 소스 (웹/로컬) | LLM 키 | 언어 |
|------|----|------|------|----------------|---------|------|
| [gitleaks](https://github.com/gitleaks/gitleaks) | 27.8k | ✅ | — | web+local | — | Go |
| [trufflehog](https://github.com/trufflesecurity/trufflehog) | 26.8k | ✅ | ✅ | local | ✅ | Go |
| [detect-secrets](https://github.com/Yelp/detect-secrets) | 4.6k | ✅ | — | — | ✅ | Python |
| [ggshield](https://github.com/GitGuardian/ggshield) | 2.0k | ✅ | — | — | ✅ | Python |
| [talisman](https://github.com/thoughtworks/talisman) | 2.1k | ✅ | — | local | — | Go |
| [secretlint](https://github.com/secretlint/secretlint) | 1.4k | ✅ | — | web+local | ✅ | TypeScript |
| [kingfisher](https://github.com/mongodb/kingfisher) | 1.1k | ✅ | ✅ | — | ✅ | Rust |
| [titus](https://github.com/praetorian-inc/titus) | 598 | ✅ | ✅ | — | ✅ | Go |
| [noseyparker](https://github.com/praetorian-inc/noseyparker) | 2.3k | ✅ | — | web+local | — | Rust |
| [CredSweeper](https://github.com/Samsung/CredSweeper) | 209 | ✅ | — | local | ✅ | Python |
| [keyhacks](https://github.com/streaak/keyhacks) | 6.3k | ✅ | ✅ | — | — | — |
| [keyscope](https://github.com/SpectralOps/keyscope) | 411 | ✅ | ✅ | — | — | Rust |
| [driftwood](https://github.com/trufflesecurity/driftwood) | 435 | ✅ | ✅ | web+local | — | Go |
| [llm-api-key-checker](https://github.com/ssfun/llm-api-key-checker) | 147 | ✅ | ✅ | — | ✅ | JavaScript |
| [keyprobe](https://github.com/datumbrain/keyprobe) | 2 | ✅ | ✅ | local | ✅ | Go |
| [keyhunter](https://github.com/fadidevv/keyhunter) | 36 | ✅ | ✅ | web | ✅ | Rust |
| [keyleak-detector](https://github.com/Amal-David/keyleak-detector) | 261 | ✅ | — | — | ✅ | Python |
| [gitrob](https://github.com/michenriksen/gitrob) | 6.2k | ✅ | — | web+local | — | Go |
| [shhgit](https://github.com/eth0izzle/shhgit) | 4.0k | ✅ | — | web+local | — | JavaScript |
| [SecretFinder](https://github.com/m4ll0k/SecretFinder) | 2.5k | ✅ | — | local | — | Python |
| [canarytokens](https://github.com/thinkst/canarytokens) | 2.1k | ✅ | — | web | — | Python |
| [agent-security](https://github.com/mintmcp/agent-security) | 71 | ✅ | — | web+local | ✅ | Python |
| [atalaia](https://github.com/juanfont/atalaia) | 4 | ✅ | — | local | — | Go |
| [privacy-filter](https://github.com/packyme/privacy-filter) | 251 | ✅ | — | — | ✅ | Go |

---

<a id="giants"></a>
## 🏆 거인들: 산업급 시크릿 스캐너

범용 시크릿/자격증명 스캐닝의 사실상 표준으로, 가장 성숙한 생태계와 가장 완전한 규칙을 갖추고 있습니다. 모든 시크릿 스캐닝 프로젝트의 첫 번째 참고 자료입니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
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
## 🚀 고성능 / 신흥 스캐너

Rust/Go 고성능 엔진, 연구 지향적이거나 혁신적 탐지 기법을 가진 스캐너 — 차용 가능한 엔지니어링 기법을 자주 제공합니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [noseyparker](https://github.com/praetorian-inc/noseyparker) 🔒Archived | 2.3k | Rust | CLI secret scanner using regex rules over files, Git history, and GitHub orgs with blob-level dedup at GB/s speed. | Apache-2.0 |
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
| [stacs](https://github.com/stacscan/stacs) 🔒Archived | 95 | Python | YARA-powered static credential scanner for binary artifacts (Docker/APK/JAR/RPM) with nested archive unpacking | BSD-3-Clause |
| [keyhog](https://github.com/santhsecurity/keyhog) · | 80 | Rust | Rust secret scanner: 901 TOML-defined detectors, SIMD/GPU backends, decode-through, live verification, SARIF output, zero-config. | MIT OR Apache-2.0 |
| [DeepPass2](https://github.com/SpecterOps/DeepPass2) | 43 | Python | Multi-layer secret scanner: NoseyParker regex → fine-tuned BERT sequence labeling → LLM verification, targeting free-form passwords in documents. | Apache-2.0 |
| [secrets-scanner](https://github.com/stefansundin/secrets-scanner) | 40 | Go | Single-file Go CLI that pipes git log output through ~8 hardcoded regex patterns and optionally tests found keys against provider APIs. | GPL-3.0 |
| [PyRepScan](https://github.com/Intsights/PyRepScan) | 40 | Python | Python library backed by Rust (git2-rs + crossbeam + regex) for high-speed regex scanning of full git history across all branches. | MIT |
| [KEYSENTINEL](https://github.com/XingTuLab/KEYSENTINEL) | 40 | Python | IEEE S&P 2025 research secret scanner: regex+entropy scan with per-language AST cross-validation, CNN password model, and multi-stage wordlist/pattern FP filters | GPL-2.0 |
| [VaultHound](https://github.com/ExploitCraft/VaultHound) | 16 | Python | Pattern-based secret scanner for local dirs, git history, and live URLs with 43 regexes and entropy filtering. | MIT |
| [Whisper](https://github.com/JamesTheGiblet/Whisper) 🤖 | 0 | Python | Uses a local Ollama LLM to contextually classify regex/entropy-detected key candidates, distinguishing test fake data from real credentials and reducing false positives. | MIT |

---

<a id="github-recon"></a>
## 🔎 GitHub 정찰 및 공개 저장소 사냥

GitHub/Gitee/Bitbucket 공개 저장소, 이벤트 스트림, 코드 검색에서 노출된 키를 대량으로 사냥합니다. Key Scanner의 `recent-public` / `github-events` 모드에 대응합니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [gitrob](https://github.com/michenriksen/gitrob) 🔒Archived | 6.2k | Go | Clone org repos and walk git history, flagging sensitive files by filename/extension/path patterns only — no content scanning. | MIT |
| [shhgit](https://github.com/eth0izzle/shhgit) | 4.0k | JavaScript | Scans GitHub/GitLab/BitBucket repos for 150+ secret signatures with entropy fallback (abandoned) | MIT |
| [git-all-secrets](https://github.com/anshumanbh/git-all-secrets) | 1.1k | Go | Orchestrator that clones entire GitHub orgs/users/gists at scale and runs truffleHog+repo-supervisor, producing merged deduplicated secret reports. | MIT |
| [gitleaks-action](https://github.com/gitleaks/gitleaks-action) | 602 | JavaScript | GitHub Action that runs gitleaks SAST on push/PR/schedule, posts PR comments, and uploads SARIF artifacts for code scanning alerts. | — |
| [secret-magpie](https://github.com/punk-security/secret-magpie) | 243 | HTML | Orchestrator that enumerates repos from multiple Git providers and runs TruffleHog+Gitleaks on all branches, deduplicating results. | GPL-3.0 |
| [git-alerts](https://github.com/boringtools/git-alerts) | 232 | Go | Monitors public repos under GitHub org members' personal accounts, detecting leaked keys and sensitive files via TruffleHog/Gitleaks. | Apache-2.0 |
| [gitdorks_go](https://github.com/damit5/gitdorks_go) | 229 | Go | GitHub code-search API wrapper that runs dork keyword lists against a target org to find potentially sensitive code snippets. | — |
| [repository-scanner](https://github.com/abnamro/repository-scanner) | 166 | Python | Kubernetes-deployed Gitleaks wrapper that auto-scrapes repos from GitHub/Bitbucket/Azure DevOps and presents findings in a Vue3 dashboard. | MIT |
| [GitLeak](https://github.com/5alt/GitLeak) | 128 | JavaScript | Keyword-driven GitHub code search for passwords in sensitive files (.env etc), using filename+content combo queries. | MIT |
| [LeakIXClient](https://github.com/LeakIX/LeakIXClient) | 104 | Go | Go CLI & library for querying LeakIX's internet-leak index (exposed git configs, open DBs); not a scanner itself. | BSD-3-Clause |
| [git-secret-scanner](https://github.com/padok-team/git-secret-scanner) | 68 | Go | Wraps TruffleHog+Gitleaks to scan all repos in a GitHub org or GitLab group, merging results by fingerprint with dedup and baseline diff. | Apache-2.0 |
| [xGitGuard](https://github.com/Comcast/xGitGuard) | 64 | Python | Built by Comcast; a keyword + extension combo scanner based on the GitHub Code Search API, with a trainable ML false-positive filter, aimed at enterprise/public GitHub repos | Apache-2.0 |
| [keyscan](https://github.com/aerovato/keyscan) 🤖 | 58 | Python | Scans GitHub Gists for exposed API keys using a local LLM (qwen3:1.7b) to classify candidates, then verifies against provider endpoints. | GPL-3.0 |
| [claudleak](https://github.com/hazcod/claudleak) 🤖 | 57 | Go | Scans public GitHub repos for leaked secrets specifically in AI coding tool config files (.claude/, .cursor/, .codex/, etc.) via TruffleHog. | — |
| [secret-scanner](https://github.com/grab/secret-scanner) | 55 | Go | Gitrob-based Go CLI that signature-matches private keys, API secrets, and tokens across GitHub/GitLab/Bitbucket repos | MIT |
| [GSSAR](https://github.com/advanced-security/GSSAR) · | 51 | TypeScript | Auto-revokes secrets found by GitHub Secret Scanning via webhook-triggered Lambda remediators (AWS Step Functions); detection-free remediation layer. | MIT |
| [KeySentry](https://github.com/AdityaBhatt3010/KeySentry) | 41 | TypeScript | Simple regex-based CLI + web scanner for ~25 API key patterns and sensitive filenames in GitHub repos/local dirs. | MIT |
| [ghmon](https://github.com/sl4x0/ghmon) | 31 | Python | Python wrapper that orchestrates TruffleHog scans across GitHub/GitLab orgs with Discord/Telegram alerting and persistent state. | — |

---

<a id="llm-key"></a>
## 🤖 LLM / AI 키 전문 ⭐

**이 목록의 핵심 트랙**: AI 제공자 키에 특화된 탐색 및 노출 탐지 — OpenAI / Anthropic / Gemini / Groq / DeepSeek / 국내 OpenAI 호환 릴레이 등. 이는 GitHub에서 **어떤 권위 있는 awesome 목록도 다루지 않는** 공백 영역이자 Key Scanner의 주된 전장입니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
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
## ✅ 키 활성 / 유효성 검사

노출된 키가 여전히 유효한지, 그리고 그 할당량/권한이 무엇인지 판정합니다 — Key Scanner의 "활성 검사" 역량에 직접 대응합니다. 차용 가치가 가장 큽니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [keyhacks](https://github.com/streaak/keyhacks) | 6.3k | — | Curated cheatsheet of curl commands to validate whether leaked API keys from ~80 SaaS providers are still alive. | — |
| [driftwood](https://github.com/trufflesecurity/driftwood) 🔒Archived | 435 | Go | Checks if a cryptographic private key (RSA/EC/DSA PEM) is actively used as a GitHub SSH key or TLS certificate. | Apache-2.0 |
| [keyscope](https://github.com/SpectralOps/keyscope) | 411 | Rust | Rust CLI that validates whether given API keys are active/inactive against 44+ SaaS providers; no scanning or detection capability. | Apache-2.0 |
| [how-to-rotate](https://github.com/trufflesecurity/how-to-rotate) | 84 | JavaScript | Hugo-based documentation site with step-by-step API key rotation tutorials for 50+ services including AWS, GitHub, and Stripe. | AGPL-3.0 |
| [Gemini-API-Key-Exposure-Scanner](https://github.com/MuhammadKhizerJaved/Gemini-API-Key-Exposure-Scanner) 🤖 | 50 | Python | Validates a known Gemini/Google API key by probing capabilities (text/image/video/TTS) and generates a bug-bounty impact report. | — |
| [cpa-codex-auth-sweep](https://github.com/paradoxie/cpa-codex-auth-sweep) 🤖 | 35 | Python | Async Codex OAuth credential hygiene scanner: probes local auth files, classifies 401/quota/unlimited, purges dead tokens. | MIT |
| [GapiChecker](https://github.com/z3n70/GapiChecker) | 30 | Ruby | Interactive Ruby CLI that tests a user-supplied Google Maps API key against 13+ Google API endpoints to check if it's unrestricted (pentesting). | — |
| [openai_key_checker](https://github.com/aikemist/openai_key_checker) 🤖 | 26 | JavaScript | Web UI that probes an OpenAI API key to report whether it has access to GPT-4 models | — |
| [api-key-checker](https://github.com/purainity/api-key-checker) 🤖 | 15 | Python | Batch-checks the balance and availability of existing AI API keys (OpenRouter/SiliconFlow/DeepSeek/Gemini); not a scanning/discovery tool | — |
| [openai_api_key_checker](https://github.com/winklemad/openai_api_key_checker) 🤖 | 7 | Python | Multi-threaded validation of OpenAI API key validity with available-balance query; supports safe Ctrl+C interruption | — |
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
## 🧬 정규식 / 규칙 데이터베이스

자체 탐지기에 흡수할 수 있는 정규식 패턴과 규칙 데이터베이스입니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [gf-secrets](https://github.com/dwisiswant0/gf-secrets) | 245 | Shell | Static collection of 23 grep regex JSON patterns (AWS/GCP/Slack/Stripe/etc.) for the gf CLI wrapper; no scanner engine, no verification, no LLM key coverage. | MIT |
| [truffleHogRegexes](https://github.com/dxa4481/truffleHogRegexes) | 227 | Python | Flat JSON file of ~35 regex patterns for common service tokens (AWS, Slack, Stripe, Google); no scanner logic, no README, unmaintained since 2022. | GPL-3.0 |
| [scan4secrets](https://github.com/m14r41/scan4secrets) | 113 | Python | SAST/DAST scanner that regex-matches ~400 secret variable names (api_key, password, etc.) against local files and crawled URLs. | MIT |

---

<a id="js-web"></a>
## 🕸️ JS / 웹 / 브라우저 키 추출

JavaScript 번들, 웹 페이지, HAR, 브라우저/Burp 트래픽에서 노출된 키/토큰을 추출합니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [SecretFinder](https://github.com/m4ll0k/SecretFinder) | 2.5k | Python | Scans JavaScript files for hardcoded secrets (API keys, tokens, JWT) using regex patterns, supports URL/file/folder input. | GPL-3.0 |
| [mantra](https://github.com/brosck/mantra) | 911 | Go | Go CLI that regex-scans JS files and HTML pages (fed via stdin URLs) for hardcoded API keys from 100+ third-party services. | GPL-3.0 |
| [Trufflehog-Chrome-Extension](https://github.com/trufflesecurity/Trufflehog-Chrome-Extension) | 423 | JavaScript | Chrome extension that passively scans visited web pages, scripts, and auto-probed .env/.git/config for leaked API keys via regex. | GPL-2.0 |
| [keyleak-detector](https://github.com/Amal-David/keyleak-detector) · | 261 | Python | Runtime web key-leak detector: Playwright scans JS bundles to extract keys, actively verifies whether Supabase/Firebase RLS is enforced, paired with a Chrome extension for real-time capture | MIT |
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
## 🐳 컨테이너 / 런타임 / 메모리 / 게이트웨이 마스킹

컨테이너 이미지와 프로세스 메모리를 스캔하거나, 게이트웨이/로그 계층에서 실시간으로 마스킹합니다 — 런타임 보호 측면입니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [privacy-filter](https://github.com/packyme/privacy-filter) · | 251 | Go | Go library/HTTP/gRPC gateway that redacts PII and secrets from text before it reaches an LLM, using gitleaks rules + entropy + context heuristics. | MIT |
| [pii-shield](https://github.com/pii-shield/pii-shield) | 146 | Go | K8s sidecar that sanitizes PII/secrets from application logs via entropy analysis + context keywords before logs leave the pod. | Apache-2.0 |
| [truffleproc](https://github.com/controlplaneio/truffleproc) | 125 | Shell | Dumps a running process's memory via gdb coredump, extracts strings, then runs TruffleHog to find secrets resident only in RAM. | Apache-2.0 |
| [agentveil](https://github.com/vurakit/agentveil) · | 83 | Go | Reverse proxy that anonymizes PII/secrets in LLM API requests, stores tokens in AES-256 Redis vault, rehydrates on response | MIT |
| [layerleak](https://github.com/Brumbelow/layerleak) | 40 | Go | Scans OCI container image layers, configs, and history for secrets without requiring Docker daemon | MIT |

---

<a id="honeypot"></a>
## 🍯 허니팟 / 카나리 토큰

가짜 키/미끼를 배치하고 노출과 악용 흔적을 추적합니다 (탐지와 상호 보완되는 방어 측면). AI/LLM 허니팟도 포함합니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [canarytokens](https://github.com/thinkst/canarytokens) | 2.1k | Python | Honeypot platform that generates decoy tokens (AWS keys, kubeconfigs, docs, URLs) and alerts when they are accessed or used. | GPL-3.0 |
| [canarytokens-docker](https://github.com/thinkst/canarytokens-docker) | 657 | Dockerfile | One-command Docker deployment of a Canarytokens honeypot server, deploying DNS/HTTP/PDF/AWS decoy tokens and capturing trigger alerts. | BSD-3-Clause |
| [honeyLambda](https://github.com/0x4D31/honeyLambda) | 526 | Python | Serverless URL honeytoken deployer: plants fake HTTP endpoints on AWS Lambda and alerts when attackers hit them — does NOT scan for leaked keys. | GPL-3.0 |
| [dcept](https://github.com/secureworks/dcept) | 504 | Python | Active Directory honeytoken tripwire: deploys fake creds in endpoint memory, detects their use against domain controllers. | GPL-3.0 |
| [honeybits](https://github.com/0x4D31/honeybits) 🔒Archived | 277 | Go | Archived PoC that plants fake credentials, bash_history entries, and honeyfiles on prod hosts to lure attackers toward honeypots. | GPL-3.0 |
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
## 🪝 AI 에이전트 시크릿 가로채기 훅

Claude Code / Cursor / Codex 같은 AI 코딩 에이전트에 추가되는 시크릿 스캐닝 훅, 스킬, MCP 도구입니다 (신흥 트렌드).

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
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
## 🏢 SaaS / 다중 플랫폼 모니터링

Slack / Jira / Confluence / Gitee 같은 협업 플랫폼 전반에 노출된 키를 모니터링합니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [badsecrets](https://github.com/blacklanternsecurity/badsecrets) | 804 | Python | Detects known/default cryptographic keys in web framework artifacts (cookies, JWTs, viewstates) via offline verification and active probing. | AGPL-3.0 |
| [slack-watchman](https://github.com/PaperMtn/slack-watchman) | 402 | Python | Scans Slack workspace messages/files via Slack API for leaked API keys, tokens, PII, and sensitive files using YAML signatures. | GPL-3.0 |
| [n0s1](https://github.com/spark1security/n0s1) | 77 | Python | Regex+entropy secret scanner targeting SaaS collab platforms (Slack, Jira, Confluence, Asana, Zendesk, Linear, Wrike) plus GitHub/GitLab repos and local files. | GPL-3.0 |
| [secret-scanning-tools](https://github.com/advanced-security/secret-scanning-tools) | 0 | Python | CI test suite for validating GitHub's built-in custom secret scanning patterns, not a standalone key/secret detector. | MIT |

---

<a id="reference"></a>
## 📚 참고 자료 및 워드리스트

키 검증 방법론, 노출 사례, 페이로드 워드리스트, 기존 awesome 목록입니다 — 도구는 아니지만 차용 가치가 매우 높습니다.

| 도구 | ⭐ | 언어 | 설명 | 라이선스 |
|------|----|----|------|------|
| [SecLists](https://github.com/danielmiessler/SecLists) | 71.7k | PHP | Curated collection of wordlists, payloads, and patterns for penetration testing and security assessments. | MIT |
| [nuclei](https://github.com/projectdiscovery/nuclei) | 29.3k | Go | General-purpose DAST vulnerability scanner using YAML templates; not a secret/key detection tool. | MIT |
| [APISecurityBestPractices](https://github.com/GitGuardian/APISecurityBestPractices) | 2.0k | — | GitGuardian's reference documentation with leak remediation checklists and secret management best practices—not a scanning tool, pure markdown guidance from 2019. | — |
| [changeme](https://github.com/ztgrace/changeme) | 1.5k | Python | Network default-credential scanner that probes live services (HTTP/SSH/DB) for known default passwords via YAML-defined fingerprint database. | GPL-3.0 |
| [leaky-repo](https://github.com/Plazmaz/leaky-repo) | 247 | Python | Benchmark corpus of fake secrets (configs, keys, high-entropy) for evaluating scanner tools' recall and precision. | MIT |
| [secret-scanning-custom-patterns](https://github.com/advanced-security/secret-scanning-custom-patterns) | 176 | HTML | Curated regex pattern library for GitHub Advanced Security's custom secret scanning, covering 80+ secret types across vendors, databases, PII, and generic credentials. | MIT |

---

<a id="experimental"></a>
## 🧪 실험적 / 소규모 도구

스타 수가 적거나 실험적 성격이지만, 틈새 방향을 대표하거나 차용 가능한 작은 기법을 담고 있습니다.

| 도구 | ⭐ | 설명 |
|------|----|------|
| [llm-wiki_obsidian_hermes_r0b0tlabbra1n](https://github.com/r0b0tlab/llm-wiki_obsidian_hermes_r0b0tlabbra1n) | 21 | Agent memory system (Obsidian vault + SQLite FTS5) with a basic regex secret scanner as write-guard, not a dedicated key finder. |
| [ApiKeyValidator](https://github.com/Syed-Ali-Dev/ApiKeyValidator) | 0 | Web UI to paste OpenAI/Anthropic keys for liveness checking (billing/rate-limit/model list); a pure validation tool, no scanning or leak detection |

---

<a id="absorb"></a>
## 🧩 기술 차용 치트시트 (흡수 가능한 아이디어)

> 이 목록의 **핵심 부가 가치**: 각 도구의 고유한 기법을 "흡수 가능한 아이디어" 표로 집약해 Key Scanner의 개선 방향에 직접 매핑합니다. "거인의 어깨 위에 서기"를 위한 실전 체크리스트입니다.

| 기법 | 대표 도구 | Key Scanner에 흡수 가능한 아이디어 |
|------|---------|--------------------------|
| **키워드 사전 필터 게이트 (Keyword pre-filter gate)** | truffleHog / gitleaks / kingfisher | 각 탐지기는 앵커 문자열(예: OpenAI의 base64 `T3BlbkFJ`)을 선언하고, 정규식 실행 전 초고속 문자열 매칭을 먼저 돌려 무관한 콘텐츠를 건너뜁니다 — 스캐닝 처리량을 몇 배로 끌어올릴 수 있습니다. |
| **검증 후 분석 (Verify-then-analyze)** | truffleHog | 활성 검사가 유효/무효 이상을 반환합니다: YAML로 정의된 제공자별 권한 모델이 키의 정확한 범위/할당량/보이는 리소스를 나열합니다. |
| **피해 반경 매핑 (Blast-radius mapping)** | mongodb/kingfisher | 노출된 키 → 클라우드 식별자 → 실제 노출된 리소스(43개 제공자)로 연결해, "노출이 있다"를 "무엇이 노출됐는지"로 끌어올려 조치 우선순위를 직접 결정합니다. |
| **API 호출 없는 체크섬 검증 (Checksum validation without API calls)** | mongodb/kingfisher | GitHub/Confluent 등 토큰의 경우 내장 체크섬 알고리즘으로 네트워크 요청 없이 유효성을 판정합니다 (할당량 소비 영, 감사 추적 영). |
| **베이스라인 스냅샷 + 증분 디프 (Baseline snapshot + incremental diff)** | Yelp/detect-secrets | 기존 시크릿을 베이스라인 JSON으로 스냅샷 떠놓고, CI에서는 "새로운" 것만 경고합니다 — 과거 오탐을 한 번에 청소합니다. |
| **ML 의미불명 분류기 (ML gibberish classifier)** | Yelp/detect-secrets | 학습된 분류기(rfc.model)로 고엔트로피 문자열 오탐을 걸러내어, 순수 엔트로피 임계값보다 더 정확합니다. |
| **정규식 → LLM 2단계 판정 (Regex→LLM two-stage adjudication)** | juanfont/atalaia | 탐지기는 재현율을 유지하고, 단일 스키마 제약 LLM 호출이 정밀도를 판정합니다; 확인/알려진 테스트 키는 토큰 절약을 위해 LLM 앞에서 단락 회로로 건너뜁니다. |
| **이중 임계값 엔트로피 + 문맥 근접 게이트 (Dual-threshold entropy + context proximity gate)** | packyme/privacy-filter | `password`/`api_key` 같은 문맥 키워드가 있으면 낮은 엔트로피 임계값(4.0)을, 없으면 높은 값(4.8)을 씁니다 — 정량화된 문맥 휴리스틱입니다. |
| **오탭 거리 파이프라인 (FP-rejection pipeline)** | packyme/privacy-filter | 템플릿 변수 / UUID / hex 해시 / 경로-URL 경계 / 자리표시자 단어 / JSON 콤마 노이즈 — 고엔트로피 오탐을 규칙별로 하나씩 거부합니다. |
| **6상태 키 상태 분류 (6-state key status classification)** | ssfun/llm-api-key-checker | 유효/무효를 넘어 저잔액 / 영 / 할당량 소진 / 속도제한 / 정상으로 세분화 — 활성 결과를 더 조치 가능하게 만듭니다. |
| **키별 역량 매트릭스 (Per-key capability matrix)** | datumbrain/keyprobe | 활성 여부를 넘어 해당 키가 어떤 모델을 쓸 수 있는지, 스트리밍/배치/파일을 지원하는지 보고합니다 — keyscanner의 제공자 매핑에 직접 대응합니다. |
| **BaaS 악용가능성 능동 탐침 (BaaS exploitability active probing)** | Amal-David/keyleak-detector | Supabase/Firebase anon 키 탐지 후 RLS가 적용되는지 능동 탐침해 "키를 찾았다"를 "악용 가능함을 입증한" 공격 체인으로 끌어올립니다. |
| **AIza 키 분류 (Maps vs Gemini) (AIza key classification (Maps vs Gemini))** | Amal-David/keyleak-detector | 같은 AIza 접두어: 노출이 예상되는 Maps 키와 실제 노출된 Gemini 키를 구분합니다 — 오탭을 줄입니다. |
| **AI 코딩 보조 훅 프로토콜 (AI coding-assistant hook protocol)** | GitGuardian/ggshield / mintmcp/agent-security | stdin JSON 이벤트(pretooluse/userpromptsubmit)를 가로채 차단/허용을 반환합니다; 오픈 페일 설계: 크래시/인증 실패 시 허용+경고, 사용자를 절대 잠그지 않습니다. |
| **카나리 토큰을 LLM 키로 (Canary token as LLM key)** | thinkst/canarytokens | 테스트 설정/저장소에 가짜 LLM API 키를 허니토큰으로 심어두고, 조회 시 경고합니다 — 노출 경로를 사전 탐지합니다. |
| **회전 튜토리얼 직접 링크 (Rotation-tutorial direct link)** | trufflesecurity/how-to-rotate | 스캔 결과 옆에 해당 제공자의 키 회전 단계로 직접 링크해, 사용자가 결과를 받자마자 조치할 수 있게 합니다. |
| **제공자별 검증 스펙 선언 (Declared per-provider verification spec)** | SpectralOps/keyscope | 각 제공자의 검증 방법을 YAML로 선언합니다(플립 모드 포함: 회전 감사를 위해 키가 이미 폐기됐음을 단언); 제공자 추가는 설정만으로 끝납니다. |
| **마스크 결과 내부 마스킹 출력 (Mask-result in-place redaction output)** | secretlint | 소스 파일 내부에서 적중 값을 내부 마스킹하고, SARIF 업로드로 GitHub Code Scanning과 짝짓습니다. |
| **조직 단위 확장 + 파일명 서명 DB (Org-level fan-out + filename signature DB)** | michenriksen/gitrob | 조직원 전체를 나열한 뒤 각자의 저장소를 병렬로 스캔합니다; 고품위 파일 위치 파악용 ~90개 파일명/확장자 서명(.pem/.kdbx/.sqlite…)을 갖춥니다. |
| **심층 추출 (zip/office/sqlite/pyc) (Deep extraction (zip/office/sqlite/pyc))** | mongodb/kingfisher | 아카이브, Office 문서, SQLite, Python .pyc에서 키를 추출합니다 — GitHub API 스캐닝이 닿지 못하는 산출물을 덮습니다. |
| **Git-blob SHA-1 중복 제거 (Git-blob SHA-1 dedup)** | praetorian-inc/noseyparker | 동일 콘텐츠를 blob 수준에서 SHA-1 중복 제거해, 입력/저장소 간 동일 키를 단일 결과로 접습니다(10-1000배 압축), 대규모 조직 스캔에서 분류 노이즈를 대폭 줄입니다. |
| **로컬 LLM으로 테스트 가짜 키와 실제 자격증명 구분 (Local LLM distinguishing test fake keys vs real credentials)** | JamesTheGiblet/Whisper | 로컬 Ollama로 정규식/엔트로피 탐지 후보를 문맥적으로 분류해, 테스트 자리표시자 키와 실제 자격증명을 구분합니다 — 오프라인, 할당량 영, 오탭 감소. |
| **JS AST 변수명 → 할당 위치 파악 (JS AST locating variable-name → assignment)** | DonIsaac/keyhunter | oxc로 JS를 AST로 파싱해 변수명(예: OPENAI_API_KEY)으로 위치를 찾은 뒤 할당을 취해, 노골한 값과 변수명 문맥을 구분합니다; CDN/라이브러리 자동 건너뛰기 포함 — 웹 JS 스캐닝에서 오탭 감소. |
| **ML 사후 필터 + 공개 벤치마크 (CredData) (ML post-filter + public benchmark (CredData))** | Samsung/CredSweeper | TF→ONNX 경량 분류기가 정규식 적중을 사후 필터링합니다; 재현 가능한 재현율/정밀도 평가용 CredData 공개 벤치마크 데이터셋을 함께 제공합니다. |

---

<a id="contributing"></a>
## 🙋 기여하기

기여를 환영합니다! PR을 열 때 제공해 주세요: 도구 이름(점프 링크 포함), 스타 수, 주 언어, 한 줄 설명, 라이선스, 그리고 "API 키 / LLM 키 노출 탐지"와의 관련성 표시. 고유한 기법이 있다면 [기술 차용 치트시트](#absorb)에 추가해 주세요.

<a id="license"></a>
## 📜 라이선스

목록 콘텐츠는 [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/)에 따라 퍼블릭 도메인에 귀속됩니다. 각 도구는 자체 라이선스를 유지합니다.


---

<a id="star-history"></a>
## ⭐ Star History

<sub>이 목록이 도움이 되었다면 ⭐ 를 남겨주세요 — 더 많은 분이 찾을 수 있어요.</sub>

<a href="https://star-history.com/#Lxcardoza993/awesome-api-key-leak-detection&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date" />
  </picture>
</a>

[⬆ 맨 위로](#awesome-api-key-leak-detection)
