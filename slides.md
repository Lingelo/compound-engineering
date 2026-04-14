---
marp: true
title: Au-delà du Vibe Coding
theme: default
paginate: true
backgroundColor: #141413
color: #e8e6dc
style: |
  section {
    font-family: 'Inter', 'Helvetica Neue', sans-serif;
  }
  h1, h2, h3 {
    color: #e8e6dc;
    font-weight: 800;
    letter-spacing: -0.02em;
  }
  h2 {
    font-size: 1.8em;
  }
  h1 code, h2 code, h3 code {
    color: #141413;
    background: #d97757;
  }
  code {
    background: #1e1e1c;
    color: #d97757;
  }
  pre {
    background: #1e1e1c !important;
    border: 1px solid #333;
  }
  pre code {
    color: #e8e6dc !important;
    background: #1e1e1c !important;
  }
  pre code span {
    color: #e8e6dc !important;
  }
  blockquote {
    border-left: 4px solid #d97757;
    color: #b0aea5;
    font-style: italic;
  }
  table {
    font-size: 0.85em;
    color: #e8e6dc;
    margin: 0 auto;
  }
  table th {
    background: #d97757;
    color: #141413;
    border: 1px solid #333;
  }
  table th strong {
    color: #141413;
  }
  table td {
    background: #1e1e1c;
    color: #e8e6dc;
    border: 1px solid #333;
  }
  table tr:nth-child(even) td {
    background: #252523;
  }
  em {
    color: #d97757;
  }
  ul, ol, li, p {
    color: #e8e6dc;
  }
  strong {
    color: #d97757;
  }
  a {
    color: #e8e6dc;
  }
---

<p style="text-align:center"><img src="images/clawd.svg" width="120"/></p>

# <span style="color:#e8e6dc">❯</span> <span style="color:#d97757">Au-delà du Vibe Coding</span>

### SDD, Compound Engineering et le spectre du développement AI-native

---

## 1. Le Vibe Coding — où on en est tous partis

> « Tu décris ce que tu veux, l'IA produit du code. Tu "vibes" avec le résultat. »
> — Andrej Karpathy, 2025

Ça marche pour un script, un POC, un side project. Mais en production :

- **~40% du code généré** contient des vulnérabilités potentielles (Black Duck, 2026)
- Pas d'architecture intentionnelle — le codebase devient un plat de spaghetti
- Zéro capitalisation — chaque session repart de zéro

> Le Vibe Coding, c'est du prototypage qui s'ignore.

---

## Vers l'ingénierie agentique

En 2026, l'industrie cherche à **structurer** le travail avec les agents IA.
Deux approches émergent pour dépasser le Vibe Coding :

<p style="text-align:center"><img src="images/spectre.svg" width="900"/></p>

Ce ne sont pas des concurrents — c'est un **spectre de maturité**.

---

## 2. Le Spec Driven Development

Né chez Harper Reed (fév. 2025), formalisé par **SpecKit** (GitHub), **OpenSpec** (Fission-AI) et **Kiro** (AWS).

<p style="text-align:center"><img src="images/sdd-flow.svg" width="800"/></p>

L'humain définit le **WHAT/WHY**. L'agent prend en charge le **HOW**.
La spec structure critères d'acceptation, edge cases, périmètre.

> La spec est la source de vérité, pas le code.

---

## Les limites du SDD

Martin Fowler et d'autres pointent des faiblesses structurelles :

- **"Waterfall in Markdown"** — on réécrit des specs détaillées *avant* de coder, comme en 2005
- **Ceremony x10** — SpecKit génère des dizaines de fichiers markdown par feature. Fowler : *« I'd rather review code than all these markdown files »*
- **La spec est jetable** — une fois l'implémentation faite, la spec ne sert plus
- **Mêmes bugs** — plus de specs ne veut pas dire moins de bugs
- **Non-déterminisme** — même spec, résultats différents. La spec ne *garantit* rien

Le SDD résout le **briefing**. Mais il ne résout pas la **capitalisation**.

---

## 3. Compound Engineering : l'étape d'après

Né chez Every Inc. — plugin open-source, **14.3k stars**, 12+ outils compatibles.

Le CE **inclut** le SDD (Brainstorm + Plan), mais ajoute ce qui manque :

<div style="display:flex; justify-content:center">

| Étape | **SDD** | **CE** |
|---|---|---|
| WHAT/WHY | Specify | Brainstorm |
| HOW | Plan → Tasks | Plan (3+ agents) |
| Exécuter | Implement | Work (worktree) |
| Vérifier | — | **Review** (14+ agents) |
| Capitaliser | — | **Compound** |

</div>

---

## La Boucle Principale

<p style="text-align:center"><img src="images/boucle.svg" width="900"/></p>

L'ingrédient secret, c'est l'étape **Compound**.
L'ingénierie traditionnelle et le SDD s'arrêtent à la livraison. Ici, on **capitalise**.

---

## Le Système de Fichiers Comme Base de Connaissances

Concrètement, voici **où** cette capitalisation vit :

```
votre-projet/
├── CLAUDE.md        # Mémoire institutionnelle
├── docs/
│   ├── brainstorms/ # Idéation
│   ├── solutions/   # Problèmes résolus
│   └── plans/       # Blueprints
└── todos/           # Tâches des reviews
```

**CLAUDE.md est le fichier le plus critique.** L'agent le lit en premier.

---

## Répartition du Temps : Le Split 80/20

| Activité | Temps | Ce qui se passe |
|----------|-------|-----------------|
| **Brainstorm** | ~10% | Explorer les besoins, clarifier les zones floues |
| **Plan** | ~40% | Recherche codebase, best practices, docs framework |
| **Review** | ~40% | 14+ agents parallèles vérifient sécurité, perf, archi |
| **Work** | ~10% | L'agent exécute le plan |
| **Compound** | ~10% | Documenter les apprentissages, MAJ CLAUDE.md |

> Plan + Review = **80%** du temps. Work + Compound = **20%**.

**Vous êtes un architecte, pas un dactylo.**

---

## Pour Démarrer

```bash
# Installer le plugin
claude /plugin marketplace add EveryInc/compound-engineering-plugin
claude /plugin install compound-engineering

# Passer les permissions pour la vélocité (environnements sûrs uniquement)
alias cc='claude --dangerously-skip-permissions'

# Lancer votre premier cycle
cc /ce:plan "Ajouter l'authentification utilisateur avec OAuth2"
```

---

## Étape 0 : Brainstorm (`/ce:brainstorm`)

Explore les besoins et les approches **avant** de planifier.

- Clarifie les exigences floues par la recherche et des questions guidées
- Génère des idées divergentes, puis filtre les plus pertinentes
- Optionnel : `/ce:ideate` génère un maximum d'idées puis un agent "avocat du diable" challenge et élimine les plus faibles

Sortie : un document d'exploration sauvegardé dans `docs/brainstorms/`.

> Le brainstorm empêche de foncer tête baissée dans une mauvaise direction.

---

## Étape 1 : Plan (`/ce:plan`)

Lance **3+ agents de recherche en parallèle** :
- Analyste du codebase
- Chercheur de docs framework (100+ frameworks)
- Chercheur de best practices
- Analyseur de specs

Sortie : un blueprint d'implémentation structuré avec fichiers, approche, cas limites et critères de succès.

> « La qualité de la planification du développeur détermine directement la qualité du résultat de l'agent. »

---

## Étape 2 : Work (`/ce:work`)

Quatre phases :
1. **Quick start** — setup git worktree (branche isolée)
2. **Exécution** — implémentation pas à pas depuis le plan
3. **Contrôle qualité** — 5+ reviewers optionnels en cours de route
4. **Livraison** — création de la PR

L'agent pose des questions de clarification *d'abord*, puis construit.

---

## Étape 3 : Review (`/ce:review`)

**14+ agents spécialisés tournent en parallèle :**

| Agent | Focus |
|-------|-------|
| `security-sentinel` | Audit de vulnérabilités |
| `performance-oracle` | Optimisation performance |
| `architecture-strategist` | Décisions architecturales |
| `data-integrity-guardian` | Migrations base de données |
| `code-simplicity-reviewer` | Design minimaliste |
| `pattern-recognition-specialist` | Détection d'anti-patterns |
| `deployment-verification-agent` | Checklists Go/No-Go |

Résultats triés : **P1** (critique) > **P2** (important) > **P3** (mineur)

---

## Étape 4 : Compound (`/ce:compound`)

L'étape qui change tout. **6 sous-agents en parallèle** analysent ce qui vient d'être résolu, extraient les patterns, et documentent le tout dans `docs/solutions/`.

Chaque session future peut consulter ces solutions — les bugs corrigent des *catégories* entières de bugs futurs.

Et la mémoire s'entretient : `/ce:compound-refresh` passe en revue les learnings existants et décide de les **garder, mettre à jour, remplacer ou archiver**.

> La mémoire n'est pas statique — elle est vivante.

---

## L'Échelle d'Adoption

<pre style="background:#1e1e1c; padding:1em 1.5em; border:1px solid #333; font-size:0.8em; line-height:1.8; font-family:'Courier New',monospace; width:100%; box-sizing:border-box">
<span style="color:#b0aea5">0 Manuel               ██</span>
<span style="color:#b0aea5">1 Copier-coller        █████</span>
<span style="color:#b0aea5">2 Valider chaque ligne ████████</span>
<span style="color:#d97757; font-weight:bold">3 Plan + Review        ████████████████████████ ← CLÉ</span>
<span style="color:#e8956a">4 Idée → PR            ██████████████████████████████████</span>
<span style="color:#e8956a">5 Parallèle cloud      ██████████████████████████████████████████</span>
</pre>

> **2 → 3 :** vous arrêtez de micro-manager — vous planifiez, l'agent exécute.

---

## Changer de posture

Le CE demande un changement de mentalité :

- **Le code n'est plus l'artefact principal** — plans, reviews et docs comptent autant
- **Extraire le goût dans des systèmes** — préférences → règles, agents, skills
- **La règle du 50/50** — 50% features, 50% amélioration du système
- **La confiance par les filets de sécurité** — tests, reviews auto, monitoring
- **Tout doit composer** — code, plans, docs, prompts, processus

---

## Ce que le CE n'invente pas

Soyons honnêtes. Will Larson le dit bien :

> « Le CE consiste en deux patterns très connus (Plan, Work), un modérément connu (Review), et un que beaucoup de praticiens font intuitivement sans l'avoir formalisé (Compound). »

La nouveauté n'est **pas** dans les étapes individuelles.
Elle est dans la **systématisation** : une boucle automatisée où chaque étape alimente la suivante.

C'est ça, la formalisation qui manquait — pas une révolution, mais une **discipline**.

---

## Limites du CE

Pas de complaisance — le CE a ses angles morts :

- **Investissement initial** — il faut "enseigner" au système avant qu'il compose (CLAUDE.md, docs/solutions, conventions). Le premier cycle est le plus lent
- **Dépend de votre CI/CD** — Larson : *« la qualité dépend plus de votre codebase et de vos tests que de l'agent »*. Sans bons tests, le CE amplifie les problèmes
- **Bottleneck humain** — le CE ne résout pas la vitesse à laquelle vous décidez *quoi* construire
- **Pas prouvé à grande échelle** — Every fait tourner 5 produits, 1 dev chacun. Quid d'une équipe de 20 ?

> Le CE n'est pas magique. C'est un multiplicateur — de vos forces *et* de vos faiblesses.

---

## Résultats Concrets

Every Inc. fait tourner **5 produits en production** servant des milliers d'utilisateurs quotidiens.

Chaque produit est principalement construit et maintenu par **une seule personne**.

> « Un seul développeur peut faire le travail de cinq développeurs d'il y a quelques années. »

Le système devient *plus simple à comprendre, modifier et fiabiliser* — l'inverse de la dette technique.

---

## La Philosophie en Un Slide

> « Le métier d'un développeur, c'est de livrer de la valeur. Le code n'est qu'un input parmi d'autres — planifier, reviewer et enseigner au système comptent aussi. »

Vous n'écrivez pas du code.
Vous **construisez un système qui écrit du code et qui s'améliore chaque jour.**

---

<!-- _class: lead -->

# One More Thing...

## Et si le vrai risque, c'était vous ?

---

## Le spectre a un angle mort

Le Vibe Coding, le SDD et le CE ont un point commun :

**Les trois externalisent le travail vers l'agent.**

- Le Vibe Coder ne sait pas ce que l'agent a produit
- Le SDD Writer sait *ce qu'il a demandé*, mais pas *comment c'est construit*
- Le Compound Engineer supervise tout — mais a-t-il encore les mains dans le moteur ?

> « Plus on délègue à l'IA, moins on comprend ce qu'elle produit. »
> — Études MIT Media Lab, Microsoft/CMU, METR 2025

La vitesse sans la compréhension, c'est de la **dette cognitive.**

---

## Trois pratiques pour lundi matin

**1. Sessions sans IA** — réservez du temps pour coder à la main. Pet projects, katas, refactoring volontaire. Le muscle qui ne travaille pas s'atrophie.

**2. Red-teaming systématique** — ne mergez jamais du code que vous ne comprenez pas à 100%. Traitez chaque PR générée comme le code d'un junior talentueux mais inexpérimenté.

**3. Expliquer avant de merger** — si vous ne pouvez pas expliquer *pourquoi* le code fonctionne (pas juste *quoi* il fait), vous n'êtes pas prêt à le merger.

> L'IA accélère. Votre compréhension décide de la direction.

---

## Des garde-fous existent

`~/.claude/CLAUDE.md` — un fichier global qui encode vos garde-fous dans chaque session :

```markdown
## Protocole anti-atrophie
> "L'IA est un junior talentueux mais inexpérimenté
>  qui a besoin de supervision."

## Signaux d'alerte (dette cognitive)
Tu dois m'alerter si tu observes ces patterns :
- Je demande de "juste corriger" sans comprendre
- Je copie-colle sans poser de questions
- Je délègue une décision archi sans la challenger
```

Complétez avec **Coding Tutor** (`/teach-me`, `/quiz-me`) pour ancrer les acquis.

> *Don't just vibe code, vibe learn.*

---

# Et vous,

# vous êtes à quel stade du spectre ?

---

## Merci — Ressources

- **Guide définitif :** every.to/source-code/compound-engineering-the-definitive-guide
- **Guide pratique :** every.to/guides/compound-engineering
- **Analyse Larson :** lethain.com/everyinc-compound-engineering
- **Plugin :** github.com/EveryInc/compound-engineering-plugin
- **SDD — SpecKit :** github.com/github/spec-kit
- **SDD — OpenSpec :** github.com/Fission-AI/OpenSpec
- **SDD — Analyse Fowler :** martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html

**Brainstorm. Plan. Work. Review. Compound. Repeat.**
