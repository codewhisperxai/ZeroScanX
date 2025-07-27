**✅ ZeroScanX**


⚔️ What is ZeroScanX?

**ZeroScanX** is an advanced, real-world bug bounty tool designed to **scan, fingerprint, and exploit** websites and IPs vulnerable to known and recent CVEs. It detects server software, grabs related CVEs, and auto-downloads public exploits — even from GitHub and Exploit-DB.

Optional GPT module gives **AI-based exploitation tips**, payload ideas, or bypass strategies.

---

## 🧠 Key Features

- 🔍 **Technology Fingerprinting** via `whatweb`, `nmap`, and headers
- 📖 **CVE Auto-Mapping** to detected services or CMS
- ⚙️ **POC Downloader** (Exploit-DB + GitHub scraper)
- 🧪 **Proof-of-Concept Collector** (.py, .sh, etc)
- 🧠 **GPT-Based Suggestions** for exploitation *(optional)*
- 📄 **Auto HTML Report Generator**
- 💻 Works on **both Kali Linux and Termux**

---

## 📦 Installation

### 📲 Termux

```bash
pkg update && pkg upgrade -y
pkg install git python curl jq -y
pip install requests beautifulsoup4 rich
git clone https://github.com/codewhishperx/ZeroScanX
cd ZeroScanX
chmod +x zeroscan.sh
./zeroscan.sh
````

### 💻 Kali Linux

```bash
sudo apt update && sudo apt install whatweb nmap git curl python3-pip -y
pip3 install requests beautifulsoup4 rich
git clone https://github.com/codewhishperx/ZeroScanX
cd ZeroScanX
chmod +x zeroscan.sh
./zeroscan.sh
```

---

## 📂 File Structure

```
ZeroScanX/
├── zeroscan.sh                 # Main launcher script
├── modules/
│   ├── fingerprint.py          # Detect services/CMS
│   ├── cve_lookup.py           # Find CVEs via API
│   ├── exploit_grabber.py      # Download POCs from GitHub/EDB
│   ├── ai_tips.py              # AI suggestions via GPT (optional)
│   └── reporter.py             # HTML report generator
├── output/
│   └── target.com/
│       ├── fingerprint.txt
│       ├── cves.json
│       ├── exploits/
│       └── report.html
├── requirements.txt
├── LICENSE
└── README.md
```

---

## 🧪 Sample Run

```bash
./zeroscan.sh

Target Domain/IP: demo.vulnweb.com

[+] Running whatweb...
[+] Detected: Apache 2.4.49, PHP 7.4.3, WordPress 5.8

[!] CVEs Identified:
   - Apache 2.4.49 → CVE-2021-41773
   - WordPress 5.8 → CVE-2021-39209

[+] Searching for Exploits...
   ✔️ GitHub POC Found: CVE-2021-41773.py
   ✔️ Exploit-DB POC Found: 50383.sh

[+] Downloading Proof-of-Concepts...
   ✅ Saved to: output/demo.vulnweb.com/exploits/

[+] Generating HTML report...
   📁 output/demo.vulnweb.com/report.html

[✓] Scan Complete!
```

---

## 🧠 AI Exploitation Suggestions *(Optional)*

> 💬 Sample GPT output:

```
For CVE-2021-41773 (Apache):
- Use path traversal with crafted URL like: /cgi-bin/.%2e/.%2e/.%2e/.%2e/etc/passwd
- Attempt to chain with RCE if mod_cgi is enabled

For WordPress CVE-2021-39209:
- Use authenticated XSS injection on media uploader
```

> Requires an OpenAI API key to enable in `modules/ai_tips.py`

---

## 📜 License

MIT License – Use responsibly. Only scan targets you **own or are authorized** to test. The author is not responsible for misuse.

---

## 🧩 Credits

* Developed by **Code Whishper X**
* APIs used: `cve.circl.lu`, `NVD`, `Exploit-DB`, `GitHub`
* Inspired by tools like `whatweb`, `nmap`, and `wpscan`

---

## 🚀 GitHub Tags (for Discoverability)

```
termux, kali-linux, bug-bounty, exploit-finder, CVE scanner, zero-day, ethical hacking, red teaming, OSINT, recon
```

---

## 🌐 Connect

🔗 Visit: [codewhishperx.com](https://codewhishperx.com)
📧 Email: [contact@codewhishperx.com](mailto:contact@codewhishperx.com)
💬 Telegram: @codewhishperx
📌 GitHub: github.com/codewhishperx
