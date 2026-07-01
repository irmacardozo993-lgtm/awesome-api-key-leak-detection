# 🔑 Awesome API Key Leak Detection
**اللغات:** [English](README.md) • [简体中文](README.zh-CN.md) • [繁體中文](README.zh-TW.md) • [Español](README.es.md) • [Français](README.fr.md) • [Deutsch](README.de.md) • [日本語](README.ja.md) • [한국어](README.ko.md) • [Português (BR)](README.pt-BR.md) • [Русский](README.ru.md) • **العربية** • [Italiano](README.it.md)

> قائمة منتقاة لأدوات ومصادر **اكتشاف مفاتيح API / كشف تسرّب مفاتيح API للنماذج اللغوية الكبيرة (LLM)**.
> مبنيٌّ فوق أداة [Key Scanner](https://github.com/irmacardozo993-lgtm/key-scanner) المطوَّرة ذاتيًّا، ويُفهرس منهجيًّا جميع المشاريع السابقة ذات الصلة — **واقفًا على أكتاف العمالقة، متجنّبًا إعادة اختراع العجلة.**
>
> كل أداة موسومة بتقنياتها الفريدة و"أفكارها القابلة للاستيعاب"، بحيث يمكنك الحكم على ما يستحق الاقتراض إلى ماسحك الخاص.

<a id="acknowledgments"></a>
## 🙏 شكر وتقدير

- **[Telegram OpenClaw 中文社区](https://t.me/OpenClaw_Group)** — مجتمع OpenClaw الصيني على تيليجرام — شكرًا على الدعم والنقاش.
- **[Linux.do](https://linux.do)** — مجتمع للمطورين والتقنية باللغة الصينية (Discourse) — شكرًا على الملاحظات والانتشار.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re) ![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg) ![Tools](https://img.shields.io/badge/tools-130+-blue) ![Focus: LLM Keys](https://img.shields.io/badge/focus-LLM%20keys-purple) ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)

---

## جدول المحتويات

- [1. 🏆 العمالقة: ماسحات الأسرار على مستوى المؤسسات](#giants)
- [2. 🚀 الماسحات عالية الأداء / الناشئة](#hp-scanner)
- [3. 🔎 استطلاع GitHub والبحث في المستودعات العامة](#github-recon)
- [4. 🤖 مختصو مفاتيح LLM / الذكاء الاصطناعي ⭐](#llm-key)
- [5. ✅ فحص حيوية المفاتيح / صحتها](#key-validator)
- [6. 🧬 قواعد بيانات الـ regex / القواعد](#pattern-db)
- [7. 🕸️ استخراج مفاتيح JS / الويب / المتصفح](#js-web)
- [8. 🐳 الحاويات / وقت التشغيل / الذاكرة / التنقيح عند البوابة](#container-runtime)
- [9. 🍯 الفخاخ / رموز الـ canary](#honeypot)
- [10. 🪝 خطافات اعتراض الأسرار لوكلاء الذكاء الاصطناعي](#ai-agent-hook)
- [11. 🏢 مراقبة SaaS / متعددة المنصات](#saas)
- [12. 📚 مصادر مرجعية وقوائم كلمات](#reference)
- [13. 🧪 أدوات تجريبية / صغيرة](#experimental)
- [14. 🧩 ورقة غش الاقتراض التقني (أفكار قابلة للاستيعاب)](#absorb)
- [🙋 المساهمة](#contributing) · [🙏 شكر وتقدير](#acknowledgments) · [📜 الترخيص](#license)

---

## وسيلة الإيضاح

| العلامة | المعنى |
|------|------|
| ⭐ | عدد نجوم GitHub (وقت البحث، تقريبي) |
| `Language` | اللغة الأساسية |
| `License` | ترخيص مفتوح المصدر |
| 🤖 | مرتبط مباشرةً بكشف تسرّب مفاتيح LLM/الذكاء الاصطناعي (محور هذه القائمة) |
| · | مرتبط جزئيًّا (يغطي عدة فئات بما فيها مفاتيح الذكاء الاصطناعي) |
| 🔒Archived | المستودع مؤرشف |

> المدخلات الموسومة بـ 🤖 تنتمي إلى مسار "كشف تسرّب مفاتيح LLM API" — منطقة فارغة على GitHub **لا يغطيها حاليًّا أي قائمة awesome موثوقة**.

---

<a id="matrix"></a>
## 🗺️ نظرة عامة: مصفوفة قدرات الأدوات الأساسية

> قارن الأدوات الأساسية عبر أبعاد القدرة لتحديد موضع "ما هو مفقود" / "ما الذي يمكن اقتراضه" بسرعة.

| الأداة | ⭐ | الكشف | الحيوية | متعدد المصادر (ويب/محلي) | مفاتيح LLM | اللغة |
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
## 🏆 العمالقة: ماسحات الأسرار على مستوى المؤسسات

المعيار الفعلي لمسح الأسرار/بيانات الاعتماد العامة، بأكثر نظام بيئي نضجًّا وأكثر القواعد اكتمالًا. المرجع الأول لأي مشروع مسح أسرار.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🚀 الماسحات عالية الأداء / الناشئة

محرّكات Rust/Go عالية الأداء، ماسحات موجّهة للبحث أو ذات كشف مبتكر — غالبًا ما تأتي بتقنيات هندسية قابلة للاقتراض.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🔎 استطلاع GitHub والبحث في المستودعات العامة

اصطياد جماعي للمفاتيح المتسرّبة من مستودعات GitHub/Gitee/Bitbucket العامة، وتدفقات الأحداث، وبحث الأكواد. يقابل وضعي `recent-public` / `github-events` في Key Scanner.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🤖 مختصو مفاتيح LLM / الذكاء الاصطناعي ⭐

**المسار المحوري لهذه القائمة**: الاكتشاف وكشف التسرّب المستهدف تحديدًا لمفاتيح مزودي الذكاء الاصطناعي — OpenAI / Anthropic / Gemini / Groq / DeepSeek / المُرحِّلات المحلية المتوافقة مع OpenAI، إلخ. هذه منطقة فارغة على GitHub **لا يغطيها أي قائمة awesome موثوقة**، وهي ساحة المعركة الرئيسية لـ Key Scanner.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## ✅ فحص حيوية المفاتيح / صحتها

تحديد ما إذا كان مفتاح متسرّب لا يزال صالحًا، وما حصته/أذوناته — يقابل مباشرةً قدرة "فحص الحيوية" في Key Scanner. الأكثر استحقاقًا للاقتراض.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🧬 قواعد بيانات الـ regex / القواعد

أنماط regex وقواعد بيانات قواعد قابلة للاستيعاب في كواشفك الخاصة.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
|------|----|----|------|------|
| [gf-secrets](https://github.com/dwisiswant0/gf-secrets) | 245 | Shell | Static collection of 23 grep regex JSON patterns (AWS/GCP/Slack/Stripe/etc.) for the gf CLI wrapper; no scanner engine, no verification, no LLM key coverage. | MIT |
| [truffleHogRegexes](https://github.com/dxa4481/truffleHogRegexes) | 227 | Python | Flat JSON file of ~35 regex patterns for common service tokens (AWS, Slack, Stripe, Google); no scanner logic, no README, unmaintained since 2022. | GPL-3.0 |
| [scan4secrets](https://github.com/m14r41/scan4secrets) | 113 | Python | SAST/DAST scanner that regex-matches ~400 secret variable names (api_key, password, etc.) against local files and crawled URLs. | MIT |

---

<a id="js-web"></a>
## 🕸️ استخراج مفاتيح JS / الويب / المتصفح

استخراج المفاتيح/الرموز المتسرّبة من حزم JavaScript وصفحات الويب وملفات HAR وحركة المتصفح/Burp.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🐳 الحاويات / وقت التشغيل / الذاكرة / التنقيح عند البوابة

مسح صور الحاويات وذاكرة العمليات، أو التنقيح لحظيًّا عند طبقة البوابة/السجلات — جانب الحماية في وقت التشغيل.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
|------|----|----|------|------|
| [privacy-filter](https://github.com/packyme/privacy-filter) · | 251 | Go | Go library/HTTP/gRPC gateway that redacts PII and secrets from text before it reaches an LLM, using gitleaks rules + entropy + context heuristics. | MIT |
| [pii-shield](https://github.com/pii-shield/pii-shield) | 146 | Go | K8s sidecar that sanitizes PII/secrets from application logs via entropy analysis + context keywords before logs leave the pod. | Apache-2.0 |
| [truffleproc](https://github.com/controlplaneio/truffleproc) | 125 | Shell | Dumps a running process's memory via gdb coredump, extracts strings, then runs TruffleHog to find secrets resident only in RAM. | Apache-2.0 |
| [agentveil](https://github.com/vurakit/agentveil) · | 83 | Go | Reverse proxy that anonymizes PII/secrets in LLM API requests, stores tokens in AES-256 Redis vault, rehydrates on response | MIT |
| [layerleak](https://github.com/Brumbelow/layerleak) | 40 | Go | Scans OCI container image layers, configs, and history for secrets without requiring Docker daemon | MIT |

---

<a id="honeypot"></a>
## 🍯 الفخاخ / رموز الـ canary

نشر مفاتيح/طُعم زائفة وتتبع آثار التسرّب والاستغلال (الجانب الدفاعي، مكمّل للكشف). يشمل فخاخ الذكاء الاصطناعي/LLM.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🪝 خطافات اعتراض الأسرار لوكلاء الذكاء الاصطناعي

خطافات مسح الأسرار ومهارات وأدوات MCP مضافة إلى وكلاء البرمجة بالذكاء الاصطناعي مثل Claude Code / Cursor / Codex (اتجاه ناشئ).

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
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
## 🏢 مراقبة SaaS / متعددة المنصات

مراقبة المفاتيح المكشوفة عبر منصات التعاون مثل Slack / Jira / Confluence / Gitee.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
|------|----|----|------|------|
| [badsecrets](https://github.com/blacklanternsecurity/badsecrets) | 804 | Python | Detects known/default cryptographic keys in web framework artifacts (cookies, JWTs, viewstates) via offline verification and active probing. | AGPL-3.0 |
| [slack-watchman](https://github.com/PaperMtn/slack-watchman) | 402 | Python | Scans Slack workspace messages/files via Slack API for leaked API keys, tokens, PII, and sensitive files using YAML signatures. | GPL-3.0 |
| [n0s1](https://github.com/spark1security/n0s1) | 77 | Python | Regex+entropy secret scanner targeting SaaS collab platforms (Slack, Jira, Confluence, Asana, Zendesk, Linear, Wrike) plus GitHub/GitLab repos and local files. | GPL-3.0 |
| [secret-scanning-tools](https://github.com/advanced-security/secret-scanning-tools) | 0 | Python | CI test suite for validating GitHub's built-in custom secret scanning patterns, not a standalone key/secret detector. | MIT |

---

<a id="reference"></a>
## 📚 مصادر مرجعية وقوائم كلمات

منهجية التحقق من المفاتيح، وحالات التسرّب، وقوائم كلمات الحمولات، وقوائم awesome الموجودة — ليست أدوات ولكنها تستحق الاقتراض بشدّة.

| الأداة | ⭐ | اللغة | الوصف | الترخيص |
|------|----|----|------|------|
| [SecLists](https://github.com/danielmiessler/SecLists) | 71.7k | PHP | Curated collection of wordlists, payloads, and patterns for penetration testing and security assessments. | MIT |
| [nuclei](https://github.com/projectdiscovery/nuclei) | 29.3k | Go | General-purpose DAST vulnerability scanner using YAML templates; not a secret/key detection tool. | MIT |
| [APISecurityBestPractices](https://github.com/GitGuardian/APISecurityBestPractices) | 2.0k | — | GitGuardian's reference documentation with leak remediation checklists and secret management best practices—not a scanning tool, pure markdown guidance from 2019. | — |
| [changeme](https://github.com/ztgrace/changeme) | 1.5k | Python | Network default-credential scanner that probes live services (HTTP/SSH/DB) for known default passwords via YAML-defined fingerprint database. | GPL-3.0 |
| [leaky-repo](https://github.com/Plazmaz/leaky-repo) | 247 | Python | Benchmark corpus of fake secrets (configs, keys, high-entropy) for evaluating scanner tools' recall and precision. | MIT |
| [secret-scanning-custom-patterns](https://github.com/advanced-security/secret-scanning-custom-patterns) | 176 | HTML | Curated regex pattern library for GitHub Advanced Security's custom secret scanning, covering 80+ secret types across vendors, databases, PII, and generic credentials. | MIT |

---

<a id="experimental"></a>
## 🧪 أدوات تجريبية / صغيرة

عدد نجوم منخفض أو تجريبية بطبيعتها، لكنها تمثل اتجاهًا متخصصًا أو تحتوي على حِيَل صغيرة قابلة للاقتراض.

| الأداة | ⭐ | الوصف |
|------|----|------|
| [llm-wiki_obsidian_hermes_r0b0tlabbra1n](https://github.com/r0b0tlab/llm-wiki_obsidian_hermes_r0b0tlabbra1n) | 21 | Agent memory system (Obsidian vault + SQLite FTS5) with a basic regex secret scanner as write-guard, not a dedicated key finder. |
| [ApiKeyValidator](https://github.com/Syed-Ali-Dev/ApiKeyValidator) | 0 | Web UI to paste OpenAI/Anthropic keys for liveness checking (billing/rate-limit/model list); a pure validation tool, no scanning or leak detection |

---

<a id="absorb"></a>
## 🧩 ورقة غش الاقتراض التقني (أفكار قابلة للاستيعاب)

> **القيمة المضافة المحورية** لهذه القائمة: تجميع تقنيات كل أداة الفريدة في جدول "أفكار قابلة للاستيعاب"، مخطوطةً مباشرةً إلى اتجاهات تحسين Key Scanner. هذه قائمة التحقق العملية لـ "الوقوف على أكتاف العمالقة".

| التقنية | الأداة الممثلة | الفكرة القابلة للاستيعاب في Key Scanner |
|------|---------|--------------------------|
| **بوابة الترشيح المسبق بالكلمات المفتاحية (Keyword pre-filter gate)** | truffleHog / gitleaks / kingfisher | يُعرِّف كل كاشف سلسلة ارتساء (مثل `T3BlbkFJ` بـ base64 الخاص بـ OpenAI)، ويُجري مطابقة سلاسل فائقة السرعة قبل الـ regex، متخطيًّا المحتوى غير ذي الصلة — يمكن أن ترتفع إنتاجية المسح عدة أضعاف. |
| **تحقّق ثم حلّل (Verify-then-analyze)** | truffleHog | فحص الحيوية يُعيد أكثر من صالح/غير صالح: نموذج أذونات لكل مزود معرَّف بـ YAML يُعدِّد النطاق/الحصة/الموارد المرئية للمفتاح بدقة. |
| **خرائط نطاق الانفجار (Blast-radius mapping)** | mongodb/kingfisher | مفتاح متسرّب ← هوية سحابية ← موارد مكشوفة فعليًّا (43 مزودًا)، ترقيةً من "هناك تسرّب" إلى "ما الذي تسرّب"، مدفوعةً مباشرةً بأولوية المعالجة. |
| **التحقق عبر الـ checksum دون استدعاءات API (Checksum validation without API calls)** | mongodb/kingfisher | لرموز GitHub/Confluent إلخ، استخدم خوارزمية checksum مدمجة للحكم على الصلاحية دون أي طلب شبكة (استهلاك حصة صفري، أثر تدقيق صفري). |
| **لقطة أساسية + فرق تزايدي (Baseline snapshot + incremental diff)** | Yelp/detect-secrets | التقاط الأسرار الموجودة في JSON أساسي، ثم التنبيه فقط على "الجديدة" منها في CI — تُمسح الإيجابيات الكاذبة التاريخية في جولة واحدة. |
| **مُصنِّف الهراء بالتعلّم الآلي (ML gibberish classifier)** | Yelp/detect-secrets | استخدام مُصنِّف مدرّب (rfc.model) لترشيح إيجابيات السلاسل عالية الإنتروبيا الكاذبة، أدق من عتبات الإنتروبيا الصرفة. |
| **تحكيم على مرحلتين regex←LLM (Regex→LLM two-stage adjudication)** | juanfont/atalaia | يحافظ الكاشف على الاستدعاء، ثم استدعاء LLM واحد مقيّد بمخطط يحكّم في الدقة؛ المفاتيح الاختبارية المؤكَّدة/المعروفة تتجاوز LLM عبر اختصار لتوفير الرموز. |
| **إنتروبيا بعتبتين + بوابة التقارب السياقي (Dual-threshold entropy + context proximity gate)** | packyme/privacy-filter | عند حضور كلمات سياقية مثل `password`/`api_key` تُستخدم عتبة إنتروبيا منخفضة (4.0)، وإلا فمرتفعة (4.8) — استدلال سياقي مُكمَّم. |
| **خط رفض الإيجابيات الكاذبة (FP-rejection pipeline)** | packyme/privacy-filter | متغيرات القوالب / UUIDs / تجزئات hex / حدود المسار-URL / كلمات placeholder / ضجيج فواصل JSON — رفض الإيجابيات الكاذبة عالية الإنتروبيا قاعدةً تلو الأخرى. |
| **تصنيف حالة المفتاح إلى 6 حالات (6-state key status classification)** | ssfun/llm-api-key-checker | ما بعد صالح/غير صالح: تقسيم فرعي إلى رصيد-منخفض / صفري / حصة-مستنزفة / محدود-المعدل / طبيعي — تصبح نتائج الحيوية أكثر قابلية للتشغيل. |
| **مصفوفة قدرات لكل مفتاح (Per-key capability matrix)** | datumbrain/keyprobe | ما بعد الحيوية، الإبلاغ عن النماذج التي يستطيع المفتاح استخدامها وما إذا كان يدعم البث/الدفعات/الملفات — يُخطَّط مباشرةً إلى مخطط المزودين في keyscanner. |
| **الاستكشاف النشط لقابلية استغلال BaaS (BaaS exploitability active probing)** | Amal-David/keyleak-detector | بعد كشف مفتاح anon لـ Supabase/Firebase، الاستكشاف النشط لما إذا كان RLS مُطبَّقًا، ترقيةً من "وُجد مفتاح" إلى سلسلة هجوم "قابلة للاستغلال مثبتة". |
| **تصنيف مفتاح AIza (Maps مقابل Gemini) (AIza key classification (Maps vs Gemini))** | Amal-David/keyleak-detector | نفس سابقة AIza: التمييز بين مفتاح Maps المتوقع تعرّضه ومفتاح Gemini المتسرّب فعلًا — يقلل الإيجابيات الكاذبة. |
| **بروتوكول خطاف مساعد البرمجة بالذكاء الاصطناعي (AI coding-assistant hook protocol)** | GitGuardian/ggshield / mintmcp/agent-security | اعتراض أحداث JSON عبر stdin (pretooluse/userpromptsubmit)، وإعادة block/allow؛ تصميم fail-open: عند الانهيار/فشل المصادقة، اسمح + نبِّه، ولا تقفل المستخدم خارجًا أبدًا. |
| **رمز canary كمفتاح LLM (Canary token as LLM key)** | thinkst/canarytokens | زرع مفاتيح LLM API زائفة في إعدادات/مستودعات الاختبار كرموز عسل، والتنبيه عند الاستعلام — كشف استباقي لمسار التسرّب. |
| **رابط مباشر لدرس التدوير (Rotation-tutorial direct link)** | trufflesecurity/how-to-rotate | بجانب نتيجة مسح، ربط مباشر بخطوات تدوير مفتاح ذلك المزود، بحيث يستطيع المستخدم المعالجة فور استلام النتيجة. |
| **مواصفات تحقق معلنة لكل مزود (Declared per-provider verification spec)** | SpectralOps/keyscope | الإعلان عن طريقة تحقق كل مزود في YAML (بما فيها flip-mode: التأكد من أن المفتاح مُبطَّل أصلًا، لتدقيق التدوير)؛ إضافة مزود هي إعداد فقط. |
| **إخراج تنقيح في-الموضع بنتيحة مقنّعة (Mask-result in-place redaction output)** | secretlint | تقنيع القيم المُصابة في-الموضع داخل الملفات المصدرية، مقرونًا برفع SARIF إلى GitHub Code Scanning. |
| **انتشار على مستوى المؤسسة + قاعدة بيانات تواقيع أسماء الملفات (Org-level fan-out + filename signature DB)** | michenriksen/gitrob | إحصاء جميع أعضاء المؤسسة ثم مسح مستودعات كل واحد منهم بالتوازي؛ ~90 توقيع اسم ملف/امتداد (.pem/.kdbx/.sqlite…) لتحديد موقع الملفات عالية القيمة. |
| **الاستخراج العميق (zip/office/sqlite/pyc) (Deep extraction (zip/office/sqlite/pyc))** | mongodb/kingfisher | استخراج المفاتيح من الأرشيفات ومستندات Office وSQLite وPython .pyc — يغطي قطعًا لا يبلغها مسح GitHub API. |
| **إزالة تكرار Git-blob عبر SHA-1 (Git-blob SHA-1 dedup)** | praetorian-inc/noseyparker | إزالة تكرار SHA-1 على مستوى الـ blob للمحتوى المتطابق، طيّ المفاتيح المتطابقة عبر المدخلات/المستودعات في نتيجة واحدة (ضغط 10-1000x)، خفضًا حادًّا لضجيج الفرز في مسح المؤسسات واسع النطاق. |
| **تمييز LLM محلي بين المفاتيح الاختبارية الزائفة وبيانات الاعتماد الحقيقية (Local LLM distinguishing test fake keys vs real credentials)** | JamesTheGiblet/Whisper | استخدام Ollama محلي لتصنيف المرشحين المكتشفين بـ regex/إنتروبيا سياقيًّا، تمييزًا لمفاتيح placeholder الاختبارية عن بيانات الاعتماد الحقيقية — دون اتصال، حصة صفرية، إيجابيات كاذبة أقل. |
| **تحديد موقع اسم-المتغير ← الإسناد عبر AST للـ JS (JS AST locating variable-name → assignment)** | DonIsaac/keyhunter | تحليل JS إلى AST عبر oxc، وتحديد الموقع باسم المتغير (مثل OPENAI_API_KEY) ثم أخذ الإسناد، تمييزًا لسياق اسم المتغير عن القيم المجردة؛ مع تخطٍّ تلقائي لـ CDN/المكتبات — إيجابيات كاذبة أقل في مسح JS للويب. |
| **مرشّح لاحق بالتعلّم الآلي + معيار أداء عام (CredData) (ML post-filter + public benchmark (CredData))** | Samsung/CredSweeper | مُصنِّف خفيف TF→ONNX يُرشِّح لاحقًا نتائج regex؛ يأتي مع مجموعة بيانات معيار CredData العامة لتقييم استدعاء/دقة قابلين لإعادة الإنتاج. |

---

<a id="contributing"></a>
## 🙋 المساهمة

المساهمات مرحَّب بها! عند فتح PR، يُرجى توفير: اسم الأداة (مع رابط قفزة)، عدد النجوم، اللغة الأساسية، وصف بجملة واحدة، الترخيص، والإشارة إلى صلته بـ "كشف تسرّب مفاتيح API / مفاتيح LLM". إذا كان لها تقنية فريدة، أضفها إلى [ورقة غش الاقتراض التقني](#absorb).

<a id="license"></a>
## 📜 الترخيص

محتوى القائمة مُكرَّس للملكية العامة بموجب [CC0-1.0](https://creativecommons.org/publicdomain/zero/1.0/). تحتفظ كل أداة بترخيصها الخاص.


---

<a id="star-history"></a>
## ⭐ تاريخ النجوم

<sub>إذا ساعدتك هذه القائمة، يُرجى ترك ⭐ — فهذا يساعد الآخرين على اكتشافها.</sub>

<a href="https://star-history.com/#Lxcardoza993/awesome-api-key-leak-detection&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Lxcardoza993/awesome-api-key-leak-detection&type=Date" />
  </picture>
</a>

[⬆ العودة للأعلى](#awesome-api-key-leak-detection)
