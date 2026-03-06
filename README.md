# LinkedSave — LinkedIn Video & Image Downloader

A static, privacy-first LinkedIn media downloader. No backend, no server, no tracking.

## Features
- Download LinkedIn **videos** and **images** via RapidAPI
- API key stored only in `sessionStorage` (cleared on tab close)
- Content Security Policy, X-Frame-Options, and other security headers
- Rate-limit tracker (soft cap of 10 requests/session)
- URL validation — only accepts valid `https://www.linkedin.com/` URLs
- Zero cookies, zero analytics, zero external scripts

## Setup

### 1. Get a RapidAPI Key
1. Go to [rapidapi.com](https://rapidapi.com)
2. Search for **"LinkedIn Bulk Data Scraper"** (or similar LinkedIn video API)
3. Subscribe to a free or paid plan
4. Copy your `X-RapidAPI-Key`

### 2. Host on GitHub Pages
```bash
git init
git add .
git commit -m "initial"
git remote add origin https://github.com/YOUR_USERNAME/linkedsave.git
git push -u origin main
```
Then go to your repo **Settings → Pages → Source: main / root**.

> ⚠️ GitHub Pages does NOT support the `_headers` file. Use **Netlify** or **Cloudflare Pages** for full security header support.

### 3. Use the App
1. Paste your RapidAPI key in Step 1
2. Select **Video** or **Image** mode
3. Paste a LinkedIn post URL
4. Click **Fetch & Download**

## API Endpoint
The app targets `linkedin-bulk-data-scraper.p.rapidapi.com`.  
If your RapidAPI subscription uses a different host, update the `apiHost` variable in `index.html`:

```js
const apiHost = 'your-api-host.p.rapidapi.com';
```

## Security Notes
- API key is base64-encoded in `sessionStorage` only (not `localStorage`)
- All inputs are validated and sanitized
- CSP blocks inline script injection and unauthorized connections
- No third-party analytics or tracking scripts

## Legal
Use responsibly. Downloading LinkedIn content may violate [LinkedIn's User Agreement](https://www.linkedin.com/legal/user-agreement). Only download content you own or have explicit permission to download.
