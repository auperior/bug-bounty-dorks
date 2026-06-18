# 🐛 Bug Bounty Dorks Collection

> **A comprehensive Google Dorks collection for finding bug bounty programs, responsible disclosure policies, and vulnerability disclosure programs.**
>
> From **Noob to Advanced** — organized by skill level and targeting strategy.

---

## 📋 Table of Contents

- [Overview](#overview)
- [How to Use](#how-to-use)
- [Level 1: Noob](#level-1-noob)
- [Level 2: Intermediate](#level-2-intermediate)
- [Level 3: Advanced](#level-3-advanced)
- [Level 4: Regional & Language-Specific](#level-4-regional--language-specific)
- [Level 5: Education & Government](#level-5-education--government)
- [Level 6: Industry-Specific](#level-6-industry-specific)
- [Level 7: Red Team & Advanced Recon](#level-7-red-team--advanced-recon)
- [Level 8: Specialized & Niche](#level-8-specialized--niche)
- [Bonus: Automation & Tooling](#bonus-automation--tooling)
- [Ethical Guidelines](#ethical-guidelines)
- [Pro Tips](#pro-tips)
- [Contributing](#contributing)

---

## 🎯 Overview

This collection contains **500+ Google Dorks** specifically crafted to discover:

- ✅ Bug Bounty Programs (public & unlisted)
- ✅ Responsible Disclosure Policies
- ✅ Vulnerability Disclosure Programs (VDP)
- ✅ Security.txt files with contact info
- ✅ Self-hosted programs (not on major platforms)
- ✅ Regional/language-specific programs
- ✅ Industry-specific programs (finance, healthcare, SaaS, etc.)
- ✅ Education & Government programs

---

## 🚀 How to Use

### Basic Usage
1. Open [Google](https://www.google.com)
2. Copy any dork from `dorks.txt`
3. Paste in the search bar and hit Enter
4. Analyze results for bug bounty programs

### Advanced Usage
```bash
# Using with automation tools
cat dorks.txt | while read dork; do
    echo "Searching: $dork"
    # Add your automation logic here
done

# Using with GoBuster for endpoint enumeration
gobuster dir -u https://target.com -w bug-bounty-paths.txt

# Using with subfinder for subdomain enumeration
subfinder -d target.com -all | tee subdomains.txt
```

### Filtering Results
```
# Exclude major platforms to find self-hosted programs
"bug bounty" -site:hackerone.com -site:bugcrowd.com

# Filter by reward type
"responsible disclosure" intext:"$" OR intext:"€" OR intext:"BTC"

# Filter by region
site:*.de inurl:bug inurl:bounty
```

---

## 📚 Level 1: Noob

> **Perfect for beginners. Simple, easy-to-understand dorks.**

### What You'll Find
- Basic responsible disclosure pages
- Standard bug bounty programs
- Security.txt files
- Hall of Fame pages

### Example Dorks
```
inurl:/responsible-disclosure
inurl:/bug-bounty
inurl:security.txt
intext:"we offer a bounty"
"responsible disclosure" "hall of fame"
```

### Tips for Beginners
- Start with `inurl:/responsible-disclosure` — most common path
- Look for security.txt files — standard way to report
- Check Hall of Fame pages — shows active programs
- Always read the policy before testing

---

## 📚 Level 2: Intermediate

> **Targeted dorks with platform detection and reward filtering.**

### What You'll Find
- Unlisted programs on major platforms
- Self-hosted programs (not on HackerOne/Bugcrowd)
- Programs with specific reward types
- Well-known security files

### Example Dorks
```
"powered by bugcrowd" -site:bugcrowd.com
"submit vulnerability report" -site:hackerone.com -site:bugcrowd.com
inurl:/.well-known/security ext:txt -hackerone -bugcrowd -synack
inurl:"bug bounty" intext:"$" inurl:/security
```

### Key Concepts
- **Platform Detection**: Find programs using HackerOne/Bugcrowd but not listed publicly
- **Exclusion**: Use `-site:` to filter out major platforms
- **Reward Filtering**: Target programs with specific currencies

---

## 📚 Level 3: Advanced

> **Complex combinations, bypasses, and deep reconnaissance.**

### What You'll Find
- Hidden/obscure programs
- Advanced platform bypasses
- Security.txt with specific reward info
- Dutch-specific programs (responsibledisclosure.nl)

### Example Dorks
```
"submit vulnerability report" | "powered by bugcrowd" | "powered by hackerone"
"powered by yeswehack" OR "powered by federacy" OR "powered by intigriti"
inurl:/security.txt "mailto*" -github.com -wikipedia.org -portswigger.net
"CVSS score" AND "eligible for a reward" -hackerone -bugcrowd
```

### Advanced Techniques
- **Boolean Operators**: Use `AND`, `OR`, `|` for complex queries
- **File Type Filtering**: `ext:txt`, `ext:pdf`, `ext:md`
- **Advanced Exclusions**: Multiple `-site:` operators
- **Specific Keywords**: Target CVSS, PGP, mailto patterns

---

## 🌍 Level 4: Regional & Language-Specific

> **Target programs by country, TLD, or language.**

### Europe
```
site:*.nl intext:responsible disclosure reward
site:*.de inurl:bug inurl:bounty
site:*.fr intext:"bug bounty" OR "prime de sécurité"
site:*.dk inurl:/sikkerhed intext:dusør
site:*.no inurl:/sikkerhet intext:belønning
```

### Asia-Pacific
```
site:*.jp intext:"vulnerability report" intext:swag
site:*.in inurl:responsible disclosure
site:*.au responsible disclosure
```

### Americas
```
site:*.ca intext:"responsible disclosure" intext:reward
site:*.br responsible disclosure
```

### Why Regional?
- Less competition
- Different legal frameworks
- Language barriers = missed by others
- Local currency rewards

---

## 🎓 Level 5: Education & Government

> **Target universities, colleges, and government agencies.**

### Universities
```
site:*.edu "responsible disclosure" AND (reward OR swag OR bounty)
site:*.edu intext:"vulnerability disclosure policy" intext:hall_of_fame
site:*.ac.uk intext:bug bounty
```

### Government
```
site:*.gov* "vulnerability disclosure program" OR "bug bounty"
site:*.gov* filetype:pdf "vulnerability disclosure policy"
site:*.gov.uk intext:bug bounty
```

### Why These?
- Often have generous rewards
- High impact (public data)
- Less saturated
- Good for building reputation

---

## 🏢 Level 6: Industry-Specific

> **Target specific sectors for specialized programs.**

### Finance & Banking
```
site:*.bank intext:bug bounty
site:*.finance intext:bug bounty
site:*.crypto intext:bug bounty
```

### Healthcare
```
site:*.health intext:bug bounty
site:*.medical intext:bug bounty
intext:"HIPAA" "bug bounty"
```

### SaaS & Technology
```
site:*.io intext:bug bounty
site:*.cloud intext:bug bounty
site:*.ai intext:bug bounty
```

### Why Industry-Specific?
- Higher payouts (finance, healthcare)
- Specialized vulnerabilities
- Less competition in niche sectors
- Better understanding of business logic bugs

---

## 🔥 Level 7: Red Team & Advanced Recon

> **Expert-level dorks for deep reconnaissance.**

### Hidden Programs
```
inurl: private bugbountyprogram
inurl:/security ext:txt "contact" "reward" -github.com
site:*.*.* inurl:bug inurl:bounty
```

### API & Developer Portals
```
site:developers.*.* intext:bug bounty
site:api.*.* intext:security intext:reward
inurl:/api intext:bug bounty
```

### GitHub/GitLab
```
site:github.com "responsible disclosure" "reward"
site:github.com "bug bounty" "SECURITY.md"
```

### Job Boards
```
intext:"bug bounty" "security engineer" site:careers.*
intext:"vulnerability disclosure" "security team" site:jobs.*
```

### Advanced Boolean
```
("vulnerability disclosure program" OR "bug bounty program") AND (reward OR bounty OR swag)
("security researchers" OR "white hat") AND (reward OR bounty)
```

---

## 🎯 Level 8: Specialized & Niche

> **Master-level targeting for specific vulnerability types and technologies.**

### Mobile Apps
```
intext:"mobile app" "bug bounty"
intext:"iOS" "vulnerability disclosure"
intext:"Android" "bug bounty"
```

### Blockchain & Web3
```
intext:"blockchain" "bug bounty"
intext:"smart contract" "bug bounty"
intext:"DeFi" "vulnerability disclosure"
```

### IoT & Hardware
```
intext:"IoT" "bug bounty"
intext:"hardware" "vulnerability disclosure"
intext:"firmware" "bug bounty"
```

### Automotive
```
intext:"automotive" "bug bounty"
intext:"vehicle" "vulnerability disclosure"
```

---

## 🛠️ Bonus: Automation & Tooling

### Common Paths to Fuzz
```
/bug-bounty
/responsible-disclosure
/.well-known/security.txt
/security.txt
/vulnerability-disclosure-policy
/security-policy
/report-a-vulnerability
/security-researchers
/hall-of-fame
/security/bug-bounty
/legal/security
/trust/report-a-vulnerability
```

### Subdomain Enumeration
```bash
# Combine with subfinder, amass, assetfinder
subfinder -d target.com -all | tee subdomains.txt

# Common bug bounty subdomains:
# security.target.com
# bugbounty.target.com
# responsible-disclosure.target.com
# security-researchers.target.com
```

### Nuclei Templates
```bash
# Keywords for custom nuclei templates:
# "bug-bounty"
# "responsible-disclosure"
# "security.txt"
# "vulnerability-disclosure"
```

---

## ⚠️ Ethical Guidelines

> **Bug bounty is about making the internet safer, not personal gain.**

1. **ALWAYS** read and follow the program's scope and rules
2. **NEVER** test without explicit authorization
3. **DO NOT** access sensitive data beyond what's needed
4. **REPORT** findings responsibly through official channels
5. **ALLOW** reasonable time for patching before disclosure
6. **RESPECT** the company's decisions on rewards
7. **NEVER** extort or threaten for higher payouts
8. **DOCUMENT** your findings clearly and professionally
9. **STAY** within legal boundaries (CFAA, Computer Misuse Act, etc.)
10. **BE** patient and professional in all communications

---

## 💡 Pro Tips

### Tip 1: Combine Dorks
```
# Layer multiple operators
site:*.com inurl:/responsible-disclosure intext:"$" -site:hackerone.com
```

### Tip 2: Use Date Filters
```
# Find recently launched programs
"bug bounty" "launched" after:2025-01-01
```

### Tip 3: Monitor Changes
```
# Use Google Alerts for new programs
# Set up alerts for: "bug bounty program" OR "vulnerability disclosure"
```

### Tip 4: Cache Analysis
```
# Check cached versions for historical data
cache:target.com/responsible-disclosure
```

### Tip 5: Related Searches
```
# Find related programs
related:target.com bug bounty
```

### Tip 6: Image Search
```
# Find bug bounty swag/images
site:twitter.com "bug bounty" "swag"
```

### Tip 7: News Search
```
# Find recently announced programs
"launched bug bounty program" site:news.google.com
```

---

## 📊 Dork Statistics

| Level | Description | Count |
|-------|-------------|-------|
| Level 1 | Noob (Basic) | ~50 |
| Level 2 | Intermediate | ~80 |
| Level 3 | Advanced | ~100 |
| Level 4 | Regional | ~60 |
| Level 5 | Education & Gov | ~40 |
| Level 6 | Industry-Specific | ~50 |
| Level 7 | Red Team & Recon | ~80 |
| Level 8 | Specialized & Niche | ~40 |
| **Total** | | **~500+** |

---

## 🔗 Useful Resources

- [HackerOne Directory](https://hackerone.com/directory)
- [Bugcrowd Programs](https://bugcrowd.com/programs)
- [Disclose.io](https://disclose.io)
- [Open Bug Bounty](https://openbugbounty.org)
- [YesWeHack](https://yeswehack.com)
- [Intigriti](https://intigriti.com)
- [Synack](https://synack.com)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)

---

## 🤝 Contributing

Found a new dork? Want to improve existing ones?

1. Fork the repository
2. Add your dorks with comments
3. Submit a pull request
4. Include the target/purpose of the dork

---

## 📜 License

This collection is for educational and ethical security research purposes only.

**Use responsibly. Hack ethically. Stay legal.**

---

## 🙏 Credits

- Inspired by [sushiwushi/bug-bounty-dorks](https://github.com/sushiwushi/bug-bounty-dorks)
- Community contributions from bug bounty hunters worldwide
- Google Dorks documentation and research

---

> **"The best bug bounty hunter is not the one who finds the most bugs, but the one who makes the internet safer for everyone."**

---

*Last Updated: 2026-06-18*
