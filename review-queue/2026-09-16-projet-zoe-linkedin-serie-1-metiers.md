---
date: 2026-09-16
agent: axiom
type: autre
statut: approved
verdict: "ok, avec les 4 arbitrages du §3 (session Axiom 37, 16/09)"
---

# Projet Zoé-LinkedIn « Manda par métier, série 1 » (dogfooding, compte matthieu.dbng@gmail.com)

> Ce fichier n'est pas un post. C'est le **projet de posts** que Zoé va recevoir (nom, angle, sources) et les
> quatre écritures prod qui l'accompagnent. **Exécutées en prod le 16/09/2026 (transaction unique, essai à blanc préalable)** :
> projet `c4da5948-e556-4c89-b8ac-4b7922393d4f`. Série générée le 16/09 à 20h08 par appel direct à l'API depuis la session Chrome de Matthieu (aucun bouton « Générer » n'existe sur un projet déjà créé : dette produit à scoper). 5 brouillons `pending_review`, créneaux 18/09 → 28/09 08:30. Revue Axiom : post 4 (carrousel) slide 7 promet un résultat au carrossier rencontré, qui n'est pas client (G10) : à corriger ou rejeter.
> Les 5 brouillons arrivent en **mode révision** (`pending_review`), créneaux proposés lun/mer/ven 08:30.

## 0. État du compte (lu en prod le 16/09)

| Élément | Valeur | Action |
|---|---|---|
| Client | `c56fe517-a193-44ab-8f0b-bbf08f202722`, actif, tier `pro`, modules eli/max/zoe | aucune |
| LinkedIn | connecté, jeton valable jusqu'au **27/10/2026** | reconnexion à prévoir fin octobre |
| Cadence | 3 posts/semaine (lun/mer/ven 08:30) | inchangée |
| Autonomie LinkedIn | **`autonomous: true`** | **→ passer en révision** (écriture 1) |
| Voix | audience « Garagistes, Electriciens, Indépendants, Freelancers », goals « expert IA », `examplePosts: []`, pas de `topicsToAvoid` | **enrichir** (écriture 2) |
| Projets existants | « l'IA pour les entrepreneurs » (3 posts `failed` du 28/07, hors ligne éditoriale) · « Lancement Fondateur » (1 publié) · test CP-123b (archivé) | archiver le premier (écriture 4, optionnelle) |

Contraintes produit qui ont dicté le découpage : un projet = **1 à 5 posts**, une seule série par génération, et les créneaux
sont calculés depuis « maintenant » sans regarder les autres projets (deux projets générés le même jour se disputent le
même lundi). Donc **un seul projet de 5 posts**, puis une deuxième série quand la file de révision est vidée.

## 1. Écritures prod (fichier `serie-1-metiers.sql`)

1. **Révision au lieu d'autonome** : `zoe_config.channels.linkedin.autonomous` → `false` (clé feuille, ADR-092).
   Motif : série sous guardrails (G2bis, G4, G7, G10), premiers posts métier, relecture obligatoire.
2. **Voix enrichie** (clés feuilles uniquement) :
   - `voice.examplePosts` = [le post Fondateur publié le 01/09] (seul post validé dans ta voix ; le writer s'en sert comme référence de ton).
   - `voice.topicsToAvoid` = liste des interdits growth (ci-dessous, §2 source A, bloc « Interdits »).
   - `voice.audience` → « Artisans et indépendants (carrossiers, tatoueurs), dirigeants de petites entreprises, comptables, créateurs de contenu ».
   - `voice.goals` → « Faire venir 10 Fondateurs sur manda.run/pricing en montrant des scènes de métier concrètes, jamais en parlant d'IA en général ».
   - `voice.sector` → « Assistants déjà formés pour indépendants et PME (Manda, Mine Digitale) ».
3. **Insertion du projet** (§2).
4. Archiver le projet « l'IA pour les entrepreneurs & Indépendants en 2026 » (3 échecs de juillet, ligne éditoriale abandonnée).

## 2. Le projet

**Nom** : `Manda par métier, série 1 : tatoueur, carrossier, créateur`
**Nombre de posts** : 5 · **Format** : texte (pas de carrousel)

**Angle** (texte transmis tel quel au ghostwriter) :

> Série de 5 posts, un métier ou une scène par post. Chaque post part d'une scène vécue, à une heure précise de la journée, où l'administratif prend la place du vrai métier. Toujours montrer ce que la personne fait à la place (le client au comptoir, la voiture sur le pont, la séance de tatouage, la vidéo à tourner), jamais « du temps libre » en abstrait. Dire « assistant », jamais « agent », « outil », « automatisation », « plateforme », « IA générative ». Manda n'apparaît qu'après la scène, en deux ou trois phrases, dans les mots exacts des sources (périmètre autorisé, rien d'autre). Répartition imposée : post 1 = pourquoi j'ai formé ces assistants (source A, histoire fondateur, à la première personne) ; post 2 = le devis qui n'arrive pas, vu du client qui attend (source B) ; posts 3 et 4 = le carrossier, deux angles distincts (source C : le soir à l'atelier fermé / la boîte mail pro qui déborde) ; post 5 = le créateur et ses commentaires (source D). Chaque post se termine par le CTA : pack complet Fondateur 34,50 €/mois pendant 12 mois au lieu de 69 €, 7 jours d'essai, manda.run/pricing, ou 15 minutes avec moi en message privé. Ne jamais inventer un chiffre, un nom ou un résultat absent des sources.

### Source A : Manda, ce que les assistants font vraiment (périmètre autorisé) + histoire fondateur

Matthieu Diabangouaya, fondateur de Mine Digitale, a formé trois assistants réunis sous la marque Manda. Ils sont déjà formés : le client décrit son activité, il ne configure rien, il n'apprend pas un logiciel.

- **Max** (email) : trie la boîte mail, envoie un récap matinal, prépare des brouillons de réponse que le client valide. Quand Max ne sait pas, il s'abstient et laisse la main.
- **Eli** (devis, factures, relances) : suit chaque devis et chaque facture depuis la boîte mail, sans changer de logiciel. Relance courtoise à J+7, relance ferme à J+15. Si une facture reste impayée, il prépare la mise en demeure ; rien ne part sans validation du client.
- **Zoé** (LinkedIn et Instagram) : sur LinkedIn, elle écrit des posts dans la voix du client, qui valide avant publication. Sur Instagram, elle garde le fil avec la communauté : réponses aux commentaires dans le ton du créateur, rien ne part sans son accord.

Offre : 29 € par mois par assistant, ou le pack complet (Max + Zoé + Eli, un seul tableau de bord) à 69 € par mois. Offre Fondateur : 10 places, le pack complet à 34,50 € par mois pendant 12 mois, 7 jours d'essai, sans engagement, sur manda.run/pricing. Le lancement Fondateur est ouvert depuis le 27 août 2026.

Histoire fondateur (faits) : Mine Digitale accompagne des petites entreprises depuis plusieurs années ; Matthieu a vu des artisans et des dirigeants faire leur administratif le soir, par petites touches, et repousser la relance « à vendredi ». Il a formé ces assistants pour que le métier reprenne la place de l'écran. Le premier client créateur a confié ses commentaires Instagram à Zoé cette semaine.

**Interdits (le post est refusé s'il en contient un)** : chiffres de marché ou statistiques externes · le mot « automatisation » · « agent », « outil », « plateforme », « configurer », « workflow », « IA générative » · tirets longs, demi-cadratins, flèches · Leo ou la prospection (n'existe pas encore) · « plus de capacité », quotas, paliers, « prix bloqué à vie », « code FONDATEUR » · promesse d'activation Instagram instantanée · « réponse automatique aux demandes de devis », « relance de l'expert », « recherche de pièces », « devis généré », tout chiffre de temps gagné · conformité e-facture · « vos données restent en Europe » · « sans supervision ».

### Source B : le devis qui n'arrive pas, vu du client (tatouage, vécu de Matthieu)

Matthieu prépare la suite de son tatouage : une manchette polynésienne à prolonger jusqu'à l'épaule, avec une bande noire, des écailles au coude et une désagrégation en pixels sur le biceps. Il a contacté plusieurs tatoueurs parisiens avec un projet précis, des photos et des références. Le premier a répondu pour décliner (projet trop géométrique pour lui). Pour les autres, il attend.

Ce qu'il constate : un tatoueur sait chiffrer une demande en quelques minutes (zone, taille, style, nombre de séances). Pourtant la demande attend, parce que le tatoueur est en séance toute la journée, que la demande est arrivée au milieu de trente autres messages, et que répondre demande de s'asseoir devant l'écran. Pendant ce temps, le client hésite, relance, ou va voir ailleurs. Aucun tatoueur n'est client de Manda : cette source est une scène vécue côté client, pas un cas client.

Ce que Manda fait pour un métier où les demandes arrivent par mail : Max trie les demandes et prépare une première réponse (accuser réception, demander la zone, la taille, les références, proposer un créneau d'échange) que le professionnel valide en une lecture ; Eli suit le devis envoyé et relance à J+7 si le client n'a pas répondu. Si les demandes arrivent en messages privés Instagram, Manda ne les traite pas aujourd'hui : ne pas le promettre.

### Source C : le carrossier (entretien terrain, fin août 2026, anonymisé)

Un carrossier indépendant rencontré fin août, repreneur d'un atelier. Une assistante deux jours par semaine, qui fait les factures et la TVA et doit lui faire valider chaque facture. Tout passe par la boîte mail pro : experts d'assurance, fournisseurs de pièces, constructeurs, plateformes. Son flux : il envoie le devis à l'expert d'assurance, l'expert valide, il facture. Le délai vit entre le devis envoyé et la validation de l'expert, et personne ne relance. Une demande de devis lui prend un quart d'heure, le temps de chercher les pièces.

Sa journée : les mains dans la carrosserie, sollicité au comptoir, le téléphone qui sonne. L'administratif se fait le soir, atelier fermé, par petites touches. Ce n'est pas un problème de rigueur : la relance est la seule tâche qu'on peut toujours repousser à demain. Son vrai travail, c'est la voiture et le client en face, pas l'écran.

Ce que Manda fait pour lui aujourd'hui, et rien de plus : ses devis et factures sont suivis et relancés depuis sa boîte mail, sans changer de logiciel (Eli) ; sa boîte est triée (experts, fournisseurs, constructeurs) avec un récap le matin (Max). Ne pas dire : relance automatique de l'expert, facture à émettre détectée, réponse automatique aux demandes de devis, recherche de pièces ou de prix, devis généré, temps gagné sur le devis. Ne jamais citer un logiciel ou un concurrent. Le paiement et l'encaissement ne sont jamais un sujet. Un carrossier sous expertise n'est pas un mécanicien : chez le mécanicien, le particulier paie à la restitution, l'angle « impayés » ne s'applique pas.

### Source D : le créateur et ses commentaires (premier client Créateur, onboardé le 16 septembre 2026)

Un créateur fitness, 260 000 abonnés Instagram. Il dit passer plusieurs heures par jour à répondre aux commentaires sous ses vidéos, parce que chaque commentaire sans réponse est une relation qui s'éteint, et que son métier c'est de tourner, pas de faire défiler. Il a confié ses commentaires à Zoé cette semaine, en mode révision : Zoé prépare les réponses dans son ton, il valide ou modifie en une lecture, et les commentaires que Zoé ne sait pas traiter restent sa décision, dans son tableau de bord. C'est trop récent pour annoncer un résultat : ne donner aucun chiffre de temps gagné, aucun avant/après.

Formulation autorisée pour Zoé Instagram : « Zoé garde le fil avec votre communauté Instagram, dans votre ton, rien ne part sans votre accord. » L'accès Instagram s'ouvre aujourd'hui avec un accompagnement à la main, jamais en libre-service instantané : ne pas promettre « connectez votre compte et c'est parti ».

## 3. Arbitrages Matthieu (16/09)

1. « Décolle-toi, action » : erreur de transcription, retirée du nom et de l'angle.
2. Post 1 fondateur : faits seulement.
3. Créateur (source D) : anonyme.
4. Projet de juillet : archivé.
