# 🌊 Verse of the Day — Ocean Wallpaper

> A living, animated wallpaper that displays a new Bible verse every day — built with HTML & JavaScript, hosted on Vercel, and powered by a free Bible API.

![Ocean Theme](https://img.shields.io/badge/theme-ocean-0a7ea4?style=for-the-badge)
![Hosted on Vercel](https://img.shields.io/badge/hosted%20on-vercel-000000?style=for-the-badge&logo=vercel)
![Wallpaper Engine](https://img.shields.io/badge/wallpaper%20engine-compatible-1b2838?style=for-the-badge&logo=steam)

---

## ✨ Features

- 🌊 **Animated wave layers** rolling across the bottom of the screen
- 🔵 **Abyssal ocean depth** background with layered gradients
- ✨ **180 bioluminescent particles** drifting upward with glowing halos
- 💡 **Caustic light shafts** filtering through the water
- 📖 **Live Verse of the Day** fetched from `labs.bible.org` — updates automatically every day
- 📅 **Today's date** displayed at the bottom
- 🔁 **Offline fallback** verse if the API is unreachable

---

## 📁 Files

```
/
├── index.html      # The entire wallpaper (HTML + CSS + JS in one file)
├── vercel.json     # Vercel routing config
└── README.md       # This file
```

---

## 🚀 Deploy to Vercel

### Step 1 — Push to GitHub

1. Create a new **public** repository on [github.com](https://github.com/new)
2. Upload `index.html` and `vercel.json` to the root of the repo
   - You can drag and drop them directly on the GitHub website

### Step 2 — Connect to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in with your GitHub account
2. Click **"Add New Project"**
3. Select your repository from the list
4. Leave all settings as default — no build configuration needed
5. Click **Deploy**

You'll get a live URL like:
```
https://your-project-name.vercel.app
```

> Every time you push a change to GitHub, Vercel automatically redeploys. No manual steps needed.

---

## 🖥️ Wallpaper Engine Setup (PC)

1. Open **Wallpaper Engine**
2. Click **"Create Wallpaper"** in the bottom left
3. Select **"Web"** as the wallpaper type
4. Paste your Vercel URL (e.g. `https://your-project.vercel.app`)
5. Set **FPS to 10** — the wallpaper is mostly animated subtly, so this saves resources
6. Click **Save** then **Apply**

> Wallpaper Engine reloads the page each time your PC wakes from sleep, so the verse will always be current when you sit down.

---

## 📱 Android Setup (Samsung Galaxy A53)

**Option A — Shortcut (easiest)**
1. Open your Vercel URL in **Chrome**
2. Tap the three-dot menu → **"Add to Home Screen"**
3. This pins it as a PWA-style shortcut you can open anytime

**Option B — Auto wallpaper with Tasker**
1. Install [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm) from the Play Store
2. Create a new **Profile** → Time → set to daily (e.g. 6:00 AM)
3. Create a **Task** with these actions:
   - `Browse URL` → your Vercel link
   - Screenshot the screen
   - `Set Wallpaper` using the screenshot
> This is more advanced but gives you a true daily wallpaper change.

---

## ⌚ Ryze Fit Watch

The Ryze Fit watch doesn't support custom programmatic wallpapers via the web. The easiest workaround is:
1. Open your Vercel URL on your phone
2. Take a screenshot
3. Set it as the watch face photo manually through the Ryze companion app

---

## 🎨 Customising

All styling lives inside the `<style>` block in `index.html`. Key variables at the top:

```css
:root {
  --abyss:      #020d18;   /* Deepest background colour */
  --deep:       #041e35;   /* Mid background */
  --teal:       #0a7ea4;   /* Wave accent */
  --foam:       #7fe8f5;   /* Text accent & ornaments */
  --white-water:#d6f4f9;   /* Main verse text colour */
}
```

To change the **fallback verse** (shown if the API is offline), find this near the bottom of the `<script>` block:

```js
const FALLBACK = {
  text: "He stilled the storm to a whisper; the waves of the sea were hushed.",
  ref:  "Psalm 107:29"
};
```

To change **fonts**, swap out the Google Fonts link in the `<head>`.

---

## 🔌 API

Verse data is fetched from:
- **Primary:** [`labs.bible.org`](https://labs.bible.org/api_web_service) — official Verse of the Day (KJV/NLT)
- **Fallback:** [`bible-api.com`](https://bible-api.com) — date-seeded verse from a curated list

Both are free and require no API key.

---

## 📄 Licence

MIT — free to use, modify, and share.
