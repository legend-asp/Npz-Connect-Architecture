# ⚡ NPZ Connect — Automated VPN & Subscription Platform

[![Live Demo](https://img.shields.io/badge/Live_Web_App-buy.npzconnect.site-8b5cf6?style=for-the-badge&logo=googlechrome&logoColor=white)](https://buy.npzconnect.site/)
[![Telegram Bot](https://img.shields.io/badge/Telegram_Bot-@npzconnect__bot-2ca5e0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/npzconnect_bot)
[![Platform](https://img.shields.io/badge/.NET-ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)]()
[![Core](https://img.shields.io/badge/Engine-3X--UI_/_Xray_VLESS-orange?style=for-the-badge)]()

> **Production Case Study:** An end-to-end commercial subscription system providing high-speed, censorship-resistant VPN access with automated cryptographic key provisioning, multi-channel user management, and payment gateway integration.

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    subgraph Clients["User Access Points"]
        Web["Web Dashboard (buy.npzconnect.site)\n- Telegram Login Widget\n- Key Viewer & Expiration Progress"]
        Bot["Telegram Bot (@npzconnect_bot)\n- Free trial & instant issuance\n- Notifications"]
    end

    subgraph Core["Backend & Business Logic (.NET)"]
        API["API Service & Orchestrator"]
        PayWebhook["Payment Webhook Handler\n(Automated transaction verification)"]
        Db[("Database\nUsers, Subscriptions, Keys")]
    end

    subgraph Infrastructure["VPN & External Nodes"]
        Panel["3X-UI Panel API\n(Xray Core / VLESS / Reality)"]
        Gateway["Payment Gateway Provider"]
    end

    Web -->|Auth & API calls| API
    Bot -->|Bot API polling/webhook| API
    Gateway -->|Payment confirmed webhook| PayWebhook
    PayWebhook --> API
    API -->|Provision/Revoke client keys| Panel
    API <-->|Sync state| Db
