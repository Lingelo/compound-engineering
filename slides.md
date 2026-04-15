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

### Compound Engineering et le développement AI-native

---

## Le Vibe Coding — le point de départ

> « Tu décris ce que tu veux, l'IA produit du code. Tu "vibes" avec le résultat. »
> — Andrej Karpathy, 2025

Ça marche pour un script, un POC, un side project.
Mais en production : pas d'architecture, zéro capitalisation, chaque session repart de zéro.

> Le Vibe Coding, c'est du prototypage qui s'ignore.

---

## Vers l'ingénierie agentique

En 2026, l'industrie cherche à **structurer** le travail avec les agents IA.
Deux approches émergent pour dépasser le Vibe Coding :

<p style="text-align:center"><img src="images/spectre.svg" width="900"/></p>

Le **SDD** structure le briefing (specs, critères, edge cases) — mais la spec est jetable, pas de capitalisation.
Le **CE** inclut le briefing, et ajoute review systématique + **capitalisation**.

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

> « La qualité de la planification détermine directement la qualité du résultat de l'agent. »

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

## Limites du CE

Pas de complaisance — le CE a ses angles morts :

- **Rien de révolutionnaire** — Larson : *« des patterns connus, systématisés en boucle »*. La nouveauté est dans la discipline, pas les étapes
- **Investissement initial** — il faut "enseigner" au système avant qu'il compose. Le premier cycle est le plus lent
- **Dépend de votre CI/CD** — *« la qualité dépend plus de vos tests que de l'agent »*. Sans bons tests, le CE amplifie les problèmes
- **Pas prouvé à grande échelle** — Every fait tourner 5 produits, 1 dev chacun. Quid d'une équipe de 20 ?

> Le CE n'est pas magique. C'est un multiplicateur — de vos forces *et* de vos faiblesses.

---

## Le piège de trop déléguer

Vibe Coding, SDD et CE ont un point commun : **les trois externalisent le travail vers l'agent.**
Le risque : perdre la maîtrise du code et de ses subtilités.

**Trois pratiques pour lundi matin :**

1. **Sessions sans IA** — le muscle qui ne travaille pas s'atrophie
2. **Red-teaming systématique** — ne mergez jamais du code que vous ne comprenez pas à 100%
3. **Expliquer avant de merger** — si vous ne pouvez pas expliquer *pourquoi* le code fonctionne, vous n'êtes pas prêt

> L'IA accélère. Votre compréhension décide de la direction.

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
