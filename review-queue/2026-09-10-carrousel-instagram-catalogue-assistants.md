---
date: 2026-09-10
agent: axiom
type: autre
sous-type: carrousel-instagram
statut: pending
verdict: "Matthieu 2026-09-10 (via session Axiom) : structure approuvée. Couverture = Max, Zoé, Eli + Leo en « Bientôt » (pas Sage/Iris). Hook = tagline « Déléguez sans recruter. ». Publication lundi 14/09 12h15 puis épinglage (la story Eli tourne jusqu'au 11/09 midi, pas de bruit avant). Visuels : recherche design carrousel demandée AVANT le rendu."
etape: "VISUELS v2 RENDUS le 10/09 après revue Matthieu (logo canonique par programme, noms centrés, Leo en dernier, finale sans « Essai 7 jours » ni mention offre) (content-factory/output/catalogue-v1/c1-s1..s5.png, REPORT.md) ; attend le verdict visuel de Matthieu, puis programmation lundi 14/09 12h15 + épinglage content-factory (5 slides 4:5, base visuelle b5.png pour la couverture)"
origine: "remarque de la femme de Matthieu (10/09) : aucune image ne montre ce qui est disponible chez Manda"
usage: "post ÉPINGLÉ en haut du profil bonjour.manda ; passe avant le carrousel Zoé (2026-09-10-carrousel-instagram-zoe-3-slides.md, parked)"
recherche: memory/learnings/2026-09-10-instagram-carousel-hooks-cta.md
---

**Carrousel catalogue, 5 slides.** La vitrine du Store : ce qui est disponible, un assistant par slide, l'offre en dernier. Vouvoiement, zéro emoji sur les visuels, zéro tiret long, **aucun prix sur les slides** (post épinglé = contenu qui dure ; prix dans la légende uniquement, règle CLAUDE.md).

**Système commun (itéré avec Matthieu le 10/09)** : 1080×1350 · fond sable `#FFF8F3` · marges 90 px, rien d'important dans la bande basse de 90 px · **header = logo Manda SVG canonique seul, en haut à gauche** (jamais le mot en typographie, aucun label à côté ni dessous) · **aucune pagination sur les visuels** (Instagram affiche la sienne) · une seule couleur d'accent par slide (celle de la pierre), reprise sur le nom uniquement · pied : `manda.run` en mono, petit.

## 1/5 — couverture (base : b5.png, les 4 pierres, nommées)

- Titre Plus Jakarta ~84 px : **Vos assistants sont prêts.**
- Sous-titre serif italique ~36 px : *Ils connaissent déjà votre métier.*
- Bande des quatre pierres au tiers bas (~180 px chacune) ; sous chaque pierre, mono 22 px, **nom seul** : MAX (corail) · ZOÉ (violet) · ELI (bleu) · LEO (terre cuite, pierre et nom atténués à 50 %, mention « bientôt » en dessous en 18 px)
- Chevron fin en bas à droite comme signal de swipe

## 2/5 — Max (pierre corail `#FF6248`, seule, centrée ~500 px)

- Nom 64 px corail : **Max**
- Rôle serif italique 32 px : *votre boîte mail.*
- Preuve 28 px : Chaque matin : un récap clair, vos mails triés, vos réponses préparées. Vous validez.

## 3/5 — Zoé (pierre violette `#9B59B6`)

- Nom 64 px violet : **Zoé**
- Rôle serif italique 32 px : *elle tient vos réseaux.*
- Preuve 28 px : Vos posts LinkedIn dans votre voix, vos commentaires Instagram suivis. Vous gardez le dernier mot.

## 4/5 — Eli (pierre bleue `#2C4A7C`)

- Nom 64 px bleu : **Eli**
- Rôle serif italique 32 px : *vos devis et vos factures.*
- Preuve 28 px : Il les suit depuis votre boîte mail et relance au bon moment. Vous validez.

## 5/5 — offre (FOND SOMBRE `#0E1912`, logo sombre, les trois pierres vendables regroupées en grappe, Leo absent ; décision Matthieu 10/09 : ne pas répéter l'écran de couverture)

- Titre : **Choisissez où récupérer votre temps.**
- Sous-titre serif italique : *Un assistant, ou le pack complet sur un seul tableau de bord.*
- Pied : `manda.run` (décision Matthieu 10/09 : ni « Essai 7 jours », ni mention offre sur le visuel)
- Pas de « sauvegardez », pas de prix, pas de bandeau.

## Légende

Le catalogue Manda en cinq images. Sauvegardez-le, vous le retrouverez quand la boîte mail débordera.

Max lit vos emails et prépare vos réponses. Zoé écrit vos posts LinkedIn et Instagram dans votre voix. Eli suit vos devis et vos factures et relance pour vous. Chacun fait son travail, vous validez, rien ne part sans vous.

Un assistant : 29 €/mois. Le pack complet Max + Zoé + Eli : 69 €/mois, et 34,50 €/mois pendant 12 mois pour les 10 premiers Fondateurs (−50 %). Essai 7 jours : manda.run/pricing, lien en bio. Une question ? Écrivez-nous en message privé.

#assistant #independants #pme #freelance #entrepreneur

## Auto-contrôle GUARDRAILS

- **G1** ✅ CTA pricing en légende + DM.
- **G2** ✅ Leo = « Bientôt, prospection » sur la couverture seulement, aucune slide, aucune date.
- **G2bis** ✅ prix d'OFFER.md uniquement, en légende seulement ; « chaque assistant reste complet » respecté (aucun retrait, aucun quota).
- **G3** ✅ zéro e-facture.
- **G4** ✅ Max : tri, récap, brouillons validés · Zoé LinkedIn : ghostwriter validé · Zoé Instagram : promise sur décision Matthieu du 10/09 (G4 à amender au resync) · Eli : relances N1/N2, mise en demeure préparée et validée.
- **G5** ✅ aucun claim RGPD.
- **G7** ✅ ni « automatisation », ni « plateforme », ni « configurer » en promesse (la couverture dit « rien à configurer », formulation déjà validée sur b5).
- **ADR-091** ✅ aucun tiret long, aucune flèche.

## Visuels

`../agent-md-framwork/content-factory/output/catalogue-v1/` : `c1-s1.png` à `c1-s5.png` (1856×2304, 4:5), itérations dans `_iterations/`, procédé et QA dans `REPORT.md`. 8 générations Higgsfield (nano_banana_pro 2k), 20 crédits. Revue Matthieu du 10/09 appliquée en v2 : logo « Mmanda » corrigé (SVG canonique posé par programme), noms Max/Zoé/Eli centrés, Leo en dernier sur la couverture et la finale, finale sans « Essai 7 jours », pied `manda.run` partout. Slide 5 refaite sur fond sombre avec les trois pierres en grappe (Matthieu ne voulait pas deux fois le même écran).

## Production

1. Verdict Matthieu sur la structure (ce fichier).
2. Rendu content-factory : couverture = b5.png en référence d'image (« reproduce EXACTLY, add names under stones »), slides 2-4 = chaque pierre seule sur fond sable, slide 5 = même gabarit que la couverture, série `c1-s1..s5`, 4:5.
3. Verdict Matthieu sur les visuels, programmation native Instagram : **lundi 14/09 12h15**, puis **épingler** le post.
4. Relevé à 48 h : sauvegardes, envois, visites de profil, clics bio.
