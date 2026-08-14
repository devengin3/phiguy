# phiguy 🛡️

<div align="center">

**because nobody wants to be the dev who leaked patient data.**

[![npm version](https://badge.fury.io/js/phiguy.svg)](https://badge.fury.io/js/phiguy)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequests.com)
[![HIPAA](https://img.shields.io/badge/HIPAA-compliant-blue.svg)](https://www.hhs.gov/hipaa)

```
██████╗ ██╗  ██╗██╗ ██████╗ ██╗   ██╗██╗   ██╗
██╔══██╗██║  ██║██║██╔════╝ ██║   ██║╚██╗ ██╔╝
██████╔╝███████║██║██║  ███╗██║   ██║ ╚████╔╝ 
██╔═══╝ ██╔══██║██║██║   ██║██║   ██║  ╚██╔╝  
██║     ██║  ██║██║╚██████╔╝╚██████╔╝   ██║   
╚═╝     ╚═╝  ╚═╝╚═╝ ╚═════╝  ╚═════╝   ╚═╝   
```

### `git commit clean.` ™️

[Install](#installation) • [Quick Start](#quick-start) • [How It Works](#how-it-works) • [Contributing](#contributing) • [Docs](#documentation)

</div>

---

## 🚨 Real Talk

One careless `git push` and suddenly you're in a conference room with lawyers explaining why Mrs. Henderson's social security number is now on GitHub.

**phiguy exists so that never happens to you.**

It's a lightweight, zero-config PHI detection tool that sits in your git pipeline like a silent bodyguard — scanning every single commit for protected health information before it ever touches your repo.

No drama. No breaches. No $1.9 million HIPAA fines.

Just clean code.

---

## 🔥 Why phiguy?

| Without phiguy | With phiguy |
|---|---|
| 😰 Manually reviewing code for PHI | 🤖 Automated scanning on every commit |
| 😱 One dev mistake = HIPAA violation | 🛡️ PHI blocked before it hits the repo |
| 😭 $100 - $50,000 PER violation | 😎 $0 in fines |
| 😩 No audit trail | 📜 Signed attestation on every clean commit |
| 🤞 Hoping nobody leaked patient data | ✅ Knowing nobody leaked patient data |

---

## 💀 What phiguy catches

phiguy detects all 18 HIPAA defined PHI identifiers including:

- 🏥 **Patient names** — first, last, and everything in between
- 🔢 **Social Security Numbers** — every format, every variation
- 📋 **Medical Record Numbers (MRN)** — no matter how they're formatted
- 📧 **Email addresses** — tied to health records or patient data
- 🎂 **Dates of birth** — in any format (MM/DD/YYYY, ISO 8601, you name it)
- 📞 **Phone numbers** — mobile, landline, fax (yes, fax)
- 🏠 **Physical addresses** — street, city, zip, the whole shebang
- 💳 **Insurance ID numbers** — every carrier, every format
- 🌐 **IP addresses** — that can be traced back to a patient
- 🧬 **Device identifiers** — serial numbers, MAC addresses
- 🔑 **Account numbers** — financial, medical, or otherwise
- 🌍 **Geographic data** — anything smaller than a state
- 📸 **Biometric identifiers** — fingerprints, voice prints, retinal scans
- 🖼️ **Full face photos** — and any comparable images

> **phiguy doesn't sleep. phiguy doesn't miss. phiguy doesn't care that it's 2am and you're tired and just want to push this hotfix.**

---

## ⚙️ How It Works

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   developer writes code                                 │
│           ↓                                             │
│   developer runs: git commit                            │
│           ↓                                             │
│   🛡️  phiguy intercepts the commit                      │
│           ↓                                             │
│   phiguy scans every line, every file, every change     │
│           ↓                                             │
│        ┌──┴──┐                                          │
│    PHI?│     │No PHI?                                   │
│        ↓     ↓                                          │
│      ❌ 🚫   ✅ 📜                                       │
│    BLOCKED  SIGNED ATTESTATION GENERATED                │
│             COMMIT APPROVED                             │
│             YOU SLEEP PEACEFULLY                        │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

phiguy uses advanced NLP and pattern recognition to detect PHI in:

- 📝 Code comments
- 🔤 Variable names and string literals
- 📄 Config files
- 📊 JSON, CSV, XML data files
- 📧 Log files
- 📑 Documentation and markdown files

---

## 📦 Installation

```bash
# npm
npm install phiguy --save-dev

# yarn
yarn add phiguy --dev

# pnpm
pnpm add phiguy --save-dev
```

---

## 🚀 Quick Start

### 1. Initialize phiguy in your project

```bash
npx phiguy init
```

### 2. That's it. Seriously.

phiguy automatically installs itself as a pre-commit hook. From this moment forward, every commit is scanned. Every clean commit gets a signed attestation. Every dirty commit gets blocked.

```bash
# Example output when PHI is detected:
🛡️  phiguy scanning commit...
❌  PHI DETECTED in src/patient-records.js (line 42)
    → Social Security Number pattern found: XXX-XX-XXXX
    → Commit BLOCKED.
    → Fix the violation and try again.
    → phiguy just saved your startup. You're welcome.

# Example output when commit is clean:
🛡️  phiguy scanning commit...
✅  No PHI detected.
📜  Signed attestation generated: [hash]
🚀  Commit approved. git commit clean.
```

---

## 📜 Signed Attestations

Every clean commit generates a cryptographically signed attestation record tied to the commit hash. This gives you:

- **Immutable audit trail** — prove your code was PHI-free at the time of commit
- **Compliance documentation** — show auditors exactly when and how PHI was checked
- **Chain of custody** — track every commit from dev to production
- **Peace of mind** — sleep at night knowing you're covered

---

## 🔧 Configuration

phiguy works out of the box with zero config. But if you want to customize:

```json
// .phiguy.json
{
  "sensitivity": "high",
  "excludePaths": ["test/fixtures", "mock-data"],
  "customPatterns": [],
  "attestation": {
    "enabled": true,
    "outputPath": ".phiguy/attestations"
  },
  "notifications": {
    "slack": false,
    "email": false
  }
}
```

---

## 🤝 Contributing

phiguy is open source and we welcome contributions from the community. Whether you're fixing bugs, adding features, or improving documentation, we'd love to have you on board.

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Read [CONTRIBUTING.md](CONTRIBUTING.md) for more details.

---

## 📊 HIPAA By The Numbers

> These numbers are why phiguy exists.

- 💰 **$1.9 million** — average cost of a healthcare data breach
- 📈 **$100 - $50,000** — HIPAA fine per violation
- 🔢 **55 million** — patient records breached in 2023 alone
- ⏱️ **280 days** — average time to identify and contain a healthcare breach
- 😱 **95%** — of healthcare organizations have experienced a data breach

---

## 🛣️ Roadmap

- [x] Pre-commit PHI scanning
- [x] Signed attestation generation
- [ ] IDE plugins (VS Code, JetBrains)
- [ ] CI/CD pipeline integration (GitHub Actions, Jenkins, CircleCI)
- [ ] Slack and email notifications
- [ ] GDPR and CCPA support
- [ ] Custom pattern library
- [ ] PHI risk scoring and analytics dashboard
- [ ] Enterprise SSO and team management

---

## 📄 License

MIT © [phiguy](https://github.com/devengin3/phiguy)

---

<div align="center">

**Built with ❤️ for healthcare developers who give a damn.**

⭐ Star this repo if phiguy saved your bacon ⭐

[Twitter](https://twitter.com/phiguy) • [Discord](https://discord.gg/phiguy) • [Product Hunt](https://producthunt.com/phiguy)

```
git commit clean. 🛡️
```

</div>
