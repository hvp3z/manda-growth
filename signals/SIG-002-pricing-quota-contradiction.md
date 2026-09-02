---
date: 2026-08-31
agent: axiom
type: pricing
statut: gravé (ADR-094) · volet wording clos (CP-130, 2026-09-02)
---

**Constat** : premier retour client externe (Maria, DM Instagram, le jour du lancement Fondateur) sur `/pricing` — la page affiche « Aucune ligne ne disparaît d'un étage à l'autre. Chaque assistant reste complet. » juste au-dessus de « Plus de capacité sur tous les assistants » (bloc Premium). Lue de l'extérieur, sans contexte produit, cette juxtaposition se lit comme contradictoire : si Premium donne « plus de capacité », c'est que les autres paliers ne sont pas complets.

**Analyse** : la contradiction est réelle à deux niveaux, pas seulement un problème de wording.
1. Le message est ambigu sur le site public, lu et signalé spontanément par une visiteuse — donc probablement par d'autres.
2. Plus profond : ADR-089 posait « quotas mesurés, jamais appliqués au lancement » — donc à ce stade, personne n'est réellement bloqué par la capacité, quel que soit le palier. La promesse « plus de capacité » sur `/pricing` n'est aujourd'hui pas techniquement vérifiable.

**Proposition** : sortir de l'état transitoire — appliquer réellement les quotas (pas seulement les mesurer), et clarifier le wording `/pricing` pour ne pas se relire comme contradictoire.

**Verdict** : gravé — ADR-094 (`adr-log.md`), décision prise en session avec Matthieu le 2026-08-31 : les quotas seront réellement appliqués. CP d'enforcement à scoper, référencé dans `project-knowledge.md` §« CP d'hygiène à scoper ». Le wording `/pricing` reste une action séparée, plus rapide, non encore planifiée.

**Suite — 2026-09-02, volet wording clos (CP-130)**. Le relevé fait au moment du brief a trouvé **quatre** occurrences de la promesse, pas une : la visiteuse n'avait vu que la troisième. `premium_title_italic` (« et le volume qui va avec »), `premium_body` (« avec plus de capacité »), `premium_adds_items` (« Plus de capacité sur tous les assistants ») ; la quatrième, `stage_premium_body`, était saine et a été conservée. Corriger la seule occurrence signalée aurait laissé la contradiction vivante sous trois autres formes.

CP-130 validé le 2026-09-02, 11 critères sur 11, contrôle visuel fait sur la page déployée. Un test de contrat de source interdit désormais toute promesse de capacité différentielle dans le namespace `pricing` des deux langues, et la règle est passée aux agents growth (GUARDRAILS G2bis). **Le volet enforcement reste entier** : ce CP retire une promesse que le produit ne tenait pas, il ne fait pas tenir la promesse.
