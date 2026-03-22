# 4D-Scope — Site Vitrine Premium

## Identité du projet

**Marque** : 4D-Scope
**Produit** : Mira — Borne immersive VR libre-service
**Marché** : B2B institutionnel (musées, villes, sites culturels, tourisme)
**Territoire** : Belgique et France
**Langue du site** : Français
**Ton** : Luxury industriel, crédibilité institutionnelle, innovation culturelle
**Référence esthétique** : Apple × Tesla × installation muséale haut de gamme

## Stack technique

- **Framework** : Astro 5 (static-first, zero JS par défaut, islands architecture)
- **Styling** : Tailwind CSS 4
- **Animations** : GSAP + ScrollTrigger (premium scroll animations)
- **Fonts** : Playfair Display (titres) + DM Sans (corps)
- **Deploy** : Vercel (static, free tier)
- **Langue** : Site 100% en français, pas d'i18n pour l'instant

## Palette de couleurs

Le site utilise un fond sombre avec un accent vert-de-gris (patine de bronze).

```
--bg:          #0a0a0a
--bg-elevated: #101212
--bg-card:     #151717
--text:        #e0e4e3
--text-muted:  #828a88
--text-dim:    #515957
--accent:      #5aaa96    (vert-de-gris)
--accent-light:#74c4ae
--accent-dim:  #2e6e5e
--white:       #f4f6f5
```

## Règles de rédaction

- **Jamais** de tirets cadratins (—). Utiliser des points médians (·), des deux-points (:) ou reformuler.
- **Jamais** de retours à la ligne forcés dans les paragraphes. Le texte coule naturellement.
- **Pas de "démo"** dans les CTA. Utiliser "Discuter de votre projet", "Demander un devis", "Nous contacter".
- **Pas** de vocabulaire startup/SaaS. Pas de "scale", "disrupt", "game-changer".
- **Pas** de fausses métriques. Tous les chiffres doivent être réels et vérifiables.
- Les `&` ne sont utilisés que dans le code HTML. Dans le texte visible, écrire "et".
- Ton institutionnel mais chaleureux. Crédible, pas corporate froid.

## Structure du site

```
src/
  components/
    Nav.astro              — Navigation fixe avec effet scroll
    Hero.astro             — Section héro principale
    Trust.astro            — Barre de sites de référence
    Process.astro          — "Du lieu à l'immersion" (3 étapes)
    Features.astro         — 6 cartes spécifications techniques
    Offer.astro            — 2 formules (Borne seule / Expérience complète)
    UseCases.astro         — 5 cas d'usage
    Stats.astro            — Chiffres clés
    Differentiator.astro   — Section "Pourquoi 4D-Scope" + tableau comparatif
    Options.astro          — 6 accessoires/options
    Installations.astro    — Portfolio (3 installations)
    Faq.astro              — 6 questions fréquentes (schema.org FAQPage)
    Cta.astro              — Call to action final
    Footer.astro           — Pied de page
  layouts/
    Base.astro             — Layout HTML de base (head, meta, schema.org, fonts)
  pages/
    index.astro            — Page unique, assemble tous les composants
  styles/
    global.css             — Reset, variables CSS, utilitaires Tailwind
  content/
    site.json              — Données textuelles centralisées (titres, descriptions, FAQ)
    features.json          — Données des 6 spécifications
    options.json           — Données des 6 options/accessoires
    installations.json     — Données des 3 installations
  assets/                  — Images, vidéos, SVGs produit
public/
  favicon.svg
  og-image.jpg             — Image Open Graph (1200x630)
  robots.txt
  sitemap.xml
```

## Données produit (source de vérité)

### Spécifications Mira V3
- Rotation horizontale : 180° à 350°
- Inclinaison verticale : -45° à +45°
- Hauteur utilisateurs : 1,20 m à 1,90 m
- Poids : 25 kg
- Anti-vandalisme : acier inoxydable + aluminium + polyamide renforcé carbone
- Alimentation : autonome avec batterie de secours
- Casque VR : PICO G3 (Qualcomm XR2, 3664×1920, 98° FoV)
- Garantie structure : 5 ans (hors pièces d'usure)
- Maintenance incluse : 2 ans
- Fabrication : Belgique (hors composants électroniques)

### Installations actives
1. **Archéoforum de Liège** — 2 unités, 3+ ans de fonctionnement continu
2. **Grand Curtius** — Liège, intégration intérieure discrète
3. **Porte de Hal** — Bruxelles, installation originale (panorama 1550)
4. **Louvre Lens Vallée** — France, partenaire incubation

### Concurrent principal
- **Timescope** (timescope.com) — France
- Leur borne : 2 m, 190 kg, acier inox, 360°, 4K, 4G, écran tactile, monnayeur
- 150+ clients, 60 bornes installées
- Se positionnent "solution + impact", multi-dispositifs
- Nos avantages : plus léger (25 vs 190 kg), hauteur ajustable, encastrable, pas de lock-in contenu, pas de monnayeur, garantie 5 ans, fabrication belge

## SEO

### Mots-clés cibles
- borne immersive
- borne VR musée
- borne réalité virtuelle patrimoine
- dispositif immersif culturel
- longue-vue virtuelle
- borne panoramique 360
- expérience immersive musée
- borne libre-service VR
- borne touristique VR

### Schema.org
Le site doit inclure :
- `Organization` (4D-Scope)
- `Product` (Mira V3, avec specs)
- `FAQPage` (6 questions)

### Meta
- Canonical : https://4d-scope.com/
- OG locale : fr_BE
- Robots : index, follow

## Conventions de code

- Composants Astro en PascalCase
- Classes Tailwind, pas de CSS custom sauf animations GSAP
- Données dans `content/*.json`, pas en dur dans les composants
- Images optimisées via `astro:assets`
- Pas de JavaScript côté client sauf GSAP et le toggle nav mobile
- HTML sémantique : `<header>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Attributs `aria-label` sur les sections

## Performance

- Target : 100 Lighthouse sur les 4 métriques
- Pas de framework JS lourd (pas de React, Vue, etc.)
- Fonts en `display: swap`
- Images en WebP/AVIF
- CSS critique inline si possible
- Preload des fonts

## Commandes

```bash
npm run dev      # Serveur de développement (localhost:4321)
npm run build    # Build statique dans dist/
npm run preview  # Preview du build
```
