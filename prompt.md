# Portfolio Website — AI Agent Prompt
## For: Anmol Kanwar | Single-file HTML/CSS/JS Portfolio

---

## Task

Build a single-file portfolio website (`index.html`) using HTML, CSS, and vanilla JavaScript for **Anmol Kanwar**, a Software Development diploma student at SAIT, Calgary. The photo is provided as a separate file — embed it using a relative path `src="photo.png"` in the hero section.

---

## Design Direction

- **Color scheme:** Deep dark background `#0a0a0f`, secondary surfaces `#111118` and `#1a1a24`, accent blue `#63b3ed`, accent purple `#9f7aea`, muted text `#7a7a9a`, white headings `#ffffff`
- **Typography:** `Syne` (Google Fonts, weight 700/800) for display headings — `Inter` (Google Fonts, weight 300–600) for body text — load both from Google Fonts
- **Do NOT use:** neon glows, rainbow color schemes, excessive animations, gradient text, or anything that looks AI/vibe-coded
- **Atmosphere:** Subtle radial glow blobs in the background at 6–10% opacity using accent colors — purely atmospheric
- **Animations:** Scroll-triggered fade-up using `IntersectionObserver` on section entry
- **Responsive:** Fully responsive, single column on screens below 900px

---

## Sections

### 1. Fixed Navbar

- Left: Logo `AK` in accent blue, Syne font
- Right: Nav links — Skills · Projects · Experience · Education · Contact
- Background: `rgba(10,10,15,0.85)` with `backdrop-filter: blur(14px)`
- Bottom border: `1px solid rgba(255,255,255,0.07)`
- Nav link text: uppercase, small letter-spacing, muted color, hover turns white

---

### 2. Hero — Two Column Grid

**Left column:**
- Eyebrow: `Software Developer` in accent blue, uppercase, small tracking, preceded by a short horizontal line
- H1: `Anmol` on line 1 / `Kanwar` on line 2 — "Kanwar" in accent blue — Syne font, ~5rem, weight 800
- Subparagraph: *"Software Development student at SAIT building web, database, and cloud-based applications. Passionate about clean code, real-world problem solving, and collaborative development."*
- Two CTA buttons:
  - `View My Work →` — filled, accent blue background, dark text
  - `Get in Touch` — outlined, accent blue border and text

**Right column:**
- Photo (`photo.png`) — aspect ratio 3/4, `object-fit: cover`, `object-position: top center`, `border-radius: 18px`
- Thin gradient border behind the image via a pseudo-element (accent blue → accent purple, low opacity)
- Floating badge at bottom-left of image:
  - Pulsing green dot (CSS animation)
  - Text: **"Open to Work"** / sub-text: *"Entry-level & Internships"*

---

### 3. Skills Section

- Background: `#111118`
- Eyebrow: `What I Know` — Title: `Technical Skills`
- CSS grid: `repeat(auto-fit, minmax(220px, 1fr))`
- Cards with category label + pill tags. On hover: lift 3px, border brightens to accent blue

| Category | Tags |
|---|---|
| Languages | JavaScript, Java, Python, SQL, HTML, CSS |
| Frameworks & Libraries | React, Flask, Tailwind CSS |
| Databases | Oracle SQL, PL/SQL, MySQL |
| Tools & Platforms | Git, GitHub, Docker, Microsoft Azure, VS Code, Postman |
| Concepts *(spans 2 cols)* | REST APIs, OOP, Agile Development, Software Testing, Responsive Web Design |

**Tag style:** `background: rgba(99,179,237,0.08)` — `border: 1px solid rgba(99,179,237,0.15)` — `border-radius: 6px` — `font-size: 0.8rem`

---

### 4. Projects Section

- Background: `#0a0a0f`
- Eyebrow: `What I've Built` — Title: `Projects`
- One project card with a **2px gradient top border** (accent blue → accent purple):

**Gerry's Docks Website** *(Capstone Project)*

> A full professional website for a real business — Gerry's Docks — helping customers browse dock products, accessories, and initiate quote requests, all in one place.

Bullet points (prefix `→` in accent blue):
- Built backend-related functionality supporting product info, quote requests, and customer inquiries
- Collaborated in a team using Agile sprints, GitHub, and clearly defined project roles
- Designed a user-friendly quote system letting customers select dock options and accessories
- Focused on maintainability — built for easy future updates and customer communication

Tech tags: `React` `JavaScript` `Database` `GitHub` `Agile`

---

### 5. Experience Section

- Background: `#111118`
- Eyebrow: `Where I've Worked` — Title: `Experience`
- Timeline style: left border line, dot marker in accent blue

**Asset Protection Associate — Walmart**
Calgary, AB · 2026 – Present

- Monitor store activity to prevent loss and maintain a safe shopping environment
- Communicate professionally with customers, team members, and management in a fast-paced environment
- Apply sharp observation, attention to detail, and problem-solving skills daily
- Prepare accurate incident reports and maintain documentation

---

### 6. Education Section

- Background: `#0a0a0f`
- Eyebrow: `Where I'm Learning` — Title: `Education`
- One card (dark bg, border, `border-radius: 14px`) with a 🎓 icon box on the left

**Software Development Diploma**
Southern Alberta Institute of Technology (SAIT) *(in accent blue)*
Calgary, AB · Expected Graduation: August 2026

Coursework: Web Development · Database Management · Object-Oriented Programming · Cloud Computing · Software Testing · Systems Analysis

---

### 7. Contact Section

- Background: `#111118`
- Eyebrow: `Let's Connect` — Title: `Get in Touch`
- 2-column grid of clickable `<a>` tag cards — hover: lift 2px, border brightens

| Icon | Label | Value | Link |
|---|---|---|---|
| ✉️ | Email | kanwar05.anmol@gmail.com | `mailto:` |
| 📱 | Phone | +1 825 760 4385 | `tel:` |
| GitHub SVG logo | GitHub | github.com/Kanwar0135 | opens new tab |
| LinkedIn SVG logo | LinkedIn | linkedin.com/in/anmol-kanwar-9904662b9 | opens new tab |

Use real SVG paths for GitHub and LinkedIn logos (not emoji).

---

### 8. Footer

- Left: `© 2026 Anmol Kanwar. All rights reserved.`
- Right: `Built with HTML · CSS · JS`
- Border top: `1px solid rgba(255,255,255,0.07)`
- Text color: muted (`#7a7a9a`)

---

## JavaScript Requirements

1. **Scroll animations:** `IntersectionObserver` on all `.fade-up` elements — adds `.visible` class which transitions `opacity: 0 → 1` and `translateY(24px) → 0`, duration `0.6s ease`, staggered delay per element
2. **Smooth scroll:** All `<a href="#...">` nav links scroll smoothly to target section
3. **Pulsing badge dot:** CSS `@keyframes pulse` animating opacity 1 → 0.4 → 1, duration 2s infinite

---

## Quality Rules

- No `<form>` tags — use `<a href="mailto:">` and `<a href="tel:">` for contact
- No external JS libraries or frameworks — vanilla JS only
- All fonts loaded from Google Fonts via `<link>` in `<head>`
- No placeholder or lorem ipsum text — use only the content specified above
- All sections must have `id` attributes matching the nav links
- Mobile breakpoint at 900px: hero becomes single column, nav links reduce gap, contact grid becomes single column
- The file must open correctly in a browser with no build step — just `index.html` + `photo.png` in the same folder

