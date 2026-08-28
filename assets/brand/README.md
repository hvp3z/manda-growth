# assets/brand — overlays fixes réutilisés sur toute vidéo Manda

Contrairement à `assets/founder/` (stock source qui change à chaque session de tournage), ce dossier contient des **overlays de marque fixes** : le même fichier est réutilisé tel quel sur chaque vidéo, tant qu'il n'est pas explicitement remplacé.

## Fichiers

- `outro-cta.png` — écran de fin (~2 secondes) à ajouter systématiquement à la fin de toute vidéo Manda (fondateur ou avatar). Fond crème, logo Manda officiel (`md-map/apps/configurator/public/manda-logo.svg`), tagline "Déléguez sans recruter.", bouton `manda.run →`, 4 points d'accent (Max/Zoé/Leo/Eli). Généré le 2026-08-27, validé par Matthieu.

## Règle

Toute vidéo Manda (mode A avatar généré ou mode B tournage réel + CapCut, voir `playbooks/founder-video.md` étape 8bis) doit se terminer par `outro-cta.png` affiché ~2s, et inclure une musique de fond sur toute sa durée (pas un asset fichier, à ajouter au montage). `playbooks/founder-video.md` est la source unique de vérité pour la procédure complète, quel que soit le mode.

Si l'outro est régénéré/mis à jour, remplacer ce fichier directement (pas de versionnage par date — un seul outro fait foi à la fois) et le signaler à Matthieu.
