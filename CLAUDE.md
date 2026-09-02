# manda-growth — OS Growth de Manda (business unit autonome)

> Espace opérationnel des agents growth de **Manda** (marketing · prospection · client ops).
> Repo indépendant du repo produit/stratégie. Ici on ne développe pas le produit : on le fait connaître et on le vend.

## 🚨 Avant TOUTE action — chargement obligatoire

Charge dans cet ordre, à chaque réveil de session ou d'agent :

1. @context/GUARDRAILS.md — les règles dures (bloquantes, jamais négociables)
2. @context/OFFER.md — ce qui est vendable AUJOURD'HUI (prix réels, exclusions)
3. @context/ICP.md — à qui on parle
4. @context/BRAND_VOICE.md — comment on parle
5. @context/ROADMAP_SNAPSHOT.md — ce qui arrive, ce qui est interdit de promesse
6. @memory/MEMORY.md — les règles apprises des corrections de Matthieu
7. @GOALS.md — le but et les objectifs de la semaine

Un agent qui produit un livrable sans avoir chargé GUARDRAILS.md est en faute — le livrable est invalide.

**Contrôle de fraîcheur (obligatoire au réveil)** : chaque fichier `context/` porte une date `sync:` en frontmatter.
Si la plus ancienne dépasse **14 jours**, ajoute en tête de chaque livrable du run : `⚠️ contexte non resynchronisé depuis <date> — vérifier OFFER/GUARDRAILS avant publication`, et note-le dans DAILY_LOG. Dans tous les cas : **ne jamais graver un prix dans un contenu evergreen** (article, page) — écrire « voir manda.run/pricing » ; les prix chiffrés ne sont admis que dans les contenus datés (posts) et proviennent d'OFFER.md.

## Boucle de travail (Observer → Penser → Agir)

1. **Observer** : lire GOALS.md, DAILY_LOG.md (dernières entrées), review-queue/ (verdicts et corrections).
2. **Penser** : choisir l'action au meilleur levier vers la north star (10 pré-payants Fondateur).
3. **Agir** : produire un **livrable FINI** (post prêt à publier, article complet, liste enrichie) — jamais un brouillon d'intention. Le coût marginal de complétude est ~zéro : livre le produit final.

## Où écrire quoi

| Contenu | Destination |
|---|---|
| Livrable en attente de validation Matthieu | `review-queue/` (1 fichier = 1 item, voir README du dossier) |
| Assets et résultats d'une campagne | `campaigns/<nom-campagne>/` (append-only) |
| Journal d'action quotidien | `DAILY_LOG.md` (1 ligne datée par action) |
| Constat stratégique (marché, pricing, produit, positionnement) | `signals/` + ligne dans `signals/INDEX.md` — **jamais** d'action directe sur le pricing/positioning |
| Enseignement de campagne (angle qui marche, taux) | `memory/learnings/` |
| Règle durable issue d'une correction | `memory/MEMORY.md` |

## Interdits structurels

- **Ne jamais modifier** les fichiers `context/*` en dehors de la SOP `playbooks/resync-context.md` — ce sont des dérivés datés de sources maîtres qui vivent ailleurs (sidecar Axiom, `/pricing` md-map, content-factory).
- **Ne jamais lire** le sidecar stratégique (`agent-md-framwork/_bmad/_memory/...`) ni `md-map/` — ton monde, c'est ce repo + `content-factory/` (lecture seule) pour la chaîne de rendu.
- Toute proposition touchant pricing, positionnement ou roadmap = un **signal** (`signals/`), jamais une action.

## Sources maîtres (lecture seule, chemins relatifs)

- Chaîne de rendu visuel : `../agent-md-framwork/content-factory/` (brand, fonts, templates, angles, visuels mineral-v1). Ce repo est le frère du parent sur les 3 postes : jamais de chemin absolu ici, il casserait les deux autres machines.
- Le reste du contexte t'arrive via `context/` — tu n'as pas besoin d'autres sources.
