# 📘 Portfolio Workshop — Student Handbook

Welcome! This is a complete, **follow-along** step-by-step guide.
Try to finish in the 20-minute session — but if you don't, that's fine. Take this doc home and finish at your own pace.

---

## What You Need (almost everything is free)

- ✅ A laptop + internet
- ✅ A Google account (to log into Gemini)
- ✅ A GitHub account (no account? We have a backup plan 👉 Plan B)
- ✅ Your content: name, headshot, 2–4 projects (video links / images / music), contact info
- ✅ A screenshot of a website whose visual style you like (strongly recommended)

**Videos / audio**: don't upload these to GitHub. Use external hosts:
- 🎬 Video → YouTube or Vimeo, set to **Unlisted** (not public — only people with the link can see it)
- 🎵 Audio → SoundCloud / Spotify / Bandcamp
- 🖼️ Images → safe to put directly in the repo (a few MB each is fine)

---

## Step 0 — Account Setup (3 min)

### Sign up for GitHub (if you don't have one)

1. Go to [github.com](https://github.com) → Sign up
2. Email → password → username
   - ⚠️ **Your username becomes part of your portfolio URL.** Use your real name or stage name — not `xXDarkLordXx`.
3. Verify your email → done

### Log into Gemini

1. Go to [gemini.google.com](https://gemini.google.com)
2. Sign in with your Google account. That's it.

---

## Step 1 — Copy the Template Repo (30 sec)

1. Open [github.com/JWWWWWANG/portfolio-starter](https://github.com/JWWWWWANG/portfolio-starter)
2. Click **Use this template → Create a new repository** (top right)
3. Name the new repo: **`portfolio`** (lowercase — your URL will be `<username>.github.io/portfolio`)
4. Set it to **Public** (required for free GitHub Pages)
5. Click **Create repository**

*[screenshot: Use this template button]*

---

## Step 2 — Enable GitHub Pages Early (1 min, important)

**Turn Pages on before you even have real content.** This way, every time you commit new HTML, you only need to refresh the page to see it live.

1. In your new `portfolio` repo, click **Settings**
2. In the left sidebar, find **Pages**
3. Under **Branch**, select `main` and folder `/ (root)`, then click **Save**
4. Wait ~10 seconds. At the top of the page you'll see:
   > Your site is live at `https://<your-username>.github.io/portfolio/`
5. **Write this URL down.** Opening it now shows placeholder content — that's normal.

*[screenshot: Pages settings + URL banner]*

---

## Step 3 — Fill the Markdown Template (5 min)

1. Based on your discipline, pick one of the four templates your instructor provides:
   - `template-general.md` — universal
   - `template-actor.md` — actors
   - `template-filmmaker.md` — filmmakers
   - `template-musician.md` — musicians
2. Copy the entire template into any text editor (Notes, VS Code, even Gemini's chat box works)
3. Replace every `[[placeholder like this]]` with your own content

**Short on time? Fill these three first:**
- Hero (name + one-line tagline)
- About (2–3 sentences)
- At least 1 project

You can add everything else later, after your site is live, by going back to Gemini.

---

## Step 4 — Feed It to Gemini (3 min) ⭐ the core moment

**Do this in order — order matters.**

### 4.1 Give Gemini the style reference first

1. Open Gemini
2. **Drag your style-reference screenshot directly into the chat**
3. Type:
   > `Remember this visual style — colors, typography, layout, vibe. I'll send you content next.`
4. Wait for Gemini to acknowledge

> 💡 No reference image? Describe it in words: `I want a minimal, modern, dark-mode portfolio with elegant serif headings.`

### 4.2 Paste the system prompt (instructor provides)

Paste the system prompt your instructor gave you — the one starting with *"You are a senior frontend designer..."*.

### 4.3 Paste your filled-in markdown content

Paste the entire filled template from Step 3 into Gemini and send.

### 4.4 Copy Gemini's output

Gemini will spit out a big chunk of HTML. **Select all** (Cmd+A) → **Copy** (Cmd+C).

> ⚠️ If the output starts with ` ```html ` or ends with ` ``` `, manually delete those wrapper lines. You want **pure HTML only**.

---

## Step 5 — Paste Into GitHub & Publish (3 min)

1. Go back to your `portfolio` repo
2. Click the file `index.html`
3. Click the **pencil icon** in the top-right (Edit this file)
4. **Cmd+A to select all → Delete** everything currently in the file
5. **Paste** the HTML Gemini just gave you
6. Scroll to the bottom of the page
7. Click the green **Commit changes...** button
8. In the confirmation dialog, click **Commit changes** again

*[screenshot: GitHub pencil edit icon + Commit button]*

### See your site

Open the URL you wrote down in Step 2. **Refresh the page.**

🎉 **Your portfolio is live.**

> Still seeing 404? Wait 1–2 more minutes and refresh again. GitHub sometimes takes a moment to deploy.

---

## Step 6 — Iterate (3 min, the fun part)

This is the heart of vibe coding: **directing Gemini with natural language**.

Go back to Gemini and try:

- `Make the hero section darker with a subtle gradient.`
- `Use a serif font like Playfair Display for the headings.`
- `Add a smooth fade-in animation when scrolling.`
- `Make it more minimal / brutalist / Y2K / vintage.`
- `Make it fully responsive on mobile.`

Each time Gemini gives you new code:
1. Copy it
2. Go back to GitHub, edit `index.html`
3. Delete the old contents, paste the new
4. Commit
5. Refresh your live site

---

## 🆘 If You Get Stuck

| Problem | Fix |
|---|---|
| Site shows 404 | Wait 2 more minutes; confirm Pages is set to `main` branch |
| HTML has ` ``` ` at the start/end | Manually delete the code-block wrappers; keep only raw HTML |
| Gemini's output is cut off | Reply `continue` to make it finish; or say `output the full file in one message` |
| Images / videos don't show up | Double-check the URLs; videos must be **embed** links, not watch links |
| Layout looks broken | Make sure this line is in your HTML: `<script src="https://cdn.tailwindcss.com"></script>` — if missing, ask Gemini to add it |
| No GitHub account, running out of time | 🚨 Jump to Plan B at the bottom |

---

## 🏠 Continuing at Home

### Keep iterating on the content

- Add more projects → ask Gemini: `Add a new project card with [details]`
- Change the palette → `Change the color palette to [description]`
- Change fonts → `Use [font name] from Google Fonts`
- Add sections → `Add a "Press" section with these logos: [...]`

### Bind a Custom Domain (optional — makes your URL more pro)

Want `yourname.com` instead of `username.github.io/portfolio`? **It's free** (except the cost of the domain itself):

**Get a domain for free (requires an .edu email):**
1. Go to [education.github.com/pack](https://education.github.com/pack)
2. Apply for the **GitHub Student Developer Pack** with your school email (approval takes 1–3 days)
3. Once approved, find **Namecheap** in the Pack and claim a free `.me` domain for 1 year (or `.tech`, `.live`, etc.)

**Buy one cheaply:**
- [Porkbun](https://porkbun.com) or [Cloudflare Registrar](https://dash.cloudflare.com)
- `.com` ≈ $10/year, `.xyz` ≈ $1–2/year, no renewal tricks

**How to bind it:**
1. In your domain registrar, add DNS records pointing to GitHub Pages
2. Back in your repo → Settings → Pages → fill in **Custom domain**
3. Check **Enforce HTTPS**
4. Wait for DNS to propagate, done

Full guide: [GitHub Pages custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

---

## 🆘 Plan B — Netlify Drop (the backup)

If your GitHub flow stalls, or you don't have a GitHub account at all, use this — **live URL in 30 seconds**:

1. Open [netlify.com/drop](https://app.netlify.com/drop)
2. Save Gemini's HTML into a file called `index.html` (saving it to your desktop is fine)
3. **Drag that file into the Netlify browser window**
4. Netlify gives you a URL instantly (something like `https://random-name.netlify.app`)
5. Done — your site is live

**Trade-off:** the URL is random and hard to remember, and updating means re-dragging the file each time. But as a workshop safety net, it's hard to beat.

---

## 📬 Keep Going

- Want more portfolio inspiration? Search "awwwards portfolio" / check [godly.website](https://godly.website) / [siteinspire.com](https://siteinspire.com)
- Push Gemini harder — mention specific designers in your prompts: `in the style of Bruno Simon / Brittany Chiang / Cassie Evans`

---

**One last thing:** what you made today is v0.1. It doesn't have to be perfect. Ship it now, then make it better. **That's vibe coding.**
