---
date: 2026-08-26
agent: growth-marketer
type: video-linkedin
statut: pending
verdict: "[v1] Script et visuel OK, mais la synthèse vocale (seed_audio) mange certains mots : \"déjà rédigés\" entendu \"déja récrilé\", \"qu'on en parle\" entendu \"qu'on en parlé\". Coquilles audibles pour un francophone natif, à corriger avant publication — regénérer la narration (débit plus lent / nouvelle tentative) et vérifier à l'oreille avant de relancer la vidéo."

🚨 **BLOCAGE PUBLICATION (2026-08-27, découvert après le verdict "rendu final bon" de Matthieu)** : `context/GUARDRAILS.md` a été resynchronisé par Axiom pendant cette session — **G1 est levée** (lancement Fondateur ouvert), le CTA change : `manda.run/pricing` en principal, RDV en secondaire, **la liste d'attente Fondateur n'existe plus** (SIG-001 caduc). Le script écrit ci-dessous ET **l'audio parlé de la vidéo v2 elle-même** disent « rejoignez la liste d'attente Fondateur » — texte maintenant caduc, **gravé dans l'audio, non corrigeable sans régénérer** la narration + la vidéo. Matthieu a validé le *rendu* (qualité visuelle/vocale) avant que ce changement de contexte soit visible ici — **ne pas publier tel quel**. Prochaine étape : régénérer la narration avec le nouveau CTA (« l'offre Fondateur est sur manda.run/pricing — ou réservez 15 minutes ») à `speech_rate -2` (recette validée, R-010) et relancer une v3.

**Suivi (2026-08-26/27)** : narration régénérée en 2 variantes (`speech_rate` -15 et -5) avec la même voix clonée. **Matthieu valide la version débit -5** (job `c6493b0c-8957-45fa-b4c6-ce91ec7d5f1d`, wav : `https://d8j0ntlcm91z4.cloudfront.net/user_3GAXiyw1licuNeQS4o1GeTHuyba/hf_20260827_073925_c6493b0c-8957-45fa-b4c6-ce91ec7d5f1d.wav`) — c'est celle-ci qui doit servir de référence audio à la prochaine génération vidéo.

**✅ Vidéo v2 générée (2026-08-27), en attente du verdict final Matthieu.** `asset:` `campaigns/linkedin-organique/founder-video/2026-08-video-max-temps-v2.mp4` (720p, 9:16, 28s).

- Stock source mis à jour par Matthieu : 4 photos identité (`image1-face.png` → `image4-face.png`) + `video1-motion.mp4` retravaillé (<30s, nouveau décor).
- **Découverte technique (R-009, memory/MEMORY.md)** : `seedance_2_5` ne supporte pas de combiner référence vidéo (mouvement) et référence audio (notre narration) dans la même génération — 422 systématique, confirmé sur plusieurs combinaisons. Choix fait : **4 images + audio** (fidélité au script/voix prime sur la fidélité gestuelle à `video1-motion`).
- **Découverte technique (R-008)** : `seedance_2_5` plafonne à 30s ; la narration débit -5 validée précédemment durait 33,4s (hors plafond). Rendu en descendant le débit par paliers : -5 (33,4s) → -3 (31,4s) → -2 (28s, **validé par Matthieu comme la meilleure prise à l'oreille**). C'est cette narration (`speech_rate -2`, job `bf6f8ab7-dd98-45fa-b7aa-b3dfe1d91a2e`) qui a servi de référence audio à la vidéo v2.
- Coût cumulé de cette itération (hors la toute première génération) : ~4 tests audio courts + génération finale vidéo (~162 crédits) + 2 générations vidéo de test qui ont échoué en 422 (facturées ~0, échec avant rendu) + 1 test image+vidéo réussi (~65 crédits, exploratoire).
---

**Vidéo générée.** `asset:` `campaigns/linkedin-organique/founder-video/2026-08-video-max-temps.mp4` (720p, 9:16, 25s).

⚠️ **Limite technique à noter avant validation** : la référence vidéo de mouvement (`video1-motion.mov`) a dû être abandonnée — Higgsfield renvoyait une erreur 422 dès qu'elle était incluse (probablement trop longue par rapport aux 2-5s recommandés par la méthodologie source ; le fichier source fait plusieurs dizaines de Mo). La vidéo a donc été générée à partir de **image + audio (voix clonée) uniquement**, sans référence de mouvement dédiée — le modèle anime lui-même l'image de départ à partir du script audio. À vérifier au visionnage : la gestuelle/les mouvements naturels peuvent être moins fidèles à Matthieu que si `video1-motion` avait pu être utilisée. Si le rendu ne convient pas, il faudra retourner un extrait de 2-5s (pas plus) pour la prochaine session.

La voix a été clonée depuis `audio1-voice.MP3` (Higgsfield `create_voice_from_confirmed_audio`, voice_id `e521de16-53c9-48e5-a21a-039341341e0a`), puis la narration a été générée en TTS avec cette voix à partir du script ci-dessous (`seed_audio`, 24,5s) — c'est cet audio qui a servi de référence de lipsync pour la vidéo.

## Angle retenu

**Temps / boîte mail (Max).** Le dernier post texte en review-queue (`2026-07-28-post-linkedin-eli-impayes.md`) portait sur l'axe impayés/trésorerie (Eli) ; première vidéo fondateur, pas de répétition d'axe vidéo à éviter, mais on évite bien de répéter l'axe du dernier post texte.

## Script parlé intégral (20-45s à l'oral, ~95 mots)

Ce matin, avant même votre café, votre boîte mail avait déjà décidé de votre journée.

C'est ce qui m'a poussé à créer Max. Chaque matin, il lit vos emails et vous prépare un récap clair, avec des brouillons de réponse déjà rédigés. Vous, vous validez — rien ne part sans votre feu vert.

Vous récupérez le temps que la boîte mail vous prenait. Pas une minute de plus à trier.

Si vous voulez qu'on en parle, réservez 15 minutes avec moi — ou rejoignez la liste d'attente Fondateur, le lien est en commentaire. *(⚠️ texte original — CTA caduc depuis G1 levée le 2026-08-27, voir blocage en tête de fichier ; nouvelle formulation à utiliser pour la v3 : « l'offre Fondateur est sur manda.run/pricing — ou réservez 15 minutes avec moi si vous préférez en parler d'abord ».)*

## Légende LinkedIn

Chaque matin, ma boîte mail décidait de ma journée avant même que j'aie ouvert les yeux.

Max, c'est l'assistant que j'aurais aimé avoir en premier : il trie, il résume, il prépare vos réponses — vous, vous validez.

15 minutes pour en parler, ou la liste d'attente Fondateur en commentaire. *(⚠️ idem — à remplacer par : « L'offre Fondateur est sur manda.run/pricing, ou 15 minutes pour en parler d'abord. »)*

## Description du plan / visuel (2-3 lignes)

Plan buste, Matthieu face caméra, ton posé et direct, léger zoom avant très lent, caméra fixe, éclairage naturel doux cohérent avec `assets/founder/session-2026-08/image1-face.jpeg`. Généré en 720p, 9:16 (LinkedIn mobile), 25s, modèle `seedance_2_5` (mode `omni_reference`).

## Auto-contrôle GUARDRAILS (fait avant génération)

- **G1** — CTA = RDV découverte 15 min / waitlist Fondateur. Aucune mention « connectez votre boîte » ni activation immédiate. OK.
- **G2** — Leo non mentionné. OK.
- **G2bis** — aucun prix cité (pas nécessaire à cet angle). OK.
- **G3** — aucune promesse de conformité e-facture. OK.
- **G4** — fonctionnalités citées (tri email, récap matinal, brouillons validés par le client) toutes réelles et livrées. « Récap » utilisé, jamais « digest » (R-001). Envoi toujours validé par le client, jamais autonome (R-003). OK.
- **G5** — aucun claim RGPD/souveraineté dans ce script (angle temps, pas confiance). OK.
- **G7** — aucun « automatisation », aucun chiffre externe, aucun jargon interdit. OK.
- **G10** — non pertinent (angle Max/temps, pas garage).

## Journal d'exécution technique (pour mémoire)

1. Upload + confirm des 3 fichiers `assets/founder/session-2026-08/` (image, vidéo, audio) via `media_upload`/`media_confirm`.
2. Clonage voix (`create_voice_from_confirmed_audio`) à partir de l'audio confirmé → `voice_id e521de16-53c9-48e5-a21a-039341341e0a`.
3. Génération de la narration TTS du script ci-dessus avec cette voix (`generate_audio`, modèle `seed_audio`) → 24,5s.
4. `get_workflow_instructions` interrogé : aucun workflow catalogue Higgsfield ne correspond exactement à « avatar parlant à partir de son propre stock image+vidéo+audio » (le plus proche, `narrator`, est pour composer un narrateur sur une vidéo existante, pas pour générer une nouvelle vidéo depuis des références — non retenu).
5. `models_explore` confirme `seedance_2_5` (mode `omni_reference`, medias roles `image_references`/`video_references`/`audio_references`, durée 4-30s, résolutions 480p/720p/1080p) comme modèle pertinent.
6. Génération vidéo (`generate_video`) avec image + audio narration ; la référence vidéo de mouvement a dû être retirée (422 systématique avec elle incluse, voir note en tête de fichier).
7. Coût : ~3,4 crédits (narration) + 162,5 crédits (vidéo) = ~166 crédits sur 890,6 disponibles.
