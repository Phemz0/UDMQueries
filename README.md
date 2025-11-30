UDM Queries for Google Chronicle

A freely accessible collection of Unified Data Model (UDM) search queries designed for threat hunting, detection engineering, and security investigations within Google Chronicle (now Google Security Operations).

📂 Repository Structure

This repository is organized into three primary categories to help security teams quickly find the relevant logic for their hunt:

1. 🛡️ CVE Based Queries

Contains queries targeted at detecting specific Common Vulnerabilities and Exposures (CVEs). Use these when checking for exploitation attempts of known vulnerabilities.

Examples: Log4Shell, ProxyNotShell, Follina, CVE-2024-3400 (GlobalProtect), ScreenConnect, etc.

2. 🕵️ Hypothesis Based TH Queries

Contains queries derived from threat hunting hypotheses and behavioral patterns. These are designed to catch "unknown unknowns" or Living-off-the-Land (LotL) techniques where no specific CVE is involved.

Examples:

Suspicious certutil.exe or bitsadmin.exe downloads.

Lateral movement via WMI spawning shells.

Shadow Copy deletion (Ransomware precursors).

Unusual WHOAMI or localized reconnaissance.

3. 🔍 Standard Queries

Contains baseline and operational queries useful for general visibility and hygiene checks.

Examples:

GCP Service Account Key creations.

Azure AD conditional access policy changes.

AWS Root user activity.

General network scanning detection (Nmap/Masscan).

🚀 Usage

Running a Query in Google Chronicle

Select a Query: Navigate to the folder matching your use case and copy the raw UDM query text.

Navigate to UDM Search: Log in to your Google Chronicle tenant and open the UDM Search page.

Paste & Configure:

Paste the query into the search bar.

Adjust the Time Range (e.g., Last 24 Hours, Last 7 Days) depending on the scope of your investigation.

Run Search: Execute the query to view matching events.

Tips for Customization

Timestamps: UDM searches default to a specific window. Always verify your time range before running.

Field Filtering: If a query returns too much noise, consider adding exclusions for known good hosts or users:

... AND principal.hostname != "approved-scanner"


Case Sensitivity: Most UDM fields are case-sensitive. Use nocase modifiers where appropriate (e.g., target.process.command_line = /malicious/ nocase).

🤝 Contributing

Contributions are welcome! If you have a useful UDM query for a new CVE, a novel attack technique, or a cloud-specific threat (AWS/GCP/Azure), please submit a Pull Request.

Fork the repository.

Create a new branch (git checkout -b feature/NewQuery).

Add your query file to the appropriate folder.

Commit your changes.

Push to the branch and open a Pull Request.

📧 Contact & Support

If you have ideas for new queries, need access, or encounter errors with any existing searches, please open an Issue in this repository.