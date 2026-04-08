# CLAUDE.md — ElegantFin

Guide for AI assistants working in this repository.

---

## Project Overview

**ElegantFin** is a pure CSS theme for the [Jellyfin](https://jellyfin.org) media server web interface. It provides a dark, Netflix-inspired UI with smooth transitions, responsive layouts, and an optional add-on system.

- **Type**: CSS-only theme — no JavaScript, no build tools, no backend, no database
- **Distribution**: Via jsDelivr CDN (GitHub-based) and direct paste into the Jellyfin dashboard
- **Documentation language**: French (README.md, CONTRIBUTING.md, commit messages)
- **License**: GPL-2.0

---

## Repository Structure

```
ElegantFin/
├── Theme/
│   ├── ElegantFin-theme-v{YY.MM.DD}.css          # Versioned source files (16 versions)
│   ├── ElegantFin-theme-nightly.css               # Active development file (copy of latest version)
│   ├── ElegantFin-jellyfin-theme-build-latest-minified.css  # Production distribution file
│   └── assets/
│       ├── add-ons/
│       │   ├── custom-media-covers-*.css           # Library cover art add-on
│       │   └── media-bar-plugin-support-*.css      # Media Bar plugin compatibility add-on
│       └── img/
│           ├── library-covers/
│           │   ├── originals/                      # Source JPG images
│           │   └── *.webp                          # Optimized WebP production images
│           └── banner.png
├── Previews/                                       # Screenshots organized by version and device
│   └── previews-v{VERSION}/
│       └── {desktop|mobile|tv}/
├── docs/
│   └── index.html                                  # Single-page HTML documentation (French)
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.md
│   │   └── feature_request.md
│   └── PULL_REQUEST_TEMPLATE.md
├── README.md                                       # Main documentation (French)
├── CONTRIBUTING.md                                 # Contribution guidelines (French)
├── custom-media-covers.md                          # Add-on guide (French)
└── workspace.code-workspace                        # VS Code settings (Prettier, format on save)
```

---

## Development Workflow

### The three CSS files

There are three roles for CSS files:

| File | Purpose |
|------|---------|
| `Theme/ElegantFin-theme-v{YY.MM.DD}.css` | Canonical versioned source — edit this |
| `Theme/ElegantFin-theme-nightly.css` | Nightly/dev copy — kept in sync with latest version |
| `Theme/ElegantFin-jellyfin-theme-build-latest-minified.css` | Production distribution copy |

**After editing the versioned source**, copy it to the other two:
```bash
cp Theme/ElegantFin-theme-v26.04.07.css Theme/ElegantFin-theme-nightly.css
cp Theme/ElegantFin-theme-v26.04.07.css Theme/ElegantFin-jellyfin-theme-build-latest-minified.css
```

The same pattern applies to add-on files:
```bash
cp Theme/assets/add-ons/custom-media-covers-v{VERSION}.css Theme/assets/add-ons/custom-media-covers-nightly.css
cp Theme/assets/add-ons/custom-media-covers-v{VERSION}.css Theme/assets/add-ons/custom-media-covers-latest-min.css
```

### Creating a new version

1. Copy the latest versioned file with the new `YY.MM.DD` date:
   ```bash
   cp Theme/ElegantFin-theme-v26.04.07.css Theme/ElegantFin-theme-v{NEW_DATE}.css
   ```
2. Edit the new versioned file.
3. Update the version identifier inside the file:
   ```css
   --elegantFinFooterText: "ElegantFin v{NEW_DATE}";
   ```
4. Update the comment header at line 1:
   ```css
   /* ElegantFin Theme for Jellyfin - Modernized v{NEW_DATE} */
   ```
5. Copy to nightly and production files (see above).

### No build step

There is no minifier, transpiler, or bundler. The "minified" file name is historical — the file is copied as-is.

---

## Versioning Convention

- **Format**: `YY.MM.DD` (e.g., `26.04.07` = April 7, 2026)
- **File naming**: `ElegantFin-theme-v{YY.MM.DD}.css`
- **Old versions are kept** in `Theme/` as an archive — do not delete them

---

## CSS Architecture

### Main file layout (`ElegantFin-theme-v{VERSION}.css`)

The file is ~4,100+ lines organized in sections marked by comments:

| Section | Content |
|---------|---------|
| Lines 1–10 | File header comment, add-on imports (commented out by default) |
| Lines 8–9 | Google Fonts import (Inter family) |
| Lines 11–190 | `:root` — all CSS custom properties (variables) |
| ~200–250 | Material Icons Round font face |
| ~270–500 | Card components (`.card`, `.cardBox`, `.cardScalable`, `.cardOverlayContainer`) |
| ~500–1000 | Episode/item grid sizing and responsive breakpoints |
| ~1000–1450 | Layout utilities, mobile/desktop/TV specifics |
| ~1450–3800 | Pages, detail views, player, menus, forms |
| ~3830–4010 | Header (solid vs. transparent app bar) |
| ~4100–4137 | Media Bar plugin compatibility |

### CSS custom properties

All theming is done through CSS custom properties on `:root`. Key groups:

**Colors:**
```css
--darkerGradientPoint: #111827;
--lighterGradientPoint: #1d2635;
--activeColor: rgb(119, 91, 244);        /* Purple accent */
--btnMiniPlayColor: rgb(41 154 93);       /* Green play button */
--textColor: rgb(209, 213, 219);
```

**Spacing and shape:**
```css
--largerRadius: 1.25em;
--largeRadius: 1em;
--smallRadius: 0.5em;
--borderWidth: 0.06em;
--sidePadding: 3.3%;
```

**Animation:**
```css
--transitionFast: 0.15s cubic-bezier(0.4, 0, 0.2, 1);
--transitionMedium: 0.3s cubic-bezier(0.4, 0, 0.2, 1);
--transitionSlow: 0.5s cubic-bezier(0.4, 0, 0.2, 1);
```

**User-overridable variables** (documented in README):
```css
--overlayPlayButtonPosition       /* Play button position on cards */
--extraCardButtonsVisibility      /* Show/hide extra card buttons */
--cardHoverEffect                 /* Enable/disable card hover scaling */
--libraryLabelVisibility          /* Library label visibility */
--appBarHeight                    /* Solid vs. fading app bar */
--loginPageBgUrl                  /* Custom login background image */
```

### Responsive strategy

- **Desktop-first** with mobile and TV overrides via media queries
- **Layout selectors**: `.layout-desktop`, `.layout-mobile`, `.layout-tv` (set by Jellyfin)
- **Grid breakpoints**: Uses `em`-based widths (300em down to 140em) to control poster column counts
- **Units**: Always use `em` — never `px` for sizing

### Key selectors

```css
.card / .cardBox / .cardScalable       /* Media item cards */
.cardOverlayContainer                  /* Hover overlay area on cards */
.cardOverlayFab-primary                /* Play button on cards */
.itemsContainer                        /* Grid wrapper */
.detailPagePrimaryContainer            /* Detail page layout */
.skinHeader-withBackground             /* App header */
.pageTitle                             /* Page headings */
.emby-button / .paper-icon-button-light  /* Buttons */
.layout-{desktop|mobile|tv}            /* Device layout contexts */
.card-hoverable                        /* Cards with hover interaction */
```

---

## Add-on System

Two optional CSS add-ons exist in `Theme/assets/add-ons/`:

| Add-on | File | Purpose |
|--------|------|---------|
| Custom Media Covers | `custom-media-covers-*.css` | Replaces default library cover images with styled versions |
| Media Bar Plugin Support | `media-bar-plugin-support-*.css` | Compatibility styles for the Jellyfin Media Bar third-party plugin |

Add-ons are enabled by uncommenting `@import` lines at the top of the main theme file:
```css
/* @import url(./assets/add-ons/media-bar-plugin-support-nightly.css); */
/* @import url("https://cdn.jsdelivr.net/.../custom-media-covers-latest-min.css"); */
```

Each add-on follows the same versioning and file-copy pattern as the main theme.

---

## Testing

There is no automated test suite. All testing is **manual and visual**.

Test on all three form factors before committing:
- **Desktop** (1080p+, browser)
- **Mobile** (phone-sized, Jellyfin Android app or browser)
- **TV** (10-foot experience, Jellyfin Media Player or Android TV)

Reference tested environment:
- Jellyfin Server v10.11.5+
- Microsoft Edge (Chromium)
- Jellyfin Android App v2.6.3

---

## Contribution Guidelines

From `CONTRIBUTING.md`:

1. **One PR per concern** — do not bundle unrelated changes
2. **Include before/after screenshots** for any visual change
3. **Use `em` units** — never `px` for sizing
4. **Avoid `!important`** — only when absolutely no alternative exists
5. **Minimize new media queries** — reuse existing breakpoints where possible
6. **Test all three form factors** before submitting
7. **Comment complex CSS rules** inline
8. **Open an issue first** for changes to overall layout, color scheme, or core UI behavior

---

## Formatting

Configured in `workspace.code-workspace`:
- **Formatter**: Prettier (VS Code extension `esbenp.prettier-vscode`)
- **Format on save**: enabled
- **Print width**: 120 characters
- **Indentation**: spaces (not tabs)

---

## Commit Message Style

All commit messages are in **French**. Follow these patterns from git history:

```
New: Ajout de l'ellipse aux menus déroulants
Fix: Suppression des contournements temporaires pour le dimensionnement des cartes
Mise à jour de la version CSS et pointage vers la branche personnalisée
Finalisation: traduction docs/index.html + améliorations Netflix CSS
```

Common prefixes: `New:`, `Fix:`, `Mise à jour`, `Finalisation:`, `Amélioration:`

---

## No CI/CD

There are no GitHub Actions workflows, no automated linting, and no deployment pipeline. Releases are managed manually by copying files and pushing to GitHub (which makes them available via jsDelivr CDN automatically).
