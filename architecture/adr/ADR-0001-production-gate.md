# ADR-0001 - Passage en mode Production

## Intention

Définir les critères de passage entre la phase de conception documentaire et la phase de production.

## Statut

Proposé.

## Contexte

Le dépôt dispose maintenant d'une architecture documentaire v2, d'une gouvernance initiale et d'un workflow BMAD. Avant de lancer la production des chapitres, il faut définir quand l'architecture est suffisamment stable pour produire sans réexpliquer le projet à chaque session.

Le risque n'est pas de commencer trop tôt parce que tout n'est pas parfait. Le risque est de commencer avant que les frontières conceptuelles, les dépendances pédagogiques et le pilotage BMAD soient assez stables pour éviter la dérive.

## Décision

Le projet ne passe en production que lorsque la milestone `M0 - Architecture validée` est atteinte.

Les conditions minimales sont :

- gouvernance documentaire complète ;
- modèle de domaine acceptable ;
- graphe de dépendances pédagogique acceptable ;
- workflow BMAD opérationnel ;
- premier backlog stabilisé ;
- premier chapitre clairement identifié, sans être encore rédigé.

Une fois ces conditions réunies :

- l'architecture documentaire est considérée comme suffisamment stable ;
- les changements majeurs d'architecture passent par une revue dédiée ;
- la production quotidienne est pilotée par BMAD ;
- la commande opérationnelle `next` devient le mode de progression par défaut.

## Rôle responsable

Le rôle de `Knowledge Program Manager` est introduit pour décider du passage de phase.

Responsabilités :

- valider ou refuser `M0 - Architecture validée` ;
- décider quand passer en `M1 - Production` ;
- vérifier que le workflow BMAD est opérationnel ;
- empêcher le lancement de la production si le modèle de domaine ou les dépendances sont encore ambigus.

Ce rôle ne remplace pas l'architecte de connaissance. Il décide du passage de phase ; l'architecte de connaissance structure le domaine.

## Conséquences

- Les chapitres ne doivent pas être rédigés avant validation de M0.
- Les labs restent possibles uniquement comme tâches de cadrage ou de validation, pas comme tutoriels.
- Les gros refactorings structurels après M0 doivent être justifiés par une nouvelle ADR.
- Les sessions futures peuvent utiliser `next` si BMAD contient une tâche `READY` et des dépendances satisfaites.

## Alternatives rejetées

- Démarrer la rédaction dès que le squelette existe : trop risqué, car les frontières conceptuelles restent incomplètes.
- Attendre que toute l'architecture soit parfaite : trop coûteux, car le projet n'apprendrait pas par production incrémentale.
- Piloter la production uniquement depuis `ROADMAP.md` : insuffisant, car la roadmap ne définit pas une file de tâches exécutable.

## Questions à traiter

- Qui valide M0 dans une session donnée ?
- Quels critères rendent le modèle de domaine simplement acceptable ?
- Quelle tâche BMAD marque officiellement le passage en M1 ?
