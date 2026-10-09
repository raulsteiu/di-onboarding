# Data Integration Onboarding

An interactive onboarding guide for new members of the Data Integration team. It walks through the full route of an integration project, from the signed contract to live data, and gives a short toolbox of the technical skills used every week.

**Live site:** https://raulsteiu.github.io/di-onboarding/

---

## What it covers

### The route
Seven phases shown on a swim-lane map (Us, Support, Client), with an exit gate for each phase:

1. Scoping call
2. Provisioning
3. Postman check (API sources only, skipped for SQL and SFTP)
4. DI Studio build
5. Staging check
6. Load and schedule
7. Sign-off

Each phase has its own tab with:
- Who does what
- An exit gate checklist
- Deeper reference sections (expand and collapse)
- A "In VBA terms" box that translates the idea for people with an Excel/VBA background
- A "Watch out" box with the most common trap
- Self-check questions with hidden answers

### The toolbox
Four short, practical areas:

- **DI Studio anatomy:** sites, agents, connections, jobs, steps and tasks
- **FC and FPA data:** the two data shapes, with an interactive demo showing how the same account is stored in each
- **Script Agent:** do and don't examples for the scripting runtime
- **SQL in six moves:** the core transformations, each mapped to an Excel equivalent

### Survival kit
Ten gotchas that cost the team real hours, where to look for help, a suggested first-week plan and the team's working principles.

---

## Features

- Click any phase on the route map, or any cell in its column, to open the detail
- Tick off exit gate checklists and mark phases complete, and the route map fills in as you go
- Progress and checklists are saved automatically in the browser (`localStorage`)
- A **Reset progress** button clears everything
- Responsive layout: the route map fits on large screens and scrolls sideways on small ones
- Keyboard-friendly, with visible focus states, and animations are turned off for people who prefer reduced motion

---

## Project structure

```
di-onboarding/
├── index.html     the whole app: HTML, CSS and JavaScript in one file
├── .nojekyll      tells GitHub Pages to skip Jekyll, so deploys are faster
└── README.md      this file
```

There is no build step, no framework and no external dependencies. Nothing is loaded from a CDN.

---

## Run it locally

Open `index.html` in any modern browser. That's it.

---

## Deploy to GitHub Pages

1. Push `index.html` and `.nojekyll` to the `main` branch.
2. Go to **Settings → Pages**.
3. Set **Source** to **Deploy from a branch**, **Branch** to `main`, folder to `/ (root)`, and click **Save**.
4. Wait for the **Actions** tab to show a green "pages build and deployment" run.
5. Open the site URL. Allow a minute or two for the CDN, and hard refresh (Ctrl+Shift+R) if you still see an old version.

---

## Updating the content

Everything lives in `index.html`:

| To change | Where to look |
|---|---|
| Colours and fonts | The `:root` variables at the top of the `<style>` block |
| Phase text, checklists, self-checks | The `<article class="phase" id="p1">` to `p7` blocks |
| Route map cells | The `PH` array at the start of the script |
| Toolbox panels | The `<section id="toolbox">` block |
| FC vs FPA demo figures | The `MV` array in the script |

After editing, commit the change. GitHub Pages redeploys automatically.

---

## Good to know

- **Progress is per browser.** It is stored in each person's own browser, so it does not sync across devices and the team lead cannot see it.
- **This site is public.** Anyone with the link can open it. Keep client names, credentials, internal URLs and other confidential details out of the content.
- **The summary is not the source of truth.** The team documentation holds the current detail and takes precedence over this guide.

---

## Maintainers

Data Integration team. For corrections or additions, edit `index.html` and commit, or raise it with the team lead.
