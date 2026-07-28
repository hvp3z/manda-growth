# manda-growth — OS Growth de Manda

Repo opérationnel des agents growth (marketing · prospection · client ops). Conçu le 2026-07-28 (Axiom + Matthieu).
Point d'entrée agents : `CLAUDE.md` · Règles dures : `context/GUARDRAILS.md` · But : `GOALS.md`.

## Lancer un agent à la main

Ouvrir une session Claude Code **dans ce dossier**, puis :
- « Lance le daily-run du growth-marketer » (ou invoquer l'agent `growth-marketer` directement)
- « Lance le daily-run du growth-prospector » (inactif tant que l'infra d'envoi n'est pas prête — voir GOALS.md)

## Runs quotidiens automatiques (à activer par Matthieu quand les dry-runs sont validés)

Deux options équivalentes :

**Option A — cron Claude Code** : dans une session ouverte dans ce dossier, demander :
« Crée un cron qui exécute chaque jour ouvré à 7h30 : *Lance le daily-run du growth-marketer (playbooks/daily-run-marketer.md)* ».

**Option B — Tâche planifiée Windows** (headless) :
```powershell
schtasks /create /tn "manda-growth-marketer" /sc weekly /d MON,TUE,WED,THU,FRI /st 07:30 /tr "cmd /c cd /d C:\Users\matdi\Documents\myApps\Agents\manda-growth && claude -p \"Lance le daily-run du growth-marketer en suivant playbooks/daily-run-marketer.md\" --permission-mode acceptEdits"
```
*(même modèle pour `manda-growth-prospector` quand la Phase 2 s'ouvre)*

## Le rituel humain (15 min/jour)

1. Ouvrir `review-queue/` → verdict sur chaque `pending` (approved / corrected + texte / rejected + motif).
2. Jeter un œil à `DAILY_LOG.md` (30 s).
3. C'est tout — les corrections deviennent des règles toutes seules au run suivant.

## Liens avec la stratégie (Axiom, repo agent-md-framwork)

- **Montant** : `signals/` — constats des agents, triés par Axiom à chaque activation.
- **Descendant** : `context/` — dérivés datés des sources maîtres, resynchronisés via `playbooks/resync-context.md` (déclencheur : validation d'un CP touchant du vendable).
