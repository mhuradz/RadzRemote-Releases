<p align="center">
  <h1 align="center">RadzRemote</h1>
  <p align="center">
    <strong>The High-Performance, Privacy-First AnyDesk Alternative for Windows</strong>
  </p>
  <p align="center">
    Native C# / .NET 10 • Zero-Config Cloud Relay • True End-to-End Encryption (ECDH + AES-256-GCM) • Standalone Portable
  </p>
</p>

<p align="center">
  <a href="https://github.com/mhuradz/RadzRemote-Releases/releases/latest"><img src="https://img.shields.io/badge/Release-v1.0.0-00D2FF?style=for-the-badge&logo=github" alt="Latest Release"></a>
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011%20(x64)-0078D4?style=for-the-badge&logo=windows" alt="Platform">
  <img src="https://img.shields.io/badge/.NET-10.0%20LTS-512BD4?style=for-the-badge&logo=dotnet" alt=".NET 10">
  <img src="https://img.shields.io/badge/Security-E2EE%20AES--256--GCM-34F5A5?style=for-the-badge&logo=shield" alt="Security">
  <img src="https://img.shields.io/badge/License-Proprietary-FF5D7A?style=for-the-badge" alt="License">
</p>

---

## ⚡ Overview

**RadzRemote** is a modern, lightweight, and ultra-secure Windows remote desktop engine engineered from scratch as a clean-room alternative to proprietary tools like **AnyDesk** and **TeamViewer**.

Built without restrictive commercial time limits, subscription popups, or invasive surveillance telemetry, RadzRemote delivers fluid low-latency remote control over standard internet connections with zero router or firewall configuration required.

```
                  ┌──────────────────────────────────────────────┐
                  │    RadzRemote Cloud Relay (TLS 1.3 / WSS)    │
                  │         remote.orangevpn.com.ph              │
                  └──────────────▲────────────────▲──────────────┘
                                 │                │
                        Encrypted│E2EE    Encrypted│E2EE
                        Packets  │        Packets  │
                                 ▼                ▼
                     ┌────────────────┐     ┌────────────────┐
                     │  Target Host   │◄───►│ Controlling PC │
                     │ (Desktop View) │     │ (Interactive)  │
                     └────────────────┘     └────────────────┘
```

---

## 📸 User Interface

### 1. Main Client Dashboard
*Minimal Antigravity 2.0 theme with 22px curved glass panels, glowing 9-digit Device ID, copy button, live network health capsule, and incoming request banner.*

![RadzRemote Main Client Interface](https://raw.githubusercontent.com/mhuradz/RadzRemote-Releases/main/mainwindow.png)

### 2. Active Remote Desktop Viewport
*Aspect-ratio preserved remote display streaming, real-time FPS & resolution telemetry, display switcher, streaming quality selector, and encrypted clipboard sync.*

![RadzRemote Active Session Window](https://raw.githubusercontent.com/mhuradz/RadzRemote-Releases/main/sessionwindow.png)

---

## 🆚 Why RadzRemote? (Comparison)

| Feature | RadzRemote | AnyDesk (Free) | TeamViewer (Free) |
| :--- | :---: | :---: | :---: |
| **Time Limits & Nag Screens** | ❌ **None (Unlimited)** | ⚠️ 5–15 min timeout warning | ⚠️ Frequent "commercial use" block |
| **Configuration Required** | ❌ **Zero (Ready to use)** | ❌ Zero | ❌ Zero |
| **End-to-End Encryption** | 🔒 **ECDH P-256 + AES-256-GCM** | 🔒 RSA-2048 + AES-128 | 🔒 RSA-2048 + AES-256 |
| **Relay Server Eavesdropping** | 🛡️ **Mathematically impossible** | ⚠️ Closed-source relay | ⚠️ Closed-source relay |
| **Installation Requirement** | 🚀 **100% Standalone Portable** | Optional | Required installer |
| **UI Experience** | ✦ **Clean, Modern, No Ads** | Banner ads & upsells | Popups & survey prompts |
| **Multi-Monitor Support** | ✅ **Included (Instant Switch)** | ✅ Included | ⚠️ Limited / Paid |
| **Clipboard Sync** | ✅ **Encrypted Bidirectional** | ✅ Included | ✅ Included |
| **Silent Auto-Update** | ✅ **Built-in GitHub Engine** | Background service | Background service |

---

## ✨ Key Features

- **🚀 Instant Zero-Configuration**: Works immediately over any home, office, or cellular connection. Both endpoints connect via secure WebSockets (`wss://remote.orangevpn.com.ph/ws/signaling`) over standard HTTPS/443 ports.
- **🛡️ True End-to-End Encryption (E2EE)**: Ephemeral ECDH (P-256) key exchange establishes directional session keys (`ClientToHost` and `HostToClient`) with authenticated **AES-256-GCM**. The relay server carries encrypted traffic but cannot inspect screen frames, keystrokes, or clipboard data.
- **🔢 9-Digit Device ID**: Every device is automatically assigned a clean, memorable 9-digit address (e.g., `763 919 872`). Device credentials and encryption secrets are bound to local hardware using the **Windows Data Protection API (DPAPI)**.
- **🤝 Explicit Consent Security**: The remote party receives an interactive **Accept & Allow** or **Decline** banner before any session starts. No unauthorized background surveillance.
- **🖥️ 60 FPS Low-Latency Engine**: Optimized Win32 capture engine with real-time JPEG compression and pre-allocated buffer pooling to eliminate garbage collection stutters.
- **⌨️ Precision Win32 Input Injection**: Pixel-perfect remote mouse movement, button clicks, mouse wheel scrolling, and full physical keyboard injection using Win32 `SendInput` with virtual multi-monitor DPI scaling.
- **🖥️ Multi-Display Switching**: Seamlessly toggle between multiple monitors on the remote desktop with one click from the session toolbar.
- **⚙️ Dynamic Stream Quality**: Adjust streaming fidelity on the fly between **High (90%)**, **Balanced (75%)**, and **Fast (50%)** to adapt to any network condition.
- **📋 Real-Time Clipboard Sync**: Securely copy and paste text between local and remote machines.
- **📦 Single-File Portable Executable**: No installer, no background services, no .NET runtime installation required. Simply double-click `RadzRemote.exe`.

---

## 🚀 How to Use

### Connecting in 3 Simple Steps:

1. **Download & Launch**:
   Download [`RadzRemote.exe`](https://github.com/mhuradz/RadzRemote-Releases/releases/latest) on both computers and launch it. No installation needed.

2. **Share Device ID**:
   Ask the partner for their 9-digit **Remote ID** (displayed prominently on their main screen).

3. **Connect & Accept**:
   - Type their 9-digit ID into the **Remote Control** box and click **Connect to Remote Desktop**.
   - The partner clicks **Accept & Allow** on their screen.
   - The remote desktop window opens instantly with full interactive control!

---

## 📥 Download

Pre-compiled, digitally signed release binaries are publicly available:

| Package | Format | Architecture | Download |
| :--- | :---: | :---: | :--- |
| **RadzRemote Portable** | `.exe` (Single-File) | Windows x64 | **[Download RadzRemote.exe](https://github.com/mhuradz/RadzRemote-Releases/releases/download/v1.0.0/RadzRemote.exe)** |
| **RadzRemote Archive** | `.zip` (Compressed) | Windows x64 | **[Download RadzRemote.zip](https://github.com/mhuradz/RadzRemote-Releases/releases/download/v1.0.0/RadzRemote-v1.0.0-win-x64.zip)** |

*Compatible with Windows 10, Windows 11, and Windows Server 2016+ (64-bit).*

---

## 🔒 Security Architecture

```
                                  ECDH P-256 Key Exchange
       Client (Controller)  ───────────────────────────────►  Host (Target PC)
                            ◄───────────────────────────────
                                            │
                                            ▼
                           HKDF-SHA256 Directional Key Derivation
                     ┌──────────────────────────────────────────────┐
                     │  Key 1: Client → Host (Inputs & Commands)    │
                     │  Key 2: Host → Client (Video Frames & State) │
                     └──────────────────────────────────────────────┘
                                            │
                                            ▼
                               Authenticated AES-256-GCM
                        (Independent Nonce Counters per Direction)
```

1. **Ephemeral Key Exchange**: A new ECDH key pair is generated for each connection session.
2. **Directional Keys**: Client-to-Host and Host-to-Client communication paths use separate cryptographic keys to eliminate any risk of nonce collisions.
3. **Hardware Storage**: Device identities and session secrets are encrypted using Windows DPAPI (`ProtectedData`), tied to the current Windows user and hardware profile.
4. **Zero-Trust Relay**: The cloud signaling server only relays encrypted packets; it has no access to private keys and cannot decrypt video or input data.

---

## 🛠️ Building from Source

### Requirements
- Windows 10 / 11 (x64)
- [.NET 10.0 SDK](https://dotnet.microsoft.com/)

### Clone & Build
```powershell
# Clone the repository
git clone https://github.com/mhuradz/RadzRemote.git
cd RadzRemote

# Build solution
dotnet build RadzRemote.slnx

# Run all automated tests
dotnet test RadzRemote.slnx

# Publish standalone single-file portable release
.\build-client-release.cmd
```

---

<p align="center">
  <sub>RadzRemote is proprietary software developed for high-performance, private, and unrestricted remote desktop access.</sub>
</p>
