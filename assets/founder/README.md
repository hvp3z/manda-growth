# assets/founder — stock source pour la vidéo mensuelle avatar parlant

Ce dossier contient le stock photo/vidéo/audio de Matthieu réutilisé par `playbooks/founder-video.md` pour générer l'avatar parlant via le MCP Higgsfield. Ce n'est **pas** un livrable (contrairement à `campaigns/`) : c'est une matière première réutilisée et mise à jour à chaque nouvelle session de tournage.

## Structure

```
assets/founder/
  session-AAAA-MM/
    image1-face.jpg      # still frame identité : visage net, face caméra, bien éclairé, expression neutre
    video1-motion.mp4     # 2-5s de mouvement naturel (parle/bouge), sans coupure ni mouvement de caméra brusque
    audio1-voice.wav      # voix propre, ≥2s, sans musique ni bruit parasite
```

- Nommage par **session de tournage**, pas par mois d'usage : un stock peut servir sur plusieurs mois si Matthieu ne retourne pas de nouveau footage.
- Noms de fichiers fixes (`image1-face.*`, `video1-motion.*`, `audio1-voice.*`) pour que le playbook les référence sans ambiguïté.

## Dernière session

`dernière session : (aucune pour l'instant — à mettre à jour au premier dépôt de stock par Matthieu)`

## Vie privée / droit à l'image

Ces fichiers contiennent l'image et la voix de Matthieu. Usage strictement interne à la génération de contenu de marque Manda (vidéos LinkedIn fondateur) :
- Jamais partagés ou réutilisés en dehors de ce repo et du MCP Higgsfield utilisé pour la génération.
- Jamais réutilisés pour un usage hors marque Manda.
- Si Matthieu retire son consentement ou quitte le projet, ce dossier est supprimé, pas archivé.

## Renouvellement

Si le stock d'une session a plus de ~6-12 mois, ou que la tenue/le contexte visuel ne correspond plus à la campagne en cours, le signaler à Matthieu (note dans le playbook, pas une étape bloquante).
