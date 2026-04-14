# ElegantFin Cinema Edition v1.2.9

## [English](#english) | [Francais](#francais)

---

<a name="english"></a>
## English

### Cinema Edition — 28 cinematic modules on top of ElegantFin v26.04.07

This release transforms the ElegantFin theme into a professional, Netflix-inspired streaming experience while keeping full compatibility with desktop, mobile, and TV platforms.

---

#### New in v1.2.0 — 8 Cinema Features

- **Skeleton loading** — Animated pulse placeholder while card images load, with subtle gradient shimmer. Disabled on TV and reduced-motion.
- **Hover preview info** — Secondary text (year, rating, genres) smoothly reveals on card hover with a cinematic bottom gradient overlay (desktop only)
- **Scroller edge fade** — Left/right gradient edges on horizontal scroll rows, indicating scrollable content. Uses `--backgroundForAppBar` for seamless blending.
- **Scroll-to-top glass** — Glass-effect button with `backdrop-filter: blur(15px)`, border glow, and hover lift animation
- **Resolution badges** — Color-coded media info badges: 4K (gold), HDR (green), Dolby Vision (purple), Atmos (cyan) with matching borders and subtle backgrounds
- **Now Playing bar glass** — Glassmorphism on the Now Playing bar with `blur(20px) saturate(1.4)`, dark border-top, and shadow. Disabled on TV.
- **Watched overlay** — Subtle dark overlay (`rgba(0,0,0,0.35)`) on already-watched cards, fading out on hover. Uses `:has(.playedIndicator)`.
- **Sidebar glass enhanced** — Sidebar with `blur(20px)`, styled nav items with rounded corners, hover highlights, selected state styling, and uppercase section headers

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
- **Reduced motion** — Full `prefers-reduced-motion: reduce` coverage: page transitions, shimmer, skeleton, login bounce, backdrop fade, card hover
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

#### v1.2.1 — Visual & Compatibility Fixes

- **Backdrop extended** — Mask extended from 45% to 65%, opacity raised from 0.55 to 0.65 — image visible further down the detail page (PC)
- **TV backdrop** — Reduced darkness from 0.95 to 0.6 — backdrop was nearly invisible on TV
- **upNext title** — Replaced `nowrap` with `line-clamp: 2` — long episode titles no longer truncated (all platforms)
- **OSD header TV** — Allows 2-line titles, reduced header height to 3.5em — fixes oversized black bar
- **OSD title mobile** — `line-clamp: 2` with wider max-width for long titles
- **Card hover** — Removed double zoom (1.06 x 1.04 = 1.10) — now single clean 1.06x pop

---

#### v1.2.2 — Editor's Choice Cinema

- **Editor's Choice Cinema** — Full cinematic styling for the Editor's Choice plugin: gradient overlay, glass buttons, zoom backdrop, smooth transitions
- **Full-width slides** — Splide carousel now shows one slide at a time (`min-width: 100%`) instead of cutting multiple slides
- **Cinema buttons** — Plugin buttons (`.button-submit`, `.emby-button.raised`) now styled with glass effect, white text, and hover lift matching the Cinema theme
- **TV disable** — All Editor's Choice blur, shadows, and animations disabled on TV layout

---

#### v1.2.3 — CSS Quality & Next Up Fix

- **Next Up dialog overflow** — Added `max-height` + `overflow-y: auto` so content scrolls instead of escaping the container
- **Next Up buttons always visible** — `flex-shrink: 0` prevents buttons from being pushed out of view
- **Next Up word-break** — Long titles now break cleanly with `word-break: break-word`
- **Next Up TV/Mobile** — TV: max 35em wide, 70vh tall with padding. Mobile: 90vw wide, 75vh tall
- **CSS audit fixes** — `justify-content: left/right` → `flex-start/flex-end` (invalid CSS), `rgb()` → `rgba()`, merged duplicate `html {}` blocks, added standard `line-clamp`, removed `calc(100% - 0em)`, fixed non-existent font, updated module count to 29

---

#### v1.2.4 — Next Up Dialog Polish

- **Wider container** — Added `min-width: 28em` so the dialog is never too narrow for long titles and buttons
- **3-line title** — `line-clamp` increased from 2 to 3 — long anime/episode titles now display fully
- **Buttons contained** — `width: 100%` on button row ensures they never overflow the container
- **No horizontal overflow** — `overflow-x: hidden` prevents content from escaping sideways
- **Mobile reset** — `min-width: unset` on mobile to avoid forcing a wide container on small screens

---

#### v1.2.5 — Next Up Title Wrap Fix

- **Root cause fixed** — Jellyfin default has `white-space: nowrap` + `width: 25.5em` + `text-overflow: ellipsis` on `.upNextDialog-title`, which forced single-line truncation. Overridden with `!important` to allow multi-line display
- **Title now wraps** — `white-space: normal`, `width: auto`, `text-overflow: unset` combined with `line-clamp: 3` — long anime titles display on up to 3 lines

---

#### v1.2.6 — Jellyfin Default CSS Overrides

- **upNext container width** — Jellyfin forces `width: 30em` fixed; overridden with `width: auto` so `min-width`/`max-width` work correctly
- **upNext buttons width** — Jellyfin forces `width: 29.75em` fixed; overridden with `width: 100%` to fill container
- **RTL support** — Added `[dir="rtl"] .upNextContainer` margin for right-to-left languages

---

#### v1.2.7 — Cleanup & CSS Quality

- **Removed Editor's Choice Cinema** — Plugin styling removed (28 modules)
- **Added standard `line-clamp`** — Missing on `.detail-clamp-text` (desktop/mobile/TV) and `.listItem-overview`
- **Fixed `justify-content: right`** — Last remaining invalid value on `.endTimeText` → `flex-end`
- **Removed permanent `will-change`** — Shimmer `::before` no longer declares `will-change: transform`
- **Fixed stale version comments** — Updated section comment references
- **Updated module count** — 29 → 28 across CSS, README, and RELEASE_NOTES

---

#### v1.2.8 — OSD Header Height Fix

- **OSD header reduced** — Video player header was using `--appBarHeight` (5em), now fixed to `3em` for all platforms — no more oversized black bar during playback

---

#### v1.2.9 — OSD Header Height Fix (stronger overrides)

- **OSD header forced to 2.75em** — Previous 3em rule was overridden by Jellyfin defaults. Now uses `!important` on both `.osdHeader` container and `.headerTop`
- **OSD buttons sized down** — Header buttons reduced to 2.5em to match the shorter bar
- **TV OSD at 3em** — Slightly taller on TV for remote visibility, still much smaller than default 5em

---

### Compatibility
- Jellyfin **10.11.x**
- Works on all web browsers (Chrome, Edge, Firefox, Safari), Android app, LG WebOS, Samsung Tizen
- Full `@supports` fallback for browsers without `backdrop-filter`

---

<a name="francais"></a>
## Francais

### Edition Cinema — 28 modules cinematiques par-dessus ElegantFin v26.04.07

Cette version transforme le theme ElegantFin en une experience de streaming professionnelle inspiree de Netflix, tout en gardant la compatibilite complete avec bureau, mobile et TV.

---

#### Nouveau dans v1.2.0 — 8 fonctionnalites Cinema

- **Skeleton loading** — Placeholder anime avec effet de pulsation pendant le chargement des images, avec degrade subtil. Desactive sur TV et mouvement reduit.
- **Info au survol** — Texte secondaire (annee, note, genres) apparait en douceur au survol des cartes avec un degrade cinematique (bureau uniquement)
- **Fondu bords scroller** — Degrades lateraux sur les rangees de defilement horizontal, indiquant le contenu defilable. Utilise `--backgroundForAppBar` pour une integration fluide.
- **Scroll-to-top verre** — Bouton avec `backdrop-filter: blur(15px)`, bordure lumineuse, et animation de levitation au survol
- **Badges resolution** — Badges media colores : 4K (dore), HDR (vert), Dolby Vision (violet), Atmos (cyan) avec bordures assorties et fonds subtils
- **Barre Now Playing verre** — Glassmorphism sur la barre de lecture en cours avec `blur(20px) saturate(1.4)`, bordure sombre et ombre. Desactive sur TV.
- **Overlay vu** — Overlay sombre subtil (`rgba(0,0,0,0.35)`) sur les cartes deja vues, s'estompant au survol. Utilise `:has(.playedIndicator)`.
- **Sidebar verre amelioree** — Sidebar avec `blur(20px)`, items de navigation avec coins arrondis, surbrillance au survol, etat selectionne stylise, et en-tetes de section en majuscules

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
- **Mouvement reduit** — Couverture complete `prefers-reduced-motion: reduce` : transitions, shimmer, skeleton, login bounce, backdrop, hover cartes
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

#### v1.2.1 — Corrections visuelles & compatibilite

- **Backdrop etendu** — Masque etendu de 45% a 65%, opacite augmentee de 0.55 a 0.65 — image visible plus bas sur la page detail (PC)
- **Backdrop TV** — Obscurite reduite de 0.95 a 0.6 — le backdrop etait quasi invisible sur TV
- **Titre upNext** — `nowrap` remplace par `line-clamp: 2` — les longs titres d'episodes ne sont plus tronques (toutes plateformes)
- **Header OSD TV** — Titres sur 2 lignes autorises, hauteur reduite a 3.5em — corrige la barre noire surdimensionnee
- **Titre OSD mobile** — `line-clamp: 2` avec largeur max elargie pour les longs titres
- **Hover cartes** — Double zoom supprime (1.06 x 1.04 = 1.10) — maintenant un seul pop propre a 1.06x

---

#### v1.2.2 — Editor's Choice Cinema

- **Editor's Choice Cinema** — Style cinematique complet pour le plugin Editor's Choice : degrade overlay, boutons en verre, zoom backdrop, transitions fluides
- **Slides pleine largeur** — Le carrousel Splide affiche maintenant un slide a la fois (`min-width: 100%`) au lieu de couper plusieurs slides
- **Boutons Cinema** — Les boutons du plugin (`.button-submit`, `.emby-button.raised`) sont maintenant styles avec effet verre, texte blanc et levitation au survol, en accord avec le theme Cinema
- **Desactivation TV** — Tous les blur, ombres et animations Editor's Choice desactives sur layout TV

---

#### v1.2.3 — Qualite CSS & Correctif Next Up

- **Debordement Next Up** — Ajout `max-height` + `overflow-y: auto` pour que le contenu defile au lieu de sortir du cadre
- **Boutons Next Up toujours visibles** — `flex-shrink: 0` empeche les boutons d'etre pousses hors de la vue
- **Retour a la ligne Next Up** — Les longs titres coupent proprement avec `word-break: break-word`
- **Next Up TV/Mobile** — TV : max 35em large, 70vh haut avec padding. Mobile : 90vw large, 75vh haut
- **Corrections audit CSS** — `justify-content: left/right` → `flex-start/flex-end` (CSS invalide), `rgb()` → `rgba()`, fusion des blocs `html {}` dupliques, ajout `line-clamp` standard, suppression `calc(100% - 0em)`, correction police inexistante, compteur modules mis a jour a 29

---

#### v1.2.4 — Finition dialogue Next Up

- **Conteneur plus large** — Ajout `min-width: 28em` pour que le dialogue ne soit jamais trop etroit pour les longs titres et boutons
- **Titre sur 3 lignes** — `line-clamp` augmente de 2 a 3 — les longs titres d'anime/episodes s'affichent completement
- **Boutons contenus** — `width: 100%` sur la rangee de boutons pour qu'ils ne debordent jamais du conteneur
- **Pas de debordement horizontal** — `overflow-x: hidden` empeche le contenu de sortir sur les cotes
- **Reset mobile** — `min-width: unset` sur mobile pour eviter de forcer un conteneur large sur petit ecran

---

#### v1.2.5 — Correctif retour a la ligne Next Up

- **Cause racine corrigee** — Le CSS par defaut de Jellyfin a `white-space: nowrap` + `width: 25.5em` + `text-overflow: ellipsis` sur `.upNextDialog-title`, forcant la troncature sur une seule ligne. Override avec `!important` pour permettre l'affichage multi-lignes
- **Le titre retourne a la ligne** — `white-space: normal`, `width: auto`, `text-overflow: unset` combines avec `line-clamp: 3` — les longs titres d'anime s'affichent sur jusqu'a 3 lignes

---

#### v1.2.6 — Surcharges CSS par defaut de Jellyfin

- **Largeur conteneur upNext** — Jellyfin force `width: 30em` fixe ; surcharge avec `width: auto` pour que `min-width`/`max-width` fonctionnent correctement
- **Largeur boutons upNext** — Jellyfin force `width: 29.75em` fixe ; surcharge avec `width: 100%` pour remplir le conteneur
- **Support RTL** — Ajout `[dir="rtl"] .upNextContainer` margin pour les langues de droite a gauche

---

#### v1.2.7 — Nettoyage & Qualite CSS

- **Retrait Editor's Choice Cinema** — Style du plugin retire (28 modules)
- **Ajout `line-clamp` standard** — Manquant sur `.detail-clamp-text` (bureau/mobile/TV) et `.listItem-overview`
- **Correction `justify-content: right`** — Derniere valeur invalide sur `.endTimeText` → `flex-end`
- **Retrait `will-change` permanent** — Shimmer `::before` ne declare plus `will-change: transform`
- **Correction commentaires obsoletes** — Mise a jour des references de version dans les commentaires
- **Compteur modules mis a jour** — 29 → 28 dans CSS, README et RELEASE_NOTES

---

#### v1.2.8 — Correction hauteur header OSD

- **Header OSD reduit** — Le header du lecteur video utilisait `--appBarHeight` (5em), maintenant fixe a `3em` sur toutes les plateformes — plus de barre noire surdimensionnee pendant la lecture

---

#### v1.2.9 — Correction hauteur header OSD (overrides renforces)

- **Header OSD force a 2.75em** — La regle 3em de v1.2.8 etait surchargee par les defauts Jellyfin. Utilise maintenant `!important` sur `.osdHeader` ET `.headerTop`
- **Boutons OSD reduits** — Boutons du header passes a 2.5em pour s'aligner avec la barre plus courte
- **TV OSD a 3em** — Legerement plus grand sur TV pour la visibilite telecommande, mais toujours bien plus petit que les 5em par defaut

---

### Compatibilite
- Jellyfin **10.11.x**
- Fonctionne sur tous les navigateurs web (Chrome, Edge, Firefox, Safari), application Android, LG WebOS, Samsung Tizen
- Fallback `@supports` complet pour les navigateurs sans `backdrop-filter`
