# Baeit POS - Downloads

Official download page for **Baeit POS**, the offline-first point-of-sale for restaurants on Windows.

> **Beta software.** Baeit POS is in a free beta. Builds published here are **pre-releases** and are **not yet code-signed**. Use them for testing and feedback, and keep your usual way of billing available while you evaluate.

This repository contains **installers only**. The source code is private.

## Download

1. Open the [**Releases**](../../releases) page.
2. Under the newest release, download **`Baeit POS Beta Setup x.y.z.exe`**.
3. Only download files from this page.

An internet connection is needed for the first sign-in, for sync and for updates; billing works offline afterwards. See **System requirements** below.

## System requirements

| | Baeit POS (no AI) | Baeit POS + optional local AI |
|---|---|---|
| **Windows** | Windows 10 or newer, 64-bit | Windows 10 or newer, 64-bit |
| **Processor** | Dual-core x64 | 4 or more threads recommended (2 minimum) |
| **Memory (RAM)** | 4 GB recommended for comfortable billing alongside other programs | **8 GB recommended**, 6 GB minimum |
| **Disk space** | Installer about 115 MB; installed about 450 MB; keep at least **5 GB free** for data, backups and updates (the app warns below 5 GB and treats under 1 GB as unsafe) | The above, plus the AI model (**3.1 GB**) and AI engine (**19 MB**), about **3.4 GB** in total. Keep at least **10 GB free** recommended, 6 GB minimum |
| **Graphics card** | Not required | Not required (AI runs on the processor) |
| **Internet** | First sign-in, sync and updates only | Same, plus a one-time model download; AI itself runs offline |

How firm these numbers are:
- **No-AI figures** come from the checks built into the app (**Settings → Device readiness**) and the installer size. They have not been tested on a wide range of low-end machines yet.
- **AI figures are provisional.** The download sizes above are exact. The RAM and processor figures are estimates, with one real measurement so far: on a 15.7 GB laptop (Intel Core i5, 12 threads) the AI loaded in about 19 seconds and answered in under 2 seconds. Smaller PCs have not been measured yet.
- **Local AI is optional.** The app checks your computer first and tells you plainly whether local AI can run. You can skip it, or set it up any time from **Settings → Local AI** or the **AI Insights** tab. The POS works fully without AI.

### What local AI downloads

Only when you press **Download & set up local AI**, and only from these publishers:
- the AI model, Google's official Gemma 4 E2B (Apache-2.0), from Hugging Face;
- the AI engine, the open-source llama.cpp (MIT), from GitHub.

Both files are checked against fixed checksums built into the app before they are used. The AI runs on your computer, and your sales data is not sent anywhere.

## Install

1. Run the downloaded `.exe`.
2. Windows may show **"Windows protected your PC"** because beta builds are unsigned. Choose **More info → Run anyway**.
3. Follow the installer, then open **Baeit POS**.
4. Complete the first-run setup:
   - accept the terms,
   - connect with your Baeit Partner email and password,
   - **Local AI is optional**: you can skip it and set it up later in **Settings → Local AI**.

## Verify your download (recommended)

Each release lists a `SHA256SUMS.txt`. In PowerShell, from the folder with the installer:

```powershell
Get-FileHash .\"Baeit POS Beta Setup x.y.z.exe" -Algorithm SHA256
```

Compare the result with `SHA256SUMS.txt` on the release page. A matching checksum shows the file was not corrupted or altered in transit. It does **not** prove who published it, which is why beta builds are unsigned and only meant for testers.

## Updates

Installed copies check this repository for newer beta releases at startup and under **Updates** inside the app. When one is available the app offers to download it and install it at a safe moment, never in the middle of an order.

Files such as `latest.yml` and `.blockmap` in each release are used by the updater. Do not delete them.

## Your data

Orders, menu and settings are stored on the computer, in your Windows user profile (`%APPDATA%\Baeit POS`), not in the install folder. Uninstalling does not delete that data. Back it up from **Settings** before wiping a PC.

## Local AI (optional)

Baeit POS can run AI on the computer itself, so it works offline. It is not included in the installer and is not required to use the POS. If you choose to install it, it is a separate download, and the app tells you whether your computer meets the requirements first.

## Feedback and problems

Please tell your Baeit contact what you ran into: the version number (**Settings → Updates**), what you did, and what you expected to happen. Do not include passwords or customer data.

---

© Baeit. All rights reserved. Third-party open-source notices are listed inside the app under **Settings → Legal & About**.
