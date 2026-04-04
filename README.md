# 🦞 OpenClaw Phone Control (No-Root)
**Control your Android device using natural language AI — powered by Shizuku & Termux.**

OpenClaw allows you to manage your phone via a Telegram bot using the power of local AI (Ollama). No root access is required, making it accessible for almost any modern Android device.

---
<img width="2048" height="1256" alt="openclaw ontroll" src="https://github.com/user-attachments/assets/40f29550-105a-4022-b063-b3f13d9783b1" />

## ✨ Key Features
* **💬 Telegram Integration:** Send commands to your phone from any device, anywhere.
* **🧠 Local AI Brain:** Powered by **Ollama**, allowing the system to understand natural language commands.
* **📱 30+ System Actions:** Toggle WiFi/Bluetooth, make calls, send SMS, take screenshots, adjust volume, and more.
* **🔒 Rootless Power:** Uses **Shizuku** to bridge ADB-level permissions without voiding warranties.
* **⚡ Rapid Setup:** A single-line script handles the heavy lifting.

---

## 📺 Video Tutorial
[![](https://img.shields.io/badge/YouTube-Watch%20Setup-red?style=for-the-badge&logo=youtube)](YOUR_YOUTUBE_LINK_HERE)
*Follow the step-by-step visual guide to ensure a smooth installation.*

---

## 📋 Prerequisites

| Requirement | Detail | Source |
| :--- | :--- | :--- |
| **Android Version** | Android 11 or higher | System Settings |
| **Terminal** | Termux (F-Droid Version) | [F-Droid](https://f-droid.org/en/packages/com.termux/) |
| **Permission Bridge**| Shizuku | [Play Store](https://play.google.com/store/apps/details?id=moe.shizuku.privileged.api) / [UpToDown](https://shizuku-manager.en.uptodown.com/android) |
| **Bot Access** | Telegram Bot Token | [@BotFather](https://t.me/botfather) |

> ⚠️ **IMPORTANT:** Do **not** use the Play Store version of Termux; it is outdated and will cause installation errors.

---

## 🏁 Setup Guide

### Step 1: Prepare Shizuku
1.  **Enable Developer Options:** Go to `Settings > About Phone` and tap **Build Number** 7 times.
2.  **Enable Wireless Debugging:** Found inside `Settings > Developer Options`.
3.  **Pair Shizuku:** * Open the Shizuku app → Tap **Pairing**.
    * Enter the pairing code from Wireless Debugging settings.
    * Tap **Start** in the Shizuku app.
4.  **Export Files:** Tap "Use Shizuku in terminal apps" → **Export files**. 
    * Save these files into a folder named exactly `Shizuku` in your internal storage.

### Step 2: Install & Run Ollama
Open Termux and run the following:
```bash
pkg install ollama
ollama serve
```
In a new Termux session, run the model:
```
ollama run minimax-m2.7:cloud
```
## Step 3: Install OpenClaw
Ensure Shizuku is running, then execute the auto-installer:
```
curl -sL https://raw.githubusercontent.com/jarvesusaram99/Openclaw-Termux-NoRoot/main/auto_setup.sh | bash
```

# 🚀 Configuration & Usage
## 1. Onboarding
Initialize your settings and link your Telegram bot:
```
openclaw onboard
```
## 2. Retrieve Gateway Token
```
cat ~/.openclaw/openclaw.json
```

## 3. Start the Gateway
Run the gateway to start listening for commands:

Debug mode (see real-time logs)
```
openclaw gateway --verbose
```
Standard start
```
openclaw gateway
```

## 🛠 Troubleshooting
Shizuku Disconnecting: Ensure "Battery Optimization" is disabled for the Shizuku app.

Permission Denied: Re-run the Export files step and ensure the folder is named Shizuku (case-sensitive).

Ollama Errors: Ensure you have enough free RAM (at least 2GB-4GB recommended for smooth AI inference).

