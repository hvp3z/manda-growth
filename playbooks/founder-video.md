# SOP — founder-video (vidéo mensuelle avatar parlant de Matthieu, LinkedIn)

**Qui** : growth-marketer (script + génération) · Matthieu (tournage du stock source, validation review-queue, publication tant que G8 n'est pas libéré).
**Quand — déclencheur** : mensuel, non calé sur un jour fixe. Déclenché par Matthieu dès qu'un stock `assets/founder/` à jour existe, ou par growth-marketer s'il constate qu'aucune vidéo fondateur n'a été produite depuis > 30 jours et qu'un stock valide est déjà disponible (jamais d'auto-déclenchement s'il faut d'abord tourner du footage).
**Agent** : growth-marketer · **Autonomie** : script + génération autonomes, publication draft-review (G8, même palier que `linkedin-post.md`).
**Canal** : compte LinkedIn de Matthieu (voix du fondateur) — nouveau format sur le canal/axe déjà décidé, pas un nouveau canal.

## Objectif
Renforcer la voix fondateur sur LinkedIn avec un format vidéo mensuel, sans jamais tourner de nouvelles images à chaque fois : on réutilise le stock `assets/founder/` et on génère l'avatar parlant via le MCP Higgsfield. Le script parlé est un livrable copy à part entière : il respecte GUARDRAILS et BRAND_VOICE **avant** génération, pas après.

## Prérequis
Un stock valide dans `assets/founder/<session la plus récente>/` : `image1-face.*`, `video1-motion.*`, `audio1-voice.*` (voir `assets/founder/README.md`). Si absent ou trop ancien (> ~6-12 mois) : le signaler à Matthieu en note, continuer avec le stock existant s'il reste présentable — ce n'est pas une étape bloquante du playbook.

## Procédure

1. Charger le contexte (CLAUDE.md) + relire `memory/MEMORY.md` et les 5 derniers items review-queue (verdicts) — mêmes lectures que `linkedin-post.md` étape 1.

2. Choisir l'angle : alterner les 3 axes — **impayés/trésorerie (Eli)** · **temps/boîte mail (Max)** · **RGPD/confiance** — en s'appuyant sur `content-factory/angles/linkedin-bank-v0.md`. Ne pas répéter l'axe du dernier post texte NI celui de la dernière vidéo.

3. Écrire le script parlé (le livrable copy, avant toute génération) :
   - Format : 20-45 secondes à l'oral (~50-110 mots), ton « collègue fiable » de BRAND_VOICE — jamais un script qu'on ne dirait pas à voix haute.
   - Structure : hook (1 phrase, recadrage ou tension) → développement (2-4 phrases, le problème vu par un dirigeant) → CTA (depuis G1 levée le 2026-08-27 : **`manda.run/pricing`** en CTA principal — pack Fondateur 34,50 €/mois, essai 7 jours — et RDV 15 min en CTA secondaire pour celui qui hésite ; **il n'y a plus de liste d'attente/waitlist**, ne jamais l'écrire ni la dire ; jamais « connectez votre boîte » comme promesse d'activation instantanée hors produit).
   - Rédiger aussi la légende LinkedIn qui accompagnera la vidéo au post (2-4 lignes, complète le script sans le répéter mot pour mot).

4. Auto-contrôle GUARDRAILS sur le script **avant génération** (bloquant — un échec ici coûte cher après génération vidéo) :
   G1 (CTA `manda.run/pricing` en principal + RDV en secondaire, plus de waitlist, jamais « connectez votre boîte » comme activation instantanée) · G2 (Leo nommable comme futur seulement, jamais en tête) · G2bis (prix uniquement 29/69/129/34,50, aucun autre montant, pas de paliers) · G3 (pas de promesse conformité e-facture) · G4 (fonctionnalités réelles seulement) · G5 (RGPD deux niveaux, jamais « IA française/européenne ») · G7 (jamais « automatisation », aucun chiffre externe, jargon interdit) · G10 (si angle garage : rien au-delà d'Eli/Max existants tant que CP-122/123 ne sont pas livrés).
   Un échec = réécrire le script avant l'étape 5. Ne jamais générer une vidéo pour « corriger le texte après coup » — le script validé GUARDRAILS est la version qui part en génération.

5. Préparer les références à partir du stock `assets/founder/<session>/` :
   - Vérifier que les 3 fichiers sont lisibles et correspondent bien à Matthieu.
   - Uploader/confirmer les médias source : `media_upload` (ou `media_upload_widget`/`media_import_url` selon la source) puis `media_confirm` pour chacun des 3 assets.
   - Si une voix de synthèse alignée est nécessaire (au lieu de réutiliser `audio1-voice` tel quel) : `create_voice` ou `create_voice_from_confirmed_audio` à partir de l'audio confirmé, puis `list_voices` pour vérifier l'ID retenu.
   - **Écouter la narration générée avant de l'utiliser pour la vidéo** (R-007, `memory/MEMORY.md`) : `seed_audio` peut manger des syllabes en français même sur un script correct, défaut audible seulement à l'oreille. Si des mots sont mangés, régénérer (nouvelle tentative) et/ou baisser `speech_rate` (paramètre `generate_audio`, plage -50/+100) avant de lancer la génération vidéo (coûteuse). Ne jamais enchaîner texte → audio → vidéo sans cette vérification.
   - **Vérifier `durationSec` du job audio avant de le passer en référence vidéo** (R-008) : `seedance_2_5` plafonne à 30s et rejette (422) toute génération où l'audio de référence dépasse ce plafond. Baisser `speech_rate` (débit plus lent, meilleure diction) allonge la narration — viser ≤ ~29s de marge, quitte à remonter le `speech_rate` par petits pas (ex. -5 → -3 → -2) jusqu'à repasser sous le plafond sans perdre la qualité de diction validée à l'oreille.

6. Vérifier le workflow et le modèle avant de générer manuellement :
   - Appeler `get_workflow_instructions` (sans argument) pour voir le catalogue — vérifier s'il existe déjà un workflow « talking avatar »/UGC talking-head adapté avant de recomposer le prompt à la main.
   - Sinon, vérifier le modèle recommandé actuel avec `models_explore` (les modèles évoluent — Seedance 2.5 sert de référence à confirmer à l'exécution, jamais à figer en dur).

7. Génération vidéo (si pas de workflow prédéfini adapté) :
   - Config : durée = durée de l'audio de référence (≤ 30s, cf. R-008), 720p, **9:16** par défaut (LinkedIn mobile — préférer 16:9 seulement si le stock source est filmé en paysage).
   - **Reference binding — choix obligatoire (R-009)** : `seedance_2_5` en mode `omni_reference` ne supporte PAS de combiner `video_references` et `audio_references` dans la même génération (422 systématique). Par défaut, privilégier **image(s) + audio** (fidélité au script/voix validés, le modèle génère lui-même le mouvement à partir des images) plutôt que image + vidéo de mouvement + audio. N'utiliser `video_references` que si l'on accepte que le modèle génère son propre audio (pas notre script).
   - Prompt structuré : [Matthieu, fondateur, plan buste face caméra] + [parle directement à la caméra, ton posé et direct] + [caméra fixe, léger zoom avant très lent] + [éclairage naturel doux, cohérent avec l'image/les images de référence] + [garder l'identité faciale et la voix strictement fidèles aux références, pas de dérive de traits sur la durée].
   - Negative prompt : dérive faciale, changement de décor, visage flou, bouche désynchronisée, artefacts, changement de tenue, arrière-plan instable.
   - Lancer avec `generate_video` (ou `generate_video_batch` pour tester plusieurs variantes en parallèle), suivre avec `job_status`/`jobs_wait`, récupérer avec `show_generations`/`reveal_generation`.

8. Contrôle qualité et troubleshooting avant dépôt review-queue :
   - Dérive faciale sur la durée → relancer en réduisant l'influence de la référence vidéo (mouvement) et en renforçant la référence image (identité).
   - Lipsync imparfait → vérifier que l'audio est propre (pas de bruit de fond) et que l'image de référence a la bouche fermée ou légèrement entrouverte (pas grande ouverte) comme point de départ.
   - Erreur content-policy → revérifier que le visage correspond bien à Matthieu, aucune ressemblance de tiers/célébrité involontaire.
   - Si upscale nécessaire pour la qualité finale LinkedIn : `upscale_video`.

9. Déposer en `review-queue/` avec `type: video-linkedin` (voir `review-queue/README.md`) :
   - `asset:` chemin vers le fichier vidéo généré (ex. `content-factory/output/founder-video/AAAA-MM-slug.mp4`).
   - Script parlé intégral, légende LinkedIn, description du plan/visuel en 2-3 lignes.
   - Nom du fichier review-queue : `AAAA-MM-JJ-founder-video-<slug-angle>.md`.

10. Ligne DAILY_LOG :
    `AAAA-MM-JJ · growth-marketer · Vidéo fondateur (axe <impayés/temps/rgpd>, stock assets/founder/session-AAAA-MM) déposée en review-queue · review-queue/AAAA-MM-JJ-founder-video-<slug>.md`

11. Au run suivant, si `approved` : publier (Matthieu tant que le palier de 10 publications sans correction n'est pas libéré, comme pour `linkedin-post.md`), archiver l'item dans `done/`, mettre à jour `campaigns/linkedin-organique/results.md` avec les métriques vidéo (vues, complétion si disponible, en plus des métriques post standard).

## Qualité
Une bonne vidéo fondateur Manda se reconnaît : le script pourrait être lu à voix haute et publié tel quel comme post texte s'il n'y avait pas de vidéo — la vidéo est un format, pas une excuse pour relâcher la discipline GUARDRAILS/BRAND_VOICE. Si le script n'aurait pas passé le contrôle d'un post `linkedin-post.md`, il ne passe pas ici non plus.
