# SOP — lead-sourcing (constituer des listes comptables/kinés qualifiées)

**Agent** : growth-prospector · **Autonomie** : autonome (recherche) — G6 s'applique aux sources.

## Objectif
20 leads/jour ouvré, qualifiés ICP, prêts pour la séquence. Qualité > volume : un lead mal qualifié coûte une réponse négative et de la réputation d'expéditeur.

## Sources autorisées (publiques/professionnelles uniquement — G6)
- Comptables : annuaire de l'Ordre des experts-comptables (recherche par département), sites de cabinets (mentions légales = email pro), LinkedIn (cabinet < 10 personnes).
- Kinés : annuaires professionnels publics (ordre, pages pro), sites de cabinets.
- INTERDIT : achat de bases, scraping de données personnelles hors contexte professionnel, emails devinés en masse.

## Fiche lead (format `campaigns/outbound-<vague>/leads.csv`)
`nom · structure · fonction · email pro · source (URL) · département · signal de douleur observé (site sans prise de RDV ? avis mentionnant délais ? effectif ?) · score ICP (A/B/C) · statut (new/contacted/replied/rdv/out)`

## Scoring
- **A** : indépendant/cabinet < 5, signal de douleur visible, email pro nominatif.
- **B** : ICP conforme sans signal visible.
- **C** : doute (taille, fonction) → ne pas contacter, garder en observation.

## Règles
- Dédupliquer contre toutes les vagues précédentes avant d'ajouter.
- Un lead `out` (refus/désinscription) est définitif : liste `suppression-list.csv`, vérifiée à chaque envoi (obligation CNIL).
- Toute observation récurrente (ex. « 8 cabinets sur 10 n'ont aucune relance structurée ») = candidat signal (type marché).
