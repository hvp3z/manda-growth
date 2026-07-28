# SOP — daily-run (growth-marketer) : le standup quotidien

**Déclencheur** : run planifié (jour ouvré) ou invocation manuelle. Durée cible : un livrable fini par run.

## Séquence

1. **Observer** : charger CLAUDE.md (contexte complet) · lire GOALS.md · DAILY_LOG (5 dernières lignes) · review-queue (verdicts nouveaux ?).
2. **Traiter les verdicts d'abord** :
   - `corrected` → appliquer la correction, graver la règle en MEMORY.md (R-XXX), re-déposer si nécessaire.
   - `approved` → publier si palier libéré, sinon préparer le prêt-à-publier pour Matthieu ; archiver dans `done/` ; métriques → campaigns/.
3. **Produire l'action du jour** :
   | Jour | Action | Playbook |
   |---|---|---|
   | Lundi | Post LinkedIn (axe 1) | linkedin-post.md |
   | Mardi | Article SEO | seo-article.md |
   | Mercredi | Post LinkedIn (axe 2) | linkedin-post.md |
   | Jeudi | Veille concurrentielle + marché (WebSearch) → signaux si constat réel | — (sortie : signals/ et/ou memory/learnings/) |
   | Vendredi | Post LinkedIn (axe 3) + compilation `campaigns/WEEKLY.md` (métriques vs GOALS) | linkedin-post.md |
4. **Journaliser** : une ligne DAILY_LOG par action. Si un objectif GOALS est menacé (retard, blocage >48 h), le dire dans la ligne — pas d'alarmisme, un fait.
5. **S'arrêter** : un livrable fini + verdicts traités = le run est complet. Ne pas enchaîner d'actions non planifiées.

## Veille du jeudi — cadrage
Concurrents à suivre : Limova, Lindy, Zapier Agents, Make AI + tout entrant FR « assistant IA PME ». Chercher : pricing, positionnement, angles publicitaires. Un constat qui change quelque chose pour Manda = un signal (type marché) avec preuve (URL, capture de prix). Pas de signal « pour faire un signal ».
