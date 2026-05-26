# PathMap — Build Your Own APK

This folder contains everything needed to build PathMap as an Android APK using GitHub Actions. No Android Studio, no SDK install on your machine required.

---

## 📁 What's Inside

```
pathmap-apk/
├── www/
│   └── index.html          ← The complete PathMap app
├── .github/
│   └── workflows/
│       └── build-apk.yml   ← GitHub Actions build script
├── capacitor.config.json   ← App ID, name, settings
├── package.json            ← Capacitor dependencies
└── README.md               ← This file
```

---

## 🚀 Steps to Get Your APK

### Step 1 — Create a GitHub account (if you don't have one)
Go to https://github.com and sign up. It's free.

### Step 2 — Create a new repository
1. Click **+** → **New repository**
2. Name it `pathmap` (or anything you like)
3. Set it to **Public** (required for free Actions minutes)
4. Click **Create repository**

### Step 3 — Upload these files
Option A — Drag & drop (easiest):
1. Open your new empty repository
2. Click **uploading an existing file**
3. Drag the entire contents of this zip into the browser
4. Click **Commit changes**

Option B — Git (if you know git):
```bash
git init
git remote add origin https://github.com/YOUR_USERNAME/pathmap.git
git add .
git commit -m "Initial commit"
git push -u origin main
```

### Step 4 — Watch it build
1. Go to your repository on GitHub
2. Click the **Actions** tab
3. You'll see **Build PathMap APK** running (takes ~3–5 minutes)
4. Wait for the green ✅ checkmark

### Step 5 — Download your APK
1. Click the completed workflow run
2. Scroll down to **Artifacts**
3. Click **PathMap-debug** to download a zip
4. Unzip it — inside is `app-debug.apk`

---

## 📲 Install the APK on Your Phone

1. Transfer `app-debug.apk` to your Android phone (via USB, Google Drive, email, etc.)
2. On your phone, go to **Settings → Security → Install unknown apps**
3. Allow your file manager or browser to install APKs
4. Open the APK file and tap **Install**
5. PathMap is now on your home screen!

---

## 🔄 Updating the App

When you want to update PathMap with a new version:
1. Replace `www/index.html` with the new file
2. Push the change to GitHub (or re-upload)
3. A new build starts automatically
4. Download and install the new APK (Android will update the existing install)

---

## ⚙️ Customise App Settings

Edit `capacitor.config.json` to change:
- `appId` — unique identifier, e.g. `com.yourname.pathmap`
- `appName` — the name shown under the icon on your phone

---

## ❓ Troubleshooting

**Build fails with Gradle error:**
→ Try re-running the workflow from the Actions tab (click **Re-run all jobs**)

**APK won't install ("Parse error"):**
→ Make sure your phone is running Android 7.0 (API 24) or higher

**"Unknown sources" warning:**
→ Normal for debug APKs. Follow the install steps above.

---

## 📝 Notes

- The APK built is a **debug** build — perfectly fine for personal use.
- All your data is stored **locally on your device** using localStorage.
- No internet connection needed after install.
- The app works fully offline.
