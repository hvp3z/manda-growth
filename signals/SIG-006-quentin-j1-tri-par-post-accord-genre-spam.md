---
date: 2026-09-17
agent: matthieu
type: produit
statut: re-scopé (CP-135 + B-28→B-32, session 38 du 2026-09-17)
---

**Constat** : deux retours de Quentin (@bourr_, 260k, premier client Créateur) : le transcript de l'onboarding du 16/09 (relu à froid) et son premier tour de tableau de bord le lendemain matin, au petit-déjeuner, qui sera sa routine.

**J+1 (17/09, matin)**
1. Les commentaires à réviser doivent être **groupés par post**, avec un repère visuel (miniature ou extrait de la légende, il n'y a pas de titre de post), et présentés comme « tout ce que je n'ai pas vu depuis ma dernière connexion ». Aujourd'hui la file est chronologique et le commentaire seul ne dit pas à quoi il répond.
2. Zoé répond au **féminin** (« contente », « joyeuse ») sur le compte d'un homme. Il faut un accord grammatical par créateur.

**J0 (16/09, transcript de l'onboarding)**
3. **Bots et liens externes** : Quentin masque et supprime à la main des commentaires de bots (« tape k.ol sur Google », liens vers des sites). Zoé ne doit jamais y répondre. Il a contourné avec les « Sujets bloqués » (`lol`, `k.ol`), dont il a d'abord cru qu'ils masquaient le commentaire.
4. **Aucune notification** : il veut, le matin, tout ce qui attend sa décision depuis la dernière fois.
5. Le badge « 20 » de l'onglet Commentaires est le total reçu, lu comme un motif : sans valeur. Ne garder que ce qui attend une décision (révision) ou ce qui est nouveau depuis la dernière connexion (autonome).
6. **Facebook** : 80k abonnés, bientôt 100k, les commentaires arrivent. Deuxième canal créateur naturel, même app Meta.
7. Comment→DM automatique (« commente APPLI ») : il l'a vu chez un autre créateur, veut la même chose. Bloqué par Meta (Advanced Access + certification), dit en séance : plus tard, quand le MRR le paie.
8. Type de créateur mono-choix : il aurait voulu fitness **et** nutrition.
9. Widget de connexion affiché en anglais à l'arrivée.
10. Invitation testeur Meta : acceptable **uniquement sur web desktop**, invisible dans l'app mobile, aucun mail pour un `pending`. Leçon d'onboarding, pas de code.
11. Hors Manda : Quentin veut faire refaire son site (coaching, e-books, réservation, paiement) pour 1 500-2 000 €/an au lieu de son appli actuelle, renouvellement mars 2027. Opportunité services LMD → fiche CRM.

**Analyse** : les points 1, 2, 3, 5 touchent ce que Quentin voit chaque matin et ce que 260k personnes lisent sous ses posts : la donnée pour 1 est déjà persistée (CP-131 : `media_id`, légende, permalink), 2 n'a aucun champ dans le schéma (le seul profil de voix est LinkedIn-only), 3 n'a aucune règle déterministe (le classifieur n'a que `too_short`, `emoji_only`, `hater`). Un seul CP, court.

**Verdict (Axiom, session 38)** : **re-scopé** → **CP-135** « Zoé Instagram, la revue du matin » (points 1, 2, 3, 5, libellé des sujets bloqués) · **B-28** digest email quotidien (4) · **B-29** Facebook (6) · **B-30** comment→DM, gaté ADR-057 (7) · **B-31** type de créateur multiple (8) · **B-32** locale du widget Clerk (9) · point 10 → `playbooks/onboarding-checklist.md` · point 11 → fiche Notion Quentin, relance février 2027.

**Mesure de succès** : Quentin traite sa file du matin sans ouvrir Instagram pour comprendre un commentaire ; zéro réponse accordée au féminin ; zéro réponse à un commentaire contenant un lien externe sur ses deux premières semaines.
