# GHOSTBEROK profile: setup and design guide

This guide is for you. Keep it out of the profile repository, or delete it after setup.

## 1. Deploy

The README loads its banner, lab strip and divider from the `assets` folder, so upload both together. If you paste only the README text, those three images show their alt text instead.

1. Open `github.com/GHOSTBEROK/GHOSTBEROK`.
2. Choose **Add file > Upload files**, drag in `README.md` and the whole `assets` folder, and commit to the default branch. The new `README.md` replaces the current one.
3. Open `github.com/GHOSTBEROK` in a private window and check it on desktop and on your phone.

With git instead:

```bash
git clone https://github.com/GHOSTBEROK/GHOSTBEROK.git
cd GHOSTBEROK
# copy README.md and the assets folder in, then:
git add README.md assets
git commit -m "Redesign profile README"
git push
```

**Fill the placeholders.** Search the README for the word `Add`. Placeholders are italic and cover: Auralis stack, repository and documentation links; the project-backed languages and frameworks; LinkedIn, portfolio, email, communities and research collaboration links. The lab notebook rows say "Awaiting first entry" until you write one. Delete any row you will not use.

## 2. Visual design system

| Role | Name | Hex | Used for |
|---|---|---|---|
| Base | Deep Black | `#080B12` | Banner, lab strip, stats card backgrounds |
| Surface | Dark Navy | `#101827` | Badge label fill, grid lines |
| Primary accent | Electric Cyan | `#00F5FF` | Node outlines, stats titles, streak ring |
| Secondary accent | Cyber Blue | `#00BFFF` | Connection lines, glow, graph area |
| Signal | Neon Green | `#39FF88` | One status dot per graphic, "in development" badge, stats icons |
| Text | White | `#F4F7FA` | Wordmark, card text |
| Secondary text | Muted Gray | `#929EAE` | Labels, dates |
| Badge fill (derived) | Deep Cyber Blue | `#0B6FA4` | Focus badges, a darker blue so white text stays readable |

**Banner concept.** The wordmark is drawn from chamfered strokes, so it does not depend on any installed font. The right side shows one core connected to five nodes, which is "one technical identity, multiple domains". The nodes run clockwise from the top in the order of your five pillars: security, engineering, intelligence, research, innovation. Motion is a single slow pulse on the core, and it stops when a viewer has reduced motion turned on.

**Badge style.** Hero badges use shields.io `for-the-badge` with label `101827` and message `0B6FA4`, worded as "focus", so they describe direction and not credentials. The status badge is `flat-square` with neon green fill, used only for live status.

**Icon strategy.** Languages and platforms use skillicons.dev in the dark theme. Tools without icons (Nmap, Burp Suite, Wireshark and so on) use plain code chips. A technology moves from the exploration radar to the project-backed table only when a public repository uses it.

**Section layout.** Hero, About, Core domains, Technology stack, Featured projects, Research lab, Solutions, Analytics, Contact. Each section has one primary table, and long or empty material sits in a collapsible block. GitHub already underlines every `##` heading, so dividers appear only under the hero and in the footer.

**Recommended image assets.**

| Asset | Size and format | Where it goes |
|---|---|---|
| `banner.svg` | 1200 x 360 SVG (included) | README hero |
| `lab.svg` | 1200 x 150 SVG (included) | Research lab |
| `divider.svg` | 1200 x 24 SVG (included) | Under the hero and in the footer |
| Social preview | 1280 x 640 PNG or JPG, under 1 MB | Repo **Settings > Social preview** (SVG is not accepted there) |
| Project screenshots | 1600 x 900 PNG, no personal data | `docs/screenshots/` in each repo |
| Demo clip | MP4 or GIF, about 10 s, under 5 MB | Top of each project README |

## 3. Repository improvement plan

**Pin six repositories**, one per category that has real work. Pin Auralis once its repository is public.

**Naming.** Lowercase kebab-case, `<domain>-<what>`, for example `sec-log-analyzer`, `ai-agent-playground`, `tool-cli-toolkit`, `web-portfolio`, `lab-notes`. Finished products keep their own name (Auralis).

**Descriptions.** One line, under 100 characters: what it is, who it is for, one differentiator. Example: *Ad-free YouTube Music desktop player for Windows with a glass UI and adaptive ambient lighting.*

**Topics** (up to 20 per repo, lowercase with hyphens; add only what is true for that repo):

| Category | Topics |
|---|---|
| Security research | `cybersecurity` `security-research` `vulnerability-research` `application-security` `incident-response` `digital-forensics` |
| Security tools | `security-tools` `red-team` `blue-team` `detection-engineering` `security-automation` |
| Web | `web-development` `fullstack` `rest-api` `react` `nodejs` |
| Apps | `desktop-app` `windows` `android` `cross-platform` |
| AI | `machine-learning` `llm` `ai-agents` `generative-ai` |
| Automation and tools | `automation` `cli` `developer-tools` |
| R&D | `proof-of-concept` `research` `experiments` |

**README structure for every repo.**

1. Name and a one-line description
2. Status and license badges
3. Screenshot or short demo
4. Features (shipped) kept separate from Roadmap (planned)
5. Install and usage
6. Tech stack
7. Security and responsible use (security tools: authorized use only, no warranty)
8. License and contributing

**Screenshots and demos.** Show the real interface in the dark theme, cropped to 16:9, with tokens, emails and personal data removed. Add one clip of the main flow at the top of the README.

**License and contribution files.** Choose MIT or Apache-2.0 for permissive reuse (Apache-2.0 adds a patent grant), or GPL-3.0 if derivatives must stay open. A repo with no license is all-rights-reserved, so others cannot legally reuse it. For security tools add an authorized-use notice. Add `SECURITY.md` (turn on private vulnerability reporting), `CONTRIBUTING.md` and issue templates. On every repo, enable Dependabot alerts, secret scanning and code scanning. For a security-focused profile, that is the visible proof.

## 4. Profile optimization

| Field | Recommendation |
|---|---|
| Bio (160 character limit) | `Securing digital systems and engineering intelligent software. Cybersecurity, AI and R&D.` (89 characters). Alternative: `Cybersecurity, software and AI. Building and researching secure, intelligent systems.` (85) |
| Name | `GHOSTBEROK`, or your real name followed by GHOSTBEROK if you want it |
| Website | Your portfolio URL once it exists. Leave it empty until then; do not point it at a placeholder. |
| Social accounts | Add only verified links (LinkedIn, personal site, a community profile) |
| Status | `Open to collaboration` |
| Profile repo description | `Profile README for GHOSTBEROK: cybersecurity, software engineering, AI and R&D.` (79) |
| Profile repo topics | `github-profile` `profile-readme` `cybersecurity` `software-engineering` `artificial-intelligence` |

## 5. Quality assurance

**Checked here**

- The README parses cleanly as CommonMark: 10 tables with consistent columns, and all 9 in-page links resolve to a heading.
- All 3 local assets exist. The SVGs are valid XML and were rendered in headless Chromium on a dark page, a light page and a phone-width page. The wordmark and the line beneath it stay legible at all widths. The small diagram labels are decorative and repeated as text.
- HTML is limited to tags GitHub allows, with no scripts, style blocks, inline styles or iframes.
- Every stats URL uses `GHOSTBEROK`, every color value is valid 6-digit hex, and parameters are limited to those each service documents.
- Every image has alt text. The dividers are decorative and use empty alt text on purpose.
- Nothing is typed by hand that reads as a statistic, star count, download count, credential, date or years of experience. Project details come only from what you have told me, and everything else is a marked placeholder.

**Not checkable from here.** My environment has no internet access, so I could not load shields.io, skillicons.dev, github-readme-stats, streak-stats or the activity graph. The URLs follow each project's documented format as I know it. After pushing, open the profile in a private window on desktop and phone and confirm every card appears.

**If a card is blank.** The public Vercel hosts are sometimes rate-limited. Options: wait and reload; self-host github-readme-stats on your own free Vercel account and swap the host in the URL; or generate cards inside your own repo with the github-profile-summary-cards GitHub Action. Copy its workflow from that project's README so you get its current version, since I have not verified it.

**One wording flag.** Your suggested headline says "Cybersecurity Engineer". I kept it as written. If you would rather not imply a job title yet, "Cybersecurity Developer" reads the same without one.

## 6. Templates for future edits

**Project card** (paste under Featured projects, change the heading and fields):

```html
### Project name

One sentence on what it is and who it is for.

<table>
  <tr><th align="left">Category</th><td>Matching category</td></tr>
  <tr><th align="left">Status</th><td><img src="https://img.shields.io/badge/status-in_development-39FF88?style=flat-square&amp;labelColor=101827" alt="Status: in development"></td></tr>
  <tr><th align="left">Stack</th><td>Languages and frameworks</td></tr>
  <tr><th align="left">Features</th><td>Shipped features only</td></tr>
  <tr><th align="left">Repository</th><td><a href="https://github.com/GHOSTBEROK/REPO">GHOSTBEROK/REPO</a></td></tr>
  <tr><th align="left">Documentation</th><td><a href="https://github.com/GHOSTBEROK/REPO#readme">README</a></td></tr>
</table>
```

Status badge values: `in_development` (neon green `39FF88`), `stable` or `released` (same green), `archived` (gray `929EAE`). Then update the "All project categories" table to link the new project.

**Lab notebook entry.** Replace "Awaiting first entry" with a link to the write-up and a maturity label, for example `[Title of write-up](link)` followed by `Concept`, `In progress`, `Proof of concept` or `Completed`.

**Promoting a technology.** Move its icon from the exploration radar into the project-backed table and name the project that uses it.
