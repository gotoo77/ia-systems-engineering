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

- **Modèle** : composant qui transforme une entrée en sortie selon des paramètres appris.
- **Inférence** : exécution d'un modèle pour produire une sortie.
- **Moteur d'inférence** : couche d'exécution entre modèle, matériel et application.
- **Token** : unité manipulée par le modèle.
- **Contexte** : information visible par le modèle pendant une inférence.
- **Mémoire** : information conservée ou récupérée hors de l'inférence immédiate.
- **Embedding** : représentation vectorielle utilisée pour comparer des contenus.
- **Indexation** : organisation de contenus pour les retrouver ou les relier.
- **RAG** : pattern combinant récupération d'information et génération.
- **Outil** : capacité externe appelée par un système d'IA.
- **Agent** : boucle de décision qui poursuit un objectif avec état et outils.
- **Orchestrateur** : composant qui coordonne modèles, outils, mémoire et règles.
- **Observabilité** : capacité à comprendre le comportement du système par traces et mesures.
- **Évaluation** : jugement structuré de la qualité d'un comportement ou d'une sortie.
- **Assistant de développement local** : système appliqué combinant modèle, outils, dépôt, tests et contrôle utilisateur.

## Frontières à clarifier

- Contexte vs mémoire.
- Embedding vs indexation.
- RAG vs mémoire.
- Modèle vs moteur d'inférence.
- Agent vs orchestrateur.
- Outil vs protocole.
- Benchmark vs évaluation.

## Questions à traiter

- Quels concepts sont centraux pour le domaine ?
- Où commence et où s'arrête chaque concept ?
- Quelles confusions doivent être empêchées avant la rédaction ?
