# 🕵️ RKHUNTER LIVE — Malware Detection Training Platform

![alt text](Screenshots/RKHUNTER_Logo.png)

![RKHUNTER LIVE](https://img.shields.io/badge/RKHUNTER_LIVE-Malware_Detection_Training-ffb300?style=for-the-badge&logo=virustotal&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Linux Security](https://img.shields.io/badge/Linux_Security-Rootkit_Hunting-f44336?style=for-the-badge&logo=linux&logoColor=white)

<p align="center">
  <img src="https://img.shields.io/badge/STATUS-LIVE-ffb300?style=for-the-badge&labelColor=0a0c14" />
  <img src="https://img.shields.io/badge/ROOTKIT_FAMILIES-6-00e5ff?style=for-the-badge&labelColor=0a0c14" />
  <img src="https://img.shields.io/badge/DETECTION_METHODS-6-00e676?style=for-the-badge&labelColor=0a0c14" />
  <img src="https://img.shields.io/badge/FORENSIC_SANDBOX-ACTIVE-f44336?style=for-the-badge&labelColor=0a0c14" />
</p>

---

### Overview
This project is a comprehensive malware detection training platform that simulates real-world rootkit hunting scenarios. It provides hands-on experience with detection tools, forensic analysis, and threat intelligence through interactive modules.

## ✨ Key Features

### 🛡️ **6 Interactive Training Modules**

| Module                            | Focus               | Description                                                                |
| --------------------------------- | ------------------- | -------------------------------------------------------------------------- |
| **01 — Live Scanner**      | Tool Simulation     | Run rkhunter, chkrootkit, AIDE, and Lynis against 5 staged system profiles |
| **02 — Detection Methods** | Technique Education | 6 core detection techniques with live terminal demos                       |
| **03 — Results Analyzer**  | Analyst Training    | Classify 8 scan findings as real threats or false positives                |
| **04 — Rootkit Families**  | Threat Intelligence | Deep dives into 6 rootkit families with technical specifications           |
| **05 — Hunt Missions**     | Forensic Exercises  | 6 investigation scenarios with command-line challenges                     |
| **06 — Knowledge Quiz**    | Assessment          | 12-question quiz with detailed forensic explanations                       |

---

## 🖥️ **Module 01: Live Scanner**

### **5 System Profiles** ⚙️

| Profile                    | Description                                  | Threat Level |
| -------------------------- | -------------------------------------------- | ------------ |
| **Clean System**     | No threats, normal operation                 | 🟢 Clean     |
| **Kernel Rootkit**   | Adore-ng LKM with hidden processes/modules   | 🔴 Critical  |
| **Bootkit**          | MBR/Grub compromised, boot-level persistence | 🔴 Critical  |
| **Userland Rootkit** | t0rn-style trojaned binaries                 | 🟡 High      |
| **Multi-Threat**     | Multiple concurrent infections               | 🔴 Critical  |

### **4 Security Tools** 🛠️

| Tool                 | Description                             | Detection Focus                                   |
| -------------------- | --------------------------------------- | ------------------------------------------------- |
| **rkhunter**   | Rootkit Hunter — comprehensive scanner | File hashes, rootkit signatures, system anomalies |
| **chkrootkit** | Lightweight rootkit checker             | Binary integrity, trojan detection                |
| **AIDE**       | File integrity monitoring               | Hash baseline comparison                          |
| **Lynis**      | Security auditing                       | Configuration hardening                           |

![alt text](<Screenshots/Live Scanner Terminal.png>)

### **Scanner Features** 📊

- **Realistic terminal output** with color-coded warnings
- **Live progress bar** with phase tracking
- **Result statistics** (OK/Warning/Critical/Error)
- **System information panel** with OS/kernel details
- **Tool version display** (rkhunter 1.4.6, chkrootkit 0.55, etc.)

### **Sample Detection Output**

```
[14:22:47] Checking for Adore-ng rootkit         [ FOUND ]
[14:22:48]   Comparing lsmod with /proc/modules...
[14:22:48]   lsmod: 124 modules
[14:22:48]   /proc/modules: 127 modules *** DISCREPANCY ***
[14:22:49]   Hidden module(s) found: kbdus, hide_module
[14:22:50]   /bin/ps: MD5 MISMATCH — trojaned
```

---

## 🔬 **Module 02: Detection Methods**

### **6 Core Detection Techniques** 🧪

| #  | Method                                  | Type                  | Description                                        |
| -- | --------------------------------------- | --------------------- | -------------------------------------------------- |
| 01 | **Hash / Signature Verification** | Static Analysis       | Compare MD5/SHA256 against known-good values       |
| 02 | **Syscall Discrepancy Detection** | Behavioral Analysis   | Compare ps vs /proc to find hidden processes       |
| 03 | **MBR / Bootloader Integrity**    | Boot-Level Analysis   | Direct disk reads to detect bootkit modifications  |
| 04 | **Hidden Module Detection**       | Kernel-Level Analysis | Compare lsmod vs /proc/modules for hidden LKMs     |
| 05 | **File System Anomaly Scanning**  | Filesystem Analysis   | Hidden directories, SUID binaries, suspicious /dev |
| 06 | **Network Backdoor Detection**    | Network Analysis      | Compare netstat vs nmap for hidden ports           |

### **Interactive Demos** 🎮

Each method includes a **click-to-expand** live terminal demo showing:

- Command syntax
- Expected output vs suspicious output
- Critical findings highlighted in red
- Explanatory notes

![alt text](<Screenshots/Detection Methods Lab.png>)

---

## 📋 **Module 03: Results Analyzer**

### **8 Forensic Findings** 🔍

| ID | Finding                                        | Severity    | Classification Task                    |
| -- | ---------------------------------------------- | ----------- | -------------------------------------- |
| 00 | `/bin/ps — MD5 Hash Mismatch`               | 🔴 Critical | Real threat vs false positive          |
| 01 | `SSH Protocol v1 Enabled`                    | 🟡 Warning  | Configuration issue vs compromise      |
| 02 | `Hidden Directory in /lib/modules`           | 🔴 Critical | Rootkit staging vs legitimate cache    |
| 03 | `Preloaded Library: libaudit.so`             | 🟡 Warning  | LD_PRELOAD rootkit vs legitimate audit |
| 04 | `Listening Port 4444 — Hidden from netstat` | 🔴 Critical | Backdoor vs legitimate service         |
| 05 | `AIDE: /etc/cron.d/sysstat modified`         | 🔵 Info     | Persistence vs legitimate update       |
| 06 | `/etc/sudoers — Unauthorized Entry`         | 🔴 Critical | Privilege escalation backdoor          |
| 07 | `World-Writable /tmp Directory`              | 🟡 Warning  | Misconfiguration vs normal permissions |

### **Analyst Features** 👨‍💻

- **Click any finding** to load into analyzer panel
- **Two-choice classification** (Threat / False Positive)
- **Detailed feedback** explaining the correct answer
- **Score tracking** (X/8 correct)
- **Color-coded results** in findings list
- **Reset capability** for repeated practice

![alt text](<Screenshots/Scan Results Analyzer.png>)

---

## 🦠 **Module 04: Rootkit Families**

### **6 Rootkit Types** 🧬

| Family                            | Type             | Risk  | Color         | Real-World Examples                           |
| --------------------------------- | ---------------- | ----- | ------------- | --------------------------------------------- |
| **LKM Kernel Rootkit**      | Kernel-Level     | 10/10 | 🔴`#f44336` | Adore-ng, Reptile, Azazel, Necurs             |
| **Bootkit**                 | Boot-Level       | 10/10 | 🟠`#ff6f00` | LoJax, TDL-4, MosaicRegressor, CosmicStrand   |
| **Userland Rootkit**        | User-Level       | 7/10  | 🟡`#ffb300` | t0rn v8, Linux.Backdoor.Gates, Umbreon, Jynx2 |
| **Memory-Resident Rootkit** | Memory-Only      | 9/10  | 🔵`#00e5ff` | Poweliks, Frodo, Turla Carbon, GhostScript    |
| **Firmware Rootkit**        | Firmware-Level   | 10/10 | 🟣`#e040fb` | Equation Group HDD, LoJax UEFI, iLOBleed      |
| **Virtual Machine Rootkit** | Hypervisor-Level | 8/10  | 🔵`#448aff` | Blue Pill, SubVirt, VBootkit, Cloudburst      |

### **Family Deep Dives** 📚

Each family includes:

- **Technical description** and operation layer
- **Detection methods** specific to the family
- **Indicators of Compromise (IOCs)** to identify
- **Persistence mechanisms** used by attackers
- **rkhunter sample output** showing detection
- **Real-world examples** with year and impact
- **Quick-run button** to launch scanner with matching profile

### **Sample Real-World Cases** 💼

- **LoJax (2018)** — First UEFI rootkit used in wild by APT28, survives disk replacement
- **Equation Group HDD (2015)** — NSA-linked group implanted HDD firmware, surviving full wipe
- **TDL-4 (2010)** — Infected 4.5M+ machines with MBR bootkit
- **Reptile (2018+)** — Modern LKM rootkit with port-knocking backdoor

![alt text](<Screenshots/Rootkit Family Catalog.png>)

---

## 🎯 **Module 05: Hunt Missions**

### **6 Investigation Scenarios** 🕵️

| #  | Mission Type                     | Title                         | Challenge                            |
| -- | -------------------------------- | ----------------------------- | ------------------------------------ |
| 00 | **Process Analysis**       | Ghost Processes Investigation | Find processes hidden from ps        |
| 01 | **Binary Verification**    | Trojaned Binary Hunt          | Identify compromised system binaries |
| 02 | **Network Forensics**      | Hidden Backdoor Detection     | Detect port hidden from netstat      |
| 03 | **Kernel Module Analysis** | Hidden Module Investigation   | Find LKMs hidden from lsmod          |
| 04 | **Persistence Analysis**   | Cron Backdoor Investigation   | Identify malicious cron persistence  |
| 05 | **MBR Integrity**          | Boot Sector Compromise        | Detect bootkit via MBR hash mismatch |

### **Mission Features** 🎮

- **Realistic terminal output** with investigation data
- **Suggested commands** to guide investigation
- **Multiple-choice question** testing forensic conclusion
- **Detailed feedback** explaining correct forensic procedure
- **Progress tracking** (X/6 missions completed)

### **Sample Mission Terminal**

```
$ for pid in $(ls /proc | grep -E '^[0-9]+$'); do 
    if ! ps -p $pid > /dev/null 2>&1; then 
      echo "Hidden PID: $pid ($(cat /proc/$pid/cmdline))"
    fi
  done
Hidden PID: 1247 (/usr/sbin/.backdoor --port 4444)
Hidden PID: 1248 (/tmp/.snd -c 185.220.x.x:8080)
Hidden PID: 3341 (nc -lvp 31337)
```

![alt text](<Screenshots/Hunt Missions.png>)

---

## 📝 **Module 06: Knowledge Quiz**

### **12 Comprehensive Questions** 📊

| #  | Topic                          |
| -- | ------------------------------ |
| 01 | rkhunter vs Traditional AV     |
| 02 | Process Discrepancy Detection  |
| 03 | MBR Integrity Checking         |
| 04 | Evidence Preservation Priority |
| 05 | LKM Rootkit Dangers            |
| 06 | Linux Memory Forensics Tools   |
| 07 | Conflicting Tool Results       |
| 08 | Hidden Port Detection          |
| 09 | Firmware Rootkit Persistence   |
| 10 | AIDE Purpose and Function      |
| 11 | Production Server Remediation  |
| 12 | rkhunter Update Commands       |

### **Quiz Features** ✅

- **Progressive tracking** with progress bar
- **Score display** (X/12 correct)
- **Immediate feedback** with detailed explanations
- **Color-coded results** (✅ correct / ❌ incorrect)
- **Letter-based selection** (A/B/C/D)

---

## 🎨 **Design & Aesthetics**

### **Forensic Sandbox Aesthetic** 🔬

- **Dark background** (`#0a0c14`) — professional forensic lab feel
- **Amber accents** (`#ffb300`) for warnings and critical findings
- **Red highlights** (`#f44336`) for critical threats
- **Green success** (`#00e676`) for clean systems
- **Cyan information** (`#00e5ff`) for detection methods
- **Scanline overlay** for terminal authenticity
- **Grid background** for technical depth

### **Typography** ✍️

- **IBM Plex Mono** — Terminal output, command syntax
- **Rajdhani** — Section headers, risk scores, badges
- **Space Mono** — File paths, IP addresses, technical details

### **Visual Elements** 🖼️

- **Terminal windows** with title bars and dots
- **Progress bars** with animated filling
- **Color-coded severity indicators** (🟢/🟡/🔴)
- **Result badges** with classification status
- **Family cards** with risk scores and real-world examples
- **Mission status indicators** (NEW/SOLVED/FAILED)

---

## 🛠️ **Technical Implementation**

### **Architecture**

```
┌─────────────────────────────────────┐
│      RKHUNTER LIVE Platform          │
├─────────────────────────────────────┤
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 1: Live Scanner     │   │
│  │   • 5 profiles × 4 tools     │   │
│  │   • Real-time output         │   │
│  │   • Progress tracking        │   │
│  │   • Result statistics        │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 2: Methods          │   │
│  │   • 6 detection techniques   │   │
│  │   • Interactive demos       │   │
│  │   • Expandable terminal     │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 3: Analyzer         │   │
│  │   • 8 findings              │   │
│  │   • Classification engine   │   │
│  │   • Score tracking          │   │
│  │   • Detailed feedback       │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 4: Families         │   │
│  │   • 6 rootkit types         │   │
│  │   • Deep-dive overlays      │   │
│  │   • Real-world examples     │   │
│  │   • Detection methods       │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 5: Hunt Missions   │   │
│  │   • 6 scenarios            │   │
│  │   • Command suggestions    │   │
│  │   • Decision trees         │   │
│  │   • Progress tracking      │   │
│  └─────────────────────────────┘   │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   Module 6: Quiz            │   │
│  │   • 12 questions            │   │
│  │   • Progress bar            │   │
│  │   • Detailed explanations   │   │
│  └─────────────────────────────┘   │
└─────────────────────────────────────┘
```

### **Key Functions**

```javascript
// Module 1: Live Scanner
startScan()          // Run selected tool against profile
stopScan()           // Interrupt running scan
clearScan()          // Reset terminal and stats
addTermLine(type, text) // Add line to terminal with formatting

// Module 2: Detection Methods
toggleDemo(idx)      // Expand/collapse method demo

// Module 3: Results Analyzer
loadAnalyzerItem(idx) // Load finding into analyzer panel
checkAz(idx)         // Submit analyst classification
updateAzScore()      // Update score display
resetAnalyzer()      // Reset all classifications

// Module 4: Rootkit Families
openFamilyOverlay(id) // Open detailed family modal
closeFamilyOverlay()  // Close modal

// Module 5: Hunt Missions
loadMission(idx)     // Load mission into display
checkHunt(mIdx)      // Submit mission decision
updateHuntScore()    // Update mission progress
resetHunt()          // Reset all missions

// Module 6: Quiz
checkQz(qi)          // Submit quiz answer
updateQuizProgress() // Update progress bar and score
```

---

## 📊 **Content Breakdown**

| Module                      | Items                                        | Interactions                             | Learning Outcomes                               |
| --------------------------- | -------------------------------------------- | ---------------------------------------- | ----------------------------------------------- |
| **Live Scanner**      | 5 profiles × 4 tools = 20 scenarios         | Profile/tool selection, scan execution   | Recognize rootkit detection tool outputs        |
| **Detection Methods** | 6 techniques                                 | Demo expansion                           | Understand HOW each detection method works      |
| **Results Analyzer**  | 8 findings × 2 choices = 16 scenarios       | Classification, feedback                 | Distinguish real threats from false positives   |
| **Rootkit Families**  | 6 families × 6 sections = 36 content blocks | Card clicks, modal navigation            | Know 6 rootkit types by behavior and indicators |
| **Hunt Missions**     | 6 scenarios × 4 choices = 24 decisions      | Command suggestions, decision submission | Apply forensic methodology to real scenarios    |
| **Knowledge Quiz**    | 12 questions × 4 choices = 48 options       | Answer selection, submission             | Test and reinforce comprehensive knowledge      |

---

## 🎥 **Video Demo Script** (45-60 seconds)

| Time | Scene    | Action                                                |
| ---- | -------- | ----------------------------------------------------- |
| 0:00 | Header   | Show amber header with live indicator                 |
| 0:05 | Module 1 | Select "Kernel Rootkit" + "rkhunter" → Run scan      |
| 0:10 | Module 1 | Show terminal output with hidden modules detected     |
| 0:15 | Module 2 | Click Syscall Discrepancy method → Show demo         |
| 0:20 | Module 3 | Select "/bin/ps hash mismatch" → Classify as threat  |
| 0:25 | Module 3 | Show feedback with correct answer                     |
| 0:30 | Module 4 | Click "LKM Kernel Rootkit" → Show family modal       |
| 0:35 | Module 4 | Scroll through detection methods and real-world cases |
| 0:40 | Module 5 | Load Ghost Processes mission → Show terminal output  |
| 0:45 | Module 5 | Submit correct answer → Show feedback                |
| 0:50 | Module 6 | Answer 2 quiz questions → Progress bar updates       |
| 0:55 | Close    | Return to main navigation                             |

---

## 🚦 **Performance**

- **Load Time**: < 2 seconds (zero external dependencies)
- **Memory Usage**: < 50 MB
- **CPU Usage**: Minimal (event-driven)
- **Network**: Zero requests after initial load

---

## 🛡️ **Security Notes**

RKHUNTER LIVE is a **completely safe** educational platform:

- ✅ No actual rootkits executed
- ✅ All simulations run in browser memory
- ✅ No data collection or tracking
- ✅ No external dependencies
- ✅ Pure HTML/CSS/JavaScript
- ✅ Educational purposes only — learn rootkit detection safely

---

## 📝 **License**

MIT License — see LICENSE file for details.

---

## 🙏 **Acknowledgments**

- **rkhunter project** — Original Rootkit Hunter tool
- **chkrootkit project** — Classic rootkit detection
- **AIDE** — Advanced Intrusion Detection Environment
- **Lynis** — Security auditing tool
- **Volatility Foundation** — Memory forensics framework
- **LiME** — Linux Memory Extractor
- **MITRE ATT&CK** — Rootkit classification framework

---

## 📧 **Contact**

- **GitHub Issues**: [Create an issue](https://github.com/Willie-Conway/RKHUNTER-LIVE/issues)
- **Website**: https://willie-conway.github.io/RKHUNTER-LIVE/

---

## 🏁 **Future Enhancements**

- [ ] Add more rootkit families (8+ total)
- [ ] Include live Volatility memory analysis simulation
- [ ] Add forensic report generation
- [ ] Export scan results as PDF
- [ ] Multi-user training progress tracking
- [ ] Certificate of completion
- [ ] Advanced rootkit evasion techniques
- [ ] Live packet capture analysis
- [ ] Integration with ELK stack for log analysis
- [ ] Cloud forensics scenarios

---

<p align="center">
  <strong>🕵️ RKHUNTER LIVE — Train Like a Digital Forensic Investigator 🕵️</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/BUILT_WITH-❤️-ffb300?style=for-the-badge&labelColor=0a0c14" />
  <img src="https://img.shields.io/badge/FOR-Linux_Forensics-00e676?style=for-the-badge&labelColor=0a0c14" />
  <img src="https://img.shields.io/badge/TRY_IT_LIVE-00e5ff?style=for-the-badge&labelColor=0a0c14" />
</p>

---

*Last updated: March 2025*
