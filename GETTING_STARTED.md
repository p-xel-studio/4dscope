# Démarrage rapide

## Prérequis

- **Node.js 18+** (recommandé : 20 LTS)
- **npm** (inclus avec Node.js)
- **VS Code** avec les extensions recommandées (voir `.vscode/extensions.json`)
- **Claude Code** (optionnel mais recommandé)

## Installation

```bash
# 1. Cloner ou décompresser le projet
cd 4dscope-site

# 2. Installer les dépendances
npm install

# 3. Lancer le serveur de développement
npm run dev
```

Le site est accessible sur `http://localhost:4321`.

## Avec Claude Code

```bash
# Depuis le dossier du projet
claude

# Claude Code lira automatiquement claude.md et connaîtra :
# - La palette de couleurs
# - Les conventions de rédaction
# - Les données produit
# - La structure des fichiers
# - Les agents disponibles
```

### Exemples de prompts Claude Code

```
"Crée le composant Hero.astro en te basant sur les données de site.json"
"Ajoute une animation GSAP de stagger sur les cartes features"
"Modifie le texte du CTA principal dans site.json"
"Vérifie le SEO du site et propose des améliorations"
"Optimise les images dans src/assets pour le web"
```

## Déploiement Vercel

```bash
# 1. Créer un repo GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin git@github.com:VOTRE-COMPTE/4dscope-site.git
git push -u origin main

# 2. Connecter à Vercel
# - Aller sur vercel.com
# - "Import Project" > sélectionner le repo GitHub
# - Framework : Astro (détecté automatiquement)
# - Deploy
```

## Structure des fichiers à connaître

| Fichier | Rôle |
|---------|------|
| `claude.md` | Cerveau du projet pour Claude Code |
| `src/content/*.json` | Tout le texte du site (ne jamais écrire en dur dans les composants) |
| `src/components/*.astro` | Un composant par section |
| `src/layouts/Base.astro` | Head HTML, meta SEO, Schema.org, GSAP |
| `src/styles/global.css` | Variables Tailwind et reset |
| `agents/AGENTS.md` | Agents spécialisés pour Claude Code |

## Modifier du contenu

Tout le texte est dans `src/content/`. Exemples :

- Changer un titre : éditer `site.json` > `hero.title`
- Ajouter une FAQ : ajouter un objet dans `site.json` > `faq[]`
- Modifier une installation : éditer `installations.json`
- Ajouter une option/accessoire : ajouter un objet dans `options.json`

Après modification, le serveur de dev recharge automatiquement.

## Ajouter des images

1. Placer les images dans `src/assets/`
2. Les importer dans le composant avec `import img from '@/assets/photo.webp'`
3. Astro les optimise automatiquement (WebP, resize, lazy loading)

Format recommandé : WebP, max 1920px de large, qualité 80.

## Checklist avant mise en ligne

- [ ] Remplacer les placeholder visuels par les vraies photos
- [ ] Vérifier tous les textes dans `src/content/`
- [ ] Tester sur mobile
- [ ] Configurer l'email dans `site.json` > `cta.email`
- [ ] Ajouter l'image OG dans `public/og-image.jpg` (1200x630)
- [ ] Vérifier le Schema.org : https://search.google.com/test/rich-results
- [ ] Lancer `npm run build` sans erreurs
- [ ] Tester avec Lighthouse (cible : 100/100/100/100)
