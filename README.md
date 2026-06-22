# TaskFlow v7.0

A comprehensive, single-file, offline-capable personal productivity web app built for shift workers, analysts, and BI/Excel developers. TaskFlow runs entirely in your browser — no backend, no install, no tracking.

![Version](https://img.shields.io/badge/version-7.0-6366F1) ![Status](https://img.shields.io/badge/status-stable-10B981) ![License](https://img.shields.io/badge/license-MIT-blue) ![PWA](https://img.shields.io/badge/PWA-ready-A78BFA)

> **Single HTML file. Zero dependencies. Works offline. Syncs across devices.**

---

## Live Demo

[Open TaskFlow →](./index.html)

Or host it on **GitHub Pages**: just rename the file to `index.html`, push to a repo, and enable Pages in **Settings → Pages**.

---

## Highlights

- **Schedule** — Tasks, recurring tasks, one-time tasks, reminders, smart timeline
- **Meetings** — Auto-extracts Teams / Zoom / Google Meet links, attendees, MoM generator
- **Developments** — Power BI / Excel / Automation project tracker with phases, logs, blockers, screenshots, and meeting links
- **Reports Directory** — Library of reports with primary / backup owners and one-click cover-task creation
- **Leave Tracker** — Personal VL / SL balance with LILO auto-sync
- **LILO Attendance** — Monthly attendance tracker with CSV export to Scorecard format
- **Expenses** — WFO money manager with budget, categories, tags, location auto-fill
- **Dashboard** — 12+ customizable widgets, drag-to-rearrange
- **AI Agent** — Daily briefings, risk alerts, smart suggestions, weekly review
- **Cloud Sync** — Backup/restore to private GitHub Gist with optional 2-way auto-sync
- **Markdown** — Live preview editor in Notes, Meeting Notes, and Dev logs
- **9 Themes** — Default Dark/Light, AMOLED, Catppuccin, Nord, Dracula, Tokyo Night, Gruvbox, Solarized
- **Accessibility** — High contrast, dyslexia-friendly mode, full keyboard navigation
- **Filipino UI** — One-click EN ↔ Tagalog toggle

---

## Features

### Productivity Core

| Module | What it does |
|--------|--------------|
| Schedule | Today / Tomorrow / NWD / All / Overdue views with shift-aware (4 PM – 4 AM) date handling |
| Recurring tasks | Daily, weekdays, weekly, monthly, custom day patterns; with end-date and start-date |
| One-time tasks | Dependencies, "waiting on" follow-up tracker, time spent timer |
| Meetings | Pattern-detected video links, attendee extraction, MoM generator → creates action-item tasks |
| Reports | Owner roster (primary + 2 backups), category icons, multi-link support |
| Leave | Annual credits per type, auto-sync with LILO (VL→PTO, SL→Sick), team leave + cover reports |
| LILO | Monthly attendance with regenerate, inline edit, status badges, CSV export |
| Expenses | Per-category budget, payment methods, tags, location auto-detect from LILO |
| Developments | 14-step phase templates (Power BI / Excel / Automation), progress %, activity log, blockers, screenshot paste, linked meetings |
| Templates | Message templates with `{{person}}`, `{{report_name}}` variables; step templates |

### Smart UX

- **Universal Search** (`Ctrl+K`) — Search tasks, meetings, devs, reports, expenses, leave, notes, templates — all at once
  - Filters: `priority:urgent`, `due:today`, `type:meeting`, `bu:claims`
- **Quick Capture bar** — Type anywhere:
  - `Refresh dashboard at 3pm high` → task
  - `/meeting Stakeholder review` → meeting
  - `/dev New Claims Dashboard` → development
  - `₱120 lunch at Jollibee` → expense
  - `/remind submit timesheet` → reminder
  - `/note follow up with John` → quick note
- **Voice commands** — `Add task review SLA at 3pm high priority`
- **AI Assistant** (`Alt+G`) — GPT-style chat connected to local data
- **Mission Card** — Top-of-page hero with greeting, progress ring, "Next Up" task, streak chip
- **Smart Suggestions** — Detects patterns ("You usually do X on Tuesdays — add it today?")
- **Weekly Review** — Auto-Sunday productivity summary

### Power Features

- **Markdown everywhere** — Notes, Meeting Notes, Dev descriptions/logs (bold, italic, headers, lists, code, links)
- **Smart Paste** — Paste from Word / Outlook / Excel → auto-converted to Markdown
- **Soft delete + Undo** — 10-second undo toast + 30-day trash bin
- **Health Check** — Validates data integrity, suggests auto-fixes
- **Carry-Forward** — Auto / Ask / Manual modes to move overdue tasks to today
- **Habit tracker** — Separate from tasks, with streak counts
- **16 Achievement badges** — Streaks, milestones, voice usage, theme exploration, etc.
- **Command Dock** — Floating FAB with quick actions (Add, Search, AI, Chat, Help, Settings)
- **Right-click / Long-press** — Context menu on tasks (Complete, Edit, Duplicate, Pin, Snooze, Delete)

### Customization

- **Density modes** — Comfortable / Cozy / Compact
- **Experience levels** — Beginner / Standard / Advanced (hides modules for less clutter)
- **Page Layout** — Toggle any section (KPIs, Mission, Goals, Quick Capture bars, etc.) per page
- **Module visibility** — Disable any module from sidebar
- **Sidebar pinning** — Star nav items to top
- **Workspaces** — Switch between completely separate data contexts

### Sync & Backup

- **Local backup** — Selective export/import per module
- **GitHub Gist sync** — Private cross-device sync (push, pull, auto, both ways)
- **Conflict detection** — Banner appears when remote has newer data
- **CSV export** — Tasks, Expenses, LILO, Leave, Dev projects

### PWA

- **Installable** — Add to Home Screen on iOS / Android / desktop
- **Offline-first** — Service worker caches the entire app
- **App badge** — Pending task count appears on app icon
- **Push notifications** — Shift start/end alerts, task reminders

---

## Quick Start

### Option 1 — Run locally (zero setup)

1. Download `index.html`
2. Double-click to open in any modern browser (Chrome, Edge, Safari, Firefox)
3. Click **Install** (Chrome) or **Add to Home Screen** (mobile) for app-like experience

### Option 2 — Host on GitHub Pages (recommended for sync)

```bash
git init
git remote add origin https://github.com/<your-username>/<your-repo>.git
# rename file so GitHub Pages serves it as the home page
mv index.html index.html
git add index.html README.md
git commit -m "Initial TaskFlow deploy"
git push -u origin main
```

Then go to **repo → Settings → Pages → Source: main / root → Save**. Your TaskFlow will be live at `https://<your-username>.github.io/<your-repo>/`.

### Option 3 — Host on Netlify / Vercel

Drag-and-drop the HTML file into Netlify Drop, or import the repo into Vercel. No build step needed.

---

## Cross-Device Sync Setup

TaskFlow uses your own private GitHub Gist as a sync backend — no third-party servers, no accounts, you own your data.

1. Create a **fine-grained Personal Access Token** at [github.com/settings/tokens](https://github.com/settings/tokens?type=beta) with **gist: read & write** scope
2. In TaskFlow: open **Admin Center → Cloud Sync → Configure**
3. Paste your token, click **Test Token**
4. Click **⬆️ Push to Gist** — this creates a new private gist
5. On a second device: open TaskFlow, configure sync, paste the **same token + the gist ID** from device 1
6. Click **⬇️ Pull from Gist** to restore
7. Enable **Auto-Sync (Both ways)** for continuous sync

> **Privacy:** Your token is stored in `localStorage` only. The gist is private. No telemetry, no external servers.

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+K` / `Cmd+K` | Universal search / Command palette |
| `Alt+N` | Quick Add task |
| `Alt+G` | Open AI Assistant |
| `Alt+/` | Show all shortcuts |
| `Alt+F` | Toggle Focus Mode |
| `Alt+D` | Toggle dark/light theme |
| `Alt+E` | Quick export backup |
| `?` or `F1` | Open Help Center |
| `/` | Focus search bar |
| `Esc` | Close any modal |
| `Swipe ←` (mobile) | Mark task done |
| `Swipe →` (mobile) | Edit task |
| `Long-press` (mobile) | Context menu on task |

---

## Tech Stack

- **One file. Zero dependencies. No build step.**
- Vanilla HTML / CSS / JavaScript (no frameworks)
- `localStorage` for persistence (~5–10 MB limit, with auto-purge of old trash)
- Service Worker for offline support
- Web APIs: `SpeechRecognition`, `SpeechSynthesis`, `Notification`, `setAppBadge`, `Web Share Target`
- GitHub Gist REST API for cloud sync
- Single-file PWA — works fully offline after first load

### Architecture (v7.0)

All code is namespaced under the global `TF` object:

```js
TF.storage     // Preferences storage
TF.util        // Helpers (debounce, escape, toast, $, $$)
TF.icons       // 54 Lucide icons + emoji-to-icon replacement
TF.layout      // Density, level, sticky headers, sidebar fold
TF.forms       // Mobile keyboard detection, smart scroll
TF.paste       // HTML → Markdown auto-conversion
TF.gist        // GitHub Gist push / pull / test
TF.autoSync    // Multi-device sync orchestration
TF.dock        // Command dock (FAB cluster)
TF.ctx         // Right-click / long-press context menu
TF.prefs       // Layout preferences modal
TF.changelog   // What's New viewer
TF.observer    // Efficient DOM watcher (replaces polling)
TF.boot        // Bootstrap entry point
```

---

## Roadmap

- [ ] End-to-end encrypted sync (E2EE backup payload before gist push)
- [ ] Calendar feed import (.ics → tasks)
- [ ] Mobile-native app via Capacitor wrapper
- [ ] Team sharing (read-only public links)
- [ ] Plugin system for custom modules
- [ ] Outlook / Google Calendar 2-way sync

---

## Privacy & Data Ownership

- **All data lives in your browser's `localStorage`** — never sent to any server unless you configure cloud sync
- **Cloud sync is opt-in** and uses **your own** private GitHub Gist
- **No analytics, no telemetry, no tracking pixels**
- **Open source** — read every line of code before trusting it

To wipe everything: Admin Center → Backup & Restore → Danger Zone → Reset All Data

---

## Contributing

This is a personal productivity tool, but PRs are welcome for:

- Bug fixes (especially mobile / iOS Safari)
- Accessibility improvements
- New theme presets
- Localization (currently EN + Filipino)
- New widget types for the Dashboard

Please test in Chrome, Safari, and Firefox before submitting.

---

## License

MIT License — see [LICENSE](./LICENSE) for full text.

> You are free to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software. No warranty.

---

## Credits

- **Icons:** [Lucide](https://lucide.dev/) (MIT)
- **Font:** [Inter](https://rsms.me/inter/) by Rasmus Andersson
- **Themes:** Inspired by Catppuccin, Nord, Dracula, Tokyo Night, Gruvbox, Solarized
- **Built by:** Mark Rusco — for shift-working BI analysts everywhere 🌙

---

## Support

- **In-app:** Click `?` (Help Center) — full searchable documentation
- **Issues:** Open a [GitHub issue](../../issues)
- **Questions:** Use [GitHub Discussions](../../discussions)

---

**Made with ☕ and Markdown. Star ⭐ this repo if TaskFlow helps you ship more, stress less.**
