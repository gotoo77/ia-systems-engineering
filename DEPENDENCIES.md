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

- `foundations/` prépare les notions de système, composant, interface et contrat.
- `llm/` prépare les notions de modèle, token, contexte et limites.
- `engines/` dépend de `llm/` et prépare les choix d'exécution.
- `agents/` dépend de `llm/`, `engines/` et des interfaces.
- `memory/` dépend du contexte, des embeddings et de l'indexation.
- `orchestration/` dépend des modèles, outils, agents et mémoires.
- `assistant-dev/` intègre les sections précédentes dans un cas système.
- `labs/` valident des hypothèses d'architecture ; ils ne remplacent pas les chapitres conceptuels.
- `prospective/` dépend des concepts stabilisés avant de formuler des hypothèses.

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
