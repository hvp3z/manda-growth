---
type: dérivé
sources: md-map /pricing (page.tsx + fr.json, état post-CP-119 « Tarifs v2 ») · ADR-087/089 · sidecar Axiom (#45, #63)
sync: 2026-08-24
règle: ne modifier que via playbooks/resync-context.md — le prix maître est TOUJOURS la page /pricing (état validé CP-119 ; en prod dès le deploy + bascule Stripe LIVE)
---

# OFFER — Ce qui est vendable AUJOURD'HUI

> ⚠️ **Resync 2026-08-24 — la grille a changé (ADR-087/089, CP-117→119 validés).** Les paliers Essentiel/Pro, le « prix bloqué à vie » et le bundle Max+Zoé sont **morts**. La nouvelle page tarif est validée mais **pas encore déployée** (deploy conjoint à la bascule Stripe LIVE, action Matthieu) : jusqu'à ce qu'Axiom lève cette ligne, **aucun prix dans un contenu public** — renvoyer vers `manda.run/pricing`. En RDV / waitlist, c'est la grille ci-dessous qui fait foi.

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
- **Pas d'activation immédiate en outbound** (#29) — CTA = RDV ou waitlist Fondateur, jusqu'à ouverture déclarée par Axiom.
- ⚠️ **Chemin de paiement** : un 11ᵉ Fondateur ou un coupon sur une unité produit aujourd'hui une erreur brute (#63, correctif à venir). Ne jamais envoyer un prospect « prendre le pack » avant que #63 soit levée — passer par le RDV.

## Mécanique de vente actuelle (mode pré-vente)

1. Contenu/prospection → **RDV découverte 15 min** ou **waitlist Fondateur**.
2. RDV : diagnostic douleur (impayés / boîte mail / présence LinkedIn) → proposition **pack complet Fondateur 34,50 €/mois pendant 12 mois** (ou une unité à 29 € si un seul pain) → place réservée.
3. Activation réelle à l'ouverture Fondateur (Fondateurs onboardés en premier, accompagnés à la main).
