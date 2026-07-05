# ADR-0003 - Passage en M1 Production

## Intention

Acter le passage de `M0 - Architecture validée` à `M1 - Production`.

## Statut

Accepté.

## Contexte

La revue M0 a initialement conclu `NO GO` parce que les critères d'acceptabilité n'étaient pas objectivés. La correction minimale consiste à définir ces critères dans `ADR-0001`, puis à vérifier si le dépôt les satisfait déjà.

Le but n'est pas de perfectionner l'architecture documentaire. Le but est de déterminer si elle est suffisamment stable pour commencer la production par petites tâches BMAD.

## Décision

Le projet passe en `M1 - Production`.

La première tâche de production débloquée est :

- `BMAD-009 — Préparer le cadrage du premier chapitre fondateur`

Cette tâche ne rédige pas encore le chapitre. Elle prépare son cadrage pédagogique.

## Justification

- La gouvernance existe et les sources de vérité sont identifiées.
- Le modèle de domaine existe avec un format de concept et des frontières ouvertes explicites.
- Le graphe pédagogique existe avec un graphe principal et des dépendances par section.
- BMAD est opérationnel avec une file de tâches et une commande `next`.
- Les dettes restantes sont connues, limitées et pilotables.

## Conséquences

- Les changements majeurs de gouvernance deviennent exceptionnels.
- La production avance par `next`.
- Une seule tâche doit être `READY` à la fois.
- Le premier travail M1 reste un cadrage, pas une rédaction complète.

## Dette acceptée

- Les frontières contexte/mémoire/RAG restent à préciser.
- Les frontières modèle/inférence/moteur restent à préciser.
- Le glossaire reste initial.
- Certains titres de chapitres orientés outils restent à refactorer plus tard.

## Dette non acceptable

- Produire un chapitre complet sans cadrage.
- Ajouter de nouvelles couches de gouvernance avant un premier vrai contenu.
- Lancer plusieurs tâches BMAD en parallèle.

## Questions à traiter

- Le cadrage du premier chapitre suffit-il pour lancer une rédaction ensuite ?
- Quelles dettes doivent être traitées avant le deuxième chapitre ?
