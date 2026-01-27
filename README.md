# SecureWallet: iOS RASP Challenge

![SecureWallet](secure_wallet_hero.png)

> **Level:** Professional
> **Target:** iOS 14.0+ (ARM64)
> **Protection:** Talsec RASP (Hardened)

## The Mission
Your objective is simple: **Bypass the security mechanisms and reach the "Authorized" screen.**

However, the application is protected by a commercial-grade RASP (Runtime Application Self-Protection) engine that detects:
*   [x] Jailbreak
*   [x] Debugging (lldb)
*   [x] Instrumentation (Frida)
*   [x] Simulator Execution
*   [x] Repackaging / Integrity

If any threat is detected, the app will enter a **"System Failure"** state and terminate after a 4-second delay.

## Download
> **[Download secure_wallet.ipa (Direct Link)](https://github.com/3xploit666/secure-wallet-challenge/raw/main/SecureWallet.ipa)**

## Installation
You can install the IPA using your preferred signing method:
1.  **TrollStore** (Recommended for entitlements)
2.  **Sideloadly** / **AltStore** (Standard signing)
3.  **Filza** (If AppSync Unified is installed)

## Tech Specs
*   **Language:** Swift 5 (Protocol Witness Tables enabled)
*   **Binary:** Stripped & Optimized (No symbols)
*   **Architecture:** ARM64 only
*   **Framework:** Talsec RASP v6.14.0

## Write-ups & Solution
Stuck? Check out the detailed technical analysis on my blog:
[Deconstructing RASP: iOS Analysis & Bypass Strategy](https://www.3xploitdev.com/blog/secure-wallet-challenge)

---
**Developed by 3xploit666**
*For educational purposes only.*
