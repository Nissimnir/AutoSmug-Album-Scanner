## 🧠 AutoSmug Album Scanner

[https://www.smugmug.com/](https://www.smugmug.com/)

**Educational Tool for High-Scale No-API Album Scanning (IndexedDB Edition)**

---

### 📘 What is this?

This is a browser-based educational tool that demonstrates how to **scan and index public albums on SmugMug without using the official API**.

Unlike the original version, this version uses **persistent IndexedDB storage** to:

* Store all scanned user and album data
* Enable instant re-filtering without re-scanning
* Support long-running and resumable sessions

> ⚠️ For educational and research purposes only.

---

### ⚙️ How to Run (Enable CORS-less Mode)

Because this tool fetches data directly from `smugmug.com`, you **must disable CORS**.

#### 🕉 Chrome (recommended):

1. Close all Chrome windows.

2. Run this command:

   ```bash
   chrome.exe --disable-web-security --user-data-dir="C:/temp/chrome-smug"
   ```

   On macOS:

   ```bash
   open -na "Google Chrome" --args --disable-web-security --user-data-dir="/tmp/chrome-smug"
   ```

3. Open `index.html` via `file://` or a local server (e.g. `http-server`)

---

### 🚀 How to Use

#### Upper Section — Scanner Control:

* **Start Scan**: Begins scanning public users, generating queries (`aaa`, `aab`, ...).
* **Scan Duration**: Optional timer (in minutes) to auto-stop.
* **Reset Scanned**: Clears current memory (IndexedDB remains).
* **Clear Everything**: Resets all local state: DB, localStorage, and memory.
* **Refresh Upload Dates**: Updates only the latest upload date of existing users.
* **Refresh All Data**: Fully updates all albums and upload times of existing users.
* Real-time **log output** and **session statistics** displayed.

#### Lower Section — Album Filter View:

* Search input for filtering albums locally by keyword.
* Results are sorted by **last upload date**, newest first.
* Expand/Collapse all users.
* Live stats: users in DB, albums, and how many matched.

---

### 🧠 How It Works

* Uses brute-force query generation (`aaa`, `aab`, …) to discover public users.
* Parses `<pre>`-encoded JSON blocks from HTML (SmugMug outputs structured data this way).
* Stores results in IndexedDB to avoid redundant queries.
* Albums and metadata (including `DateTimeUploaded`) are fetched per user.
* UI is split between **background scanner** and **frontend explorer**.

---

### 📂 Persistence & Resume

* Scanned data persists in the browser via IndexedDB.
* You can stop, refresh, pause/resume, or restart at any time.
* Scanning resumes from the last query point automatically.
* Each "Refresh" operation can be paused/resumed mid-process.

---

**TheCurator1.0**
