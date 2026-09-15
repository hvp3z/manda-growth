---
date: 2026-09-12
agent: matthieu
type: positionnement
statut: re-scopé (2026-09-15)
---

**Constat** : retour informel de Toinou (ami de Matthieu, profil marketing) et d'autres amis lors d'une soirée le 2026-09-11, sur le discours commercial et le vocabulaire du pitch Manda face à la cible artisan/PME.

**Analyse** :
1. « Temps libre » est trop abstrait pour la cible visée (garagistes, plombiers, artisans terrain). L'accroche qui fonctionne concrétise l'usage : temps pour le cinéma, les enfants, reprendre le sport — pas le concept de temps lui-même. `context/BRAND_VOICE.md` (lexique) ne couvre pas encore cette nuance : il liste « déjà formé / déjà fait pour vous » côté ✅ mais rien sur la promesse de temps elle-même.
2. Le mot **« agent »** est incompris de la cible : dans le test raconté, un garagiste à qui on parle d' »agent » raccroche (« ça fait site internet, il vend son truc plus loin »). Le lexique actuel de `BRAND_VOICE.md` interdit déjà « outil / plateforme / configurez / automatisation » côté ❌, mais **n'interdit pas explicitement « agent »** alors que côté produit Manda se présente précisément comme un « Store d'assistants ». À vérifier si "agent" fuite dans le discours commercial oral (hors visuels) malgré le lexique écrit.
3. Proposition d'image concrète testée avec succès à l'oral : « j'ai la clé de 12 qui te fait gagner du temps » — plus parlant qu'une formulation solution/outil/IA.
4. Le discours devrait se segmenter par sous-persona (PME structurée / auto-entrepreneur / artisan terrain deskless) plutôt qu'un pitch unique — à rapprocher des déclinaisons A/B/C déjà actées dans l'ICP (cf. ADR-090 cité en SIG-003) : possible que ce soit déjà couvert côté ICP.md mais pas encore répercuté dans le pitch oral.
5. Storytelling fondateur jugé sous-exploité : le fil « passion jeux vidéo → envie de faire de l'IA → envie de récupérer du temps » (histoire personnelle de Matthieu) est identifié comme accroche universelle et memorable, à intégrer davantage au pitch/speech plutôt que l'argumentaire technique seul.
6. Une démo courte (~4 slides) est suggérée pour rendre le mécanisme produit tangible : « brouillon → tu valides/corriges → il apprend », pitché comme « ton stagiaire qui devient bon ». Le déroulé raconté nomme Max (mails), Zoé (réseaux sociaux), « Amy » (relances devis/factures) et Léo (prospection).

**Clarifié (2026-09-13)** : « Amy » n'existe nulle part dans les sources Manda (`context/BRAND_VOICE.md`, `OFFER.md`, `GUARDRAILS.md`, `memory/MEMORY.md` — recherche exhaustive, zéro occurrence). Le rôle décrit colle mot pour mot à **Eli** (`OFFER.md` : « Eli — Devis, factures & relances » ↔ transcript : « un suivi facture et devis qui va aller relancer dans tes mails »), et le rôle de Léo colle au statut canon de **Leo** (« Bientôt — prospection », non livré, G2 ↔ transcript : « Léo qui sera pour la prospection commerciale, je suis encore en train de bosser »). Il n'y a donc pas de confusion produit ni d'outil tiers : c'est Manda lui-même qui était démontré ce soir-là, et « Amy » est une coquille de dictée (speech-to-text) pour « Eli ». Aucune action produit requise sur ce point ; la démo à préparer (point 6) doit utiliser Max/Zoé/Eli/Leo, pas Amy.

**Proposition** : pas de modification de `BRAND_VOICE.md` à ce stade (signal, pas source). Matthieu prévoit une session dédiée avec Toinou (rappel calendrier 2026-09-16) : présenter le speech actuel, le faire retravailler sur l'angle storytelling fondateur + vulgarisation vocabulaire. Si les mêmes constats ressortent de cette session, envisager un CP/ADR pour : (a) ajouter « agent » à la colonne ❌ du lexique si confirmé comme mot à bannir à l'oral aussi, (b) documenter la promesse de temps sous forme d'usages concrets plutôt que le mot « temps libre », (c) capitaliser le storytelling fondateur dans un playbook (ex. `founder-video.md` existe déjà — vérifier s'il couvre déjà cet angle).

**Inconnues à lever** : le retour vient d'amis non-clients, pas d'un test terrain avec un vrai prospect artisan — à valider avant d'en faire une règle (même réserve que SIG-003 sur les signaux réseau). Le point 6 (Amy/Léo vs Eli/canon) est clarifié, voir ci-dessus.

---

**Verdict Axiom (2026-09-15) : re-scopé.** Le point 6 (démo courte) est exécuté : vidéo ≤ 1 min tournée le 15/09 sur le Débrief du compte prod de Matthieu (faits fictifs `demo-charline-2026-09-15`), envoyée à Charline (relais réseau), script écrit sous les contraintes 1, 2 et 6 du signal (« agent » absent, promesse de temps concrétisée, Max/Zoé/Eli nommés, Leo « bientôt », aucune promesse d'apprentissage par correction : le backend livre « formé sur vos exemples », ADR-072). Les points 1, 2, 4 et 5 passent par la **session Toinou, reportée à la semaine du 21/09** (Toinou indisponible la semaine du 14, créneau proposé par Matthieu le 15/09, date à confirmer) ; les retours de Charline et de ses contacts seront le premier test hors cercle d'amis. Décision d'ADR (lexique « agent » en ❌, promesse de temps en usages, storytelling fondateur en playbook) **après** ces deux retours, pas avant : réserve inchangée, signal réseau ≠ prospect. Référence : DAILY_LOG 2026-09-15.
