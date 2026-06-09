# PFL 2026 — Betting GTM Deck

> The reference version of the PFL 2026 Go-To-Market deck, focused on the **betting partner pitch**.

**Live reference:** https://pfl-2026.github.io/GTM/

---

## What this project is

This Claude Project pins the **betting GTM deck** — the master reference version. Everything attached (the `index.html`, all the images, logos, videos) is your source material.

> [!IMPORTANT]
> You are **not editing this version directly.**
> You're forking it to create **your own tailored version** — for a specific partner pitch, region, or audience.

Think of the pinned deck as your starting block. Your job is to make it yours.

---

## How chats work

When you open this project and start a chat, **the chat is private to you**. Each chat is your own working session — Claude reads the pinned deck as the starting point, and you steer it from there.

> **Pro tip:** Start a new chat for each version you're building. Rename it (click the title at the top) to something like *"DraftKings pitch"* or *"MENA region cut"* so it's easy to find later.

---

## Making your own version

### The 6-step flow

| Step | What to do |
|:----:|:-----------|
| **1** | Open this project in Claude.ai |
| **2** | Start a new chat |
| **3** | Tell Claude what you need (examples below) |
| **4** | Claude returns an updated `index.html` + full `PFL-2026.zip` |
| **5** | Download both files |
| **6** | Deploy to your hosting (GitHub Pages or Azure — see below) |

### What good prompts look like

> *"Make a version of this deck for the DraftKings pitch — replace the betting stats with their relevant numbers, swap the cover image, and update the partner logos slide"*

> *"Create a MENA-focused version — emphasise the regional broadcasters and the Riyadh event"*

> *"Build a shorter 8-slide cut focused on the fan demographic story"*

---

## Deploy to GitHub Pages

> **Free** · **Simple** · **Auto-deploys on commit**

### One-time setup (your first version)

1. Go to **[github.com](https://github.com)** and sign in (free account if you don't have one)
2. Click **New** to create a repository
3. Name it (e.g. `pfl-draftkings-pitch`)
4. Set to **Public** *(required for free GitHub Pages)*
5. Tick **Add a README file**, click **Create repository**
6. Click **Settings** → **Pages** (left sidebar)
7. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
   - Click **Save**

Your repo is ready. Your live URL will be:
`https://[your-username].github.io/[repo-name]/`

### Uploading your deck

1. Download `PFL-2026.zip` from Claude, unzip it
2. In your repo, click **Add file** → **Upload files**
3. Drag the **contents** of the unzipped folder (`index.html` + `assets` folder) into the upload area
4. Type a commit message → click **Commit changes**
5. Wait ~30 seconds → visit your live URL → **Live**

### Updating later

When Claude sends you a new version:

1. In your repo, click `index.html` → **pencil icon** to edit
2. Open the new `index.html` from Claude in any text editor → select all → copy
3. In GitHub editor, select all → paste over existing content
4. Commit message → **Commit changes**
5. Live in ~30 seconds

> If asset files (images, videos) also changed, repeat the **Upload files** step and overwrite the existing ones.

---

## Deploy to Azure Static Web Apps

> **Use this if:** you're already on Azure or need integration with Microsoft 365 / Entra ID
> **Free tier** available

### One-time setup

1. Go to **[portal.azure.com](https://portal.azure.com)** and sign in
2. Search **Static Web Apps** → click **Create**
3. Fill in:

   | Field | Value |
   |:------|:------|
   | Subscription | Your Azure subscription |
   | Resource Group | Create new (e.g. `pfl-decks`) |
   | Name | Descriptive (e.g. `pfl-draftkings-pitch`) |
   | Plan type | **Free** |
   | Region | Closest to you |
   | Deployment source | **GitHub** (recommended) or **Other** |

4. Click **Review + create** → **Create**
5. Wait ~1 minute for deployment
6. Click **Go to resource** → you'll see your live URL (e.g. `https://nice-water-12345.azurestaticapps.net`)

### Option A — Deploy from GitHub *(recommended)*

If you've also got a GitHub repo, or you want git-based version history:

1. During Azure setup, set **Deployment source** to **GitHub**
2. Authorise Azure to read your GitHub account
3. Pick your repo and the `main` branch
4. **App location:** `/`
5. **Output location:** *leave blank*
6. Azure now auto-deploys every time you push to GitHub

### Option B — Direct upload *(no GitHub)*

If you don't want a GitHub repo:

1. In your Static Web App resource → **Deployment** → **Manual deployments**
2. Click **Upload** → select your unzipped folder
3. Wait ~1 minute → refresh your live URL

> **The GitHub-linked option is much easier to update later.** Direct upload is fine for one-off pitches.

---

## Other deploy options

Need something faster for a one-off?

| Platform | Best for | Link |
|:---------|:---------|:----|
| **Netlify Drop** | Instant drag-and-drop, no account needed | [app.netlify.com/drop](https://app.netlify.com/drop) |
| **Vercel** | GitHub-integrated, similar to Netlify | [vercel.com](https://vercel.com) |
| **Cloudflare Pages** | Free, fast, GitHub-integrated | [pages.cloudflare.com](https://pages.cloudflare.com) |

All three: connect a repo or drag a folder, get a URL.

---

## What's in the pinned deck

| File / folder | What it is |
|:---|:---|
| `index.html` | The entire deck — one self-contained HTML file |
| `assets/logos/` | **Cleaned transparent PFL + third-party logos** (these load locally for proper transparency). All other broadcaster logos load from the live site |
| `assets/images/` | Backgrounds, content tiles, fighter / arena imagery *(loaded from live site)* |
| `assets/video/` | 5 MP4 clips *(loaded from live site)* |
| `assets/fighters/` | Fighter photos *(loaded from live site)* |

> [!IMPORTANT]
> When you deploy your version, you **must** include the `assets/logos/` folder from the zip — these transparent versions are critical for the deck to look right. The other assets can come from the live site OR your own hosting.

---

## House rules for asking Claude to edit

Keep your edits clean and predictable:

- **Be specific about which slide.** *"Slide 4"* > *"the slide with the stats"*
- **Quote the exact text** you want to change (copy-paste from the deck if you can't remember it)
- **For new images, upload directly into the chat or share a URL** — Claude can't grab from your desktop
- **Don't ask Claude to push to your repo.** It can't — you do the deploy yourself
- **Always ask for the full folder archive** if anything changed beyond the HTML

---

## Brand & content rules

> [!WARNING]
> These are non-negotiable to keep the deck on-brand.

- **PFL Navy:** `#052383` *(set as CSS variable — don't override)*
- **PFL Red:** `#FF0404` *(set as CSS variable — don't override)*
- **Fonts:** Bebas Neue (display) + Saira / Saira Condensed (body) — don't add new fonts without sign-off
- **Cite sources** for stats (e.g. *"Source: YouGov 2025"*)
- **Don't add real broadcaster/sponsor logos** unless the partnership is publicly announced
- **Fighter photos** must come from the official PFL fighter database

---

## Need help?

If something breaks or you're stuck, just tell Claude what you tried and what happened. Paste any error messages. Most issues fix in one or two turns.
