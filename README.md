# Research Command Center

A personal daily planning dashboard for economics researchers. Built as a single HTML file — host on GitHub Pages and use from any computer.

## Features

- **Morning Planning Gate** — Forces you to set Big 5 priorities with time allocations before you start working
- **Google Calendar Sync** — Live day/week view of your calendar, with NOW/NEXT badges and 10-minute meeting alerts
- **Day Timer** — Track total working hours from start to end of day
- **Task Tracker** — Tick off completed tasks or reschedule to another day (auto-creates Google Calendar event)
- **End of Day Review** — Log what happened, what blocked you, and tomorrow's #1 focus
- **Yesterday's Notes** — Previous day's closing notes appear as a banner so you pick up where you left off
- **Editable Links** — Customize your Google Docs links, research databases, and tools
- **Focus Principles** — Built-in reminders for deep work habits

## Setup

### 1. Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g., `research-dashboard`)
2. Upload `index.html` to the repo
3. Go to **Settings → Pages → Source** → select `main` branch
4. Your dashboard will be live at `https://yourusername.github.io/research-dashboard/`

### 2. Customize Your Links

Click **EDIT** in the "My Docs & Links" section to add your actual Google Doc URLs. Changes persist in your browser's localStorage.

### 3. Calendar Integration

The dashboard uses Claude's API with Google Calendar MCP to sync your calendar. This works when accessed from claude.ai artifacts. For standalone hosting, you may need to set up your own Google Calendar API integration.

## How to Use

### Morning Ritual (2 min)
1. Open the dashboard
2. Fill in your Big 5 priorities + time allocations
3. Write your deep intention for the day
4. Click "Start Working" — timer begins

### During the Day
- Check calendar for upcoming meetings (alerts pop up 10 min before)
- Tick off tasks as you complete them
- Reschedule incomplete tasks → creates calendar event automatically
- Use Quick Notes for ideas and scratch work

### End of Day (2 min)
1. Click "End Day"
2. Write what happened and what blocked you
3. Set tomorrow's #1 focus
4. Save — notes appear tomorrow morning

## File Structure

```
index.html    ← Everything in one file. That's it.
```

## Data Storage

All data is stored in `localStorage` — it persists across browser sessions on the same computer. Data is keyed by date, so each day starts fresh while preserving yesterday's review notes.

## License

MIT — use however you want.
