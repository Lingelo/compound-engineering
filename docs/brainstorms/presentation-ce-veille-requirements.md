---
title: Refonte slides Compound Engineering - Talk veille tech
status: active
created: 2026-04-14
updated: 2026-06-01
---

# Refonte de la presentation Compound Engineering (v2)

## Contexte

Presentation de veille tech pour des coequipiers Sfeir, **praticiens Claude Code** decouvrant pour la premiere fois le concept de Compound Engineering. Le plugin a evolue significativement depuis la premiere version des slides (passage v3.0 avec renommage des skills en prefixe `ce-`, ajout de skills product et de phases workflow, multi-plateforme), et la presentation doit etre mise a jour avant le prochain talk.

Format vise : **15-20 min, ~15-16 slides, dev-centre**.

## Objectif du talk

Faire decouvrir le concept de Compound Engineering en montrant qu'il a atteint une maturite qui justifie d'investir maintenant. Le fil rouge : *"il y a un an, c'etait 4 commandes bricolees ; aujourd'hui, c'est un framework de 37 skills qui apprend de session en session"*.

L'arc atrophie cognitive + mode tuteur reste central (eviter de vendre l'IA comme substitut au jugement du dev).

## Arc narratif retenu : "Du POC au framework" (Arc B)

Garde l'ossature storytelling existante (Lundi matin → spectre → boucle → atrophie → call-to-action), mais reorganise le coeur pour :
1. **Rendre visible la maturation du plugin** comme fil narratif (pas une slide isolee)
2. **Integrer la phase Polish** dans le cycle (4 → 5 etapes)
3. **Mettre en avant ce-sessions** (memoire transversale) comme illustration concrete du compound
4. **Actualiser les commandes et ressources** (toutes les references `/ce:` deviennent `/ce-`)

### Structure cible (15-16 slides)

1. Hook "Lundi matin" *(existant, garde)*
2. Le probleme commun *(existant, garde)*
3. Spectre Vibe → SDD → CE *(existant, garde)*
4. L'idee centrale : la boucle qui apprend *(existant, retoucher pour annoncer le passage a 5 etapes)*
5. **NOUVEAU** — Filesystem + ce-sessions : la memoire qui survit aux conversations
6. **REFONDU** — Le cycle complet : Plan → Work → Review → **Polish** → Compound
7. **NOUVEAU** — D'un POC a un framework : 37 skills, 51 agents, v3.9 (slide courte "ecosysteme")
8. Ce qui change au quotidien (table avant/apres) *(existant, garde)*
9. Ou en etes-vous ? (echelle) *(existant, garde)*
10. Soyons honnetes (limites) *(existant, ajuster : "Will Larson ecrivait ca a v0.X, on est a v3.9, c'est toujours vrai")*
11. Le piege GPS / atrophie cognitive *(existant, garde)*
12. L'etude MIT *(existant, garde)*
13. Garder la main + mode tuteur *(existant, garde)*
14. Pour essayer (commandes a jour : `/ce-plan`, `/ce-work`, `/ce-sessions`, `/coding-tutor`)
15. Demain matin vous changez quoi ? *(existant, garde)*
16. Ressources *(actualisees, ajout du CHANGELOG)*

## Decisions de cadrage

### Audience
Praticiens Claude Code, **decouvrant le CE pour la premiere fois**. Pas besoin d'introduire ce qu'est un agent IA. En revanche le concept "filesystem comme memoire", "skills compose en cycle", "ce-sessions traverse les conversations" demande pedagogie.

### Angle
**Dev-centre.** Les skills product (`ce-strategy`, `ce-ideate`, `ce-brainstorm`, `ce-product-pulse`) ne seront pas presentes en detail. Mentionner leur existence eventuellement dans la slide ecosysteme, sans developper.

### Nouveautes integrees
- **ce-sessions** (memoire transversale) — slide dediee, illustre le compound de maniere concrete
- **ce-polish** (human-in-the-loop entre review et merge) — integre dans le cycle (4→5 etapes)
- **Maturite du plugin** (37 skills, 51 agents, v3.9, 163 releases) — fil narratif + slide "ecosysteme"

### Nouveautes ecartees (volontairement)
- **Multi-plateforme** (Cursor, Codex, Copilot, Pi, Gemini CLI) — l'audience est full Claude Code, ce n'est pas une accroche
- **Skills product** (`ce-strategy`, `ce-product-pulse`, `ce-ideate`) — hors angle dev-centre
- **Liste exhaustive des 37 skills** — on en cite 5-6 emblematiques maximum

### Actifs visuels a regenerer
- **`images/boucle.svg`** — actuellement 4 etapes, doit passer a 5 pour integrer Polish. **Inclus dans la refonte**, pas un follow-up.
- Verifier que `images/spectre.svg`, `images/echelle.svg`, `images/clawd.svg` sont toujours coherents avec le nouveau message — pas de regeneration prevue a priori.

## Non-goals

- Ce n'est pas une formation a l'utilisation du plugin
- Pas de demo live
- Pas de comparaison exhaustive des outils SDD ni des autres plateformes
- Pas de couverture exhaustive des skills (37 dispos, on en cite ~5-6)
- Pas de discussion approfondie des skills product (mention possible, pas plus)

## Risques et points d'attention

- **Surcharge** — 15-16 slides en 15-20 min, c'est environ 1 min/slide. Le rythme est tenable mais zero slide ne doit etre verbeuse. Test : si une slide demande plus de 90s a l'oral, la couper.
- **Slide "ecosysteme"** — risque de devenir un catalogue ennuyeux. Doit etre tres visuelle, peu de texte, montrer l'echelle (chiffres clefs) plutot que lister.
- **Phase Polish** — concept nouveau pour l'audience. Doit etre defini clairement (une phrase) avant d'etre nomme dans le cycle.
- **Coherence narrative** — le fil "POC → framework" doit etre visible dans l'enchainement, pas seulement dans la slide ecosysteme. A verifier slide par slide lors de l'ecriture.

## Sources verifiees

- Plugin GitHub : https://github.com/EveryInc/compound-engineering-plugin (v3.9.4 au 2026-05-31, 163 releases, 37 skills, 51 agents)
- CHANGELOG du plugin : evolutions cles documentees (ce-setup, ce-sessions, ce-polish-beta, ce-ideate, ce-strategy, ce-product-pulse, support multi-plateforme, renommage v3.0)
- Guide definitif Every : https://every.to/source-code/compound-engineering-the-definitive-guide (fevrier 2026)
- Analyse Larson : https://lethain.com/everyinc-compound-engineering (toujours d'actualite)

## Suite

Prochaine etape : `/ce-plan` ou edition directe de `slides.md` selon ce que le user prefere.

Le plan devrait :
1. Identifier precisement quelles sections de `slides.md` reecrire et lesquelles garder telles quelles
2. Specifier le contenu des 3 nouvelles slides (5, 6 refondue, 7)
3. Specifier la regeneration de `images/boucle.svg` (5 etapes, style coherent avec l'existant)
4. Lister toutes les occurrences a corriger pour les commandes obsoletes
5. Prevoir la regeneration de `slides.html` apres edition (`npx @marp-team/marp-cli slides.md -o slides.html`)
