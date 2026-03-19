# Research Command Center

A personal daily planning dashboard for economics researchers. Single HTML file — host on GitHub Pages, use from any computer.

## Features

- **Morning Planning Gate** — Set Big 5 priorities with time allocations before you start
- **Google Calendar Sync** — Live day/week view with NOW/NEXT badges and 10-min meeting alerts
- **Day Timer** — Track total working hours from start to end of day
- **Task Tracker** — Complete tasks or reschedule them (auto-creates Google Calendar event)
- **End of Day Review** — Log what happened and set tomorrow's focus
- **Obsidian Integration** — Plans and reviews auto-save as daily notes in your vault
- **Yesterday's Notes** — Previous day's closing notes appear each morning
- **Editable Links** — Customize your Google Docs and research database links

## Quick Start

### 1. Create GitHub Repo
1. Create a new repo (e.g., `research-dashboard`)
2. Upload `index.html`
3. **Settings → Pages → Source** → `main` branch
4. Live at `https://yourusername.github.io/research-dashboard/`

### 2. Set Up Google Calendar API (5 min)
1. Go to [Google Cloud Console](https://console.cloud.google.com/apis/credentials)
2. Create a project → **+ CREATE CREDENTIALS → OAuth client ID → Web application**
3. Add **Authorized JavaScript origins**:
   - `https://yourusername.github.io`
   - `http://localhost` (for local testing)
4. Add same URLs under **Authorized redirect URIs**
5. Copy the **Client ID**
6. Enable [Google Calendar API](https://console.cloud.google.com/apis/library/calendar-json.googleapis.com)
7. Go to **OAuth consent screen** → Add your email as test user

### 3. Configure Dashboard
Open the dashboard — paste your Client ID, enter your Obsidian vault name, done.

## Security

**This repo can be public.** Here's why:
- The Client ID is designed to be public (Google expects it in client-side code)
- OAuth consent screen controls who can authenticate
- Your calendar data flows directly from Google → your browser (never touches GitHub)
- All task/note data is in your browser's `localStorage`
- No server, no backend, no data collection whatsoever

**What your Client ID cannot do alone:**
- It cannot read anyone's calendar without their explicit OAuth consent
- It cannot be used without the matching authorized origin URL
- Google rate-limits and monitors all API usage

## Obsidian Integration

The dashboard saves notes to your vault using Obsidian's URI protocol:
- **Morning plan** → `Daily Notes/2026-03-19.md` (auto-saved when you submit)
- **End of day review** → Same file, overwritten with full day summary
- **Quick notes** → Appended to the same daily note

Make sure Obsidian is running on the same machine. Create a `Daily Notes` folder in your vault.

## File Structure

```
index.html    ← Everything. That's the whole app.
README.md     ← This file.
```

## Data Storage

All data lives in `localStorage` — persists across sessions on the same browser. Each day starts fresh. Yesterday's review notes carry over as a banner.

Note: Since data is in localStorage, it's per-browser. If you use multiple computers, your tasks won't sync between them (but your calendar will, since that's from Google). Obsidian Sync or a cloud-synced vault handles the notes side.

## License

MIT
