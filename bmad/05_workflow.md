# BMAD Workflow

## Intention

Décrire le flux de travail standard d'une session agentique.

## Rôle du document

Ce fichier sert de procédure opérationnelle. Il garantit que les sessions futures restent séquentielles, traçables et limitées.

## Workflow standard

1. Lire `bmad/00_operating_model.md`.
2. Lire `bmad/03_next_action.md`.
3. Lire `GOVERNANCE.md`.
4. Lire `DOMAIN_MODEL.md`.
5. Lire `DEPENDENCIES.md`.
6. Identifier la première tâche `READY`.
7. Vérifier ses dépendances.
8. Exécuter uniquement cette tâche.
9. Mettre à jour `bmad/03_next_action.md`.
10. Mettre à jour `bmad/06_decision_log.md` si nécessaire.
11. S'arrêter.

## Règles de limitation

- Ne pas exécuter deux tâches dans la même réponse.
- Ne pas rendre une tâche `DONE` sans critères vérifiables.
- Ne pas débloquer une tâche sans vérifier sa dépendance.
- Ne pas modifier les chapitres sauf si la tâche le demande explicitement.

## Résumé attendu

Chaque session se termine par :

- tâche exécutée ;
- résultat ;
- fichiers modifiés ;
- décisions consignées ;
- prochaines tâches candidates.

## Questions à traiter

- La session respecte-t-elle une seule unité de travail ?
- L'arrêt est-il explicite après la tâche ?
