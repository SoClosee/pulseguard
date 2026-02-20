<div align="center">

# 📊 PulseGuard

**Real-time server monitoring dashboard with intelligent alerts**

[![Status](https://img.shields.io/badge/Status-Production-brightgreen?style=flat-square)]()
[![Stack](https://img.shields.io/badge/Stack-Node.js_·_React_·_WebSocket-blue?style=flat-square)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)]()

</div>

---

## Overview

PulseGuard is a lightweight, self-hosted server monitoring solution designed for developers and small teams managing VPS infrastructure. It provides real-time metrics, intelligent alerting, and a clean dashboard — without the overhead of enterprise monitoring stacks.

Born from the need to monitor multiple VPS servers running SaaS products, trading bots, and automation systems simultaneously.

## Features

- **Real-Time Dashboard** — Live CPU, RAM, disk, and network metrics via WebSocket
- **Multi-Server Support** — Monitor all your VPS instances from a single dashboard
- **Smart Alerts** — Configurable thresholds with Telegram/Discord/Email notifications
- **Service Health Checks** — Monitor Nginx, Docker containers, databases, and custom processes
- **Uptime Tracking** — Historical uptime data with SLA percentage calculation
- **Incident Timeline** — Automatic incident detection and resolution tracking
- **Low Footprint** — Agent uses < 20MB RAM, minimal CPU impact

## Architecture

```
┌─────────────────────────────────────────────┐
│                  Dashboard                   │
│              React + Tailwind                │
└──────────────────┬──────────────────────────┘
                   │ WebSocket
┌──────────────────┴──────────────────────────┐
│               API Server                     │
│           Node.js + Express                  │
│         Alert Engine · Storage               │
└──────┬───────────┬───────────┬──────────────┘
       │           │           │
  ┌────┴───┐  ┌───┴────┐  ┌──┴──────┐
  │ Agent  │  │ Agent  │  │  Agent  │
  │ VPS-1  │  │ VPS-2  │  │  VPS-3  │
  └────────┘  └────────┘  └─────────┘
```

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Dashboard | React, Tailwind CSS, Recharts |
| API Server | Node.js, Express, WebSocket |
| Agent | Python (psutil), lightweight daemon |
| Alerts | Telegram Bot API, Discord Webhooks, SMTP |
| Storage | SQLite (single-server) / PostgreSQL (multi) |
| Deployment | Docker, systemd |

## Quick Start

```bash
# Install the agent on each server
curl -sSL https://raw.githubusercontent.com/SoClosee/pulseguard/main/install.sh | bash

# Configure your server endpoint
pulseguard config --server https://your-dashboard.com --token YOUR_TOKEN

# Start monitoring
pulseguard start
```

## Status

PulseGuard is in production, actively monitoring infrastructure for multiple SaaS products.

**Roadmap:**
- [x] Real-time metrics dashboard
- [x] Multi-server agent system
- [x] Telegram & Discord alerts
- [x] Docker container monitoring
- [ ] Log aggregation
- [ ] Custom metric plugins
- [ ] Mobile app (React Native)

---

<div align="center">

Built by **[SoClose](https://github.com/SoClosee)** · Part of the **[SoClose](https://soclose.co)** ecosystem

</div>
