---
type: dérivé
sources: positioning-intel.md (sidecar, section 6 — persona v2) · ADR-052 (verticale kiné) · ADR-068
sync: 2026-07-28
règle: ne modifier que via playbooks/resync-context.md
---

# ICP — À qui on parle

## Archétype : « Le Dirigeant Débordé »

| Attribut | Profil |
|---|---|
| Qui | Dirigeant de PME / indépendant FR, 35-55 ans |
| Douleur n°1 | Plus assez de temps — ni pour le business, ni pour sa vie |
| Douleur n°2 | Tâches répétitives à faible valeur qui volent ses heures (emails, relances) |
| Tech | ChatGPT novice, zéro culture agentique — la sophistication zéro est une force |
| Ce qu'il veut | Que « quelqu'un s'en occupe » — sans avoir à gérer ce quelqu'un |
| Budget | 200-500 €/mois de capacité, décision seule, rapide, émotionnelle |
| Vrai concurrent | « Je le fais moi-même » ou « j'embauche un assistant à temps partiel » — PAS n8n/Make |
| Nature de l'achat | Une **respiration**, pas une « automatisation » (mot interdit) |

## Cible v1 (décision 2026-07-28) : professions du chiffre et de la santé

### Déclinaison A — Comptable indépendant / petit cabinet
- Exemple réel : ~200 K€ CA, 3 enfants, déborde.
- Douleurs : boîte mail saturée en période fiscale · relances d'honoraires impayés repoussées · zéro temps commercial.
- Assistants : **Max** (récap + brouillons) + **Eli** (relances honoraires).
- Angle RGPD fort (données clients sensibles) — secteur prioritaire RGPD.
- Canal non-équitable : prescription OEC / CNOEC (charte : hébergement UE, no-training) — dossier à préparer, activation = décision Axiom/Matthieu.

### Déclinaison B — Kinésithérapeute libéral (ADR-052)
- Douleurs : administratif hors soin non facturé · relances (dépassements, factures mutuelles/patients) jamais faites · emails entre deux patients.
- Assistants : **Eli** (relances) + **Max** (tri/récap).
- Sensible à : temps rendu au soin, simplicité absolue, conformité données de santé (ne JAMAIS promettre un traitement de données de santé — Manda traite l'administratif, pas le médical).
- Canal : URPS kiné, ordres régionaux, groupes métier.

## Objections types (à désamorcer, jamais ignorer)

1. « Encore un logiciel à apprendre » → Ce n'est pas un logiciel à configurer, c'est un assistant déjà formé.
2. « Mes données / celles de mes clients » → règle RGPD 2 niveaux (GUARDRAILS G5), DPA EU, révocable en un clic.
3. « L'IA va écrire n'importe quoi » → Vous validez tout ; rien ne part sans votre feu vert (vrai dans le produit : ADR-064).
4. « Pas le temps de mettre ça en place » → Vous décrivez votre activité, c'est tout. (Store, pas Builder.)
