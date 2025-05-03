## 🧠 AutoSmug Album Scanner

**Educational Tool for API-less Album Scanning**

### 📘 What is this?

This project is a browser-based learning tool that demonstrates how to scan public album data from **SmugMug** **without using an official API**.

It leverages raw HTML responses and extracts embedded `<pre>`-formatted JSON blocks to bypass CORS and token requirements — ideal for **no-API** learning use cases.

> ⚠️ This is **strictly** for educational purposes.

---

### ⚙️ How to Run (Enable CORS-less Mode)
Because this tool fetches data directly from `smugmug.com`, you **must disable CORS in your browser**.

#### 🧩 Chrome (recommended):
1. Close all Chrome windows.
2. Run this command:

   ```bash
   chrome.exe --disable-web-security --user-data-dir="C:/temp/chrome-smug"
   ```

   Or on macOS:

   ```bash
   open -na "Google Chrome" --args --disable-web-security --user-data-dir="/tmp/chrome-smug"
   ```
3. Visit the tool's `index.html` via `file://` or local server (like `http-server`).
4. 
### 🚀 How to Use

1. **Open the tool** (`index.html` in a CORS-less Chrome session).
2. **Enter a keyword** (e.g. `wedding`, `gopro`, `phone`) in the search field.
3. Optionally set a scan **duration** (in minutes).
4. Click **Start Scan** to begin scanning public SmugMug users and albums.
5. Results will appear dynamically, with matched albums listed under each user.

You can:

* Expand/collapse all results.
* Click "Reset Scanned" to clear local storage.
* Resume where you left off – local data is cached per keyword.

---

### 🧠 How It Works

* The tool auto-generates queries (`aaa`, `aab`, etc.).
* For each user found via SmugMug's public search, it fetches their albums.
* It parses the HTML responses to extract JSON from `<pre>` blocks.
* Matches are stored locally to avoid repeated scans.

---

**TheCurator1.0**
