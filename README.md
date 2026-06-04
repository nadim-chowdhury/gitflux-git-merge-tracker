# 🔀 GitFlux

**A simple, single-file dashboard to track your Git merges, deploys, and DORA metrics without the overhead.**

GitFlux is a privacy-first, zero-dependency tool designed for developers who want a clear view of their workflow across GitHub and GitLab. No servers, no databases, and no sign-ups. It’s just one HTML file that runs entirely in your browser.

---

## Why GitFlux?

I built this because tracking merges and promotions across different environments and platforms is often a headache. Most tools are either too complex, require a server, or compromise your privacy.

GitFlux connects directly to your repository APIs, stores everything locally (encrypted), and gives you a beautiful dashboard in seconds. Whether you're tracking a hotfix to production or monitoring your team's DORA metrics, GitFlux makes it easy.

## 🚀 Key Features

- **Single-File Architecture:** Zero dependencies. Just open `gitflux-v5.html` and you're good to go.
- **Privacy First:** Your API tokens are encrypted with AES-GCM (256-bit) and stored only in your browser's `localStorage`. Nothing ever leaves your machine.
- **DORA Metrics:** Automatically calculate Deployment Frequency, Lead Time for Changes, Change Failure Rate, and MTTR.
- **Merge Tracker:** Visualize the flow of branches and see exactly what’s waiting to be promoted to production.
- **Promotion Tracing:** Follow the lifecycle of a single commit from the first merge all the way to the final deploy.
- **Multi-Source:** Seamlessly track activity across both GitHub and GitLab in one unified view.
- **Git Log Parser:** Don't have API access? Just paste your `git log` output to import data manually.

---

## 🛠 Getting Started

1.  **Clone the repo** (or just download the HTML file):
    ```bash
    git clone https://github.com/nadim-chowdhury/gitflux-git-merge-tracker.git
    ```
2.  **Open it:** Double-click `gitflux-v5.html` in your browser.
3.  **Connect:** Add your GitHub or GitLab Personal Access Tokens.
    - _Note: These are only used for read-only API calls and are stored locally._

### Pro Tip: Demo Mode

Not ready to connect your accounts? Click the **Demo** button in the header to see how everything looks with sample data.

---

## ⌨ Keyboard Shortcuts

I use these constantly to speed up my workflow:

- `Ctrl + K`: Quick search
- `1` through `5`: Switch between views (Dashboard, Log, Merge Tracker, etc.)
- `D`: Toggle Dark Mode
- `S`: Sync everything
- `?`: Show all shortcuts

---

## 🔒 Security

Security isn't an afterthought here.

- **Local-Only:** Your data stays in your `localStorage`.
- **Encryption:** Tokens are never stored in plaintext. We use the Web Crypto API to keep them safe.
- **Read-Only:** GitFlux never asks for write permissions. It only reads your activity to build the dashboard.

---

## 📤 Export & Backup

Your data belongs to you. You can export everything as:

- **Markdown** (perfect for changelogs)
- **JSON / CSV** (for your own analysis)
- **Full Backup** (migrating to a new device? Just export and import).

---

## 👤 About the Author

Hey, I'm **Nadim Chowdhury**. I build tools that make the developer experience just a little bit better.

- 🌍 [Website](https://nadim.vercel.app)
- 🐙 [GitHub](https://github.com/nadim-chowdhury)
- 🐦 [X / Twitter](https://x.com/aspect_dev)

---

## 📄 License

This project is open-source under the [MIT License](LICENSE). Feel free to fork it, break it, and make it your own!

---

<div align="center">
Built with ❤️ by Nadim Chowdhury. If this helped you, drop a ⭐ on the repo!
</div>
