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

## Lundi matin, 9h

Vous ouvrez votre terminal. Vous décrivez une feature à l'agent.
Dix minutes plus tard, le code est là. Ça compile. Les tests passent.

Vous mergez.

**Mardi, un bug en prod.** Vous rouvrez l'agent. Il ne se souvient de rien.
Vous ré-expliquez le contexte. Il propose un fix. Vous mergez.

**Mercredi, le même bug — ailleurs.** L'agent ne fait pas le lien.
Et vous non plus, parce que ce n'est plus votre code.

---

## Le problème n'est pas l'IA

> « Tu décris ce que tu veux, l'IA produit du code. Tu "vibes" avec le résultat. »
> — Andrej Karpathy, 2025

Scripts, POCs, side projects — c'est redoutablement efficace.

Mais en production, trois choses manquent :
- **Pas de mémoire** — chaque session repart de zéro
- **Pas de review** — le code passe, sans regard critique
- **Pas de capitalisation** — les erreurs ne servent qu'une fois

> Le Vibe Coding, c'est du prototypage qui s'ignore.

---

## L'industrie cherche la sortie

En 2026, deux approches émergent pour structurer le travail avec les agents :

<p style="text-align:center"><img src="images/spectre.svg" width="900"/></p>

Le **Spec-Driven Development** structure le briefing — specs, critères, edge cases.
Mais la spec est jetable. La session d'après, on recommence.

Le **Compound Engineering** fait la même chose, puis ajoute deux étapes :
**review systématique** et **capitalisation**.

---

## L'idée centrale

Et si chaque problème résolu rendait le suivant plus facile ?

<p style="text-align:center"><img src="images/boucle.svg" width="900"/></p>

La plupart des workflows s'arrêtent à la livraison.
Ici, après chaque cycle, on **extrait ce qu'on a appris** et on le réinjecte dans le projet.

L'agent de demain commence là où celui d'aujourd'hui a fini.

---

## Concrètement : la mémoire vit dans le repo

```
votre-projet/
├── CLAUDE.md        # Ce que l'agent doit savoir
├── docs/
│   ├── brainstorms/ # Idéation structurée
│   ├── solutions/   # Patterns extraits des bugs résolus
│   └── plans/       # Blueprints d'implémentation
└── todos/           # Tâches issues des reviews
```

Pas de base de données externe. Pas de SaaS. **Des fichiers markdown dans votre repo.**

L'agent les lit au démarrage. Vos collègues aussi.

---

## Le cycle en action

Reprenons le bug de mardi. Avec le CE, ça donne :

**1. Brainstorm** (*vous pilotez · agent explore*) — on clarifie le problème, l'agent explore les causes possibles.

**2. Plan** (*vous validez · agent recherche*) — l'agent analyse le codebase, la doc framework, les best practices. Blueprint *avant* d'écrire une ligne de code.

**3. Work** (*vous clarifiez · agent code*) — il implémente depuis le plan, sur une branche isolée.

---

## Le cycle en action (suite)

**4. Review** (*vous décidez · agent analyse*) — des agents spécialisés (sécu, perfs, archi, simplification) passent le code au peigne fin. En parallèle.

**5. Compound** (*vous supervisez · agent documente*) — le fix est analysé : quel pattern a causé le bug ? La réponse est documentée dans `docs/solutions/`.

**Mercredi**, quand un bug similaire apparaît, l'agent *le sait déjà*.

---

## Ce qui change au quotidien

Avant : vous écrivez du code et parfois de la doc.
Après : **vous pilotez un système qui apprend.**

| Avant | Après |
|-------|-------|
| Décrire → Coder → Merger | Planifier → Exécuter → Reviewer → Capitaliser |
| L'agent est un outil | L'agent est un junior supervisé |
| La doc est une corvée | La doc est le carburant du système |
| Chaque session repart de zéro | Chaque session démarre avec le contexte |

> Le code n'est plus l'artefact principal. Le *système* l'est.

---

## Le Split 80/20

Every Inc le résume ainsi :

**80%** de votre temps sur **Plan + Review** — réfléchir, vérifier, décider.
**20%** sur **Work + Compound** — l'agent exécute, le système capitalise.

Vous ne codez presque plus. Vous **pilotez et contrôlez**.

> Vous êtes un architecte, pas un dactylo.

---

## Où en êtes-vous ?

<p style="text-align:center"><img src="images/echelle.svg" width="850"/></p>

Le passage de **2 à 3** est le moment clé.
Vous arrêtez de relire chaque ligne. Vous commencez à **diriger**.

---

## Soyons honnêtes

Le CE n'est pas magique. Voici ce que personne ne met dans les slides de démo :

- **Rien de révolutionnaire** — Will Larson : *« des pratiques connues, converties en quelque chose de concret et largement automatique »*. La nouveauté est dans la discipline, pas dans les idées
- **Le premier cycle est le plus lent** — il faut "enseigner" au système avant qu'il compose
- **Vos tests sont le plafond** — Will Larson : *« la qualité dépend plus de votre codebase et vos tests que de l'agent lui-même »*
- **Pas prouvé à grande échelle** — Every fait tourner 5 produits, 1 dev par produit. Quid d'une équipe de 20 ?

> C'est un multiplicateur — de vos forces *et* de vos faiblesses.

---

## Le piège que personne ne voit

80% du temps à piloter, 20% à exécuter. Ça sonne bien.
Mais si vous ne codez presque plus... **comprenez-vous encore ce que l'agent produit ?**

L'**effet GPS** : les chauffeurs de taxi londoniens qui mémorisent les rues développent un hippocampe plus gros. Ceux qui utilisent le GPS le voient s'atrophier.

Même mécanisme avec le code. Plus l'outil est bon, plus le piège est confortable :
vous livrez plus vite, mais vous comprenez moins.

> Micode — *« Comment ChatGPT détruit votre cerveau »*

---

## L'étude qui change tout

Le MIT teste trois groupes d'étudiants face à des problèmes complexes :

| Groupe | Méthode | Résultat immédiat | Sans IA ensuite |
|--------|---------|-------------------|-----------------|
| **A** | Sans aide | Moyen | Stable |
| **B** | IA libre | **Le meilleur** | **S'effondre** |
| **C** | IA tuteur | Bon | **Progresse** |

Le groupe B accumule une **dette cognitive** : des résultats sans compétences.
Le groupe C apprend *avec* l'IA — et devient autonome.

---

## Garder la main

Deux réflexes pour rester dans le groupe C :

- **Coder sans IA régulièrement** — katas, pet projects, debugging manuel. Le muscle qui ne travaille pas s'atrophie
- **Configurer votre `CLAUDE.md` en mode socratique** — l'agent donne des indices, pas des réponses. Vous restez aux commandes *même quand vous utilisez l'IA*

**Le mode tuteur** (`/coding-tutor`) pousse cette logique plus loin :
l'agent analyse *votre* codebase et crée des exercices personnalisés.

> Au lieu de déléguer ce que vous ne comprenez pas, vous l'**apprenez**.
> — Plugin CE : github.com/EveryInc/compound-engineering-plugin

---

## Pour essayer

```bash
# Compound Engineering
claude /plugin marketplace add EveryInc/compound-engineering-plugin
claude /plugin install compound-engineering
claude /ce:plan "Ajouter l'authentification OAuth2"

# AI Tutor — apprendre depuis votre code
claude /coding-tutor
```

---

# Demain matin,

# vous changez quoi ?

---

## Ressources

- **Guide définitif :** every.to/source-code/compound-engineering-the-definitive-guide
- **Guide pratique :** every.to/guides/compound-engineering
- **Analyse Larson :** lethain.com/everyinc-compound-engineering
- **Plugin :** github.com/EveryInc/compound-engineering-plugin
- **SDD :** martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html
- **Atrophie cognitive :** Micode — *Comment ChatGPT détruit votre cerveau* (YouTube)

**Merci.**
