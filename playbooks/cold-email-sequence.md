# SOP — cold-email-sequence (séquence 3 touches, mode pré-vente)

**Agent** : growth-prospector · **Autonomie** : rédaction autonome · **ENVOI : validation Matthieu obligatoire, sans exception (G6/G8)**.

## Prérequis infra (actions Matthieu — rien ne part avant)
Domaine d'envoi dédié (ex. `getmanda.fr`) · SPF + DKIM + DMARC configurés · warm-up 2-3 semaines · outil d'envoi tranché · boîte de réception relevée (les réponses sont le produit de ce playbook).

## La séquence (objectif : RDV 15 min OU inscription waitlist — JAMAIS « connectez votre boîte », G1)

- **T1 (J0)** — l'observation. Objet lié à la fonction (ex. « relances d'honoraires » / « votre boîte mail entre deux patients »). 4-6 lignes : une observation spécifique au métier du destinataire, une question, pas de pitch produit. Signature claire (Matthieu, Manda, adresse, lien désinscription).
- **T2 (J+4)** — la valeur. Un conseil actionnable immédiatement (ex. le calendrier de relance J+7/J+15 en 3 lignes), puis une ligne sur ce que Manda fait de ce problème. CTA : RDV 15 min.
- **T3 (J+9)** — la porte ouverte. Court (3 lignes) : offre Fondateur (10 places, −50 %), lien waitlist, « et sinon, bonne continuation » — on clôt proprement, pas de culpabilisation.

## Règles d'écriture
Ton BRAND_VOICE (calme, direct, zéro jargon G7) · un email = un seul CTA · personnalisation réelle (métier + signal observé dans la fiche lead), jamais de fausse familiarité · mise en demeure mentionnée uniquement avec « vous validez » (G4) · RGPD : niveau 1 et 2 jamais mélangés si le sujet vient (G5).

## Mécanique
1. Rédiger la vague complète (20 leads max) : chaque email personnalisé, dans `review-queue/` (type `sequence-email`, un fichier par vague avec les 20 × T1).
2. Après validation : Matthieu (ou l'outil) envoie. Statuts mis à jour dans `leads.csv`.
3. Réponses : chaque réponse est traitée sous 24 h (draft de réponse en review-queue) ; positif → `playbooks/discovery-call-prep.md`.
4. Métriques par vague dans `campaigns/outbound-<vague>/results.md` : envoyés, ouvertures (si dispo), réponses, RDV, désinscriptions. **> 5 % de réponses = angle validé ; < 2 % après 2 vagues = changer d'angle et le documenter en learning.**

## Dogfooding (obligatoire)
Chaque élément de ce playbook exécuté à la main est annoté `[LEO-PROSPECTION: exigence O/N + note]` dans les rapports de vague — c'est la matière première du brief produit Leo-Prospection (septembre).
