# 📘 Exam Tracker Central – Personal Exam Date Manager

A **single‑file HTML/JS/CSS** application to store, track, and manage all key dates for government & private exams – form start/end, exam date, admit card release date, official notices, checklists, and calendar reminders.

No backend, no database setup – runs entirely inside your browser and saves all data locally on your device, with optional cloud backup using GitHub Gists.

---

## 🚀 Key Features

- **Dynamic Theme Palette Switcher**: Choose from 5 sleek color schemes (*Midnight Indigo*, *Forest Jade*, *Crimson Velvet*, *Sunset Amber*, or *Nordic Slate*) to combat color fatigue.
- **Interactive Prep Checklists**: Every exam card includes a collapsible checklist drawer to track preparation steps (e.g., *Fill application*, *Pay fees*, *Download admit card*) and add custom milestones.
- **Cloud Backup & Restore**:
  - Securely upload your local schedule data to a private, secret **GitHub Gist**.
  - Configure your own **GitHub Personal Access Token (PAT)** and Gist ID in the settings modal.
  - Sync and restore your data across multiple devices (laptops, phones) entirely from the browser client.
- **Calendar Integrations**:
  - **Google Calendar (GCal)**: Instantly generate an event in your Google Calendar for your exam date.
  - **iCalendar (.ics) Export**: Download a calendar configuration file to import all dates (registration, deadlines, exams) into Outlook, Apple Calendar, or mobile calendars.
- **Quick Web Updates Search**: Search Google directly for latest news, admit cards, or syllabus changes matching your exam name with a single click.
- **Print & Save as PDF Sheet**: Automatically formats your active exam schedules into a clean, structured table view when printing or saving as a PDF.
- **Stats Dashboard Widget**: View real-time totals of tracked schedules, forms closing within 5 days, and exams scheduled within 7 days.
- **LocalStorage Persistence**: Close and reopen the page; your exams remain stored safely in your browser memory.
- **Deduplicated Browser Notifications**: Get reminded when a date is approaching (configurable alert windows of 1, 2, 5, or 7 days) without duplicate alarm spam on reloads.

---

## 📁 File Structure

```text
exam-tracker/
├── index.html         # The complete app (HTML, Tailwind CSS, JavaScript)
└── README.md          # This file
```

---

## 🛠️ How to Use

### Option 1 – Local use (Offline)
1. Double‑click `index.html` to open it in your web browser.
2. Fill out the form to save exams. Data is saved automatically in your browser's local sandbox memory (`localStorage`).

### Option 2 – Local HTTP Server (To enable desktop notifications locally)
Some browsers block permission prompts over local file protocols. If notifications are blocked:
1. Open terminal in the project directory and run:
   ```bash
   python -m http.server 8000
   ```
2. Navigate to `http://localhost:8000/index.html` in your browser.

### Option 3 – Host on GitHub Pages (Access anywhere on Phone & Laptop)
1. Create a free **private** GitHub repository and upload `index.html` to the root.
2. In your repo, go to **Settings → Pages** and set the source branch to `main`.
3. Your tracker will be live at `https://<your-username>.github.io/<repo-name>/`.
4. Bookmark the URL. All data stays secure on **your device** (localStorage is specific to the browser app/device).

---

## 🧹 Data Management

- All exams are stored locally under the browser storage key `examTracker`.
- **Export Backup**: Click the **Export** button in the header to download a `.json` backup file of all schedules.
- **Import Backup**: Click the **Import** button and select your exported `.json` file to safely merge/restore your exam planner list.
- **Cloud Backup & Restore**:
  1. Click the **Cloud Settings (gear icon)** in the header.
  2. Input your GitHub Personal Access Token (PAT) with the `gist` scope enabled.
  3. Click **Backup** to create (or update) a secret Gist containing your data.
  4. Copy the returned Gist ID to access and restore this backup from another device.
- **Reset Storage**: Click the **Reset** button in the header to wipe all tracker data. This action is guarded by confirmation dialog overlays to prevent accidental data loss.

---

## 📦 CDNs & Dependencies

No local installations are required; dependencies load over CDNs:
- **Tailwind CSS v3** – Styling & Color Palette Variables
- **Font Awesome v6** – Icons
- **Flatpickr** – Calendar Date Selection

Once loaded, the app works offline (using cached assets).
