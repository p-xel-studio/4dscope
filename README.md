# 4D-Scope · Site Vitrine

Site vitrine premium pour 4D-Scope, fabricant belge de bornes immersives VR pour musées, villes et sites culturels.

## Stack

- **Astro 5** · Static-first, zero JS par défaut
- **Tailwind CSS 4** · Utility-first styling
- **GSAP + ScrollTrigger** · Animations premium au scroll
- **Vercel** · Déploiement statique

## Démarrage rapide

```bash
npm install
npm run dev        # http://localhost:4321
```

## Build et déploiement

```bash
npm run build      # Génère le site statique dans dist/
npm run preview    # Preview local du build
```

Le déploiement sur Vercel est automatique au push sur la branche `main`.

## Structure

```
src/
  components/      14 composants Astro (Nav, Hero, Trust, etc.)
  layouts/         Layout de base (head, meta, schema.org, GSAP)
  pages/           index.astro (page unique)
  styles/          global.css (Tailwind + variables)
  content/         Données JSON centralisées
  assets/          Images et SVGs
public/            Favicon, robots.txt, OG image
claude.md          Instructions pour Claude Code
agents/            Agents spécialisés
```

## Contenu

Tout le texte est dans `src/content/*.json`. Ne jamais modifier les composants pour changer du texte.

## Claude Code

Ce projet est configuré pour fonctionner avec Claude Code. Le fichier `claude.md` contient toutes les instructions, la palette, les conventions et les données produit.
