# Sudipta's Kitchen — Website Project Documentation

## Purpose

This is the project handover / continuation document for the Sudipta's Kitchen website.

If the project is paused and resumed later, read this file first. It records the current brand decisions, technical setup, domain/DNS configuration, files, design decisions, known problems, and planned future work.

---

## 1. Project Overview

**Business / website name:** Sudipta's Kitchen

**Current website purpose:** A simple coming-soon landing page for a future food business.

**Location shown:** Helsingborg, Sweden

**Current design direction:** Dark, warm, premium, elegant.

The site is intentionally simple at this stage. The goal is to establish the brand identity first and expand the website gradually.

---

## 2. Brand Decisions

### Brand name

The current display name is:

**Sudipta's Kitchen**

Keep the spelling and apostrophe unless explicitly changed later.

The business name should be visually prominent.

### Visual hierarchy

The intended hierarchy is:

1. Logo
2. **Sudipta's Kitchen**
3. "Something delicious is coming soon."
4. "Coming soon."
5. Helsingborg, Sweden

The temporary coming-soon message should not visually overpower the business name.

### Typography

Preferred display font:

**Cormorant Garamond**

It is loaded from Google Fonts and is used for the brand and major display text.

The font was selected because the previous plain/default treatment looked too generic.

---

## 3. Current Logo

The site uses the custom `logo.png`.

The logo contains:

- Circular gold outline
- Stylized kettle / teapot
- Large intertwined SK monogram
- "INDIA UNDISCOVERED"
- Gold artwork on a black background

### Critical asset rule

`logo.png` must remain in the same repository folder as `index.html`.

Current HTML:

```html
<img
  src="logo.png"
  alt="Sudipta's Kitchen logo"
  class="logo"
>
```

Do not use a local Windows path such as `C:\Users\...` in the HTML.

The relative path `logo.png` is correct for GitHub Pages.

---

## 4. Repository

### GitHub repository

`dipanjansikdar/sudiptaskitchen`

### Branch

`main`

### Visibility

Public

### Current repository files

```text
sudiptaskitchen/
├── .git/
├── CNAME
├── index.html
└── logo.png
```

### Local repository

```text
C:\Users\dipanjan\Documents\GitHub\sudiptaskitchen
```

GitHub Desktop is now being used to manage the local repository.

---

## 5. GitHub Pages

### Pages source

**Deploy from a branch**

Branch:

`main`

Folder:

`/(root)`

### Custom domain

Current GitHub Pages custom domain:

`www.sudiptaskitchen.se`

### HTTPS

**Enforce HTTPS is enabled.**

This was confirmed after the domain/DNS setup progressed.

---

## 6. CNAME

Repository contains:

`CNAME`

Current intended content:

```text
www.sudiptaskitchen.se
```

If the domain configuration is changed later, check both GitHub Pages and the CNAME file.

Do not accidentally remove the CNAME file.

---

## 7. Domain and DNS

### Main domain

`sudiptaskitchen.se`

DNS is managed through Cloudflare.

Cloudflare dashboard was successfully accessed for the domain.

### Related domains previously discussed

- `sudiptaskitchen.se`
- `www.sudiptaskitchen.se`
- `saffronkettle.com`
- `saffronkettle.se`

Do not assume all of these currently point to the same site.

The active GitHub Pages custom domain is:

`www.sudiptaskitchen.se`

---

## 8. Loopia Parked Page Problem

At one point visiting:

`sudiptaskitchen.se`

showed a Loopia page:

**"Parked at Loopia"**

This was a domain/DNS routing issue, not an HTML problem.

If the Loopia parked page appears again:

1. Check Cloudflare DNS records.
2. Check Cloudflare nameservers.
3. Check GitHub Pages custom domain.
4. Check the repository CNAME.
5. Test `www.sudiptaskitchen.se`.
6. Test `sudiptaskitchen.se`.
7. Only change HTML if the domain is actually reaching GitHub Pages.

Do not repeatedly edit the website to fix a DNS routing problem.

---

## 9. Cloudflare Web Analytics

Cloudflare Web Analytics was accessed successfully.

Observed location in dashboard:

Cloudflare → Analytics → Web Analytics

Site:

`sudiptaskitchen.se`

Available metrics include:

- Page load time
- Visits
- Page views
- Core Web Vitals

At the time it was checked, Visits showed:

`0`

This was expected because the website had only recently been configured / had little recorded traffic.

Future analytics questions can include:

- Visitors
- Page views
- Countries
- Referrers
- Devices
- Traffic trends
- Popular pages

---

# 10. Current Landing Page

The current page is a centered coming-soon landing page.

### Background

Current background:

```css
--background: #250806;
```

This is a very dark warm brown / burgundy.

The previous cream background was considered too bright and visually shocking when the page opened.

The dark background was tested locally and approved.

### Gold

```css
--gold: #e4ae43;
```

### Cream

```css
--cream: #f5ecd8;
```

The current palette is:

- Dark warm brown
- Gold
- Warm cream

This is the approved direction.

---

## 11. Current Landing Page Content

### Logo

`logo.png`

### Brand name

```text
Sudipta's Kitchen
```

### Main message

```text
Something delicious
is coming soon.
```

### Secondary line

```text
Coming soon.
```

### Location

```text
Helsingborg, Sweden
```

### Intentionally removed

This text was removed:

```text
We are preparing something special.
```

It was considered unnecessary.

---

## 12. Current CSS / Design Targets

### Desktop logo

```css
.logo {
  width: 300px;
  height: 300px;
}
```

### Brand name

```css
.brand-name {
  color: var(--gold);
  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(52px, 7vw, 76px);
  font-weight: 600;
  letter-spacing: 4px;
}
```

### Main headline

```css
h1 {
  color: var(--cream);
  font-family: "Cormorant Garamond", Georgia, serif;
  font-size: clamp(32px, 4.5vw, 46px);
  font-weight: 500;
}
```

### Mobile logo

```css
.logo {
  width: 210px;
  height: 210px;
}
```

### Mobile brand

```css
.brand-name {
  font-size: 42px;
  letter-spacing: 2.5px;
}
```

The page includes a mobile media query and should remain responsive.

---

# 13. Current HTML Structure

Conceptually:

```text
HTML
└── HEAD
    ├── charset
    ├── viewport
    ├── title
    ├── Google Fonts
    └── CSS
        ├── colour palette
        ├── reset
        ├── page
        ├── logo
        ├── brand name
        ├── headline
        ├── coming soon
        ├── footer
        └── mobile media query

BODY
└── main.page
    ├── logo.png
    ├── Sudipta's Kitchen
    ├── Something delicious / is coming soon.
    ├── Coming soon.
    └── Helsingborg, Sweden
```

---

# 14. Current Status

### Working

- GitHub repository exists.
- GitHub Pages is configured.
- Custom domain is configured.
- HTTPS is enabled.
- `logo.png` exists in the local repository.
- Dark background design works locally.
- Logo loads locally.
- Brand name is prominent.
- Cormorant Garamond is used.
- Extra supporting sentence has been removed.

### Current local test

The local page was tested directly from:

```text
C:\Users\dipanjan\Documents\GitHub\sudiptaskitchen\index.html
```

The dark design rendered correctly and the logo loaded.

### Current pause point

The dark design has been approved and is ready to be committed through GitHub Desktop.

---

# 15. GitHub Desktop Workflow

Current repository in GitHub Desktop:

`sudiptaskitchen`

Current branch:

`main`

### Normal future workflow

1. Edit files inside:
   `C:\Users\dipanjan\Documents\GitHub\sudiptaskitchen`
2. Save.
3. Open GitHub Desktop.
4. Review changed files.
5. Review the diff.
6. Enter a meaningful commit summary.
7. Commit to `main`.
8. Push to origin.
9. Wait for GitHub Pages deployment.
10. Test the live site.
11. If something is wrong, determine whether it is HTML/CSS or DNS before changing anything.

### Prefer small commits

Examples:

```text
Test dark landing page design
```

```text
Increase brand prominence
```

```text
Add landing page logo
```

Do not combine unrelated changes unnecessarily.

---

# 16. Previous Design Problems and Decisions

## Problem: Cream background

The original cream background:

```css
#f5ecd8
```

looked visually shocking when the page first opened.

### Decision

Use a dark warm background:

```css
#250806
```

This was tested and approved.

---

## Problem: Coming-soon headline dominated

Earlier:

```text
Something delicious
is coming soon.
```

was visually stronger than:

```text
Sudipta's Kitchen
```

### Decision

Make the brand name larger and more prominent.

The temporary headline remains secondary.

---

## Problem: Brand font was too plain

The previous brand typography looked generic.

### Decision

Use:

**Cormorant Garamond**

for the brand and display typography.

---

## Problem: Extra supporting text

Removed:

```text
We are preparing something special.
```

The page is cleaner without it.

---

## Problem: Logo not loading

At an earlier stage the HTML referenced `logo.png`, but the image was not available at the expected deployed path.

### Solution

Keep:

```text
logo.png
```

beside:

```text
index.html
```

in the repository root.

---

## Problem: Loopia parked page

This was a DNS/domain-routing problem.

### Rule

Do not try to fix DNS by changing HTML.

---

# 17. Brand Story Direction Previously Discussed

Possible story wording:

> Rooted in Bengal. Shaped by India. Inspired by discovery.

Another phrase:

> Conceived in Sudipta's Kitchen.

Important:

The website should not overemphasize Bengal.

The founder's Bengali background can be part of the story, but the brand should represent Indian cuisine broadly.

The logo already contains:

> INDIA UNDISCOVERED

This should be considered when future brand copy is developed.

---

# 18. Future Website Structure

The landing page will eventually become a fuller business website.

Previously discussed sections:

1. Hero
2. Our Story
3. What We Serve
4. Why Sudipta's Kitchen
5. Featured Food / Menu
6. Contact / Order
7. Footer

Do not add everything at once.

Build incrementally.

---

# 19. Future Brand Tone

Desired impression:

- Premium
- Warm
- Authentic
- Personal
- Elegant
- Indian
- Welcoming to Swedish customers
- Not overly corporate
- Not generic
- Food-focused
- Story-driven

Avoid a generic Indian restaurant template.

The brand should feel personal and culinary while remaining professional.

---

# 20. Saffron Kettle History

A related brand concept previously explored was:

**Saffron Kettle**

Important historical preferences:

- Initials should be **SK**
- "Saffron" should be the first word

Domains related to this concept were also discussed.

However, the current website repository and visible brand are:

**Sudipta's Kitchen**

Do not change the visible brand to Saffron Kettle unless explicitly requested.

---

# 21. Domain Redirect History

Previously discussed possible long-term behavior:

```text
sudiptaskitchen.se
        ↓
saffronkettle.com
```

and/or:

```text
saffronkettle.se
        ↓
saffronkettle.com
```

These were ideas, not the current confirmed implementation.

Before changing redirects, verify the actual business/domain strategy.

---

# 22. Future Website Development

## Phase 1 — Current landing page

- Dark premium background
- Custom logo
- Prominent brand name
- Coming-soon message
- Location
- Mobile responsiveness

This is the current phase.

## Phase 2 — Brand polish

Possible additions:

- Gold decorative details
- Better spacing
- Very subtle animation
- Favicon
- Social media links
- SEO metadata
- Open Graph metadata

Avoid excessive animation.

## Phase 3 — Our Story

Potential content:

- Cooking journey
- Indian food
- Personal inspiration
- Discovery
- Home-style authenticity

Do not invent final business claims without confirmation.

## Phase 4 — Menu

Eventually create a proper menu.

Possible categories:

- Starters
- Main dishes
- Rice
- Breads
- Vegetarian
- Chicken
- Fish
- Desserts
- Specials

Do not invent final dishes or prices.

## Phase 5 — Ordering / Contact

Possible additions:

- Contact details
- Ordering
- Catering
- Event enquiries
- Social media
- Online ordering

## Phase 6 — Launch

Replace coming-soon content with actual operating information when the business is ready.

---

# 23. Future SEO

Eventually consider:

```html
<meta name="description" content="...">
```

Open Graph:

```html
<meta property="og:title" content="Sudipta's Kitchen">
<meta property="og:description" content="...">
<meta property="og:image" content="...">
```

Also consider:

- Favicon
- Canonical URL
- Schema.org structured data
- Google Search Console
- Proper page headings
- Social sharing preview

Not required for the current simple page.

---

# 24. Future Analytics

Cloudflare Web Analytics is already available.

Potential future questions:

- How many people visited?
- How many page views?
- Where are visitors from?
- How did they find the site?
- What devices are they using?
- Which pages are most popular?
- How is traffic changing over time?

For the simple landing page, Cloudflare Web Analytics may be sufficient.

A more advanced analytics system can be considered later if the site becomes larger.

---

# 25. Technical Rules

### Keep assets together

Current root:

```text
index.html
logo.png
CNAME
```

### Use relative asset paths

Correct:

```html
<img src="logo.png">
```

Incorrect:

```html
<img src="C:\Users\dipanjan\Documents\GitHub\sudiptaskitchen\logo.png">
```

### Separate DNS and website problems

If the wrong page appears:

1. Check DNS.
2. Check GitHub Pages.
3. Check CNAME.
4. Check the domain.
5. Only then investigate HTML.

### Do not silently change brand decisions

Keep the approved:

- Dark background
- Gold branding
- Cormorant Garamond
- Prominent Sudipta's Kitchen
- Custom logo

unless explicitly asked to change them.

---

# 26. Current Baseline Snapshot

```text
Brand:
Sudipta's Kitchen

Repository:
dipanjansikdar/sudiptaskitchen

Branch:
main

Hosting:
GitHub Pages

Pages source:
main / root

Custom domain:
www.sudiptaskitchen.se

DNS provider:
Cloudflare

Registrar:
Loopia

HTTPS:
Enabled

Analytics:
Cloudflare Web Analytics

Main asset:
logo.png

Display font:
Cormorant Garamond

Background:
#250806

Gold:
#e4ae43

Cream:
#f5ecd8

Status:
Coming-soon landing page

Design:
Approved dark premium version

Current next step:
Commit current changes through GitHub Desktop
```

---

# 27. Resume Checklist

When returning after a break:

- [ ] Read this document.
- [ ] Open GitHub Desktop.
- [ ] Confirm repository is `sudiptaskitchen`.
- [ ] Confirm branch is `main`.
- [ ] Confirm local repository path.
- [ ] Confirm `index.html` exists.
- [ ] Confirm `logo.png` exists.
- [ ] Confirm `CNAME` exists.
- [ ] Check GitHub Pages.
- [ ] Check custom domain.
- [ ] Check HTTPS.
- [ ] Check Cloudflare DNS.
- [ ] Test `www.sudiptaskitchen.se`.
- [ ] Test `sudiptaskitchen.se`.
- [ ] Confirm the site is not showing the Loopia parked page.
- [ ] Test the local HTML.
- [ ] Confirm the logo loads.
- [ ] Confirm dark background is still the baseline.
- [ ] Confirm Sudipta's Kitchen remains visually prominent.

Before editing, classify the task as one of:

- HTML/content
- CSS/design
- Image/asset
- Domain/DNS
- GitHub Pages
- Analytics
- SEO

Avoid mixing unrelated changes.

---

# 28. Change Log

### Initial site

Created a simple Sudipta's Kitchen coming-soon landing page.

### Logo

Added custom `logo.png`.

### Brand prominence

Made "Sudipta's Kitchen" more prominent than the temporary coming-soon message.

### Typography

Changed the display typography to Cormorant Garamond.

### Supporting copy

Removed:

```text
We are preparing something special.
```

### Background

Changed from bright cream to dark warm brown.

### Current design

Dark premium landing page approved.

### GitHub workflow

Project moved toward management through GitHub Desktop.

---

# 29. End State of This Work Session

The current dark landing page is approved.

The current website changes are ready to be committed through GitHub Desktop.

**Important:** This documentation file is intended to be committed together with the website changes so that the project can be resumed later without reconstructing the decisions from old conversations.

When resuming, start by checking GitHub Desktop and the current repository state, then continue from the approved dark landing-page baseline.
