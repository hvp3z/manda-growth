---
date: 2026-09-16
agent: matthieu
type: produit
statut: livré (CP-132 revu le 2026-09-16, validated après AC-11 en prod)
---

**Constat** : retour à chaud de Quentin (@bourr_, 260k, premier client Créateur, onboardé le jour même en mode révision) après la démo du tableau de bord Zoé Instagram.

1. **Les commentaires ignorés doivent rester sa décision en mode révision.** Aujourd'hui Zoé écarte seule (pas de texte, compte suspect, trop court, emoji seul, classé « à ignorer », hostile ou sensible selon les réglages) et le tableau de bord ne montre qu'un badge « Ignoré » dans l'activité, sans action. Quentin veut pouvoir, sur chacun : publier une réponse s'il en a envie, la modifier, ou confirmer « Ignorer ». Formule : « faut que ce soit lui qui décide ».
2. **Liker le commentaire depuis le tableau de bord**, placé en haut du cadre de la carte, pas au niveau des boutons Publier / Modifier / Rejeter.

**Analyse** :
- Le point 1 est le prolongement naturel d'ADR-074 (mode révision) : en révision, Zoé propose, le créateur dispose. Un commentaire écarté par Zoé sans que le créateur le voie contredit la promesse. Techniquement, la file « À valider » ne reçoit que les réponses générées : il faut une carte « Ignoré par Zoé » avec motif, réponse générée à la demande (« Répondre quand même »), édition libre, et « Ignorer » explicite. Les filtres mécaniques restent utiles en autonome : l'écart se joue par canal et par mode.
- Le point 2 bute sur l'API : l'Instagram API avec Instagram Login expose sur un commentaire lecture, réponse, masquage et suppression, **pas le like**. Le like n'est possible que dans Instagram. Le mieux faisable : un accès direct au commentaire (lien post + identifiant de commentaire, CP-131 a posé `post_url` et `comment_id`) en tête de carte, pour liker en un geste dans l'app. À dire à Quentin tel quel, plutôt qu'un bouton qui simule.

**Proposition** : CP « Révision complète » (B-26) : cartes « Ignoré par Zoé » actionnables en mode révision + accès direct au commentaire en tête de carte. Volet like natif : refusé pour cause d'API, ré-évaluer si Meta l'ouvre. Mesure de succès : part des « ignorés » que Quentin republie ou modifie sur ses deux premières semaines ; si elle est élevée, les filtres sont trop agressifs pour un compte à 260k et c'est un second signal.

**Inconnues à lever** : volume réel d'ignorés chez Quentin (à lire en base après 48 h), et s'il veut aussi voir les ignorés en mode autonome (probablement oui, en lecture).
