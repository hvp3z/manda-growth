---
type: dérivé
sources: md-map /pricing (page.tsx + fr.json, état post-CP-112) · ADR-041/066/082 · sidecar Axiom
sync: 2026-07-28
règle: ne modifier que via playbooks/resync-context.md — le prix maître est TOUJOURS la page /pricing en prod
---

# OFFER — Ce qui est vendable AUJOURD'HUI

## Catalogue (prix publics, mensuel pur, essai 7 jours sans engagement)

| Assistant | Rôle (mots client) | Essentiel | Pro |
|---|---|---|---|
| **Max** — assistant email | Trie, résume (récap matinal), prépare vos réponses dans votre style. Vous validez, il envoie. | **19 €/mois** | **39 €/mois** |
| **Zoé** — assistante réseaux sociaux | Écrit et publie vos posts LinkedIn dans votre voix. Vous validez. *(Instagram : ne pas promettre — gate Meta)* | **29 €/mois** | **49 €/mois** |
| **Pack Max + Zoé Pro** | Les deux, au complet. | — | **69 €/mois** |
| **Eli** — assistant documents & impayés | Relance vos devis et factures (J+7 courtoise, J+15 ferme), prépare la mise en demeure — **vous validez avant envoi**. | **29 €/mois** (offre unique) | — |

- **Prix bloqué à vie** tant que l'abonnement reste actif.
- **Offre Fondateur** : −50 % pendant 12 mois, coupon `FONDATEUR`, **10 places** (ADR-041). C'est l'offre à pousser en pré-vente.

## Exclusions fermes (voir GUARDRAILS)

- **Leo n'est pas vendable en communication** (#46) — ne jamais le mentionner.
- **Pas de bundle « cash-flow » 49 €** — supprimé (ADR-082). Eli se vend seul.
- **Pas d'import Google Sheets** — retiré de la v1 (ADR-062 amendé).
- **Pas d'activation immédiate en outbound** (#29) — CTA = RDV ou waitlist Fondateur.

## Mécanique de vente actuelle (mode pré-vente)

1. Contenu/prospection → **RDV découverte 15 min** ou **waitlist Fondateur**.
2. RDV : diagnostic douleur (impayés / boîte mail) → proposition assistant adapté → place Fondateur réservée.
3. Activation réelle dès la levée de #29 (les Fondateurs sont onboardés en premier, accompagnés à la main).
