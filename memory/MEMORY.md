# MEMORY — Règles apprises (corrections humaines → règles durables)

> Protocole : chaque correction de Matthieu en review-queue est transformée ICI en règle durable par l'agent
> au run suivant (une correction = une règle, datée, avec la raison). On ne répète jamais une erreur corrigée.
> Les enseignements de campagne (angles, taux) vont dans `learnings/`, pas ici.

## Règles héritées des campagnes passées (seed 2026-07-28, source : mineral-v1 REPORT.md)

- **R-001** · Dire « récap », jamais « digest » — collision avec « Le Débrief » (accueil produit). *(v1.1, 2026-07-12)*
- **R-002** · Toutes les relances (devis, factures, impayés) s'attribuent à **Eli**, jamais à Max ni Leo. *(ADR-078)*
- **R-003** · Max n'envoie pas seul : « Vous validez. Max envoie. » — jamais de formulation d'envoi autonome. *(v1.1)*
- **R-004** · Ne pas inventer de tri « informatives/archivées » — la promesse réelle : « Le récap lit vos 30 emails. Vous lisez le récap. » *(v1.1)*
- **R-005** · Retouche visuelle = original validé en référence d'image, « reproduce EXACTLY, change only… ». *(v1.1b)*
- **R-006** · Préférer « Récupérez vos soirées » à « Reprenez vos matinées » — registre validé par Matthieu. *(v1.1)*

## Règles founder-video (Higgsfield / TTS)

- **R-007** · La synthèse vocale `seed_audio` (Higgsfield) peut manger des syllabes en français, même sur un script simple et correctement écrit (« déjà rédigés » entendu « déja récrilé », « qu'on en parle » entendu « qu'on en parlé »). Ce ne sont pas des fautes du script — c'est un défaut de prononciation du modèle, audible uniquement à l'oreille d'un francophone natif. **Toujours écouter la narration générée avant de l'utiliser pour la vidéo** (ne jamais enchaîner texte→audio→vidéo sans vérification à l'oreille) ; si des mots sont mangés, régénérer (nouvelle tentative aléatoire) et/ou baisser `speech_rate` (paramètre `generate_audio`, plage -50/+100, défaut 0) avant de relancer la génération vidéo coûteuse. *(2026-08-26, retour Matthieu sur la première vidéo fondateur)*
- **R-008** · Le modèle vidéo `seedance_2_5` (mode `omni_reference`) plafonne à **30s** et **rejette (422) toute requête où la durée de l'audio de référence dépasse ce plafond** — donc baisser `speech_rate` allonge la narration (ex. -5 → 33,4s, -3 → 31,4s, -2 → 28s) et peut faire sortir l'audio de la fenêtre utilisable ; toujours vérifier `durationSec` du job audio avant de le passer en référence vidéo, viser ≤ ~29s de marge. *(2026-08-27)*
- **R-009** · `seedance_2_5` (mode `omni_reference`) **ne supporte pas de combiner `video_references` (mouvement) et `audio_references` (voix/lipsync) dans la même génération** — 422 systématique quelle que soit la combinaison testée (confirmé avec plusieurs médias). Choix à faire à chaque fois : soit `image_references` + `video_references` (mouvement fidèle, mais audio généré par le modèle, pas notre script), soit `image_references` + `audio_references` (notre script/voix clonée, mouvement généré par le modèle à partir des images). Le playbook `founder-video.md` retient la seconde option par défaut (fidélité au script prime). *(2026-08-27)*
- **R-010** · **Recette de génération validée** pour la vidéo fondateur (à réutiliser telle quelle sur les prochains posts, pour ne pas regaspiller de crédits à re-découvrir ces réglages) :
  - Voix clonée une fois par session de tournage : `create_voice_from_confirmed_audio` sur `audio1-voice.*` → réutiliser le `voice_id` obtenu sur tous les scripts de la même session (pas besoin de re-cloner à chaque script).
  - Narration : `generate_audio`, modèle `seed_audio`, `voice_type: element`, `speech_rate: -2` (débit légèrement ralenti, meilleure diction FR sans dépasser la limite de durée — validé à l'oreille par Matthieu sur la 2ᵉ vidéo). **Toujours vérifier `durationSec` du résultat ≤ ~29s** (R-008) ; si le script est plus long/court, ajuster `speech_rate` par petits pas plutôt que de repartir de 0.
  - Vidéo : `generate_video`, modèle `seedance_2_5`, `mode: omni_reference`, `resolution: 720p`, `aspect_ratio: 9:16`, `duration` = durée exacte de l'audio généré. Médias : plusieurs `image_references` (4 photos face/¾ different angles ont donné un bon résultat) + 1 `audio_references` (le job de narration) — **jamais de `video_references` en même temps** (R-009).
  - Coût observé : ~3-4 crédits par variante de narration (cheap, itérer librement sur `speech_rate` avant de valider) + ~162-195 crédits pour la génération vidéo finale (25-30s, 720p, 9:16) — donc itérer sur l'AUDIO seul jusqu'à validation avant de lancer la vidéo, ne jamais regénérer la vidéo pour tester un réglage audio. *(2026-08-27)*

<!-- Nouvelles règles en dessous : R-007, R-008… format : **R-XXX** · règle · *(date, source de la correction)* -->
