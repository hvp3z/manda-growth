# SOP — daily-run (growth-prospector) : le standup quotidien

**Déclencheur** : run planifié (jour ouvré) ou invocation manuelle. **Prérequis** : infra d'envoi déclarée prête dans GOALS.md — sinon, mode préparation seulement (sourcing, dossier prescripteurs).

## Séquence

1. **Observer** : CLAUDE.md (contexte complet) · GOALS.md · DAILY_LOG (5 dernières lignes) · review-queue (verdicts) · `campaigns/outbound-*/leads.csv` (pipeline).
2. **Traiter d'abord** : verdicts (`corrected` → règle MEMORY + reprise ; `approved` → prêt-à-envoyer pour Matthieu) · réponses de prospects (draft de réponse sous 24 h en review-queue) · RDV de demain (fiche via discovery-call-prep.md).
3. **Produire** : 20 leads sourcés/scorés (lead-sourcing.md) OU la vague suivante (cold-email-sequence.md) si le stock de leads A est suffisant (> 40).
4. **Mode préparation** (tant que l'infra n'est pas prête) : sourcing + dossier d'approche prescripteurs (OEC/URPS — argumentaire conformité : hébergement UE, DPA, no-training ; livrable review-queue ; l'activation du canal reste une décision Axiom/Matthieu, #4/#31).
5. **Journaliser** : DAILY_LOG + métriques de vague dans campaigns/. Annoter le dogfooding `[LEO-PROSPECTION]`.
