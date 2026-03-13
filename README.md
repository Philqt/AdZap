<div align="center">
  <img src="https://img.shields.io/badge/Status-Active_Development-brightgreen?style=for-the-badge&logo=android" alt="Status" />
  <img src="https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Platform" />
  <img src="https://img.shields.io/badge/License-MIT-blue?style=for-the-badge" alt="License" />
</div>

<br />

<div align="center">
  <h1 align="center">🛡️ AdZap VPN: The Stealth Engine</h1>
  <p align="center">
    <strong>A high-performance, system-wide, and 100% offline DNS/DPI Ad Blocker built for Android.</strong>
  </p>
</div>

<hr />

## 🚀 Overview

**AdZap** is not just another DNS filter—it's a custom-built, native Android VPN Engine meticulously crafted to eradicate ads, trackers, and telemetry at the network level. Designed to intercept aggressive ad networks (like YouTube, VidSrc, and encrypted DoH streams) using intelligent Deep Packet Inspection and direct Datagram Socket manipulation.

Say goodbye to pop-ups and tracking, and reclaim your digital sovereignty entirely offline.

## ✨ Core Features

*   **🛡️ System-Wide Ad Blocking:** Silently drops telemetry, pop-unders, and ad networks across all apps and browsers.
*   **🔍 Deep Packet Inspection (DPI) & SNI Intercept:** Reads raw TLS handshakes (SNI) and HTTP cleartext boundaries to intercept malicious packets hiding behind verified IPs.
*   **🔥 Hardcore Mode (IPv6 Null-Routing):** Forces complete DNS downgrade by intentionally blackholing all IPv6 (`::/0`) traffic, stopping sneaky ad leaks.
*   **🔨 TCP Reset (RST) Injection:** Kills active Ad/WebSocket tracking connections immediately by spoofing TCP Reset packets to the tracking endpoints.
*   **🚫 Anti-QUIC & DoH Bypass Prevention:** Blocks popular DNS-over-HTTPS providers and drops UDP (Port 80/443) to force aggressive apps (like YouTube) to fallback to interceptable TCP traffic.
*   **📱 Sleek & Interactive UI:** A gorgeous, futuristic dashboard featuring real-time packet monitoring, Moti animations, haptic feedback, and a fully customizable rule whitelister.
*   **🔒 100% Private (No External Servers):** Everything operates strictly on your local device. **Zero logs, zero telemetry, zero compromises.**

---

## 🛠️ Technology Stack

AdZap masterfully bridges a smooth, modern User Interface with low-level, high-speed custom network engineering.

### Frontend (Application Layer)
*   <img src="https://img.shields.io/badge/React_Native-20232A?style=flat&logo=react&logoColor=61DAFB" /> **React Native & Expo CLI** - Core UI framework.
*   <img src="https://img.shields.io/badge/TypeScript-007ACC?style=flat&logo=typescript&logoColor=white" /> **TypeScript** - Strongly typed scalable architecture.
*   <img src="https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat&logo=tailwind-css&logoColor=white" /> **NativeWind** - High-speed utility styling classes.
*   <img src="https://img.shields.io/badge/Reanimated-FF4154?style=flat&logo=react&logoColor=white" /> **Reanimated & Moti** - Smooth, GPU-accelerated micro-animations.

### Backend (Native Android Layer)
*   <img src="https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white" /> **Java** - The bare-metal engine powering the networking protocol.
*   **Android VpnService API** - Establishes the virtual local tunnel intercept.
*   **Raw IP/UDP/TCP Sockets (DatagramSocket)** - Low-level byte manipulation for packet inspection and custom DNS packet crafting.

---

## 🎯 How It Works

1.  The Android `VpnService` forces network traffic through a local, virtual gateway interface (`10.0.0.1`).
2.  AdZap captures outgoing `UDP 53 (DNS)` requests and checks them against a massive custom Blacklist HashMap (Over 50K+ Active Rules).
3.  **If the Domain is Allowed:** The packet is relayed safely to an upstream generic DNS server, and the real IP is returned to the requesting app.
4.  **If the Domain/Signature is Blocked:** AdZap intercepts the packet and instantly fabricates an offline response pointing to `0.0.0.0` (with a 1-second TTL). The Ad network is completely blackholed!

---

<br />

<div align="center">
  <a href="https://facebook.com/juphil.kadusale">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" alt="Facebook" />
  </a>
  <a href="mailto:phu12@gmail.com">
    <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" />
  </a>
  <a href="https://tiktok.com/@jkdevworks">
    <img src="https://img.shields.io/badge/TikTok-000000?style=for-the-badge&logo=tiktok&logoColor=white" alt="TikTok" />
  </a>
</div>

<p align="center">
  <i>"Crafted with precision. Built with passion. Optimized for performance."</i><br>
  © 2026 Juphil Kadusale. All rights reserved.
</p>
