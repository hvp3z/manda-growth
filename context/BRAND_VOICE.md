---
type: dérivé
sources: content-factory/brand/BRAND_RULES.md + corrections v1.1 (REPORT.md mineral-v1, ADR-078/082) · positioning-intel.md
sync: 2026-07-28
règle: ne modifier que via playbooks/resync-context.md
note: BRAND_RULES.md master corrigé le 2026-07-28 (bundle 49 € retiré, Sheets retiré, relances → Eli)
---

# BRAND_VOICE — Comment Manda parle

## Positionnement en une ligne

**Manda = un Store d'assistants IA déjà formés, pas un Builder.** Promesse : « C'est déjà fait pour vous. » Tagline : **« Déléguez sans recruter. »**

## Ton

Calme, direct, chiffré (chiffres produit uniquement), autorité tranquille. Un collègue fiable. Jamais de hype startup, jamais d'emoji dans les visuels, français impeccable (accents sur majuscules : À, É).

## Lexique

| ✅ Dire | ❌ Ne jamais dire |
|---|---|
| assistant · il s'en charge · vous validez | outil · plateforme · configurez · automatisation |
| récap matinal | digest (collision « Le Débrief ») |
| déjà formé · déjà fait pour vous | IA générative · workflow · LLM · RAG · n8n |

## Attribution par assistant (v1.1 — ADR-078)

- **Max** `#FF6248` (coral) — email : tri, récap, brouillons validés. « Libérez 2h par jour. »
- **Zoé** `#9B59B6` (violet) — LinkedIn : posts dans votre voix, vous validez.
- **Eli** `#2C4A7C` (navy) — **TOUTES les relances** (devis + factures + impayés) + mise en demeure préparée. *(Jamais Leo.)*
- Vert brand `#22C55E` : éléments génériques Manda uniquement (wordmark, CTA neutre) — jamais en accent persona.

## Design system (visuels — chaîne content-factory)

- Fonds : sable `#FFF8F3` · papier chaud `#FFFBF8` · sombre `#0E1912` (2-3 posts max par série).
- Typo : Plus Jakarta Sans (corps + titres) · Instrument Serif italique (pull quotes émotionnelles uniquement) · JetBrains Mono uppercase (petits labels `MANDA · <NOM>`).
- Badges pill `9999px` · cards `16px` · style Notion/Linear, généreux en blanc, zéro stock-photo.
- Logo Higgsfield réutilisable : `media_id 773e0860-cb6f-4b1d-9f6a-f608550bc45b` — « reproduce FAITHFULLY, do NOT redesign ».
- **Toute retouche d'un visuel existant passe l'original validé en référence d'image** (« reproduce EXACTLY, change only… ») — leçon v1.1b.

## Structures de posts qui marchent (banque d'angles pilote v0/v1.1)

- **Stat card produit** : chiffre produit géant (« jusqu'à 2h », « 0 relance oubliée »).
- **Quote card serif** : phrase rhétorique (« Votre trésorerie ne devrait pas dépendre de votre mémoire. »)
- **Hook card** : recadrage (« Un devis sans réponse n'est pas un non. C'est un oubli. »)
- **Carrousel 5 slides** : méthode déroulée, slide N générée avec slide N-1 en référence, CTA final fond sombre.
- Levier central : décharge de la charge mentale + « vous validez » comme preuve de contrôle.
