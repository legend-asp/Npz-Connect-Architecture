# ⚡ NPZ Connect — Automated VPN & Subscription Platform

[![Live Demo](https://img.shields.io/badge/Live_Web_App-buy.npzconnect.site-8b5cf6?style=for-the-badge&logo=googlechrome&logoColor=white)](https://buy.npzconnect.site/)
[![Telegram Bot](https://img.shields.io/badge/Telegram_Bot-@npzconnect__bot-2ca5e0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/npzconnect_bot)
[![Free Trial](https://img.shields.io/badge/Free_Trial-1_Day_Available-22c55e?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/npzconnect_bot)
[![Platform](https://img.shields.io/badge/.NET-ASP.NET_Core-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)]()
[![Engine](https://img.shields.io/badge/Engine-3X--UI_/_Xray_VLESS-orange?style=for-the-badge)]()

> **Production Case Study:** An end-to-end commercial subscription system providing high-speed, censorship-resistant VPN access with automated cryptographic key provisioning, multi-channel user management, and payment gateway integration.  
> 🎁 **Free 1-Day Trial** is available instantly via the Telegram bot.

---

## 🏗️ System Architecture

```mermaid
flowchart TD
    subgraph Clients["User Access Points"]
        Web["Web Dashboard (buy.npzconnect.site)\n- Telegram Login Widget\n- Key Viewer & Expiration Progress"]
        Bot["Telegram Bot (@npzconnect_bot)\n- 1-Day Free Trial & instant issuance\n- Automated renewal alerts"]
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
```

---

## 🌟 Key Engineering Highlights

- **Automated Client Lifecycle:** Zero human intervention required — accounts and VLESS/Reality keys are instantly provisioned and revoked via the 3X-UI REST API upon subscription triggers.
- **Instant Free Trial Onboarding:** Users can immediately test connection quality with a 1-day free trial issued directly through the Telegram bot.
- **Resilient Payment Webhooks:** Robust transactional handling for asynchronous payment status notifications to guarantee zero lost transactions.
- **Multi-Channel Delivery:** Unified session state accessible both via a responsive Web Dashboard (authenticated via Telegram Widget) and a Telegram Bot.
- **Real-Time Subscription Tracking:** Dynamic expiration calculation, visual progress bar indicators, and automated renewal reminders.

---

## 🛠️ Technology Stack

| Layer | Technologies |
| :--- | :--- |
| **Backend** | C#, .NET / ASP.NET Core, HttpClient orchestration |
| **Infrastructure** | 3X-UI Panel, Xray Core (VLESS / Reality protocol) |
| **Frontend** | Responsive Glassmorphism UI, CSS custom properties, Telegram Auth Widget |
| **Integrations** | Telegram Bot API, Commercial Payment Gateway API |

---

## 🔗 Live Production Links

* 🌐 **Web Dashboard:** [https://buy.npzconnect.site](https://buy.npzconnect.site)
* 🤖 **Telegram Bot (with 1-day free trial):** [https://t.me/npzconnect_bot](https://t.me/npzconnect_bot)
