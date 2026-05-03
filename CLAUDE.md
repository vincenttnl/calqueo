# Projet Manéo — Instructions pour Claude Code

## Contexte
Manéo est une agence web pour artisans et commerçants, spécialisée plomberie/sanitaire en spearhead avec élargissement à toutes les TPE. Side project de Vincent.

## Référence marque obligatoire
Avant toute modification visuelle, copy, ou décision de design : **lire `brand-book-maneo.md` à la racine du projet**.

Ce document contient :
- La plateforme de marque (mission, vision, valeurs, tagline)
- L'identité visuelle complète (palette, typo, composants)
- La voix et le ton (mots oui/non, règles de copy)
- La direction iconographique
- Le système motion
- L'offre et les tarifs

## Règles non négociables

### Couleurs (toujours utiliser ces hex)
- Lin (fond) : `#F4F2EE`
- Lin clair (surfaces) : `#FAFAF7`
- Encre (texte) : `#0A0A0A`
- Encre claire (texte secondaire) : `#4A4A4A`
- Violet vif (accent) : `#5B3FFF`
- Violet profond (hover) : `#2D1F8C`
- Lin foncé (borders) : `#E8E3D5`

**Règle 60/30/10 stricte** : 60% Lin, 30% Encre, 10% Violet. Le violet est en signature, jamais dominant.

### Mode visuel
**Clear mode prioritaire.** Le lin domine, l'encre est en accent. Pas de blocs noirs lourds. Le dark mode sera traité en V2.

### Typographie
- Display : Inter Display 500 ou Boldonse
- Body : Inter 400 / 500
- Mono : JetBrains Mono (prix, données)
- Sentence case partout (sauf eyebrow labels en UPPERCASE letter-spacing 1px)
- Deux poids seulement : 400 et 500

### Composants signature
- CTA primaire : fond encre (#0A0A0A), texte lin, flèche violette `→`
- CTA secondaire : transparent, border 1px encre
- Cards : fond lin clair (#FAFAF7), border 0.5px lin foncé, radius 8-12px
- Eyebrow labels : violet 10% bg, violet texte, 11px UPPERCASE letter-spacing 1px

### Coins arrondis
- 4px pills/labels stricts
- 6px boutons et badges
- 8px cards
- 12px sections principales

### Voix & ton
- **Tutoiement systématique** en marketing
- **Phrases courtes** (12 mots max si possible)
- **Pas de "nous"** — Vincent parle, pas une agence anonyme
- **Pas de point d'exclamation** en marketing
- **Mots oui** : métier, outil, concret, livré, fait main, prix fixe, savoir-faire, atelier
- **Mots interdits** : solution, optimiser, synergie, ROI, funnel, scaler, stack, écosystème

## Stack technique préférée
À définir selon le projet (Next.js / Astro / Vite + React selon besoin). Privilégier les frameworks rapides à mettre en prod et faciles à maintenir solo.

## Chantiers à venir (note pour reprise)
1. Nom Manéo possiblement reconsidéré (pas validé à 100%)
2. Tester crédibilité cible artisan 50+ ans
3. Activer direction photo après 5 clients livrés
4. Finaliser kit prospection imprimable
5. Vérifier dispo .fr + INPI + handles
6. Variant dark mode plus tard

## Comportements attendus de Claude Code
- Toujours référencer le brand book avant de proposer du code visuel
- Ne pas inventer de couleurs en dehors de la palette
- Ne pas utiliser de jargon dans le copy (cf. mots interdits)
- Proposer du code propre, commenté légèrement, pas de surengineering
- Privilégier les solutions simples et maintenables (Vincent code seul)
