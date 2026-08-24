---
type: dérivé
sources: sidecar Axiom (project-knowledge.md §4/§8, roadmap-backlog.md, ADR-085/087/089)
sync: 2026-08-24
règle: resynchronisé par Axiom via playbooks/resync-context.md après chaque session stratégie qui change la donne
---

# ROADMAP_SNAPSHOT — Ce que les agents growth doivent savoir de la roadmap

## Vendable aujourd'hui (grille ADR-089 — détail OFFER.md)
- **Max** (email) — en prod, **29 €/mois** à l'unité. Prérequis techniques de lancement soldés (CP-115). Mode pré-vente maintenu jusqu'à l'ouverture Fondateur (bandeau « non vérifiée », fenêtre ≤100 comptes — voir G1).
- **Zoé** (LinkedIn & Instagram) — en prod, publication LinkedIn réelle prouvée, **29 €/mois**. Instagram : gate Meta, ne pas promettre.
- **Eli** (devis, factures & relances) — en prod, **29 €/mois**. Même contrainte #29 pour l'email.
- **Pack complet Max + Zoé + Eli — 69 €/mois**, **l'offre cible** ; Fondateur = 34,50 €/mois pendant 12 mois, 10 places, packs uniquement.
- **Premium 129 €** (Leo + multi-comptes Zoé) — affiché, **non souscriptible** tant que Leo-Prospection n'est pas livré.

## État du chantier pricing (#45 — clos côté code le 2026-08-24)
- CP-117 (wording e-facture, Fondateur 12 mois, pages légales) · CP-118 (socle Stripe 29/69/129, modules retirés à la résiliation, Fondateur pack-only) · CP-119 (page tarif « Tarifs v2 ») : **tous validés**.
- ⚠️ **Pas encore en prod** : deploy conjoint à la bascule Stripe LIVE (prix + coupon côté live + env prod — action Matthieu). Jusqu'à la levée par Axiom : **aucun prix dans un contenu evergreen**, renvoyer vers `manda.run/pricing`.
- **#63 (High, avant le premier post)** : le chemin de paiement crashe sans message sur toute erreur métier (11ᵉ Fondateur, coupon sur unité). Ne pas pousser « prendre le pack » en direct avant sa levée — passer par le RDV.

## Angle éditorial (décision Axiom 2026-07-31, inchangé)
- **Tête d'affiche : Eli (impayés) + Zoé (LinkedIn).** Max = porte d'entrée du catalogue, jamais le héros seul. Le pack complet est **l'offre à vendre** ; l'unité sert à entrer.
- Raison (contexte interne, ne pas citer dans le copy) : résumés/brouillons d'email en voie de commoditisation par les chatbots grand public ; la valeur défendable de Manda = le résultat managé (relances qui partent, posts qui sortent) sans aucune configuration.
- Ne jamais nommer ni attaquer un concurrent IA (Claude, ChatGPT, Gemini) dans le copy.

## En chantier (ne rien promettre, mais contexte utile)
- **#29 — App Review Google (CASA Tier 2)** : le lancement ne l'attend plus (décision 2026-07-31) — ouverture possible sous la fenêtre ≤100 comptes (cohorte Fondateur), bandeau « app non vérifiée » assumé. La waitlist reste le réceptacle du trafic jusqu'à nouvel ordre.
- **Leo-Prospection** : après le deploy pricing et #63 ; prérequis externes #58 (avocat RGPD) et #59 (contrat FullEnrich). Jusqu'à livraison : Leo = futur uniquement (G2).
- **Migration Mistral — IA française (ADR-085)** : gravée, NON livrée, après Leo-Prospection. Aucun claim « IA française / européenne / vos données ne quittent pas l'Europe » tant qu'Axiom n'a pas levé G5.
- **#62 — segment kiné (session terrain IDEL 2026-08-24)** : le pattern tiers-payant / canal non-mail rend Max et Eli sans objet chez les IDEL et **probablement chez les kinés** (cible ADR-084). **Aucun investissement growth kiné** avant 1 entretien kiné titulaire (grille H1–H4, sidecar). Comptables non affectés.

## Interdits de promesse (rappel — détail GUARDRAILS)
Leo disponible / daté (G2) · paliers, « à vie », quotas chiffrés, ✗ (G2bis) · conformité e-facture (#21) · Instagram ferme (gate Meta) · Google Sheets (retiré) · agenda (non codé) · activation immédiate (#29) · **IA française / données en Europe (ADR-085 non livrée)**.

## Séquence growth décidée (2026-07-28, confirmée 2026-07-31, amendée 2026-08-24)
Deploy pricing + bascule Stripe LIVE → #63 → **premier post** (LinkedIn = Matthieu fondateur · Instagram = compte Manda ; offre Fondateur **sur le pack**) → outbound pré-vente **comptables** (kinés suspendus par #62) → client ops à l'arrivée des premiers Fondateurs. Zéro payant avant #29.
