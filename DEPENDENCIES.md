# Dependencies

## Intention

Rendre explicites les dépendances pédagogiques entre concepts et chapitres.

## Rôle du document

Ce fichier complète `TABLE_OF_CONTENTS.md`. La table des matières donne un ordre de lecture ; ce fichier décrit ce qui dépend conceptuellement de quoi.

## Graphe principal

```text
Information
  -> Complexité
  -> Modularité
  -> Interfaces et contrats
  -> Modèles
  -> Inférence
  -> Moteurs d'inférence
  -> Outils
  -> Agents
  -> Mémoire et RAG
  -> Orchestration
  -> Assistant de développement local
```

## Chaînes conceptuelles prioritaires

```text
Token
  -> Contexte
  -> Limites de génération
  -> Hallucination
  -> Récupération externe
  -> RAG
```

```text
Modèle
  -> Inférence
  -> Moteur d'inférence
  -> Déploiement local ou serveur
  -> Latence, coût, débit, contrôle
```

```text
Composant
  -> Interface
  -> Contrat
  -> Orchestration
  -> Observabilité
  -> Évaluation
```

## Dépendances par section

- `foundations/` prépare les notions de système, composant, interface et contrat ; orchestration et observabilité y restent des ouvertures.
- `llm/` prépare les notions de modèle, token, contexte et limites.
- `engines/` dépend de `llm/` et prépare les choix d'exécution.
- `agents/` dépend de `llm/`, `engines/` et des interfaces.
- `memory/` dépend du contexte, des embeddings et de l'indexation.
- `orchestration/` dépend des modèles, outils, agents et mémoires.
- `assistant-dev/` intègre les sections précédentes dans un cas système.
- `labs/` valident des hypothèses d'architecture ; ils ne remplacent pas les chapitres conceptuels.
- `prospective/` dépend des concepts stabilisés avant de formuler des hypothèses.

## Table de dépendances exploitable

| Section | Prérequis | Concepts introduits | Concepts réutilisés |
| --- | --- | --- | --- |
| `docs/` | Aucun. | Intention, périmètre, mode de lecture. | Gouvernance, roadmap. |
| `foundations/` | Aucun. | Information, système, complexité, composant, interface, contrat. | Intention, périmètre. |
| `llm/` | Information, système, contexte. | Modèle, token, fenêtre de contexte, hallucination, embedding, quantification. | Complexité, responsabilité, limites. |
| `engines/` | Modèle, inférence, quantification. | Moteur d'inférence, runtime, latence, débit, placement matériel. | Modèle, contexte, compromis. |
| `agents/` | Modèle, inférence, moteur, outil, interface. | Agent, boucle agentique, autonomie, tool use, sandboxing. | Interface, contexte, moteur d'inférence. |
| `memory/` | Contexte, embedding, indexation. | Mémoire, mémoire documentaire, récupération, RAG. | Modèle, contexte, évaluation. |
| `orchestration/` | Composant, interface, agent, mémoire, outil. | Orchestrateur, pattern d'orchestration, multi-agents, observabilité, feedback. | Moteur, modèle, RAG, contrat. |
| `assistant-dev/` | LLM, moteurs, agents, mémoire, orchestration. | Assistant de développement local, permissions, boucle git/tests. | Tous les concepts précédents. |
| `labs/` | Chapitres conceptuels concernés. | Hypothèse, protocole, métrique, validation expérimentale. | Patterns, composants, observabilité. |
| `prospective/` | Concepts stabilisés du modèle de domaine. | Self-scaffolding, inference-time scaling, systèmes intelligents. | Graphe pédagogique complet. |

## Frontière de `foundations/03`

`foundations/03_interfaces_orchestration_observabilite.md` doit préparer l'architecture sans l'anticiper.

- **À introduire** : interface, contrat, frontière de composant.
- **À annoncer** : orchestration, observabilité, évaluation.
- **À reporter** : patterns d'orchestration, multi-agents, boucles de feedback, instrumentation détaillée.

## Premier chapitre fondateur

`foundations/01_information_complexite_emergence.md` introduit les concepts racines suivants :

- information ;
- système ;
- complexité ;
- interaction ;
- émergence.

Ces concepts préparent directement :

- `foundations/02_diviser_pour_mieux_comprendre.md` ;
- `foundations/03_interfaces_orchestration_observabilite.md` ;
- `orchestration/01_patterns_d_orchestration.md` ;
- `agents/01_pourquoi_les_agents.md`.

## Questions à traiter

- Une notion est-elle utilisée avant d'être introduite ?
- Un chapitre dépend-il implicitement d'un concept non nommé ?
- Une dépendance pédagogique doit-elle devenir un chapitre dédié ?
