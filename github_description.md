<h1 align="center">🛡️ VulnSentry Pro</h1>
<p align="center">
  <b>Enterprise-Grade, Open-Source Web Vulnerability Scanner</b><br>
  <a href="#">English</a> | <a href="#">中文</a>
</p>
<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-blue?style=flat-square&logo=python" />
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square" />
  <img src="https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey?style=flat-square" />
  <img src="https://img.shields.io/badge/OWASP%20Top%2010-Covered-success?style=flat-square" />
</p>

---

## 🚀 Why VulnSentry Pro?

**Stop paying $10,000/year for commercial scanners.**

VulnSentry Pro is a **fully open-source, enterprise-grade** web vulnerability scanner that rivals proprietary tools like AWVS, Nessus, and OpenVAS — at **zero cost**.

- ✅ **Real-time exploit payload updates** from CVE, Exploit-DB, and GitHub PoC repos
- ✅ **12+ vulnerability classes** covering OWASP Top 10 and beyond
- ✅ **Async high-performance engine** (aiohttp + asyncio, up to 20 concurrent threads)
- ✅ **Smart dual-mode crawler** with JavaScript rendering (Playwright) for SPAs
- ✅ **Modular architecture** — swap detectors, customize payloads, scale horizontally
- ✅ **Multi-format reporting** (Markdown / HTML / JSON) with auto-generated remediation advice

---

## 🔥 What It Detects

| Category | Detection Methods |
|---|---|
| **SQL Injection** | Error-based, Boolean Blind, Time-based Blind |
| **XSS** | Reflected, Stored, DOM-based |
| **RCE** | Command injection, Code execution, Reverse-shell validation |
| **File Inclusion** | LFI (`../../etc/passwd`), RFI, `php://filter` |
| **File Upload** | Extension bypass, Content-Type spoofing, WebShell upload |
| **SSRF** | Internal IP probing, DNS out-of-band, Cloud metadata APIs |
| **XXE** | External entity injection, File read via XML |
| **CSRF** | Missing token detection, Sensitive action probing |
| **Directory Traversal** | 2,000+ wordlist for backups, admin panels, source leaks |
| **Information Disclosure** | phpinfo, `.git` exposure, API keys, stack traces |
| **Weak Passwords** | Admin panels, SSH, FTP, MySQL — 1,000+ common passwords |
| **CVE Matching** | Struts2, ThinkPHP, Log4j, Spring4Shell, WordPress plugins |

---

## 🏗️ Architecture

```
Target Input → Smart Crawler (BFS/DFS + JS Render) 
    ↓
Live Payload Sync (CVE / Exploit-DB / GitHub PoC)
    ↓
Async Detection Engine (12+ Modular Detectors)
    ↓
External Validation (Webhook.site / VirusTotal / Shodan)
    ↓
Report Generation (Markdown / HTML / JSON + Remediation)
```

**Key Design Principles:**
- **Modular**: Every detector inherits `BaseDetector` — add your own in minutes
- **Async**: Built on `aiohttp` + `asyncio` for maximum throughput with WAF evasion
- **Self-Updating**: Payloads and CVE databases refresh automatically on launch
- **Offline-Fallback**: Local cache ensures scanning works even without internet

---

## ⚡ Quick Start

```bash
# Clone the repo
git clone https://github.com/yourname/vulnsentry-pro.git
cd vulnsentry-pro

# Install dependencies
pip install -r requirements.txt

# Run a single target scan
python scanner.py -u https://target.com

# Deep scan with JS rendering
python scanner.py -u https://target.com --deep

# Batch scan from file
python scanner.py -f targets.txt -t 10

# Specific modules only
python scanner.py -u https://target.com -m sqli,xss
```

---

## 📊 Sample Output

```
[2026-05-16 14:30:25] [Crawler]   Discovered 47 pages, 93 parameters, 12 forms
[2026-05-16 14:30:27] [SQLi]      [CRITICAL] /page?id=1 — Error-based injection confirmed
[2026-05-16 14:30:28] [XSS]       [HIGH]     /search?q= — Reflected XSS triggered
[2026-05-16 14:30:30] [CVE]       [CRITICAL] Apache Struts2 2.5.26 — CVE-2017-5638 RCE
[2026-05-16 14:30:35] [DirScan]   [HIGH]     /.git/config — Source code exposure
[2026-05-16 14:30:40] [SSRF]      [CRITICAL] 127.0.0.1:22 — Internal service reachable
[2026-05-16 14:30:45] [Report]    Scan complete: 6 Critical / 3 High / 2 Medium / 1 Low
```

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Core Language | Python 3.9+ |
| HTTP Engine | `aiohttp` (async) / `requests` (sync fallback) |
| Parser | `beautifulsoup4` + `lxml` |
| JS Rendering | `playwright` / `selenium` |
| Database | `sqlite3` (local scan storage) |
| Reporting | `jinja2` (HTML templates) |
| Concurrency | `asyncio` + `concurrent.futures` |

---

## ⚖️ Legal & Responsible Disclosure

**This tool is intended for authorized security testing only.**

- ✅ Systems you fully own
- ✅ Systems with explicit written authorization
- ✅ Legitimate penetration testing engagements

**Unauthorized scanning of systems you do not own is illegal.** Users assume all legal liability. We strongly recommend testing against local targets like [DVWA](https://github.com/digininja/DVWA) or [Vulhub](https://github.com/vulhub/vulhub) before production use.

---

## 📜 License

MIT License — free for personal and commercial use. Fork it, modify it, sell services built on it. **No restrictions.**

---

<p align="center">
  <b>Star ⭐ the repo if it helps you secure your assets.</b><br>
  <i>Built by security engineers, for security engineers.</i>
</p>
