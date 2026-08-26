---
type: dérivé
sources: positioning-intel.md (sidecar, section 6 — persona v2) · ADR-052 · ADR-068 · **ADR-090 (vertical garage/carrosserie)** · terrain Davy 25/08 + Yann IDEL 24/08 (sidecar archive)
sync: 2026-08-26
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

## Cible v1 (décision 2026-07-28, amendée 2026-08-26) : comptables + **garages/carrossiers** (kinés en suspens)

> **Changement 2026-08-26** : le terrain IDEL (24/08) a montré que les professions conventionnées (tiers payant, logiciel de télétransmission, canal SMS/WhatsApp) rendent Max et Eli sans objet — risque transféré aux kinés (#62, **en suspens** jusqu'à un entretien kiné titulaire). Le terrain garage (Davy, carrossier, 25/08) a montré l'inverse : tout passe par la boîte mail pro. **Priorité de travail : A (comptables) et C (garages/carrossiers). B reste écrite mais gelée.**

### Déclinaison A — Comptable indépendant / petit cabinet
- Exemple réel : ~200 K€ CA, 3 enfants, déborde.
- Douleurs : boîte mail saturée en période fiscale · relances d'honoraires impayés repoussées · zéro temps commercial.
- Assistants : **Max** (récap + brouillons) + **Eli** (relances honoraires).
- Angle RGPD fort (données clients sensibles) — secteur prioritaire RGPD.
- Canal non-équitable : prescription OEC / CNOEC (charte : hébergement UE, no-training) — dossier à préparer, activation = décision Axiom/Matthieu.

### Déclinaison B — Kinésithérapeute libéral (ADR-052) — ⏸️ EN SUSPENS (#62, aucun investissement growth avant entretien titulaire)
- Douleurs : administratif hors soin non facturé · relances (dépassements, factures mutuelles/patients) jamais faites · emails entre deux patients.
- Assistants : **Eli** (relances) + **Max** (tri/récap).
- Sensible à : temps rendu au soin, simplicité absolue, conformité données de santé (ne JAMAIS promettre un traitement de données de santé — Manda traite l'administratif, pas le médical).
- Canal : URPS kiné, ordres régionaux, groupes métier.

### Déclinaison C — Garagiste / carrossier indépendant (ADR-090, prioritaire depuis le 2026-08-26)
- Exemple réel : carrossier repreneur, atelier + 1 assistante à temps partiel (mar/jeu) qui fait factures/TVA et doit lui faire valider chaque facture ; logiciel simple ~140 €/mois hérité ; les outils haut de gamme coûtent 600-700 €/mois.
- Profil : **deskless mais pas mobile** — mains dans le moteur, sollicité au comptoir, l'administratif se fait le soir par petites touches. Ne pas copier l'argumentaire « camionnette/tournée » du plombier.
- Douleurs : devis envoyés à l'**expert d'assurance** qui tarde à valider (aucune relance) · facture pas émise après validation · demandes de devis par mail = ~15 min chacune (recherche de pièces) · boîte mail pro = fournisseurs, constructeurs, experts, plateformes — **tout passe par le mail**, pas SMS/WhatsApp.
- Assistants : **Eli** (suivi devis/factures, relances) + **Max** (tri de la boîte fournisseurs/experts, récap). Zoé : non pertinent.
- Ancre de prix (à faire dire avant tout prix Manda) : logiciel 140 € → 700 €/mois + une assistante 2 j/semaine.
- Deux flux distincts sous le même mot « garage » : **carrossier sous expertise** (un tiers valide) ≠ **mécanicien** (le particulier dit oui, paiement comptant à la restitution — l'angle « impayés » y est faible). Ne pas vendre « impayés » à un mécanicien.
- Angle interdit tant que CP-122/123 ne sont pas livrés : voir GUARDRAILS G10. Angle autorisé : « vos devis et factures suivis et relancés depuis votre boîte mail, sans changer de logiciel ».
- Canal : réseau direct (intros de Davy), FNA / Mobilians (fédérations MRA), groupes métier ; concurrence IA déjà présente sur la verticale (ne pas nommer).
- Segment écarté (non validé) : **IDEL** — tiers payant, canal non-mail.

## Objections types (à désamorcer, jamais ignorer)

1. « Encore un logiciel à apprendre » → Ce n'est pas un logiciel à configurer, c'est un assistant déjà formé.
2. « Mes données / celles de mes clients » → règle RGPD 2 niveaux (GUARDRAILS G5), DPA EU, révocable en un clic.
3. « L'IA va écrire n'importe quoi » → Vous validez tout ; rien ne part sans votre feu vert (vrai dans le produit : ADR-064).
4. « Pas le temps de mettre ça en place » → Vous décrivez votre activité, c'est tout. (Store, pas Builder.)
