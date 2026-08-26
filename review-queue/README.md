# review-queue — File de validation humaine

**Rituel Matthieu : 15 min/jour.** Ouvrir les fichiers `pending`, écrire le verdict dans le frontmatter, c'est tout.

## Format d'un item (1 fichier = 1 livrable)

Nom : `YYYY-MM-DD-slug.md` — frontmatter :

```yaml
---
date: 2026-07-28
agent: growth-marketer
type: post-linkedin | article-seo | sequence-email | page | video-linkedin | autre
statut: pending        # pending → approved | corrected | rejected
verdict: ""            # rempli par Matthieu : "ok publie" / la correction / le motif du rejet
---
```

Corps = le livrable FINI, prêt à publier tel quel.

**Cas d'un livrable vidéo (`type: video-linkedin`)** : le corps du fichier `.md` n'est pas la vidéo elle-même — c'est la fiche de publication :
- `asset:` chemin exact vers le fichier vidéo généré (ex. `content-factory/output/founder-video/2026-08-video-eli.mp4`)
- le script parlé intégral (texte prononcé, ligne par ligne)
- la légende LinkedIn qui accompagne la vidéo au post
- une description du visuel/plan en 2-3 lignes (ce qu'on voit à l'écran)

Le fichier vidéo lui-même n'est jamais déposé dans `review-queue/` (poids, binaire) : Matthieu valide sur la base du script + une prévisualisation de l'asset généré, puis écrit son verdict dans le `.md` comme d'habitude.

## Règles

- **Agents** : déposer ici tout livrable soumis à validation (échelle d'autonomie, GUARDRAILS G8). Ne jamais publier un item non `approved`.
- **Matthieu** : `approved` = l'agent publie au run suivant (ou toi directement — le noter dans verdict) · `corrected` = écrire la correction dans `verdict`, l'agent applique ET grave une règle dans `memory/MEMORY.md` · `rejected` = motif dans `verdict`.
- Item traité (publié/clos) → l'agent le déplace dans `done/` avec une ligne dans DAILY_LOG.
- Item `pending` > 48 h : l'agent passe à autre chose (G9), sans relance.
- Compteur de libération : 10 publications consécutives `approved` sans correction → la publication LinkedIn/SEO passe en autonome (mise à jour de GUARDRAILS G8 par Matthieu/Axiom, pas par l'agent).
