# CLAUDE.md — Travel Room Nepal

This file guides AI assistants working on this repository.
Read it fully before making any changes.

---

## Project overview

A single-page landing page for **Travel Room Nepal**, a small personal jungle tour
company run by Khagendra, based in Sauraha (Chitwan National Park, Nepal).

The page targets Dutch and Belgian travelers who have discovered the tour through
word of mouth or social media. Its purpose is to inform first-time visitors about
the experience and guide them toward filling in the interest form.

This is a **static site** — no backend, no framework, no build step.

---

## Hosting

- Platform: GitHub Pages — branch: `main`, folder: root
- Live URL: TBD (custom domain to be connected after launch)
- HTTPS is handled automatically by GitHub Pages via Let's Encrypt

---

## File structure

```
travel-room-nepal/
├── CLAUDE.md           ← you are here
├── README.md           ← human-facing project description
├── index.html          ← the entire page lives here
├── images/
│   ├── hero.jpg        ← full-viewport hero image (jungle/wildlife atmosphere)
│   └── ...             ← any additional photos (update Available images below)
├── css/
│   └── style.css       ← all styles (linked from index.html)
└── .gitignore
```

---

## Available images

*Update this list whenever a new image is added to /images/.*
Use this section to inform design decisions — do not reference images not listed here.

- `hero.jpg` — [describe when added]

---

## Design direction

- **Aesthetic:** organic, immersive — field journal meets tropical naturalism
- **Colors:** deep jungle greens, warm earthy tones; no corporate palettes
- **Typography:** bold display font + refined humanist or serif body font (Google Fonts only)
- **Feel:** handcrafted and personal, as if a passionate guide made it — not a travel agency
- **Animations:** subtle scroll-triggered entrance animations via Intersection Observer; CSS only

Do not introduce generic AI aesthetics (Inter, purple gradients, card-grid templates).
Every design decision should reinforce the jungle/nature/adventure feel.

---

## Page sections (in order)

1. **Hero** — full-viewport, headline, subline, season note, scroll cue
2. **Prijzen** — three pricing tiers + what's included + deposit note
3. **Dagprogramma** — four-day timeline (dag 1–4), vertical layout
4. **Wat meenemen** — six-item visual checklist (icon grid)
5. **Busvervoer** — short info block about bus transfers
6. **Boekingsformulier** — interest form embed placeholder (Google Form)
7. **Footer** — Instagram handle + WhatsApp contact + sign-off

Full content for each section lives in `index.html` as Dutch-language copy.
Do not translate content to English.

---

## Content rules

- **Language:** Dutch throughout (target audience: Dutch/Belgian travelers)
- **Tone:** warm, personal, adventurous — written as if Khagendra is speaking directly
- **Prices:** always show in euro (€) for per-person rates; bus in Nepalese rupees (Rs)
- **Key facts — never change without explicit instruction:**
  - 1 persoon: €315 pp / 2 personen: €249 pp / 3+ personen: €199 pp
  - Voorschot: €25 pp
  - Bus Kathmandu/Pokhara ↔ Sauraha: 1200 Rs pp
  - Instagram: @the_travel_room_nepal
  - WhatsApp: +32 498 43 00 89 (Jonas Verhamme)
  - Season: oktober t/m april

---

## Contact

The primary contact channel for clients is **WhatsApp**, not email or a contact form.

- **Contact person:** Jonas Verhamme (Dutch-speaking co-organiser; handles client communication)
- **WhatsApp number:** +32 498 43 00 89
- Display this as a WhatsApp link in the footer and near the interest form:
  `https://wa.me/32498430089`
- Label it naturally in Dutch, e.g. *"Stuur ons een bericht op WhatsApp"*
- Do not display Khagendra's personal contact details
- Do not add an email address or contact form separate from the Google Form

---

## The interest form

The form in section 6 is **not a booking form** — it is a conversation starter.
It asks four questions:

1. Wat wil je het liefst zien of beleven in de jungle?
2. Waarom wil je dit avontuur maken?
3. Met hoeveel personen kom je?
4. Heb je dieetwensen of allergieën?

The actual form is a Google Form embedded via iframe.
The placeholder in the HTML is: `<div id="form-placeholder">`.
Do not replace this with a custom HTML form — the embed URL will be added later.

When the Google Form URL is available, replace the placeholder with:

```html
<iframe
  src="[GOOGLE_FORM_EMBED_URL]"
  width="100%"
  height="780"
  frameborder="0"
  marginheight="0"
  marginwidth="0"
  style="border: none;">
  Laden…
</iframe>
```

The 780px height comfortably fits four questions, a submit button, and Google's
default form chrome without excessive whitespace. Adjust only if the form renders
with significant empty space at the bottom.

---

## Technical constraints

- **Single HTML file** — all content in `index.html`; styles in `css/style.css`
- **No frameworks** — no React, Vue, Bootstrap, Tailwind, or similar
- **No JS libraries** — vanilla JS only; use Intersection Observer for scroll animations
- **Google Fonts only** — no self-hosted fonts, no Adobe Fonts
- **Mobile-first** — fully responsive; test at 375px, 768px, 1280px
- **No backend** — the form is a Google Form iframe embed; nothing else sends data
- **Performance** — images must be compressed before committing; no unoptimized photos

---

## What NOT to do

- Do not add a navigation bar unless explicitly asked
- Do not add a cookie banner or GDPR notice (static site, no tracking)
- Do not change pricing, dates, or factual content without instruction
- Do not switch the language to English
- Do not introduce a CSS framework or JS library
- Do not add placeholder lorem ipsum — use the real Dutch copy from the brief
- Do not add an email address or separate contact form
- Do not display Khagendra's personal contact details

---

## Future features (not yet built)

- **Field Guide:** a downloadable PDF booklet (animals, plants, Tharu culture)
  with a QR code linking back to the site with a discount — planned as a
  post-trip gift to returning guests
- **Booking form (formulier B):** a separate form for confirmed bookings
  (name, date, bus needed, passport photo upload) — different from the
  interest form and added later
- **Custom domain:** to be connected to GitHub Pages once confirmed
- When these are ready, add them as new sections or linked sub-pages —
  do not restructure the existing page to accommodate them prematurely

---

## Commit style

Use short, descriptive commit messages in English:
- `add hero section with scroll animation`
- `fix pricing layout on mobile`
- `update dag 3 copy`
- `add whatsapp link to footer`
