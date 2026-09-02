---
date: 2026-08-31
agent: axiom
type: pricing
statut: gravé (ADR-094)
---

**Constat** : premier retour client externe (Maria, DM Instagram, le jour du lancement Fondateur) sur `/pricing` — la page affiche « Aucune ligne ne disparaît d'un étage à l'autre. Chaque assistant reste complet. » juste au-dessus de « Plus de capacité sur tous les assistants » (bloc Premium). Lue de l'extérieur, sans contexte produit, cette juxtaposition se lit comme contradictoire : si Premium donne « plus de capacité », c'est que les autres paliers ne sont pas complets.

**Analyse** : la contradiction est réelle à deux niveaux, pas seulement un problème de wording.
1. Le message est ambigu sur le site public, lu et signalé spontanément par une visiteuse — donc probablement par d'autres.
2. Plus profond : ADR-089 posait « quotas mesurés, jamais appliqués au lancement » — donc à ce stade, personne n'est réellement bloqué par la capacité, quel que soit le palier. La promesse « plus de capacité » sur `/pricing` n'est aujourd'hui pas techniquement vérifiable.

**Proposition** : sortir de l'état transitoire — appliquer réellement les quotas (pas seulement les mesurer), et clarifier le wording `/pricing` pour ne pas se relire comme contradictoire.

**Verdict** : gravé — ADR-094 (`adr-log.md`), décision prise en session avec Matthieu le 2026-08-31 : les quotas seront réellement appliqués. CP d'enforcement à scoper, référencé dans `project-knowledge.md` §« CP d'hygiène à scoper ». Le wording `/pricing` reste une action séparée, plus rapide, non encore planifiée.
