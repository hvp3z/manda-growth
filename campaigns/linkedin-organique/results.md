# linkedin-organique — résultats

> Append-only. Une section par contenu publié. Ce qui est mesuré, et ce qui ne l'est pas, est dit.
> Créé le 2026-09-02, demandé par le verdict Matthieu du 2026-08-27 et resté dû cinq jours.

## 2026-09-01 · Post LinkedIn « Un devis sans réponse n'est pas un non » (Eli, impayés)

| Fait | Valeur |
|---|---|
| Canal | LinkedIn, compte Matthieu, publié par Zoé |
| URN | `7500545705221185536` |
| Programmé | 2026-08-31 08:30 Paris |
| Réellement publié | 2026-09-01 |
| Inscriptions attribuables | 0 |

**Écart entre programmation et publication.** Le post a été refusé le 31/08 par LinkedIn
(`426 NONEXISTENT_VERSION`) : la version d'API était figée en dur depuis CP-88 et avait été sunsetée.
Corrigé par CP-128a et republié le 01/09, à quelques heures de la règle des 48 h qui l'aurait tué
définitivement. Le post de lancement a donc manqué son créneau du lundi matin.

**Ce qui n'est pas mesuré.** Impressions, clics et vues du profil ne sont pas relevés : personne ne
les a notés dans les 48 h et LinkedIn ne les expose pas rétroactivement de façon fiable. Le trafic
vers `manda.run` est instrumenté côté Vercel Analytics mais n'a jamais été lu. Conclusion honnête :
on sait que ce post n'a produit aucune inscription, on ne sait pas s'il a produit de l'audience.

**Leçon.** Un contenu publié sans relevé dans les 48 h est un contenu dont on ne saura jamais rien.
Le relevé n'est pas de la rigueur administrative, c'est la seule chose qui distingue un test d'un coup
de dés.

## 2026-08-31 ou 09-01 · Vidéo d'introduction, compte Instagram Manda

| Fait | Valeur |
|---|---|
| Canal | Instagram, compte Manda |
| Format | vidéo verticale, tournage réel mode B, montage CapCut |
| Script | V3, `review-queue/done/2026-08-28-founder-video-intro-instagram.md` |
| Retours entrants | plusieurs, dont Maria (message privé) |
| Rendez-vous obtenu | 1 — Maria, vendredi 2026-09-04 |
| Inscriptions attribuables | 0 |

**C'est le seul contenu du lancement qui a produit une conversation.** Aucune inscription n'a suivi,
mais la conversion visée à ce stade n'est pas l'inscription en libre-service : c'est le rendez-vous.
Le premier retour produit de tout le lancement (contradiction de capacité sur `/pricing`, SIG-002 puis
ADR-094) vient de ce canal, pas de LinkedIn.

**Ce qui n'est pas mesuré.** Vues, portée, taux de complétion de la vidéo. À relever dans Instagram
Insights tant que la fenêtre le permet.

## 2026-09-09 · Post Instagram « Vos impayés ne le resteront plus » (Eli, visuel a1), compte Manda

| Fait | Valeur |
|---|---|
| Canal | Instagram, compte `bonjour.manda` (31 abonnés, 1 publication avant celle-ci) |
| Format | image 4:5 `content-factory/output/mineral-v1/a1.png`, légende approuvée le 27/08 |
| Programmé | 2026-09-09 12:15 Paris, programmateur natif Instagram, par Axiom via Chrome |
| Réellement publié | à confirmer après 12:15 |
| Lien de bio au moment de la publication | `manda.run` (décision Matthieu du 09/09 : pas de passage à `/pricing`) |
| Hashtags | `#tresorerie #impayes #independants #pme #entrepreneur` |
| Inscriptions attribuables | à relever |
| Retours entrants (DM, commentaires) | à relever |

**Ce que ce post teste.** Le format affiche (visuel minéral + légende produit) sur Instagram, là où le seul
contenu qui a produit une conversation jusqu'ici est la vidéo d'intro face caméra. Si ce post ne produit ni
DM ni commentaire à 48 h, la conclusion est que sur ce compte le format qui convertit est le fondateur à
l'image, et les affiches passent en support secondaire.

**Relevé dû avant le 2026-09-11 12:15** : portée, impressions, visites du profil, clics sur le lien de bio,
DM et commentaires. Sans relevé dans les 48 h, ce post ne nous apprend rien.
