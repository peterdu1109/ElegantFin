# ElegantFin Cinema Edition v1.1.2

## [English](#english) | [Francais](#francais)

---

<a name="english"></a>
## English

### Cinema Edition — 20 cinematic modules on top of ElegantFin v26.04.07

This release transforms the ElegantFin theme into a professional, Netflix-inspired streaming experience while keeping full compatibility with desktop, mobile, and TV platforms.

---

#### Glassmorphism & Animations

- **Login page glassmorphism** — Frosted glass card with `backdrop-filter: blur(20px)`, smooth `loginCardAppear` animation, and `@supports` fallback for older browsers
- **Page transitions** — `pageFadeIn` (0.4s) and `sectionSlideIn` (0.5s) animations with cascade delays on sections (0.05s increments)
- **Shimmer effect** — Subtle light sweep on the first row of cards (desktop only, disabled on mobile/TV)
- **Backdrop animation** — Cinematic `detailBackdropIn` with scale + fade on detail pages

---

#### Visual Enhancements

- **Netflix card pop** — Scale 1.06x on hover with glowing borders (`rgba(255,255,255,0.3)`), deep shadows, and text color transition to white
- **Cinema detail page** — Ultra-light titles (weight 100), italic tagline, `line-height: 1.65` synopsis, white Play button with hover lift
- **White progress bars** — Clean `#fff` progress bars replacing theme-colored ones, with glow effect on OSD slider hover
- **Premium badges** — Glass-blurred indicators (`backdrop-filter: blur(8px)`) for count, resolution, and watched badges
- **Glass dialogs** — `backdrop-filter: blur(20px)` on dialogs, `blur(15px)` on drawer/menus/toast/upNext, all with `@supports` fallback

---

#### Typography & Layout

- **Section titles** — Bold (700), negative letter-spacing, hidden chevron arrows, overflow ellipsis with `max-width: calc(100vw - 8em)`
- **Navigation tabs** — White active tab (`#fff`/`#000`), subtle inactive (`rgba(255,255,255,0.06)`) with smooth hover
- **Long titles fix** — Responsive line-clamp (2 desktop, 3 mobile, 2 TV), word-break on metadata, card text overflow handling
- **Typography hierarchy** — Refined font-weights for episode titles (600), secondary text (`dimTextColor`), page title (500)
- **Fluid title sizing** — `clamp(2em, 5vw, 4em)` for smooth scaling across all screen sizes

---

#### Performance & Accessibility

- **TV optimizations** — All `backdrop-filter`, `box-shadow`, animations, `will-change`, and shimmer disabled on TV layout
- **Mobile optimizations** — Reduced blur intensity (`blur(10px)` instead of `blur(20px)`) via `@supports` query
- **GPU hints** — `will-change: transform` on hover only (not permanent), disabled on TV to free GPU memory
- **Reduced motion** — Full `prefers-reduced-motion: reduce` coverage: page transitions, shimmer, login bounce, backdrop fade, card hover
- **Thin scrollbars** — 4px cross-browser scrollbars scoped to `html` (inherited, not universal `*`)
- **Focus-visible** — Keyboard navigation focus rings on tabs, Play button, detail buttons, skip button, login

---

#### Header & OSD

- **Cinema header gradient** — Deep transparent gradient (`rgba(0,0,0,0.75)` to transparent) replacing theme-colored one
- **OSD header glass** — `rgba(0,0,0,0.85)` background with `blur(10px)` on the video player header
- **OSD bottom gradient** — Softer 3-stop gradient (85% to 50% to transparent)
- **Reactive slider** — Expands to `0.5em` on hover, white thumb with `border-radius: 2px`, glow on progress bar
- **Firefox slider** — Full `::-moz-range-thumb` styling matching WebKit (size, border, radius, transitions)
- **Skip button** — Bold (700), `letter-spacing: 0.03em`, `scale(1.03)` on hover

---

#### v1.1.2 — Quality & Compatibility Fixes

- **Bug fixes** — Fixed missing unit (`0.25` → `0.25em`), invalid `border-radius: inherit` in shorthand (Firefox), 6 duplicate CSS properties removed
- **Accessibility** — Alpha picker contrast raised from 20% to 50% opacity (WCAG), tab focus outline restored, complete reduced-motion coverage
- **Performance** — `will-change: transform` moved to hover-only (saves GPU memory), scrollbar scoped to `html` instead of `*`
- **Responsive** — Login card uses `min(28em, calc(100vw - 2em))` for small screens, fluid `clamp()` title sizing
- **Firefox** — Complete `::-moz-range-thumb` and `::-moz-progress-bar` styling
- **Visual consistency** — Named colors (`peru`, `steelblue`, `indianred`, `whitesmoke`) replaced with curated RGB values, `.button-link` uses `var(--dimTextColor)`

---

### Compatibility
- Jellyfin **10.11.x**
- Works on all web browsers (Chrome, Edge, Firefox, Safari), Android app, LG WebOS
- Full `@supports` fallback for browsers without `backdrop-filter`

---

<a name="francais"></a>
## Francais

### Edition Cinema — 20 modules cinematiques par-dessus ElegantFin v26.04.07

Cette version transforme le theme ElegantFin en une experience de streaming professionnelle inspiree de Netflix, tout en gardant la compatibilite complete avec bureau, mobile et TV.

---

#### Glassmorphism & Animations

- **Login glassmorphism** — Carte en verre depoli avec `backdrop-filter: blur(20px)`, animation fluide `loginCardAppear`, et fallback `@supports` pour les anciens navigateurs
- **Transitions de pages** — Animations `pageFadeIn` (0.4s) et `sectionSlideIn` (0.5s) avec delais en cascade sur les sections (increments de 0.05s)
- **Effet shimmer** — Balayage lumineux subtil sur la premiere rangee de cartes (bureau uniquement, desactive sur mobile/TV)
- **Animation du backdrop** — `detailBackdropIn` cinematique avec scale + fade sur les pages de details

---

#### Ameliorations visuelles

- **Cartes Netflix pop** — Scale 1.06x au survol avec bordures lumineuses (`rgba(255,255,255,0.3)`), ombres profondes, et transition du texte vers le blanc
- **Page de details cinema** — Titres ultra-legers (poids 100), tagline italique, synopsis `line-height: 1.65`, bouton Play blanc avec effet de levitation
- **Barres de progression blanches** — Barres `#fff` epurees remplacant les barres colorees, avec effet de lueur sur le slider OSD au survol
- **Badges premium** — Indicateurs floutes en verre (`backdrop-filter: blur(8px)`) pour compteur, resolution et badges vus
- **Dialogues en verre** — `backdrop-filter: blur(20px)` sur les dialogues, `blur(15px)` sur drawer/menus/toast/upNext, tous avec fallback `@supports`

---

#### Typographie & Mise en page

- **Titres de sections** — Gras (700), espacement negatif, fleches chevron masquees, overflow ellipsis avec `max-width: calc(100vw - 8em)`
- **Onglets de navigation** — Onglet actif blanc (`#fff`/`#000`), inactifs subtils (`rgba(255,255,255,0.06)`) avec hover fluide
- **Fix longs titres** — Line-clamp responsive (2 bureau, 3 mobile, 2 TV), word-break sur les metadonnees, gestion overflow du texte des cartes
- **Hierarchie typographique** — Poids affines pour titres d'episodes (600), texte secondaire (`dimTextColor`), titre de page (500)
- **Taille de titres fluide** — `clamp(2em, 5vw, 4em)` pour un dimensionnement fluide sur toutes les tailles d'ecran

---

#### Performances & Accessibilite

- **Optimisations TV** — Tous les `backdrop-filter`, `box-shadow`, animations, `will-change` et shimmer desactives sur layout TV
- **Optimisations mobile** — Intensite de blur reduite (`blur(10px)` au lieu de `blur(20px)`) via requete `@supports`
- **Hints GPU** — `will-change: transform` uniquement au survol (pas permanent), desactive sur TV pour liberer la memoire GPU
- **Mouvement reduit** — Couverture complete `prefers-reduced-motion: reduce` : transitions, shimmer, login bounce, backdrop, hover cartes
- **Scrollbars fines** — Scrollbars 4px cross-browser sur `html` (herite, pas `*` universel)
- **Focus-visible** — Indicateurs de focus clavier sur onglets, bouton Play, boutons detail, skip, login

---

#### En-tete & OSD

- **Degrade cinema** — Degrade transparent profond (`rgba(0,0,0,0.75)` vers transparent) remplacant le degrade du theme
- **Header OSD en verre** — Fond `rgba(0,0,0,0.85)` avec `blur(10px)` sur l'en-tete du lecteur video
- **Degrade OSD bas** — Degrade plus doux a 3 paliers (85% vers 50% vers transparent)
- **Slider reactif** — S'agrandit a `0.5em` au survol, pouce blanc avec `border-radius: 2px`, lueur sur la barre de progression
- **Slider Firefox** — Stylisation complete `::-moz-range-thumb` identique a WebKit (taille, bordure, radius, transitions)
- **Bouton skip** — Gras (700), `letter-spacing: 0.03em`, `scale(1.03)` au survol

---

#### v1.1.2 — Corrections qualite & compatibilite

- **Corrections de bugs** — Unite manquante (`0.25` → `0.25em`), `border-radius: inherit` invalide en shorthand (Firefox), 6 proprietes CSS dupliquees supprimees
- **Accessibilite** — Contraste alpha picker augmente de 20% a 50% (WCAG), outline focus restaure sur onglets, couverture complete reduced-motion
- **Performance** — `will-change: transform` deplace au survol uniquement (economie memoire GPU), scrollbar cible sur `html` au lieu de `*`
- **Responsive** — Carte de login utilise `min(28em, calc(100vw - 2em))` pour petits ecrans, taille de titres fluide avec `clamp()`
- **Firefox** — Stylisation complete `::-moz-range-thumb` et `::-moz-progress-bar`
- **Coherence visuelle** — Couleurs nommees (`peru`, `steelblue`, `indianred`, `whitesmoke`) remplacees par des valeurs RGB, `.button-link` utilise `var(--dimTextColor)`

---

### Compatibilite
- Jellyfin **10.11.x**
- Fonctionne sur tous les navigateurs web (Chrome, Edge, Firefox, Safari), application Android, LG WebOS
- Fallback `@supports` complet pour les navigateurs sans `backdrop-filter`
