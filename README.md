# HardWorker

> Automated App Activity Simulator for Android

[![License](https://img.shields.io/badge/license-Educational-blue.svg)](LICENSE)
[![API](https://img.shields.io/badge/API-21%2B-brightgreen.svg)](https://android-arsenal.com/api?level=21)
[![Platform](https://img.shields.io/badge/platform-Android-green.svg)](https://www.android.com)

<div align="center">

**HardWorker** is an Android automation utility that simulates periodic in-app activity using the Accessibility Service API. Perfect for testing, automation research, and UX simulation tasks.

[Features](#-features) • [Installation](#-getting-started) • [Usage](#-usage) • [Permissions](#-permissions) • [Support](#-support)

</div>

---

## 📋 Table of Contents

- [Overview](#overview)
- [✨ Features](#-features)
- [🚀 Getting Started](#-getting-started)
  - [Requirements](#requirements)
  - [Installation](#installation)
  - [Setup](#setup)
- [📖 Usage](#-usage)
- [🔐 Permissions](#-permissions)
- [🛠️ How It Works](#-how-it-works)
- [⚠️ Important Notes](#-important-notes)
- [❌ Troubleshooting](#-troubleshooting)
- [💬 Support](#-support)
- [📄 License](#-license)

---

## Overview

HardWorker automatically simulates app activity by:
- Launching a selected app
- Performing configurable swipe gestures
- Waiting a few seconds
- Closing the app
- Repeating the sequence based on your schedule

Perfect for **testing scenarios** that require continuous app activity simulation without manual intervention.

---

## ✨ Features

### 🤖 Automated App Interaction
- Automatically launches the selected app
- Performs configurable swipe gestures
- Controlled wait intervals between actions
- Auto-closes app after interaction
- Repeats based on schedule

### 📅 Weekly Scheduler
- Choose specific days of the week
- Set exact start and end times
- Automation triggers at next scheduled interval
- Easy enable/disable toggle

### ♿ Accessibility-Based Automation
- Built on Android's Accessibility Service API
- Detects UI activity
- Simulates natural gestures
- Works without additional UI automation libraries

### 🔗 Discord Support
- Built-in contact button
- Direct access to developer for help and feedback

---

## 🚀 Getting Started

### Requirements

- Android 5.0 (API 21) or higher
- Accessibility Service enabled on device
- At least 5 MB free storage

### Installation

1. Clone or download this repository
   ```bash
   git clone https://github.com/yourusername/HardWorker.git
   ```

2. Open in Android Studio
3. Build and install on your device

   ```bash
   # Build APK
   ./gradlew assembleRelease
   
   # Install via ADB
   adb install app/build/outputs/apk/release/app-release.apk
   ```

### Setup

#### Step 1: Enable Accessibility Service
1. Go to **Settings** → **Accessibility**
2. Find and tap **HardWorker**
3. Toggle **ON**

#### Step 2: Grant "Exact Alarm" Permission (Android 12+)
1. Go to **Settings** → **Apps** → **HardWorker**
2. Tap **Alarms & reminders**
3. Enable **Allow exact alarms**

#### Step 3: Optimize Battery Settings
1. Go to **Settings** → **Battery**
2. Find HardWorker and disable battery optimization
3. Keep app excluded from power-saving modes

---

## 📖 Usage

### Quick Start

1. ✅ Grant Accessibility permission in Settings
2. ✅ Select the app you want to automate
3. ✅ Choose automation mode:
   - **One-time**: Press "Start" button
   - **Scheduled**: Configure weekly schedule
4. ✅ (Optional) Set start/end times and weekdays
5. ✅ Monitor status in app UI

### Scheduling Behavior

The scheduler will:
- Automatically trigger automation at next valid scheduled time
- Continue working daily within the selected time range
- Stop after the end time
- Enable/disable with a simple toggle

**Note:** Automation continues running with UI closed if:
- ✅ Accessibility Service is enabled
- ✅ Battery optimization is disabled
- ✅ Device is awake

---

## 🔐 Permissions

| Permission | Purpose |
|-----------|---------|
| `QUERY_ALL_PACKAGES` | Lists installed apps for user selection |
| `SCHEDULE_EXACT_ALARM` | Triggers scheduler at precise times |
| `BIND_ACCESSIBILITY_SERVICE` | Automates gestures (swipe, click, etc.) |

**Privacy Statement:** HardWorker does not collect, transmit, or store personal information.

---

## 🛠️ How It Works

### Automation Flow

1. Waits for next active window
2. Launches selected app
3. Performs top-to-bottom swipe gesture
4. Waits 2 seconds
5. Closes app
6. Repeats based on schedule

### Technical Details

- Uses **Accessibility Service** for gesture simulation
- Respects Android lifecycle and background restrictions
- Handles app launch/close events
- Monitors system state for optimal execution

---

## ⚠️ Important Notes

### 1. Accessibility Service Required ⚙️
HardWorker **requires** Android's Accessibility API. You must enable:
- **Settings** → **Accessibility** → **HardWorker** → **ON**
- Without this, the app cannot simulate gestures

### 2. "Exact Alarm" Permission (Android 12+) ⏰
For precise scheduled automation:
- Required permission: `SCHEDULE_EXACT_ALARM`
- **Settings** → **Apps** → **HardWorker** → **Alarms & reminders** → **Allow**

### 3. Background Limitations ⚠️
Due to Android battery policies:
- Automation may not run while device is locked
- Some devices delay alarms by 10–60 seconds
- OEM battery savers may prevent background execution

**Best Practices:**
- ✅ Keep device unlocked during automation
- ✅ Disable battery optimization for HardWorker
- ✅ Exclude app from power-saving modes

---

## ❌ Troubleshooting

### Automation Does Not Start

**Issue:** App doesn't trigger automation

**Solutions:**
- ✅ Ensure Accessibility Service is enabled in Settings
- ✅ Verify the selected app is installed on device
- ✅ Disable battery optimization for HardWorker
- ✅ Confirm "Schedule exact alarms" is allowed (Android 12+)
- ✅ Check if device is awake and unlocked

### Nothing Happens on Screen

**Issue:** Automation runs but no visible gestures

**Causes:**
- Device is locked
- Screen is off
- Another app overlays the screen

**Solution:**
- Unlock device and ensure no overlays are blocking interaction
- Try again with app in foreground

### App Keeps Closing

**Issue:** Automation terminates unexpectedly

**Solutions:**
- ✅ Check available device storage
- ✅ Update app to latest version
- ✅ Restart device
- ✅ Reinstall HardWorker

### Permission Errors

**Issue:** "Permission denied" or "Service not available"

**Solutions:**
- Fully disable and re-enable Accessibility Service
- Go to Settings → Apps → HardWorker → Permissions
- Manually review and grant all required permissions

---

## 💬 Support

Need help or want to report issues?

- **Discord**: [@YourUsername](https://discordapp.com/users/193954733617053696)
- **Issues**: [GitHub Issues](../../issues)
- **Discussions**: [GitHub Discussions](../../discussions)

---

## 📄 License

This project is for **educational and testing purposes only**.

Use responsibly and follow your local laws and regulations. The developer is not responsible for misuse of this tool.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to:
- Report bugs via [Issues](../../issues)
- Suggest features via [Discussions](../../discussions)
- Submit pull requests for improvements

---

## 📌 Roadmap

- [ ] Gesture customization (swipe direction, duration)
- [ ] Multiple app automation in sequence
- [ ] Custom automation scripts
- [ ] Usage statistics and logs
- [ ] Cloud sync for schedules

---

## Image

<img width="377" height="831" alt="image" src="https://github.com/user-attachments/assets/4cd4d394-c1a0-4af0-95df-001b65ea0b91" />

## Video

https://cdn.discordapp.com/attachments/683876016363798550/1445317277439361045/Screen_recording_20251202_032947.mp4?ex=692fe81b&is=692e969b&hm=47707f6400867c05e81c0d76a2a3a031e7ed3c8de28a9bad999f1576ecdb5ecb&
---

## Acknowledgments

Built with ❤️ for the Android automation community.

---

<div align="center">

Made with ☕ and 🔧 by [@YourUsername](https://github.com/yourusername)

</div>
