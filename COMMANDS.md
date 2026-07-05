# Commands

## Intention

Définir les commandes opérationnelles que l'utilisateur peut employer pour piloter le dépôt.

## Rôle du document

Ce fichier est le registre des commandes du projet. Il transforme des demandes récurrentes en protocoles stables, afin qu'une session future puisse agir sans réexpliquer le contexte.

## Principe

Les commandes ne remplacent pas la gouvernance. Elles déclenchent des workflows définis ailleurs :

- `bmad/00_operating_model.md` pour l'exécution séquentielle ;
- `GOVERNANCE.md` pour les sources de vérité ;
- `DOMAIN_MODEL.md` pour les frontières conceptuelles ;
- `DEPENDENCIES.md` pour les dépendances pédagogiques.

## Commandes

| Commande | Effet | Modifie les fichiers ? |
| --- | --- | --- |
| `bootstrap` | Commande one-shot qui vérifie M0, lance `design-review`, puis prépare M1 si verdict `GO`. | Oui, seulement sur les fichiers de pilotage. |
| `next` | Exécute la première tâche `READY` de `bmad/03_next_action.md`, puis s'arrête. | Oui, uniquement dans le périmètre de la tâche. |
| `review` | Lance une revue exigeante du dépôt : doublons, incohérences, frontières, dépendances, risques. | Non, sauf demande explicite. |
| `design-review` | Prépare une revue de phase, notamment pour `M0 - Architecture validée`. | Non, sauf demande explicite. |
| `sync` | Vérifie la cohérence documentaire : liens, statuts BMAD, sources de vérité, conventions. | Non, sauf demande explicite. |
| `plan` | Propose ou met à jour un plan de travail, sans exécuter les tâches. | Non, sauf demande explicite. |
| `refactor` | Propose un refactoring documentaire ou applique un refactoring validé. | Seulement si le périmètre est validé. |
| `release` | Prépare une version publiable selon les critères de `bmad/04_definition_of_done.md`. | Oui, si les prérequis sont satisfaits. |

## Commande one-shot : bootstrap

`bootstrap` prépare le passage de `M0 - Architecture validée` vers `M1 - Production`.

Protocole :

1. Vérifier la gouvernance : `GOVERNANCE.md`, `AGENTS.md`, `COMMANDS.md`.
2. Vérifier les liens Markdown.
3. Vérifier le modèle de domaine : `DOMAIN_MODEL.md`.
4. Vérifier le graphe pédagogique : `DEPENDENCIES.md`.
5. Vérifier les ADR : `architecture/adr/`.
6. Vérifier BMAD : epics, backlog, next action, definition of done, workflow, decision log.
7. Lancer `design-review`.
8. Produire un verdict `GO` ou `NO GO`.
9. Si `GO`, préparer `M1 - Production` et débloquer la première tâche de production.
10. Marquer `bootstrap` comme exécutée ou la retirer des commandes actives.

Règles :

- Ne pas rédiger de chapitre.
- Ne pas corriger automatiquement les problèmes détectés.
- Transformer les problèmes bloquants en tâches BMAD.
- S'arrêter après le verdict et les mises à jour de pilotage.

## Garde-fou

Le système doit servir le contenu, jamais l'inverse. Une nouvelle couche de processus ne doit être ajoutée que si elle réduit une ambiguïté réelle ou rend `next` plus fiable.

Après validation de `M0 - Architecture validée`, les changements de gouvernance doivent rester exceptionnels tant qu'au moins un vrai chapitre n'a pas été produit.

## Questions à traiter

- La commande demandée existe-t-elle ?
- Son protocole est-il défini dans le bon fichier ?
- L'action risque-t-elle de faire grossir le système au lieu de faire avancer le contenu ?
