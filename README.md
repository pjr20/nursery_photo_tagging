# Maple Lane · Photo Capture Tool

A mobile web app for photographing nursery stock. Scan a barcode tag,
take a photo, and it downloads with the correct filename
(`KnockOutRose_3Gal_20260330.jpg`) ready to sync to Google Drive.

---

## First-Time Setup (~10 minutes)

### Step 1 — Create the GitHub repo

1. Go to [github.com](https://github.com) and sign in
2. Click the **+** in the top-right → **New repository**
3. Name it: `maple-lane-photos`
4. Set it to **Private** (recommended) or Public
5. Click **Create repository**

### Step 2 — Upload the project files

1. On the repo page, click **Add file → Upload files**
2. Drag and drop ALL of these files/folders:
   - `index.html`
   - `vercel.json`
   - `public/` folder (containing `plants.csv`)
3. Scroll down, click **Commit changes**

Your repo should look like this:
```
maple-lane-photos/
├── public/
│   └── plants.csv
├── index.html
└── vercel.json
```

### Step 3 — Deploy to Vercel

1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Click **Add New → Project**
3. Find `maple-lane-photos` in the list → click **Import**
4. Leave all settings as defaults → click **Deploy**
5. Wait ~30 seconds → your app is live at:
   **`https://maple-lane-photos.vercel.app`**

That's it. The app is now live and pulling the plant list automatically.

---

## Adding the App to Phones (no App Store needed)

### iPhone (Safari)
1. Open `https://maple-lane-photos.vercel.app` in Safari
2. Tap the **Share** button (box with arrow)
3. Scroll down → tap **Add to Home Screen**
4. Tap **Add** → app icon appears on home screen

### Android (Chrome)
1. Open `https://maple-lane-photos.vercel.app` in Chrome
2. Chrome shows a banner "Add to Home Screen" — tap it
3. Or: tap the **⋮** menu → **Add to Home Screen**

---

## Updating the Plant List (weekly / as needed)

This is the routine you'll do whenever your inventory changes:

### Export from CounterPoint
Export your items as a CSV with at least these columns:
- **Name** (or "Item Name", "Description")
- **Size** (or "Container", "UOM")
- **SKU** (or "Item #", "Product ID", "Barcode")

Column order doesn't matter. Extra columns are ignored.

### Upload to GitHub
1. Go to your GitHub repo: `github.com/YOUR-USERNAME/maple-lane-photos`
2. Click into the `public/` folder
3. Click `plants.csv` → click the **pencil (edit) icon** OR
   click **Add file → Upload files** to replace it entirely
4. Commit the change

Vercel redeploys in ~30 seconds. All phones get the updated list
within 4 hours automatically, or immediately if someone taps ↻ Refresh.

---

## If the Vercel URL is Different

If Vercel gave your project a different URL than `maple-lane-photos.vercel.app`:

1. Open `index.html` in a text editor
2. Find this line near the top of the `<script>` section:
   ```
   const DEFAULT_URL = 'https://maple-lane-photos.vercel.app/plants.csv';
   ```
3. Replace the URL with your actual Vercel URL + `/plants.csv`
4. Re-upload `index.html` to GitHub

---

## Photo → Google Drive Workflow

**iPhone:**
- Tap **Save Photo** in the app → photo downloads to Files app
- Open Google Drive app → tap **+** → **Upload** → find it in Downloads

**Android:**
- Tap **Save Photo** → photo downloads to Downloads folder
- If Drive app has Downloads sync enabled: appears automatically
- Otherwise: open Files → share the photo to Drive

**Tip:** Set your phone's Google Drive app to auto-backup your
Downloads folder and you'll never need a manual step.

---

## File Naming Convention

Photos are named automatically:
```
PlantName_Size_YYYYMMDD.jpg
PlantName_Size_angle2_YYYYMMDD.jpg   (second angle, same plant)
```

Examples:
- `KnockOutRose_3Gal_20260330.jpg`
- `JapaneseMapleFire_7Gal_20260415.jpg`
- `ArborvitaeEmeraldGreen_6ftBB_20260510.jpg`
