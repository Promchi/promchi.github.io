# Promchi.github.io — Portfolio Site

Single-page portfolio. Live at **https://Promchi.github.io** once deployed.

## How to deploy (one-time setup)

1. Create a **new public repository** on GitHub named **exactly** `Promchi.github.io` (case matters — use the same capitalisation as your username).
2. Upload `index.html` and the `images/` folder to the repository root. You can either:
   - **Drag and drop in the GitHub web UI**: go to the new repo → click "uploading an existing file" → drag everything in → commit.
   - **Or use git from the terminal**:
     ```bash
     git init
     git add .
     git commit -m "Initial portfolio site"
     git branch -M main
     git remote add origin https://github.com/Promchi/Promchi.github.io.git
     git push -u origin main
     ```
3. Go to the repo's **Settings → Pages**. Under "Build and deployment", set Source to `Deploy from a branch`, Branch to `main`, folder to `/ (root)`, then Save.
4. Wait ~30–60 seconds. Refresh `https://Promchi.github.io` — you're live.

## How to add a new project later

The site is a single `index.html` file. To add a project:

1. Open `index.html` in the GitHub web editor (pencil icon on the file) or locally.
2. Find the comment that says `<!-- ADD NEW PROJECTS BELOW THIS LINE -->` near the bottom of the projects section.
3. Above that line, paste a copy of the **TEMPLATE block** (the first project — look for `<!-- TEMPLATE START -->` and `<!-- TEMPLATE END -->`).
4. Update the new card:
   - `card-number` — bump to 07, 08, etc.
   - `card-tag`, `<h3>`, `card-tagline` — set the new project's framing.
   - `card-image` class — pick one of: `theme-amber`, `theme-rust`, `theme-teal`, `theme-rose`, `theme-violet`, `theme-magenta`. (Or add a new gradient in the CSS if you want a fresh colour.)
   - **Objective / Approach / Result** — fill in.
   - `card-tech` — list tools.
   - `card-link` — either link the GitHub repo, or if it's not on GitHub yet replace with:
     ```html
     <span class="card-link disabled">In progress</span>
     ```
5. Commit. GitHub Pages redeploys automatically in ~30 seconds.

## How to swap a placeholder image for a real screenshot

Each project card currently shows a gradient placeholder with the project name in monospace. To replace it with a real dashboard screenshot:

1. Drop the screenshot into the `images/` folder. Use a descriptive filename, e.g. `images/revenue-intelligence-dashboard.png`.
2. In `index.html`, find the matching project's `<div class="card-image ...">` block.
3. Replace the inner `<span class="card-image-label">...</span>` with:
   ```html
   <img src="images/revenue-intelligence-dashboard.png" alt="Revenue Intelligence dashboard">
   ```
4. Commit. Done.

Tip: aim for screenshots around 1600 × 700 px for a clean 16:7 fit. PNG or JPG both work — JPG is smaller for photo-realistic dashboards.

## File structure

```
Promchi.github.io/
├── index.html         ← The whole site. CSS embedded inline.
├── README.md          ← This file.
└── images/            ← Drop project screenshots here.
    └── .gitkeep
```

## Stack

Pure HTML + CSS — no framework, no build step, no JavaScript. Fonts loaded from Google Fonts. Hosted free on GitHub Pages.

---

Built by Promise Ezeike · [LinkedIn](https://www.linkedin.com/in/promise-ezeike/) · [Email](mailto:ezeikechime25@gmail.com)
