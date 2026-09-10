---
type: dérivé
sources: sidecar Axiom (décisions #29/#46/#21/#63, ADR-064/068/082/085/087/089/094, CP-120/120b/121/130 validés) · CNIL B2B · positioning-intel.md
sync: 2026-09-10
règle: ne modifier que via playbooks/resync-context.md
---

# GUARDRAILS — Règles dures (bloquantes)

Un livrable qui viole une de ces règles est **invalide**, même s'il est excellent. En cas de doute : review-queue, pas d'envoi.

## G1 — Lancement Fondateur : OUVERT depuis le 2026-08-27 (règle CTA changée)

**✅ LEVÉE le 2026-08-27 (Axiom, session 24).** Tout ce que la séquence exigeait avant le premier post est soldé : Stripe LIVE prouvé (26/08), **CP-120/120b** (chemin de paiement sans crash : 11ᵉ Fondateur = bandeau « places prises », coupon sur unité refusé, déjà abonné → lien compte, sign-up ↔ tarif) et **CP-121** (Zoé canal-aware) validés et **vérifiés en prod le 27/08**. #29 ne bloque plus (fenêtre ≤100 comptes Google, bandeau « application non vérifiée » assumé et annoncé aux Fondateurs). Nouvelle règle :
- **CTA principal autorisé : `manda.run/pricing`** — pack complet Fondateur **34,50 €/mois pendant 12 mois** (10 places, essai 7 jours). L'essai se lance en self-serve ; l'accompagnement à la main des Fondateurs commence **après** l'inscription (client-ops), il n'est plus un préalable.
- **CTA secondaire** : RDV 15 min / message privé — toujours proposé à côté du lien (le prospect qui hésite ne doit jamais être seul face au tarif).
- Toujours interdit : « connectez votre boîte » ou « démarrez l'essai » comme promesse d'activation *instantanée* hors du produit ; un Fondateur qui connecte Gmail verra un écran Google « application non vérifiée » — on le dit (script RDV, onboarding), on ne le cache pas.
- **Média payant : toujours interdit** (décision distincte de Matthieu, pas levée par G1).

<details><summary>Historique (avant le 27/08)</summary>

**Changement de statut (resync 2026-07-31, CP-115 validé)** : la porte email **fonctionne** techniquement de bout en bout — l'écran « phishing » est levé depuis le 2026-07-22, le bug d'activation de la cible n°1 (dirigeant PME/artisan) et la reconnexion de boîte sont corrigés et prouvés (CP-115). Ce qui reste : un bandeau Google « application non vérifiée » (CASA en cours, fenêtre ≤100 comptes) et l'ouverture réservée à la cohorte Fondateur au lancement. Donc la règle opérationnelle NE CHANGE PAS :
- **Aucun CTA « connectez votre boîte » / « démarrez l'essai » dans l'outbound** tant qu'Axiom n'a pas déclaré le lancement ouvert. CTA autorisés : RDV découverte 15 min · inscription waitlist Fondateur.
- Aucun média payant (déjà acté 2026-07-12).
</details>

## G2 — Leo : #46 close (CP-118), statut CHANGÉ le 2026-08-24

**Changement de statut (resync 2026-08-24, CP-118/119 validés)** : le checkout Leo est retiré du produit (#46 soldée par construction) et la page tarif publique nomme Leo comme **futur** (« Bientôt — prospection », « Premium ouvre avec Leo »). La règle passe de « ne jamais mentionner » à :
- Leo est **nommable uniquement comme futur**, dans les mots de la page (« arrive avec Premium », « bientôt — prospection »). **Jamais** de date, jamais « disponible », jamais de feature Leo décrite comme livrée, jamais Leo en tête d'affiche.
- Les assistants **vendables** restent **Max, Zoé, Eli** (unité 29 € / pack 69 €). Leo ne livre rien avant Leo-Prospection.

## G2bis — Grille tarifaire (ADR-087/089) — nouvelle règle

- **Jamais de paliers** (Essentiel/Pro), jamais « prix bloqué à vie », jamais de bundle Max+Zoé ni cash-flow 49 € : tout est mort (voir OFFER).
- **Fondateur = packs uniquement** (−50 % / 12 mois, 10 places). Écrire « Fondateur sur Max à 9,50 € » est un défaut bloquant.
- **Jamais de quota chiffré** ni de comparatif avec des ✗ (décision Matthieu 2026-08-21) : « chaque assistant reste complet ».
- 🆕 **Jamais la capacité comme argument de palier (ADR-094, CP-130, 2026-09-02).** Écrire que Premium — ou n'importe quel étage — donne « plus de capacité », « plus de volume », « plus de traitements » est un **défaut bloquant**, chiffré ou non. Deux raisons, et la seconde suffit : ça contredit l'invariant « chaque assistant reste complet », et **c'est faux** — aucun client n'est aujourd'hui réellement limité par sa capacité, à aucun étage, donc la promesse n'est même pas vérifiable. Une visiteuse l'a relevée seule sur `/pricing` le jour de l'ouverture Fondateur (SIG-002). **Premium se justifie par deux choses, et uniquement par elles : Leo (la prospection) et plusieurs comptes Zoé.** Cette ligne sera levée par Axiom le jour où l'enforcement des quotas sera livré.
- ~~Jusqu'au deploy CP-119 + bascule Stripe LIVE : aucun prix dans un contenu public~~ → **LEVÉE le 2026-08-26** (grille en prod, Stripe LIVE prouvé de bout en bout). Les prix 29 / 69 / 129 et le Fondateur 34,50 € peuvent être écrits — **uniquement ces montants**, dans les mots d'OFFER.md.

## G3 — #21 : e-facture (close dans le produit le 2026-08-24, la règle de discours reste)

Le copy produit ne porte plus aucune promesse de conformité (CP-117 + CP-119 : « conforme 2026 », « Factur-X », « prêt pour l'obligation » sont morts). La règle growth **ne change pas** : jamais une promesse ni un levier de peur (« conformité assurée » = mensonge : réception 2026 ≠ émission PME 2027). Au plus un rappel de contexte, 1 contenu max — par défaut : ne pas en parler.

## G4 — Périmètre produit réel (zéro promesse fantôme, ADR-072)

Fonctionnalités mentionnables : tri email · brouillons validés par le client · récap matinal (dire « récap », jamais « digest ») · relances devis/factures N1/N2 auto · **mise en demeure toujours préparée puis VALIDÉE par le client avant envoi** (toute formulation d'envoi auto = défaut bloquant) · publication LinkedIn Zoé (ghostwriter validé) · connexion Gmail/Outlook.
NON mentionnables : import Google Sheets (retiré, ADR-062 amendé) · agenda/calendrier (non codé) · toute feature non livrée.

**Changement 2026-09-10 (décision Matthieu, session Axiom 35) : Zoé Instagram devient mentionnable.** La gate Meta (ADR-057) n'est pas levée, mais Matthieu onboarde les Fondateurs Instagram **à la main** (ajout comme testeurs) tant qu'elle ne l'est pas. Formulation autorisée : « Zoé garde le fil avec votre communauté Instagram, dans votre ton, rien ne part sans votre accord » (réponses aux commentaires). Toujours interdit : promettre une activation Instagram instantanée en libre-service, et tout ce qui n'est pas livré. Le mot « automatisation » et toute formule de type « sans supervision » restent exclus (G7, ADR-072).

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
