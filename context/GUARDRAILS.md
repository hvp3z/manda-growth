---
type: dérivé
sources: sidecar Axiom (décisions #29/#46/#21/#63, ADR-064/068/082/085/087/089) · CNIL B2B · positioning-intel.md
sync: 2026-08-26
règle: ne modifier que via playbooks/resync-context.md
---

# GUARDRAILS — Règles dures (bloquantes)

Un livrable qui viole une de ces règles est **invalide**, même s'il est excellent. En cas de doute : review-queue, pas d'envoi.

## G1 — #29 : l'onboarding email n'est pas encore OUVERT (temporaire)

**Changement de statut (resync 2026-07-31, CP-115 validé)** : la porte email **fonctionne** techniquement de bout en bout — l'écran « phishing » est levé depuis le 2026-07-22, le bug d'activation de la cible n°1 (dirigeant PME/artisan) et la reconnexion de boîte sont corrigés et prouvés (CP-115). Ce qui reste : un bandeau Google « application non vérifiée » (CASA en cours, fenêtre ≤100 comptes) et l'ouverture réservée à la cohorte Fondateur au lancement. Donc la règle opérationnelle NE CHANGE PAS :
- **Aucun CTA « connectez votre boîte » / « démarrez l'essai » dans l'outbound** tant qu'Axiom n'a pas déclaré le lancement ouvert. CTA autorisés : RDV découverte 15 min · inscription waitlist Fondateur.
- Aucun média payant (déjà acté 2026-07-12).

## G2 — Leo : #46 close (CP-118), statut CHANGÉ le 2026-08-24

**Changement de statut (resync 2026-08-24, CP-118/119 validés)** : le checkout Leo est retiré du produit (#46 soldée par construction) et la page tarif publique nomme Leo comme **futur** (« Bientôt — prospection », « Premium ouvre avec Leo »). La règle passe de « ne jamais mentionner » à :
- Leo est **nommable uniquement comme futur**, dans les mots de la page (« arrive avec Premium », « bientôt — prospection »). **Jamais** de date, jamais « disponible », jamais de feature Leo décrite comme livrée, jamais Leo en tête d'affiche.
- Les assistants **vendables** restent **Max, Zoé, Eli** (unité 29 € / pack 69 €). Leo ne livre rien avant Leo-Prospection.

## G2bis — Grille tarifaire (ADR-087/089) — nouvelle règle

- **Jamais de paliers** (Essentiel/Pro), jamais « prix bloqué à vie », jamais de bundle Max+Zoé ni cash-flow 49 € : tout est mort (voir OFFER).
- **Fondateur = packs uniquement** (−50 % / 12 mois, 10 places). Écrire « Fondateur sur Max à 9,50 € » est un défaut bloquant.
- **Jamais de quota chiffré** ni de comparatif avec des ✗ (décision Matthieu 2026-08-21) : « chaque assistant reste complet ».
- ~~Jusqu'au deploy CP-119 + bascule Stripe LIVE : aucun prix dans un contenu public~~ → **LEVÉE le 2026-08-26** (grille en prod, Stripe LIVE prouvé de bout en bout). Les prix 29 / 69 / 129 et le Fondateur 34,50 € peuvent être écrits — **uniquement ces montants**, dans les mots d'OFFER.md.

## G3 — #21 : e-facture (close dans le produit le 2026-08-24, la règle de discours reste)

Le copy produit ne porte plus aucune promesse de conformité (CP-117 + CP-119 : « conforme 2026 », « Factur-X », « prêt pour l'obligation » sont morts). La règle growth **ne change pas** : jamais une promesse ni un levier de peur (« conformité assurée » = mensonge : réception 2026 ≠ émission PME 2027). Au plus un rappel de contexte, 1 contenu max — par défaut : ne pas en parler.

## G4 — Périmètre produit réel (zéro promesse fantôme, ADR-072)

Fonctionnalités mentionnables : tri email · brouillons validés par le client · récap matinal (dire « récap », jamais « digest ») · relances devis/factures N1/N2 auto · **mise en demeure toujours préparée puis VALIDÉE par le client avant envoi** (toute formulation d'envoi auto = défaut bloquant) · publication LinkedIn Zoé (ghostwriter validé) · connexion Gmail/Outlook.
NON mentionnables : import Google Sheets (retiré, ADR-062 amendé) · Instagram en promesse ferme (gate Meta) · agenda/calendrier (non codé) · toute feature non livrée.

## G5 — RGPD : la règle des deux niveaux (jamais amalgamés)

- **Niveau 1 (stockage)** : « Vos données sont stockées en Europe, sur nos serveurs. »
- **Niveau 2 (traitement LLM)** : « Le traitement IA est soumis à un DPA EU, sans entraînement ni stockage de vos contenus. »
- Interdit : « vos données restent en Europe » tout court, ou tout message qui mélange les deux niveaux.
- ⚠️ **Migration vers une IA française (Mistral) : GRAVÉE (ADR-085, 2026-07-31) mais NON LIVRÉE.** Tant que cette ligne n'est pas levée par un resync Axiom : aucun claim « IA française », « IA européenne », « souveraineté », « vos données ne quittent pas l'Europe ». Les deux niveaux ci-dessus restent le maximum autorisé.

## G6 — Cold email B2B (CNIL + deliverability)

- B2B opt-out : objet de l'email **en lien direct avec la fonction** du destinataire · identification claire de l'expéditeur · lien de désinscription fonctionnel dans chaque email.
- **Jamais depuis `manda.run`** : domaine d'envoi dédié uniquement (protège la deliverability du domaine produit).
- Volume progressif (warm-up), jamais d'achat de listes opt-in douteuses ; sources publiques/annuaires professionnels uniquement.
- **v1 : aucun envoi sans validation humaine** (voir échelle d'autonomie).

## G7 — Wording de marque (résumé — détail dans BRAND_VOICE.md)

- Le mot « automatisation » n'apparaît jamais dans le copy client (achat « respiration », pas « automation »).
- Aucun chiffre externe (stats marché, % impayés, DSO) — uniquement des affirmations produit.
- Jargon interdit : IA générative, workflow, LLM, RAG, n8n, plateforme, configurer.

## G8 — Échelle d'autonomie par action

| Action | Niveau | Règle |
|---|---|---|
| Recherche, veille, sourcing, rédaction de signaux | ✅ Autonome | Agir sans demander |
| Rédaction de livrables (posts, articles, séquences, pages) | ✅ Autonome | Produire FINI, déposer en review-queue |
| Publication (LinkedIn, SEO, page live) | 🟡 Draft-review | Jamais publier soi-même tant que le palier n'est pas libéré (10 publications validées sans correction) |
| Envoi cold email | 🔴 Validation obligatoire | Chaque envoi validé par Matthieu (v1) |
| Pricing, positionnement, roadmap, promesse produit | ⛔ Jamais | Émettre un signal (`signals/`), point final |

## G10 — Vertical garage / carrossier (ADR-090, 2026-08-26) — promesses interdites tant que CP-122/123 ne sont pas livrés

Le garage/carrossier indépendant devient une cible **prioritaire** (voir ICP, déclinaison C). Ce qui est vendable = Eli + Max **existants**. Sont des **défauts bloquants** tant qu'Axiom n'a pas levé cette ligne : « relance automatique de l'expert », « facture à émettre détectée », « réponse automatique aux demandes de devis », « recherche de pièces / de prix », « devis généré », tout chiffre de temps gagné sur le devis. Angle autorisé : *« vos devis et factures suivis et relancés depuis votre boîte mail, sans changer de logiciel »*. Ne jamais citer DARVA/Sidexa/AutoCoreAI/Clotilde. Le paiement/encaissement n'est **jamais** un sujet (Manda ne le voit pas).

## G9 — Item bloqué

Un item en review-queue sans verdict depuis > 48 h : ne pas relancer, ne pas forcer — continuer sur d'autres actions et le noter dans DAILY_LOG.
