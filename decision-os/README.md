# Decision OS — Deploy Guide

The Abundance Architect: Identity & Decision Operating System.

## What's in this bundle

| File | Purpose |
|---|---|
| `index.html` | The app itself. Self-contained except for icons + manifest. |
| `manifest.json` | PWA manifest — makes it installable as a real app. |
| `apple-touch-icon.png` | iOS home screen icon (180×180). |
| `icon-192.png` | Android / PWA icon (192×192). |
| `icon-512.png` | High-res PWA icon (512×512). |

## Deploy to GitHub Pages — recommended layout

In your existing GitHub Pages repo, create a subdirectory:

```
your-repo/
├── index.html                  ← your existing landing page
├── abundance-architect/        ← your existing app
└── decision-os/                ← NEW
    ├── index.html
    ├── manifest.json
    ├── apple-touch-icon.png
    ├── icon-192.png
    └── icon-512.png
```

Drop all five files into a new `decision-os/` folder. Commit. Push.

It'll be live at:
`https://<your-username>.github.io/<your-repo>/decision-os/`

## Add to home screen (iOS)

1. Open the deployed URL in **Safari** (not Chrome — Chrome on iOS has weaker PWA support).
2. Tap the Share button.
3. Tap "Add to Home Screen."
4. The gold diamond icon appears on your home screen.
5. Tapping it opens the app fullscreen, no browser chrome — exactly like a native app.

## Data persistence

Uses `localStorage` — fully offline. Data lives on the device. Clearing Safari data will wipe it, so if that ever matters, tell me and I'll add an export/import feature.

## What's stored

- `identity:traits` — your three identity statements
- `checkins:all` — daily embodiment marks (for streak tracking)
- `decisions:history` — every decision you've run through the Lens

## Customizing

The traits, principles, and aesthetic are all defined at the top of `index.html`:
- `DEFAULT_TRAITS` array — your three identity statements (also editable in-app)
- `PRINCIPLES` array — the five decision principles
- CSS `:root` variables — color palette

That's it. Build in silence. Let results speak.
