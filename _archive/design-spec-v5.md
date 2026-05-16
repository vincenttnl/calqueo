# Manéo — Design Spec V5 (Stripe-like)

> Brief visuel à coller en début de session pour tout asset Manéo (og-image, bannière, poster, slide, mockup). Reflète la direction visuelle réelle du site `maneo.fr` au 13 mai 2026, **pas** le `brand-book-maneo.md` qui décrit une autre direction (clear mode lin/encre) abandonnée.

---

## Identité

- **Nom** : Manéo
- **Tagline** : *Le digital fait main pour les artisans*
- **Positionnement** : agence web pour artisans et commerçants, spearhead plomberie. Prix fixe, livré en 15 jours, zéro jargon.
- **Inspiration visuelle** : Stripe (pas un calque, mais l'esprit : tech moderne, gradients colorés, navy sombre, typo nette, beaucoup d'espace).

---

## Palette

### Couleurs principales
| Rôle | Hex | Usage |
|---|---|---|
| Violet signature | `#635BFF` | CTAs, accents, links, focus, dots |
| Violet profond | `#2D1F8C` | Hover de certains accents (optionnel) |
| Navy / indigo | `#0A2540` | Texte principal, fond du footer, fond du loader |
| Navy 2 | `#1A1F36` | Variante très foncée |
| Blanc | `#FFFFFF` | Fond principal du site et des cards |

### Slate (gris bleutés Stripe)
| Var | Hex | Usage |
|---|---|---|
| slate-50 | `#FAFBFD` | Fonds très clairs, surfaces |
| slate-100 | `#F1F5F9` | Borders légères, fond hover |
| slate-200 | `#E2E8F0` | Borders cards |
| slate-300 | `#CBD5E1` | Lignes, séparateurs |
| slate-400 | `#94A3B8` | Placeholders, légendes |
| slate-500 | `#64748B` | Texte secondaire |
| slate-600 | `#475569` | Texte courant atténué |
| slate-700 | `#334155` | Texte de listes |
| slate-800 | `#1E293B` | Quasi-noir |
| slate-900 | `#0A2540` | = navy |

### Accents secondaires (gradients uniquement)
- Cyan vif : `#00D4FF`
- Rose : `#FF6B9D`
- Vert succès : `#059669` / `#10B981` (badges "disponible", check marks)

**À éviter** : couleurs hors palette (orange terne, jaune doré, marron, vert sapin, etc.).

---

## Gradients signature

```css
/* Texte / accents "fait main" / scroll progress bar */
linear-gradient(135deg, #00D4FF, #635BFF, #FF6B9D)

/* Sur les featured cards : version animée 5 stops */
linear-gradient(135deg, #00D4FF, #635BFF, #FF6B9D, #635BFF, #00D4FF)
```

Le gradient cyan→violet→rose est l'élément le plus reconnaissable. À utiliser **avec parcimonie** : 1 par écran max (titre hero, scroll progress, bordure d'une card mise en avant).

---

## Typographie

- **Display & body** : `Inter` (Google Fonts), poids 400 / 500 / 600 / 700 / 800
- **Mono / données chiffrées** : `JetBrains Mono`, poids 400 / 500 / 600

### Hiérarchie
- H1 : `clamp(40px, 5vw, 72px)`, weight 800, letter-spacing `-0.03em`, line-height 1.05
- H2 : `clamp(32px, 4vw, 48px)`, weight 800, letter-spacing `-0.02em`
- H3 : 24-32px, weight 700
- Body : 15-16px, weight 400, line-height 1.6
- Eyebrow : 13px, weight 600, UPPERCASE, letter-spacing 0.08em, couleur violet `#635BFF`
- Mono prix : `JetBrains Mono` 42px weight 700

### Style d'écriture
- **Tutoiement systématique** ("tu", "ton site")
- **Phrases courtes**, 12-15 mots max
- **Pas de "nous"** — c'est Vincent qui parle, pas une agence
- **Pas de jargon** : interdit → solution, optimiser, synergie, ROI, funnel, scaler, stack, écosystème
- **Mots oui** : métier, outil, concret, livré, fait main, prix fixe, savoir-faire, atelier

---

## Composants signature

### CTA primaire
```css
background: #635BFF;
color: #FFFFFF;
padding: 14px 28px;
border-radius: 8px;
font-weight: 600;
/* Texte avec flèche → intégrée */
/* Hover : translateY(-2px) + box-shadow violet 0.3 opacity */
```

### CTA secondaire (ghost)
```css
background: transparent;
color: #0A2540;
border: 1.5px solid #E2E8F0;
border-radius: 8px;
/* Hover : border-color: #635BFF */
```

### Card standard
```css
background: #FFFFFF;
border-radius: 16px;
border: 1px solid #E2E8F0;
box-shadow: 0 4px 20px rgba(10,37,64,0.08);
padding: 36px 28px;
```

### Card "featured" (mise en avant)
- Fond navy `#0A2540` + texte blanc
- Bordure gradient animée (cyan→violet→rose en boucle)
- Scale 1.03 pour la sortir des autres

### Eyebrow label
```css
font-size: 13px;
font-weight: 600;
text-transform: uppercase;
letter-spacing: 0.08em;
color: #635BFF;
```

### Phone mockup (hero)
- Largeur 300px, hauteur 600px, fond `#111`, radius 40px, padding 12px
- Notch noir en haut
- Floating badges flottants autour avec dot coloré

### Ombres (échelle Stripe)
```css
--shadow-sm: 0 2px 8px rgba(10,37,64,0.06);
--shadow-md: 0 4px 20px rgba(10,37,64,0.08);
--shadow-lg: 0 8px 40px rgba(10,37,64,0.12);
--shadow-xl: 0 16px 60px rgba(10,37,64,0.16);
```

---

## Radius

- Boutons : **8px**
- Cards : **16px**
- Badges / pills arrondis : 20-30px (forme stade)
- Inputs : 8px

---

## Effets & motion

- **Easing par défaut** : `cubic-bezier(0.16, 1, 0.3, 1)` (out-expo)
- **Durée par défaut** : 200ms (hovers), 400ms (reveals)
- **Hero blobs** : 3 cercles flous (500/400/300px) en background, opacity 0.6, animation `blobFloat 20s ease-in-out infinite` (translation + scale légères)
- **Particles canvas** : ~40 points violets `rgba(99,91,255,0.15)` reliés par lignes quand distance < 120px
- **Scroll progress bar** : 2px de haut, gradient cyan→violet→rose, animé selon scroll
- **Reveal sections** : translateY(20px) + opacity 0 → 1 via IntersectionObserver

---

## Anti-patterns (à ne pas faire)

- ❌ Palette lin/écru/beige (`#F4F2EE`, `#FAFAF7`) — c'est l'autre direction du brand book papier, abandonnée
- ❌ Violet vif `#5B3FFF` — proche mais pas le bon, utiliser `#635BFF`
- ❌ Aplats noirs purs (`#000`) — toujours préférer navy `#0A2540`
- ❌ Plus d'un gradient par composition
- ❌ Mélanger les emojis pleins (🔧) avec des icônes line — choisir un style
- ❌ Vouvoiement, points d'exclamation excessifs dans le marketing
- ❌ "Solution", "optimiser", "synergie" et autre jargon agence

---

## Cas d'usage prêts à briefer

### og-image (1200×630)
- Fond navy `#0A2540`
- Titre "Le digital fait main" en blanc, weight 800, accent "fait main" en gradient cyan→violet→rose
- Sous-titre "Sites et applis pour artisans · à partir de 990€"
- Logo Manéo en bas à gauche
- Petit blob violet flou en haut à droite

### Bannière LinkedIn / réseaux
- Format paysage, palette identique, focus sur tagline
- Photo de Vincent ou phone mockup à droite

### Slide pitch
- Fond blanc, eyebrow violet UPPERCASE, H2 weight 800 navy
- 1 visual : phone mockup, card, ou stat en JetBrains Mono

---

## Liens utiles

- Site live : `~/Desktop/CLAUDE SESSION/MANEO/index.html`
- Brand book papier (voix/ton seulement, **pas couleurs**) : `brand-book-maneo.md`
- Stratégie prix : `strategie-prix-maneo.md`
- Feuille de route : `feuille-de-route-maneo.md`
