---
type: dérivé
sources: sidecar Axiom (project-knowledge.md §4/§8, roadmap-backlog.md, ADR-085/087/089)
sync: 2026-09-10
règle: resynchronisé par Axiom via playbooks/resync-context.md après chaque session stratégie qui change la donne
---

# ROADMAP_SNAPSHOT — Ce que les agents growth doivent savoir de la roadmap

## Vendable aujourd'hui (grille ADR-089 — détail OFFER.md)
- **Max** (email) — en prod, **29 €/mois** à l'unité. **Lancement Fondateur ouvert le 27/08 (G1 levée)** — bandeau Google « non vérifiée » assumé, fenêtre ≤100 comptes.
- **Zoé** (LinkedIn & Instagram) — en prod, publication LinkedIn réelle prouvée, **29 €/mois**. Depuis CP-121 (27/08) l'admin est canal-aware : un client LinkedIn-only atterrit sur son admin LinkedIn. Instagram : gate Meta non levée, **mais mentionnable depuis le 2026-09-10** (décision Matthieu, onboarding à la main, voir G4).
- **Eli** (devis, factures & relances) — en prod, **29 €/mois**. Même contrainte #29 pour l'email.
- **Pack complet Max + Zoé + Eli — 69 €/mois**, **l'offre cible** ; Fondateur = 34,50 €/mois pendant 12 mois, 10 places, packs uniquement.
- **Premium 129 €** (Leo + multi-comptes Zoé) — affiché, **non souscriptible** tant que Leo-Prospection n'est pas livré.

## État du chantier pricing (#45 — clos côté code le 2026-08-24)
- CP-117 (wording e-facture, Fondateur 12 mois, pages légales) · CP-118 (socle Stripe 29/69/129, modules retirés à la résiliation, Fondateur pack-only) · CP-119 (page tarif « Tarifs v2 ») : **tous validés**.
- ✅ **En prod depuis le 26/08** : prix live 29/69/129, coupon `FONDATEUR`, **webhook Stripe live posé et souscription test réelle prouvée de bout en bout** (puis remise à l'état normal). Les prix peuvent être écrits (G2bis levée).
- ✅ **CP-120 / CP-120b / CP-121 validés (26–27/08) et vérifiés en prod** : erreurs de paiement rendues métier (#63 clos), coupon inconnu refusé, `redirect_url` sign-up honoré, Zoé canal-aware. **Le self-serve pack Fondateur peut être poussé** (OFFER §Mécanique).

## Angle éditorial (décision Axiom 2026-07-31, inchangé)
- **Tête d'affiche : Eli (impayés) + Zoé (LinkedIn).** Max = porte d'entrée du catalogue, jamais le héros seul. Le pack complet est **l'offre à vendre** ; l'unité sert à entrer.
- Raison (contexte interne, ne pas citer dans le copy) : résumés/brouillons d'email en voie de commoditisation par les chatbots grand public ; la valeur défendable de Manda = le résultat managé (relances qui partent, posts qui sortent) sans aucune configuration.
- Ne jamais nommer ni attaquer un concurrent IA (Claude, ChatGPT, Gemini) dans le copy.

## En chantier (ne rien promettre, mais contexte utile)
- **#29 — App Review Google (CASA Tier 2)** : ne bloque plus — lancement ouvert le 27/08 sous la fenêtre ≤100 comptes, bandeau « app non vérifiée » assumé. **La page waitlist ne sera pas construite (SIG-001 caduc)** : tout le trafic va sur `manda.run/pricing`.
- **Leo-Prospection** : après le deploy pricing et #63 ; prérequis externes #58 (avocat RGPD) et #59 (contrat FullEnrich). Jusqu'à livraison : Leo = futur uniquement (G2).
- **Migration Mistral — IA française (ADR-085)** : gravée, NON livrée, après Leo-Prospection. Aucun claim « IA française / européenne / vos données ne quittent pas l'Europe » tant qu'Axiom n'a pas levé G5.
- **#62 — segment kiné** : en suspens (entretien kiné titulaire — Hugo — toujours attendu). **Aucun investissement growth kiné** d'ici là. Comptables non affectés.
- **Vertical garage/carrosserie — ADR-090 (2026-08-26), PRIORITAIRE** : terrain Davy (carrossier) → la carrosserie sous expertise vit dans la boîte mail. Deux CP après CP-121, **avant Leo-Prospection** : **CP-122** (relance de validation expert J+2 + « facture à émettre » dans le récap) puis **CP-123** (brouillon de réponse aux demandes de devis, tableau dans le mail, pas de PDF). Contrat data pièces (TecAlliance, #64) en attente — la « recherche de prix » n'existe pas et n'est pas promise. Jusqu'à leur validation : **G10** (aucune de ces capacités n'est mentionnable).
- **Leo-Prospection** : passe **derrière** le chantier garage (décision Matthieu 2026-08-26 : non pressé, bloqué #58/#59).

## Interdits de promesse (rappel — détail GUARDRAILS)
Leo disponible / daté (G2) · paliers, « à vie », quotas chiffrés, ✗ (G2bis) · conformité e-facture (#21) · activation Instagram instantanée en libre-service (gate Meta ; la mention de Zoé Instagram est autorisée depuis le 10/09, G4) · Google Sheets (retiré) · agenda (non codé) · activation immédiate (#29) · **IA française / données en Europe (ADR-085 non livrée)**.

## Séquence growth décidée (2026-07-28, confirmée 2026-07-31, amendée 2026-08-24)
~~Deploy pricing + bascule Stripe LIVE~~ ✅ (26/08) → ~~CP-120 → CP-121~~ ✅ (26–27/08) → **premier post — MAINTENANT** (LinkedIn = Matthieu fondateur · Instagram = compte Manda ; offre Fondateur **sur le pack**, CTA `manda.run/pricing`) → outbound pré-vente **comptables + garages/carrossiers** (kinés suspendus par #62) → CP-122/123 garage → client ops dès le 1er Fondateur. Zéro média payant sans décision Matthieu. *(amendé 2026-08-27)*
