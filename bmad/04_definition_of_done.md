# BMAD Definition of Done

## Intention

Définir les critères de terminaison d'une tâche BMAD.

## Rôle du document

Ce fichier évite les tâches ambiguës. Une tâche n'est terminée que si elle satisfait ses critères d'acceptation et ne déclenche pas de travail hors périmètre.

## Definition of Done

Une tâche est `DONE` si :

- les fichiers concernés ont été modifiés uniquement dans le périmètre prévu ;
- les critères d'acceptation de la tâche sont vérifiés ;
- aucun chapitre n'a été rédigé si la tâche est structurelle ;
- les références Markdown ajoutées pointent vers des fichiers existants ;
- les statuts BMAD sont mis à jour ;
- une décision structurante est consignée dans `bmad/06_decision_log.md` si nécessaire ;
- le résumé final liste les fichiers modifiés et les prochaines tâches candidates.

## Definition of Done v0.1

La version `v0.1 - Fondations` est publiable si :

- le périmètre v0.1 est défini dans `ROADMAP.md` ;
- la checklist v0.1 de `QUALITY_CHECKLIST.md` est satisfiable sans interprétation implicite ;
- `DOMAIN_MODEL.md` et `DEPENDENCIES.md` couvrent les concepts utilisés par `docs/` et `foundations/` ;
- aucun chapitre de fondation ne porte une responsabilité réservée aux sections aval ;
- les liens Markdown sont vérifiés ;
- la prochaine étape après v0.1 est explicite.

## Non terminé

Une tâche n'est pas terminée si :

- elle ajoute une règle dans le mauvais fichier source de vérité ;
- elle mélange plusieurs tâches BMAD ;
- elle modifie un chapitre hors périmètre ;
- elle laisse une dépendance non vérifiée ;
- elle nécessite une décision non consignée.

## Questions à traiter

- La tâche a-t-elle produit exactement ce qui était attendu ?
- Une décision structurante a-t-elle été prise ?
- La prochaine tâche est-elle identifiable ?
