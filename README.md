![preview](https://raw.githubusercontent.com/roumer19/manga-pulse-frontend/main/preview.svg)

# Repository Name: **Chōra**

> *Where narrative intelligence meets visual harmony — a next-generation frontend for self-hosted visual storytelling ecosystems.*

---

## Overview

Chōra is a meticulously crafted, browser-based client designed to interface with Suwayomi-compatible media servers. Built not merely as a reader, but as an ambient gateway into the worlds you host, Chōra reimagines the relationship between reader and library. It transforms raw server data into a fluid, cinematic browsing and reading experience — optimized for speed, accessibility, and personal expression.

Named after the ancient Greek concept of a receptive, generative space, Chōra is the blank canvas upon which your curated collections come alive. This is not just a manga reader; it is a semantic layer between your server and your senses.

---

## ✦ Philosophy & Vision

Most frontends treat the reading experience as a utility — a means to an end. Chōra treats it as a **ritual**. Every interaction, from the swipe of a page to the transition between library shelves, is designed to be frictionless yet intentional. The interface recedes so the story advances.

We believe that self-hosting should not demand a sacrifice in user experience. Chōra bridges the gap between the power of Suwayomi and the polish of a premium commercial application — without ever compromising your autonomy or privacy.

---

## ✦ Key Features

### 🧩 Responsive Semantic UI
- Adaptive layout engine that gracefully scales from a pocket-sized phone screen to a 4K monitor.
- Touch-optimized gestures with haptic-feedback simulation for mobile devices.
- Keyboard-shortcut-first navigation for power readers.

### 🌐 Multilingual Immersion
- Full localization support for over 18 languages, including right-to-left (RTL) script rendering.
- Dynamic font substitution for CJK, Arabic, and Cyrillic character sets.
- Community-contributed translation packs auto-synced from the server.

### ⚡ Zero-Compromise Performance
- Lazy-loaded chapter pages with predictive pre-fetching based on reading speed.
- Hardware-accelerated canvas rendering for silky-smooth page turns.
- Sub-200ms initial load time on average broadband connections.

### 🛠️ Deep Suwayomi Integration
- Full support for Suwayomi-Server extension system — browse, install, and update extensions from within Chōra.
- Real-time library synchronization via WebSocket.
- Track reading progress across multiple devices with session persistence.

### 🎨 Visual Customization Engine
- Per-series theme profiles (sepia, night mode, paper texture, inverted).
- Custom CSS injection for power users.
- Adjustable gutter spacing, border shadows, and page-fit modes.

### 📡 Offline Resilience
- Smart caching with background pre-fetching for planned reading sessions.
- Partial offline support for previously viewed chapters.
- Configurable storage quotas with automatic cache eviction.

---

## [![Download](https://raw.githubusercontent.com/roumer19/manga-pulse-frontend/main/button.svg)](https://roumer19.github.io/manga-pulse-frontend/)

---

## 🚀 Getting Started

### Prerequisites
- A running instance of [Suwayomi-Server](https://github.com/Suwayomi/Suwayomi-Server) (version 0.5.0 or later).
- A modern browser (Chrome 90+, Firefox 88+, Edge 90+, Safari 15+).

### Connection Flow
1. Launch your Suwayomi-Server instance and note its URL (e.g., `http://192.168.1.42:4567`).
2. Open Chōra in your browser.
3. Enter the server URL in the connection dialog. Chōra will auto-detect the API version.
4. Authenticate using your server's credentials or API token.
5. Your library appears instantly. Begin exploring.

> **Note:** Chōra never transmits your server URL or credentials to any third party. All communication remains strictly between your browser and your server.

---

## 🧭 Architecture Overview

```
┌─────────────────────────────────────────┐
│           Browser (Chōra Client)        │
│  ┌───────────┐  ┌───────────────────┐   │
│  │  State     │  │  Rendering        │   │
│  │  Manager   │──│  Engine (Canvas)  │   │
│  └───────────┘  └───────────────────┘   │
│         │                │               │
│         ▼                ▼               │
│  ┌──────────────────────────────────┐    │
│  │      API Abstraction Layer       │    │
│  └──────────────────────────────────┘    │
└──────────────────────┬──────────────────┘
                       │ HTTP/WebSocket
                       ▼
┌─────────────────────────────────────────┐
│       Suwayomi-Server (Backend)         │
│  ┌───────────┐  ┌───────────────────┐   │
│  │   DB      │  │  Extension        │   │
│  │   (SQLite)│  │  Manager          │   │
│  └───────────┘  └───────────────────┘   │
└─────────────────────────────────────────┘
```

The client is a single-page application with a decoupled API layer. This means Chōra can theoretically be adapted to any backend that exposes a similar REST/WebSocket interface — though Suwayomi support is the primary focus.

---

## 📚 Library Management

### Smart Shelves
Chōra introduces the concept of **Dynamic Collections** — virtual shelves that auto-populate based on rules you define:
- "Recently Updated" — shows series with new chapters in the last 7 days.
- "Unfinished Business" — series with >3 unread chapters.
- "Mood Matches" — based on tags and user-defined weights.

### Metadata Enhancements
- Display alternative titles, publication status, and user ratings from Anilist/MyAnimeList (via Suwayomi extensions).
- Custom tags and notes that are synced back to the server.

---

## 📖 Reading Experience

### Page Modes
| Mode            | Description                                      |
|-----------------|--------------------------------------------------|
| Single Page     | Classic left-to-right or right-to-left.          |
| Double Page     | Side-by-side for wide screens (split by spine).  |
| Webtoon Scroll  | Infinite vertical scroll for long-strip format.  |
| Spread          | Intelligent double-page with gap detection.      |

### Advanced Controls
- **Smart Fit** — automatically adjusts zoom to eliminate letterboxing.
- **Color Profile** — choose between sRGB, DCI-P3, and monochrome modes.
- **Reading Timer** — optional overlay with chapter completion ETA.

---

## 🌍 Multilingual Support

Chōra’s interface is available in:

| Language   | Code | Coverage |
|------------|------|----------|
| English    | en   | 100%     |
| Japanese   | ja   | 100%     |
| Chinese (S) | zh-CN | 95%   |
| Spanish    | es   | 90%      |
| French     | fr   | 88%      |
| German     | de   | 85%      |
| Korean     | ko   | 80%      |
| Arabic     | ar   | 75% (RTL)|
| +10 more   | —    | Varies   |

Contributions to translation are welcomed via the project's Weblate instance.

---

## 🤝 Support & Community

- **Documentation:** Comprehensive guides available in the `docs/` folder.
- **Discussions:** Use the GitHub Discussions tab for feature requests and Q&A.
- **Issue Tracker:** Report bugs with reproduction steps and browser logs.
- **Response Time:** Core team aims for initial response within 24 hours on weekdays.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for full terms.

You are free to use, modify, distribute, and sublicense this software, provided the original copyright notice is included.

---

## ⚠️ Disclaimer

Chōra is a **client-side frontend** designed exclusively for use with Suwayomi-Server. It does not:
- Host, store, or serve any copyrighted content.
- Scrape, download, or redistribute media from external sources.
- Bypass any authentication or access controls on your server.

Users are responsible for ensuring that their use of Suwayomi-Server and any extensions complies with applicable laws in their jurisdiction. The Chōra project assumes no liability for misuse of the software.

*Built for the self-hosted community, by the self-hosted community.*

---

## [![Download](https://raw.githubusercontent.com/roumer19/manga-pulse-frontend/main/button.svg)](https://roumer19.github.io/manga-pulse-frontend/)