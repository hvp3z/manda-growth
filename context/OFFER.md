---
type: dérivé
sources: md-map /pricing (page.tsx + PricingComposer.tsx + fr.json, état post-CP-120) · ADR-087/089 · sidecar Axiom (#45, #63 clos, G1 levée)
sync: 2026-08-27
règle: ne modifier que via playbooks/resync-context.md — le prix maître est TOUJOURS la page /pricing (état validé CP-119 ; en prod dès le deploy + bascule Stripe LIVE)
---

# OFFER — Ce qui est vendable AUJOURD'HUI

> ✅ **Resync 2026-08-26 — la grille est EN PROD et Stripe LIVE est prouvé** (CP-117→119 déployés, 3 prix live, coupon `FONDATEUR`, webhook live posé et souscription test réelle de bout en bout le 26/08, remise à l'état normal). **La ligne « aucun prix public » est levée** : les prix ci-dessous peuvent apparaître dans les contenus, tels quels (jamais d'autres montants — la page `/pricing` fait foi). Les paliers Essentiel/Pro, le « prix bloqué à vie » et le bundle Max+Zoé restent **morts**.

## Grille (mensuel pur, essai 7 jours, sans engagement, annulable en 1 clic)

| Étage | Prix | Contenu | Fondateur (−50 % / 12 mois) |
|---|---|---|---|
| **À l'unité** | **29 €/mois par assistant** | Max, Zoé **ou** Eli — **complet**, aucune fonctionnalité retirée, à aucun étage | ✗ non applicable |
| **Pack complet** ⭐ | **69 €/mois** | Max + Zoé + Eli, un seul tableau de bord (2 unités = 58 € → l'unité est un leurre, le pack est l'offre cible) | ✅ **34,50 €** les 12 premiers mois |
| **Premium** | 129 €/mois | Pack complet + **Leo (prospection)** + plusieurs comptes Zoé + plus de capacité — **pas encore souscriptible** (« Ouvre avec Leo », CTA = mailto « Parler à un humain ») | ✅ 64,50 € — à l'ouverture seulement |

**Rôles (mots client, copy validée)** : Max — *Email* · Zoé — *LinkedIn & Instagram* · Eli — *Devis, factures & relances* · Leo — *Bientôt — prospection*.

**Invariant de discours (Fig. 03 de la page)** : « Aucune ligne ne disparaît d'un étage à l'autre. Chaque assistant reste complet. » → jamais de ✗, jamais de retrait, jamais de quota chiffré (décision Matthieu 2026-08-21 : pas de chiffres de quotas au lancement).

## Offre Fondateur (ADR-089)

- **−50 % pendant 12 mois**, coupon `FONDATEUR`, **10 places**, **packs uniquement** (pack 69 → 34,50 € · Premium 129 → 64,50 €). **Jamais sur l'unité.**
- « Prix bloqué à vie » est **mort** : ne plus jamais l'écrire (la remise dure 12 mois, point).
- Formulation de la page : « Les 10 premiers comptes gardent −50 % pendant 12 mois — pack et Premium ». Compteur de places affiché en live sur `/pricing`.
- C'est l'offre à pousser en pré-vente ; la porte d'entrée du catalogue reste **l'essai 7 jours** (à l'unité ou pack).

## Exclusions fermes (voir GUARDRAILS)

- **Leo n'est pas vendable** : plus de checkout Leo (#46 close par CP-118). Il est **nommable uniquement comme futur** (« arrive avec Premium », « bientôt — prospection »), jamais avec une date, jamais comme disponible.
- **Pas de paliers** (Essentiel/Pro), **pas de bundle cash-flow 49 €**, **pas de bundle Max+Zoé** : tout cela n'existe plus.
- **Pas d'import Google Sheets** — retiré de la v1 (ADR-062 amendé).
- ~~Pas d'activation immédiate en outbound (#29)~~ → **LEVÉE le 2026-08-27 (G1)** : le CTA `manda.run/pricing` est autorisé, le RDV reste le chemin secondaire.
- ~~Chemin de paiement fragile (#63)~~ → **✅ CP-120/120b validés le 26/08, vérifiés en prod** : les erreurs métier sont propres (11ᵉ Fondateur → bandeau « places prises » sans coupon ni prix remisé · coupon sur unité refusé · déjà abonné → lien vers le compte · sign-up avec retour au tarif). **Le self-serve pack Fondateur est ouvert.** Le coupon est appliqué automatiquement par la page (aucun code à saisir, ne jamais écrire « code FONDATEUR » dans un contenu).
- Il n'existe **aucune page waitlist** (SIG-001 caduc le 27/08) : ne jamais promettre « inscrivez-vous sur la liste » — le lien, c'est `/pricing`.
- 🚗 **Garages / carrossiers (ADR-090, 2026-08-26)** : ce qu'on leur vend **aujourd'hui** = Eli et Max tels qu'ils existent (relances devis/factures N1/N2, tri de la boîte fournisseurs/experts, récap). **Non livré, donc non promis** : relance de l'expert d'assurance (J+2), « facture à émettre », brouillon de réponse aux demandes de devis, recherche de pièces/prix. Ces capacités arrivent avec CP-122/CP-123 — Axiom lèvera cette ligne à leur validation.

## Mécanique de vente actuelle (lancement ouvert depuis le 2026-08-27)

1. Contenu/prospection → **`manda.run/pricing`** (pack complet Fondateur 34,50 €/mois pendant 12 mois, essai 7 jours) **ou** RDV découverte 15 min pour celui qui hésite.
2. RDV : diagnostic douleur (impayés / boîte mail / présence LinkedIn) → proposition **pack complet Fondateur** (ou une unité à 29 € si un seul pain) → il souscrit lui-même sur `/pricing`, place comptée en live.
3. Activation immédiate à la souscription (essai 7 jours) ; chaque Fondateur est ensuite **accompagné à la main** (client-ops s'active au 1er payant). Zoé : l'admin bascule Instagram | LinkedIn selon les canaux connectés (CP-121) — un Fondateur B2B n'a besoin que de LinkedIn.
