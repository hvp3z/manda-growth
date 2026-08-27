---
date: 2026-07-28
agent: growth-marketer
type: produit
statut: caduc
verdict: "Axiom 2026-08-27 — CADUC : la destination de conversion existe désormais (manda.run/pricing, Stripe LIVE prouvé 26/08, chemin de paiement sans crash CP-120/120b, G1 levée le 27/08). Aucune page waitlist ne sera construite (ADR-072 : pas de page intermédiaire quand le produit vend). Historique : Axiom 2026-07-28 — accepté, re-scopé en CP produit (backlog G-1), en attente spec growth + choix destination emails ; jamais briefé."
---

# SIG-001 — Besoin d'un CP produit : page waitlist Fondateur (`manda.run/fondateur`)

## Constat

Tout le trafic growth (posts LinkedIn, futur article SEO, outbound pré-vente) n'a aujourd'hui aucune destination de conversion valide. Tant que #29 (app review Google OAuth / CASA) bloque l'activation, envoyer du trafic vers `/pricing` produit des checkouts qui aboutissent à un onboarding cassé (écran « phishing »). Les CTA autorisés (G1) sont « RDV 15 min » et « inscription waitlist Fondateur » — mais la waitlist n'a pas de page. Le premier post de la campagne (déposé ce jour en review-queue) doit se rabattre sur un CTA « message privé », moins mesurable et non scalable.

## Preuve

- `context/GUARDRAILS.md` G1 : CTA autorisés = RDV découverte 15 min · inscription waitlist Fondateur (aucune activation self-serve avant la levée de #29).
- `playbooks/landing-waitlist.md` §Pourquoi : « Il faut UNE destination : la page Fondateur — capture email + promesse claire. »
- `GOALS.md` : objectif semaine 2026-07-28 « Page waitlist Fondateur spécifiée et livrée » + jalon « 30 inscrits waitlist avant d'ouvrir l'outbound à froid » — impossible à compter sans page.
- `review-queue/2026-07-28-post-linkedin-eli-impayes.md` : premier livrable de campagne dont le CTA pointe vers le DM faute de page.

## Proposition

Qu'Axiom scope un CP produit dans md-map pour implémenter la page :

1. **URL** : `manda.run/fondateur`.
2. **Contenu** : copy intégral FR fourni par growth-marketer (spec complète à venir en review-queue selon `playbooks/landing-waitlist.md` — hook douleur ICP, offre Fondateur 10 places −50 % / 12 mois prix bloqué, périmètre Max/Zoé/Eli conforme G4, bloc RGPD 2 niveaux G5, mention « lancement accompagné : les 10 Fondateurs sont onboardés à la main »).
3. **Formulaire** : email (requis) + « votre plus gros voleur de temps ? » (optionnel, qualification du lead).
4. **Tracking** : un événement de conversion `waitlist_fondateur_signup`.
5. **À trancher par Matthieu** : où atterrissent les emails (outil emailing vs table DB).

Dès la page live : tous les CTA growth (posts, articles, bio LinkedIn, outbound) pointent vers elle jusqu'à la levée de #29.
