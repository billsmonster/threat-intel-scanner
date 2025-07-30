
 Threat Intelligence Scanner

**Scan IPs and domains for known threats using the AlienVault OTX API — with local caching, geolocation, detailed reports, and rich terminal output.**

-
The **Threat Intelligence Scanner** is a Python-based CLI tool that queries the [AlienVault OTX](https://otx.alienvault.com/) threat intelligence platform to check whether IP addresses or domains are associated with known malicious activity.

Key features include:

*  Real-time threat analysis from AlienVault
*  Geolocation enrichment using ip-api.com
*  Caching with SQLite to reduce redundant API calls
*  Visual bar charts of threat scores (via `matplotlib`)
*  Exports to CSV, JSON, and Markdown formats
* 🖥 Clean, styled terminal output with `rich`

---

## 📸 Screenshots

**Welcome Banner & Progress Bar**

```
===============================
  Threat Intelligence Scanner
  Powered by AlienVault OTX
===============================
```

**Summary Table Output**

```
+-------------+--------+----------+----------+
| Indicator   | Score  | Level    | Country  |
+-------------+--------+----------+----------+
| 8.8.8.8     | 70.0   | High     | US       |
| 1.1.1.1     | 10.0   | Low      | AU       |
+-------------+--------+----------+----------+
```

---

 Features

 Query OTX for IP/domain threat intelligence
 Normalize and score threat levels (Critical, High, Medium, Low)
 Cache results with timestamped SQLite DB
 Enrich IPs with geolocation (country, region, city, ISP)
 Export to `.csv`, `.json`, and `.md` report formats
 Plot threat score bar chart
 Styled console output using `rich`

---

## 🛠️ Installation

1. **Clone the repo**

   ```bash
   git clone https://github.com/yourusername/threat-intel-scanner.git
   cd threat-intel-scanner
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Set your OTX API key**

   * Create a `.env` file in the root directory with this content:

     ```
     OTX_API_KEY=your_otx_api_key_here
     ```

---

 Usage

```bash
python threat_scanner.py
```

### Output Files

* `threat_report.csv` – Structured CSV for Excel/Sheets
* `threat_log.json` – Raw JSON logs for automation
* `threat_report.md` – Markdown summary for GitHub/reporting

---

 Configuration

Edit the `INDICATORS` list in the script to add your IPs or domains:

```python
INDICATORS = ["8.8.8.8", "1.1.1.1", "example.com"]
```

---
 Threat Scoring System

| Score Range | Level    |
| ----------- | -------- |
| 80–100      | Critical |
| 50–79       | High     |
| 20–49       | Medium   |
| 0–19        | Low      |

Threat scores are computed based on tags and pulse count.

Sample Use Cases

* SOC teams scanning IOCs from incident reports
* Students learning threat hunting and API integration
* Red team analysts building custom tooling

  Requirements

* Python 3.7+
* Modules:

  * `requests`, `sqlite3`, `matplotlib`, `rich`, `dotenv`

Disclaimer

> This tool is for **educational and professional use** only. Please do not use it to scan IPs or domains without permission. Respect privacy laws and organizational policies.

 🧑‍💻 Author

**Derek Lenz**
Cybersecurity enthusiast & threat hunter


 Contributions

Pull requests, issues, and forks are welcome!
If this tool helped you, consider giving it a ⭐️ on GitHub.

