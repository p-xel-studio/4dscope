# Agents 4D-Scope

## Agent : Component Builder

Rôle : Créer un composant Astro à partir des données JSON et du design existant.

Instructions :
1. Lire le fichier `claude.md` pour le contexte global
2. Lire le fichier JSON correspondant dans `src/content/`
3. Créer le composant dans `src/components/` en suivant les conventions :
   - Composant Astro (pas de React/Vue)
   - Classes Tailwind uniquement (pas de CSS custom sauf GSAP)
   - Données importées depuis les JSON, jamais en dur
   - HTML sémantique avec aria-label sur la section
   - Classe `gs-reveal` sur les éléments à animer
4. Décommenter l'import et l'usage dans `src/pages/index.astro`
5. Tester visuellement avec `npm run dev`

Prompt type :
"Crée le composant [NomSection].astro en te basant sur les données de [fichier].json et le design de la version HTML actuelle (4dscope.html)."

---

## Agent : SEO Auditor

Rôle : Vérifier et améliorer le SEO technique du site.

Instructions :
1. Vérifier la présence et la qualité de :
   - title, meta description, canonical, OG tags, Twitter cards
   - Schema.org (Organization, Product, FAQPage)
   - Headings hierarchy (H1 unique, H2 par section, H3 dans les cartes)
   - Alt text sur toutes les images
   - Sitemap.xml généré par Astro
   - robots.txt
2. Vérifier la performance :
   - Pas de JS inutile (Astro islands only)
   - Fonts en display:swap
   - Images optimisées (WebP/AVIF via astro:assets)
   - CSS critique inline
3. Lancer `npm run build` et vérifier le output

---

## Agent : Content Editor

Rôle : Modifier le contenu textuel du site.

Instructions :
1. Tout le contenu est dans `src/content/*.json`
2. Ne jamais modifier les composants pour changer du texte
3. Respecter les règles de rédaction du `claude.md` :
   - Pas de tirets cadratins
   - Pas de "démo" dans les CTA
   - Pas de retours à la ligne forcés
   - Ton institutionnel, pas startup
4. Après modification, vérifier que le build passe : `npm run build`

---

## Agent : Animation Designer

Rôle : Créer et affiner les animations GSAP.

Instructions :
1. Les animations globales sont dans `src/layouts/Base.astro` (script client)
2. Utiliser GSAP + ScrollTrigger uniquement
3. Classe `.gs-reveal` pour les éléments scroll-triggered
4. Animations recommandées :
   - Hero : stagger fadeInUp sur badge, titre, sous-titre, CTA
   - Cartes : fadeInUp avec stagger 0.1s
   - Stats : countUp animation sur les chiffres
   - Nav : backdrop-blur on scroll
5. Garder les animations subtiles et performantes (will-change, transform only)
6. Tester sur mobile (réduire ou désactiver les animations complexes)

---

## Agent : Deployment

Rôle : Préparer et déployer le site sur Vercel.

Instructions :
1. Vérifier le build : `npm run build`
2. Vérifier le preview : `npm run preview`
3. S'assurer que `astro.config.mjs` a le bon `site:` URL
4. Vérifier `public/robots.txt` et que le sitemap est généré
5. Push sur GitHub, Vercel déploie automatiquement
6. Après déploiement, vérifier :
   - HTTPS actif
   - Redirections www → non-www (ou inverse)
   - OG image visible sur les réseaux sociaux
   - Schema.org validé sur search.google.com/test/rich-results
