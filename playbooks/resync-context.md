# SOP — resync-context (resynchroniser les dérivés `context/` depuis leurs sources maîtres)

**Qui** : Axiom (session /bmad) ou Matthieu — jamais un agent growth de sa propre initiative.
**Quand — déclencheur SYSTÉMATIQUE** : à chaque `valide CP-X`, Axiom se pose la question « ce CP change-t-il quelque chose de vendable (prix, feature visible, promesse, statut #29/#46) ? ». Si oui, le resync se fait **dans la même session que la validation** — un CP qui touche du vendable n'est pas clos tant que `context/` n'est pas à jour. S'y ajoutent : toute session stratégie qui change pricing/positionnement/roadmap, et la levée d'une décision bloquante (#29, #46).

## Tables des sources maîtres

| Dérivé | Source maître (autorité) |
|---|---|
| `context/OFFER.md` | `md-map/apps/configurator/.../pricing/page.tsx` + `fr.json` (l'état de la page /pricing fait foi) |
| `context/ICP.md` | `_bmad/_memory/strategist-sidecar/positioning-intel.md` |
| `context/BRAND_VOICE.md` | `content-factory/brand/BRAND_RULES.md` + dernier REPORT.md de campagne |
| `context/GUARDRAILS.md` | décisions ouvertes du sidecar (#29, #46, #21…) + ADRs cités en frontmatter |
| `context/ROADMAP_SNAPSHOT.md` | `project-knowledge.md` §4 (roadmap) + décisions ouvertes |

## Procédure

1. Relire la source maître de chaque fichier touché par le changement.
2. Mettre à jour le dérivé, **mettre à jour `sync:` dans le frontmatter** (date du jour).
3. Si une règle GUARDRAILS change de statut (ex. #29 levée) : le dire explicitement dans la section concernée, ne pas se contenter de supprimer la règle (les agents doivent voir le changement).
4. Une ligne dans `DAILY_LOG.md` : `resync-context · fichiers · raison`.
5. Jamais l'inverse : une bonne idée trouvée dans un dérivé remonte par `signals/`, puis Axiom modifie la source, PUIS resync. *(Leçon ADR-081 : deux versions d'une même vérité finissent par se contredire sur un montant.)*
