# GIP EEE FaceAttend — Setup & Hosting Guide

## Why the camera wasn't working
Your phone was opening the file from Downloads using a `content://` or `file://` address.
Android and iPhone **BLOCK camera access** for local files — it only works on proper `https://` websites.

## Solution: Host it FREE in 5 minutes (Netlify Drop)

### Step 1 — Upload the folder
1. On your computer, go to: https://app.netlify.com/drop
2. Drag and drop the entire `faceattend-pwa` FOLDER onto the page
3. Wait ~30 seconds — Netlify gives you a FREE link like: `https://amazing-name-123.netlify.app`

### Step 2 — Open on your phone
1. Open that `https://` link in Chrome (Android) or Safari (iPhone)
2. Camera will now work because it's a real `https://` address
3. Allow camera when prompted

### Step 3 — Install as an App (No App Store needed!)
**Android Chrome:**
- Open the link → tap the 3-dot menu → "Add to Home screen" → Install
- OR tap the "Install" banner that appears at the top of the app

**iPhone Safari:**
- Open the link → tap the Share button (box with arrow) → "Add to Home Screen" → Add
- The app icon appears on your home screen just like a real app

---

## Alternative: Use GitHub Pages (also free)
1. Create a free account at https://github.com
2. Create a new repository
3. Upload all files from the `faceattend-pwa` folder
4. Go to Settings → Pages → Source: main branch → Save
5. Your link: `https://yourusername.github.io/repository-name`

---

## Files in this folder
```
faceattend-pwa/
├── index.html      ← Main app
├── manifest.json   ← PWA config (app name, icon, colors)
├── sw.js           ← Service worker (offline support)
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## Features
- ✅ Real face recognition (face-api.js TinyFaceDetector)
- ✅ Installs as standalone app on Android & iPhone
- ✅ Works offline after first load
- ✅ Students persist in storage (won't lose data on refresh)
- ✅ Free matric number input — any format
- ✅ Gateway ICT Polytechnic branding
- ✅ EEE course options and levels
- ✅ CSV export for attendance records
- ✅ Light/bright theme

## For your Final Year Project writeup
Technology stack:
- face-api.js v0.22.2 (TensorFlow.js-based face recognition)
- Models: TinyFaceDetector + FaceLandmark68TinyNet + FaceRecognitionNet
- Storage: Browser localStorage (face descriptors as Float32Array)
- PWA: Web App Manifest + Service Worker (offline caching)
- No backend server required — runs entirely client-side
