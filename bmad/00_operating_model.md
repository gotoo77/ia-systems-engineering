# BMAD Operating Model

## Intention

Définir le modèle de pilotage du dépôt comme un projet d'ingénierie documentaire.

## Rôle du document

Ce fichier explique comment travailler par petites tâches séquentielles, vérifiables et traçables. Il permet à une session future de reprendre le projet sans reconstituer le contexte.

## Principes

- Une session agentique exécute une seule tâche BMAD à la fois.
- Une tâche doit être petite, vérifiable et reliée à un epic.
- Une tâche ne doit pas rédiger un chapitre si son objectif est structurel.
- Les décisions structurantes sont consignées dans `bmad/06_decision_log.md`.
- Le statut des tâches est mis à jour dans `bmad/03_next_action.md`.

## Statuts

- `TODO` : tâche identifiée mais non prête.
- `READY` : tâche exécutable immédiatement.
- `IN_PROGRESS` : tâche en cours dans la session active.
- `DONE` : tâche terminée et vérifiée.
- `BLOCKED` : tâche bloquée par une dépendance ou une décision.

## Commande opérationnelle : next

Quand l'utilisateur dit `next`, l'agent doit :

1. Lire `bmad/03_next_action.md`.
2. Sélectionner la première tâche au statut `READY`.
3. Vérifier ses dépendances.
4. Exécuter uniquement cette tâche.
5. Mettre à jour son statut.
6. Ajouter une entrée dans `bmad/06_decision_log.md` si une décision structurante est prise.
7. S'arrêter.
8. Fournir un résumé, la liste des fichiers modifiés et les prochaines tâches candidates.

## Questions à traiter

- La prochaine tâche est-elle vraiment prête ?
- Ses dépendances sont-elles satisfaites ?
- Peut-elle être terminée sans dériver vers du contenu de chapitre ?
