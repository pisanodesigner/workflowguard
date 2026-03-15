# 🛡️ WorkflowGuard

**Free security scanner for n8n, Make & Zapier automation workflows**

Detect hardcoded credentials, exposed webhooks, and compliance vulnerabilities before auditors do.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

🔗 **[Try Live Demo](https://pisanodesigner.github.io/workflowguard/workflowguard-poc.html)** • 📖 **[Full Documentation](https://pisanodesigner.com/projects/workflowguard)**

---

## 📊 The Problem

- **79%** of companies fail their first PCI DSS audit (Source: Verizon)
- **89%** of HIPAA entities fail to document adequate compliance (Source: HHS-OCR)
- **Most failures** involve exposed credentials in automation workflows

Your n8n, Make, or Zapier workflows may contain:
- ❌ Hardcoded AWS keys exposing your entire infrastructure
- ❌ Stripe API keys allowing unauthorized payment processing
- ❌ Unauthenticated webhooks anyone can trigger
- ❌ Database credentials in plaintext
- ❌ OAuth tokens that never expire

**WorkflowGuard finds them before auditors do.**

---

## ✨ Features

- 🔍 **Pattern-Based Detection** - Scans for 10+ credential types
- ⚡ **Platform-Specific Checks** - n8n, Make, and Zapier vulnerabilities
- 🔒 **100% Private** - Runs entirely in your browser, no data sent to servers
- 📊 **Security Score** - 0-100 rating with severity levels
- 💡 **Remediation Guidance** - Step-by-step fix instructions
- 📥 **Downloadable Reports** - Export results for compliance documentation

---

## 🚀 Quick Start

### Option 1: Use Online (Recommended)

1. Visit **[WorkflowGuard POC](https://pisanodesigner.github.io/workflowguard/workflowguard-poc.html)**
2. Export your workflow as JSON from n8n/Make/Zapier
3. Drag & drop the file or click to upload
4. Get instant security scan results

### Option 2: Run Locally

```bash
# Clone the repository
git clone https://github.com/pisanodesigner/workflowguard.git

# Open the HTML file in your browser
cd workflowguard
open workflowguard-poc.html  # macOS
# or
start workflowguard-poc.html  # Windows
# or
xdg-open workflowguard-poc.html  # Linux
```

No dependencies. No installation. Just open the HTML file.

---

## 🔍 What WorkflowGuard Detects

### Credential Types

| Type | Pattern | Severity |
|------|---------|----------|
| AWS Access Keys | `AKIA[0-9A-Z]{16}` | Critical |
| AWS Secret Keys | 40-character secrets | Critical |
| Stripe API Keys | `sk_live_*`, `sk_test_*` | Critical |
| OpenAI Keys | `sk-*` (48 chars) | Critical |
| GitHub Tokens | `ghp_*` | Critical |
| Slack Tokens | `xox*-*` | High |
| Private Keys | RSA/DSA private keys | Critical |
| Generic API Keys | Common patterns | High |
| Hardcoded Passwords | `password=`, `pwd=` | High |

### Platform-Specific Vulnerabilities

**n8n:**
- Unauthenticated webhook nodes
- Credentials in Code/Function nodes
- Exposed environment variables

**Make (Integromat):**
- Exposed connection tokens
- Plaintext authentication

**Zapier:**
- Authentication in plaintext
- Exposed auth configurations

---

## 📖 How to Export Workflows

### n8n
1. Open your workflow
2. Click the three-dot menu (⋮)
3. Select "Download"
4. Save the `.json` file

### Make (Integromat)
1. Open your scenario
2. Click the three-dot menu (⋮)
3. Select "Export Blueprint"
4. Save the `.json` file

### Zapier
1. Open your Zap
2. Click "Settings" tab
3. Scroll to "Advanced"
4. Click "Export Zap"
5. Save the `.txt` file (rename to `.json`)

---

## 🛠️ How It Works

WorkflowGuard uses **pattern-based detection** with regex patterns to identify:

1. **Known credential formats** (AWS keys, API tokens, etc.)
2. **Platform-specific misconfigurations** (unauthenticated webhooks)
3. **Common security anti-patterns** (hardcoded secrets)

### Privacy-First Design

- ✅ **No backend** - Pure client-side JavaScript
- ✅ **No data transmission** - Your workflow never leaves your computer
- ✅ **No tracking** - No analytics, cookies, or logging
- ✅ **No storage** - Nothing saved to disk

You can verify this by inspecting the source code or running it offline.

---

## 🎯 Use Cases

### For Developers
- Pre-commit security checks
- Code review assistance
- Learning secure automation patterns

### For Security Teams
- Audit preparation
- Compliance documentation
- Vulnerability assessment

### For Compliance Professionals
- SOC 2 evidence collection
- ISO 27001 gap analysis
- PCI DSS pre-audit scanning
- HIPAA compliance validation

---

## 📊 Example Output

```
Security Score: 45/100

Findings:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
❌ CRITICAL - AWS Access Key Detected
   Found: AKIA************
   Location: HTTP Request Node
   Remediation: Move to credential vault

⚠️ HIGH - Unauthenticated Webhook Found
   Node: Webhook #2
   Remediation: Enable Basic Auth or Header Auth

🔵 MEDIUM - Possible API Key in Code Node
   Review Code Node #5 for hardcoded credentials
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 🚀 WorkflowGuard Pro (Coming Soon)

This POC provides pattern-based scanning. **WorkflowGuard Pro** adds:

- 🤖 **AI-Powered Deep Analysis** - Contextual vulnerability detection
- 🔄 **Continuous Monitoring** - Auto-scan via webhooks
- 📈 **Scan History & Dashboards** - Track security over time
- 👥 **Team Collaboration** - Shared workspaces
- 📋 **Compliance Reports** - SOC 2, ISO 27001, PCI DSS, HIPAA
- 🔗 **GitHub Integration** - Automated CI/CD scanning
- 🎨 **White-Label Reports** - Custom branding for MSPs
- 🔌 **API Access** - Programmatic scanning

**[Join the waitlist](https://pisanodesigner.com/projects/workflowguard)** for early access and lifetime discount.

---

## 🧑‍💻 Contributing

Contributions are welcome! Here's how you can help:

### Add New Detection Patterns

Found a credential type we're missing? Submit a PR:

1. Fork the repository
2. Add pattern to `PATTERNS` object in `workflowguard-poc.html`
3. Test with sample workflow
4. Submit pull request

### Report Issues

Found a bug or false positive? [Open an issue](https://github.com/pisanodesigner/workflowguard/issues).

### Suggest Features

Have an idea? [Start a discussion](https://github.com/pisanodesigner/workflowguard/discussions).

---

## 👤 About the Author

**Radu Pisano** • [Pisano Designer](https://pisanodesigner.com)

- 🎓 **CISSP** - Certified Information Systems Security Professional
- 🔍 **CFE** - Certified Fraud Examiner
- 🛡️ **CAISP** - Certified AI Security Professional
- 🏛️ **16+ Years** - Fraud investigator

Built WorkflowGuard after seeing companies repeatedly fail audits due to exposed credentials in automation workflows—a gap that existing security tools don't address.

---

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

**You are free to:**
- ✅ Use commercially
- ✅ Modify
- ✅ Distribute
- ✅ Use privately

**With attribution** - Please keep the copyright notice and link back to this repository.

---

## 🔗 Links

- **🌐 Website**: [pisanodesigner.com/projects/workflowguard](https://pisanodesigner.com/projects/workflowguard)
- **🚀 Live Demo**: [pisanodesigner.github.io/workflowguard-poc](https://pisanodesigner.github.io/workflowguard/workflowguard-poc.html)
- **💼 Consulting**: [pisanodesigner.com](https://pisanodesigner.com)
- **📧 Contact**: [Contact Form](mailto:radu@pisanodesigner.com)

---

## ⚠️ Disclaimer

WorkflowGuard is a security scanning tool, not a security audit. It helps identify common vulnerabilities but does not guarantee complete security or compliance. 

**For compliance certification (SOC 2, ISO 27001, etc.), you still need an independent third-party auditor.**

WorkflowGuard provides:
- ✅ Pre-audit gap analysis
- ✅ Evidence collection
- ✅ Vulnerability identification
- ❌ NOT certification
- ❌ NOT legal compliance guarantee

Always consult with qualified security professionals and auditors for compliance requirements.

---

## 📈 Stats

![GitHub stars](https://img.shields.io/github/stars/pisanodesigner/workflowguard?style=social)
![GitHub forks](https://img.shields.io/github/forks/pisanodesigner/workflowguard?style=social)

---

## 🙏 Acknowledgments

- Inspired by the n8n, Make, and Zapier communities
- Pattern detection based on common security research
- Built with feedback from compliance professionals

---

**Made with 🛡️ by security professionals, for automation engineers.**

**[⭐ Star this repo](https://github.com/pisanodesigner/workflowguard)** if you find it useful!
