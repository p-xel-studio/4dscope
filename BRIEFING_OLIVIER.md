# 4D-Scope · Briefing technique du site

## Comment le site est construit

Le site 4d-scope.com est un **site statique** : il n'y a pas de serveur, pas de base de données, pas de CMS. Les pages sont générées une seule fois au moment du déploiement, puis servies directement comme de simples fichiers HTML. C'est la technologie la plus rapide et la plus sûre qui existe pour un site vitrine.

### Stack technique

| Composant | Technologie | Pourquoi |
|-----------|------------|----------|
| Framework | **Astro 5** | Génère du HTML pur, zéro JavaScript inutile envoyé au visiteur |
| Mise en page | **Tailwind CSS 4** | Styles modernes, responsive, légers |
| Animations | **GSAP** | Animations premium au scroll (apparitions, flottements) |
| Hébergement | **Vercel** (gratuit) | CDN mondial, HTTPS automatique, déploiement en 30 secondes |
| Code source | **GitHub** | Versionné, sauvegardé, historique complet des modifications |

### Comment ça fonctionne

1. Le contenu (textes, specs, FAQ) est centralisé dans des fichiers JSON faciles à modifier
2. Les composants visuels (Hero, Specs, FAQ, etc.) lisent ces fichiers et génèrent le HTML
3. À chaque modification pushée sur GitHub, Vercel reconstruit et déploie automatiquement en ~30 secondes
4. Le site est servi depuis le CDN Vercel le plus proche du visiteur (Bruxelles, Paris, etc.)

## Avantages concrets

### Performance
- **Temps de chargement < 2 secondes** sur une connexion standard
- Aucun serveur à maintenir, aucune base de données, aucun risque de crash
- Le site reste en ligne même avec des milliers de visiteurs simultanés (CDN distribué)
- Score Lighthouse élevé (Google valorise les sites rapides dans le référencement)

### Sécurité
- Pas de CMS type WordPress = pas de failles de sécurité, pas de mises à jour urgentes
- Pas de base de données = rien à pirater
- HTTPS activé automatiquement
- Aucun cookie de tracking, conforme RGPD sans bandeau cookie

### Coût
- Hébergement **gratuit** sur Vercel (le plan gratuit couvre largement nos besoins)
- Domaine `4d-scope.com` : seul coût récurrent (~12 EUR/an)
- Pas de licence CMS, pas d'abonnement mensuel

### SEO (référencement Google)
- Balisage Schema.org intégré (Organisation, Produit, FAQ) pour les résultats enrichis Google
- Sitemap XML généré automatiquement
- Meta tags, Open Graph, Twitter Cards en place
- Structure HTML sémantique (un seul H1, hiérarchie H2/H3 propre)
- FAQ balisée pour apparaître directement dans les résultats Google

### Maintenabilité
- Modifier un texte = changer une ligne dans un fichier JSON
- Ajouter une installation = ajouter une entrée dans `installations.json`
- Tout l'historique des modifications est conservé sur GitHub

## Pages du site

| Page | URL | Contenu |
|------|-----|---------|
| Accueil | `/` | Hero, logos partenaires, processus, specs, offre, cas d'usage, stats, différenciateurs, options, installations, témoignages, FAQ, formulaire de contact |
| Fiche technique | `/fiche-technique` | Toutes les specs Mira V3, imprimable en PDF depuis le navigateur |
| Mentions légales | `/mentions-legales` | Infos légales (à compléter avec BCE, TVA, adresse) |
| Confidentialité | `/confidentialite` | Politique RGPD |

## Ce qu'il reste à faire

### Urgent (avant démarchage)

- [ ] **Connecter le formulaire de contact** à un service d'envoi (pour recevoir les demandes par email)
- [ ] **Compléter les mentions légales** : nom de l'entreprise, forme juridique, adresse, n° BCE/KBO, n° TVA
- [ ] **Image de partage LinkedIn** : créer un visuel 1200x630 pour que les partages du site aient un bel aperçu
- [ ] **Connecter le domaine** `4d-scope.com` à Vercel

### Quand disponible

- [ ] **Témoignages clients** : citations de l'Archéoforum, du Curtius ou de la Ville de Liège (la section est prête, il suffit de remplacer les placeholders)
- [ ] **Métriques d'impact** : nombre de visiteurs ayant utilisé les bornes, satisfaction, fréquentation (les élus ont besoin de chiffres pour justifier la dépense)
- [ ] **Numéro de téléphone** : à ajouter sur le site pour les contacts institutionnels qui préfèrent appeler
- [ ] **Photos supplémentaires** des installations (Archéoforum, Curtius, Porte de Hal)

### Pour plus tard

- [ ] Page dédiée "Villes et Communes" avec argumentaire spécifique (subsides, marchés publics, cas concrets)
- [ ] Études de cas détaillées par installation
- [ ] Blog/actualités pour le référencement longue traîne
- [ ] Fiche technique en PDF généré (actuellement c'est une page web imprimable)
