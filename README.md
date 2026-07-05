# ia-systems-engineering

Manuel d'ingénierie des systèmes d'IA appliquée.

## Intention

Fournir le point d'entrée du dépôt, sa philosophie et sa progression pédagogique.

## Philosophie

Ce dépôt documente des principes d'architecture durables pour concevoir, observer et faire évoluer des systèmes d'IA. Il privilégie les modèles mentaux, les interfaces, les compromis et les patterns opérationnels plutôt que les outils à la mode.

Le livre avance comme un projet logiciel : petits lots, chapitres autonomes, vocabulaire partagé, contributions relues, expériences reproductibles.

La gouvernance du projet est définie dans `GOVERNANCE.md`.

## Progression

1. Fondations : information, complexité, découpage, interfaces.
2. LLM : fonctionnement, contexte, limites, représentations.
3. Moteurs : inférence, exécution locale, compromis de déploiement.
4. Agents : délégation, outils, sandboxing, protocoles.
5. RAG et mémoire : récupération, indexation, mémoire court/long terme.
6. Orchestration : coordination, multi-agents, observabilité, évaluation.
7. Assistant de développement local : application intégrée des briques précédentes.
8. Labs : validation expérimentale sur assistants, Git et dépôts de code.
9. Prospective : systèmes auto-structurants et scaling à l'inférence.

## Structure

- `docs/` : préface et guide de lecture.
- `foundations/` : concepts d'ingénierie générale.
- `llm/` : concepts spécifiques aux modèles de langage.
- `engines/` : moteurs d'inférence et exécution.
- `agents/` : agents, outils, MCP, sandboxing.
- `memory/` : RAG, mémoire et indexation.
- `orchestration/` : patterns de coordination, multi-agents et feedback.
- `assistant-dev/` : architecture d'un assistant de développement local.
- `labs/` : expériences guidées.
- `prospective/` : hypothèses et tendances.
- `templates/` : formats de rédaction.

Voir `TABLE_OF_CONTENTS.md` pour l'ordre détaillé des chapitres.
Voir `DEPENDENCIES.md` pour les dépendances pédagogiques.
Voir `bmad/00_operating_model.md` pour le pilotage opérationnel du projet.
Voir `COMMANDS.md` pour les commandes disponibles.

## Statut

Squelette éditorial initial. Le contenu détaillé sera ajouté par lots incrémentaux.

## Licence

Contenu publié sous licence Creative Commons Attribution-ShareAlike 4.0 International.

## Questions à traiter

- Quelle progression rend le sujet accessible sans le simplifier à l'excès ?
- Quels principes resteront utiles malgré l'évolution des modèles ?
- Comment maintenir ce manuel comme un projet logiciel ?
