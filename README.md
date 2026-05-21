<div align="center">

# 🔀 GitFlux — Deploy & Merge Tracker

**A privacy-first, zero-dependency dashboard for tracking Git merges, deploys, and repository activity across GitHub & GitLab.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Single File](https://img.shields.io/badge/Architecture-Single_File-green.svg)](#architecture)
[![No Server](https://img.shields.io/badge/Server-None_Required-orange.svg)](#getting-started)

[Live Demo](#demo-mode) · [Features](#-features) · [Getting Started](#-getting-started) · [Keyboard Shortcuts](#-keyboard-shortcuts) · [Security](#-security)

</div>

---

## 📖 Overview

GitFlux is a **single-file HTML application** that gives you a complete overview of your Git workflow — merges, deploys, branches, and contributors — all from one beautiful dashboard. It connects directly to the **GitHub** and **GitLab** APIs, stores everything locally in your browser, and encrypts your tokens with **AES-GCM 256-bit** encryption.

No servers. No databases. No sign-ups. Just open the file and go.

---

## ✨ Features

### 📊 Dashboard
- **Activity chart** — 14-day bar chart showing daily event volume
- **Event breakdown** — Donut chart by type (commits, merges, deploys, tags, PRs/MRs, branches)
- **Environment breakdown** — See activity distribution across dev, QA, staging, UAT, and production
- **Top active branches** — Quickly identify where work is happening
- **Recent merges & deploys** — At-a-glance feed of the latest activity
- **Commit heatmap** — 12-week GitHub-style heatmap of commit activity

### 📋 Activity Log
- **Table view** — Sortable, searchable table of all events with project, branch, type, message, and environment columns
- **Timeline view** — Chronological timeline grouped by day with visual indicators
- **Advanced filtering** — Filter by type, environment, source (GitHub/GitLab/Manual), and date range
- **Full-text search** — Search across projects, branches, commit messages, and authors
- **Export** — Download your data as **Markdown**, **JSON**, or **CSV**

### 🔀 Merge Tracker
- **Merge flow** — Visual timeline showing source → target branch merge patterns with project tags
- **Merge matrix** — Interactive grid showing merge counts between branch pairs
- **Pending promotions** — Identify branches that haven't been promoted to the next environment
- **Branch lifecycle** — Track branches through dev → QA → staging → production progression
- **Git log parser** — Paste `git log` output directly to import merge data
- **Merge search** — Search and filter merge events by branch name or commit message
- **Export report** — Generate and download a full merge report

### 📁 Repositories
- **Repository cards** — View all connected repos with descriptions, languages, and stats
- **Visibility badges** — Easily distinguish private vs. public repos
- **Sidebar navigation** — Quick-access repo list with source indicators

### 📈 Analytics
- **Top contributors** — Leaderboard with commit counts and activity bars
- **Activity by author** — Visual breakdown of each contributor's work
- **Environment comparison** — See which branches are deployed to which environments
- **Stale branches** — Identify branches with no recent activity
- **Data backup & restore** — Export/import full backups as JSON (tokens excluded for security)

### 🎨 Design & UX
- **Dark mode** — Full dark theme with smooth transitions
- **Responsive layout** — Sidebar + main content grid layout
- **Micro-animations** — Subtle transitions on rows, cards, bars, and interactive elements
- **Custom scrollbars** — Sleek, minimal scrollbar styling
- **Toast notifications** — Non-intrusive feedback for actions
- **Demo mode** — Preview the UI with sample data before connecting real accounts

---

## 🚀 Getting Started

### Quick Start

1. **Clone the repo:**
   ```bash
   git clone https://github.com/nadim-chowdhury/gitflux-git-merge-tracker.git
   cd gitflux-git-merge-tracker
   ```

2. **Open the file:**
   Simply open `gitflux-v5.html` in any modern browser — no build step, no server required.

3. **Connect your accounts:**
   - **GitHub** — Enter a [Personal Access Token](https://github.com/settings/tokens) with `repo` and `read:user` scopes
   - **GitLab** — Enter a [Personal Access Token](https://gitlab.com/-/user_settings/personal_access_tokens) with `read_api`, `read_user`, and `read_repository` scopes

That's it! GitFlux will start syncing your repositories and events automatically.

### Try Demo Mode

Click the **Demo** button in the header to load sample data and explore the UI without connecting any accounts.

---

## ⌨ Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `⌘/Ctrl + K` | Focus search |
| `⌘/Ctrl + N` | New log entry |
| `⌘/Ctrl + Enter` | Save entry |
| `⌘/Ctrl + S` | Sync all sources |
| `Esc` | Close modal |
| `1` | Dashboard view |
| `2` | Activity Log view |
| `3` | Merge Tracker view |
| `4` | Repositories view |
| `5` | Analytics view |
| `D` | Toggle dark mode |
| `?` | Show shortcuts |

---

## 🔒 Security

GitFlux takes your token security seriously:

- **AES-GCM 256-bit encryption** — Tokens are encrypted using the Web Crypto API before storage
- **PBKDF2 key derivation** — A unique encryption key is derived from your device fingerprint with 100,000 iterations
- **100% local storage** — All data stays in your browser's `localStorage`. Nothing is sent to any external server
- **No plaintext tokens** — Tokens are never stored unencrypted
- **Backup safety** — Exported backups deliberately exclude tokens

> ⚠️ **Note:** Tokens are used exclusively for read-only API calls to GitHub/GitLab. GitFlux never writes to your repositories.

---

## 🏗 Architecture

GitFlux is intentionally built as a **single HTML file** (~188 KB) with zero external dependencies beyond fonts and icons:

```
gitflux-v5.html
├── <head>
│   ├── Google Fonts (DM Sans, DM Mono)
│   ├── Font Awesome 7 (icons)
│   └── <style> — Full CSS design system with:
│       ├── CSS custom properties (theming)
│       ├── Light & dark mode variables
│       ├── Grid/flexbox layouts
│       └── Animations & transitions
│
├── <body>
│   ├── Header (logo, navigation, sync status, actions)
│   ├── Sidebar (source connections, filters, repo list)
│   ├── Main content (5 switchable views)
│   ├── Footer (author info, social links)
│   └── Modals (log entry, settings, shortcuts)
│
└── <script> — Application logic:
    ├── CRYPTO module (AES-GCM encryption)
    ├── State management (localStorage)
    ├── GitHub API integration
    ├── GitLab API integration
    ├── Dashboard charts & visualizations
    ├── Merge tracking engine
    ├── Git log parser
    ├── Export functions (MD, JSON, CSV)
    └── Auto-refresh system
```

### Tech Stack

| Layer | Technology |
|-------|-----------|
| Structure | HTML5 semantic markup |
| Styling | Vanilla CSS with custom properties |
| Logic | Vanilla JavaScript (ES2020+) |
| Typography | [DM Sans](https://fonts.google.com/specimen/DM+Sans) & [DM Mono](https://fonts.google.com/specimen/DM+Mono) |
| Icons | [Font Awesome 7](https://fontawesome.com/) |
| Encryption | Web Crypto API (AES-GCM) |
| Storage | Browser localStorage |

---

## ⚙️ Settings

Access settings via the ⚙ gear icon in the header:

| Setting | Options | Default |
|---------|---------|---------|
| Dark Mode | On / Off | Off |
| Refresh Interval | 1, 3, 5, 10, 15 minutes | 5 minutes |
| Max Entries | 1K, 2.5K, 5K, 10K | 5,000 |

---

## 📤 Data Export

GitFlux supports multiple export formats:

| Format | Description | Use Case |
|--------|-------------|----------|
| **Markdown** | Human-readable activity log | Documentation, changelogs |
| **JSON** | Structured data export | Integration, backup |
| **CSV** | Spreadsheet-compatible | Excel, Google Sheets analysis |
| **Merge Report** | Focused merge flow summary | Sprint reviews, audits |
| **Full Backup** | Complete data snapshot (no tokens) | Device migration, disaster recovery |

---

## 🖥 Browser Support

GitFlux requires a modern browser with Web Crypto API support:

- ✅ Chrome / Edge 90+
- ✅ Firefox 90+
- ✅ Safari 15+
- ✅ Opera 76+

---

## 👤 Author

**Nadim Chowdhury**

- 🌐 [Portfolio](https://nadim.vercel.app)
- 🐙 [GitHub](https://github.com/nadim-chowdhury)
- 💼 [LinkedIn](https://linkedin.com/in/nadim-chowdhury)
- 🐦 [X (Twitter)](https://x.com/aspect_dev)
- 📺 [YouTube](https://youtube.com/@aspect-developer)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

<div align="center">

**Built with ❤️ by [Nadim Chowdhury](https://nadim.vercel.app)**

*If you found this useful, give it a ⭐ on GitHub!*

</div>
