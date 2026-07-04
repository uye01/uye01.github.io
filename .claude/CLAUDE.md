# CLAUDE.md — Personal Academic Homepage (uye01.github.io)

## Project
Personal academic homepage for **Hankyeol Kim** (M.S. student, Industrial Engineering, Seoul National University; DSBA Lab, advisor Prof. Pilsung Kang; B.S. in Physics and Astronomy, SNU).
- Deployed via **GitHub Pages**, repo: `uye01/uye01.github.io`, branch `main`, root. Live at https://uye01.github.io
- **Hand-written static site. No templates (al-folio etc.), no frameworks, no build system.** One `index.html` with inline CSS/JS + assets (`profile.jpg`, `logos/`, `cv.pdf`).
- Communicate with the user **in Korean**. Code, comments in code, and site copy are in English.
- **See [DESIGN_LOG.md](DESIGN_LOG.md)** for the current design system (theme tokens, dark mode, active effects) and the change history. When it disagrees with a rule below, the DESIGN_LOG reflects the newer decision.

## Hard content rules (settled after several iterations — do not revisit without asking)
1. **Section order:** About → Education → Professional Experience → Publications → Research Projects.
2. **Sticky top nav** linking to each section.
3. Sidebar (desktop-sticky): photo at top with name, role, affiliation, and contact links (email, GitHub, LinkedIn, **Google Scholar**) directly under the profile. **No separate Contact section.**
4. **No Korean name (김한결) anywhere.**
5. About = short (3 sentences max). ~~Chips: NOW ×2 only~~ **Updated:** research-interest chips are a **PAST → NOW → NEXT arc** (PAST · PINN, PAST · LLM, NOW · Spatiotemporal Diffusion, NOW · Visual Reasoning, NEXT · Physical AI), colored by tier. About copy is the direct first-person intro incl. B.S. Physics & Astronomy.
6. **CV link ("Curriculum Vitae" → cv.pdf) sits under the About text**, inside the About card.
7. Publications: **text-only** — title, authors (Hankyeol Kim bold, Pilsung Kang†), venue line ("Under review · 2026"), and **Paper / Code** pill buttons (**Paper = soft blue, Code = soft red**). **Never generate synthetic/placeholder teaser images for publications.** The user inserts real links/images himself (real arXiv/GitHub links are now in place).
8. Education / Experience / Research Projects items each have a **40×40 logo slot** in front (`logos/*.png`, `onerror` fallback hides gracefully). Filenames: `snu, lunosoft, aiara, sesac, skhynix, meritz, samsungfire, etri`.
9. All project/company names **verbatim from the CV** (full official names, e.g. "Meritz Fire & Marine Insurance Co., Ltd."). Experience projects are rendered as bullet lists, including all AIARA sub-roles (PM Team Leader / Project Manager / App Developer) with their own date ranges and client project lists.

## Design preferences (EVOLVED — see DESIGN_LOG.md for the current system)
- **Historical (early sessions):** user wanted **simple, plain, content-first**, rejected a canvas/wave animation, a full dark theme ("too much"), and flourishes on publications.
- **Superseded:** the user later **lifted the "simple/small-variation" constraint** ("be more creative") and **asked for a dark/light toggle**. The site now has dark mode + several ambient effects (aurora, grain, cursor spotlight, animated gradient name). So (b) "no dark theme" no longer holds; publications still stay restrained (Paper/Code coloring + hover only — no teaser images / no decorative flourishes).
- Still true: **default is the light theme**; subtlety within each effect (the user prunes anything that feels like "too much" — has already removed 3D tilt and the timeline connector).
- **Accepted design language:** dual light/dark via CSS variables; light = warm-white `#FBFBF9`, white cards, ultramarine `#2C46C7` + cyan `#3FBBD8`; fonts Space Grotesk / Public Sans / IBM Plex Mono. **Full token table + effect list live in [DESIGN_LOG.md](DESIGN_LOG.md).**
- Reference sites the user likes: https://onground-korea.github.io/ and https://jaeyongko.github.io/ (sidebar + card sections + pub link buttons).
- The **design-polish pass is DONE** (was previously deferred). Do not re-defer; make incremental design changes on request.

## Working style
- **Make changes incrementally**; don't rewrite the page or change design direction without asking.
- Keep the `✏️` HTML comments that mark user-editable spots (links, logos, CV). Add new ones when introducing placeholders.
- After any visual change, **verify by rendering** (e.g. headless Chromium screenshot) at desktop ~1280px and mobile ~390px before declaring done. Past bugs caught this way: distorted `img` (missing `height:auto`), header padding overriding wrapper padding, nav overflow on mobile.
- Respect `prefers-reduced-motion` for any animation; keep semantic HTML and focus-visible styles.
- Single-file philosophy: inline CSS/JS in `index.html`; assets as separate files.

## Current state & open TODOs
- `index.html` now carries the full design system (dual light/dark, ambient effects — see DESIGN_LOG.md), plus `profile.jpg`, `logos/`, `cv.pdf`. LinkedIn URL and real Paper/Code arXiv/GitHub links are filled in by the user.
- If Pages still 404s: Settings → Pages → toggle Source (GitHub Actions ↔ Deploy from a branch, main /root) and re-run, or delete the `github-pages` environment in Settings → Environments and re-run.
- Open placeholders (`href="#"` with `✏️` markers): **Google Scholar** URL in the sidebar. Confirm the DSBA Lab URL (currently `http://dsba.snu.ac.kr`).

## Facts for content (from CV — do not invent beyond this)
- Publications (both "Under review, 2026", authors: Hankyeol Kim, Pilsung Kang†):
  1. "Asking Is Not Enough: Protocol Sensitivity in LLM Confidence Calibration"
  2. "naPINN: Noise-Adaptive Physics-Informed Neural Networks for Recovering Physics from Corrupted Measurement"
- Research projects: SK hynix i-TAP (May 2026–), Meritz contextual bandit (Apr 2026–), Samsung Fire retriever data (Mar 2025–Mar 2026), ETRI anomalous situation detection (Jul 2025–Nov 2025).
- Experience: Lunosoft PM (Feb–Nov 2024; Druid Rising / 2026 Trash King / Love Revolution), AIARA (Dec 2022–Feb 2024; Samsung Electronics, E-MART, Megastudy ×2, SNU Hospital, LUXROBO), SBA SeSAC Boost Camp Mentor — Service Design (Dec 2023–Mar 2024).
- Contact: hankyeol@snu.ac.kr · github.com/uye01