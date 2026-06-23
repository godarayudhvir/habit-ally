<div align="center">

# 🌱 Habit Ally

**Master your daily routine — privately, beautifully, for free.**

[![Live App](https://img.shields.io/badge/Live%20App-habit--ally.workflare.in-4ade80?style=for-the-badge&logo=googlechrome&logoColor=white)](https://habit-ally.workflare.in/app)
[![Made with Alpine.js](https://img.shields.io/badge/Alpine.js-3.x-77c1d2?style=for-the-badge&logo=alpinedotjs&logoColor=white)](https://alpinejs.dev/)
[![No Backend](https://img.shields.io/badge/Backend-None-slate?style=for-the-badge)](#)
[![Privacy First](https://img.shields.io/badge/Data-100%25%20Local-6366f1?style=for-the-badge&logo=shieldsdotio&logoColor=white)](#privacy)

![Main Site Thumbnail](/site.webp) 

<br/>

> *Track what matters. Own your data. Build the life you want — one day at a time.*

<br/>

</div>

---

## ✨ What is Habit Ally?

**Habit Ally** is a lightweight, privacy-first habit tracker that lives entirely in your browser. No accounts, no servers, no subscriptions — just you and your goals.

Built as a single HTML file, it runs completely offline after the first load. Your data never leaves your device.

```
Open browser → Track habits → Close tab → Data is still there tomorrow.
That's it. No login. No cloud. No nonsense.
```

---

## 🖼️ Features at a Glance

| Feature | Description |
|--------|-------------|
| 📅 **Monthly Grid View** | See your entire month on one beautiful table |
| 🌓 **Dark Mode Toggle** | Toggle between light and dark themes with system preference sync |
| 🏷️ **Color-Coded Habits** | Assign beautiful, curated color categories (Blue, Emerald, Indigo, Amber, Rose) to habits |
| 📈 **Weight Trend Sparkline** | Dynamic inline SVG sparkline chart visualizing your weight logs over the month |
| 🔔 **Toast Notifications** | Elegant, non-disruptive, animated custom alert popups |
| ✅ **One-click Habit Tracking** | Check off habits with a single click or tap |
| 🔥 **Streak Tracking** | See your current streak, best-ever streak, and total completions per habit |
| ⚖️ **Weight Logger** | Log your daily weight alongside your habits |
| 📊 **Daily Score %** | Each day gets a score based on how many habits you completed |
| 🌱 **Visual Legend** | Emoji-based status icons (💨🌱🌳🌲🍎) for instant progress reading |
| 📈 **Monthly Average** | One number summary of how your month is going |
| 💾 **Export / Import** | Download your data as JSON and restore it anytime |
| 🔒 **100% Private** | Everything stored in `localStorage` — nothing ever sent anywhere |
| ⌨️ **Keyboard Accessible** | Navigate the entire tracker without touching your mouse |

---

## 🚀 Getting Started

### Option 1 — Use the Live App

Just open **[habit-ally.workflare.in/app](https://habit-ally.workflare.in/app)** — no installation needed.

### Option 2 — Self-host in 30 seconds

```bash
git clone https://github.com/workflare-in/habit-ally.git
cd habit-ally
# Open index.html in any browser
open index.html
```

That's it. No `npm install`. No build step. No dependencies to manage.

### Option 3 — Deploy to any static host

Drop `index.html` onto any static host — Netlify, Vercel, GitHub Pages, Cloudflare Pages, or your own server. It's a single file.

```bash
# GitHub Pages example
git add index.html
git commit -m "deploy"
git push origin main
# Enable Pages in repo settings → done
```

---

## 🏗️ How It Works

```
┌─────────────────────────────────────────────────────┐
│                    Your Browser                     │
│                                                     │
│   index.html  ──────►  Alpine.js (reactive state)   │
│      │                        │                     │
│      │                        ▼                     │
│   Tailwind CSS          localStorage                │
│   (styling)          (your private data)            │
│                                                     │
│             Zero network requests after load        │
└─────────────────────────────────────────────────────┘
```

Habit Ally is built on three zero-config technologies:

- **[Alpine.js v3](https://alpinejs.dev/)** — lightweight reactivity directly in HTML attributes
- **[Tailwind CSS](https://tailwindcss.com/)** — utility-first styling via CDN
- **[localStorage API](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)** — persistent, device-local storage

The entire app is **one HTML file** with no build tooling, no backend, and no database.

---

## 📂 Project Structure

```
habit-ally/
├── index.html        ← The entire application (HTML + CSS + JS)
├── README.md         ← You are here
└── LICENSE           ← MIT License
└── site.webp
└── privacy-policy.md
└── terms-of-service.md
```

---

## 🔥 Streak System

Habit Ally tracks three streak metrics per habit, computed entirely from your local check history:

| Metric | Meaning |
|--------|---------|
| **Current streak** | Consecutive days checked up to and including today (or yesterday) |
| **Best streak** | Your all-time longest unbroken run for that habit |
| **Total completions** | All-time count of days you checked this habit |

Streaks are shown inline on every habit row and summarised in the **Streak Overview** table below the main grid.

---

## 💾 Your Data

### Storage format

All data is stored under the key `allyTrackerData` in your browser's `localStorage` as a JSON object:

```json
{
  "grid": {
    "Workout": {
      "2026-03-01": true,
      "2026-03-02": true,
      "2026-03-04": true
    }
  },
  "weights": {
    "2026-03-01": 74.5,
    "2026-03-02": 74.2
  },
  "customHabits": ["Workout", "Reading", "No Junk Food"]
}
```

Date keys use ISO 8601 format (`YYYY-MM-DD`). Any data exported from an older version with non-padded keys (e.g. `2026-3-5`) is automatically migrated on import.

### Export & Import

- **Export** — Downloads a timestamped `.json` file to your device.
- **Import** — Restores any previously exported backup, with automatic legacy key migration.

> ⚠️ Clearing browser data or using a different browser/device means starting fresh — export regularly if your data matters to you.

---

## 🔒 Privacy

Habit Ally is designed with privacy as a hard constraint, not an afterthought.

- ✅ **No account required** — ever
- ✅ **No analytics** — not even anonymous ones
- ✅ **No cookies** — `localStorage` only
- ✅ **No network requests** after the initial page load
- ✅ **No ads** — it's free, open source, and will stay that way
- ✅ **Data stays on your device** — we literally cannot see it

---

## 🛠️ Customising Your Habits

The default habits are a starting point. You can:

**Add a habit** — click `+ Add Habit` in the header, type a name, press Enter.

**Delete a habit** — hover over the habit row, click the `×` button. You'll be asked to confirm — this deletes all history for that habit.

**Reorder habits** — currently managed by the order you add them. (Drag-to-reorder is on the roadmap!)

---

## 🤝 Contributing

Contributions are welcome! Habit Ally is intentionally simple — please keep PRs focused and avoid adding dependencies.

```bash
# Fork → clone → edit index.html → open in browser to test → PR
git fork https://github.com/workflare-in/habit-ally
git checkout -b feature/your-feature-name
# make your changes to index.html
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# Open a Pull Request
```

### Good contributions
- Bug fixes
- Accessibility improvements
- Performance improvements
- New features that don't require a backend or build step

### Out of scope
- Any feature that requires a server, database, or user account
- External npm dependencies
- Build tooling or bundlers

---

## 🗺️ Roadmap

- [ ] Drag-to-reorder habits
- [x] Dark mode
- [x] Habit categories / colour tagging
- [x] Mobile responsive (Yesterday/Today portrait view + Landscape device rotation support)
- [ ] Habit notes / journal per day
- [ ] PWA / installable offline app
- [ ] React Native cross platform app

Have an idea? [Open an issue](https://github.com/workflare-in/habit-ally/issues) — we'd love to hear it.

---

## 📄 License

See [LICENSE](LICENSE) for details.

---

<div align="center">

Built with ❤️ by [Workflare](https://workflare.in/)

[🌐 Live App](https://habit-ally.workflare.in/app) · [🐛 Report a Bug](https://github.com/workflare-in/habit-ally/issues)

</div>