<div align="center">

# 🔎 Nmap Network Scanning & Enumeration

**A practical, step-by-step Nmap learning project using an authorized Metasploitable lab**

Build a repeatable workflow for host discovery, port scanning, service enumeration, OS detection, NSE scripts, firewall observations, and reporting.

![Nmap](https://img.shields.io/badge/Tool-Nmap-2C8EBB?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Kali%20Linux-557C94?style=for-the-badge)
![Lab](https://img.shields.io/badge/Lab-Metasploitable-orange?style=for-the-badge)
![Focus](https://img.shields.io/badge/Focus-Network%20Reconnaissance-success?style=for-the-badge)

</div>

---

## 📌 About This Project

This repository documents hands-on practice with **Nmap**, a network discovery and security auditing tool. Each numbered folder focuses on one stage of the scanning workflow and includes notes, commands, and screenshots where available.

The goal is to understand **what a command does, why it is used, and how to interpret its output**—not just copy commands.

> **Safety note:** Run scans only against systems you own or have explicit permission to test. The exercises in this repository are intended for an isolated, authorized lab such as Metasploitable.

## 🗺️ Project Contents

| # | Topic | What you will learn | Notes / Evidence |
|---|---|---|---|
| 01 | [Host Discovery](./01-Host-Discovery/README.md) | Identify live hosts and understand discovery results. | [View screenshot](./01-Host-Discovery/host-discovery.png) |
| 02 | [Port Scanning](./02-Port-Scanning/README.md) | Scan selected ports and interpret port states. | [View screenshot](./02-Port-Scanning/port-scanning.png) |
| 03 | [Service & Version Detection](./03-Service-Version-Detection/README.md) | Identify services and estimate software versions. | [Full scan image](./03-Service-Version-Detection/service-version-detection-full.png) · [Selected results](./03-Service-Version-Detection/service-version-detection-selected.png) |
| 04 | [OS Detection](./04-OS-Detection/README.md) | Understand Nmap OS guesses and their limitations. | [OS detection](./04-OS-Detection/os-detection.png) · [Guess output](./04-OS-Detection/os-detection-guess.png) |
| 05 | [NSE Script Scanning](./05-NSE-Script-Scanning/README.md) | Learn the Nmap Scripting Engine and review script output carefully. | [View screenshot](./05-NSE-Script-Scanning/nse-script-scanning.png) |
| 06 | [Firewall Detection](./06-Firewall-Detection/README.md) | Observe how filtering can affect scan results. | [View screenshot](./06-Firewall-Detection/firewall-detection.png) |
| 07 | [Final Scan Report](./07-Final-Scan-Report/README.md) | Bring findings together into a structured report. | [View final scan](./07-Final-Scan-Report/nmap-final-scan.png) |

## ⚡ Quick Start

### 1. Check that Nmap is installed

```bash
nmap --version
```

On Kali Linux, Nmap is commonly available already. If it is missing, update package metadata and install it using your system's package manager:

```bash
sudo apt update
sudo apt install nmap
```

### 2. Identify your authorized lab target

Use the IP address assigned to your own lab machine. Do not copy an example IP unless it matches your environment.

### 3. Start with a basic scan

Replace `<LAB-IP>` with the IP address of your authorized target:

```bash
nmap <LAB-IP>
```

This performs a basic scan of Nmap's default commonly used TCP ports. Results depend on network reachability and target configuration.

### 4. Save results for review

```bash
nmap -oN nmap-scan.txt <LAB-IP>
```

The output is written to `nmap-scan.txt` so you can compare findings and include evidence in a report.

## 🖼️ Screenshots — Preview Directly in This README

The images below are embedded directly from this repository so they appear on this page. Click an image to open the full-size version.

### Discovering hosts in the authorized lab

[![Host discovery results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/01-Host-Discovery/host-discovery.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/01-Host-Discovery/host-discovery.png)

### Scanning ports on the authorized lab target

[![Port scanning results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/02-Port-Scanning/port-scanning.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/02-Port-Scanning/port-scanning.png)

### Full service and version detection output

[![Service and version detection](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/03-Service-Version-Detection/service-version-detection-full.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/03-Service-Version-Detection/service-version-detection-full.png)

### Selected service detection output

[![Selected service results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/03-Service-Version-Detection/service-version-detection-selected.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/03-Service-Version-Detection/service-version-detection-selected.png)

### Nmap OS detection output

[![OS detection results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/04-OS-Detection/os-detection.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/04-OS-Detection/os-detection.png)

### Example OS guess output

[![OS guess results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/04-OS-Detection/os-detection-guess.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/04-OS-Detection/os-detection-guess.png)

### Nmap Scripting Engine lab output

[![NSE script scan results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/05-NSE-Script-Scanning/nse-script-scanning.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/05-NSE-Script-Scanning/nse-script-scanning.png)

### Firewall and filtering observations

[![Firewall detection results](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/06-Firewall-Detection/firewall-detection.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/06-Firewall-Detection/firewall-detection.png)

### Final Nmap scan evidence

[![Final scan report](https://raw.githubusercontent.com/SanathBansod/Nmap-Network-Scanning/main/07-Final-Scan-Report/nmap-final-scan.png)](https://github.com/SanathBansod/Nmap-Network-Scanning/blob/main/07-Final-Scan-Report/nmap-final-scan.png)

## 🧰 Useful Starter Commands

| Command | Purpose |
|---|---|
| `nmap -sn <LAB-NETWORK/CIDR>` | Host discovery without a port scan; use only on your authorized lab network. |
| `nmap -p 22,80,443 <LAB-IP>` | Check selected TCP ports. |
| `nmap -sV <LAB-IP>` | Probe open ports to identify services and versions. |
| `nmap -O <LAB-IP>` | Attempt operating-system detection; results may be uncertain and often require elevated privileges. |
| `nmap -oN scan.txt <LAB-IP>` | Save results in normal text format. |
| `nmap -oA lab-scan <LAB-IP>` | Save output in normal, XML, and grepable formats. |

**Tip:** Start with a low-impact scan, read the output, and choose the next scan based on a clear question. Aggressive options can generate more traffic and should be used only when appropriate for the lab.

## 🔄 Suggested Workflow

1. **Confirm scope** — record the target IP and the permission/scope for the lab.
2. **Discover hosts** — determine which lab systems appear reachable.
3. **Scan ports** — identify relevant open, closed, or filtered port states.
4. **Enumerate services** — investigate service names and version guesses.
5. **Check OS clues** — treat OS detection as an estimate, not a guarantee.
6. **Use scripts carefully** — read what each NSE script does before running it.
7. **Record evidence** — save command lines, timestamps, output, and screenshots.
8. **Report findings** — document observations, limitations, and recommended next steps.

## 📂 Repository Structure

```text
Nmap-Network-Scanning/
├── README.md
├── 01-Host-Discovery/
│   ├── README.md
│   └── host-discovery.png
├── 02-Port-Scanning/
│   ├── README.md
│   └── port-scanning.png
├── 03-Service-Version-Detection/
│   ├── README.md
│   ├── service-version-detection-full.png
│   └── service-version-detection-selected.png
├── 04-OS-Detection/
│   ├── README.md
│   ├── os-detection.png
│   └── os-detection-guess.png
├── 05-NSE-Script-Scanning/
│   ├── README.md
│   └── nse-script-scanning.png
├── 06-Firewall-Detection/
│   ├── README.md
│   └── firewall-detection.png
└── 07-Final-Scan-Report/
    ├── README.md
    └── nmap-final-scan.png
```

## 🧠 What This Project Demonstrates

- A structured network reconnaissance workflow.
- Familiarity with Nmap's core scan types and common options.
- Basic interpretation of host, port, service, and OS-detection results.
- Responsible use of NSE scripts in a controlled lab.
- Evidence collection and basic technical reporting.

This repository records lab practice; it should not be read as a claim of professional penetration-testing experience or as proof that every possible Nmap feature has been covered.

## ✅ Lab Checklist

- [ ] Complete host discovery and review the output.
- [ ] Compare a default port scan with a selected-port scan.
- [ ] Run service/version detection and note uncertain results.
- [ ] Attempt OS detection and explain its limitations.
- [ ] Read the documentation for any NSE script before running it.
- [ ] Save scan output and create a short findings report.

## 📚 Official References

- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [Nmap Official Download & Installation](https://nmap.org/download.html)
- [Nmap Scripting Engine (NSE)](https://nmap.org/book/nse.html)
- [Nmap Network Scanning Book](https://nmap.org/book/)

---

<div align="center">

**Built for learning • Practiced in an authorized lab • Findings documented clearly**

</div>
