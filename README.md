<!-- Image banniere -->
<img src="https://github.com/lscambo13/ElegantFin/blob/main/Theme/assets/img/banner.png?raw=true" alt="ElegantFin Cinema Edition - Banner">

<div align="center">

# ElegantFin Cinema Edition

**A cinematic fork of [ElegantFin](https://github.com/lscambo13/ElegantFin) — Netflix-inspired Jellyfin theme**

[![Version](https://img.shields.io/badge/Cinema%20Edition-v1.1.0-red?style=flat&logo=github)](https://github.com/peterdu1109/ElegantFin/releases)
[![Based on](https://img.shields.io/badge/Based%20on-ElegantFin%20v26.04.07-blue?style=flat&logo=github)](https://github.com/lscambo13/ElegantFin)
[![Jellyfin](https://img.shields.io/badge/Jellyfin-10.11.x-00A4DC?style=flat&logo=jellyfin&logoColor=white)](https://jellyfin.org)
[![Platform](https://img.shields.io/badge/Platform-Desktop%20%7C%20Mobile%20%7C%20TV-green?style=flat)]()

</div>

---

## [English](#english) | [Francais](#francais)

---

<a name="english"></a>

## English

### What is this?

This is a **Cinema Edition** of the ElegantFin theme by [lscambo13](https://github.com/lscambo13), enhanced with **20 cinematic modules** that transform your Jellyfin into a professional streaming experience inspired by Netflix, Disney+ and Apple TV+.

Everything works on **desktop, mobile and TV** with a single CSS import.

---

### What's new compared to the original?

| Module | Description |
|--------|-------------|
| **Glassmorphism Login** | Frosted glass login card with smooth entrance animation |
| **Page Transitions** | Fade-in and slide-up animations on every page load |
| **Cascade Sections** | Staggered delays for a Netflix-style reveal effect |
| **Shimmer Effect** | Subtle light sweep on the first row of cards (desktop) |
| **Cinema Backdrop** | Deeper transparent header gradient, softer backdrop |
| **Netflix Cards** | Pop zoom (1.06x), glowing borders, text highlight on hover |
| **White Progress Bars** | Clean white progress bars replacing colored ones |
| **Premium Badges** | Blurred glass indicators for count, resolution, watched |
| **Cinema Detail Page** | Ultra-light titles (weight 100), italic tagline, white Play button |
| **Modern OSD Player** | Soft gradient, reactive slider, glass footer |
| **Section Titles** | Bolder (700), hidden chevrons, overflow ellipsis |
| **Glass Dialogs** | Backdrop blur on dialogs, menus, drawer, toast, upNext |
| **Navigation Tabs** | White active tab, subtle inactive with hover effect |
| **Typography Hierarchy** | Refined weights for body text, episode titles, subtitles |
| **Long Titles Fix** | Responsive line-clamp (2 desktop, 3 mobile), word-break |
| **Thin Scrollbars** | 4px cross-browser scrollbars, transparent track |
| **OSD Header Glass** | Blurred dark header during video playback |
| **Alpha Picker** | Smooth transition on library A-Z picker |
| **TV Optimizations** | No blur, no shadows, no animations for low-end TVs |
| **Mobile Optimizations** | Reduced blur intensity for better performance |

---

### Installation

**Paste the following in your Custom CSS field:**

```
@import url("https://cdn.jsdelivr.net/gh/peterdu1109/ElegantFin@main/Theme/ElegantFin-jellyfin-theme-build-latest-minified.css");
```

<details>
<summary><b>Server-side installation</b></summary>

1. Open the **Dashboard** from the Administration tab in Settings
2. In the sidebar, select **Branding** (Jellyfin 10.11.x) or **General** (older versions)
3. Scroll down to the **Custom CSS** field
4. Paste the CSS import above
5. Click **Save**
</details>

<details>
<summary><b>Client-side installation</b></summary>

1. Open the **Display** tab in Settings
2. Scroll down to the **Custom CSS** field
3. Paste the CSS import above
4. Click **Save**
</details>

---

### Customization

All original ElegantFin customization options are preserved. Add these overrides **after** the import line:

<details>
<summary><b>Available options</b></summary>

| Option | Variable | Values |
|--------|----------|--------|
| Login background | `--loginPageBgUrl` | `url("your-server/Branding/Splashscreen...")` |
| Play button position | `--overlayPlayButtonPosition` | `50%` (center) / `-999em` (hidden) |
| Card hover effect | `--cardHoverEffect` | `""` (enabled) / `none` (disabled) |
| Library labels | `--libraryLabelVisibility` | `block` / `none` |
| Extra card buttons | `--extraCardButtonsVisibility` | `block` / `none` |
| App bar style | `--appBarHeight` | `5em` (fading) / `4.6em` (solid) |
| Original title | `--itemOriginalTitleVisibility` | `block` / `none` |
| Clear logo | `--clearLogoVisibility` | `block` / `none` |
| Icon pack (LG TV fix) | `--iconPack` | `'Material Icons'` (old) |
| Color themes | See [Playground](https://github.com/lscambo13/ElegantFin/discussions/221) | Various |

</details>

---

### Compatibility

| Platform | Status |
|----------|--------|
| Jellyfin Server 10.11.x | Fully supported |
| Web browsers (Chrome, Edge, Firefox, Safari) | Fully supported |
| Jellyfin Android App | Fully supported |
| LG WebOS | Supported (may need icon pack fix) |
| Android TV native app | Not supported (no CSS support) |
| Jellyfin Media Player (Qt 5.x) | Partial (outdated web engine) |

---

### Accessibility

- `prefers-reduced-motion` is respected: all animations are disabled when the user has this preference enabled
- TV layouts disable all blur, shadows and animations for performance
- Mobile layouts use reduced blur intensity

---

### Credits

- **Original theme:** [ElegantFin](https://github.com/lscambo13/ElegantFin) by [lscambo13](https://github.com/lscambo13)
- **Cinema Edition:** Enhanced by [peterdu1109](https://github.com/peterdu1109)

---

<a name="francais"></a>

## Francais

### C'est quoi ?

C'est une **Edition Cinema** du theme ElegantFin par [lscambo13](https://github.com/lscambo13), enrichie de **20 modules cinematiques** qui transforment votre Jellyfin en une experience de streaming professionnelle inspiree de Netflix, Disney+ et Apple TV+.

Tout fonctionne sur **bureau, mobile et TV** avec un seul import CSS.

---

### Quoi de neuf par rapport a l'original ?

| Module | Description |
|--------|-------------|
| **Login Glassmorphism** | Carte de connexion en verre depoli avec animation d'entree |
| **Transitions de pages** | Animations fade-in et slide-up a chaque chargement |
| **Sections en cascade** | Delais decales pour un effet de revelation style Netflix |
| **Effet Shimmer** | Balayage lumineux sur la premiere rangee de cartes (bureau) |
| **Backdrop Cinema** | Degrade transparent profond, arriere-plan plus doux |
| **Cartes Netflix** | Zoom pop (1.06x), bordures lumineuses, texte surbrillance |
| **Barres de progression blanches** | Barres blanches epurees remplacant les barres colorees |
| **Badges Premium** | Indicateurs en verre flou pour compteur, resolution, vu |
| **Page de details Cinema** | Titres ultra-legers (poids 100), tagline italique, bouton Play blanc |
| **Lecteur OSD moderne** | Degrade doux, slider reactif, pied de page en verre |
| **Titres de sections** | Plus gras (700), chevrons masques, overflow ellipsis |
| **Dialogues en verre** | Backdrop blur sur dialogues, menus, drawer, toast, upNext |
| **Onglets de navigation** | Onglet actif blanc, inactifs subtils avec effet hover |
| **Hierarchie typographique** | Poids affines pour texte, titres d'episodes, sous-titres |
| **Fix longs titres** | Line-clamp responsive (2 bureau, 3 mobile), word-break |
| **Scrollbars fines** | Scrollbars 4px cross-browser, piste transparente |
| **Header OSD en verre** | En-tete sombre floute pendant la lecture video |
| **Alpha Picker** | Transition fluide sur le selecteur A-Z des bibliotheques |
| **Optimisations TV** | Pas de blur, pas d'ombres, pas d'animations pour les TV |
| **Optimisations Mobile** | Intensite de blur reduite pour de meilleures performances |

---

### Installation

**Collez le code suivant dans le champ CSS personnalise :**

```
@import url("https://cdn.jsdelivr.net/gh/peterdu1109/ElegantFin@main/Theme/ElegantFin-jellyfin-theme-build-latest-minified.css");
```

<details>
<summary><b>Installation cote serveur</b></summary>

1. Ouvrez le **Tableau de bord** depuis l'onglet Administration dans les Parametres
2. Dans la barre laterale, selectionnez **Marque** (Jellyfin 10.11.x) ou **General** (versions plus anciennes)
3. Descendez jusqu'au champ **CSS personnalise**
4. Collez l'import CSS ci-dessus
5. Cliquez sur **Enregistrer**
</details>

<details>
<summary><b>Installation cote client</b></summary>

1. Ouvrez l'onglet **Affichage** dans les Parametres
2. Descendez jusqu'au champ **CSS personnalise**
3. Collez l'import CSS ci-dessus
4. Cliquez sur **Enregistrer**
</details>

---

### Personnalisation

Toutes les options de personnalisation originales d'ElegantFin sont preservees. Ajoutez ces surcharges **apres** la ligne d'import :

<details>
<summary><b>Options disponibles</b></summary>

| Option | Variable | Valeurs |
|--------|----------|---------|
| Fond de connexion | `--loginPageBgUrl` | `url("votre-serveur/Branding/Splashscreen...")` |
| Position bouton lecture | `--overlayPlayButtonPosition` | `50%` (centre) / `-999em` (cache) |
| Effet hover cartes | `--cardHoverEffect` | `""` (active) / `none` (desactive) |
| Labels bibliotheques | `--libraryLabelVisibility` | `block` / `none` |
| Boutons suppl. cartes | `--extraCardButtonsVisibility` | `block` / `none` |
| Style barre d'app | `--appBarHeight` | `5em` (fondu) / `4.6em` (solide) |
| Titre original | `--itemOriginalTitleVisibility` | `block` / `none` |
| Logo clair | `--clearLogoVisibility` | `block` / `none` |
| Pack icones (fix LG TV) | `--iconPack` | `'Material Icons'` (anciens) |
| Themes de couleurs | Voir [Playground](https://github.com/lscambo13/ElegantFin/discussions/221) | Divers |

</details>

---

### Compatibilite

| Plateforme | Statut |
|------------|--------|
| Jellyfin Server 10.11.x | Entierement supporte |
| Navigateurs web (Chrome, Edge, Firefox, Safari) | Entierement supporte |
| Jellyfin Android App | Entierement supporte |
| LG WebOS | Supporte (peut necessiter le fix icones) |
| Android TV app native | Non supporte (pas de support CSS) |
| Jellyfin Media Player (Qt 5.x) | Partiel (moteur web obsolete) |

---

### Accessibilite

- `prefers-reduced-motion` est respecte : toutes les animations sont desactivees si l'utilisateur a cette preference
- Les layouts TV desactivent tous les blur, ombres et animations pour la performance
- Les layouts Mobile utilisent une intensite de blur reduite

---

### Credits

- **Theme original :** [ElegantFin](https://github.com/lscambo13/ElegantFin) par [lscambo13](https://github.com/lscambo13)
- **Edition Cinema :** Ameliore par [peterdu1109](https://github.com/peterdu1109)
