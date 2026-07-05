# Domain Model

## Intention

Définir le modèle conceptuel du domaine couvert par le dépôt.

## Rôle du document

Ce fichier est la source de vérité pour les concepts et leurs frontières. Il sert à décider si un contenu appartient à un chapitre existant, doit être extrait, ou relève d'un autre domaine.

## Format d'un concept

Chaque concept important doit être décrit avec :

- responsabilité ;
- frontières ;
- relations ;
- dépendances ;
- exemples ;
- contre-exemples ;
- concepts voisins.

## Concepts initiaux

- **Information** : contenu transmis, transformé ou sélectionné par un système.
- **Système** : ensemble de composants en interaction produisant un comportement observable.
- **Complexité** : difficulté à prédire le comportement global à partir des seules parties isolées.
- **Interaction** : relation par laquelle un composant influence un autre composant ou un état partagé.
- **Émergence** : comportement global produit par des interactions locales, non évident à partir d'un composant seul.
- **Modèle** : artefact paramétré qui encode des capacités apprises et transforme une entrée en sortie.
- **Inférence** : opération qui exécute un modèle pour produire une sortie à partir d'une entrée.
- **Moteur d'inférence** : couche d'exécution qui charge, paramètre et fait tourner un modèle sur un environnement matériel ou serveur.
- **Token** : unité manipulée par le modèle.
- **Contexte** : information effectivement visible par le modèle pendant une inférence.
- **Mémoire** : information conservée, récupérée ou reconstruite hors de l'inférence immédiate.
- **Embedding** : représentation vectorielle utilisée pour comparer des contenus.
- **Indexation** : organisation de contenus pour les retrouver ou les relier.
- **RAG** : pattern combinant récupération d'information externe et génération par modèle.
- **Outil** : capacité externe appelée par un système d'IA.
- **Agent** : boucle de décision qui poursuit un objectif avec état et outils.
- **Orchestrateur** : composant qui coordonne modèles, outils, mémoire et règles.
- **Observabilité** : capacité à comprendre le comportement du système par traces et mesures.
- **Évaluation** : jugement structuré de la qualité d'un comportement ou d'une sortie.
- **Assistant de développement local** : système appliqué combinant modèle, outils, dépôt, tests et contrôle utilisateur.

## Frontières à clarifier

- Information vs donnée.
- Système vs composant.
- Complexité vs complication.
- Émergence vs effet magique.
- Embedding vs indexation.
- Agent vs orchestrateur.
- Outil vs protocole.
- Benchmark vs évaluation.

## Frontières stabilisées

### Contexte vs mémoire

- **Contexte** : contenu actuellement injecté dans l'inférence.
- **Mémoire** : contenu disponible hors inférence, qui peut être sélectionné, résumé, récupéré ou ignoré.
- **Frontière** : une mémoire ne devient contexte que lorsqu'elle est rendue visible au modèle.
- **Confusion à éviter** : appeler "mémoire" toute fenêtre de contexte longue.

### Mémoire vs RAG

- **Mémoire** : capacité générale à conserver ou retrouver de l'information.
- **RAG** : pattern précis où une récupération externe alimente une génération.
- **Frontière** : le RAG est une manière d'utiliser une mémoire documentaire ; toute mémoire n'est pas du RAG.
- **Confusion à éviter** : croire que le RAG remplace une stratégie de mémoire.

### Contexte vs RAG

- **Contexte** : entrée visible par le modèle au moment de produire.
- **RAG** : mécanisme qui choisit une partie de l'information à mettre dans le contexte.
- **Frontière** : le RAG prépare le contexte ; il n'est pas le contexte lui-même.
- **Confusion à éviter** : mesurer seulement la taille du contexte au lieu de mesurer la qualité de récupération.

### Modèle vs inférence

- **Modèle** : artefact appris, disponible avant l'exécution.
- **Inférence** : opération d'exécution qui utilise le modèle.
- **Frontière** : un modèle peut exister sans être exécuté ; une inférence est un événement ou un processus d'exécution.
- **Confusion à éviter** : attribuer au modèle seul des comportements causés par la stratégie d'inférence.

### Inférence vs moteur d'inférence

- **Inférence** : opération logique de production d'une sortie.
- **Moteur d'inférence** : logiciel qui rend cette opération possible dans un environnement concret.
- **Frontière** : l'inférence décrit ce qui se passe ; le moteur décrit ce qui l'exécute.
- **Confusion à éviter** : traiter le moteur comme un simple détail technique sans impact sur latence, coût, débit et contrôle.

### Modèle vs moteur d'inférence

- **Modèle** : poids, architecture et capacités apprises.
- **Moteur d'inférence** : runtime qui charge le modèle, gère les paramètres d'exécution et dialogue avec le matériel ou le serveur.
- **Frontière** : changer de moteur peut modifier performance, contraintes et intégration sans changer le modèle.
- **Confusion à éviter** : croire qu'un "bon modèle" garantit seul un système utilisable.

## Questions à traiter

- Quels concepts sont centraux pour le domaine ?
- Où commence et où s'arrête chaque concept ?
- Quelles confusions doivent être empêchées avant la rédaction ?
