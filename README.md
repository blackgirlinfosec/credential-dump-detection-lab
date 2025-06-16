# 🧪 Credential Dump Detection Lab (LSASS Monitoring with Sysmon)

This lab simulates a real-world credential theft attempt using **only a Windows 10 VM, built-in tools, and Sysmon**. The goal is to understand how attackers dump credentials from **Local Security Authority Subsystem Service (LSASS)** and how a Tier 1 SOC analyst can detect it using logs.

---

## 🧠 What I Did

| Step | Summary |
|------|---------|
| 🔧 Set up a Windows 10 virtual machine in Azure | Created a safe lab environment |
| 🛡️ Installed Sysmon + config | Set up internal system logging with SwiftOnSecurity’s config |
| 🧍🏽 Simulated normal behavior | Browsed sites, used Notepad, ran PowerShell to understand baseline logs |
| 💀 Simulated LSASS dump | Used Task Manager to attempt memory dump of LSASS (like an attacker might) |
| 🕵🏾 Analyzed logs | Found evidence of the dump in **Event ID 11 (File Create)** |

---

## 📸 Screenshots

| Step | File Name |
|------|-----------|
| ✅ Sysmon installed | `step2_sysmon_installed_confirmation.png` |
| 📊 Logs confirmed | `step3_sysmon_eventviewer_check.png` |
| 🧍🏽 Baseline activity | `step4_sysmon_baseline_activity.png` |
| 💀 Dump attempt | `step5_lsass_dump_attempt.png` |
| 🕵🏾 Dump file detected | `step6_sysmon_lsass_dump_file_creation.png` |

---

## 🔑 Key Windows Event IDs

| Event ID | Description |
|----------|-------------|
| `1` | **Process Create** — logs when a program starts (e.g., `taskmgr.exe`) |
| `10` | **Process Access** — logs when one program tries to access another (e.g., memory access to LSASS) |
| `11` | **File Create** — logs when a file is written (e.g., LSASS dump `.dmp` file) |

---

## 💬 How This Shows SOC Skills

- 🧠 I understand how attackers target **Local Security Authority Subsystem Service (LSASS)** to steal credentials
- 🕵🏾 I know how to detect this behavior using **Sysmon logs** and **Event Viewer**
- 🛠️ I used only **free tools and built-in features**, just like in resource-limited environments
- 💼 I practiced triage and baseline analysis like a real Tier 1 SOC analyst

---

## ✨ Reflection

> “This lab helped me see how credential theft actually works on a Windows system. By simulating a suspicious action and catching it with Sysmon, I built confidence in detection, log analysis, and what to look for in real alerts. I now understand the importance of baseline behavior and small red flags that show up before a major attack.”

---

