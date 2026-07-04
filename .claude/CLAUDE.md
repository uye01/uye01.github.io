# CLAUDE.md — Personal Academic Homepage (uye01.github.io)

## Project
Personal academic homepage for **Hankyeol Kim** (M.S. student, Industrial Engineering, Seoul National University; DSBA Lab, advisor Prof. Pilsung Kang; B.S. in Physics and Astronomy, SNU).
- Deployed via **GitHub Pages**, repo: `uye01/uye01.github.io`, branch `main`, root. Live at https://uye01.github.io
- **Hand-written static site. No templates (al-folio etc.), no frameworks, no build system.** One `index.html` with inline CSS/JS + assets (`profile.jpg`, `logos/`, `cv.pdf`).
- Communicate with the user **in Korean**. Code, comments in code, and site copy are in English.

## Hard content rules (settled after several iterations — do not revisit without asking)
1. **Section order:** About → Education → Professional Experience → Publications → Research Projects.
2. **Sticky top nav** linking to each section.
3. Sidebar (desktop-sticky): photo at top with name, role, affiliation, and contact links (email, GitHub, LinkedIn) directly under the profile. **No separate Contact section.**
4. **No Korean name (김한결) anywhere.**
5. About = short (3 sentences max). Research-interest chips: `NOW · Temporal Diffusion`, `NOW · Visual Reasoning` **only** — no "NEXT/Pursuing/Physical AI" chip.
6. **CV link ("Curriculum Vitae" → cv.pdf) sits under the About text**, inside the About card.
7. Publications: **text-only** — title, authors (Hankyeol Kim bold, Pilsung Kang†), venue line ("Under review · 2026"), and **Paper / Code** pill buttons with `href="#"` placeholders. **Never generate synthetic/placeholder teaser images for publications.** The user inserts real links/images himself.
8. Education / Experience / Research Projects items each have a **40×40 logo slot** in front (`logos/*.png`, `onerror` fallback hides gracefully). Filenames: `snu, lunosoft, aiara, sesac, skhynix, meritz, samsungfire, etri`.
9. All project/company names **verbatim from the CV** (full official names, e.g. "Meritz Fire & Marine Insurance Co., Ltd."). Experience projects are rendered as bullet lists, including all AIARA sub-roles (PM Team Leader / Project Manager / App Developer) with their own date ranges and client project lists.

## Design preferences (learned the hard way)
- The user rejected: (a) a decorative canvas/wave animation, (b) a full dark "technological" theme (**"too much"**), (c) creative flourishes attached to publications.
- Wanted: **simple, plain, content-first**, but not boring — "a little unique with some eye-catching point, **not too much or dramatic**". Subtlety wins.
- Current accepted design language (v5): light theme, warm-white `#FBFBF9` bg, white cards with 1px `#E8E8E3` borders (radius 12px); accent **ultramarine `#2C46C7`** + cyan `#3FBBD8` (gradient hairline under name, section tick squares, chips); fonts **Space Grotesk** (headings) / **Public Sans** (body) / **IBM Plex Mono** (dates, small labels).
- Reference sites the user likes: https://onground-korea.github.io/ and https://jaeyongko.github.io/ (sidebar + card sections + pub link buttons). Follow their skeleton, differentiate in detail.
- A dedicated **design-polish pass is planned but deferred** ("let's think about the design later") — do not restyle proactively; finish content/infra tasks first.

## Working style
- **Make changes incrementally**; don't rewrite the page or change design direction without asking.
- Keep the `✏️` HTML comments that mark user-editable spots (links, logos, CV). Add new ones when introducing placeholders.
- After any visual change, **verify by rendering** (e.g. headless Chromium screenshot) at desktop ~1280px and mobile ~390px before declaring done. Past bugs caught this way: distorted `img` (missing `height:auto`), header padding overriding wrapper padding, nav overflow on mobile.
- Respect `prefers-reduced-motion` for any animation; keep semantic HTML and focus-visible styles.
- Single-file philosophy: inline CSS/JS in `index.html`; assets as separate files.

## Current state & open TODOs
- `index.html` (v5) and `profile.jpg` are in the repo. Site returned **404**: the first Pages deploy failed with the generic "Deployment failed, try again later" (Jekyll build succeeded; deploy step failed). A re-run was queued. If it still fails: Settings → Pages → toggle Source (GitHub Actions ↔ Deploy from a branch, main /root) and re-run, or delete the `github-pages` environment in Settings → Environments and re-run.
- User will provide: LinkedIn URL (sidebar `href="#"`), Paper/Code links per publication, `logos/*.png` images, `cv.pdf`, and confirmation of the DSBA Lab URL (currently `http://dsba.snu.ac.kr`).
- Deferred: the subtle design-polish pass described above.

## Facts for content (from CV — do not invent beyond this)
- Publications (both "Under review, 2026", authors: Hankyeol Kim, Pilsung Kang†):
  1. "Asking Is Not Enough: Protocol Sensitivity in LLM Confidence Calibration"
  2. "naPINN: Noise-Adaptive Physics-Informed Neural Networks for Recovering Physics from Corrupted Measurement"
- Research projects: SK hynix i-TAP (May 2026–), Meritz contextual bandit (Apr 2026–), Samsung Fire retriever data (Mar 2025–Mar 2026), ETRI anomalous situation detection (Jul 2025–Nov 2025).
- Experience: Lunosoft PM (Feb–Nov 2024; Druid Rising / 2026 Trash King / Love Revolution), AIARA (Dec 2022–Feb 2024; Samsung Electronics, E-MART, Megastudy ×2, SNU Hospital, LUXROBO), SBA SeSAC Boost Camp Mentor — Service Design (Dec 2023–Mar 2024).
- Contact: hankyeol@snu.ac.kr · github.com/uye01