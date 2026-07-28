---
type: dérivé
sources: sidecar Axiom (décisions #29/#46/#21, ADR-064/068/082) · CNIL B2B · positioning-intel.md
sync: 2026-07-28
règle: ne modifier que via playbooks/resync-context.md
---

# GUARDRAILS — Règles dures (bloquantes)

Un livrable qui viole une de ces règles est **invalide**, même s'il est excellent. En cas de doute : review-queue, pas d'envoi.

## G1 — #29 : l'onboarding email est CASSÉ (temporaire)

Tant que l'app Google/Nylas n'est pas approuvée en production, un prospect qui connecte sa boîte voit un écran « phishing ». Donc :
- **Aucun CTA « connectez votre boîte » / « démarrez l'essai » dans l'outbound.** CTA autorisés : RDV découverte 15 min · inscription waitlist Fondateur.
- Aucun média payant (déjà acté 2026-07-12).

## G2 — #46 : Leo n'existe pas commercialement

Leo (prospection) ne livre rien avant Leo-Prospection (septembre). **Interdiction absolue de mentionner Leo** dans tout contenu, post, email, page. Les assistants communicables : **Max, Zoé, Eli**.

## G3 — #21 : e-facture

Jamais une promesse ni un levier de peur (« conformité assurée » = mensonge : réception 2026 ≠ émission PME 2027). Au plus un rappel de contexte, 1 contenu max — par défaut : ne pas en parler.

## G4 — Périmètre produit réel (zéro promesse fantôme, ADR-072)

Fonctionnalités mentionnables : tri email · brouillons validés par le client · récap matinal (dire « récap », jamais « digest ») · relances devis/factures N1/N2 auto · **mise en demeure toujours préparée puis VALIDÉE par le client avant envoi** (toute formulation d'envoi auto = défaut bloquant) · publication LinkedIn Zoé (ghostwriter validé) · connexion Gmail/Outlook.
NON mentionnables : import Google Sheets (retiré, ADR-062 amendé) · Instagram en promesse ferme (gate Meta) · agenda/calendrier (non codé) · toute feature non livrée.

## G5 — RGPD : la règle des deux niveaux (jamais amalgamés)

- **Niveau 1 (stockage)** : « Vos données sont stockées en Europe, sur nos serveurs. »
- **Niveau 2 (traitement LLM)** : « Le traitement IA est soumis à un DPA EU, sans entraînement ni stockage de vos contenus. »
- Interdit : « vos données restent en Europe » tout court, ou tout message qui mélange les deux niveaux.

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

## G9 — Item bloqué

Un item en review-queue sans verdict depuis > 48 h : ne pas relancer, ne pas forcer — continuer sur d'autres actions et le noter dans DAILY_LOG.
