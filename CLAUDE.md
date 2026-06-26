# Projet Calquéo — Instructions pour Claude Code

## Contexte
Calquéo est un studio web indépendant pour les pros qui veulent un site à la hauteur de leur métier. Side project de Vincent.

Sur le site, **c'est Vincent qui parle** (auteur en nom propre, plus de persona Giovanni). Décision actée 2026-05-19 : bascule Giovanni → Vincent sur tout le site et les docs internes.

✅ Nom validé : **Calquéo** (2026-05-16). Domaines `calqueo.fr` + `calqueo.com` enregistrés chez OVH. L'ancien nom Manéo est définitivement abandonné (maneo.fr détenu par BPCE, MANÉO Opticiens occupe maneo.com). Voir `rebranding-noms.md` et `rebranding-shortlist.md` pour l'historique du brainstorm.

## Source de vérité unique
**Avant toute modif visuelle, copy, ou décision de design : lire `brand-book.md`** (V2 mai 2026).

Ce doc unique contient :
- Plateforme de marque (mission, vision, valeurs, taglines)
- Identité visuelle V5 Stripe-like complète
- Voix et ton (mots oui/non, règles copy)
- Direction iconographique
- Système motion
- Offre + pricing officiel
- Kit prospection
- Pitch 30 secondes (versions Karim + Camille)

## Personas (2 en parallèle)
- **Karim · spearhead marque** — artisans/commerçants TPE en IDF (page d'accueil `calqueo.fr`)
- **Camille · priorité commerciale** — libérales premium (psy, coach, naturo, photographe, déco, wedding planner) qui facturent +80€/séance (page de vente `signature.html`)
- *Olivier (B2B) réservé phase 3*

## Règles non négociables

### Palette V5 Stripe-like (officielle)
- **Violet signature** : `#635BFF` (CTAs, accents, links, point)
- **Violet profond** : `#2D1F8C` (hover optionnel)
- **Navy** : `#0A2540` (texte principal, footer, sections fortes)
- **Navy 2** : `#1A1F36` (variante très foncée)
- **Blanc** : `#FFFFFF` (fond principal)
- **Slate** : `#FAFBFD` → `#334155` (gradations gris bleutés Stripe)

⚠️ **Palette V1 lin/encre (`#F4F2EE` / `#5B3FFF`) ABANDONNÉE.** Ne jamais réintroduire.
⚠️ Violet `#5B3FFF` proche mais incorrect → utiliser **`#635BFF`**.

### Gradient signature (1 par écran max)
```css
linear-gradient(135deg, #00D4FF, #635BFF, #FF6B9D)
```

### Typographie
- Display & body : Inter (400 / 500 / 600 / 700 / 800)
- Mono / prix : JetBrains Mono
- H1 : `clamp(40px, 5vw, 72px)` weight 800
- Eyebrow : 13px UPPERCASE letter-spacing 0.08em couleur violet

### Composants signature
- CTA primaire : fond `#635BFF`, texte blanc, radius 8px, flèche `→` intégrée
- CTA secondaire : transparent, border 1.5px slate-200, hover → border violet
- Card : fond blanc, radius 16px, border 1px slate-200, shadow-md
- Card featured : bord violet 2px, badge "LE PLUS CHOISI"
- Logo : wordmark `calquéo.` (point violet `#635BFF`), Inter 800 lowercase

### Voix & ton
- **Tutoiement systématique** en marketing
- **Phrases courtes** (12-15 mots max)
- **Pas de "nous"** — Vincent parle, pas une agence anonyme
- **Pas de point d'exclamation** en marketing
- **Mots oui (universels)** : métier, outil, concret, livré, prix fixe, savoir-faire, compagnonnage, à l'écoute
- **Mots oui (Karim)** : chantier, fait main, atelier, terrain, à l'ancienne
- **Mots oui (Camille)** : image, sur-mesure, signature, joignable, maison, comprendre, univers, durée
- **Mots interdits** : solution, optimiser, synergie, ROI, funnel, scaler, stack, écosystème, transformation digitale

## Pricing officiel (validé 2026-05-14)

### Sites (one-shot)
| Pack | Prix | Délai | Cible |
|---|---|---|---|
| Démarrage | **990€** | 7 jours | Karim / indé qui démarre |
| Signature ⭐ | **2 490€** | 3 semaines | Camille (cœur) |
| Premium | **3 990€** | 5 semaines | Camille établie / petite TPE |
| Sur-mesure | dès **5 900€** | 6-10 sem | B2B / projets spécifiques |

### Récurrent
| Pack | Prix/mois | Cible |
|---|---|---|
| Veille | **49€** | Karim ou prudent |
| Atelier ⭐ | **99€** | Camille (cœur) |
| Croissance | **199€** | Camille+ / B2B |

3 premiers mois offerts. Sans engagement.
**Plein tarif dès la 2e cliente.** Mélina (Waly) reste à 1 690€ tarif lancement acquis (seule exception).

### Apps métier
Outil simple dès 4 900€ · Outil métier dès 9 900€ · Outil complet dès 19 900€

## Règles business
- ❌ **Pas de "satisfait ou remboursé"** (abandonné v2). Filet : appel découverte amont + 90€/h en sortie de scope.
- ❌ Pas d'engagement caché type Simplébo / Solocal
- ❌ Pas d'e-commerce 50k produits
- ❌ Jamais "templates Wix avec ton logo"
- ❌ Jamais promettre formation / autonomie au client

## Stack technique
- Sites : HTML/CSS/JS statique → Netlify
- Apps : Next.js + Supabase + Stripe + Resend + Vercel (PWA, pas natif)

## Fichiers du projet

```
CALQUEO/
├── index.html             ← site V5 (homepage Karim) ⚠️ SEUL HTML servi à la racine
├── og-image.png / robots.txt / sitemap.xml / netlify.toml
├── brand-book.md          ← source de vérité unique (bloqué 404 en ligne)
├── CLAUDE.md              ← ce doc
├── rebranding-noms.md / rebranding-shortlist.md  ← historique noms (bloqués 404)
├── legal/                 ← pages légales regroupées (rangement 2026-06-26)
│   ├── cgv.html / mentions-legales.html / politique-confidentialite.html
│   └── _legal-shared.css   (anciennes URLs /cgv.html etc. → redirigées 301 dans netlify.toml)
├── assets/                ← images + vidéo du site (servis)
├── _etudes/               ← vault Obsidian (études INTERNES, ex-dossier "maneo", gitignoré, ne pas modifier)
│   ├── etude-100-profils-INTERNE.md
│   ├── etude-apps-positionnement-INTERNE.md
│   ├── etude-marche-INTERNE.md
│   ├── etude-pricing-INTERNE v2.md
│   └── copy-page-camille-V1.md
├── _explorations/         ← maquettes/brouillons HTML (gitignoré) : hero, prisma, anims, navbar, audits
├── _logos/                ← tous les logos (officiel = _logos/logo v3/PACK OFFICIEL/, gitignoré)
└── _archive/              ← anciennes versions (ne pas exhumer sans raison)
```

## Comportements attendus de Claude Code
- Toujours référencer `brand-book.md` avant de proposer du code visuel
- Ne pas inventer de couleurs hors palette V5
- Ne pas utiliser de jargon dans le copy (cf. mots interdits)
- Vincent code seul → solutions simples et maintenables, pas de surengineering
- Avant tout deploy : pointer DNS `calqueo.fr` → Netlify dans le Manager OVH
- Le repo est PUBLIC → ne jamais commiter d'infos commerciales clients (tarifs nominatifs, devis, fiches)
