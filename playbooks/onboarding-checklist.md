# SOP — onboarding-checklist (accompagnement d'un Fondateur, v0)

**Agent** : client-ops (squelette) · S'active à la levée de #29, pour chaque Fondateur converti.

## Checklist par Fondateur (un fichier `campaigns/fondateurs/<prenom>.md`)

1. **Avant l'activation** : mail de bienvenue personnalisé (gabarit review-queue) · rappel de ce qui a été convenu au RDV (assistant, douleur, prix Fondateur) · créneau d'onboarding accompagné proposé.
2. **Activation (avec Matthieu en visio)** : compte créé · paiement Stripe Fondateur OK · connexion boîte mail OK (post-#29) · configuration business complétée (le client décrit, on s'occupe du reste) · premier livrable de l'assistant constaté EN SÉANCE (un récap, une relance préparée).
3. **J+7** : point 15 min — ce qui a servi, ce qui a surpris, ce qui manque. Verbatims → `memory/learnings/`.
4. **J+30** : **preuve ROI chiffrée** (décision #24) — temps gagné estimé (Max) ou relances envoyées + réponses obtenues (Eli). Consigner le chiffre + la citation client. Demander : « accepteriez-vous d'être cité ? »
5. Signal churn (silence, non-usage, déception) → `signals/` (type produit) immédiatement.

## Cas Créateur Instagram (tant que l'app Meta est en Standard Access, ADR-057)
- Le créateur doit être ajouté **et avoir accepté** l'invitation « Instagram Tester » de l'app Meta avant l'écran « Connecter un canal ». Une invitation envoyée n'est pas une invitation acceptée (session 36).
- L'acceptation se fait **uniquement sur Instagram web, sur ordinateur** (Paramètres → Autorisations des sites web → Invitations à tester). Dans l'app mobile, la section n'existe pas et un `pending` reste invisible ; Meta n'envoie aucun mail. Prévoir un ordinateur en séance (Quentin, 16/09).
- **Accord grammatical (ADR-098)** : à l'étape Contexte du premier assistant, le wizard demande « Vos assistants écrivent au : masculin / féminin / neutre » **si le compte ne l'a pas encore**. Vérifier en séance que la question apparaît, que la valeur est enregistrée (visible ensuite dans `/dashboard/account`) et qu'aucun autre wizard ne la redemande. Volet (3) d'AC-12 de CP-138, jamais observé en production : ce prochain onboarding en est la preuve.
- Vérifier avant la séance que l'invitation part bien depuis l'app Meta de Manda et vers le bon compte Instagram (un doublon `pending` sur un mauvais compte a coûté 20 minutes le 16/09 : expirer, supprimer, réinviter).

## Règle d'or
Les 10 Fondateurs ne sont pas des clients : ce sont les co-fondateurs de la preuve. Chaque friction qu'ils rencontrent est un signal prioritaire.
