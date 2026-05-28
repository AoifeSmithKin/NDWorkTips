# ND Workplace Survival Playbook

> 500 prompts, scripts, and strategies for neurodivergent people navigating the workplace — built from lived experience, not advice columns.

**Live demo:** `https://your-username.github.io/nd-workplace-playbook`

---

## What this is

A self-contained, offline-ready web app with 500 expandable prompt cards across 10 chapters. Every card opens to reveal colour-coded responses:

- 🩷 **Pink** — RSD notes (what is happening neurologically, the emotional context)
- 💚 **Green** — Strategy tips (what to actually do)
- 💛 **Yellow** — Scripts (exact words to say or send)

Built for autistic and ADHD adults who are tired of workplace advice that assumes a neurotypical brain.

---

## The 10 chapters

| # | Chapter | What's inside |
|---|---------|---------------|
| 1 | **Meeting Survival** | Scripts for being put on the spot, buying time, freezing, following up, Zoom vs in-person |
| 2 | **Task & Brain Management** | Starting tasks, ADHD paralysis, externalising the mental pile, perfectionism, body doubling |
| 3 | **Communication Scripts** | Asking for more time, chasing without anxiety, disagreeing via email, saying no |
| 4 | **Office Politics** | Reading subtext, protecting yourself, credit, visibility, staying out of drama |
| 5 | **RSD & Sensitivity** | Managing the emotional gut-punch, spirals, justice sensitivity, feedback shame |
| 6 | **Energy & Burnout** | Mid-week crash, masking depletion, micro-recovery, recognising burnout early |
| 7 | **Masking & Authenticity** | Where masking costs too much, invisible stims, unmasking gradually, work identity |
| 8 | **Unwritten Rules** | What 'team player' really means, visibility, alignment, executive presence — decoded |
| 9 | **Sensory & Overstimulation** | Open offices, noise, light, temperature, cumulative load, sensory toolkit |
| 10 | **Work Identity** | Comparison trap, strengths, non-linear careers, sustainable meaning, imposter syndrome |

---

## Features

- **Tap to expand** — every card opens to reveal full colour-coded RSD, strategy, and script responses
- **Search** across all 500 prompts instantly (press `/` anywhere to focus the search bar)
- **Filter by chapter** using the scrollable tab bar
- **Bookmark** any prompt and access all saved items in a dedicated Bookmarks tab
- **Download any chapter** as a `.txt` file including all expanded responses
- **Copy to clipboard** button inside every expanded card
- **Works offline** once loaded — no external dependencies, no CDN, no API calls
- **Mobile-first** — large tap targets, smooth expand animation, horizontal tab scroll
- **Dark mode by default** — high contrast, ND-friendly layout throughout

---

## File structure

```
nd-workplace-playbook/
├── index.html        ← the entire app (single self-contained file)
└── README.md         ← this file
```

No build tools. No dependencies. No node_modules. No server required. Opens directly in any modern browser and works offline once loaded.

---

## Deploying to GitHub Pages

### Option A — Using the GitHub web interface (no coding required)

1. Go to [github.com](https://github.com) and sign in
2. Click **New repository**
3. Name it `nd-workplace-playbook` — keep it Public
4. Click **Create repository**
5. On the next screen, click **uploading an existing file**
6. Drag and drop both `index.html` and `README.md`
7. Click **Commit changes**
8. Go to **Settings → Pages**
9. Under **Source**, select `Deploy from a branch`
10. Set Branch to `main` and folder to `/ (root)`
11. Click **Save**
12. Wait 2–3 minutes, then visit `https://your-username.github.io/nd-workplace-playbook`

### Option B — Using the command line

```bash
# Clone your new empty repo
git clone https://github.com/your-username/nd-workplace-playbook.git
cd nd-workplace-playbook

# Add your files, then:
git add index.html README.md
git commit -m "Initial release — ND Workplace Survival Playbook v2"
git push origin main
```

Then enable GitHub Pages via **Settings → Pages** as described in Option A from step 8.

---

## How the prompt data is structured

All 500 prompts live in the `C` array inside the `<script>` tag in `index.html`. Each prompt follows this pattern:

```javascript
["Prompt question text",
 "rsd",    "RSD note — emotional context and neurological explanation",
 "strat",  "Strategy tip — what to actually do",
 "script", "Script — exact words to say or send"]
```

**Rules:**
- The question text is always the first element
- Block types are `rsd`, `strat`, and `script`
- You can use any combination of the three — one, two, or all three
- Blocks appear in the order you write them
- The first block type determines the colour dot shown on the collapsed card

**To add a new prompt** to an existing chapter, add a new array entry to that chapter's `prompts` array following the same format.

**To add a new chapter**, add a new object to the `C` array:

```javascript
{
  id: 'c11',
  label: 'Your Chapter Name',
  color: 'var(--c1)',   // use any of --c1 through --c10
  prompts: [
    ["Your prompt question", "rsd", "RSD note", "strat", "Strategy", "script", "Script"]
  ]
}
```

---

## Saving and bookmarks

Bookmarks are stored in `localStorage` under the key `nd_bm3` and persist across sessions in the same browser. They are not synced across devices. Clearing browser data will remove saved bookmarks.

---

## Sharing and use

This playbook is free to use, share, and adapt. If you share it, please keep the footer credit intact:

> *You are not broken. The system is.*

If you build on it, expand it, or adapt it for a specific community or workplace context — please do.

---

## Accessibility

- Semantic HTML with ARIA `role`, `aria-expanded`, and `aria-label` attributes throughout
- Screen reader summary via `.sr-only` heading
- All interactive elements keyboard-accessible (tab, enter, space)
- High contrast dark theme throughout
- Minimum 16px body text
- Touch targets sized for mobile use
- No external fonts or resources — fully self-contained

---

## Browser support

Tested and working on:
- iOS Safari (iPhone and iPad)
- Android Chrome
- Desktop Chrome, Firefox, Safari, and Edge

Requires a modern browser with ES6 support. Works offline once the page has loaded once.

---

*Built from lived experience as an autistic, inattentive-ADHD adult who spent years getting it wrong — so you don't have to.*
