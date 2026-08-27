# SIGNALS — Index (canal growth → stratégie)

> Un signal = un constat qui touche la stratégie (marché, pricing, produit, positionnement), documenté avec preuve
> et proposition. Les agents growth ÉCRIVENT des signaux ici ; ils ne touchent jamais au pricing/positioning/roadmap.
> **Axiom lit cet index à chaque activation** et triage les `new` : `gravé (ADR-XXX)` · `re-scopé (CP-XXX)` · `rejeté (motif)`.
> Le verdict est écrit sur le fichier du signal ET dans la colonne statut ci-dessous. Append-only, jamais de suppression.

Format fichier : `SIG-XXX-slug.md` avec frontmatter `date / agent / type: marché|pricing|produit|positionnement / statut: new`.

| ID | Date | Agent | Type | Constat (une ligne) | Statut |
|----|------|-------|------|----------------------|--------|
| SIG-001 | 2026-07-28 | growth-marketer | produit | Le trafic growth n'a aucune destination de conversion valide tant que #29 bloque — besoin d'un CP produit pour la page waitlist Fondateur `manda.run/fondateur` (capture email + tracking) | **caduc (2026-08-27)** — `/pricing` live + CP-120 = destination valide, G1 levée ; pas de page waitlist |
