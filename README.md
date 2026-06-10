
# 📘 Exam Tracker Central – Personal Exam Date Manager

A **single‑file HTML/JS/CSS** application to store all important dates for government & private exams – form start/end, exam date, admit card date, advertisement link, notes, and browser‑based reminders.  
No backend, no database setup – runs entirely in your browser and saves data locally.

![Screenshot Placeholder](screenshot.png)  
*(Add a screenshot of the app here for reference)*

---

## 🚀 Features

- **All exam dates in one place**  
  Form start, form end, exam date, admit card release date.
- **Advertisement URL** – store the official notice link.
- **Notes** – eligibility, fee, age limit, etc.
- **LocalStorage persistence** – close and reopen the page, your exams remain.
- **Filter & search** – by Government / Private or by exam name.
- **Countdown indicators** – shows “Exam in X days”, “Form ends soon”.
- **Browser notifications** – get reminded when a date is within 2 days (requires permission).
- **Clean responsive UI** – works on desktop, tablet, and mobile.
- **No installation** – just open the HTML file in any modern browser.

---

## 📁 File Structure

exam-tracker/
├── index.html # The complete app (HTML, Tailwind CSS, JavaScript)
└── README.md # This file


> You can rename `index.html` to anything you like (e.g., `exam-tracker.html`).

---

## 🛠️ How to Use

### Option 1 – Local use (no internet after first load)
1. Download the `index.html` file.
2. Double‑click it – opens in your default web browser.
3. Start adding exams using the form.
4. Data is saved automatically in your browser’s `localStorage`.

### Option 2 – Host on GitHub Pages (for access from anywhere)
1. Create a new **private** GitHub repository.
2. Upload `index.html` to the root.
3. Go to **Settings → Pages** → set source to `main` branch.
4. Your app will be live at `https://<your-username>.github.io/<repo-name>/`.
5. Bookmark the URL – all data stays on **your device** (localStorage is per browser/device).

---

## 🔔 Notifications

- Click the **“Enable Notifications”** button at the top and grant permission.
- The app will send a browser notification for any upcoming date (form end, exam, admit card) that is **within 2 days**.
- Notifications are checked:
  - On page load.
  - Every 6 hours while the page remains open.
- Notifications are **local** – they won’t appear on another device unless you open the page there and enable them.

---

## 📦 Dependencies (all loaded via CDN – no local install)

- [Tailwind CSS](https://tailwindcss.com/) – styling
- [Font Awesome](https://fontawesome.com/) – icons
- [Flatpickr](https://flatpickr.js.org/) – date picker

All are loaded over the network when you open the page. Once cached, the app works offline (except for first load).

---

## 🧹 Data Management

- All exams are stored in `localStorage` under the key `examTracker`.
- To **backup** your data: open browser DevTools (`F12`) → Console → run:
  ```js
  copy(localStorage.getItem('examTracker'));

  This copies the JSON to your clipboard. Save it somewhere safe.

To restore from backup: in the Console run:

```js
localStorage.setItem('examTracker', 'PASTE_YOUR_JSON_HERE');
location.reload();

To clear all data: use the “Clear Storage” button (not present – you can delete each exam manually or run localStorage.removeItem('examTracker') in the Console).

📝 Example Exam Entry
Field	Example Value
Exam Name	SSC CGL 2025
Type	Government
Form Start Date	2025-01-10
Form End Date	2025-02-10
Exam Date	2025-05-15
Admit Card Date	2025-05-01
Advertisement URL	https://ssc.nic.in/notice/cgl-2025
Notes	Age 18-32, Graduation required, fee ₹100
🧪 Browser Compatibility
Works on Chrome, Edge, Firefox, Safari (latest versions).

Notifications require HTTPS when hosted online (GitHub Pages provides HTTPS).
On file:// protocol (local file), some browsers may block notifications – open the file via a local web server (e.g., npx serve .) for full functionality.

🛡️ Privacy
Zero data leaves your device. No backend, no tracking, no analytics.

All data stays in your browser’s localStorage.

If you host it on GitHub Pages, the code is public (if the repo is public) but your personal data remains in your browser, not on GitHub.

🔧 Customisation (Advanced)
To change the reminder window (default 2 days), edit the line inside checkUpcomingDatesAndNotify():

js
if(diffDays >= 0 && diffDays <= 2)   // change 2 to any number
To add more date fields (e.g., “Result Date”), modify the dateFields array in the same function and extend the form HTML accordingly.

📄 License
This project is for personal use only. You are free to modify and use it privately. If you wish to share, please keep the original credits.

❓ Troubleshooting
Problem	Solution
Dates not saving / form resets	Make sure you click Save Exam after filling.
Notifications not showing	Enable them via the yellow button; on file:// use a local web server.
Data lost after clearing browser cache	localStorage is permanent until you clear site data manually. Backup regularly.
Flatpickr not working	Check your internet connection – the library loads from CDN.
Enjoy keeping all your exam dates organised!
Build with vanilla HTML/JS + Tailwind + flatpickr – no frameworks, no complexity.
