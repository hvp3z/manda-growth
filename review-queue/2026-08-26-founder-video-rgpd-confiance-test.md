---
date: 2026-08-26
agent: growth-marketer
type: video-linkedin
statut: pending
verdict: ""
---

**Script de test — vidéo NON générée** (déposé à la demande de Matthieu pour tester un second angle, en parallèle de `2026-08-26-founder-video-max-temps.md`). Génération à lancer seulement si demandé.

## Angle retenu

**RGPD / confiance.** Alternance avec les 2 items déjà en review-queue : dernier post texte = impayés/Eli, dernière vidéo = temps/Max → RGPD/confiance est l'axe qui n'a pas encore été utilisé récemment.

## Script parlé intégral (20-45s à l'oral, ~90 mots)

Vos clients vous confient leurs informations les plus sensibles. Vous ne pouvez pas vous permettre de les confier n'importe où.

C'est pour ça qu'avec Manda, vos données sont stockées en Europe, sur nos serveurs. Et le traitement par l'intelligence artificielle est encadré par un contrat de protection des données européen — rien ne sert à entraîner quoi que ce soit, rien n'est conservé au-delà du nécessaire.

Vous gardez la main : rien ne part sans votre validation.

Si la confidentialité de vos données est un sujet pour vous, l'offre Fondateur est sur manda.run/pricing — ou réservez 15 minutes avec moi si vous préférez en parler d'abord.

## Légende LinkedIn

Vos clients vous confient leurs informations les plus sensibles.

Chez Manda : données stockées en Europe, traitement IA encadré par un contrat de protection des données européen, aucun entraînement sur vos contenus. Et vous validez tout avant que ça parte.

L'offre Fondateur est sur manda.run/pricing, ou 15 minutes pour en parler d'abord.

## Description du plan / visuel (2-3 lignes)

Plan buste, Matthieu face caméra, ton posé et direct, léger zoom avant très lent, caméra fixe, éclairage naturel doux — même traitement visuel que la première vidéo (`2026-08-video-max-temps.mp4`) pour rester cohérent stylistiquement. Références prévues : `assets/founder/session-2026-08/image1-face.jpeg` (identité) + voix clonée `e521de16-53c9-48e5-a21a-039341341e0a` (déjà créée lors de la première génération, réutilisable directement sans re-cloner).

## Auto-contrôle GUARDRAILS (fait avant toute génération)

- **G1** — CTA principal `manda.run/pricing`, RDV 15 min en secondaire (règle G1 mise à jour le 2026-08-27 : lancement ouvert, plus de waitlist). Aucune mention « connectez votre boîte » ni activation instantanée hors produit. OK.
- **G2** — Leo non mentionné. OK.
- **G2bis** — aucun prix cité. OK.
- **G3** — aucune promesse de conformité e-facture. OK.
- **G4** — « vous gardez la main : rien ne part sans votre validation » : affirmation générique de contrôle utilisateur, cohérente avec le produit réel (ADR-064), ne décrit aucune feature non livrée. OK.
- **G5** — **règle des deux niveaux respectée et jamais amalgamée** : niveau 1 (stockage : « vos données sont stockées en Europe, sur nos serveurs ») et niveau 2 (traitement : « le traitement par l'intelligence artificielle est encadré par un contrat de protection des données européen — rien ne sert à entraîner ») écrits comme deux phrases distinctes, pas de « vos données restent en Europe » générique qui mélangerait les niveaux. **Aucun claim « IA française » ou « souveraine »** (ADR-085 non livrée) — non écrit. OK.
- **G7** — aucun « automatisation », aucun chiffre externe. Jargon vérifié : ni « IA générative », ni « LLM », ni « RAG », ni « plateforme », ni « configurer », ni « workflow », ni « n8n » — « intelligence artificielle » utilisé (autorisé, différent de « IA générative »). OK.
- **G10** — non pertinent (angle RGPD, pas garage).

## Note

Script uniquement — pas de génération vidéo tant que non demandée explicitement. Si validé, la génération peut réutiliser la voix déjà clonée (`voice_id e521de16-53c9-48e5-a21a-039341341e0a`) sans repasser par `create_voice_from_confirmed_audio`, ce qui réduit le coût par rapport à la première vidéo.
